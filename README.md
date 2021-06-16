# LearningGit

This is a simple cheat sheet on how to use git and github as a beginner. I'm also a beginner so if you refer to this repository, please take the info at your own risk, I'm not an expert.

## Cloning

Cloning is use to get the data from Github to your local computer. When using the git bash the cloned repository will be cloned to the location in which you are currently located in the bash terminal.

> Note : The repository name will be the same as the one on Github.

use the following command to clone a project to your local computer :

```git
git clone "https name""
```

the file should now be on your computer.

## Commit

Doing a commit will do as it sais, it will commit the changes to the local repository. This will not change anything in Github, the `push` command need to be used for that and will be explained in later sections. First to see what file has changed (different from the current git version) use the following command :

```git 
git status
```

The you are ready to commit the data to your local repo by using the following command :

```git 
git commit -a -m "Message"
```

This will commit all the file to the repository, however your are able to only commit specifique file to the repository by using the `add` function :

```git
git add filename.ext
git commit -m "message"
```

## Branch

When creating a project the main/master branch is automatically created. However if commits are done on this branch the main project will be change to the new files. If you want to try some changes without impacting the main branch you can create your own branch and do the changes that you want. Then if your happy with the changes you can merge the newbranch to the main/master branch. To create a new branch use the following command :

```git
git branch NewBranchName
```

To change from one branch to another use the following command. If the destination branch does not exist, you have to append the “-b” option, otherwise you won’t be able to switch to that branch.

```git
$ git checkout <existing_branch>

$ git checkout -b <new_branch>
```

To list all the branches in the git repository:

```
$ git branch
```

To merge the `NewBranch` to the `main/master` branch use the following command. A couple of step are suggested to make sure that the merge goes well.

1. Execute git status to ensure that HEAD is pointing to the correct merge-receiving branch. If needed, execute git checkout to switch to the receiving branch. In our case we will execute git checkout main.

2. Make sure the receiving branch and the merging branch are up-to-date with the latest remote changes. Execute git fetch to pull the latest remote commits. Once the fetch is completed ensure the main branch has the latest updates by executing git pull.

Once the previously discussed **preparing to merge** steps have been taken a merge can be initiated by executing : 

```git 
git merge where 
```

`where` is the name of the branch that will be merged into the receiving branch.

> Note : If the merged project affects some other changes in the new version Git will ask what you what to keep. Ether keep your changes.

This is very usefull since every develloper can have there own branch and so changes without impacting the main project.

## Push

Push is use to upload the file/project to Github. First the remote must be linked to the correct repository on git hub. Then you can push a specifique branch to github.

```git 
git push origin BranchName
```

username and password may be required to push to github.

## Pull

The pull command is used to acces the most resent version of the project. If multiple devellopers have pushed some changes to the project your local version of the project is out of date therefore you must pull the project data from github.

```git 
git pull origin BranchName
```

git pull, in contrast, is used with a different goal in mind: to update your current HEAD branch with the latest changes from the remote server. This means that pull not only downloads new data; it also directly integrates it into your current working copy files. This has a couple of consequences:

- Since "git pull" tries to merge remote changes with your local ones, a so-called "merge conflict" can occur. Check out our in-depth tutorial on How to deal with merge conflicts for more information.
- Like for many other actions, it's highly recommended to start a "git pull" only with a clean working copy. This means that you should not have any uncommitted local changes before you pull. Use Git's Stash feature to save your local changes temporarily.

## Fetch

git fetch really only downloads new data from a remote repository - but it doesn't integrate any of this new data into your working files. Fetch is great for getting a fresh view on all the things that happened in a remote repository.
Due to it's "harmless" nature, you can rest assured: fetch will never manipulate, destroy, or screw up anything. This means you can never fetch often enough.

```
git fetch origin
```

## Returning to a Old version

The fastest way to restore an old version is to use the **reset** command:

```
$ git reset --hard 0ad5a7a6
```

This will rewind your HEAD branch to the specified version. All commits that came after this version are effectively undone; your project is exactly as it was at that point in time.

The reset command comes with a couple of options, one of the more interesting ones being the `--soft` flag. If you use it instead of `--hard`, Git will keep all the changes in those "undone" commits as local modifications:

```
$ git reset --soft 0ad5a7a6
```

You'll be left with a couple of changes in your working copy and can then decide what to do with them.

## Restoring a Revision in a New Local Branch

As said, using the reset command on your HEAD branch is a quite drastic action: it will remove any commits (on this branch) that came after the specified revision. If you're sure that this is what you want, everything is fine.

However, there is also a **safer** way in case you'd prefer leaving your current HEAD branch untouched. Since **branches** are so cheap and easy in Git, we can easily create a new branch which starts at that old revision:

```
$ git checkout -b old-project-state 0ad5a7a6
```

Normally, the checkout command is used to just switch branches. However, providing the -b parameter, you can also let it create a new branch (named "old-project-state" in this example). If you don't want it to start at the current HEAD revision, you also need to provide a commit hash - the old project revision we want to restore.

> note : you now have a new branch named "old-project-state" reflecting the old version of your project - without touching or even removing any other commits or branches.

