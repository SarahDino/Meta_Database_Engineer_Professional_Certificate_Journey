# Version control (keep track of changes)

basicly its how to communicate new update with the rest of the team,
who made tha change, when, what ? also you can roll back


Centralized version control systems :

    have a server and clinets 
    you need to use a "pull" request in order to modify the code and when ever you are done you use a "push" request to upload the code and the rest of the team will be able to see it

Distributes version control systems :

    the same as Centralized version control systems but evry clinet is a server evry time you "pull" a code you will have the full history on your local system.



<br><br><br>

commonly used Git command line instructions :

1. Create repositories, When starting out with a new repository you only need to do it once <br>

A. locally then push to GitHub.<br>
```SQL
$ git init

Turn an existing directory into a git repository
```

B. cloning an existing repository.<br>
```SQL
$ git clone [url]

Clone (download) a repository that already exists on GitHub, including all of the files, branches, and commits
```


2. The .gitignore file 

In almost any coding project, you’ll have some files that you don’t want to be included in version control: temporary files, compiled code, sensitive data, etc.

This is typically done in a special file named .gitignore 

<br>
3. Configure tooling<br><br>

Configure user information for all local repositories

A. Sets the name you want attached to your commit transactions 
```SQL
$ git config --global user.name "[name]"
```

B. Sets the email you want attached to your commit transactions
```SQL
$ git config --global user.email "[email address]"
```

<br><br>
3. Branches<br><br>
Any commits you make will be made on the branch you're currently “checked out” to. Use git status to see which branch that is.

A. Creates a new branch
```SQL
$ git branch [branch-name]
```

B. Switches to the specified branch and updates the working directory
```SQL
$ git checkout [branch-name]
```

C. Combines the specified branch’s history into the current branch. This is usually done in pull requests but is an important Git operation.
```SQL
$ git merge [branch]
```

D. Deletes the specified branch
```SQL
$ git branch -d [branch-name]
```

<br><br>
4. Synchronize changes<br><br>
Synchronize your local repository with the remote repository on GitHub.com

A. Downloads all history from the remote tracking branches
```SQL
$ git fetch
```

B. Combines remote tracking branch into current local branch
```SQL
$ git merge
```

C. Uploads all local branch commits to GitHub
```SQL
$ git push
```

D. Updates your current local working branch with all new commits from the corresponding remote branch on GitHub. git pull is a combination of git fetch and git merge
```SQL
$ git pull
```

<br><br>
5. Make changes

A. Lists version history for the current branch
```SQL
$ git log
```

B. Lists version history for a file, including renames
```SQL
$ git log --follow [file]
```

C. Shows content differences between two branches
```SQL
$ git diff [first-branch]...[second-branch]
```

D. Outputs metadata and content changes of the specified commit
```SQL
$ git show [commit]
```

E. Snapshots the file in preparation for versioning
```SQL
$ git add [file]
```

F. Records file snapshots permanently in version history
```SQL
$ git commit -m "[descriptive message]"
```

<br><br>
6. Redo commits<br><br>
Erase mistakes

A. Undoes all commits after [commit], preserving changes locally
```SQL
$ git reset [commit]
```

B. Discards all history and changes back to the specified commit
```SQL
$ git reset --hard [commit]
```




