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
moreFromAuthor:
  -
    path: _posts/2024-07-20-why-prefer-unit-testing-through-layer-entrypoints.md
  - 
    path: _posts/2024-07-13-why-package-by-feature-first-and-then-layer.md
  -
    path: _posts/2024-07-20-why-disallow-package-within-the-class-name.md
discussionPages:
  - https://www.reddit.com/r/programming/comments/1dxipgu/why_use_onion_layering/
  - https://www.linkedin.com/posts/garrettdbates_why-use-onion-layering-activity-7215731052445589504-6hAJ?utm_source=share&utm_medium=member_desktop
  - https://news.ycombinator.com/item?id=40898715
backgroundArticles:
  - 
    link: https://herbertograca.com/2017/11/16/explicit-architecture-01-ddd-hexagonal-onion-clean-cqrs-how-i-put-it-all-together/
    image: /assets/related-articles/070-explicit-architecture-svg.png
    title: DDD, Hexagonal, Onion, Clean, CQRS, … How I put it all together
    date: 2017-11-16
  -
    link: https://jeffreypalermo.com/2008/07/the-onion-architecture-part-1/
    image: /assets/related-articles/palermo-onion.png
    title: "The Onion Architecture : part 1"
    date: 2008-07-01
  -
    link: https://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html
    image: /assets/related-articles/CleanArchitecture.jpg
    title: The Clean Architecture
    date: 2012-08-13
  -
    link: https://www.youtube.com/watch?v=_Js-GEqB-8I
    image: https://i.ytimg.com/vi/_Js-GEqB-8I/maxresdefault.jpg?sqp=-oaymwEmCIAKENAF8quKqQMa8AEB-AH-CYAC0AWKAgwIABABGFYgXShlMA8=&rs=AOn4CLDL869SYpTxeyTVzcSt_NAYoXm4Rw
    title: Sławek Sobótka - Ports and Adapters architecture
    date: 2013-04-10
  -
    link: https://alistair.cockburn.us/hexagonal-architecture/
    image: https://alistair.cockburn.us/wp-content/uploads/2017/03/logo285x146-half.png
    title: Hexagonal architecture
    date: 2017-03-01
  -
    link: https://stackoverflow.com/questions/21554977/should-services-always-return-dtos-or-can-they-also-return-domain-models#answer-21569720
    image: https://cdn.sstatic.net/Sites/stackoverflow/Img/apple-touch-icon@2.png?v=73d79a89bded
    title: Should services always return DTOs?
    date: 2014-02-05
  -
    link: https://netflixtechblog.com/ready-for-changes-with-hexagonal-architecture-b315ec967749
    image: https://miro.medium.com/v2/resize:fill:1200:632/g:fp:0.49:0.49/1*NfFzI7Z-E3ypn8ahESbDzw.png
    title: Ready for changes with Hexagonal Architecture
    date: 2020-03-10
lucidchart:
  link: https://lucid.app/folder/invitations/accept/inv_62b31f1e-a79e-491c-a203-0727d4034c27
  image: /assets/why-use-onion-layering/lucidchart-folder.png
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

---

> You know you got it right if you cry more each time you look at another layer. Thats why it’s called Onion Architecture. - [Top Reddit Comment](https://www.reddit.com/r/programming/comments/1dxipgu/why_use_onion_layering/lc1xvqv/){:target="_blank"}

<div style="display:flex;justify-content:center">
    <img src="/assets/why-use-onion-layering/onion.png" alt="Onion" style="max-height:558px">
</div>

## Context
For those seeking to understand *what* onion layering is and its relationship to other architectures I recommend checking out some of my favorite articles on the topic here 👉 [what is onion layering?](#related-background-articles)

This post provides a terse overview of *why* you might pursue onion layering with a few examples.

I've found these notes to be valuable in quickly setting the frame for group discussions on whether onion layering should be used in a certain setting. Hopefully they will help you too.

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