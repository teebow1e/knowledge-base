---
title: Git Installation and Setup
type: docs
prev: docs/git/
weight: 1
---

### Git Installation
Git is installed as a standalone software/package on your machine. To install on Linux-based system, please install the `git` package from your package manager. For example:
```sh
sudo apt install git -y
```

On Windows machine, please naviage to [the Git homepage](https://git-scm.com/) to download and install. The installation process in Windows is a bit complicated, but you can just press next to get pass it.

After installation, you can verifiy Git has been installed by this command:
```
teebow1e@teebow1e:~$ git --version
git version 2.34.1
```

### Verify yourself in Git
Normally, you can start using Git right after the installation. However, in HUST, most of the repositories you work with are private. Therefore, in order to interact with it (clone, push, delete, ..), you need to verify yourself with GitHub using the `git` package. I have written a [GitHub Gist](https://gist.github.com/teebow1e/7af5d089f6b3f492943157869029dc41) pointing out how you can authenticate yourself.

In constrast to the authentication steps in Linux, the one in Windows is pretty simple. You only need to:
- Create a private GitHub repo.
- Clone that repo using HTTPS protocol to trigger the authentication process.
![](/images/git/http-protocol.png)
![](/images/git/windows-clone.png)
- Enjoy!
![](/images/git/auth-done.png)
