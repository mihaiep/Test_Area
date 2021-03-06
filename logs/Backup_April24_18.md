## 2018-04-27 Public User Feedback Meeting - Enterprise Use Case
### Time
* Friday, 2018-04-27 at 17:00 UTC / noon ET / 11am CT / 9am PT
* Followed immediately afterward by 20 minute private discussion at 18:00 UTC / 1pm ET / noon CT / 10am PT.
### Links
* Minutes Doc: https://docs.google.com/document/d/187IFxgsW8YKoJvKF0Kv27HKaEBFm99WYsbzht32uHVg/edit#heading=h.91romyv4a6yu 
* Recording:https://www.youtube.com/watch?v=AAsHeKsOqCQ 
* Issue [#52](https://github.com/nodejs/user-feedback/issues/52)
* Next team meeting 
* [Tool discussion](https://github.com/nodejs/user-feedback/issues/59)
* [General meeting](https://github.com/nodejs/user-feedback/issues/58)

## Agenda
* This is a public User Feedback meeting with invited participants focused on specific topics. 
  Please feel free to propose discussion items for the agenda related to this topic below. Create a new issue to propose a new topic. 
  Normally, @nodejs/user-feedback team meetings are extracted from neuf-agenda labelled issues and pull requests from the user-feedback 
  repo prior to the meeting.
 * Topics:
   * Round table Introductions:
   * Who are you?
   * Where do you work?
   * What do you do?
   * Describe your Node.js. Enterprise Use Case
   * What's working and what isn't for Node.js in the Enterprise?
   * ✋ Raise hand to join the discussion
 * Open feedback forum
### Invited
   * **User Feedback team members** 
     * Dan Shaw (@dshaw - User Feedback Champion, Mentorship, CommComm)
     * Mihai Ene-Pietrosanu (@mihaiep, User Feedback)
     * Michael Dawson (@mhdawson - User Feedback, CommComm, TSC Chair)
     * Tierney Cyren (@bnb - User Feedback, CommComm Chair)
   * **Enterprise Use Case Representatives**
     * Ahmad Nassri (@ahmadnassri - Principal Architect, TELUS)
### Participants
 * Dan Shaw (@dshaw - User Feedback Champion, Mentorship, CommComm)
 * Mihai Ene-Pietrosanu (@mihaiep, User Feedback)
 * Michael Dawson (@mhdawson - User Feedback, CommComm, TSC Chair)
 * Tierney Cyren (@bnb - User Feedback, CommComm Chair)
 * Mark Hinkle (@mrhinkle)
 * Ahmad Nassri (@ahmadnassri-Telus)
 * Agiri Abraham (@codeekage)

## Notes:
* **Intro by Dan Shaw**
* **Good to have you here Mark!**
* **Thank you, Ahmad, for the great feedback and great Intro!**
* Ahmad: I think the main lesson for me in joining the telecommunication  is seeing how deep and how far the legacy exist, 
  because it’s easy for us in the software world to think about refactor fast, refactor often adopting new technologies, 
  even transitioning a massive amount of users from one system to another or database of other the telecom side of it though 
  there’s physical hardware impact on that as well, so when we talk about people signing up  even on like the website and creating
  a new account that has to propagate its way all the way down to provisioning physical networks and IP addresses and 
  following the packets along the actual network for that account to be activated for your home Internet, to reach your home;
  so that means there is a lot of technologies that have been around for over 30-40 years that we just simply cannot easily replace;
  so that also propagates this way all the way  back up to even our software layers and our ability to integrate and 
  our ability to change the dynamics of how our technologies and software interact with each other. The other thing is the 
  broad spectrum of quote business that we are in as, so typically people of telecom business the Internet provider the cellular
  network provider, perhaps your home TV.
  * I keep discovering parts of business units in the company (Telus is a small, medium size telecom in Canada )
  outside the norm of ISP technologies and cellular networks like we actually offer B2B services (business to business)
  and products that we go in and retrofit entire buildings with networks for business customers; we have a studio part of 
  our business we actually do some video production which is interesting; we have a VC part of the company we actually invest 
  in other companies; we operate multiple brands of our telecom, not just the one brand, so we have subsidiaries and smaller brands 
  of our telecom business that operate as well.
  * We are in IT consulting and outsourcing international call center as well as tech and IT support business. 
    We are in competition with companies like Netflix as it’s probably painfully there’s the old cable business, 
    there’s also the new IPTV business; Google is building fiber networks and spreading Internet connectivity even Facebook 
    is getting into that business as well, that’s direct competition with us.
* Dan: When we talked about technologies, node.js in enterprise, we tend to talk about scale, number of instances, 
  but so much of the enterprise experience is really the different business unit and all that collaborating/competing together,
  since we talked about node in the enterprise in terms of scale , in terms of usage maybe could help us understand 
  how nodes used at Telus and some sense of scale.   
* Ahmad: I’m part of a team within the company called Telus digital and our purpose in our mission is to digitize 
  the hundred-year-old telco, that’s our tagline. We are coming to the table with is modern software practices and more 
  software technology and looking of how we can modernize the entire business all the way from the user experiences 
  down to systems and technologies and infrastructure and somewhere in between there is Node.Js .
  * If you think about it from experience point of view or our case customer interaction as we refer to them and talking about web,
    about mobile, application interfaces Node.Js is obviously that space, so the choice is made for us, in that context 
    it’s easy to say that we are building things on the web, Node, the JavaScript is the platform there is no other 
    choice to be honest; it’s clear enough that where you want to invest you’re hiring you want to invest your skillset growth 
    you want to invest your contribution back to the open-source community, that’s good enough where that happens and how that 
    can be effective.
  * From the systems and APIs an integration layer it becomes even more interesting. We are also on healthcare business, in the IOT, 
    home-security business, those are quite interesting because now all of the sudden you’re talking about a level of governance, 
    security and privacy that is beyond building web applications and mobile applications, so if I’m talking to my peers and 
    the home security line of work or the healthcare infrastructure that’s actually provided as the applications for our healthcare
    professionals across Canada, then there is a whole different level of complexity involved at least from the system’s point 
    of view, so when you look at technologies like Node.Js and compare that to the traditional kind of enterprise IT world,
    Java and .Net, the backend technology they used to refer to them the challenge is entirely and mostly from my perspective
    is in the scale of the talent, not the scale of technology. At the end of the day you can build anything you want with 
    any programming language you want; the effort might different, but the things that makes the effort harder or makes or
    brakes the bank is the level of apatite from the tech community to actually work in these technologies and your access to
    skilled humans in the space to help you scale to the level you ask a lot, so if you want to be a competitive telco 
    business in 21st and 22nd century and continue to be competitive with our markets and all these different things, 
    we cannot misrely on technology that was there from twenty something years ago, we have to adopt[t the latest and the greatest
    and be actually part of the change on the technology itself so open source is key for that, and JavaScript and Node.js 
    are in the heart of it; we can’t be on proprietary systems and proprietary technologies we have to be open source because
    that’s actually attract the right talent and grow our team, that’s where we can actually scale in terms of our ability
    to impact the technology evolution itself; we are in the digital transformations and the digital transformations starts 
    with the humans if we don’t have the right culture then technology and architecture it doesn’t really matter.   
* Tierney: Questions are around how can I hire more developers, what’s your experiences, what approach you all take cookies to that? 
* Ahmad: The company it’s across Canada, our primary offices are in Toronto and Vancouver, and what I’ve found from a 
  higher perspective, in Toronto is much easier for us to go the marketplace, BTW we are telco and we are using Noide.js
  for everything, that alone made a massive impact and our pipelines for hiring just got flooded; because Node.js is an open 
  source community being very well aware of the value of technology brings. It wasn’t the same in Vancouver because of the competitive
  space in the west coast. Internally we try to do and growing people and have seen massive success in bringing those folks 
  over and have start building things in Node.js, we have a digital platform build entirely on node, collection of infrastructure
  API tooling, front-end components kind of management and NCI CD lifecycle tooling all put together, very measurable and visible
  to their leadership, and more teams are moving to Node.js, that success happened organically, but also we’re investing in more
  mentorship programs more kind of reaching out to the community and being part of the community as well; but not just for the 
  purpose of hiring, but the purpose of contributing back.
  * My team is 350 technologists , but my community of practice within the business is over 2-3000 people of technologists
    and developers, if we can actually get those 3000 people at some point in some shape of form, contribute back to open-source
    community , that’s unique, doesn’t happen often unless you’re a company the size of Google, Facebook, IBM; so this is where 
    I want to start seeing maturity level of the technology adoption and the usage of the language. I think that’s my measure 
    of technical maturity for team members, how do they actually come being first-time Node.js users all the way to actual 
    contributors back into that.
* Michael: What’s working and what’s not working (agenda) , that’s a good place to start in terms of understanding where we might
  prioritize things on our end, if there’s something we can or should be doing differently. 
* Ahmad: We just launched Node.js, but we can’t use it yet. I have a community of practice, developers who are learning 
  and or experts, but I can’t use it in a professional sense, that’s the point, is not LCS yet, we’re not there yet, 
  where can I leverage those two thousand humans and use the most recent version we can provide that feedback?
  What does that mechanism look like and short of people working on site projects, we cannot do something ad-hoc, maybe is 
  something the foundation can have a structure so that organizations can feel they can do something fast and early,
  as opposed to just standard mode of “Node.js is out, great, we’ll just wait for LTS, let me know when you guys are ready”. 
* Michael: You start experimenting with Node.js or just wait for it to be LTS and that’s the first time you start experimenting? 
* Ahmad: As a business I wait until LTS, individually I’ve been playing it for a long time, but I don’t have a mechanism
  to be useful to the foundation and in trying something earlier . 
* Michael: If you have a set of regression tests, you are not going to put in production but you ran those regression tests using 
  Node 10, that would be something that I could see be quite useful as did anything new come up and if does feeding that back into
  the project.
* Ahmad: That’s a structure that I can follow so that’s one item I can add to the list.
* Michael: Do you suggest we would help people if document that somewhere?
* Ahmad: Correct. Provide the mark of that you would expect people can and would do, run all regression tests and see what breaks.
* Dan: Will be great if you can frame as a internal process, open an issue, this /Enterprise point of view.
* Ahmad: There is also things like discovery and exploratory things, do you want to know how many times core call what 
  certain internal APIs because I can go through my codebase and tell you exactly how many times you call file system APIs
  for example and what we use in what we don’t use.
* Tierney: I’d be curios to see how many times you hit the new buffer in your own code or the deprecations that we are shipping;
  before you don’t want to find out about, that once we go LTS these are the major changes that might affect you, is there
  anything additional on top of what shipped in Node.js that we can do to kind of lessen this barrier or create a better path
  for you to upgrade and I don’t think that kind of deprecation happens often, like in my experience it hasn’t,  but getting 
  feedback on, you just run this with your app what like does it error or just run fine?
* Michael: One of the things that we want to do is engage a channel through which the TSC or comm-comm or anybody in the project
  can say: well I’m trying to make a decision and I liketo get some feedback from people who have large-scale production 
  deployments, so how do they put that question together how does it get to the enterprise’s, how do we get the feedback ,
  I think that’s one of the things we should work together on, formalizing that so that’s easy, we come to make a hard decision
  and we say ok, wait a sec, we can get more information which always helps let’s go ask this group over here, and that’s part of
  the motivation of trying to get this group together and sort of making an ongoing thing.
* Ahmad: I did a quick search on new buffer   and I only have 90 results, all probably easily replaceable within a day or less
  in a few hours, so it’s not even a big deal.
* Michael: Having that additional we can bring into those discussions is one of the important things we can work on here.
* Ahmad: If you provide this structure, kind of a playbook for companies to say” here’s something you can do, maybe go search 
  your codes, for the following tell us how many times it’s used, what context is it’s used in. I can do that, and I can provide 
  you that data and then helps, inform”.
* Michael: Having the direct feedback would help us narrow and test out early ideas and options, often we’re looking at things
  like worker support and do we have concrete use cases and places where we can validate that, that’s actually useful that is going
  to be a benefit, it’s another area we’re sort of more proactively if we could come as the enterprise group come together and sort 
  of highlight a few priorities and then work with the project to provide the use cases and the feedback when we have ideas 
  and things to try out.
* Ahmad; for my example to dive deeper, when the blog post went out that security changes, our security patches are coming on
  all major versions, it’s a big deal, and everybody needs to pay attention; there is a level of anxiety and then when announcement
  was made there was a full 24 hour period before we can actually get the latest docker images, because that was we’re running 
  on an infrastructure wise and then because we wanted to use the official ones we didn’t  want to just roll our own and then still
  doesn’t mean that our applications have all been entirely patched and upgraded so that took us another 48hours before everything 
  is updated. What ca you or we work together on, so we can have a better structure for those things.
* Michael: A good discussion/involve security group. Some of the hard trade-offs like: would you prefer to get it later but have 
  some additional notice? (another area of discussion).
  * It comes down if are some concrete use cases where people will see real benefits, and will those benefits be better,
    like can you get significantly better benefits by using multi-threaded worker implementation versus using cluster
    and having multiple instances of node.
* Dan: We’ve adopted that constraint because it’s reasonable one and good one and it matches , you get really sweet spot of single
  compute unit in your orchestration and auto scaling; I wouldn’t necessarily say that we want to heavily index on single process
  as a primary constraint in evaluating the technical use case. One more room for what is working and what is not with Node.js.
* Ahmad: People don’t tend to think too deep about the core, but they do think about performance so that’s important, and then 
  debugging performance and measuring performance it’s definitely key, whatever happens at the core in terms of surfacing 
  user level performance measurement that people can do it and I know debugging tools exist maybe, there’s a little bit more 
  improvements to be made to the API’s for these tools to do surface that data.
* Michael: On the performance side, I’d be interested if you run into specific regression when you moved up from one version
  to the other.
* Ahmad: Personally yes, on different benchmarks that I ran my personal stuff, I don’t have that level of investment in a 
  consistent matter across my enterprise level work with the applications and the teams, primarily because  it’s more taxing 
  to create that kind of level of benchmarking across projects and work, so my feedback is there improvements to the debugging 
  API’s and the measurement benchmark  to surface the data better, because right now to do a core dump and you have to collect
  that data and maybe use some visualization tool to do a flame chart, maybe some more investments from the core to make that 
  more user friendly for none initiated or non-advanced developer who is going to invest a lot of time to do that.
* Michael: What you mentioned come under the work from the diagnostic group is working.
* Dan: The benchmarking WG manages the benchmarking, manages internally with a suite of applications and tests that we’re designing
  and running against our stuff. There is an opportunity to extend that beyond our infrastructure and bring in that data 
  not just is the diagnostic working or are we able to get data.
* Michael: We know we need better documentation for some of that, but it’s been a challenge to find volunteers with enough 
  resources to go through and build that documentation.
* Dan: Would be the opportunity to capture large-scale telemetry? the approach you see in Chrome dev tools or other infrastructure 
  like that?
* Ahmad: The challenge is how effective is that be, how can I make that information useful without being too noisy during due 
  to the continuous upgrades, improvements, deployments that happen, that happen again an area  where you provide the guidance,
  the structure then companies can take that and say ok, I have a framework, I have a playbook, I have the type of information
  that I can provide.  
  * (parallel with http archive.org)
* Michael: What can we sort of document and recommend and ask enterprises can do, validate the current so that the LTS
  is as good as it possibly can be (next topic).
    
  ## Upcoming Meetings

* Click +GoogleCalendar at the bottom right to add to your own calendar.



