---
{"dg-publish":true,"permalink":"/05-notes/single-responsibility-principle/","dgHomeLink":true,"dgPassFrontmatter":false}
---


# Single Responsibility Principle
Tags: #🌲evergreen 
Links: [[Encapsulation|Encapsulation]]

---
Every [[05 notes/Software Unit|Software Unit]] should encapsulate and have responsibility over a single part of the system that overlaps as little as possible. [^1]

In other words, you should write the system gathering things that change for the same reasons and separating those things that change for different reasons (see [[05 notes/Cohesion and Coupling|Cohesion and Coupling]]).

One intention of this principle is to improve [[05 notes/Organizational Scalability|Organizational Scalability]] by allowing developers to work on different parts of the system without affecting each others work.

It also makes it easier to reason about a module by reducing [[Team Cognitive Load|Team Cognitive Load]] by helping to [[Abstraction|abstract away unecessary details]].

Having separate responsibilities also leads to a more robust code base. Example: a module that compiles a report and prints it. Without applying SRP any change to the compilation responsibility would affect the unrelated printing responsibility.

## Separation of Concerns
Separation of Concerns is considered the same as SRP here [^2]. It originally states that each class should have only one reason to change (or responsibility). Example: an invoice class should not have to print itself.

[^1]: [Single-responsibility principle - Wikipedia](https://en.wikipedia.org/wiki/Single-responsibility_principle)
[^2]:  [Difference between Single Responsibility Principle and Separation of Concerns - Stack Overflow](https://stackoverflow.com/questions/1724469/difference-between-single-responsibility-principle-and-separation-of-concerns)
[^3]: