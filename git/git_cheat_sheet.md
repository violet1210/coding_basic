# Git Cheet Sheet

[![GitHub tag](https://img.shields.io/static/v1?label=tag&message=v2.20.1&color=blue)](https://github.com/git/git/releases/tag/v2.20.1)

## git config setting
`git config --local --list`  List all the settings in local Git repo  
`git config --global --list`  List all the global settings  
`git config pager.log false`  Disable Git pager for `git log` command  
`git config --global --unset pager.log`  Unset Git pager setting  
`git config --global color.ui auto`  Enable helpful colorization of command line output  
`git config --global core.editor vim`  Set editor to vim (the editor launch when you try `git commit`)  
`git config --global alias.last5 'log -5 HEAD'` Rename git command. Here we can use `git last5` as `git log -5 HEAD`  

## review changes
`git diff --staged`  Shows file differences between staging and the last file version  
`git diff 15d1c89...a87170b` View changes between commit 15d1c89 and commit a87170b   
`git log 15d1c89...a87170b` View commits between commit 15d1c89 and commit a87170b  
`git log --follow <file_name>`  Lists version history for a file, including renames  
  
`git log --oneline` Display Git commits and make each commit fit in one line  
```console
a87170b Add Open HTML to PDF
391ade4 Add Perses
ff9149f Restore "Bytecode Manipulation" entry in Contents
15d1c89 Merge pull request #747 from gunnarmorling/patch-1
6b3588e Merge pull request #731 from vdiravka/Apache_Drill
cff1cf9 Add Doma 2
49efca9 Update README.md
```

`git log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit`  Show Git commits with graph and color, see more formats [here](https://git-scm.com/docs/pretty-formats)   
```console
* a87170b - (HEAD -> master, origin/master, origin/HEAD) Add Open HTML to PDF (6 days ago) <Jeff Schwartz>
* 391ade4 - Add Perses (6 days ago) <Júlio Falbo>
* ff9149f - Restore "Bytecode Manipulation" entry in Contents (8 days ago) <Johnny Lim>
*   15d1c89 - Merge pull request #747 from gunnarmorling/patch-1 (3 weeks ago) <Andreas Kull>
|\
| * eae33f8 - Adding link to "Awesome Annotation Processing" list (7 weeks ago) <Gunnar Morling>
* |   6b3588e - Merge pull request #731 from vdiravka/Apache_Drill (3 weeks ago) <Andreas Kull>
|\ \
| * | e630552 - Add Apache Drill (4 months ago) <Vitalii Diravka>
* | |   cff1cf9 - Add Doma 2 (3 weeks ago) <Andreas Kull>
|\ \ \
| * | | 49efca9 - Update README.md (3 weeks ago) <Andreas Kull>
| * | | dc91e40 - [Doma 2](https://doma.readthedocs.io/en/stable/) (7 weeks ago) <Adam Gent>
| | |/
| |/|
* | |   ecba472 - Add Serenity BDD (3 weeks ago) <Andreas Kull>
```

`git log --author="violet" --since="2019-06-10" --until="2019-06-20"`  List all change commited by violet with given time range  

## make changes
`git rm --cached <file_name>`  Remove the file from version control but preserves the file locally  
`git stash show stash@{5}`  Inspect the fileschange in stash change stash@{5}  
`git stash show -p`  Shows the content change made in latest stash  
`git stash push -k -m "test description"`  Stash all files, except the indexed ones, with give stash description  
`git stash --patch` Prompt interactively mode that which file you would like to keep in working directory  
`git stash drop stash@{0}` Remove given stash -- stash@{0}  

## branch
`git branch -a`  List both local and remote branch  
`git branch -vv` List branch with sha1, commit subject and upstream branch  
`git branch <branchname> -u origin/<remote-branchname>` Set up upstream branch  
`git checkout -b <branchname>` Create a new branch and swtich to it  
`git branch -d <branchname>` Delete branch  
`git push origin -d <branchname>` Delete remote branch  
`git merge --ff-only <branchname>`  Merge given branch into the current branch

## resolve conflict/merge changes
`git rebase --onto <new-parent-commit> <old-parent-commit>` Switch from current parent commit to a new commnit
