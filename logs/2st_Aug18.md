## 2018-08-16 End User Feedback Meeting - Enterprise Use Case
## Time
Thursday, 2018-08-16 at 17:00 UTC / noon ET / 11am CT / 9am PT
## Links
* Youtube recording https://www.youtube.com/watch?v=mDE6G6I180w 
## Agenda
* This is a public User Feedback meeting with invited participants focused on a specific topic, the Enterprise Use Case 
  or Node.js.  Please feel free to propose items for discussion to be added to the agenda below.
* Topics:
  * Round table Introductions:
  * Who are you?
  * Where do you work?
  * What do you do?
* Describe your Node.js. Enterprise Use Case
* What's working and what isn't for Node.js in the Enterprise?
✋ Raise hand to join the discussion
* Open feedback forum
### Invited
* User Feedback team members
* Dan Shaw (@dshaw - User Feedback Champion, Mentorship, CommComm)
* Mihai Ene-Pietrosanu (@mihaiep, User Feedback)
* Michael Dawson (@mhdawson - User Feedback, CommComm, TSC Chair)
* Tierney Cyren (@bnb - User Feedback, CommComm Chair)
* Enterprise Use Case Representatives
* Ahmad Nassri (@ahmadnassri - Principal Architect, TELUS)
### Present
* Dan Shaw (@shaw)
* Ahmad Nassri (@ahmadnassri)
* Mihai Ene-Pietrosanu (@mihaiep)
* Tierney Cyren (@bnb)
* Joel Chen (@jchip)
* Adrian Maurer

