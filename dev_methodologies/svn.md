Svn is centralized, you can't access locally, all you create is on a server.

It keeps track of history like git.

Apart that the two systems are fairly similar.

### Basic commands

`svn list` -> show repository contents

`svn mkdir` -> make directory

`svn import` -> `git add + commit` (unversioned data - only new files)

`svn checkout` or `svn co` -> `git checkout` (versioned data)

`svn update` or `svn up` -> update working copy

`svn commit` -> just like git commit (it is useful for review)

### Operations with files

`svn add` -> `git add` (only for new files - unversioned data)

`svn move` or `svn rename` -> move files

`svn copy` -> make a file copy

`svn delete` -> delete a file

`svn revert` -> undo local uncommited files

### Creating a branch
`$ svn copy https://example.com/MyRepo/trunk https://example.com/MyRepo/branches/MyNewBranch -m "Creating a new branch"`

Later use:

`svn merge`
