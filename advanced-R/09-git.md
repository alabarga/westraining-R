Version control using `git`
================
September 28, 2016

Sometimes you make mistakes and want to revert to an old version of the code, or you want to explore some features that may or may not end up belonging to the project, or you want to cooperate with other people and be able to selectively incorporate their changes to the codebase. Version control systems help with all these tasks. A version control system is essentially a way to keep code organized that lets you go back to different versions of the file and gives you tools to merge different versions from different authors.

`git` is very popular but not the only alternative. `git` is "distributed" which means that instead of having a centralized codebase with which each user interacts,each peer's working copy of the codebase is a complete repository.

`git` has a reputation for being complex, but it is becoming the standard in version control. Also, most of the tasks in a normal operation with `git` only involve a few, very intuitive commands.

We start using `git` by setting up a repository: we can either start a new project in our folder or we can pull code from an existing repository. Let's start by making our own new repo. In the current directory, we run

    git init

which will create a `.git` folder. We can check the status of our repository with

    git status

We can then add files to the repostory using `git add filename`. `filename` is now added to the staging area and the changes will be tracked.

The *changes* are *committed* to the repository with

    git commit -m "Adding files"

The `-m` option allows us to include a message describing what we did in this commit. Running `git commit` will do nothing unless you explicitly add files to the commit with `git add.`

We can now take a look at the history of changes using

    git log

The changes so far have been stored in our local copy of the repository, but we usually want to store a copy of our code in a remote server. To do that, we can `push` the changes to a particular address (either `https` or `ssh`). We can register this `remote` with a label using

    git remote add origin https://example.com/myproject.git

Now, we can send the code to the `master` branch of our code in the `origin` remote server with

    git push origin master

How do we retrieve upstream changes? Imagine some has made changes to the code from their side and we want to incorporate them to our copy of the repository. We can then

    git pull origin master

to download the changes to the `master` branch in the `origin` server. This operation will fecth the changes and merge them into the codebase automatically *unless there is a conflict*.

We can do a lot more things with `git`. We can check differences between two files using `git diff`, reset the status of the repository to an old version, create different branches, ... but that's outside the scope of this class.

You can learn more in [Try GitHub](https://try.github.io/).
