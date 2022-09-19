---
title: Software Engineer Interview Guide
categories:
- Tech
feature_image: "/assets/images/job_search.jpg"
---

Love it or hate it, anyone looking for a gig as a Software Engineer has to go through the gruelling Tech interview loop before landing that lucrative offer. As of writing this in late 2022, many have complained about the way tech interviews are conducted without offering a working alternative. So here is me documenting my experience while going through it earlier this year.

### Getting used to the environment

Even if you're great at anything, when someone is watching you do it over your shoulder, most of us are more than likely to slip up. This is no different when it comes to tech interviews. So the thing that can be most helpful is getting used to the environment where someone is evaluating you. 

The easiest way to go through this _immunotherapy_ is expert mock interviews like [interviewing.io](https://interviewing.io/). The more economical way is peer-to-peer mock interviews. [Pramp.com](https://www.pramp.com) is a blessing which helps you setup hour-long session with an anonymous peer wherein you end up interviewing each other. This not only helps you hone your problem-solving skills when put on the spot but also gives you the perspective as an interviewer and observe the typical mistakes that are common across candidates.

Another obvious antidote to this is to just appear for more interviews. If you're taking this route, it's important to not go for that dream company (if you have one) or top tech company too early before you have put in enough yards.

Eventually, the goal is to not feel any kind of nerves during the interview. This will help you put all your energy into actual problem-solving and block out everything else as noise.

### Coding Assignment

If a company expects you to spend 2+ hours on a coding assignment before any engineer talks to you, don't bother spending time on them and seriously make a hard pass (if your situation permits).

### Coding Interview

Most of us are not acing coding competititons week-in week-out. So the straight-forward way to be war-ready for this is what they call _leetcode_ grinding. It's not just the amount of problems that you solve but make sure to cover a wide variety of them as well as be able solve to them in reasonable amount of time. 

Do your due-dilligence about the kind of questions each company goes for. Most sane companies won't ask you Dynamic Programming questions. Also, not all of them rely on inverting binary trees as some may want to test you on your design skills, code modularity or tackling an ambiguous problem. Typically smaller companies tend to ditch the DS&A Qs for Object-oriented design type questions. Various forums like Leetcode, Glassdoor, [Blind](https://www.teamblind.com/) and [Reddit](https://www.reddit.com/r/cscareerquestions/) are helpful to gauge difficulty levels as well as get curated Qs [list](https://leetcode.com/discuss/general-discussion/460599/blind-75-leetcode-questions).

The most hammered point about these interviews is to _think out loud_. If you're one of those people who can't think and talk at the same time, ask the interviewer that you would like a couple of minutes (not more) to grasp the problem and then summarize your thoughts. When you feel clueless about a question, remember not to panic. There are only a handful of strategies which can be employed. So start thinking about which data structure can be employed there (most of the time the answer will be a [hashmap](https://www.youtube.com/watch?v=5bId3N7QZec)!). If not a DS, evaluate which one of the typical strategies (Recursion, Divide & Conquer, Two pointer, Binary search, BFS/DFS etc.) can be leveraged.

When it comes to producing actual code, I would highly recommend using Python as imo it is the most interview friendly programming language. Ensure that you stick to best-practices with regards to variable / function naming, code modularity and in general code readability. If you're copy-pasting certain snippets in the interest of time, make sure to clarify that you would write a function for this otherwise.

### System Design Interview

As you graduate out of entry level positions, this is the type of interview that will make-or-break your loop. Typically, you'll be asked an open-ended question to design a real-world software system. Often this doesn't have a set answer and you'll end up responding "_it depends_" a lot of the times. A successful system design interview is being able to clearly articulate various trade-offs that come at each decision point. 

[system-design-primer](https://github.com/donnemartin/system-design-primer) is a great resource which covers all aspects about the domain. There are a ton of great Youtube channels as well that cover most of the typical questions. [System Design Interview](https://www.amazon.com/System-Design-Interview-insiders-Second/dp/B08CMF2CQF) is a great resource which I found quite helpful to read through. Another popular paid resource is [Grokking the System Design Interview](https://www.educative.io/courses/grokking-the-system-design-interview). When reading through various resources, if you come across an unfamiliar term, make sure to double-click on it and dig deeper to read other related content. There are plenty of great Stack Overflow answers about each concept which provide you the valuable nuance. All you need to be is curious.

This interview will typically run for an hour. When starting out, it's helpful to have a rough template of things you're planning to talk about such as Functional / Non-functional requirements, Data estimation, Data modelling, Design Deep Dive etc. Once this is done, the interviewer might choose to focus on certain aspect which might be important for the position. Given most of the interviews are virtual nowadays, make sure you're comfortable with a digital whiteboarding tool (shoutout to [Whimsical](https://whimsical.com/)).

### Debugging Interview

This is a new type of interview that a lot of companies are starting to incorporate in their process. The basic idea behind this is to evaluate your debugging skills which are often a lot more relevant to the job than solving esoteric puzzles. The nature of debugging can range widely here. It could be failing tests in an open source library or a failing docker compose setup or an unresponsive production service. 

Again, the idea is to not find a needle in a hay-stack but more about the process you employ to find that needle. There is not much preparation you can do for this kind of interview apart from coming across a lot of different kind of problems. You're allowed to _Google_ stuff as you would in a real world setting. The overall interview ends up being a process of lifting & inspecting a lot of stones to figure out what could be wrong. The evaluators will be noting down various strategies that you employed and how effectively you justify them.

### Behavioural Interview

A lot of folks tend to just plan to tackle this on the fly which can backfire. Although I don't recommend blurting out memorized answers, it certainly helps to list the various talking points beforehand. Writing stuff down is underestimated. Jot down all your exeperiences so far be it positive / negative and then devise a plan to use them based on the use-case. The STAR framework is a reliable for dividing up your response.

It's worth paying attention to the job posting which often reflects what the hiring manager is looking for. So make sure to pitch your related experience upfront. 

### Landing the offer(s)

Finally we're at the point where all your persistence pays off and you land that sweet offer email! A crucial thing when it comes to this stage is to have multiple (at least two) offers at the same time if possible. This gives you a lot of leverage to negotiate and not be low-balled. Even in 2022, finding and recruiting good engineers is draining for companies in terms of resources. So there is always going to be some room for asking for that level bump or a sweeter compensation. 

The same forums listed above plus [levels.fyi](https://www.levels.fyi/) are handy tools at this stage to make sure your offer is market comptetitive. In the end, your final decision shouldn't just be based on monetary factors but also incorporate things such as company trajectory, work-life balance, job security (if on a visa) as well as work-satisfaction.

### Final Points

First of all thank you if you got this far. To wrap up, there is a significant element of luck involved in all of this. You might be able to score 5 heads in a row but over 100 coin tosses, the numbers are likely to average out. Your task is to minimize the variance as much as possible by taking as many shots as possible. At the same time, be mindful that no outcome defines you as a person and is just a result of circumstances at that point. Good luck!
