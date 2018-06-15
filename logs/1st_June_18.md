# Node.js Foundation User Feedback Meeting 2018-06-08: Tooling Feedback Session

## Links

* **Recording**:https://www.youtube.com/watch?v=8NCutuQx5Qk 
* **GitHub Issue**: [#68](https://github.com/nodejs/user-feedback/issues/68)
* **Minutes Google Doc**: 
* **Discussion focused on tooling** [59](https://github.com/nodejs/user-feedback/issues/59) 

## Time
* Friday, June 8th 2018 16:00 UTC

* https://docs.google.com/document/d/1bP7fdN-mf47SJcNEfWm_F2EbcpSgDEEyw4tIhRMDpPg/edit 

##

* From Live Chat: from Christopher Hiller to All Panelists:  09:51 AM
in python: os is low-level fs stuff, shutil is high-level
From Gus Caplan to Everyone:  09:58 AM
so being able to have a complete isolation between you and the “untrusted” code
yeah i was about to mention that
process.exit will just kill the thread instead of the process
i’ve heard that come up before, iirc it was a limitation with v8, it seems like its worth opening an issue for though
v8 expects you to collect entire isolates not individual contexts
so being able to have a complete isolation between you and the “untrusted” code
yeah 
i was about to mention that
process.exit will just kill the thread instead of the process
i’ve heard that come up before,
iirc it was a limitation with v8, it seems like its worth opening an issue for though
v8 expects you to collect 
entire isolates not individual contexts

thats been such an issue that tc39 is trying to think of some new type apis for it
as realms come up*

also improving communication; vm was never intended to be a security mechanism, 
and its pretty apparent how many people get confused about it

it’s that word "sandbox"
maybe the language shoudl be changed or 
there should be qualifiers in the docs
