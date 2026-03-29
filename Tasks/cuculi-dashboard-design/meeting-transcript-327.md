Dashboard Development Planning
Friday, March 27

The team discussed the progress on implementing Mixpanel for better observability and user tracking. Cristian is working on the notification service, while Paul is integrating Mixpanel into the application. The goal is to create a real-time dashboard using Mixpanel to track user engagement and marketing effectiveness. They plan to meet with Yuka to define strategic objectives and key metrics, such as user engagement and conversion rates. Chris emphasized the importance of actionable insights and suggested creating a design for the dashboard. They also discussed using Mixpanel's API for real-time updates and its integration with MongoDB and cloud code.

Transcript
https://otter.ai/u/qkWmF_bMJ07br-iyKZZY0VEv5Kw

Action Items
• [] @Chris Cruz - Schedule and hold a meeting with Yuka to define the strategic objectives, core business questions, key metrics, targets, drill-down paths, and actionable insights needed for the engagement and user growth dashboards.
• [] @Chris Cruz - Review the Engram repository and tool referenced in the meeting to understand how it can be used to build centralized agent memory and improve team productivity.
• [] Finish implementing the Mixpanel event tracking in the notification service and ensure it correctly captures events such as notification sends (push/SMS/email) for Leo users.
• [] Send Chris access credentials or login details for the Mixpanel project so he can explore its features and data.
• [] Compare Mixpanel's current configuration against MongoDB to verify whether Mixpanel is directly connected to MongoDB and identify any missing pieces that need to be resolved.
• [] Add Mixpanel event tracking to the web application next week, extending the existing Mixpanel instrumentation across the app to support customer journey analytics.
• [] Share the Engram repository and related materials from the mentioned AI developer with the team as a reference for development workflows and agent memory.
• [] Investigate and resolve any remaining issues with connecting Mixpanel to MongoDB, ensuring reliable data flow between the two systems.

Outline
Implementation of Notification Service and Observability
• Cristian Guerrero discusses the progress on implementing the next panel Avi on the notification service and setting it up to track notifications effectively.
• Chris Cruz emphasizes the importance of having better observability to self-improve and mentions the potential for automatic improvement over time.
• Jose Velasquez asks for help in building a useful dashboard using Mixpanel, expressing a need for real-time monitoring for Luca.
• Chris Cruz inquires about the specific reasons for choosing Mixpanel and the data sources involved, such as MongoDB.
Choosing and Integrating Dashboarding Tools
• Jose Velasquez explains the plan to use Mixpanel API to centralize information and mentions the addition of smart events.
• Chris Cruz highlights the importance of selecting actionable and insightful metrics for the dashboard.
• Adrian suggests expanding on the current implementation and mentions the ease of developing a good dashboard with access to raw data.
• Jose Velasquez plans to create a dashboard to follow the entire customer journey and suggests meeting with Yuka to discuss metrics and strategic objectives.
Defining Metrics and Strategic Objectives
• Chris Cruz proposes creating a design for the dashboard, including metrics, graphs, and the reasons behind them.
• Adrian mentions his experience with Pulse Hog and suggests expanding on the current implementation for time efficiency.
• Jose Velasquez emphasizes the need for Yuka's input on strategic objectives and key metrics to track user engagement and growth.
• Chris Cruz outlines the steps to define key metrics, conversion rates, and the importance of having goals and targets for tracking improvements.
Next Steps and Collaboration
• Jose Velasquez and Chris Cruz discuss the importance of Yuka's input in defining the dashboard's design and metrics.
• Chris Cruz suggests setting up a meeting with Yuka to confirm requirements and show her a few options.
• Cristian Guerrero looks forward to the implementation of Mixpanel, which will enable powerful segmentation and user growth.
• Chris Cruz expresses excitement about Mixpanel's features, such as notifications for triggers and the ability to generate reports.
Exploring Mixpanel Features and Future Plans
• Chris Cruz inquires about Mixpanel's ability to answer questions through cloud code and its connection to MongoDB.
• Jose Velasquez confirms Mixpanel's connector with cloud code and its potential to provide real-time updates on user actions.
• Chris Cruz plans to check out Mixpanel's features and expresses interest in using it for tracking user behavior and generating reports.
• Jose Velasquez mentions the roadmap to create a standardized workflow and repository of skills for the development team.
Discussion on Skills and Repositories
• Chris Cruz introduces the idea of creating a repository of skills, such as publishing and writing, for the team to tap into.
• Jose Velasquez and Cristian Guerrero mention their limited experience with skills but express interest in using them for development.
• Jose Velasquez shares his plan to create a standardized workflow and repository of skills after finishing the migration to the infrastructure.
• Chris Cruz mentions his interest in tools like Memzero for vectorized memory and plans to check out Engram, a tool recommended by Jose Velasquez.
Meeting Conclusion and Next Steps
• Chris Cruz summarizes the next steps, including meeting with Yuka, defining metrics, and building the dashboard.
• Jose Velasquez and Cristian Guerrero express their readiness to implement Mixpanel and track user behavior effectively.
• Chris Cruz plans to stay connected on Teams and mentions his upcoming travel to Japan.
• The meeting concludes with a positive outlook on the next steps and the potential benefits of using Mixpanel and Engram for the team.




