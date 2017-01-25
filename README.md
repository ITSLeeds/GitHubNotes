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
  3. a propriatory social net layer managing pull requests / contributor histories

To be wary of:
  - GitHub is a for-profit VC backed company, the VCs value it at 2bn USD and will want to exit and take profits
  - how will they do this?
  - the value must all be in the social network data 
    - like other propriatory social nets we must presume they will be mining and selling this
    - like other propriatory social nets it may be hard to leave once linked your social cpaital into it

Alternatives to Github:
  - GNU Savannah - is completely open source kosher
  - GitLab - opensource community version that you can host yourself
    - but criticised for pushing propriatory "enterprize" version off it
  - just use git -- but github's pull req managment and social net are quite nice
  - maybe one day someone will link up GNUSocial to Savannah and make a more similar competitor


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
  3. either a) email patch to project maintainer or
            b) beg project maintainer to give you commit priviledge, then svn commit 
)


Warning: if you make subsequent pushes to yoru personal fork after sending the pull request, these will automatically be included in the pull request!  eg. you might fix a bug, push, send pull req, then test a crazy experiment on your own fork the next week . If the upstairs maintainer doesn't read their email for a week and opens your pull request after your crazy experiment, then the crazy experiment will appear in it as well as the original bug fix.   Soultions to this include:
   1. make multiple branches inside your personal fork, for master and CraszyExperiment
   2. make two personal forks, one for bugfix and one for crazyexperiment, where crazyexperiment is a second fork off of the first bugfix fork.
   3. work only on your local git clone not on your github fork for the crazyexperiment (though this won't get your crazyexperiment backed up.)

branching is an SVN and git level concept; forking is a gitHUB level concept. (as it would be on sourceforge, though would require creating a whole new project there). Computationally branch and fork are the same but socially they are different. Any kid can make a fork of the linux kernel, but only trusted team members can made a branch. A branch exists within the official version and a fork does not.
