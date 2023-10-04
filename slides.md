---
# try also 'default' to start simple
theme: eloc
# https://sli.dev/custom/highlighters.html
highlighter: prism
# show line numbers in code blocks
lineNumbers: false

title: 'Intro to git: stats seminar'

# some information about the slides, markdown enabled
info: |
  ## Git intro
# persist drawings in exports and build
drawings:
  persist: false

# enable pdf download in SPA build
download: true
exportFilename: 'intro-to-git-stats-seminar'

selectable: true

aspectRatio: '16/9'

fonts:
  sans: 'Source Sans Pro'

layout: intro
---

<img src="https://upload.wikimedia.org/wikipedia/commons/e/e0/Git-logo.svg" class="h-60" al6="git"/>


Statistics seminar | Oct. 4, 2023



---

<img src="/phd-comics-not-final.gif" class="h-full">

---

<div class="grid grid-cols-2 gap-50">

<div class="flex justify-center">

## Centralized

<img src="/vcs-comparison-centralized.svg">

</div>

<div class="flex justify-center">

## Decentralized

<img src="/vcs-comparison-decentralized.svg">

</div>
</div>

<style>
  h2 {
    @apply absolute top-5 text-center;
  }
</style>

---
clicks: 3
---

# git building blocks
<ul>
  <li v-click="1"> <b>commits</b>: a snapshot of your files* </li>
  <li v-click="2"> <b>commit graph</b>: commits are organized into a <i>directed acyclic graph</i> </li>
</ul>

<br>

<div v-click="3" class="relative -left-110 top-10">

### history

</div>

<arrow v-click="3" x1="350" y1="640" x2="350" y2="520" color="#f59e0b" width="6"/>

<div v-click="1">

*if git is *tracking* the files

</div>


<style>
  p {
     font-size: 0.5em;
  }
  h3 {
    @apply text-amber-500;
  }
</style>


---

<img src="/commit-graph.svg">

---
layout: statement
class: 'text-center'
---

# Create a repository

<a href="https://github.com/new">https://github.com/new</a>

---
layout: statement
class: 'text-center'
---

# Clone the repository

`git clone`


---

# The basics

<v-clicks>

- `git add`
- `git commit`
- `git push`
- `git pull`
- `git status`
- `git log`

</v-clicks>

<div v-click="7" class="absolute left-1000px top-350px text-amber-500">

#### committing changes

</div>

<div v-click="8" class="absolute left-1000px top-520px text-blue-500">

#### interact with GitHub

</div>

<div v-click="9" class="absolute left-1000px top-680px text-red-500">

#### view what you've done

</div>

<div v-click="7" class="absolute left-900px top-295px">
<svg width="100" height="500" class="stroke-amber-500">
<polyline points="0,40 80,40 80,190 0,190" fill="none" stroke-linecap="round" stroke-linejoin="round" stroke-width="8"/>
</svg>
</div>

<div v-click="8" class="absolute left-900px top-455px">
<svg width="100" height="500" class="stroke-blue-500">
<polyline points="0,40 80,40 80,190 0,190" fill="none" stroke-linecap="round" stroke-linejoin="round" stroke-width="8"/>
</svg>
</div>

<div v-click="9" class="absolute left-900px top-615px">
<svg width="100" height="500" class="stroke-red-500">
<polyline points="0,40 80,40 80,190 0,190" fill="none" stroke-linecap="round" stroke-linejoin="round" stroke-width="8"/>
</svg>
</div>


---
layout: section
---

# The three trees


---


<img  class="absolute top-0 h-screen" src="/git-three-trees-overview.svg">

<img v-click="1" class="absolute top-0 h-screen" src="/git-three-trees-annotated-add.svg">
<img v-click="2" class="absolute top-0 h-screen" src="/git-three-trees-annotated-commit.svg">
<img v-click="3" class="absolute top-0 h-screen" src="/git-three-trees-annotated-full.svg">




---

# The index / staging area

- *staging changes*: `git add <files>`
- *viewing the index*: `git status`

