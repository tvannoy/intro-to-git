---
# try also 'default' to start simple
theme: eloc
# https://sli.dev/custom/highlighters.html
highlighter: shiki
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

layout: intro
---

<img src="https://upload.wikimedia.org/wikipedia/commons/e/e0/Git-logo.svg" class="h-60" al6="git"/>

EELE 467


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
    @apply absolute top-0 text-center
  }
</style>

---
clicks: 3
---

# git: building blocks
<ul>
  <li v-click="1"> <b>commits</b>: a snapshot of your files* </li>
  <li v-click="2"> <b>commit graph</b>: commits are organized into a <i>directed acyclic graph</i> </li>
</ul>

<br>

<div v-click="3" class="relative -left-110 top-10">

### history

</div>

<arrow v-click="3" x1="350" y1="640" x2="350" y2="520" color="" width="6" arrowSize="1" />

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


---

<img src="/commit-graph.svg">
<!-- do an example visualization here-->

---

# Getting practical
## Get a pre-existing repo: "cloning"

`git clone git@github.com:<user-or-org>/<repo-name>.git`

---
layout: statement
---

# Exercise

Clone your starter GitHub repository


---

# The three trees

<img src="/git-three-trees-overview.svg">

<style>
  h1 {
    @apply absolute top-0 text-center
  }
</style>

---

# The index / staging area

- *staging changes*: `git add <files>`
- *viewing the index*: `git status`

---

# Committing changes

`git commit`

- only changes in the staging area are added to the commit


---
layout: statement
---

# Exercise

1. delete the contents of your `README.md` file
2. stage those changes
3. commit the changes

---

## Review: the three trees

<img src="/git-three-trees-annotated.svg">

<!-- <style>
  h1 {
    @apply absolute top-0 text-center
  }
</style> -->

---

# Viewing changes

- *between your working tree and the index*: `git diff`
- *between the index and HEAD (the parent commit)*: `git diff --staged` or `git diff --cached`

---

# Viewing histry

`git log`

---
layout: statement
---

# Exercise

1. add some text into `README.md`
2. view the changes between your working tree and the index
   
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; remember `status` and `diff`

3. add the changes into the index
4. view changes between the index and the last commit

  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`diff --staged`

5. commit the changes in your index / "staging area"

---

## Local vs remote repository


<img src="/local-vs-remote-repos-local-changes.svg">

<style>
  h2 {
    @apply absolute top-0 text-center
  }
</style>


---

## Local vs remote repository

<img src="/local-vs-remote-repos-local-changes-push.svg">

<style>
  h2 {
    @apply absolute top-0 text-center
  }
</style>

---

## Local vs remote repository


<img src="/local-vs-remote-repos-remote-changes.svg">

<style>
  h2 {
    @apply absolute top-0 text-center
  }
</style>

---

## Local vs remote repository

<img src="/local-vs-remote-repos-remote-changes-pull.svg">

<style>
  h2 {
    @apply absolute top-0 text-center
  }
</style>


---
layout:statement
---

# Exercise

1. verify that your local branch is ahead of the remote
  <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; `git status`
2. push your local changes to the GitHub repository (remote)
3. edit a file and make a commit using your repo's GitHub webpage
4. pull those changes

---
layout: section
---

# Tags and branches

a commit by any other name...

---

# Tags

<img src="/tags-and-branches-tag.svg">


---

## Annotated tags **
`git tag -a v1.2`

** preferred


## Lightweight tags
`git tag v1.2`


---
layout: statement
---

# Exercise

1. tag your most recent commit as `my-first-tag`

---

# Branches

<img src="/tags-and-branches-branch.svg">


---

# Branches

<img src="/tags-and-branches-branch-2.svg">


---

# Branching

- *creation*: `git branch <branch-name>`
- *changing branches*: `git switch <branch-name>`
- *changing branches*: `git checkout <branch-name>`
- *both at the same time*: `git switch -c <branch-name>`

---
layout: statement
---

# Exercise

1. create a branch called `my-first-branch` and switch to it
2. add `hello from my-first-branch` to your `README.md`

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
2. merge `my-first-branch` into `main`
