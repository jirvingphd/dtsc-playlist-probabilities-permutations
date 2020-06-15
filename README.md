
# Sect 11A: Combinatorics & Probability (last S.G.)


- Study Group for: online-ds-pt-041320

- 06/12/20


## Learning Objectives

- Understand what sets are and set operations.
- Understand what probability is and how it is calculated.
- Understand factorials, permutations, and combinations. 

- **Activity: Playlist Probabilities**

### Links/References:
- Study Groups:
    - [Reviewing Probability & Combinatorics - M3S17 [2019-07-16]](https://www.youtube.com/watch?v=UBWnkflWvmU&list=PLVoXE6pv5LIgIui2D6u0Nga3oHtQ2ogmY&index=2) - Victor
    - [Permutations & Factorials](https://youtu.be/-tzUcmASgC8) - Jeff
    - [Permutations/Combinations](https://www.youtube.com/watch?v=WMYnIe2f7to&feature=youtu.be) - Rafael


## QUESTIONS:



## Part 1: Intro to Probability

### Sets


> A **Set**: *a well-defined collection of unique objects*.

**Math notation:**
- Define a set as $S$ 
- If $x$ is an element of set $S$:
    - $x \in S$.
- If $x$ is not an element of set $S$:
    - $x\notin S$.
        
### Subset: 
> A **Subset**: set $T$ is a subset of set $S$ if *every element* in set $T$ is also in set $S$. 

**Math Notation**
- $T$ is a subset of $S$.   
    - $T \subset S$

- $T$ and $S$ can be the SAME population 
- If $T$ != $S$, but $T \subset S$, called a 'proper subset'
    - Can use notation:  $T \subsetneq S$ and $T \subseteq S$ 

### Universal set:
> A **Universal Set**: The collection of all possible outcomes in a certain context or universe.

**Math Notation**
- Universal set denoted by Omega ($\Omega$)
- Can have infinite # of elements (e.g. the set of all real numbers!)
- Example: all possible outcomes of a 6-sided die:
    - $\Omega = \{1,2,3,4,5,6\}$



### Set operations:

- Data used in examples:

Imagine you have two sets of numbers, say the first 4 multiples of 3 in set $S$:

$ S = \{3,6,9,12\}$

 and the first 4 multiples of 2 in set $T$:
 
$ T = \{2,4,6,8\} $.

#### Union (combining elements)

- the union of $S$ and $T$ is denoted as $S \cup T$
<img src="https://raw.githubusercontent.com/jirvingphd/dsc-intro-to-sets-online-ds-ft-100719/master/images/new_union.png" width=200>

#### Intersection

- contains all elements of $S$ that also belong to $T$. 
    - denoted as $S \cap T$.

<img src="https://raw.githubusercontent.com/jirvingphd/dsc-intro-to-sets-online-ds-ft-100719/master/images/new_intersection.png" width=200>

#### Relative complement / difference

<img src="https://raw.githubusercontent.com/jirvingphd/dsc-intro-to-sets-online-ds-ft-100719/master/images/new_rel_comp.png" width=200>

-  the relative complement of S contains all the elements of T that are NOT in S.
    - relative complement of S (or $ T\backslash S $) is $\{2,4,8\}$.
    - relative complement  of T (or $ S\backslash T $) is $\{3,9,12\}$.
    
<!img src="https://raw.githubusercontent.com/learn-co-students/dsc-1-08-07-introduction-to-sets-online-ds-ft-021119/master/rel_comp.png" width=300>

#### Absolute complement

<img src="https://raw.githubusercontent.com/jirvingphd/dsc-intro-to-sets-online-ds-ft-100719/master/images/new_abs_comp.png" width=200>


- The absolute complement of $S$, with respect to the Universal set $\Omega$, is the collection of the objects in $\Omega$ that don't belong to $S$.
    -  absolute complement of $S$ is denoted as $S'$ or $S^c$.
    
<!img src="https://raw.githubusercontent.com/learn-co-students/dsc-1-08-07-introduction-to-sets-online-ds-ft-021119/master/abs_comp.png" width=300>

- Example: Let's define $\Omega$ (box around the two venn diagrams) = multiples of both 2 and 3 until 20.

    - Elements of $\Omega$ are $\{2,3,4,6,8,9,10,12,14,15,16,18,20\}$. 

    - The absolute complement of $S$ (so $S'$ or $S^c$) is then given by $\{2,4,8,10,14,15,16,18,20\}$.
 

### Note on Important Number Sets & Their Notation

- If you define that the event "low daily number of text messages sent" means 20 or fewer text messages, the event space is defined as: $E = \{x \mid x \in \mathbb{Z}, 0 \leq x \leq 20 \}$
- Binge-watch day:  $E = \{x \mid x \in \mathbb{R}, x \geq 6 \}$

| SYMBOL | MEANING |
| --- | --- |
|$\emptyset$ or $\{\}$ | empty set 
|$ \mathbb{N}$ | natural numbers |
|$\mathbb{Z}$ | integers (from Zahl, German for number). |
|$ \mathbb{Q}$ | rational numbers (from quotient) |
|$\mathbb{R}$  | real numbers |
|$ \mathbb{C}$ | complex numbers |

### Inclusion Exclusion principle

- Used to calculate the number of elements of each set and the union of all sets.

- Note $|S|$ denotes the *cardinality* of S aka the number of element in S

<img src="https://raw.githubusercontent.com/jirvingphd/dsc-intro-to-sets-online-ds-ft-100719/master/images/new_venn_diagram.png" width=400>


- When combining  2 sets, the method for obtaining the union of two finite sets is given by:

    - $\mid S \cup T \mid = \mid S \mid + \mid T \mid - \mid S \cap T \mid $
    
        - Horizontal lines denote the *cardinality* of a set, which is the number of elements, considering a finite set. 
- When combining 3 sets:

$\mid S \cup T\cup R \mid = \mid S \mid + \mid T \mid + \mid R \mid - \mid S \cap T \mid  -\mid S \cap R \mid - \mid R \cap T \mid  + \mid S \cap T \cap R \mid $
        
        
- *The formula expresses the fact that the sum of the sizes of the two sets may be too large since some elements may be counted twice. For the double-counted elements, one is substracted again.*

### Empty 
 - An **empty** set has no elements
 - denoted by $\emptyset$ or simply $\{\}$
 
 

### SET OPERATIONS IN PYTHON


 

| Method        |	Equivalent |	Result |
| ------                    | ------       | ------    |
| s.issubset(t)             |	s <= t     | test whether every element in s is in t
| s.issuperset(t)           |	s >= t     | test whether every element in t is in s
| s.union(t)                |	s $\mid$ t | new set with elements from both s and t
| s.intersection(t)         |	s & t      | new set with elements common to s and t
| s.difference(t)           |	s - t 	   | new set with elements in s but not in t
| s.symmetric_difference(t) |	s ^ t      | new set with elements in either s or t but not both

## Probability


### What is probability?

> **Probability is the likelihood of a specific outcome/event occuring out of all possible outcomes, expressed as a fraction between 0 and 1.**
<!---
Example Probability Qs:
- How likely is it to end up with heads when flipping a coin once? (the answer here is 50% - not very surprising)

- How likely is it to end up with exactly 2 x heads and 3 x tails when flipping a coin 5 times?

- How likely is it to throw tails first, then heads, then tails, then heads, then tails when flipping a coin 5 times?

- If you throw 5 dice, what is the probability of throwing a ["full house"](http://grail.sourceforge.net/demo/yahtzee/rules.html)?

- What is the probability of drawing 2 consecutive aces from a standard deck of cards?

> But how do we calculate it? ..._to be continued_...

--->

### Sample Space & Event Space

##### Sample space:

$$S = \{ 1,2,3,4,5,6\}$$ 
being the possible outcomes when throwing a dice.
- Sample space =  $\Omega$ 

##### Event space:

-   The **event space** is a subset of the sample space. It is the **desired outcome** of the experiment.
$$E \subseteq S$$
-   Example:
    -   Throwing an odd number would lead to an event space $$E = \{ 1,3,5\}$$.

### Probability of an Event

$$ P(E) = \frac{|E|}{|S|} $$
probability is the number of possible preferred outcomes over the sample space / all outcomes

### Law of relative frequency

- Limit of large infinite outcomes produce fixed numbers .
$$ \large P(E) = \lim_{n\to\infty}\frac{S(n)}{n}$$
    - Probability of Event E having Successful(S) outcomes for $n$ trials
    

### Probability axioms

1.  Positivity : 

    - Prob is always $0 <= P(E) <=1$


2.  Probability of a certain/guaranteed event:

    - $P(S)=1$


3.  Additivity Union of 2 exclusive sets = sum prob of individual events happening
    
    - If $A\cap B = \emptyset $, then $P(A\cup B) = P(A) + P(B)$

### Addition law of probability 

-   Prob of union of A and B is individual P minus intersection

$$ \large P(A\cup B) = P(A) + P(B) - P(A \cap B)$$

## Permutations

- **Permutations have to do with arranging objects.(Order is important)**

> ***How many ways to arrange n elements?***
    $$\large P(n) = n!$$

### Factorials


The factorial of $n$ is calculated by multiplying every number below $n$ together.

$$n! = n  \times (n-1) \times (n-2)\times...\times1$$



**Factorial Rules/Operations:**
- Negative numbers do not have a factorial.
- $0! = 1$
- $n! = (n-1)! \cdot n$
- $(n+1)! = n! \cdot (n+1)$ 

- $ (n+k)! = n! \cdot (n+1) \cdot (n+2) \cdot... (n+k) $

- $ (n-k)! = \frac{n!}{(n-k+1)\cdot(n-k+2) \cdot ... (n-k+k) }$
- When $n>k$:
    - $\frac{n!}{k!} = (k+1)\cdot(k+2)\cdot...n $

### Permutations of a subset / AKA Permutations without replacement

> ***How many ways to select $k$ elements out of a pool of $n$ objects?***

$$ \large P_{k}^{n}= \dfrac{n!}{(n-k)!}$$ 

this is known as the **$k$-permutation of $n$**

### Permutations with replacement 

$$ \large {P}_{j}^{n} = n^j $$
- where $n$ = total number of elements
- $j$ = number of positions to fill   

### Permutations with repetition

- Permutation where there are some elements that may appear multiple times. 
    - i.e. looking at the word TENNESSEE by itself, you can swap the 3rd and the 4th letter and have the same word. So the total number is less than $9!$.
    
    - The solution is to divide $9!$ by the factorials for each letter that is repeated!
    - The answer here is then (9 letters, 4 x E, 2 x N, 2 x S)

    - $\dfrac{9!}{4!2!2!} = 3780$

The general formula can be written as:

$$\dfrac{n!}{n_1!n_2!\ldots n_j!}$$

where $n_j$ stands for identical objects of type $j$ (the distinct letters in our TENNESSEE example). 

## Combinations

- How many ways can we create a subset $k$ out of $n$ objects, when order is not important? 


$$\large C_{k}^{n} = \displaystyle\binom{n}{k} = \dfrac{P_{k}^{n}}{k!}=\dfrac{ \dfrac{n!}{(n-k)!}}{k!} = \dfrac{n!}{(n-k)!k!}$$

## 📖 Activity: Planning Party Playlists

### Activity Pt 1: Playlist Probabilities

- **We are constructing a dinner party playlist for a gathering we are planning.** 
    - We asked our attendees to each provide a handful of songs they would like to be played at the dinner party.
    - Their suggestions are saved in csvs located in the `probability_playlists/` folder

- **We want the sound-scape of our dinner party to express the tastes of every single attendee, so we will allow for duplicate/repeated songs if multiple people recommended it.**


```python
!pip install -U fsds

from fsds.imports import *
from math import factorial
```

    fsds v0.2.13 loaded.  Read the docs: https://fs-ds.readthedocs.io/en/latest/ 



<style  type="text/css" >
</style><table id="T_77775122_aea3_11ea_a44d_4865ee12e626" ><caption>Loaded Packages and Handles</caption><thead>    <tr>        <th class="col_heading level0 col0" >Handle</th>        <th class="col_heading level0 col1" >Package</th>        <th class="col_heading level0 col2" >Description</th>    </tr></thead><tbody>
                <tr>
                                <td id="T_77775122_aea3_11ea_a44d_4865ee12e626row0_col0" class="data row0 col0" >dp</td>
                        <td id="T_77775122_aea3_11ea_a44d_4865ee12e626row0_col1" class="data row0 col1" >IPython.display</td>
                        <td id="T_77775122_aea3_11ea_a44d_4865ee12e626row0_col2" class="data row0 col2" >Display modules with helpful display and clearing commands.</td>
            </tr>
            <tr>
                                <td id="T_77775122_aea3_11ea_a44d_4865ee12e626row1_col0" class="data row1 col0" >fs</td>
                        <td id="T_77775122_aea3_11ea_a44d_4865ee12e626row1_col1" class="data row1 col1" >fsds</td>
                        <td id="T_77775122_aea3_11ea_a44d_4865ee12e626row1_col2" class="data row1 col2" >Custom data science bootcamp student package</td>
            </tr>
            <tr>
                                <td id="T_77775122_aea3_11ea_a44d_4865ee12e626row2_col0" class="data row2 col0" >mpl</td>
                        <td id="T_77775122_aea3_11ea_a44d_4865ee12e626row2_col1" class="data row2 col1" >matplotlib</td>
                        <td id="T_77775122_aea3_11ea_a44d_4865ee12e626row2_col2" class="data row2 col2" >Matplotlib's base OOP module with formatting artists</td>
            </tr>
            <tr>
                                <td id="T_77775122_aea3_11ea_a44d_4865ee12e626row3_col0" class="data row3 col0" >plt</td>
                        <td id="T_77775122_aea3_11ea_a44d_4865ee12e626row3_col1" class="data row3 col1" >matplotlib.pyplot</td>
                        <td id="T_77775122_aea3_11ea_a44d_4865ee12e626row3_col2" class="data row3 col2" >Matplotlib's matlab-like plotting module</td>
            </tr>
            <tr>
                                <td id="T_77775122_aea3_11ea_a44d_4865ee12e626row4_col0" class="data row4 col0" >np</td>
                        <td id="T_77775122_aea3_11ea_a44d_4865ee12e626row4_col1" class="data row4 col1" >numpy</td>
                        <td id="T_77775122_aea3_11ea_a44d_4865ee12e626row4_col2" class="data row4 col2" >scientific computing with Python</td>
            </tr>
            <tr>
                                <td id="T_77775122_aea3_11ea_a44d_4865ee12e626row5_col0" class="data row5 col0" >pd</td>
                        <td id="T_77775122_aea3_11ea_a44d_4865ee12e626row5_col1" class="data row5 col1" >pandas</td>
                        <td id="T_77775122_aea3_11ea_a44d_4865ee12e626row5_col2" class="data row5 col2" >High performance data structures and tools</td>
            </tr>
            <tr>
                                <td id="T_77775122_aea3_11ea_a44d_4865ee12e626row6_col0" class="data row6 col0" >sns</td>
                        <td id="T_77775122_aea3_11ea_a44d_4865ee12e626row6_col1" class="data row6 col1" >seaborn</td>
                        <td id="T_77775122_aea3_11ea_a44d_4865ee12e626row6_col2" class="data row6 col2" >High-level data visualization library based on matplotlib</td>
            </tr>
    </tbody></table>



```python
import os,glob
datafolder = "probability_playlists/" ## student filepath
rec_files = glob.glob(datafolder+"*.csv")

playlists = {}
for file in rec_files:
    key = os.path.basename(file).replace('_recs.csv','')
    playlists[key] = pd.read_csv(file)
playlists.keys()
```




    dict_keys(['joe', 'james', 'anne', 'john', 'samantha'])




```python
for name,playlist in playlists.items():
    display(playlist.style.set_caption(name))
```


<style  type="text/css" >
</style><table id="T_7ab2842e_aea3_11ea_9f6d_4865ee12e626" ><caption>joe</caption><thead>    <tr>        <th class="blank level0" ></th>        <th class="col_heading level0 col0" >artist</th>        <th class="col_heading level0 col1" >track</th>        <th class="col_heading level0 col2" >Recommended By</th>    </tr></thead><tbody>
                <tr>
                        <th id="T_7ab2842e_aea3_11ea_9f6d_4865ee12e626level0_row0" class="row_heading level0 row0" >0</th>
                        <td id="T_7ab2842e_aea3_11ea_9f6d_4865ee12e626row0_col0" class="data row0 col0" >Green Day</td>
                        <td id="T_7ab2842e_aea3_11ea_9f6d_4865ee12e626row0_col1" class="data row0 col1" >Time of your Life</td>
                        <td id="T_7ab2842e_aea3_11ea_9f6d_4865ee12e626row0_col2" class="data row0 col2" >Joe</td>
            </tr>
            <tr>
                        <th id="T_7ab2842e_aea3_11ea_9f6d_4865ee12e626level0_row1" class="row_heading level0 row1" >1</th>
                        <td id="T_7ab2842e_aea3_11ea_9f6d_4865ee12e626row1_col0" class="data row1 col0" >B-52s</td>
                        <td id="T_7ab2842e_aea3_11ea_9f6d_4865ee12e626row1_col1" class="data row1 col1" >Rock Lobster</td>
                        <td id="T_7ab2842e_aea3_11ea_9f6d_4865ee12e626row1_col2" class="data row1 col2" >Joe</td>
            </tr>
            <tr>
                        <th id="T_7ab2842e_aea3_11ea_9f6d_4865ee12e626level0_row2" class="row_heading level0 row2" >2</th>
                        <td id="T_7ab2842e_aea3_11ea_9f6d_4865ee12e626row2_col0" class="data row2 col0" >Lady GaGa</td>
                        <td id="T_7ab2842e_aea3_11ea_9f6d_4865ee12e626row2_col1" class="data row2 col1" >Poker Face</td>
                        <td id="T_7ab2842e_aea3_11ea_9f6d_4865ee12e626row2_col2" class="data row2 col2" >Joe</td>
            </tr>
            <tr>
                        <th id="T_7ab2842e_aea3_11ea_9f6d_4865ee12e626level0_row3" class="row_heading level0 row3" >3</th>
                        <td id="T_7ab2842e_aea3_11ea_9f6d_4865ee12e626row3_col0" class="data row3 col0" >John Lennon</td>
                        <td id="T_7ab2842e_aea3_11ea_9f6d_4865ee12e626row3_col1" class="data row3 col1" >Imagine</td>
                        <td id="T_7ab2842e_aea3_11ea_9f6d_4865ee12e626row3_col2" class="data row3 col2" >Joe</td>
            </tr>
    </tbody></table>



<style  type="text/css" >
</style><table id="T_7ab2e9e6_aea3_11ea_b4de_4865ee12e626" ><caption>james</caption><thead>    <tr>        <th class="blank level0" ></th>        <th class="col_heading level0 col0" >artist</th>        <th class="col_heading level0 col1" >track</th>        <th class="col_heading level0 col2" >Recommended By</th>    </tr></thead><tbody>
                <tr>
                        <th id="T_7ab2e9e6_aea3_11ea_b4de_4865ee12e626level0_row0" class="row_heading level0 row0" >0</th>
                        <td id="T_7ab2e9e6_aea3_11ea_b4de_4865ee12e626row0_col0" class="data row0 col0" >Eve 6</td>
                        <td id="T_7ab2e9e6_aea3_11ea_b4de_4865ee12e626row0_col1" class="data row0 col1" >Here's to the Night</td>
                        <td id="T_7ab2e9e6_aea3_11ea_b4de_4865ee12e626row0_col2" class="data row0 col2" >James</td>
            </tr>
            <tr>
                        <th id="T_7ab2e9e6_aea3_11ea_b4de_4865ee12e626level0_row1" class="row_heading level0 row1" >1</th>
                        <td id="T_7ab2e9e6_aea3_11ea_b4de_4865ee12e626row1_col0" class="data row1 col0" >Neutral Milk Hotel</td>
                        <td id="T_7ab2e9e6_aea3_11ea_b4de_4865ee12e626row1_col1" class="data row1 col1" >Into the Aeroplane Over the Sea</td>
                        <td id="T_7ab2e9e6_aea3_11ea_b4de_4865ee12e626row1_col2" class="data row1 col2" >James</td>
            </tr>
            <tr>
                        <th id="T_7ab2e9e6_aea3_11ea_b4de_4865ee12e626level0_row2" class="row_heading level0 row2" >2</th>
                        <td id="T_7ab2e9e6_aea3_11ea_b4de_4865ee12e626row2_col0" class="data row2 col0" >Rilo Kiley</td>
                        <td id="T_7ab2e9e6_aea3_11ea_b4de_4865ee12e626row2_col1" class="data row2 col1" >With Arms Outstretched</td>
                        <td id="T_7ab2e9e6_aea3_11ea_b4de_4865ee12e626row2_col2" class="data row2 col2" >James</td>
            </tr>
            <tr>
                        <th id="T_7ab2e9e6_aea3_11ea_b4de_4865ee12e626level0_row3" class="row_heading level0 row3" >3</th>
                        <td id="T_7ab2e9e6_aea3_11ea_b4de_4865ee12e626row3_col0" class="data row3 col0" >Red Hot Chili Peppers</td>
                        <td id="T_7ab2e9e6_aea3_11ea_b4de_4865ee12e626row3_col1" class="data row3 col1" >Otherside</td>
                        <td id="T_7ab2e9e6_aea3_11ea_b4de_4865ee12e626row3_col2" class="data row3 col2" >James</td>
            </tr>
    </tbody></table>



<style  type="text/css" >
</style><table id="T_7ab33ffe_aea3_11ea_add7_4865ee12e626" ><caption>anne</caption><thead>    <tr>        <th class="blank level0" ></th>        <th class="col_heading level0 col0" >artist</th>        <th class="col_heading level0 col1" >track</th>        <th class="col_heading level0 col2" >Recommended By</th>    </tr></thead><tbody>
                <tr>
                        <th id="T_7ab33ffe_aea3_11ea_add7_4865ee12e626level0_row0" class="row_heading level0 row0" >0</th>
                        <td id="T_7ab33ffe_aea3_11ea_add7_4865ee12e626row0_col0" class="data row0 col0" >Smashing Pumpkins</td>
                        <td id="T_7ab33ffe_aea3_11ea_add7_4865ee12e626row0_col1" class="data row0 col1" >Tonight, Tonight</td>
                        <td id="T_7ab33ffe_aea3_11ea_add7_4865ee12e626row0_col2" class="data row0 col2" >Anne</td>
            </tr>
            <tr>
                        <th id="T_7ab33ffe_aea3_11ea_add7_4865ee12e626level0_row1" class="row_heading level0 row1" >1</th>
                        <td id="T_7ab33ffe_aea3_11ea_add7_4865ee12e626row1_col0" class="data row1 col0" >Black Eyed Peas</td>
                        <td id="T_7ab33ffe_aea3_11ea_add7_4865ee12e626row1_col1" class="data row1 col1" >Let's Get it Started</td>
                        <td id="T_7ab33ffe_aea3_11ea_add7_4865ee12e626row1_col2" class="data row1 col2" >Anne</td>
            </tr>
            <tr>
                        <th id="T_7ab33ffe_aea3_11ea_add7_4865ee12e626level0_row2" class="row_heading level0 row2" >2</th>
                        <td id="T_7ab33ffe_aea3_11ea_add7_4865ee12e626row2_col0" class="data row2 col0" >Green Day</td>
                        <td id="T_7ab33ffe_aea3_11ea_add7_4865ee12e626row2_col1" class="data row2 col1" >Time of your Life</td>
                        <td id="T_7ab33ffe_aea3_11ea_add7_4865ee12e626row2_col2" class="data row2 col2" >Anne</td>
            </tr>
    </tbody></table>



<style  type="text/css" >
</style><table id="T_7ab38f06_aea3_11ea_8c5d_4865ee12e626" ><caption>john</caption><thead>    <tr>        <th class="blank level0" ></th>        <th class="col_heading level0 col0" >artist</th>        <th class="col_heading level0 col1" >track</th>        <th class="col_heading level0 col2" >Recommended By</th>    </tr></thead><tbody>
                <tr>
                        <th id="T_7ab38f06_aea3_11ea_8c5d_4865ee12e626level0_row0" class="row_heading level0 row0" >0</th>
                        <td id="T_7ab38f06_aea3_11ea_8c5d_4865ee12e626row0_col0" class="data row0 col0" >Black Eyed Peas</td>
                        <td id="T_7ab38f06_aea3_11ea_8c5d_4865ee12e626row0_col1" class="data row0 col1" >Let's Get it Started</td>
                        <td id="T_7ab38f06_aea3_11ea_8c5d_4865ee12e626row0_col2" class="data row0 col2" >John</td>
            </tr>
            <tr>
                        <th id="T_7ab38f06_aea3_11ea_8c5d_4865ee12e626level0_row1" class="row_heading level0 row1" >1</th>
                        <td id="T_7ab38f06_aea3_11ea_8c5d_4865ee12e626row1_col0" class="data row1 col0" >Lady GaGa</td>
                        <td id="T_7ab38f06_aea3_11ea_8c5d_4865ee12e626row1_col1" class="data row1 col1" >Poker Face</td>
                        <td id="T_7ab38f06_aea3_11ea_8c5d_4865ee12e626row1_col2" class="data row1 col2" >John</td>
            </tr>
            <tr>
                        <th id="T_7ab38f06_aea3_11ea_8c5d_4865ee12e626level0_row2" class="row_heading level0 row2" >2</th>
                        <td id="T_7ab38f06_aea3_11ea_8c5d_4865ee12e626row2_col0" class="data row2 col0" >Lady GaGa</td>
                        <td id="T_7ab38f06_aea3_11ea_8c5d_4865ee12e626row2_col1" class="data row2 col1" >Bad Romance</td>
                        <td id="T_7ab38f06_aea3_11ea_8c5d_4865ee12e626row2_col2" class="data row2 col2" >John</td>
            </tr>
            <tr>
                        <th id="T_7ab38f06_aea3_11ea_8c5d_4865ee12e626level0_row3" class="row_heading level0 row3" >3</th>
                        <td id="T_7ab38f06_aea3_11ea_8c5d_4865ee12e626row3_col0" class="data row3 col0" >Lady GaGa</td>
                        <td id="T_7ab38f06_aea3_11ea_8c5d_4865ee12e626row3_col1" class="data row3 col1" >Just Dance</td>
                        <td id="T_7ab38f06_aea3_11ea_8c5d_4865ee12e626row3_col2" class="data row3 col2" >John</td>
            </tr>
    </tbody></table>



<style  type="text/css" >
</style><table id="T_7ab3e36e_aea3_11ea_8849_4865ee12e626" ><caption>samantha</caption><thead>    <tr>        <th class="blank level0" ></th>        <th class="col_heading level0 col0" >artist</th>        <th class="col_heading level0 col1" >track</th>        <th class="col_heading level0 col2" >Recommended By</th>    </tr></thead><tbody>
                <tr>
                        <th id="T_7ab3e36e_aea3_11ea_8849_4865ee12e626level0_row0" class="row_heading level0 row0" >0</th>
                        <td id="T_7ab3e36e_aea3_11ea_8849_4865ee12e626row0_col0" class="data row0 col0" >Black Eyed Peas</td>
                        <td id="T_7ab3e36e_aea3_11ea_8849_4865ee12e626row0_col1" class="data row0 col1" >Let's Get it Started</td>
                        <td id="T_7ab3e36e_aea3_11ea_8849_4865ee12e626row0_col2" class="data row0 col2" >Samantha</td>
            </tr>
            <tr>
                        <th id="T_7ab3e36e_aea3_11ea_8849_4865ee12e626level0_row1" class="row_heading level0 row1" >1</th>
                        <td id="T_7ab3e36e_aea3_11ea_8849_4865ee12e626row1_col0" class="data row1 col0" >Panic at the Disco</td>
                        <td id="T_7ab3e36e_aea3_11ea_8849_4865ee12e626row1_col1" class="data row1 col1" >Hallelujah</td>
                        <td id="T_7ab3e36e_aea3_11ea_8849_4865ee12e626row1_col2" class="data row1 col2" >Samantha</td>
            </tr>
            <tr>
                        <th id="T_7ab3e36e_aea3_11ea_8849_4865ee12e626level0_row2" class="row_heading level0 row2" >2</th>
                        <td id="T_7ab3e36e_aea3_11ea_8849_4865ee12e626row2_col0" class="data row2 col0" >Adele</td>
                        <td id="T_7ab3e36e_aea3_11ea_8849_4865ee12e626row2_col1" class="data row2 col1" >Set Fire to the Rain</td>
                        <td id="T_7ab3e36e_aea3_11ea_8849_4865ee12e626row2_col2" class="data row2 col2" >Samantha</td>
            </tr>
    </tbody></table>


> For now, lets assume we take everyone's recommendations and add them all to our play list, even if the same song has been recommended by someone else. 


```python
df = pd.concat(playlists).reset_index(drop=True)
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>artist</th>
      <th>track</th>
      <th>Recommended By</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>Green Day</td>
      <td>Time of your Life</td>
      <td>Joe</td>
    </tr>
    <tr>
      <td>1</td>
      <td>B-52s</td>
      <td>Rock Lobster</td>
      <td>Joe</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Lady GaGa</td>
      <td>Poker Face</td>
      <td>Joe</td>
    </tr>
    <tr>
      <td>3</td>
      <td>John Lennon</td>
      <td>Imagine</td>
      <td>Joe</td>
    </tr>
    <tr>
      <td>4</td>
      <td>Eve 6</td>
      <td>Here's to the Night</td>
      <td>James</td>
    </tr>
    <tr>
      <td>5</td>
      <td>Neutral Milk Hotel</td>
      <td>Into the Aeroplane Over the Sea</td>
      <td>James</td>
    </tr>
    <tr>
      <td>6</td>
      <td>Rilo Kiley</td>
      <td>With Arms Outstretched</td>
      <td>James</td>
    </tr>
    <tr>
      <td>7</td>
      <td>Red Hot Chili Peppers</td>
      <td>Otherside</td>
      <td>James</td>
    </tr>
    <tr>
      <td>8</td>
      <td>Smashing Pumpkins</td>
      <td>Tonight, Tonight</td>
      <td>Anne</td>
    </tr>
    <tr>
      <td>9</td>
      <td>Black Eyed Peas</td>
      <td>Let's Get it Started</td>
      <td>Anne</td>
    </tr>
    <tr>
      <td>10</td>
      <td>Green Day</td>
      <td>Time of your Life</td>
      <td>Anne</td>
    </tr>
    <tr>
      <td>11</td>
      <td>Black Eyed Peas</td>
      <td>Let's Get it Started</td>
      <td>John</td>
    </tr>
    <tr>
      <td>12</td>
      <td>Lady GaGa</td>
      <td>Poker Face</td>
      <td>John</td>
    </tr>
    <tr>
      <td>13</td>
      <td>Lady GaGa</td>
      <td>Bad Romance</td>
      <td>John</td>
    </tr>
    <tr>
      <td>14</td>
      <td>Lady GaGa</td>
      <td>Just Dance</td>
      <td>John</td>
    </tr>
    <tr>
      <td>15</td>
      <td>Black Eyed Peas</td>
      <td>Let's Get it Started</td>
      <td>Samantha</td>
    </tr>
    <tr>
      <td>16</td>
      <td>Panic at the Disco</td>
      <td>Hallelujah</td>
      <td>Samantha</td>
    </tr>
    <tr>
      <td>17</td>
      <td>Adele</td>
      <td>Set Fire to the Rain</td>
      <td>Samantha</td>
    </tr>
  </tbody>
</table>
</div>




```python
## Making Sample Spaces for Tracks and artists
sTracks = set(df['track'])
sArtists = set(df['artist'])

print(f"There are {len(sTracks)} unique tracks and {len(sArtists)} unique artists.")
```

    There are 14 unique tracks and 12 unique artists.


#### Q1: What is the probability of the next song being by Lady GaGa?

(**If we just accept everyone's suggestions (full df) and play on shuffle**)

$$ P(E) = \frac{|E|}{|S|} $$



```python
num = df['artist'].value_counts()['Lady GaGa']
denom =  len(df)
num/denom
```




    0.2222222222222222




```python
df['artist'].value_counts(normalize=True)
```




    Lady GaGa                0.222222
    Black Eyed Peas          0.166667
    Green Day                0.111111
    Panic at the Disco       0.055556
    Rilo Kiley               0.055556
    Smashing Pumpkins        0.055556
    B-52s                    0.055556
    Eve 6                    0.055556
    John Lennon              0.055556
    Red Hot Chili Peppers    0.055556
    Neutral Milk Hotel       0.055556
    Adele                    0.055556
    Name: artist, dtype: float64




```python
## get counts for how many times artists appear
counts = df['artist'].value_counts()
counts
```




    Lady GaGa                4
    Black Eyed Peas          3
    Green Day                2
    Panic at the Disco       1
    Rilo Kiley               1
    Smashing Pumpkins        1
    B-52s                    1
    Eve 6                    1
    John Lennon              1
    Red Hot Chili Peppers    1
    Neutral Milk Hotel       1
    Adele                    1
    Name: artist, dtype: int64




```python
## What is the event space?
event_space = counts.loc['Lady GaGa']# / len(counts)

## What about the sample_space?
sample_space = sum(counts)
```


```python
P_lady_gaga = event_space/sample_space
P_lady_gaga
```




    0.2222222222222222



#### Q2: What is the probability of the next song being "Time of Your Life"?


```python
counts = df['track'].value_counts()
counts
```




    Let's Get it Started               3
    Poker Face                         2
    Time of your Life                  2
    Bad Romance                        1
    Rock Lobster                       1
    Imagine                            1
    Tonight, Tonight                   1
    With Arms Outstretched             1
    Just Dance                         1
    Otherside                          1
    Into the Aeroplane Over the Sea    1
    Set Fire to the Rain               1
    Here's to the Night                1
    Hallelujah                         1
    Name: track, dtype: int64




```python
## What is the cardinality of the event space?
event_space = counts.loc['Time of your Life']# / len(counts)

## What about the sample_space?
sample_space = sum(counts)
```


```python
P_time_of_your_life = event_space/sample_space
P_time_of_your_life
```




    0.1111111111111111



## Activity Pt 2: Playlist Permutations

#### Q1: How many different ways could we build a playlist using everyone's recommendations (without shuffle, no looping, and no repeated songs)?

- Q: Combination or permutation?
    -  Permutation

- Q: What formula would we use?
 $$\large P(n) = n!$$


```python
from math import factorial
factorial(len(sTracks))
```


```python
"{:,}".format(factorial(len(sTracks)))
```

#### Q2: What if we limit the playlist to only 10 songs, without replacement? How many possible playlists?

- Q: Combination or permutation?
    - Permutation

- Q: What formula would we use?
$$ \large P_{k}^{n}= \dfrac{n!}{(n-k)!}$$ 



```python
len(sTracks)
```


```python
p_10_14 = factorial(len(sTracks)) / factorial(len(sTracks)-10)
"{:,}".format(p_10_14)
```

#### Q3: what if we limit the playlist to 10 songs, WITH replacement?

- Q: Combination or permutation?
    - Permutation

- Q: What formula would we use?
$$ \large {P}_{j}^{n} = n^j $$



```python
p_10_14R = 14**10
"{:,}".format(p_10_14R)
```

#### Q4: what if we select 10 songs out of the total number of suggestions and allow for repitition?

- Q: Combination or permutation?
    - Permutation

- Q: What formula would we use?
$$\dfrac{n!}{n_1!n_2!\ldots n_j!}$$



```python
print(df['track'].value_counts().sum())
df['track'].value_counts()
```


```python
p18R = factorial(18) / (factorial(3)*factorial(2)*factorial(2))
"{:,}".format(p18R)
```

### So....  We realize we need to relax and not worry about the song-order. That's what Shuffle is for, right? 😅

#### Q5: How many playlists can we produce for an 8-track playlist from the unique suggested songs (10)?

- Q: Combination or permutation?
    - Combination

- Q: What formula would we use?
$$\large C_{k}^{n} = \displaystyle\binom{n}{k} = \dfrac{P_{k}^{n}}{k!}=\dfrac{ \dfrac{n!}{(n-k)!}}{k!} = \dfrac{n!}{(n-k)!k!}$$


```python
c_8_10 = factorial(10)/ (factorial((10-8))*factorial(8))
"{:,}".format(c_8_10)
```

# Sect 11B: Conditional Probability & Law of Total Probability


- 06/16/20 Study Group

## Learning Objectives

- We will review Independent, Dependent, vs Disjointed Events before diving deeper into conditional probability.
- We will cover conditional probability and its theorems.
- We will discuss the Law of Total Probability.



- **Activity: We will extend our dinner party activity to a house party to explore conditional probability and the Law of Total Probability**
- **Demo: Teaser for Sect 12 (if theres time)**

### QUESTIONS?
- [Questions Doc](https://docs.google.com/document/d/196yIMNSRSRspBdBmjHq7vMhFF-YdpvkyYEHYV5nm8xg/edit?usp=sharing)



##  Independent, Dependent, and Disjoint Events


### Indepdent Events

#### If 2 indepedent events:

**Events $A$ and $B$ are independent when the occurrence of $A$ has no effect on whether $B$ will occur (or not).**

- A and B are independent if:
    - $P(A \cap B) = P(A)\cdot P(B)$

 <img src="https://raw.githubusercontent.com/jirvingphd/dsc-conditional-probability-online-ds-ft-100719/master/images/Image_67_independent.png" width=400>

- Probability of A or B occurring:
    - $P (A \cup B) = P(A) + P(B) - P(A \cap B)$

 Thus, in the case of two independent events, by substitution,

$$P (A \cup B) = P(A) + P(B) - P(A)P(B).$$

#### If 3 independent events:
- A, B, and C are independent if:
    - $P(A \cap B) = P(A)P(B)$ 
    - $P(A \cap C) = P(A)P(C)$ 
    - $P(B \cap C) = P(B)P(C)$
    - $P(A \cap B \cap C) = P(A)P(B)P(C)$
    - So you need both *pairwise independence* and *three-way independence*


### Disjoint Events


<img src="https://raw.githubusercontent.com/jirvingphd/dsc-conditional-probability-online-ds-ft-100719/master/images/Image_68Disjoint.png" width=400>


**Events $A$ and $B$ are disjoint if $A$ occurring means that $B$ cannot occur.**

Disjoint events are **mutually exclusive**. $P (A \cap B)$ is **empty**.


### Dependent Events

**Events $A$ and $B$ are dependent when the occurrence of $A$ somehow has an effect on whether $B$ will occur (or not).**


In simple terms, the probability of seeing an event $B$ in the second trial depends on the outcome $A$ of the first trial. We say that $P(B)$ is **conditional** on $P(A)$.

A **tree diagram** can be used to explore all possible events.

<img src="https://raw.githubusercontent.com/jirvingphd/dsc-conditional-probability-online-ds-ft-100719/master/images/Image_71_TreeDiag.png" width = 500>


### Conditional Probability Definition

**Conditional probability emerges when the outcome a trial may influence the results of the upcoming trials.**

The conditional probability (Probability of $A$ **given** $B$) can be written as:
$$ P (A \mid B) = \dfrac{P(A \cap B)}{P(B)}$$



$P(A|B)$, is the probability A **given** that $B$ has just happened. 

### Derivation of Conditional Probability
Understanding this formula may be easier if you look at two simple Venn Diagrams and use the multiplication rule. Here's how to derive this formula:
<img src="https://raw.githubusercontent.com/jirvingphd/dsc-conditional-probability-online-ds-ft-100719/master/images/Image_72_Cond4.png" width="300">



Step 1: Write out the multiplication rule:
* $P(A \cap B)= P(B)*P(A\mid B)$

Step 2: Divide both sides of the equation by P(B):
* $\dfrac{P(A \cap B)}{ P(B)} = \dfrac{P(B)*P(A\mid B)}{P(B)}$

Step 3: Cancel P(B) on the right side of the equation:
* $\dfrac{P(A \cap B)}{P(B)} = P(A \mid B)$

Step 4: This is of course equal to:
* $ P(A \mid B)=\dfrac{P(A \cap B)}{P(B)} $

And this is our conditional probability formula. 



## 🚨Laws & Theorems Based on Conditional Probability


### Theorem 1: Product Rule

The intersection of events $A$ and $B$ can be given by

\begin{align}
    P(A \cap B) = P(B) P(A \mid B) = P(A) P(B \mid A)
\end{align}

Remember that if $A$ and $B$ are independent, then conditioning on $B$ means nothing (and vice-versa) so:
- $P(A|B) = P(A)$, and 
- $P(A \cap B) = P(A) P(B)$.


### Theorem 2: Chain Rule AKA "General Product Rule"

- Allows calculation of any member of the joint distribution of a set of random variables using _only_ conditional probabilities.

- Built on the product rule: 
$$P(A \cap B) = P(A \mid B) P(B)$$

- When applied to 3 variables, becomes:


$$P(A\cap B \cap C) = P(A\cap( B \cap C))$$
$$ = P(A\mid B \cap C) P(B \cap C)$$
$$ = P(A \mid B \cap C) P(B \mid C) P(C)$$

And you can keep extending this to $n$ variables:

$$P(A_1 \cap A_2 \cap \ldots \cap A_n) = P(A_1 \mid A_2 \cap \ldots\cap A_n) P(A_2 \mid A_3  \cap \ldots \cap \ A_n) P(A_{n-1}|A_n) P(A_n)$$

This idea is known as the **chain rule**.



### Theorem 3 - Bayes Theorem



The **Bayes theorem**, which is the outcome of this section. Below is the formula that we will dig deeper into in upcoming lessons.

$$ P(A|B) = \frac{P(B|A)P(A)}{P(B)} $$

- It uses that $P(A \cap B) = P(B) P(A \mid B) = P(A) P(B \mid A)$. 
- Note that, using Bayes theorem, you **can compute conditional probabilities without explicitly needing to know $P(A \cap B)$!** 


### Additional note: the complement of an event

You learned about (absolute and relative) complements before, but the complement of an event is also applicable to conditional probabilities.

The basic rule is:

$P(A) + P(A') = 1$

with A' being the complement of A.

Similarly, extending this to conditional probabilities:

$P(A|B) + P(A'|B) = 1$

## 🕹 Activity Pt 3: Dinner Party Playlist - Conditional Probabilities

- Loading in the Data and Adding the Recommendatins of a last minute invitee (Carla)


```python
!pip install -U fsds

from fsds.imports import *
from math import factorial
```


```python
import os,glob
datafolder = "probability_playlists/" ## student filepath
rec_files = glob.glob(datafolder+"*.csv")

playlists = {}
for file in rec_files:
    key = os.path.basename(file).replace('_recs.csv','')
    playlists[key] = pd.read_csv(file)
playlists.keys()
```


```python
### New Attendee, Carla

# Carla's Recs:
carla_recs = [['artist','track']]
carla_recs.append(['Cartman (South Park)','Poker Face'])
carla_recs.append(['Nicki Minaj','Right By My Side'])
carla_recs.append(['Kelly Clarkson',"Since You've Been Gone"])
carla_recs.append(['Nicki Minaj',"Marilyn Monroe"])
carla_recs.append(['Kelly Clarkson',"Never Again"])
carla_recs.append(['Green Day',"Minority"])



carla_recs = pd.DataFrame(carla_recs[1:],columns=carla_recs[0])
carla_recs['Recommended By'] ='Carla'
playlists['carla'] = carla_recs

```


```python
for name,playlist in playlists.items():
    display(playlist.style.set_caption(name))
```

> For now, lets assume we take everyone's recommendations and add them all to our play list, even if the same song has been recommended by someone else. 


```python
df = pd.concat(playlists).reset_index(drop=True)
df
```

### Basic Probability Revisited

#### **Q: What is the probability of hearing "Let's Get it started"?**


```python
counts = df['track'].value_counts()#sum()#sort_values('track')
counts
```

- Reminder: probability equation
$$P(E) = |E| / |S|  $$


```python
## Get Event Space
P_lets_get_it = None
P_lets_get_it
```

#### **Q: What is the probability of playing a song by Lady GaGa?**


```python
## Get Sample Space
```


```python
## Get Event Space and calc prob
P_lady_gaga = None
P_lady_gaga
```


```python
## See if you get the same result with value_counts and normalize=True

```

### Conditional Probabilities

$$ P (A \mid B) = \dfrac{P(A \cap B)}{P(B)}$$


#### Q: what is the probability of hearing a "Poker Face" given that the song is by Lady GaGa?

- **Q1: What would be the formula to calculate $P(\text{PokerFace}|\text{LadyGaga})$  ?**

A:

$$ \large P(\text{PokerFace}|\text{LadyGaga}) =\frac{P(\text{Track:"Poker Face" & Artist:"Lady Gaga"})}{ P(\text{Lady GaGa})} $$


```python
## Get Value Counts for all tracks by GaGa
track_counts = None
track_counts
```


```python
## Get Value Counts for all artists
artist_counts = None
artist_counts
```


```python
## Calculate manually
P_poker_face_lady_gaga = None
P_poker_face_lady_gaga
```


```python
## Show how groupby and value_counts gives same answer

```

# Sect 11B Cont'd: LAW OF TOTAL PROBABILITY

- This law allows us to calculate $P(B)$ from partial/conditional probabilitie of subsets ($A_n$).
- Requires that the different $A$'s that make up sample space $S$ be disjointed events.

S $A_1, A_2, \dots, A_n$ partition sample space $S$ into disjoint regions that sum up to $S$. In the example, the four regions

<img src="https://raw.githubusercontent.com/jirvingphd/dsc-law-of-total-probability-online-ds-ft-100719/master/images/Image_55_TotProb.png">

The probability of a random event $B$ (orange area) can be written down as:

\begin{align}
    P(B) &= P(B \cap A_1) + P(B \cap A_2) + P(B \cap A_3)+ P(B \cap A_4) \\
         &= P(B \mid A_1)P(A_1) + P(B \mid A_2)P(A_2) +P(B \mid A_3)P(A_3)+ P(B \mid A_4)P(A_4)
\end{align}

- using the first theorem above let us find the combined probabilities.


#### Law of Total Probability

If $B_1$,$B_2$,$B_3$,$\dots$ is a partition of the sample space S, then for any event A we have

$$P(A)= \sum_i P(A \cap B_i)= \sum_i P(A \mid B_i)P(B_i)$$

Using a Venn diagram, we can pictorially see the idea behind the law of total probability. In the figure below, we have

* $A_1 = A \cap B_1$
* $A_2 = A \cap B_2$
* $A_3 = A \cap B_3$


## 🕹 Activity: From Dinner Party Playlist to House Party Playlists

- We've decided to be a little more adventurous and turn our dinner party into a larger house party.
    - The House party spread across 4 rooms that we assume people will spread their time evenly across the various rooms:
        - living room
        - basement
        - back patio
        - kitchen
        
- We have separate play lists playing at each location that were constructed with our dinner party recommendations.


#### OUR HOUSE PARTY & LAW OF TOTAL PROB
- Our House Party is sample space S
- The 4 rooms are A1,A2,A3,A4
- B represents the probabilty of hearing a specific song or artist as you wander the house.
<img src="https://raw.githubusercontent.com/jirvingphd/dsc-law-of-total-probability-online-ds-ft-100719/master/images/Image_55_TotProb.png" width=50%>

$$P(A)= \sum_i P(A \cap B_i)= \sum_i P(A \mid B_i)P(B_i)$$





```python
## Sample playlists for our 4 rooms from our recommendations
house_party = dict(living_room = df.sample(12,random_state=12).reset_index(drop=True).copy(),
                   basement = df.sample(10,random_state=321).reset_index(drop=True).copy(), 
                   back_patio = df.sample(9,random_state=42).reset_index(drop=True).copy(),
                  kitchen=df.sample(8,random_state=3210).reset_index(drop=True).copy())
## Display room playlists
for k,v in house_party.items():
    v['Room'] = k 
    display(v.style.set_caption(f"Playlist for {k}"))

house_party.keys()
```

#### Q1: What is the probability of hearing a Green Day song at the house party at any given moment?


```python
## Let's 
house_party['living_room']
```

####  To Calculate $P(GD)$ for a Room

$$ P(\text{Green Day})=\sum_i P(\text{Green Day} \mid \text{Room}_i)P(\text{Room}_i)$$

- Q: **With our 4 rooms, what would our equation look like?** (What is the probability of being in each room?)

- A:
$$P(\text{Green Day})= P(GD|Room1)\times \frac{1}{4} + P(GD|Room2)\times \frac{1}{4} + P(GD|Room3)\times \frac{1}{4} + P(GD|Room4)\times \frac{1}{4} $$


```python
## Make a dictionary of prob of being in each room
house_party_room_odds = {'living_room':0,
                         'basement':0,
                         'back_patio':0,
                         'kitchen':0}#]
house_party_room_odds
```


```python
## Get just 1 room FIRST as test case 
liv_room_artists = None
liv_room_artists
```


```python
## Get the prob of hearing green day in this room
P_gd_given_liv_room = None
P_gd_given_liv_room
```


```python
## Calc Part of Total Prob but just for the room above
P_gd_room1 = None
P_gd_room1
```

#### Let's functionize extracting a room's probability of a specific event



```python
def get_prob_by_room(house_party, room,sample_column,outcome,display_counts=True):
    """Calculates the probability of a certain outcome from a specific room
    
    Args:
        house_party (dict): Dictionary of room playlists
        room (str): Room to extract probability for.
        sample_column (str):  Which column is the sample space?
        outcome (str): The event we are targeting from the sample_column
        display_counts(bool): Controls whether the value counts for the room are displayed.
        
    Returns:
        float: the probability of the outcome occuring in the room.
        
        """
    ## Get the value counts for the room and the target column
    res = None
    
    ## If display_counts, display res with 
    if display_counts:
        caption = None
        display(res.to_frame().style.set_caption(caption))#": {sample_column}={outcome}"))
        
    ## CALCULATE PROBABILITy
    try:
        prob=None
        
    ## Add a clause to handle if the outcome does not appear in the sample space
    except KeyError:
        pass
        
    return prob
```


```python
## Test function with living room , Green Day

```


```python
house_party.keys()
```


```python
## NOW CREATE A FOR LOOP TO CALCULATE THE TOTAL PROB OF HEARING GREEN DAY

# Specify Target column and event.
sample_column= None
event= None

## Create total_prob var and set=0 
total_prob_green_day = 0


## For each room in the house party
    
    ## Get prob of event from room's space
    
    ## Get prob of being in taht specific room
       
    ## Calculate P_GD x P_Room
    
    ## Aded the roomm prob to total prob

    ##Print a summary of the room's prob


print(f"\n\n[i] The total probability of hearing Green Day at the party is {round(total_prob_green_day,3)}")
    
```

### But wait...what if we have unequal probabilties for being in each room?



- The True prob of people being in each room is determined by what is going on in that room.
    - The snacks are in the kitchen (prob=0.4)
    - The drinks/bar is on the back patio (prob=0.3).
    - The living room and basement have no special amenities. (prob=0.15 each)


```python
## Update house_party_room_odds
house_party_room_odds['kitchen'] = 0.4
house_party_room_odds['back_patio'] = 0.3
house_party_room_odds['living_room'] =0.15
house_party_room_odds['basement'] =0.15
house_party_room_odds
```


```python
np.sum(list(house_party_room_odds.values()))
```

#### Q1: What is the probability of hearing a Lady GaGa song at the house party at any given moment with the new room probabilities?


```python
total_prob_gaga = 0
sample_column='artist'
event='Lady GaGa'

## For each room in the house party
for room in house_party:
    
    ## Get prob of event from room's space
    prob_event = get_prob_by_room(house_party,room,sample_column,event,
                                  display_counts=True)
    
    ## Get prob of being in taht specific room
    prob_room = house_party_room_odds[room]
       
    ## Calculate P_LG x P_Room
    prob_gaga_room = prob_event * prob_room
    
    ## Add the room's prob to the total prob calculation
    total_prob_gaga = total_prob_gaga + prob_gaga_room
    
    print(f"Prob {room} = {round(prob_event,2)} * {prob_room} = {round(prob_gaga_room,3)}")

total_prob_gaga
```

___

#### Q: what is the probability of hearing a song recommend by Anne?

$$ P(AnneRec)=\sum_i P(AnneRec \mid Room_i)P(Room_i)$$



```python
totel_prob_anne = 0
sample_column='Recommended By'
event='Anne'

## For each room in the house party
for room in house_party:
    
    ## Get prob of event from room's space
    prob_event = get_prob_by_room(house_party,room,sample_column,event,
                                  display_counts=True)
    
    ## Get prob of being in taht specific room
    prob_room = house_party_room_odds[room]
       
    ## Calculate P_LG x P_Room
    prob_gaga_room = prob_event * prob_room
    
    ## Add the room's prob to the total prob calculation
    totel_prob_anne = totel_prob_anne + prob_gaga_room
    
    print(f"Prob {room} = {round(prob_event,2)} * {prob_room} = {round(prob_gaga_room,3)}")

total_prob_gaga
```

# Intro to Section 12 - Statistical Distributions (if time)

- Distributions are directly related to probability, which is a critical concept we will explore more with Hypothesis Testing in Module 3.

### Probability Mass Function (AKA Probability Distribution Function)

#### Flipping a coin


```python
import  numpy as np
import matplotlib.pyplot as plt
from collections import Counter
np.random.seed(3210)
def coin_toss(n_flips=10,outcomes=None,verbose=True):
    """Flips a coin and gets heads or tails to append to outcomes list(if provided)"""
    ##
    if outcomes is None:
        outcomes = []
    
    for toss in range(n_flips):
        result = 'H' if np.random.random() >0.5 else 'T'
        outcomes.append(result)
        
        if verbose: print(f"Toss {toss}: \t{result}")
            
    return outcomes

```


```python
outcomes = coin_toss(n_flips=4)
outcomes
```


```python
counter= Counter(outcomes)
counter
```


```python
def plot_pmf_vs_hist(counter):
    """PMF vs Hist Code Inspired by Lessons/Labs"""
    
    ## If input is a list, make it a counter
    if isinstance(counter,list):
        from collections import Counter
        counter = Counter(counter)

    ## Prepare subplots
    fig,ax=plt.subplots(ncols=2,figsize=(12,4))
    
    ## Calc PMF
    pmf = [] 
    for k,v in counter.items():
        pmf.append(round(v/len(outcomes),2))

    ## Plot PMF
    ax[0].bar(counter.keys(),pmf)
    ax[0].set(title=f'PMF (sum={np.sum(pmf)})',ylabel='Frequency',xlabel='Outcomes')
    
    ## Plot Hist
    ax[1].hist(outcomes)#counter.keys(),counter.values())
    ax[1].set(title=f'Histogram (sum={np.sum(list(counter.values()))})',ylabel='Counts',xlabel='Outcomes')
    plt.tight_layout()
    return fig,ax
```


```python
plot_pmf_vs_hist(counter)
```


```python
outcomes = coin_toss(n_flips=12,outcomes=outcomes)
plot_pmf_vs_hist(outcomes)
```


```python
outcomes = coin_toss(n_flips=21,outcomes=outcomes)
plot_pmf_vs_hist(outcomes)
```


```python
outcomes = coin_toss(n_flips=20,outcomes=outcomes)
plot_pmf_vs_hist(outcomes)
```


```python
outcomes = coin_toss(n_flips=200,outcomes=outcomes)
plot_pmf_vs_hist(outcomes)
```


```python

```


```python

```
