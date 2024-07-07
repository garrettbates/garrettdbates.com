---
layout: post
title:  "Why use onion layering?"
date:   2024-07-07 03:51:45 -0700
categories: jekyll update
---
# Why use onion layering?

## Motivation 
There is a constant assault on our code base in the form of feature enhancements, bug fixes, and hygiene. Envision each incoming change as a bomb :bomb:, and the damage it does is based on the number of files impacted. Onion layering promises to reduce this blast radius.

### Reduces blast radius of change
![Code Base Damage](/assets/why-use-onion-layering/change-damage.png)

Each change bomb is typically unique and requires a deep understanding of our code bases existing behaviors. Onion layering promises to reduce the time to understand existing behaviors.

### Accelerates understanding
![Reduces time to understand existing behaviors](/assets/why-use-onion-layering/change-time.png)

## Examples

### Adding a field to our API

Imagine the most annoying possible client of our microservice. Suppose they want a new field, and they insist that it be named a certain way. Not only that but the API Stewards mandate that the new field be prefixed with a 25 character prefix and 45 character suffix.

The resulting request object that hits our system is horrifyingly ugly. It will sit in the .api.\* layer of our onion architecture, and **it will go no further**. Our .core\.* classes will not be beholden to the insane demands of our clients. Instead we can represent this new field in an idiomatic way that feels native to the language we are using.

Onion layering reduced how much pain our clients inflicted on our code base to the .api.\* package and in doing so also increased the readability of our .core.\* package.

![Example damage control](/assets/why-use-onion-layering/example-damage-control.png)

### Introducing a new downstream dependency

Imagine the most annoying possible microservice dependency. Suppose every input field is an acronym, they are using SOAP, and output is spread across response headers, body, and cookies.

The raw code to interact with this dependency is horrifyingly ugly. It will sit in the .infra.\* layer of our onion architecture, and **it will go no further**. Our .core.\* classes will not be beholden to speak the insane language of our downstream dependency. Instead we will reflect exactly what we need via an interface in .core.\*.

Onion layering reduced how much pain our dependency inflicted on our code base to the .infra.\* package and in doing so also increased the readability of our .core.\* package.

![Example damage control - dependency](/assets/why-use-onion-layering/damage-control-dependency.png)


### Introducing a new library dependency

Imagine the most annoying possible library dependency. Suppose they have an interface we need to use, but constructing the object requires 10 configuration fields, 5 separate object dependencies, encryption algorithm selection, and a custom HTTP client.

The raw code to wire up this dependency is completely irrelevant to our existing behaviors. It will sit in the .config.\* layer of our onion architecture, and **it will go no further**.

Onion layering isolates the distracting details of our new library into the .config.\* package and in doing so also increases the readability of the rest of our code base.

![Example clarity - configuration isolation](/assets/why-use-onion-layering/configuration-example.png)