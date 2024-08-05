---
layout: post
title: Why disallow package within the class name?
date: 2024-07-20 04:30 -0700
read_time: 1 min read
categories: blog software-architecture
image:
  path: /assets/why-disallow-package-within-the-class-name/package-information-overload.png
moreFromAuthor:
  -
    path: _posts/2024-07-20-why-prefer-unit-testing-through-layer-entrypoints.md
  - 
    path: _posts/2024-07-07-why-use-onion-layering.md
  -
    path: _posts/2024-07-13-why-package-by-feature-first-and-then-layer.md
discussionPages:
  - https://www.reddit.com/r/programming/comments/1e7u735/why_disallow_package_within_the_class_name/
  - https://www.linkedin.com/posts/garrettdbates_why-disallow-package-within-the-class-name-activity-7220401579915399168-oSAK?utm_source=share&utm_medium=member_desktop
  - https://news.ycombinator.com/item?id=41015924
backgroundArticles:
  -
    link: https://blog.codinghorror.com/new-programming-jargon/#21
    image: https://blog.codinghorror.com/content/images/2014/Jun/brainy-smurf.png
    title: Coding Horror - Smurf Naming Convention
    date: 2012-07-20
lucidchart:
  link: https://lucid.app/folder/invitations/accept/inv_534f6a27-5bef-4a30-97e1-c29dd79d1f2c
  image: /assets/why-disallow-package-within-the-class-name/lucidchart-folder.png
  title: Lucidchart folder
nounProjectIcons:
  - 
    link: https://thenounproject.com/icon/arrow-2146615/
    name: Arrow
  - 
    link: https://thenounproject.com/icon/explosion-563988/
    name: Explosion
  -
    link: https://thenounproject.com/icon/brain-475578/
    name: Brain
  -
    link: https://thenounproject.com/icon/yes-5537946/
    name: Check
  -
    link: https://thenounproject.com/icon/sad-1515667/
    name: Sad
  -
    link: https://thenounproject.com/icon/bracket-3883565/
    name: Bracket
---

## Motivation
After opening a directory it is the developers job to filter out the files that are not relevant to their task at hand. The more words to filter, the more difficult it becomes to quickly orient themselves and start making changes. Disallowing package within the class name promises to reduce this information overload.

### Reduces information overload
![Reduces information overload](/assets/why-disallow-package-within-the-class-name/package-information-overload.png)

As developers are choosing names for their classes the overall length plays a huge role in the clarity it provides. Too long and it becomes unwieldy to use in in our thoughts and conversation. Disallowing package within the class name promises to free developers to use more descriptive and relevant words.

### Encourages more descriptive/relevant words
![Encourages descriptive/relavant words](/assets/why-disallow-package-within-the-class-name/package-relevant-words.png)