### Notes:
* Thank you, Ahmad, for leading this meeting!
* Ahmad: I want to understand a little bit more from everybody, what does it actually mean that you’re using node.js? What are you using? What is the ecosystem for your development tooling look like and is I mostly JavaScript with node.js as an accelerator for tooling or is it you relying on node.js itself for running your backends and your APIs in your systems?
* Joel: We are still a very heavy user JVM We used different script framework like backbone and jquery so when we moved to node.js we were primary thinking of using node.js to back to power react web application, that means node.js has replaced all and powering would react to run the website and in the backend as an orchestration layer to connect to all the backend, so the backend is still based on Java and a lot of our tooling existed as Java framework like we use Nexus with Jenkins for build and we are building new tools in  Java that are complementing the existing Nexus and the Jenkins ecosystem , for example we have teams who built an NPM server on top of Nexus and we have teams who built system on top Jenkins, so node.js is mainly used as an orchestration for the web applications.
* Ahmad: How reliant are you on that middleware terms of your business operations? What’s the opportunity cost for you to even consider trying something other that node.js is that something that you’re heavily invested in, in terms of that matter or being technology reliant on node.js given the front-end dependency or is that just a investment that you’re doing now but you don’t have a dependency?
* Joel: I will say we are deeply integrated with node.js as far as running our websites.
* Ahmad: what would you say the biggest kind of contributing factors for you to be successful and what have been the biggest hindering factors for your success?
* Joel: The biggest factor and is sort of benefit and also a disadvantage, we initially went with node.js from Java because we want to have a unified technology, because before we have to do JavaScript and Java, but the way node.js work asynchronous nature, training has been our biggest thing and we continue to invest heavily in training and to help our developers how to learn Node.js and get up to speed on the entire ecosystem .
* Ahmad: Is there any direct relation to the documentation on Node.js or the kind of guides that exist today from the community that you have benefited more from or seeing lacking?
* Joel: I don’t find documentation lacking and of course I dig into the core more frequently I look at the documentation, but for a lot of our developers the documentation it’s kind of fragmented as far as the documentation goes.
* Ahmad: Adrian, what sort of workloads are you using Node.js for and what has been your success factors and challenges and getting your teams to adopt and use?
* Adrian: Node.js is picking up a lot in that back-end as a front-end kind of style with a lot of the clients and the teams that I’m working on, the companies I work with are heavy into the Java ecosystem they have existing large applications built in Java they want to interface with. There are specific challenges I like to talk about, dealing with complexities maybe in the sharing of certain code bases libraries things like that. Where you have several organizations within these larger organizations each developing libraries or things like standards they want to distribute across broader organization they do that with NPM registries they are self-hosted on their own Nexus  repository then the consumer of those libraries or API libraries that are being developed standards are consumed your regular package; the problem is when you have multiple repositories you set up you specific repository, and call the libraries by name in your package JSON file that creates a lot of headache when we try to do things like creates more of a standard way of delivering software, configurations in those environments become complex when you have to deal with several types of our C files.
* Ahmad: How big is a team and how many applications are you managing?
* Adrian: Teams from two to doze, applications portfolios about two thousandand there is an exponential when you talked about libraries are being published.
* Ahmad: My team right now is about 450, one third are developers and the rest are between QA design and project/business leadership teams, as applications, 800 individual apps and 100 or so libraries that we’ve created and maintained internally.
* Joel: about 300 web developers, 10/12 teams with 10-15 developers but as a global org Walmart has probably hundreds of teams continuously migrating to Node.js
* Ahmad: Any recent examples any recent releases or changes or updates to APIs in the core of node that have directly impacted your team or are directly in your line of sight? Do you just rely on CI/CD tools to just keep those up-to-date for you, how do you keep track of all the changes on the core and do you even invest time personally to look at it?
* Adrian: Things moves slow, now we could talk about containers and passes kubernetes to kind of solve these issues and shift responsibilities a bit left to the development teams we’re not there yet, so being able to upgrade and get the latest patches and things like that it is a bit of a process.
* Joel: We have many people who passively and actively monitoring the changes in the core, for our practice we lock to a version and we don’t update that version unless there’s something that’s measuring; we do update every six months then if there is any security or big release then we would consider upgrading.
* Ahmad: Is there an opportunity to become a feedback cycle loop like at what point are you able to invest something back to the community by either testing those things ahead of time? When you look at stats on NPM and you look at numbers, those are devout of any sort of that business value or consumer value,  you can see how many downloads a certain package has, but it doesn’t tell you that is operating on let’s say Walmart back ends it’s a critical path the delivery for Walmart, how do we surface these things, so that the investment in either the core or the packages around the ecosystem are, given more attention if not potentially more funding.
* Joel: Whenever a major version comes out with plenty of our developers and teams trying out and running their apps and test. We were able to migrate easily, started with version 4 to 6 and then to 8 and 10, if we find any issues we go to core and see, usually some other people run into same issues; definitely we can have a more systematic feedback loop and we can help out on contributing testing new versions.
* Tierney: it sounds like seamless and smooth upgrades between versions, is kind of a key value for you, would you agree with that?
* Joel, Ahmad, Adrian: Yes
* Tierney: I think there are a different kind of enterprises that are using node, there’s ones who are kind of bleeding edge and have this kind of mandate from the top to act like a startup, I’ve hard that multiple times, there’s those ones I think kind of fall line with what we’re discussing here, and then there’s other ones that are much more laggards, I echo that they don’t have the cost concern but it’s more of an expertise concern; what is the benefit for us?
* Joel: For our management it’s always what is the value of that.
* Ahmad: What information can you provide back that can help? For example: do you track your version history and your performance characteristics of your servers and historically look back at those and say if improved or not; do you look at the amount of error rates you’ve been getting of versions of your code, but also versions of what you are running under your code libraries, the tooling and so on? Is there any way to anonymize that data and perhaps publish it somewhere or feed it back to a crusted organization or group part of the node ecosystem, so that can help them to do something better about it?
* Dan: We have the opportunity with this group to make proposals, like the other groups (tooling).  
* Mihai: Ahmad you should open an to follow up or for tracking purposes.
 
* (DanS) Node.js follow-up points:
  * State of documentation
  * Join the Node.js Foundation
* @dshaw I'd also like to add:
  * Security releases and how they affect version pinning
  * Ahmad Some interesting prior art from the CNCF around effectively what we were talking
  * about Ahmad: https://www.cncf.io/certification/kcsp/

* Node.js Foundation Calendar: https://nodejs.org/calendar
  * Click +GoogleCalendar at the bottom right to add to your own Google calendar.








