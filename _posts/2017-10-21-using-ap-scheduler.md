---
title: Using APScheduler for cron jobs on Heroku
categories:
- Tech
feature_image: "/assets/images/cron.png"
---

Python has been the go-to language for many developers playing around with data for some time now. In case of pet projects, the data often resides in a remote location accessed through REST API. Or the data needs to be updated periodically. Or the data simply needs computation every time it arrives. For such repetitive tasks, [APScheduler](https://apscheduler.readthedocs.io/en/latest/) is a very handy Python library that can be used to design [cron](https://www.dyclassroom.com/reference-server/how-to-create-a-cron-job) style jobs to execute at a later time.

When it comes to pet projects, [Heroku](https://www.heroku.com/) is a reliable platform to host your web app with its free tier. There are options like Heroku Scheduler add-on to schedule jobs. I’m going to describe how to use APScheduler to achieve this. For the explanation, I’m using a Flask app as a reference.

Firstly, you’ll have to install the library using pip by:

```
$ pip install apscheduler
```

Exhaustive documentation for the library can found [here](https://apscheduler.readthedocs.io/en/latest/).

Now, in root of your Flask app, you can create a file jobs.py as:

<script src="https://gist.github.com/code247/99ed27f22acaf6493172b3365f508a4f.js"></script>

Explaining it line by line, line 1 is the standard import. Line 2 is importing the functions that you have written that you want to run at specific time.

There are different types of scheduler of which BlockingScheduler is the common one and one you will likely end up using.

For each cron-style job you want to create, you have to create a function in your jobs.py file and add a decorator to it specifying the scheduler params.

First parameter is the type of job. Following are possible values based on your requirement:

- interval : This should be used when you want to run a function after fixed number of hours/minutes/seconds irrespective of day/month/year.
- cron : This should be used when you want to run a function at a particular day/month/year at a particular hour/minute/second.
- date: This is used to run a one-off job on a particular date at a particular time.

Some of the other important parameters are:

- day_of_week : Specified using three letter short names. Values can be singular such as ‘mon’, ‘fri’ or range based like ‘mon-fri’, ‘sun-wed’.
- hour : Can be any number between 0 to 23 and can be singular or range based. Examples can be ‘4’, ‘14’, ‘16–23’.
- minute : Can be any number between 0 to 59 and can be singular or range based. Examples can be ‘9’, ‘35’, ‘30–59’.
- timezone : Specifies the timezone to operate the jobs in. Default would be server timezone.

Another example of hour/minute/second specification can be ‘a-b/c’ which implies that you want to run the job between a and b after every c.

E.g. run a cron job every 15 minutes between 12PM to 4PM on weekends would translate to (‘cron’, day_of_week= ‘sat-sun’, hour = ‘12–16’, minute = ‘0–59/15’, timezone = ‘America/New_York’)

After specifying the jobs in jobs.py, you have to add it Procfile so that Heroku would allot a ‘clock’ dyno to it. The Procfile would look like:

```
web: *command to run your flask app*

clock: python jobs.py
```

The final thing to do is scale the ‘clock’ process so that there aren’t multiple dynos doing duplicate work. This can be done thru Heroku CLI by:

```
$ heroku ps:scale clock=1
```

One issue that may arise when using the free tier of Heroku is app being put to sleep. Heroku puts your app to sleep after 30 minutes of inactivity to manage its resources. If you want to perform certain tasks irrespective of the traffic, this is a roadblock as the clock process will be put to sleep as well.

Fortunately, there is a workaround. There are services that ‘ping’ your app to wake it up after specified period of time. One such simple service is [https://kaffeine.herokuapp.com](https://kaffeine.herokuapp.com) You can specify your app name and it will give your app some ‘kaffeine’ every 30 minutes. Also, you need to specify what time it should not ping as there is a mandatory 6 hour sleep rule for Heroku free tier apps.

Hope this walk-through helps your pet projects and lets them grow further. Cheers!
