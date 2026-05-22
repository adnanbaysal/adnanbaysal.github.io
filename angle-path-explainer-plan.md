Section 1: Intro
Imagine a turtle walking on an endless plane. 
Because of unknown reasons, this turtle has a pen attached to its body, touching the plane.
As the turtle moves, it draws lines to the plane. 
You can command this turtle to either change its direction by any degree, or move a step forward.
This is the basic idea behind "Turtle graphics", although it is a resticted version of it. 
It's already known that even with this very basic set of instructions, we can draw very complicated shapes. 

But complicated drawings require a complicated algorithm to instruct the turtle, right. 
This article will prove that may not be the case. We'll draw very detailed and beautiful images 
which combines symmetry and chaos with a very simple algorithm that is based on some nice mathematical structure. 
With only two integers as input, the algorithm outputs an infinite variety of stunning results. 
Here are a few selected examples:

{{
AGENT: Put an interactive section here showing some predefined set of images by clicking the corresponding button.
}}

As you can see, these graphs has rosette-like symmetric structures with some chaotic behaivor. 
The images have repeating patterns in a circular way, which we call "petals". 
In the next section, we'll explain the algorithm that generates them. 
Next, we'll analyze the mathematical reason behind these symmetries.

Section 2: The Algorithm
Assume our turtle is facing to the east, but any other direction works as well.
Choose two relatively prime integers r and s, i.e. with no common (positive) divisors except 1.
Although not a restriction, it's enough to consider the case 1 <= r < s.

* Calculate the number of steps N using s using a formula that will be given later. 
  The formula will result in a positive integer multiple of N that is at most 6s.
* Calculate the unit angle of rotation c = 2 * PI * r / s radians, or ecuivalently 360 * r / s degrees.
  Note that this rotation is r / s of a full turn, that's one reason why we select them coprime and r < s.
* For n from 1 to N, turtle repeats the following:
    - Move one step forward in the curent facing direction
    - Rotate facing direction clockwise by n^2 * c radians.

For simplicity of analysis, we can assume turtle starts at origin and faces towards positive x-axis.
Lets see some small examples where 1 <= s <= 12. Also we'll set r = 1 for now. 
We'll se the effect of different r values later:

{{
AGENT: Put an interactive section here. User should be able to select s value and could see resultant N and also the image drawn with these values.
}}

From these simple cases, we see all graphs has reflectional symmetries, and most of them also have rotational symmetries. 
Mathematically, these graphs form a Dihedral group: Groups with rotational and reflectional symmetries. 
Here is a table of Dihedral groups that each graph belongs to:

{{
    AGENT: Give a table showing s, N, symmetry group that the graph belongs to.
}}

We see that the rotational symmmetries has order 1, 2, 3, 4, 6, and 12, which are divisors of 12. 
Besides, repeating petal like structures all have reflection symmetries. 
We'll see why this happens in the next section.

Section 3: The Math Behind the Symmetries

{{
    AGENT: In this section, simply explain why we see symmetric shapes. 
    First, derive the formula for the heading angle after n steps. 
    Then show that for both angle change and cumulative orientation, we can simplify arithmetic in modulo s.
    After that, prove that the change of angles (i.e. relative rotations) are s-periodic, 
    and heading angle is k*s periodic for some k which is a divisor of 6.
    Explain what those periodicities mean geometrically.
    Then explain the palindromic nature of n^2 mod s, and prove that this and the above two periodicity 
    makes almost all of the symmetric images we see before (I'm not sure this is true, so verify it first).
    Also create a random turtle walk having the same set of properties as the n^2 angle change: 
        - s-period for angle change, 
        - a multiple of 2PI/6 as offset after s steps, 
        - k*s period for total angle, and 
        - palindromic nature of s length sub walks.
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