Jose Velasquez (Cuculi Engineer) 0:00
Or not. So, yeah, Christian, if you want to mention your progress about this will be good.

Cristian Guerrero (Cuculi Engineer) 0:07
Well, it's pretty much still work in progress. I've got to, as you said, to implement the next panel Avi on the notification service, and I've been working on set it up nicely to be able to use it to track correctly Leo notifications. Once we have that ready, we'll know a lot more about how is it working, or how are not just working for the user.

Chris Cruz 0:50
Nice, perfect. Yeah, that's going to be a great Intel to understand that. And I think that'll be also another great input to, you know, an LLM to self improve. You know, after once we have that better observability, we can have a self improving process where it assesses, you know, the metrics all the observability you guys are, and then the process can just automatically improve over time, including the profit

Cristian Guerrero (Cuculi Engineer) 1:33
stuff. So very much looking forward to that. I think shows show us, it will be really helpful to have that message done and those analytics ready for that. Yeah,

Jose Velasquez (Cuculi Engineer) 1:54
I have a question for sorry for you, Chris or maybe Adrian. We know about which steps need to add for Google in order to have an extensive monitoring system, right, but our concern is, yeah, how to build this dashboard using midspanel in order to have a useful dashboard. We are new is with that. So if you know how to use that tool, or if you can help us building this will be amazing, because my idea is just provide a real time dashboard for Luca. So we will need somebody to build this, maybe a broad person or something like that. Maybe, you know, please, I don't know.

Chris Cruz 2:54
Yeah, no, I think such a great question. I have a couple thoughts on it, but my first question is, so you said a mix panel, is that the tool that you want to use, and is there a reason for why you want to use that tool?

Jose Velasquez (Cuculi Engineer) 3:14
Any particular reason? I just see the tool. I see we can integrate all our provider, Stripe, magic, one signal. So I use thinking the long term to have an Excel observability. So, yeah, that's, that's why I take its panel. I I know that we have falsehood I believe, but it's just that I see the tool and the tool achieve like, like my perspective.

Chris Cruz 3:50
Got it. Yeah, I think integrations is definitely one of the best criteria for picking a tool. Definitely want to know what Adrian thinks. You know, the landscape of different dashboarding tools is quite rich. There's a lot of options. So that's why I was wondering, like, what was special about it? And then I did want to ask about the data sources, like, what are the it's MongoDB. What are the what else you said? There's other ones that we might need

Jose Velasquez (Cuculi Engineer) 4:21
our plan is use the mix panel API to start to reach the information, as mentioned Christian for example, for notification service, our planets for each notification start to add the event ID, the user ID and the marketing channel. You know, yesterday we mentioned about send this nudge using Push notification or SMS or email. So we are going to add this Miss panel API on the notification service, just to have centralized that part on the application. For example, we are adding these smart events. I know we have clarity before also, but at the end, it's always the same problem. We have test steps on the application, but we never build a dashboard. But yeah, we are just putting the Mixpanel API in the Keys parts. Christian is working on the notification. Paul is adding for the application. And next week, our planet add this also in the web. So we will have a lot of information, I guess, this time to analyze.

Chris Cruz 5:48
Got it? Got it? No Thanks for that update. Okay, cool, yeah, one of the other things I want to think through with you guys is now that we have a tool to use, like Mixpanel, and it has integrations, really being thoughtful about which metrics we want to track. And also, you know, because, you know, I built many dashboards before, and you can build graphs, and, you know, all these things very easily. But the challenge is, it needs to be actionable and it needs to be insightful. And one of the big things is, with every element on the dashboard, asking ourselves, what's the action that we could take? You know, whether it's, yeah, so I think, I think what we could do, what I'd like to do with you guys, is first, like craft, create a design, just the front and just like a, you know, can be really quickly, vibe coded like. This is what we want it to look like. These are the metrics we want to track. These are the graphs we want. And this is why, you know, and that'll tell us over time, you know, give us like, make it actionable. So I think that'd be a good exercise for us to do like from a design perspective. And Adrian, I'd love to get your opinion on it too around like building the best dashboard that can help us accomplish, you know, our objective of more engagement and more users,

