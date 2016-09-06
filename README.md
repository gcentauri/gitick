
gitick - a simple git and filesystem based ticket system
========================================================


DISCLAIMER
----------

This these commands are dangerous and are really no better than bash
aliases most of the time.  They perform absolutely no checking of any
kind, and, if run from the wrong directory, they may have
unintended and possible hazardous consequences.


COMMANDS
----------

### `gitick-new <project>`

Creates a new directory called `gitick.<project>` and populates it
with some some directories.

### `gitick-user <user>`

From within a gitick directory, creates a new user directory called
`<user>`.  This is where you put tickets assigned to a team member.

### `gitick-add <short title> <number>`

Called from within a gitick toplevel directory, this is how you add
new tickets.

E.g.

    gitick-add 'My New Issue' 5
	
This creates a file called `new/My-New-Issue.md` with priority 5.

You can edit it as you like, some text is filled in already.

### `gitick-wip`

From a gitick top level directory, lists all work in progress. Just a
wrapper around grep.

### `gitick-rfc`

From a gitick top level directory, lists all tickets for which
information is needed from some team-member.  Again, a wrapper around
grep.

### `gitick-tagged <tag>`

From a git top level directory, another wrapper around grep. Finds all
tickets tagged with `<tag>`.

### `gitick-sync`

Called from within a gitick top level directory. This is could be
dangerous if called from the wrong place as it just does the
following:

    git pull origin master
    git add .
    git commit -m "$(date)"
    git push origin master

It also assumes that you have set up a git repo on a remote location
called `origin` that has a `master` branch to which you have the
permission to `pull` and `push`.


