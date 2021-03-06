---
bibliography: refs/vewhitepaper.bib
output:
  html_document: default
  pdf_document: default
---

# Appendix to Open Source Projects: Best Practices for VisionEval

*Draft*


## Creating Duplicate Repositories
To bring in the work done on RPAT into the VisionEval team GitHub account, two main options would be available. The first is to simply transfer ownership of the repository to the VisionEval team; skip to step 5 below. The second is to create an identical copy of the existing repository, which would keep all the history of contributions and edits. The newly created duplicate repository can then be transferred to VisionEval. 

The process of copying from one repository to a second one, while preserving all the history, would be as follows:

Using the [`git bash`](https://git-scm.com/) command line tool:

1.	In top-level git directory on the local machine (which may be named "GitHub" for on your machine), make a copy of existing repository using clone, and rename it 

    `git clone https://github.com/username/originalrepo newrepo`

2.	Go into that repository, delete the link to the original repository, and re-write each file to start new branch history using filter-branch. This needs to be done for each top-level subdirectory in the repository, where `foldername` refers to a given subdirectory.

    `cd newrepo`
    
    `git remote rm origin`
    
    `git filter-branch -subdirectory-filter foldername -- --all`
    
If there are no subdirectories, simply `git filter-branch -d newrepo -- --all`. The first two lines of step 3. below would be unnecessary.

3.	Now make a new directory and place all those re-written files in the new directory. As above, `foldername` refers to the subdirectory name, and is the only variable which would change in this process. 

    `mkdir foldername`
    
    `mv * foldername`
    
    `git add .`
    
    `git commit`

    Add a commit message, hit `esc`, `:wq` to save and quit `vim`.

4.	Push it to GitHub. Create the repository on GitHub first, then add this to the remote. If transfering to a new organization that you have rights to create repositories in, replace `username` with the organization name.

    `git remote add origin https://github.com/username/newrepo`
    
    `git push -u origin master`

5.	If necessary, [Transfer this to another GitHub user](https://help.GitHub.com/articles/transferring-a-repository-owned-by-your-personal-account/. 
)
This sends an email to the proposed new repository owner, asking them to confirm it.

## Cloning a wiki

Per [this StackOverflow post](https://stackoverflow.com/questions/16800999/fork-github-project-with-custom-wiki/33828142#33828142), an existing wiki from a repository can be cloned to a fork as follow.

First, fork the `project` repository from `user1` account into `user2` account. 
Create one wiki page in the forked version. [See here](https://stackoverflow.com/questions/40159478/fork-clone-and-push-a-wiki-in-github).
Then inside the local machine version (local clone) of this newly-forked project: 

```shell
 git clone https://github.com/user1/project.wiki.git
 git remote add my-fork https://github.com/user2/project.wiki.git
 git push my-fork -f
```

To keep the wikis in sync:

```shell
 git pull origin master
 git push my-fork master
```

