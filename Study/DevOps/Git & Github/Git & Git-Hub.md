# Working with directories

| Command                                  | Full form if exist        | Use                                                                 |
| ---------------------------------------- | ------------------------- | ------------------------------------------------------------------- |
| `pwd`                                    | Present working directory | Shows path of present working directory                             |
| `ls`                                     | List (maybe)              | Lists your content                                                  |
| `cd [path]`                              | change directory          | change directory                                                    |
| `cd ..`                                  | change directory up       | Go to upper page of directory                                       |
| `touch [filename]`                       | -                         | To create a new file in your git repo                               |
| `git rm [filename]`                      | Git remove                | To delete file                                                      |
| `git mv [currentfilename] [newfilename]` | Git move                  | For changing file name because moving and renaming is same in linux |

# Git remote repos

| command                           | Full form if exist | Use                                                                                                                                             |
| --------------------------------- | ------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| `git status`                      | -                  | shows status of current working directory                                                                                                       |
| `git init`                        | -                  | For initialize git repo                                                                                                                         |
| `git add [filename]`              | -                  | For put files on staging area                                                                                                                   |
| `git add --a` or `git add .`      | -                  | Put all files on staging area                                                                                                                   |
| `git rm --cached [filename]`      | -                  | Remove from staging area                                                                                                                        |
| `git commit -m "My first repo"`   | -                  | Commit all staged files                                                                                                                         |
| `rm -rf .git`                     | -                  | Remove from tracking repo and delete all files                                                                                                  |
| `git clone [repolink] [filename]` |                    | For cloning the whole repo in your pc and`[filename]` uses for declaring a saperate name for local, you can also clone a repo without adding it |
| `git -a -m "Direct commit"`       | -                  | Skip staging area and commit directly                                                                                                           |

# Working with remote

| command                            | Full form if exist | Use                                                                               |
| ---------------------------------- | ------------------ | --------------------------------------------------------------------------------- |
| `git remote [repolink]`            | -                  | Connects your local directory with git remote repo                                |
| `git push origin [branchname]`     | -                  | Push your local directory to git repo                                             |
| `git remote add origin [repolink]` | -                  | Same command as `git remote [repolink]` just insert `add origin` in command       |
| `git remote`                       | -                  | Shows your all remote repos                                                       |
| `git remote -v`                    | -                  | Shows fetching/pulling and pushing remote repo                                    |
| `git push -u origin [branchname]`  | -                  | Same as `git push` but `-u` represents user and `origin main` defines branch name |

# Git log

| command                                   | Full form if exist | Use                                                                                 |
| ----------------------------------------- | ------------------ | ----------------------------------------------------------------------------------- |
| `git log`                                 | -                  | Shows all commits                                                                   |
| `git log -p`                              | -                  | Shows all commits with changes                                                      |
| `git log -p -3`                           | -                  | If you write -3 after of -p it will show 3 commits according to your written number |
| `git log --stat`                          | -                  | Shows all commits in short                                                          |
| `git log --pretty=full`                   | -                  | Shows all commits in more details in compare to `--stat`                            |
| `git log --pretty=short`                  | -                  | Shows all commits in short                                                          |
| `git log --pretty=oneline`                | -                  | Shows all commits in one line                                                       |
| `git log --since=2 days`                  | -                  | Shows all commits of last 2 days                                                    |
| `git log --pretty=fomat, [writesomething` | -                  | Go to "git scm log preety documentation"                                            |

**Note:** Click on `Q` and `enter` to exit from log page.

# Git ignore

Create `.gitignore` file and put all ignoring files into it (just write file names into it) 

**Pro tip:** Use `*.log` it means ignore all files which has `.log` extension.

# Git diff

| command            | Full form if exist | Use                                                    |
| ------------------ | ------------------ | ------------------------------------------------------ |
| `git diff`         | -                  | Difference between working directory and staging area  |
| `git diff -staged` | -                  | Difference between Last/recent commit and staging area |


# Working with commits

| command                           | Full form if exist | Use                                                                                                 |
| --------------------------------- | ------------------ | --------------------------------------------------------------------------------------------------- |
| `git commit -amend`               | -                  | To change previous commit                                                                           |
| `git restore --staged [filename]` | -                  | Unstage file                                                                                        |
| `git restore [filename]`          | -                  | Restore modification to last commit                                                                 |
| `git checkout -- [filename]`      | -                  | Unmodify repo, it will get your file into last commit status but it will only work on unstaged file |
| `git checkout -f`                 | -                  | It will take your whole working directory into last commit but it is only works on unstaged files   |

# Branches

| Command | Use |
|------------------------|-------------|
| Create new branch      | `git checkout -b [branch name]` |
| Change branch          | `git checkout [branch name]` |
| Delete branch          | `git branch -d [branchname]` (with warning if not merged) |
| Force delete branch    | `git branch -D [branchname]` (no warning) |
| Merged branches        | `git branch --merged` |
| Non-merged branches    | `git branch --no-merged` |
| Show all branches      | `git branch` |
| Show last commits      | `git branch -v` |
| Merge branches         | `git merge [another branch]` |

# Branch Push

| Branch Pushing                         | Command                                                    |
| -------------------------------------- | ---------------------------------------------------------- |
| Push current branch                    | `git push origin [branchname]`                             |
| Push with different remote branch name | `git push origin [branchnameOnLocal]:[branchnameOnRemote]` |
| Delete remote branch                   | `Git push -d origin [branchname]`                          | 

# Merge conflicts

| Merge Conflicts | Resolution |
|---------------------|----------------|
| Resolve conflicts in VS Code, then | `git add .` |
| Commit changes                      | `git commit` |

# Alias commands


`Git config --global alias.st status`
`Git config --global alias. Unstage 'restore --staged --'`

Use this type of commands for alias.

# Important note
A commit doesn't make staging area empty. Staging area is always a copy of last commit and using `git add` command will make changes in it.

Refer to [docs.chaicode.com](https://docs.chaicode.com/git-and-github/) for more detailed notes.
