---
title: "Advice on learning math"
draft: false
---
## The growth mindset

An observation I have made teaching is that many students believe you need talent to be good at math. I find this belief interesting, since the same people holding it will acknowledge the fact that, for example in athletics and sports, one needs to train before getting good. One needs to lift weights to get stronger, one needs to run laps to become faster, one needs to train to improve. Yet in math, there is the belief that some people simply get it while others do not. Solving problems, doing exercises, learning how to write proofs, are necessary precursors to becoming good at math. This has been researched extensively and in a more general framework by [Dr. Carol Dweck](https://youtu.be/wh0OS4MrN3E?si=6ZS0K5TSUMxmOutW).

Anecdotally, the students who try solving the greatest number of exercises are the ones who get **better grades**. Hockey players that push the limits of their ability during training know that they are meant to fall. Engineers know that stuff is meant to break over and over again. Power-lifters know that they are meant to reach muscle failure. Soccer players know that they are meant to miss while training. Otherwise, they are not training, they are merely repeating what they already know. Doing math and, more concretely, writing proofs is like any other skill you get good at: by practicing. It is meant to be challenging. Starting out confused and unsure about what to use is part of the process. Otherwise, if you already know how to solve a problem and write down the solution, then you will not learn anything new by doing it.

## To solve a difficult problem, solve an easier one

When I was in high school, we were learning how to calculate _determinants_ of matrices by minors. If you know what this means, then you know that this can be a long and tedious process, especially for larger matrices. The course was completely computation-focused and we did not cover any theory beyond the definitions. So one day, the teacher wrote a huge matrix on the board and left us to work on it for the entire class. Something like this:

$$
\begin{pmatrix}
1 & 2 & 3 & 6 & 3\\
2 & 1 & 1 & 5 & 3\\
3 & 2 & 3 & -1 & 5\\
2 & 1 & 7 & 0 & 3\\
-1 & 0 & -1 & -4 & -1
\end{pmatrix}
$$

The teacher's daughter, an early undergrad, came to drop off some documents for her at the end of the class. As she was walking out of the room she took one glance at the board and, after thinking about it for a few seconds, triumphantly exclaimed, it's zero right? The class was stunned. **Her brain must be a thousand times faster than ours**, we all thought.

Years later I learned that matrices are not just arrangements of numbers, but they represent _linear transformations_. This insight eventually led me to understand that if, for example, the columns of a matrix are linearly dependent, then the transformation cannot be invertible, and thus its determinant is zero. This idea does not require nearly as much computation. If you look at the matrix in the above exercise, indeed the first two columns add up to the last, and so a clever observer would immediately be able to tell that the determinant was zero.

This epiphany is not about linear algebra. It is about the fact that we often assume that some people are much faster and smarter because of their ability to solve very difficult problems. When in reality, because of knowledge, practice, or just luck, but generally all three of them, they find an easier problem to be solved beneath the seemingly harder one. 

## The ingredients of success

Here are some concrete tips that might help you succeed in your math proof-based courses. Most courses follow a structure where you are given definitions, then theorems using those definitions and then proofs of the theorems. Finally, you are given a list of exercises to practice on, and then you are evaluated by having to write down a proof using the definitions and theorems and similar techniques to the ones you saw in the exercises. Most proof-based courses from early undergraduate to advanced graduate level follow this basic structure.

If you are given the reading material or notes before the lecture, spend some time reading them **before** each class. This will allow you to focus on the difficult things and give you a chance to ask relevant questions in the moment. Doing this requires good time-management skills, but it will save you time in the long run, since you

- prevent attending a lecture where you are either distracted or confused for most of the time; and
- when you see something for the second time, you absorb more of the content.

From personal experience, unless the lecturer is particularly engaging, if I don't come prepared to class, later reviewing the notes feels like seeing the material for the first time.

## How to read math

**How to read a definition:** Try coming up with examples and non-examples yourself. Ask yourself what are the edge cases, the exceptions. Is there an aspect of the definition that seems nuanced or overly complicated? There might be a reason for this, so ask. You conclusions should be documented as part of your notes, so you can refer to them later. You never know if you are later asked to submit an exercise involving something very similar to what you already wrote down somewhere.

**How to read a theorem:** Try seeing if you can understand it intuitively first. Make a mental model of the concepts being used. For example, the _Intermediate Value Theorem_ can be understood by noticing that drawing a curve without lifting the pencil from one side of the $x$-axis to the other must necessarily cross the axis. Then, try proving the theorem yourself before you read the proof given in the lecture/textbook. If you get stuck, read the first line of the proof and then continue. This might seem like a huge time investment and, well, it is. But understanding the subject in depth **pays off**. Reflect on the following questions during this process:

- Is the proof in the textbook very different from the one you wrote yourself? Why?
- Is there anything nuanced you missed during your intuitive explanation?

In the above example with the Intermediate Value Theorem, you may realize that the definition of continuous function is more complicated than the analogy with the pencil. For example, if the domain of the function is _disconnected_, then it is no longer true that you can draw the graph without lifting the pencil from the paper.

**How to do exercises:** You typically don't want to start solving them until you have at least understood the statements of the theorems: enough for you to get a feel as to how and where you they can be applied. The first few exercises tend to be simple applications of the definitions. For example, prove that $f(x)=x^3$ is continuous everywhere. More challenging exercises will require you to apply the theorems seen in the chapter, and the harder exercises are the ones that require you to prove entirely new theorems, often based on similar developed techniques.

So, what should you do when you get stuck? And remember, you **should** get stuck. Keep trying and let yourself be stuck, and when you need help get help from someone else. Contact your instructor, TA for help or hints of advice. It also helps to work well in advance of deadlines. When pressured to get work done in a short time period, you learn less and it's more stressful. Working ahead allows you the time to be stuck, ponder, and ask for help. Using time as an ally and not a deadline marker puts time in your favor.