## Links 

* **Recording**: https://www.youtube.com/watch?v=eiN0gnAJNeU&t=10s 
* **GitHub Issue**: https://github.com/nodejs/user-feedback/issues/58
* **Minutes Google Doc**: https://docs.google.com/document/d/1kswsnzh5ziblp3mcrKS8S3_UPGo7EK5MLybIoDCqxDM/ 
* **Survey for typing**  issue [#61](https://github.com/nodejs/user-feedback/issues/61) 
* Next meeting: issue [#64](https://github.com/nodejs/user-feedback/issues/64)

## Present

* Tierney Cyren (@bnb)
* Michael Dawson (@mhdawson)
* Dan Shaw (@dshaw)
* Aaron Bartell
* Agiri Abraham
* Nikolay Matvienko (@nmatvienjko)
* Aaron Heckmann (@aheckmann)


## Agenda

## Announcements

*Extracted from **neuf-agenda** labelled issues and pull requests from the **nodejs org** prior to the meeting.

### nodejs/user-feedback

* Public User Feedback request - European General User Feedback at WorkerConf [#56](https://github.com/nodejs/user-feedback/issues/56)
* Invite Node.js tooling ecosystem folks to discuss user feedback [#37](https://github.com/nodejs/user-feedback/issues/37)

# Discussions
Gathering use cases to help technical discussions in threading
Building an educational discussion around folks who wants to get started
Survey on typescript 

### Intro by Dan. 
* Aaron entered a set of topics for discussion. 
**Thanks Aaron Bartell, Aaron Heckmann, Nikolay Matvienko for participating!**
* Aaron Bartell: the challenge that we have and it’s on github issue is that IBM i, is traditionally used by a lot of 
  insurance    companies, auto manufactures, banks-medium to large companies that are looking what’s my modernization path, 
  they are reviewing  Node.Js, but are struggling through all the things that they’re reading online, so here’s is the big issue.
  Some of them were true in time, some are no longer true, some are still true, so it’s just trying to find a more exhaustive 
  and authoritative series of articles, that I can point them at, so what to bring up probably the threading and the typing
  some of the biggest ones. 
* Dan: Threading:  that is a discussion, in general, we’ve had around node, interesting phenomenon happening where rather than getting bigger our computing environments are often getting smaller; there is this competing force where so much of the growth that we experienced when Moore’s Law was exponentiating, but unfortunately power has constrained that and how we scale things has shifted from monolithic applications to orchestrated applications; so in those orchestrated applications we now have  frequently thin pods of execution environment that are being scheduled and orchestrated as a part of a larger reality, so if you look at the sort of macro technology changes that have happened around Node, many of the operating environments have been optimized down to single threaded event model as being the more efficient way to compute in today’s operating environment, so my best answer for why Node, in this new operating context, is has nothing to do with Node, it just the world is moving around us into a model that really optimizes for Node.Js and it’s a better fit for the kinds of applications that were writing today, scaling single monoliths has been proven by many companies to be incompatible with the development life cycles they need delivering on today..
Aaron B: So you say that changing your authoring and deployment strategies is probably the biggest thing?  So if somebody’s coming from a Java servlet container background, it’s changing that concept and moving to a new one that’s microservices, are you leaning more towards that way or are you talking  just modularizing your business?
Dan: Modularizing, yes, and I’m not the only voice chiming on this, but I do think that  the pattern that I’ve seen over the past decade for successful software development, has shifted from we're gonna spend a bunch of time trying to figure it out the right way to we’re gonna put something into production as fast as we can so we can validate it in front of our end-users, and that  just changes the way you want to deploy and therefore you’re forced to consider new strategies and that’s why I see things like serverless being a great first step for companies that are looking how they evolve their technology story, so you can just set up a function and route to it and explore new functionality that way and farm away  from some of the your back-end services while evolving your practices. Aaron Heckmann is one of the infrastructure leads at PayPal and they’ve gone through this journey so I started collaborating with them back in 2013, and they went through a C++ to Java journey, and then...kind of tipping point for PayPal was at this moment where they were trying to make a single line of text change in their deployment and it took eight months for that to flow through to production so the front-end team was like:”this has got to change because we can’t deliver the front-end experiences that we need with that sort of lifecycle , so they started with that  as the challenge point and work from there.
Aaron Heckmann: That transition happened before I started at PayPal (a year and a half ago) , but since this change definitely has been very positive for PayPal as Dan mentioned, release cycles were insanely slow, people were very frustrated, something need to be done Node.Js was selected primarily for that reason , and along with that choice of tech, it wasn’t just the technology, was also the mindset behind it, how to use this technology, it enables teams to move more quickly; you don’t need to have  bulletproof plans , you have an idea what you think is gonna work, you get a pretty good version out the door, and then iterate on that , you just can’t do it with multi-month release cycles, so it was a lot of education that came with it. What came with that was Node.Js -enables of being a little move more quickly, so I think it’s been successful as far as that goes at PayPal, and now we’re facing different kind of problems, we’re like how do we want to take it to the next level. It is politics involved, somebody from the top decide it to change.
Dan: the digital transformation that I’ve seen been successful, all had buy-in and trust, you need a little bit of both, you need yes we’re in this but also we’re gonna let those folks take and run with it. Nikolay do you have any thoughts that you wanted to dive in here and touch on threading?
Nikolay Matvienko: We’re working on digital transformation for large ecommerce companies such as Macy’s, Toys’R Us,  and also we decompose our applications to smaller apps, but within each request we do work for CPU , empty collection, logging, SSR server-side rendering, garbage collection, all those execution in the request and box event loop and block servers our web server, so  the solutions that we use is to process or move execution to other child processes so we use stream server-side rendering to do not block event local; there is a thread pool in v8 and it helped a lot, and for APM, matrix collection we also use external process so we just send them and around and collect those in matrix and passed to serious time zeros database. I’m interesting in an ability of any work your API, our application becomes work slowly.
Michael: There’s been some initial work on worker APIs and support that kind of stuff,  the one thing I don’t see that’s come out of that yet, it’s like a real concrete use case that’s says: here’s one where you do this today but we think it would be more efficient if we had in process worker threats and if you can help sort of capture that, that’s one of the ways that I think it would be more useful. Here’s an area where it’s defined use case basically we can use to test out things and stuff like that and make the case for worker threads that would be very useful.
Dan: there is a good example right now and react with async rendering stuff that’s being developed mostly for a front end context, the ability to break up the complex rendering of a page and basically fulfill as needed and then flush to the server is one example.
Michael: So it’s sort of capturing a bunch of those where you could then experiment with, or we could do that today like with the cluster modules; you can say Ok, but then here’s some bottlenecks and then are already NPM packages that will let you use worker threads and stuff we could compare those, just sort of help in terms of the process of making the case for why you need them and why they’re important.
Dan: One thing happening today in front-end Javascript is we’ve introduced in the front-end platform a service worker, and that is an off main thread , and that begins to introduce a whole possibility of compute model for the platform and it’s not quite multithreading, it’s kind of background workers , message passing, it’s a model that is working very effectively in front end and I think there’s a base argument for Node just in we’re going to enable parity for the rest of platform, and then in terms of that you apply that execution model , I think we would look first to how it’s being applied on those environments and then you’ll also see how we can leverage that model for doing more heavy compute, NLP, AI managing infrastructure, the ability to plug those in and not have to design around compute.
Michael: When I think the concrete outcome, is if we can get this group to help with some of the work, if we have from our users or end users like solid and documented use cases that say either we can’t do it today so we’re using something else or we can do it today but it’s suboptimal because we’re using these other things; that’s kind of the piece that’s been missing from the technical discussion. There’s some people: this is a good thing we should have threads and then there's some people well no , does very well without threads , you can already do it with things like a cluster module and so forth, so I think bringing to the table the end user experience to make the case is one of the thing that would help push that forward. This sound like if it’s a concern for  the people Aaron’s working with.
Aaron B: I just share a deck slide where it shows an example of communicating with that RPG business logic so it’s same machine , a different runtime environment same operating system so it’s two different processes so are spanning processes in this scenario, but that could be the case for maybe a use case and this is a frequent use case that’s gonna happen on IBM i. So I don’t know if that would work, it sound like there’s two different things: are we talking about web workers as separate threads within the same process but then also web workers also can be a separate process ?
Michael: You can implement them as threads or processes so there’s advantage pluses and minuses that way there’s the kind of APIs that you need , so today you could use the cluster module or child processes to kick off things that would work on their own. Most people are looking that kind of model where it’s message passing and you have another sort of environment, but even this one you could probably look and say well can we act, could you actually do that with the cluster module by farming it off and then when it’s done: hey here’s the answer and if you could then there’s still the dimension  that well is the ergonomics of that bad enough it’s worth having  a new API that lets you do it much more easily, because it’s a common and important use case in which case like the workers may let you do it a lot more easily without having to have a s much knowledge as so forth , but it’s difficult, it’s like one of the areas where people figure it out but there’s not a good How TO Guide , or here are the cases that we can’t do and I would have moved over to node except I couldn't do this and that’s that having those captured somewhere so we can have as input , I think is where I could see you guys getting in people, getting involved and maybe we can put something together on that front. 
Aaron Bartell: you shouldn't store any business logic in Javascript and I’m wondering if you have a comment on that based upon your experience with PaypPal.
Aaron Heckmann:Lots of business logic is in node apps , but I think the majority is still  in the Java services layer, so I mean that’s  like a historical thing; PayPal has gone through many different evolution and technology stacks, primarily  it was C++ and then Java node. For me personally, I was surprised that there wasn’t a lot in Node, just based on the companies I’ve been working in. Some of the teams are curently considering moving from Java to Node for the API service layer, which is a pretty big commitment, but we are not there yet. 
Aaron B: One of the things I’ve been doing it, kind of further justify this line of thought is put together a list of existing open-source, full ERP or what have you applications  that are larger that have done the business logic thing, but if anybody else had additional open source repositories to add to that are full-fledged business apps, please let me know so I can forward those to these different IBM i companies because I’m constanly facing a littered legitimization  of was it is just of fisher price mode, there’s Node.Js thing can it really be used for these  types of things .
Tierney: Node.Js foundation has actually done a few case studies with major users of Node, I can FW those. 
Aaron B: Those cases aren’t going that deep, so t’s great for CEO, because PayPal went before him and JP Morgan went before him, but once it get down to the geeks, the Java coders that love  their environment today they want to see that justification; so a testimonial of an existing Java coder who gives examples of here’s how I succeeded in my career and helped my business, moving to Node.Js there’s things like that, that could be put on a legitimate site Nodejs.org would mean a lot.
 Michael: If you could capture that list, as a group we could come up with answers. I’m sure once we do that we can get those to Node.Js web sites , because the Foundation is very interested in helping to push those kind of things as well.
Tierney: If you’re interested in machine learning and Node.Js there’s now no tensorflow that was announced at Google 
Dan: I hosted an event up in Toronto and we had Cuhady the CTO of Condenast, come and share some of the ways they're adopted, to modernize the business across the board moved to the platform of the Node to embrace the agility of the platform; they are now incorporating blockchain  and AI and other compute-intensive projects into their ecosystem , and rather than force all of the machine learning folks to adopt node the approach they use around AI is: we’re going hire talented machine learning developers and let them work in the native language they are proficient in, and then everything they deliver to the apps is exposed via API, and most of that’s written with Node.
Debugging Node: Tierney: We need to fully implement source maps. That will help us get debug ability back for those transplant languages.
Michael: I wonder about a survey. What do we need to do to support typing since we now think it’s important and prioritize some of the things that would make that. Kind of questions that tease out that, people want types, but they’re not really gonna  use it seriously until it’s part of the language or is running an extra tool that helps you use them acceptable or not, because it will help us decide where we should advocate; if it’s a project though type is important for the success of Node maybe we should be pushing a TC39.
Dan: Nikolay are you seeing folks adopting typescripts and if so why?
Nikolay: I like a freedom of weak type or streak type in Javascript and in Russia we have a lot of companies that for example use a closure to Node.Js, because they have a closure  developers or types, or Jetbrains. 
Michael: With the group here can we come up with a set of question? (#61)



## Upcoming Meetings
https://github.com/nodejs/user-feedback/issues/64 

* **Node.js Foundation Calendar**: https://nodejs.org/calendar

Click `+GoogleCalendar` at the bottom right to add to your own Google calendar.




