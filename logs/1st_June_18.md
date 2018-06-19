## User Feedback Meeting 2018-06-08: Tooling Feedback Session

### Links

* **Recording**:https://www.youtube.com/watch?v=8NCutuQx5Qk 
* **GitHub Issue**: [#68](https://github.com/nodejs/user-feedback/issues/68)
* **Minutes Google Doc**: https://docs.google.com/document/d/1bP7fdN-mf47SJcNEfWm_F2EbcpSgDEEyw4tIhRMDpPg
* **Discussion focused on tooling** [59](https://github.com/nodejs/user-feedback/issues/59) 

### Time
* Friday, June 8th 2018 16:00 UTC
* Attendees
  * Michael Dawson (@mhdawson)
  * Dan Shaw (@dshaw)
  * Christopher Hiller (@boneskull)
  * Agiri Abraham Jr (@codeekage)
  * Mihai Ene-PIetrosanu (@mihaiep)
  * Chris Barber
  * Gus Caplan
 
### Notes
* We will gather user feedback from Tooling group. For this session, I've selected a few "hot-button" issues from #59 
  which we will   discuss:
  Cross-platform problems (fs, child_process)
* Chris H ->fs.watch does not work like it expects, may only work on linux. Userland modules have sprung up to fix some
  of these  problems.
* Chris B -> need recursive file watching, but linux does not support it, they have to maintain code to manage watching.
  Need to be able to watch files that don’t exist, broken symlinks, those that have permission changes.  Wrote library 
  that does it the hard way, only watch directories to keep numbers of messages down.  Widows emits 3 events, 
  linux/osx only 2. Tested 27 file system watches, and none could watch files that did not exist.
* Chris H, looking at how python handles this, does not have an equivalent. Some third party tools like watchdog, 
  or facebooks watchman.  Sounds like a difficult problem to get right and consistent behaviour across platforms. 
  May be difficult, don’t care if it’s hard, need it to be fixed.  Struggle with shipping native code, requirement 
  for compiler is too much. 
* Tierney, Chris H can you provide some context.  Work on Titanium mobile sdk at “accelerator something”. 
  Built service that runs in the background (similar to adb), need to watch if install new xcode, connect device to machine etc. 
  They listen for changes and broadcast changes to listeners.
* Chris B, are you shipping Node.  Before no but now yes. Daemonized process runs using version of Node that they 
  downloaded (or installed as part of their offering).  They use node-pre-gyp.  Started by building native addons 
  and building into with their package.   They actually strip out just the Node binary (minus npm, etc.)
* Chris H, seems like issues are beyond just fs watch, difficulty with native modules , Chris B you also mentioned
  some more cross platform issue (os.arch)
* Chris B, if you run 32 bit on 64 bit machines it returns 32 bit as opposed to the architecture of the machine itself.  
  (Michael 32 bit dropped in 10.x).  
  fs is missing some key operations (rimraf, mkdirp, fs-extra, etc.)
* Chris H, a number of modules that do very common file system operations.  Many people report that these should be in core. 
  Also graceful-fs which has a lot of history. Claims to improve cross platform compatibility with windows and some other things. 
  Why do these exist to fix problems in core?  Why fix in userland, does anybody have the history.
* Dan, fs module largely exposes posix API, rimraf/mkdirp are convenience on top, argument was that you can go and create 
  them independently in userland.
* Michael, point in time decision? Do we have more info how? 
* Dan, effort to avoid dead code library (ie unused code), at some point thought APIs would be done but,
  no longer view that we are going to be done at some specific release.  Quite likely just that it is the way it was and just
  there has not be anybody to advocate for since.
* Chris H, agree with small core philosophy, but seems to have become obvious that rimra, mkdirp should be part of fs. 
  Should be focus of what this group can start by championing?
* Dan, we should likely start by focussing on a smaller subset.
* Dan, graceful fs, does not use native code, but does use internals which has been one of the things driving the project
  from letting userland do whatever to being to protect core apis (ie clarify contract).
* Dan, not sure what graceful fs does that could not be achieved in core.
* Chris H, cross spawn, why can’t I use spaw on windows and have it work as expected.
* Chris B, have not needed graceful-fs or cross spawn, do use rimraf, mkdirp, fs-extra.
* Dan, can’t speak to apis, can can speak to why it was developed. Core maintainer of npm
build graceful-fs to smooth over some of the challenges he was having building npm. 

* VM module
  * want to create sandbox, give it to the user and make sure they don’t escape
  * vm2 module tries to do that, but has to do all sorts of terrible things.  
  * Chris H, as somebody working on test, would like to be able to create pool and let test run in isolation,so that can re-use
  * Chirs B, when needing to assemble configuration using a number of modules but would be nice if code running was limited in what they could mess up. Their app allows plugins, want to prevent things like calling exit and would like plugins to be prevented from doing that.  They recently solved by running in a sub-process.  
   
* **From Live Chat:** 
    * from Christopher Hiller to All Panelists: in python: os is low-level fs stuff, shutil is high-level
    * from Gus Caplan to Everyone: so being able to have a complete isolation between you and the 
      “untrusted” code; I was about to mention that process.exit will just kill the thread instead of the process
      i’ve heard that come up before, iirc it was a limitation with v8, it seems like its worth opening an issue
      for though v8 expects you to collect entire isolates not individual contexts;
      thats been such an issue that tc39 is trying to think of some new type apis for it
      as realms come up.
    * also improving communication; vm was never intended to be a security mechanism, 
      and its pretty apparent how many people get confused about it. 
    * it’s that word "sandbox" maybe the language shoudl be changed or there should be qualifiers in the docs.

  * **Upcoming Meetings**
    Node.js Foundation Calendar: https://nodejs.org/calendar
    Click +GoogleCalendar at the bottom right to add to your own Google calendar.
    
