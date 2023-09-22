---
# try also 'default' to start simple
theme: eloc
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: false
# some information about the slides, markdown enabled
info: |
  ## Git intro
# persist drawings in exports and build
drawings:
  persist: false
layout: intro
---

<img src="https://upload.wikimedia.org/wikipedia/commons/e/e0/Git-logo.svg" class="h-60" al6="git"/>

EELE 467


---
layout: statement
---

# What is version control?

---
layout: image
---

<img src="/phd-comics-not-final.gif" class="h-full">

---
class: 'text-center'
---

<div class="grid grid-cols-2 gap-50 place-items-center">
<div>

## Centralized

<img src="/vcs-comparison-centralized.svg">

</div>

<div>

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

# git: basic ideas

- **commits**: a snapshot of your working tree
- **commit graph**: commits are organized into a *directed acyclic graph*


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
