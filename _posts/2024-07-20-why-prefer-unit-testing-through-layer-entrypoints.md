---
layout: post
title: Why prefer unit testing through layer entrypoints?
date: 2024-07-20 08:50 -0700
read_time: 3 min read
categories: blog software-architecture
---

## Status Quo
There is significant artistic variance on how to craft tests which provide developers quick and useful feedback. A common point of contention is the number of files which should be included within these quick and useful tests. The most popular strategy is to have a single file under test at a time.

![Most popular solitary unit testing](/assets/why-prefer-unit-testing-through-a-layer-entrypoint/most-popular.png)

The solitary unit testing strategy is popular for a reason. They are guaranteed to run fast and are typically simple to author. 

## Motivation
Solitary unit tests while popular, have a few drawbacks. First and foremost it hinders our ability to confidently refactor across multiple files. An individual file working correctly doesn't imply it works well with its neighbors.  

![Refactoring multiple files](/assets/why-prefer-unit-testing-through-a-layer-entrypoint/refactoring-multiple-files.png)

A second drawback to solitary unit tests is the need to update tests when refactoring. This effectively **doubles** the amount of code change during a refactor even when the observable behavior of the system hasn't changed.

![Solitary refactor damage multiplier](/assets/why-prefer-unit-testing-through-a-layer-entrypoint/solitary-refactor-damage-multiplier.png)

This lack of confidence and double-work of refactoring is discouraging to those who seek to improve and refine the structure of the code base.

## Solution
Proposed solve to unlock refactoring freedom is to prioritize sociable unit tests which focus on [layer](/blog/software-architecture/why-use-onion-layering) interfaces. In doing so we get higher confidence when refactoring with zero test change overhead.

![Refactoring freedom](/assets/why-prefer-unit-testing-through-a-layer-entrypoint/refactoring-freedom.png)

These tests will also get to piggy-back on layer isolation making them more stable and isolated from changes in other parts of the code base.

![Layer change isolation](/assets/why-prefer-unit-testing-through-a-layer-entrypoint/layer-change-isolation.png)

## Risks and mitigations
The proposal to prefer unit testing through a layer entry point does not come without its own fair share of drawbacks. These are acknowledged with mitigations listed below.

<table>
  <thead>
    <tr>
      <th><span style="color:red">Risk</span></th>
      <th><span style="color:green">Mitigation</span></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Unit test takes longer to run</td>
      <td><ul><li>Restrict scanning to the layer under test</li></ul></td>
    </tr>
    <tr>
      <td>Test setup becomes more complex</td>
      <td><ul><li>Maintain reusable layer-specific testing configurations</li><li>Maintain convention for factory methods to default injected dependencies to the happy path</li><li>Prefer <a href="https://kotlinlang.org/docs/fun-interfaces.html#sam-conversions">SAM</a> interfaces to simplify mocking dependencies</li></ul></td>
    </tr>
    <tr>
      <td>Difficult to test exhaustively</td>
      <td><ul><li>Allow fallback to solitary tests based on developer judgement</li></ul></td>
    </tr>
  </tbody>
</table>


### Appendix

#### Related Background Articles
* [https://martinfowler.com/bliki/UnitTest.html](https://martinfowler.com/bliki/UnitTest.html)
* [https://dev.to/dylanwatsonsoftware/socialise-your-unit-tests-5da0](https://dev.to/dylanwatsonsoftware/socialise-your-unit-tests-5da0)
* [https://garrettdbates.com/blog/software-architecture/why-use-onion-layering](https://garrettdbates.com/blog/software-architecture/why-use-onion-layering)

#### Discussion Threads
* [Hacker News](https://news.ycombinator.com/item?id=41018406)
* [Reddit](https://www.reddit.com/r/programming/comments/1e81vil/why_prefer_unit_testing_through_layer_entrypoints/)
* [LinkedIn](https://www.linkedin.com/posts/garrettdbates_why-prefer-unit-testing-through-layer-entrypoints-activity-7220486583773224960-9xLl?utm_source=share&utm_medium=member_desktop)
* [Twitter](https://x.com/garrettdbates/status/1814721450227671427)

#### Lucidchart Folder
* [https://lucid.app/folder/invitations/accept/inv_bffe0f2e-8ba2-4e55-9f6c-c072e86e836b](https://lucid.app/folder/invitations/accept/inv_bffe0f2e-8ba2-4e55-9f6c-c072e86e836b)

#### Noun Project Assets
* [Arrow](https://thenounproject.com/icon/arrow-2146615/)
* [Explosion](https://thenounproject.com/icon/explosion-563988/)
* [Check](https://thenounproject.com/icon/yes-5537946/)
* [Sad](https://thenounproject.com/icon/sad-1515667/)
* [Bracket](https://thenounproject.com/icon/bracket-3883565/)
* [Brain](https://thenounproject.com/icon/brain-475578/)
* [Badge](https://thenounproject.com/icon/badge-1114431/)