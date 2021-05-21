# GIT

Git Book: [www.git-scm.com/book/en/v2](https://www.git-scm.com/book/en/v2)

## Configuration

Configuration can be set on specific levels (system, user and per repository).
Use following options to configure each of them.

### Global (System)

Use option: `--system`

`git config --system user.email "you@example.com"`  
`git config --system user.name "Your Name"`

### Global (User specific)

Use option: `--global`

`git config --global user.email "you@example.com"`  
`git config --global user.name "Your Name"`

### Global (Repository specific)

Use option: `--local`

`git config --local user.email "you@example.com"`  
`git config --local user.name "Your Name"`

## Commands

### Undoing a Specific Commit

Sometimes a commit (ready to push) needs to be reverted.

use: `get reset <commit-id>`

## 🗃 Large files

Versioning large files isn't performand for git. To allow storing bigger files Git Large Files Storages or LFS is available.

Git Large File Storage: [git-lfs.github.com](https://git-lfs.github.com)

### GitHub LFS

GitHub allows LFS. To use it follow the steps provided in the documentation.  
Versioning large files: [docs.github.com/en/github/managing-large-files/versioning-large-files](https://docs.github.com/en/github/managing-large-files/versioning-large-files)

### IntelliJ LFS

Pushing large files, even after LFS configuration takes an endless time using IntelliJ.  
I managed to resolve this by simply using the terminal and command: `git push`.    
Which even shows a nice upload progress indication for free 👍.