Speaker 1 7:15
right? So I been using pulse hog in the in the past, as Jose mentioned before. So I don't have experience with Mixpanel, so I say, if you guys are already using that, maybe, maybe we should expand on what's being implemented already, just for the sake of time. But currently, it's not that difficult to if we have the data, the access to the raw data. It's not difficult at all to just have a good dashboard developed by cloud code or coding, as long as we whatever.

Jose Velasquez (Cuculi Engineer) 8:09
Okay, okay, because you know what the tools are, just a manner to create dashboard. It's not just a single dashboard. So my plan the first dashboard is just one to follow the entire customer journey. When you when we use the notch we have like we plan the algorithm to track everything. So this is just the fish, the first dashboard. Guys. I mentioned this before. If you can meet with yoga and talk about these metrics, it will be helpful. I for example, something that I mentioned to you guys, in order to do cool cooling road, it's, yeah, it's about, we need to have metric which restaurant is most popular, top user. For example, Chris. I mentioned to you guys, hey, how we can identify a possible host. So what I need from you, Adrian and Chris, just maybe, if you can schedule an hour with yoga to get to write these answers, these questions, and maybe I can do a better job, because I indicating that they think, hey, I need these steps. But you know, this require business, so if you can help me with that, will be helpful. So it's the only thing I need.

Chris Cruz 9:57
Yeah, absolutely. I love Adrian's point on that. It's easy to do with quad code, too. I mean, that's an option, but, yeah, regardless of the tool, I appreciate that what you're mentioning, because I think that is a good next step is meeting with Yuka. And essentially, what I want to do is, you know, walk with your ask a few questions. Number one, what's the strategic objectives? Which I think, you know, I think, I think we've been talking about them for some time around engagement, one

Speaker 2 10:28
user, please. Perfect, only objective,

Chris Cruz 10:33
perfect, awesome. That helps with that. Okay, so strategic, objective, number of users, that's the best metric we can track. So then the next, next set of questions around, you know, the what are the core business questions that we need to ask about these users? Like, for example, you know, I guess we need to know whether they're new or not. You know, how do they hear about capoe and what messages did they get? You know, because once we get these users, we need to know what's working about them, what's not working about them. So I think getting into, you know, the business questions there and then, and then defining the key metrics that you know, maybe the top three or five metrics that help us determine, you know, how we get the most users. And I think it's going to be simply conversion rates, you know, I think if it's user, it's innate law of numbers. It's a law of conversion, you know, the funnel, you know, tracking it from the point that they just got the first message to the point of them clicking through to the point of them, you know, actually opening, you know, clicking on the joint event, to the point of, you know, spending money so and then having targets, most important, you know, after that, having goals and targets so that whatever whatever actions that we perform, whatever changes we make, that we can ultimately, you know, track improvement, you know, if it's working versus it's not just kind of like the way Yuka was already kind of doing it, and then the and then finally, after that, it's, you know, making it drillable. Because what's going to happen is, when we get these metrics, we're going to ask more and more questions, and it's going to be very important for us to be able to dissect all the numbers and looking at the elements, so looking at the drill paths, and then finally, like the actionable insights. So anyways, we'll do that with Yuka. That way we can define those, you know, define what the dashboard should look like. And then once we have that, we'll have a nice design, and then we can build it with whatever.

Jose Velasquez (Cuculi Engineer) 12:44
Yeah, exactly, yeah, I think, yeah. Here's where the nidr take more value after now, Julia thought we can build this dashboard using code. I absolutely agree with that. But, yeah, we need just the Yuka idea, so just painting a little drought with her. We can, you know, we can work with clothes after that.

Chris Cruz 13:17
Yeah, yeah. What I'd like to do too is like, you know, set up some time with Yuka, you know, do a little have a meeting with her, confirm the requirements, what the outcome is, and then also maybe show her a few options too, you know, and we can move from there. So, yeah, cool. Perfect, perfect.

Jose Velasquez (Cuculi Engineer) 13:44
Yeah, okay, I think on our side, we don't have any any other update,

Unknown 13:54
and we're looking forward to the at least at this stage of the

Cristian Guerrero (Cuculi Engineer) 14:01
mixed implementation, because we'll be able to basically track everything. We'll be able to do even more powerful, like segmentation for the type of future or, yeah, that would be a really great, I think, for police and have that there is a lot of ways to make use of it. Of course, for those type of user, there will be different types of marketing, right? If we manage to get all that information and use it correctly, I think that would be for the growth, for the growth of the business, yeah, absolutely.

