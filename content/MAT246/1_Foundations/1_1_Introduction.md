---
title: "1.1. Introduction"
draft: false
---
This is the [Baron Münchhausen](https://en.wikipedia.org/wiki/File:Muenchhausen_Herrfurth_7_500x789.jpg). (I can't embed images yet sorry.)

In one of his adventures, he rides his horse into a marsh and get trapped in the mud. He pulls from his hair upwards, freeing both the horse and himself from his fate.

In real life, he would not be able to do this without standing on **solid ground**. This begs the question: what is math build on?

Consider the childish game of repeatedly asking **what is that?** For instance, you may study _continuous mappings_. What is that? Well, it is a type of _real-valued function_. What is that? Well, it is a type of _[[1_4_Functions|function]]_. What is that? Well, a special _[[1_3_Relations|relation]]_. What is that? A sub-_set_ of a Cartesian product... In the end, these games always hit the same bottom: a _set_. What is a _set_?

Like the Baron stuck in mud, we have run into the following situation.
## Münchhausen's trilemma

>**Any truth** ultimately boils down to one of three types of arguments.
>
>1. _Circular:_ the proof of some proposition presupposes the truth of that very proposition.
>2. _Infinitely regressive:_ the proof requires a further proof, ad infinitum.
>3. _Dogmatic:_ the proof rests on accepted precepts which asserted without proof.

## Russel's paradox

One might naively think that a _set_ is any well-defined collection of objects. But what does _well-defined_ mean exactly? Consider the following collection of sets.

$$
X=\{x:x\notin x\}
$$

Notice that the following statements are _logically equivalent_. In symbols,

$$
X\in X\quad\iff\quad X\notin X
$$

I have arrived at a contradiction. How do we resolve this? One way is to make rules that govern what things can be sets. These rules should not allow $X$ to be a set, to avoid this paradox.

Evidently, the problem of making a set of rules that will disallow **all** paradoxes is much more complicated than you might think.

**Further recommended reading:**
- [Here](https://en.wikipedia.org/wiki/Zermelo%E2%80%93Fraenkel_set_theory) are the axioms (the _dogmas_ of math) that govern modern set theory, and thus all of modern math.
- Veritasium's great summary [video](https://youtu.be/HeQX2HjkcNo?si=_yv1taK4Kn6d0BXp).