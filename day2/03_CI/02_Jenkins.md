!SLIDE smbullets
# Jenkins

* Standalone self-hosted server (Java)
* Trigger build jobs from git commits
* Start build jobs from specific branches (e.g. daily snapshots)
* Run tests which update your ticket system
* Build packages and deploy them into your repository

<center><img src="../../_images/ci/git_jenkins_ci_git_hook.png" style="width:600px" alt="Git CI Jenkins"/></center>

!SLIDE smbullets printonly
# Continuous Integration: Jenkins

* Standalone self-hosted server (Java)
* Trigger build jobs from git commits
* Start build jobs from specific branches (e.g. daily snapshots)
* Run tests which update your ticket system
* Build packages and deploy them into your repository

<center><img src="../../_images/ci/git_jenkins_ci_git_hook.png" style="width:450px" alt="Git CI Jenkins"/></center>

~~~SECTION:handouts~~~

****

Adding Jenkins to your Git workflow requires additional toolsets.

A Git hook configured on the git server is able to trigger a Jenkins job.
It passes the git commit id to the Jenkins job which runs a local git checkout
and further job actions afterwards, for example tests and/or package builds.

Vice versa a Jenkins build job hook needs to update the ticket system. This will
notify the user of an unsuccessful run immediatly allowing further actions.

The issue id can be for example passed from the git hook into the Jenkins job.
This requires strict rules on git commits - a git commit without any referenced
issue id will destroy this workflow.

Define and document a git commit format specification and enforce this
to your users. In addition to that install a git hook on the server
which rejects a git push when the commit is missing an issue id.


~~~ENDSECTION~~~

