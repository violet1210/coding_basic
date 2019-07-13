# Git Cheet Sheet
## git config setting
---
`git config --local --list`  List all the settings in local Git repo
`git config --global --list`  List all the global settings
`git config pager.log false`  Disable Git pager for `git log` command
`git config --global --unset pager.log`  Unset Git pager setting
`git config --global color.ui auto`  Enable helpful colorization of command line output
`git config --global core.editor vim`  Set editor to vim (the editor launch when you try `git commit`)

## make/review changes
---
`git diff --staged`  Shows file differences between staging and the last file version
`git rm --cached <file_name>`  Removes the file from version control but preserves the file locally
`git log --follow <file_name>`  Lists version history for a file, including renames
`git diff 15d1c89...a87170b` View changes between commit 15d1c89 and commit a87170b 
`git log 15d1c89...a87170b` View commits between commit 15d1c89 and commit a87170b 

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

`git log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit`  Show Git commits with graph and color
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
