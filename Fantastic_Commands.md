Fantastic Commands and How to Use Them
======================================
# Overview
- Systems
  - [Linux/GNU/Terminal](#linux)
- Programs
  - [Git](#git)
- Languages
  - [Racket](#racket)
  - [Scribble](#scribble)
  - [Markdown](#markdown)

# Git
---


#### git blame
```sh
git blame -L a,b $FILE
```
-L = limit output
a = line start
b = line end
$FILE = file you want to check
Example:
```sh
git blame -L 12,24 frog.rkt
```
---
#### git add
```sh
git add <FILE OR DIR>
```
Adds the file or folder to git staging to prepare before committing it
Example:
```sh
git add ./frog
```
---
#### git commit
```sh
git commit
```
Commits added files and prompts for a commit comment on what was changed (should be pretty detailed).

---
#### git push
```sh
git push
```
Pushes the committed changes to a [remote] repository. Must be the working directory where git was initialized.

Example:
```sh
cd $HOME/projects/
git push origin master
```
---
#### git remote
```sh
git remote -v
```
Lists the remote repositories

```sh
git remote add [-t <branch>] [-m <master>] [-f] [--[no-]tags] [--mirror=<fetch|push>] <name> <url>
```

```sh
git remote add origin https://github.com/HelixCarinae/ToolTips.git
---
You have to do 'git init' before this.  

#### git log
```sh
git log
```
brings up a log of changes that have been committed

---


# Markdown
---
> https://enterprise.github.com/downloads/en/markdown-cheatsheet.pdf

---
#### Headers
```md
Use 1 to 6 # for different headers in decreasing size
```
---
#### Emphasis
```md
*italic*
_itatlic_

**bold**
__bold__
```
These can be combined

---
#### Lists
```md
- Item 1
  - Item 1.a
    - Item 1.a.a
  - Item 1.b
- Item 2

1. This is
2. a numbered
3. List
```
- Item 1
  - Item 1.a
    - Item 1.a.a
  - Item 1.b
- Item 2

1. This is
2. a numbered
3. List

---
#### Links
```md
[Name](https://link.zelda)
OR just use plain link
https://www.wikipedia.org
```
[Name](https://link.zelda)
OR just use plain link
https://www.wikipedia.org
---
#### Quotes
> To automate or not to automate
> That is the question

```md
> To automate or not to automate
> That is the question
```
---
#### Tables

Using Tables | Like It's 1999
------------ | --------------
Flashbacks   | To
Geocities    | Sites

```md
Using Tables | Like It's 1999
------------ | --------------
Flashbacks   | To
Geocities    | Sites
```


---

# Racket

#### Syntax

```racket
#lang racket
(define (list-length list)
  (if (empty? list)
      0
      (+ 1 (list-length list))))

(module+ test
  (require rackunit)
  (define test-list '(1 2 3))
  (define tl2 (build-list 123 list))
  (check-equal? (length test-list) (list-length test-list)))
```

\#lang racket
- essentially an import



---

# Scribble

Essentially just racket that uses @ in front of calls

---

# Linux

## History

### ctrl + r

First there's the wonder ctrl+r
```sh
$ [ctrl+r] Fantast [enter]
$ less $HOME/networkHome/uni/cs/2613/frog/post/_src/date-Fantastic_Commands.md
```

### alt + .
Pressing [**_alt+._**] inserts the parameter (you info) from the last command you used
```sh
$ ls -a $HOME/Desktop/files
$ nano [alt+.]/Fantastic_Commands
```

### bang bang he shot me down !
We also have !$ which does the same as [alt + .]
```sh
$ cat $HOME/networkHome/uni/cs/2613/frog/post/_src/date-Fantastic_Commands.md
$ less !$
```

there's more we can do with the bang however
```sh
cd ~/Desktop/animals
get http://www.cutepuppers.com/border_collie.jpg
w!! #this runs 'wget http://www.cutepuppers.com/border_collie.jpg' immediately
cd ~/cats/all/the/cats
wget http://www.cutepuppers.com/labrador.jpg
mv ./labrador.jpg !-6&/dogs

```
!! does the last command
!n where n is the order you used the commands (this can be found with history)
!-y where y is the number you want to go back you have to add -1 to what you expect as running the command itself counts as history so !-1 just does !-1
adding $ strips the command part from it (like ls -a)


---


## Heads or Tails?