Chris Cruz 14:46
A few other things on mix I'm looking forward to checking out mixpan. I've only heard about it. Some other features I'm looking, you know, to see if it has the ability to notify if, you know, certain triggers, certain things happen, you know, and then also the ability to generate, like, I know it's a dashboarding tool, but I I wonder if, like, if it can generate reports, because oftentimes you have a Live, a live dashboard, but then the problem is you can't. It might be harder to see that. You want to see it over time. You want to see the numbers change over time, and I'm wondering how, especially for calculated metrics, you know, I'm looking forward to seeing if it has, if it can help us with that.

Jose Velasquez (Cuculi Engineer) 15:34
Good part about mid planet is that have a connector with Cloud code. So nice.

Speaker 2 15:42
That's nice. That's great, interesting, yeah, yeah, for you, for Alex, yeah, it will be amazing.

Chris Cruz 15:52
Yeah, if it does that, that's pretty cool. And I'm wondering if could you ask it questions through cloud code, like, let's say everything's connected to mix panel. You just wanted to know a number. You know, off the cuff, like, you just had an idea. You're curious about something. Could you ask? Ask it a question, and then could it answer

Speaker 2 16:16
looks like the answer is yes. Awesome. Love that, yeah, yeah. This gives me a lot of ideas,

Jose Velasquez (Cuculi Engineer) 16:31
because we cannot step for everything if we connect with the stripe. We can know when a user

Speaker 2 16:42
notes pay again, oh, my God, this is good. This is good, nice.

Chris Cruz 16:51
That's great. Cool, good stuff. Yeah, I'm looking forward to checking it out. Do you? Could you guys share a login or, or, I mean, provide me access. Yeah, I will send you. I will send you. Yeah, okay, cool, nice. That's great. And mix panels also connected to MongoDB, right? Like, it can, is that, right? Like, is it all connected, or is it still we're being we're just getting started, right?

Jose Velasquez (Cuculi Engineer) 17:21
Yeah, we used to start it, so I need to compare.

Unknown 17:41
Yeah, looks like direct connection, but we can, we can do something we always solve.

Chris Cruz 17:53
Yeah, awesome, great meeting. Yeah, looking forward to checking this next step. I'm going to be away up a little bit, but I'm going to work on this is really exciting. You know, meet with you, and then after that, I'll be in Japan. So I don't know if I'll be able to meet again this upcoming Friday, but let's stay connected on teams and stuff. Sounds good, I guess only the thing was around, you know, Christian and I, we met last week. We're talking about skills, building a repository of skills. You know, agentic skills is all the rage lately, for good reason, and was thinking about that, and wanted to know what you guys thought of creating, like, you know, a set of shareable skills that we could all tap into, whether it's skills for, you know, for for me, I'm going to be using it skills for publishing and skills for writing and all these other types of skills that I'm thinking. But have you guys? I'm sure you guys are using skills in a variety of ways. Or how are you guys using it?

Jose Velasquez (Cuculi Engineer) 19:08
On my side, yes, I don't know, Christian or the thing, the thing is starting to use local. So, no, not sure. Yeah, my side

Cristian Guerrero (Cuculi Engineer) 19:19
just started using skills, but it's really for develop

Jose Velasquez (Cuculi Engineer) 19:26
skills, specifically something that I want to do with a development team I was, I have been following Argentinian guy who is a beast To be honest on when we talk about AI and this guy provide a set of technology and open source technology about how we stand, how create a standard inside development team. And to be honest, it's incredible. I will send a repository because, for example, he provide a tool called Engram is basically, it's a database based on SQLite to keep the memory of the agents in the in the laptop. But these, these Engram tool also allow us to sync using it, so all the team member can have, like, a centralized memory about the mistake that they can do on the code about learnings. So yeah, our plan after finish this migration to infrastructure school, it's focused on creating a standard inside Google about skills, about memory. Yeah, used to be more productive. That's in our roadmap.

Chris Cruz 20:56
Very cool. Yeah, I haven't heard engram. That sounds cool. Though I've been, I've been dabbling with one of the tools I've been checking out a lot is mem zero just to wait memory in a vectorized way. But, yeah, definitely gonna check out engram. That seems like interesting to him.

Jose Velasquez (Cuculi Engineer) 21:14
It's just that I think, Well, men, zero is more for a genetic system, and England is more like for development, workflow, repository, the guy have a YouTube channel. If somebody want to follow it's

Cristian Guerrero (Cuculi Engineer) 21:41
actually talk about, I actually talked with Chris about that video last Friday.

Chris Cruz 21:50
Yeah, awesome. Well, actually, I go in here, guys. Was great catching up. We got some good next steps. Excited for the next step too, getting the stash food in order. So yeah, that's all for me. Perfect. Yeah, great. Thank you, Chris. Thank you, Chris. Thank you, Chris. Bye, bye. Thank you guys.

Transcribed by https://otter.ai