---

# Committing changes

`git commit`

- only changes in the staging area are added to the commit
- commits need a *commit message*

---

# Viewing changes

- *between your working tree and the index*: `git diff`
- *between the index and HEAD (the parent commit)*: `git diff --staged`

---

# Exercise

1. modify the contents of your `README.md` file
2. stage those changes (`git add`)
3. commit the changes (`git commit`)



---

# Viewing history

`git log`

---

# Exercise

1. create a new file: `test.md`
2. write stuff in `test.md`
3. add `test.md` to the staging area
4. commit your changes

---
layout: statement
class: 'text-center'
---

# Reverting changes

<div class="text-7xl">
oops! <emojione-bug /> <emojione-grinning-face-with-sweat />
</div>

<br>

`git revert`

---

# Exercise

1. revert your first commit

---
layout: section
---

# Interacting with GitHub

local vs. remote repositories

---
layout: full
---


<img class="h-screen" src="/local-vs-remote-repos-local-changes.svg">


---
layout: full
---


<img class="h-screen" src="/local-vs-remote-repos-local-changes-push.svg">


---
layout: full
---

<img class="h-screen" src="/local-vs-remote-repos-remote-changes.svg">

---
layout: full
---

<img class="h-screen" src="/local-vs-remote-repos-remote-changes-pull.svg">


---

# Exercise
#### *pushing* to GitHub (the "remote" repository)

1. verify that your local branch is ahead of the remote
  <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; `git status`
2. push your local changes to the GitHub repository (remote)

---

# Exercise
#### *pulling* from GitHub

1. edit a file and make a commit using your repo's GitHub webpage
2. pull those changes into your local repo

---
layout: section
---

# Tags and branches

a commit by any other name...

---

# Tags

<img src="/tags-and-branches-tag.svg">

<v-click>

`git tag -a v0.1`

</v-click>



---

# Exercise

1. tag your most recent commit as `v1.0`

---

<div class="absolute top-1">

# Branches

</div>

<img class="absolute bottom-0" src="/tags-and-branches-branch.svg">



---

<div class="absolute top-1">

# Branches

</div>

<img class="absolute bottom-0" src="/tags-and-branches-branch-2.svg">


---

# Branching

- *creation*: `git branch <branch-name>`
- *changing branches*: `git switch <branch-name>`
- *changing branches*: `git checkout <branch-name>`
- *both at the same time*: `git switch -c <branch-name>`

---

# Exercise

1. create a branch called `cool-feature` and switch to it
2. add `hello from cool-feature branch` to your `README.md`

---

## Merging branches

<img src="/tags-and-branches-merge.svg">


---

# Merging branches

`git merge <branch-to-merge>`


---
layout: statement
---

# Exercise

1. switch to your `main` branch
2. merge `cool-feature` into `main`

---

# Typical branching workflow

```mermaid
gitGraph:
  commit
  commit
  commit
  branch feature1
  checkout feature1
  commit
  commit
  checkout main
  merge feature1
  commit
  branch feature2
  commit
  commit
  checkout feature2
  commit
  commit
  commit
  checkout main
  commit
  branch feature3
  checkout feature3
  commit
  commit
  checkout main
  merge feature3
  checkout feature2
  commit
  checkout main
  merge feature2
  commit

```


---
layout: two-cols-header
---

# Resources <emojione-books />

::left::

- [git - the simple guide](https://rogerdudler.github.io/git-guide/)
- [GitHub Git Guides](https://github.com/git-guides/)
- [Atlassian git tutorials](https://www.atlassian.com/git/tutorials)
- [Think like (a) Git](https://think-like-a-git.net/)

::right::

- [Command line Git](https://docs.gitlab.com/ee/gitlab-basics/start-using-git.html)
- [Pro Git book](https://www.git-scm.com/book/en/v2)
- [GitLab git cheat sheet](https://about.gitlab.com/images/press/git-cheat-sheet.pdf)
- [GitHub git cheat sheet](https://training.github.com/downloads/github-git-cheat-sheet/)
