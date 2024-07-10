---
title: The Basic Workflow
type: docs
prev: docs/setup/
weight: 2
---

{{< callout type="info" >}}
  This guide only serves as a crash course to familiarize yourself with Git in the command line interface. For a deeper details into Git, please visit the other section.
{{< /callout >}}

## GitHub and initialize your first repo
Before step into your first project, let's join [GitHub](https://github.com); the process is pretty easy, so I won't mention it. However, pay attention to this guide when you first create a repo.
![](/images/git/project_empty.png)

If you left this untick, GitHub will create an empty repository by default. And we will left this untick so that we can have the instruction to get started.
![](/images/git/options.png)

At this point, we have 2 options:
- Upload file from browsers (drag and drop)
- Upload file using CLI

I will choose the command line approach. So just navigate to the root directory of the project and run each command, one by one. The output should be:
```sh
teebow1e@teebow1e:~/test-project$ ls
go.mod  main.go
teebow1e@teebow1e:~/test-project$ echo "# test_project" >> README.md
teebow1e@teebow1e:~/test-project$ git init
hint: Using 'master' as the name for the initial branch. This default branch name
hint: is subject to change. To configure the initial branch name to use in all
hint: of your new repositories, which will suppress this warning, call:
hint:
hint:   git config --global init.defaultBranch <name>
hint:
hint: Names commonly chosen instead of 'master' are 'main', 'trunk' and
hint: 'development'. The just-created branch can be renamed via this command:
hint:
hint:   git branch -m <name>
Initialized empty Git repository in /home/teebow1e/test-project/.git/
teebow1e@teebow1e:~/test-project$ git add .
teebow1e@teebow1e:~/test-project$ git commit -m "first commit"
[master (root-commit) 6fdb849] first commit
 3 files changed, 4 insertions(+)
 create mode 100644 README.md
 create mode 100644 go.mod
 create mode 100644 main.go
teebow1e@teebow1e:~/test-project$ git branch -M main
teebow1e@teebow1e:~/test-project$ git remote add origin git@github.com:teebow1e/test_project.git
teebow1e@teebow1e:~/test-project$ git push -u origin main
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (5/5), 361 bytes | 361.00 KiB/s, done.
Total 5 (delta 0), reused 0 (delta 0), pack-reused 0
To github.com:teebow1e/test_project.git
 * [new branch]      main -> main
Branch 'main' set up to track remote branch 'main' from 'origin'.
```
And in your GitHub repository:
![](/images/git/after_push.png)

### Explanation
- `echo "# test_project" >> README.md` - push the text `# test_project` into `README.md`. README is an important file that tells about your repository, and it's rendered by default on GitHub.
- `git init` - initailize a repository on your local machine. You may notice a `.git` folder has been created, inside it is the information about tracked files and your repository.
- `git add .` - add everything (untracked) into staging area - ready to be committed (saved)
- `git commit -m ""` - add the commit message
- `git branch -M main` - rename the current branch to `main`. Git by default set the default branch name as `master`, however, GitHub likes `main`, so we rename to avoid any conflict that may happen.
- `git remote add origin git@github.com:teebow1e/test_project.git` - add the remote origin (just understand this as the address of your GitHub repo - this is stored online, so it's "remote")
- `git push -u origin main` - push every committed item into branch `main` of origin (GitHub), flag `-u` means from now on, `git push` will push to `main` branch of `origin` by default. In short, next time you push, just use `git push`.

### Todo:
- git add
- git commit
- git branch/switch/checkout
- git merge
- git push
- git log
- github PR