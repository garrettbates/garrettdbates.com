---
layout: post
title: Why package by feature first and then by layer?
date: 2024-07-15 19:56 -0700
read_time: 4 min read
categories: blog software-architecture
---

## Context
For those seeking to understand *what* the vertical slice architecture is I recommend checking out some of my favorite articles on the topic here 👉 [what is vertical slicing?](#related-background-articles)

This post provides a terse overview of *why* you might pursue vertical slicing with a few examples.

## Rationale

### 1. Reduces information overload
![Reduces information overload](information-overload.png)
After opening a directory it is the developers job to filter out the files that are not relevant to their task at hand. The more files to filter, the more difficult it becomes to quickly orient themselves and start making changes. Packaging by feature first promises to reduce this information overload.

### 2. Reduces merge conflicts
![Reduces merge conflicts](reduce-merge-conflicts.png)

We anticipate there will always be concurrent development going on within our code base. Packaging by feature first promises to reduce merge conflicts.

### 3. Reduces barrier to share code
![Reduces barrier to share code](reduce-code-share-barrier.png)

Occasionally we develop code that has incredible utility across multiple microservices. The process of surgically extracting useful pieces typically requires deep understanding of the code base and is often painful. Packaging by feature first promises to reduce the barrier to share code across microservices by simplifying the proces down to copying a single directory. 

### Appendix

#### Related Background Articles
* https://gregorriegler.com/2020/08/08/levels-of-modularity.html
* https://www.jimmybogard.com/vertical-slice-architecture/