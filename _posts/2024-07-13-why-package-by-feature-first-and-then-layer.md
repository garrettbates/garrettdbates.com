---
layout: post
title: Why package by feature first and then by layer?
date: 2024-07-19 13:10
read_time: 3 min read
categories: blog software-architecture
image:
  path: /assets/why-package-by-feature-first/feature-slice.png
  height: 100
  width: 100
moreFromAuthor:
  -
    path: _posts/2024-07-20-why-prefer-unit-testing-through-layer-entrypoints.md
  - 
    path: _posts/2024-07-07-why-use-onion-layering.md
  -
    path: _posts/2024-07-20-why-disallow-package-within-the-class-name.md
discussionPages:
  - https://www.reddit.com/r/programming/comments/1e7dqzm/why_package_by_feature_first_and_then_by_layer/
  - https://www.linkedin.com/posts/garrettdbates_why-package-by-feature-first-and-then-by-activity-7220185968144760832-epw6?utm_source=share&utm_medium=member_desktop
  - https://news.ycombinator.com/item?id=41013148
  - https://x.com/garrettdbates/status/1814421999558766963
backgroundArticles:
  -
    link: https://gregorriegler.com/2020/08/08/levels-of-modularity.html
    image: https://gregorriegler.com/assets/modularity/modularity_level1_layered.svg
    title: Levels of Modularity
    date: 2020-08-08
  -
    link: https://www.youtube.com/watch?v=cVVMbuKmNes
    image: https://i.ytimg.com/vi/cVVMbuKmNes/maxresdefault.jpg
    title: Restructuring to a Vertical Slice Architecture
    date: 2021-07-28
  -
    link: https://www.jimmybogard.com/vertical-slice-architecture/
    image: https://jimmybogardsblog.blob.core.windows.net/jimmybogardsblog/3/2018/Picture0030.png
    title: Vertical Slice Architecture
    date: 2018-04-19
lucidchart:
  link: https://lucid.app/folder/invitations/accept/inv_a4d9ca23-8ddb-4d76-97da-bc18ba4a7f21
  image: /assets/why-package-by-feature-first/lucidchart-folder.png
  title: Lucidchart folder
nounProjectIcons:
  - 
    link: https://thenounproject.com/icon/arrow-2146615/
    name: Arrow
  - 
    link: https://thenounproject.com/icon/explosion-563988/
    name: Explosion
  - 
    link: https://thenounproject.com/icon/halo-4031793/
    name: Halo
  - 
    link: https://thenounproject.com/icon/file-354396/
    name: File
  -
    link: https://thenounproject.com/icon/brain-475578/
    name: Brain
  -
    link: https://thenounproject.com/icon/yes-5537946/
    name: Check
  -
    link: https://thenounproject.com/icon/smily-face-688850/
    name: Smiley Face
  -
    link: https://thenounproject.com/icon/sad-1515667/
    name: Sad
  -
    link: https://thenounproject.com/icon/excited-3500628/
    name: Excited
  -
    link: https://thenounproject.com/icon/bracket-3883565/
    name: Bracket
---

<div style="display:flex;justify-content:center">
    <img src="/assets/why-package-by-feature-first/feature-slice.png" alt="Feature Slice" style="max-height:400px">
</div>

## Context
For those seeking to understand *what* vertical slice architecture is and its relationship to other architectures I recommend checking out some of my favorite articles on the topic here 👉 [what is vertical slicing?](#related-background-articles)

This post provides a terse overview of *why* you might pursue vertical slicing with a few examples.

I've found these notes to be valuable in quickly setting the frame for group discussions on whether vertical slicing should be used in a certain setting. Hopefully, they will help you too.

## Rationale

### 1. Reduces information overload
![Reduces information overload](/assets/why-package-by-feature-first/information-overload.png)
After opening a directory it is the developer's job to filter out the files that are not relevant to their task at hand. The more files to filter, the more difficult it becomes to orient themselves and start making changes quickly. Packaging by feature first promises to reduce this information overload.

### 2. Reduces merge conflicts
![Reduces merge conflicts](/assets/why-package-by-feature-first/reduce-merge-conflicts.png)

Code bases with multiple developers will often run into issues where changes end up stepping on each other's toes. Packaging by feature first promises to reduce these merge conflicts.

### 3. Reduces barrier to share code
![Reduces barrier to share code](/assets/why-package-by-feature-first/reduce-code-share-barrier.png)

Occasionally we develop code that has incredible utility across multiple microservices. Surgically extracting useful pieces typically requires a deep understanding of the code base and is often painful. Packaging by feature first promises to reduce the barrier to sharing code across microservices by simplifying the process down to copying a single directory.