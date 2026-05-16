Section 1: Intro
Imagine a turtle walking on an endless plane. 
Because of unknown reasons, this turtle has a pen attached to its body, touching the plane.
As the turtle moves, it draws lines to the plane. 
You can command this turtle to either change its direction by any degree, or move a step forward.
This is the basic idea behind "Turtle graphics", although it is a resticted version of it. 
It's already known that even with this very basic set of instructions, we can draw very complicated shapes.

This article will show a specific family of drawings that uses the essence of turtle graphics, 
combined with very simple mathematical functions, which creates beautiful, 
symmetric images which has both symmetry and chaotic nature. 
With only two integers as input, the algorithm outputs an infinite variety of stunning results. 
Here are a few selected examples:

{{
AGENT: Put a horizontally slided list of images. We can generate them using the algorithm. Make the code tweakable so that I can choose which images to show later.
}}

As you can see, these graphs has rosette-like symmetric structures with some chaotic behaivor and has some number of "petals" that repeats. 
After showing the algorithm that generates them, we'll analyze the mathematical reason behind these symmetries.

Section 2: The Algorithm

Our algorithm is very simple, as promised: 
* Turtle starts facing east, but any other direction works as well.
* Choose two relatively prime integers r and s, i.e. with no common (positive) divisors except 1.
* Let N be the maximum number of steps that whe turtle will move. 
  N depends on s whose relation will be given later. 
  N is at most 6s and is an integer multiple of s.
* For n from 1 to N, turtle repeats the following:
    - Move one step forward in the curent facing direction
    - Rotate facing direction clockwise by n^2 * 360 * r / s degrees (or equivalently n^2 * 2 * PI * r / s radians)

For simplicity of analysis, we can assume turtle starts at origin and faces towards positive x-axis.
Lets see some small examples where 1 <= s <= 12. Also we'll set r = 1 for now. 
We'll se the effect of different r values later:

{{
AGENT: Put an interactive section here. User should be able to select s value and could see resultant N and also the image drawn with these values.
}}

From these simple cases, we see all graphs has reflectional symmetries, and most of them also have rotational symmetries. 
Here is a table of symmetry groups (rotations and reflections) that each graph belongs to:

{{
    AGENT: Give a table showing s, N, symmetry group that the graph belongs to.
}}

We see that the rotational symmmetries has order 1, 2, 3, 4, 6, and 12, which are divisors of 12. 
Besides, repeating petal like structures all have reflection symmetries. 
Let's see why this happens in the next section.

Section 3: The Math of Symmetry

{{
    AGENT: In this section, simply explain why we see symmetric shapes. 
    First, derive the formula for the heading angle after n steps. 
    Then prove that the change of angles (i.e. relative rotations) are s periodic, 
    and heading angle is k*s periodic for k is a divisor of 6.
    Explain what those periodicities mean geometrically.
    Then explain the palindromic nature of n^2 and prove that this and the above two periodicity 
    makes almost all of the symmetric images we see before (I'm not sure this is true, so verify it).
    Also create a random turtle walk having the same set of properties as the n^2 angle change: 
    s and k*s periodicity and palindromic nature of s length sub walks.
    After that, show a few example with degree 4 and degree 12 symmetry, and emphasize these are not divisors of 6.
    Next, show that when 4 | s, we have also s/2 shift equivalence property which makes some graphs with 4 and 12 symmetries.
}}

Section 4: More Math and Future Work

{{
    AGENT: In this section, briefly explain exponential sums by first giving a small intro on complex plain, s-th roots of unity.
    The give some existing literature on the topic about bounds on the exponential sums and put my work a place in the existing
    exponential sums literature. Express that detailed analysis on this topic in this exponential sum perspective may 
    open more analysis results. Give a few links to D. H. Lehmer's work on the topic, especially "Incomlete Gauss Sums" and 
    "Picturesque Exponential Sums I and II". 
}}
