---
layout: post
title: Why package by feature first and then by layer?
date: 2024-07-19 13:10
read_time: 3 min read
categories: blog software-architecture
---

## Context
For those seeking to understand *what* vertical slice architecture is I recommend checking out some of my favorite articles on the topic here 👉 [what is vertical slicing?](#related-background-articles)

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

### Appendix

#### Discussion Threads
* [Hacker News](https://news.ycombinator.com/item?id=41010866)
* [Reddit](https://www.reddit.com/r/programming/comments/1e7dqzm/why_package_by_feature_first_and_then_by_layer/)

#### Background Articles
* [https://gregorriegler.com/2020/08/08/levels-of-modularity.html](https://gregorriegler.com/2020/08/08/levels-of-modularity.html)
* [https://www.jimmybogard.com/vertical-slice-architecture/](https://www.jimmybogard.com/vertical-slice-architecture/)
  
#### Lucidchart Folder
* [https://lucid.app/folder/invitations/accept/inv_a4d9ca23-8ddb-4d76-97da-bc18ba4a7f21](https://lucid.app/folder/invitations/accept/inv_a4d9ca23-8ddb-4d76-97da-bc18ba4a7f21)

#### Noun Project Assets
* [Arrow](https://thenounproject.com/icon/arrow-2146615/)
* [Explosion](https://thenounproject.com/icon/explosion-563988/)
* [File](https://thenounproject.com/icon/file-354396/)
* [Check](https://thenounproject.com/icon/yes-5537946/)
* [Smiley Face](https://thenounproject.com/icon/smily-face-688850/)
* [Sad](https://thenounproject.com/icon/sad-1515667/)
* [Excited](https://thenounproject.com/icon/excited-3500628/)
* [Bracket](https://thenounproject.com/icon/bracket-3883565/)
* [Brain](https://thenounproject.com/icon/brain-475578/)