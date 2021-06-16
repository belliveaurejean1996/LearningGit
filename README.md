# LearningGit

This is a simple cheat sheet on how to use git and github as a beginner. I'm also a beginner so I you somwone refers to this repo, please take the info at your own risk. I'm not an expert.

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

To change from one branch to another use the following command

```git

```

To merge the `NewBranch` to the `main/master` branch use the following command :

```git 

```

This is very usefull since every develloper can have there own branch and so changes without impacting the main project.

## Push

Push is use to upload the file/project to Github. First the remote must be linked to the correct repository on git hub. Then you can push a specifique branch to github.

```git 

```

username and password may be required to push to github.

## Pull

The pull command is used to acces the most resent version of the project. If multiple devellopers have pushed some changes to the project your local version of the project is out of date therefore you must pull the project data from github.

```git 

```

## Fetch

I do not know what this does haha!
