## Managing Git branches with `git-trim`


![git.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1645170660256/PzkvqwYP7.jpeg)

After creating so many branches on your current project, pushed some to git, merged some with the main branch and you even forgot that some branch existed or needed to clean up stale or old local branches that have already been merged and deleted on GitHub. Well, I have found a way to take care of that. 
[Jason McCreary](https://twitter.com/TraderJMac) has released a CLI tool for organizing local and remote branches.

The ``` `git trim` ```  command provides a way to easily remove merged, pruned, untracked, and stale branches within a repository.


## Installation
#### Basic install
The preferred installation method is to simply save the git-trim script somewhere included in your path. For example, copy git-trim into an existing included path like /usr/local/bin, or add the parent directory to your PATH environment.

#### Installing via npm

```
npm install --global git-trim
``` 

## Configuration

By default, ```git trim``` will never remove the current branch. However, depending on your branching strategy, you may have additional branches you never want to remove. For example, a ```dev``` or ```staging``` branch.

If so, you may set a ```gt.exclude``` option to your Git configuration, either locally or globally, with a space delimited string of any additional branches you want to exclude from removal.

```
git config gt.exclude "dev staging"
    # Always exclude the "dev" and "staging" branches from removal
```

## Usage

![git trim.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1645172424759/EnuHLkY97.png)

Available options are:


```
all!              remove all local branches, except the current branch
dry-run!          prints branches which will be removed instead of deleting them
m,merged!         remove local branches already merged into the current branch
p,pruned!         remove local branches where its remote branch no longer exists
r,remote!         remove remote branches instead of local branches
reset=?           remove all local branches except those existing on remote (default: origin)
s,stale!          remove local branches without commits in the last 3 months
t,tracked!        remove the tracking branch from remote
u,untracked!      remove local branches not tracking a remote branch
``` 

You can also combine these options when it makes sense, such as removing merged and stale branches:


```
git-trim --merged --stale
``` 

Thanks for reading this article. If you'd like to learn more about the source code, you can check it out on GitHub at [jasonmccreary/git-trim](https://github.com/jasonmccreary/git-trim)

