---
layout: post
title:  "Why use onion layering?"
last_modified_at: 2024-07-13 07:56:00 -0000
read_time: 4 min read
view_count: 6.9k
comment_count: 85
categories: blog software-architecture
image:
  path: /assets/why-use-onion-layering/onion.png
  height: 100
  width: 100
---

> You know you got it right if you cry more each time you look at another layer. Thats why it’s called Onion Architecture. - [Top Reddit Comment](https://www.reddit.com/r/programming/comments/1dxipgu/why_use_onion_layering/lc1xvqv/)

<div style="display:flex;justify-content:center">
    <img src="/assets/why-use-onion-layering/onion.png" alt="Onion" style="max-height:558px">
</div>

## Context
For those seeking to understand *what* onion layering is and its relationship to other architectures I recommend checking out some of my favorite articles on the topic here 👉 [what is onion layering?](#related-background-articles)

This post provides a terse overview of *why* you might pursue onion layering with a few examples. I created these notes so that I could quickly set the frame for group discussions on whether a given use case warrants an onion approach.

## Rationale 

### 1. Reduces blast radius of change
![Code Base Damage](/assets/why-use-onion-layering/change-damage.png)
There is a constant assault on our code base in the form of feature enhancements, bug fixes, and hygiene. Envision each incoming change as a bomb 💣, and the damage it does is based on the number of files impacted. Onion layering promises to reduce this blast radius.


### 2. Accelerates understanding
![Reduces time to understand existing behaviors](/assets/why-use-onion-layering/change-time.png)

Each change bomb is typically unique and requires a deep understanding of our code bases existing behaviors. Onion layering promises to reduce the time to understand existing behaviors.

## Examples

### Adding a field to our API

Imagine the most annoying possible client of our microservice. Suppose they want a new field, and they insist that it be named a certain way. Not only that but the API Stewards mandate that the new field be prefixed with a 25 character prefix and 45 character suffix.

The resulting request object that hits our system is horrifyingly ugly. It will sit in the .api.\* layer of our onion architecture, and **it will go no further**. Our .core\.* classes will not be beholden to the insane demands of our clients. Instead we can represent this new field in an idiomatic way that feels native to the language we are using.

Onion layering reduced how much pain our clients inflicted on our code base to the .api.\* package and in doing so also increased the readability of our .core.\* package.

![Example damage control](/assets/why-use-onion-layering/example-damage-control.png)

### Introducing a new downstream dependency

Imagine the most annoying possible microservice dependency. Suppose every input field is an acronym, they are using SOAP, and in the middle of revamping their whole API design.

The raw code to interact with this dependency is horrifyingly ugly and has inevitable upcoming changes. It will sit in the .infra.\* layer of our onion architecture, and **it will go no further**. Our .core.\* classes will not be beholden to speak the deprecated language of our downstream dependency. Instead we will reflect exactly what we need with the latest ubiquitous language of our team via an interface in .core.\*.

Onion layering reduced how much pain our dependency inflicted on our code base to the .infra.\* package and in doing so also increased the readability of our .core.\* package.

![Example damage control - dependency](/assets/why-use-onion-layering/damage-control-dependency.png)


### Introducing a new library dependency

Imagine the most annoying possible library dependency. Suppose they have an interface we need to use, but constructing the object requires 10 configuration fields, 5 separate object dependencies, encryption algorithm selection, and a custom HTTP client.

The raw code to wire up this dependency is completely irrelevant to our existing behaviors. It will sit in the .config.\* layer of our onion architecture, and **it will go no further**.

Onion layering isolates the distracting details of our new library into the .config.\* package and in doing so also increases the readability of the rest of our code base.

![Example clarity - configuration isolation](/assets/why-use-onion-layering/configuration-example.png)

### Appendix

#### Discussion Threads
* [Hacker News](https://news.ycombinator.com/item?id=40898715)
* [Reddit](https://www.reddit.com/r/programming/comments/1dxipgu/why_use_onion_layering/)
* [LinkedIn](https://www.linkedin.com/posts/garrettdbates_why-use-onion-layering-activity-7215731052445589504-6hAJ?utm_source=share&utm_medium=member_desktop)

#### Related Background Articles
* [https://herbertograca.com/2017/11/16/explicit-architecture-01-ddd-hexagonal-onion-clean-cqrs-how-i-put-it-all-together/](https://herbertograca.com/2017/11/16/explicit-architecture-01-ddd-hexagonal-onion-clean-cqrs-how-i-put-it-all-together/)
* [https://jeffreypalermo.com/2008/07/the-onion-architecture-part-1/](https://jeffreypalermo.com/2008/07/the-onion-architecture-part-1/)
* [https://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html](https://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html)
* [https://www.youtube.com/watch?v=_Js-GEqB-8I](https://www.youtube.com/watch?v=_Js-GEqB-8I)
* [https://alistair.cockburn.us/hexagonal-architecture/](https://alistair.cockburn.us/hexagonal-architecture/)
* [https://stackoverflow.com/questions/21554977/
should-services-always-return-dtos-or-can-they-also-return-domain-models#answer-21569720](https://stackoverflow.com/questions/21554977/
should-services-always-return-dtos-or-can-they-also-return-domain-models#answer-21569720)
* [https://netflixtechblog.com/ready-for-changes-with-hexagonal-architecture-b315ec967749](https://netflixtechblog.com/ready-for-changes-with-hexagonal-architecture-b315ec967749)

#### Lucidchart Folder
* [https://lucid.app/documents#/documents?folder_id=375593430](https://lucid.app/documents#/documents?folder_id=375593430)

#### Noun Project Icons
* [Arrow](https://thenounproject.com/icon/arrow-2146615/)
* [Explosion](https://thenounproject.com/icon/explosion-563988/)
* [Halo](https://thenounproject.com/icon/halo-4031793/)
* [File](https://thenounproject.com/icon/file-354396/)
* [Brain](https://thenounproject.com/icon/brain-475578/)