# GitHubNotes


ITS github team page:
https://github.com/itsleeds

ITSLeeds is a "team"
	R4TS is a repo (project) (like a sourceforge project)
	GitHubNotes is another repo (project) containing these notes
	each repo can have different owners
	accounts for individuals in it
	ITSLeeds/GitHubNotes is owned and must be approved by Robin

GitHub is not free software - it is a propriatory, for-profit web site
It consists of:
  1. free storage for public git repos
  2. paid storage for private git repos (or free to academic addresses to hook us in)
  3. a propriatory pointy clicky web interface to git (including wikipedia-like web-based editor)
  4. a propriatory social net layer managing pull requests / bug tracking / contributor histories

To be wary of:
  - GitHub is a for-profit VC backed company, the VCs value it at 2bn USD and will want to exit and take profits
  - how will they do this?
  - the value must all be in the social network data 
    - like other propriatory social nets we must presume they will be mining and selling this
    - like other propriatory social nets it may be hard to leave once linked your social cpaital into it

RMS has said that GitHub is bad:   https://lists.gnu.org/archive/html/discuss-gnustep/2015-12/msg00169.html

Alternatives to Github:
  - GNU Savannah - is completely open source kosher
  - GitLab - opensource community version that you can host yourself
  - but criticised for pushing propriatory "enterprize" version off it
  - SourceForge has a git version now (https://sourceforge.net/p/forge/documentation/Git/) though is traditionally used with svn (advantage: is all free software on the server side)
  - just use git -- but github's pull req managment and social net are quite nice
  - maybe one day someone will link up GNUSocial to Savannah and make a more similar competitor (project, anyone?)
  - see https://en.wikipedia.org/wiki/Comparison_of_source_code_hosting_facilities   for full list

github has no download metric like sourcefroge - instead star clicks / likes from named users

"github desktop" app - to sync local disc with github - like dropbox
  - linux -- no desktop app, just use regular git cmds
  - use as dropbox replacement (but would need to write own autosync deamon?)

to access ITSLeeds team:
got to github home page (not personal profile) then dropdon for ITSLeeds
	acting as ITSLeeds rather than as charles-fox 

to change a project:
  1. fork the project on github (using GUI)
  2. clone the forked project to local machine (usually public)
  3. make changes on local machine
  4. commit them on local machine
  5. push to personal fork on github (not to main project) using credentials
  6. send pull request to main project owner using GUI

(To compare with sourceforge -- this would usually involve:
  1. svn download project from sourceforge (using GUI)
  2. make changes
  3. either 
    a) email patch to project maintainer or
    b) beg project maintainer to give you commit priviledge, then svn commit 
)


Warning: if you make subsequent pushes to yoru personal fork after sending the pull request, these will automatically be included in the pull request!  eg. you might fix a bug, push, send pull req, then test a crazy experiment on your own fork the next week . If the upstairs maintainer doesn't read their email for a week and opens your pull request after your crazy experiment, then the crazy experiment will appear in it as well as the original bug fix.   Soultions to this include:
   1. make multiple branches inside your personal fork, for master and CraszyExperiment
   2. make two personal forks, one for bugfix and one for crazyexperiment, where crazyexperiment is a second fork off of the first bugfix fork.
   3. work only on your local git clone not on your github fork for the crazyexperiment (though this won't get your crazyexperiment backed up.)

branching is an SVN and git level concept; forking is a gitHUB level concept. (as it would be on sourceforge, though would require creating a whole new project there, which is traditionally seen as an act of war). Computationally branch and fork are the same but socially they are different. Any kid can make a fork of the linux kernel, but only trusted team members can made a branch. A branch exists within the official version and a fork does not.    GitHub's forks formalize what regular git/svn users do informally -- they clone a major repo, make changes, then send a pull request by email to upstairs.   GitHub replaces the email request with an request on its social network, which also lets other developers see all the requests and responses to them.  Hence one can more easily shame upstairs into doing stuff if there are many requests accumulating without being responsed to.  GitHub also tracks who has forked what so 
that if a project dies it is easier to find if anyone has brought it back.



* How to update your own fork with changes made to the main team version

```
	git clone https://github.com/charles-fox/GitHubNotes.git
	git remote add upstream https://github.com/ITSLeeds/GitHubNotes.git       #tells git that there is a main "remote" version of the repo as well as the fork
	git remote -v         #check its there
	git fetch upstream    #brings in remote changes to a local branch called upstream/master
	remote: Counting objects: 17, done.
	remote: Compressing objects: 100% (12/12), done.
	remote: Total 17 (delta 3), reused 16 (delta 2), pack-reused 0
	Unpacking objects: 100% (17/17), done.
	From https://github.com/ITSLeeds/GitHubNotes
	 * [new branch]      master     -> upstream/master
	 * [new branch]      test-pull-request -> upstream/test-pull-request
	git checkout master
	Already on 'master'
	Your branch is up-to-date with 'origin/master'.
	git merge upstream/master         #merge changes from upstream/master into local clone
	git push origin master		  #store changes to my fork

	(it is quicker just to delete your fork and fork a new one off the main project ?)
```
