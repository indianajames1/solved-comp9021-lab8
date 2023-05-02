Download Link: https://assignmentchef.com/product/solved-comp9021-lab8
<br>






<h1>1           R Fibonacci codes</h1>

Recall that the Fibonacci sequence (<em>F<sub>n</sub></em>)<em><sub>n&gt;</sub></em><sub>=0 </sub>is defined by the equations: <em>F</em><sub>0 </sub>= 0, <em>F</em><sub>1 </sub>= 1 and for all <em>n &gt; </em>0, <em>F<sub>n </sub></em>= <em>F<sub>n</sub></em><sub>+1 </sub>+ <em>F<sub>n</sub></em><em>−</em><sub>2</sub>

<em>F</em><sub>0 </sub>= 0        <em>F</em><sub>1 </sub>= 1        <em>F</em><sub>2 </sub>= 1        <em>F</em><sub>3 </sub>= 2        <em>F</em><sub>4 </sub>= 3        <em>F</em><sub>5 </sub>= 5        <em>F</em><sub>6 </sub>= 8         <em>F</em><sub>7 </sub>= 13        <em>F</em><sub>8 </sub>= 21        <em>…</em>

It can be shown that every strictly positive integer <em>N </em>can be uniquely coded as a string <em>σ </em>of 0’s and 1’s ending with 1, so of the form <em>b</em><sub>2</sub><em>b</em><sub>3 </sub><em>…b<sub>k </sub></em>with <em>k ≥ </em>2 and <em>b<sub>k </sub></em>= 1, such that <em>N </em>is the sum of all <em>F<sub>i</sub></em>’s, 2 <em>≤ i ≤ k</em>, with <em>b<sub>i </sub></em>= 1. For instance, 11 = 3 + 8 = <em>F</em><sub>4 </sub>+ <em>F</em><sub>6</sub>, hence 11 is coded by 00101.

Moreover:

<ul>

 <li>there are no two successive occurrences of 1 in <em>σ</em>;</li>

 <li><em>F<sub>k </sub></em>is the largest Fibonacci number that fits in <em>N</em>, and if <em>j </em>is the largest integer in <em>{</em>2<em>,…,k−</em>1<em>} </em>such that <em>b<sub>j </sub></em>= 1 then <em>F<sub>j </sub></em>is the largest Fibonacci number that fits in <em>N − F<sub>k</sub></em>, and if <em>i </em>is the largest integer in <em>{</em>2<em>,…,j −</em>1<em>} </em>such that <em>b<sub>i </sub></em>= 1 then <em>F<sub>i </sub></em>is the largest Fibonacci number that fits in <em>N − F<sub>k </sub>− F<sub>j</sub></em>…</li>

</ul>

Also, every string of 0’s and 1’s ending in 1 and having no two successive occurrences of 1’s is a code of a strictly positive integer according to this coding scheme. For instance:

<ul>

 <li>There is only one string of 0’s and 1’s of length 1 ending in 1 and having no two successive occurrences of 1’s; it is 1, and it codes 1.</li>

 <li>There is only one string of 0’s and 1’s of length 2 ending in 1 and having no two successive occurrences of 1’s; it is 01, and it codes 2.</li>

 <li>The strings of 0’s and 1’s of length 3 ending in 1 and having no two successive occurrences of 1’s are 001 and 101 and they code 3 and 4, respectively.</li>

 <li>The strings of 0’s and 1’s of length 4 ending in 1 and having no two successive occurrences of 1’s are 0001, 1001 and 0101 and they code 5, 6 and 7, respectively.</li>

 <li>The strings of 0’s and 1’s of length 5 ending in 1 and having no two successive occurrences of 1’s are 00001, 10001, 01001, 00101 and 10101 and they code 8, 9, 10, 11 and 12, respectively. …</li>

</ul>

The <em>Fibonacci code </em>of <em>N </em>adds 1 at the end of <em>σ</em>; the resulting string then ends in two 1’s, therefore marking the end of the code, and allowing one to let one string code a finite sequence of strictly positive integers. For instance, 00101100111011 codes (11<em>,</em>3<em>,</em>4).

Write a program with two function, one that takes one argument <em>N </em>mean to to be a strictly positive integer and returns its Fibonacci code, and one that takes one argument <em>σ </em>meant to be a strict consisting 0’s and 1’s, returns 0 if <em>σ </em>cannot be a Fibonacci code, and otherwise returns the integer <em>σ </em>is the Fibonacci code of.

Here is a possible interaction:

$ python3 …

&gt;&gt;&gt; from fibonacci_codes import *

&gt;&gt;&gt; encode(1)

’11’

&gt;&gt;&gt; encode(2)

’011’

&gt;&gt;&gt; encode(3)

’0011’

&gt;&gt;&gt; encode(4)

’1011’

&gt;&gt;&gt; encode(8)

’000011’

&gt;&gt;&gt; encode(11)

’001011’

&gt;&gt;&gt; encode(12)

’101011’

&gt;&gt;&gt; encode(14)

’1000011’

&gt;&gt;&gt; decode(’1’)

0

&gt;&gt;&gt; decode(’01’)

0

&gt;&gt;&gt; decode(’100011011’)

0

&gt;&gt;&gt; decode(’11’)

1

&gt;&gt;&gt; decode(’011’)

2

&gt;&gt;&gt; decode(’0011’)

3

&gt;&gt;&gt; decode(’1011’)

4

&gt;&gt;&gt; decode(’000011’)

8

&gt;&gt;&gt; decode(’001011’)

11

&gt;&gt;&gt; decode(’1000011’)

14

<h1>2           R Linked lists</h1>

Entend the module linked_list.py which is part of the material of the 8th lecture into a module extended_linked_list.py to implement the extra method remove_duplicates(), that keeps only the first occurrence of any value. As for the 7th quiz, this should be done without creating new nodes and without using Python lists.

Here is a possible interaction.

$ python3 …

&gt;&gt;&gt; from extended_linked_list import *

&gt;&gt;&gt; LL = ExtendedLinkedList([1, 2, 3])

&gt;&gt;&gt; LL.remove_duplicates()

&gt;&gt;&gt; LL.print()

1, 2, 3

&gt;&gt;&gt; LL = ExtendedLinkedList([1, 1, 1, 2, 1, 2, 1, 2, 3, 3, 2, 1])

&gt;&gt;&gt; LL.remove_duplicates()

&gt;&gt;&gt; LL.print() 1, 2, 3

<h1>3           R Doubly linked lists</h1>

Modify the module linked_list.py which is part of the material of the 8th lecture into a module doubly_linked_list.py, to process lists consisting of nodes with a reference to both next and previous nodes, so with the class Node defined as follows.

class Node:

def __init__(self, value = None):

self.value = value self.next_node = None self.previous_node = None

<h1>4                    Using linked lists to represent polynomials (optional)</h1>

Write a program polynomial.py that implements a class Polynomial. An object of this class is built from a string that represents a polynomial, that is, a sum or difference of monomials.

<ul>

 <li>The leading monomial can be either an integer, or an integer followed by x, or an integer followed by xˆ followed by a nonnegative integer.</li>

 <li>The other monomials can be either a nonnegative integer, or a nonnegative integer followed by x, or a nonnegative integer followed by xˆ followed by a nonnegative integer.</li>

</ul>

Spaces can be inserted anywhere in the string.

A monomial is defined by the following class:

class Monomial:

def __init__(self, coefficient = 0, degree = 0):

self.coefficient = coefficient self.degree = degree self.next_monomial = None

A polynomial is a linked list of monomials, ordered from those of higher degree to those of lower degree. An implementation of the __str__() method allows one to print out a polynomial.

Here is a possible interaction.

$ python3 …

&gt;&gt;&gt; from polynomial import *

&gt;&gt;&gt; Polynomial(’-0’)

Incorrect input

&gt;&gt;&gt; Polynomial(’+0’)

Incorrect input

&gt;&gt;&gt; Polynomial(’0x^-1’)

Incorrect input

&gt;&gt;&gt; Polynomial(’2x + +2’)

Incorrect input

&gt;&gt;&gt; Polynomial(’2x + -2’)

Incorrect input

&gt;&gt;&gt; Polynomial(’2x – +2’)

Incorrect input

&gt;&gt;&gt; poly_0 = Polynomial(’0’)

&gt;&gt;&gt; print(poly_0)

0

&gt;&gt;&gt; poly_0 = Polynomial(’0x’)

&gt;&gt;&gt; print(poly_0)

0

&gt;&gt;&gt; poly_0 = Polynomial(’0x^0’)

&gt;&gt;&gt; print(poly_0)

0

&gt;&gt;&gt; poly_0 = Polynomial(’0x^5’)

&gt;&gt;&gt; print(poly_0)

0

&gt;&gt;&gt; poly_1 = Polynomial(’x’)

&gt;&gt;&gt; print(poly_1) x

&gt;&gt;&gt; poly_1 = Polynomial(’1x’)

&gt;&gt;&gt; print(poly_1) x

&gt;&gt;&gt; poly_1 = Polynomial(’1x^1’)

&gt;&gt;&gt; print(poly_1) x

&gt;&gt;&gt; poly_2 = Polynomial(’2’)

&gt;&gt;&gt; print(poly_2)

2

&gt;&gt;&gt; poly_2 = Polynomial(’2x^0’)

&gt;&gt;&gt; print(poly_2)

2

&gt;&gt;&gt; poly_3 = Polynomial(’1 + 2-3 +10’)

&gt;&gt;&gt; print(poly_3)

10

&gt;&gt;&gt; poly_4 = Polynomial(’x + x – 2x -3x^1 + 3x’)

&gt;&gt;&gt; print(poly_4)

0

&gt;&gt;&gt; poly_5 = Polynomial(’x + 2 + x – x -3x^1 + 3x + 5x^0’)

&gt;&gt;&gt; print(poly_5)

x + 7

&gt;&gt;&gt; poly_6 = Polynomial(’-2x + 7x^3 +x                                                            – 0 + 2 -x^3 + x^23 – 12x^8 + 45 x ^ 6 -x^47’)

&gt;&gt;&gt; print(poly_6)

-x^47 + x^23 – 12x^8 + 45x^6 + 6x^3 – x + 2

<h1>5                    Markov chains (optional)</h1>

Write a program markov_chain.py that prompts the user to input two positive integers <em>n </em>and <em>N</em>, and outputs <em>N </em>words generated by a Markov chain where a dictionary file, named dictionary.txt, stored in the working directory, determines the probability that an <em>n</em>-gram (that is, a sequence of <em>n </em>letters) be followed by this or that character (including the “end-of-word” character). More precisely, assume that <em>n </em>= 3. Then a word <em>c</em><sub>1 </sub><em>…c<sub>k </sub></em>is generated as follows.

<ul>

 <li><em>c</em><sub>1 </sub>is generated following the probability that, according to txt, a word starts with <em>c</em><sub>1</sub>.</li>

 <li><em>c</em><sub>2 </sub>is generated following the probability that, according to txt, a word that starts with <em>c</em><sub>1 </sub>starts with <em>c</em><sub>1</sub><em>c</em><sub>2</sub>; in case <em>c</em><sub>2 </sub>is the end of word marker then <em>k </em>= 1.</li>

 <li><em>c</em><sub>3 </sub>is generated following the probability that, according to txt, a word that starts with <em>c</em><sub>1</sub><em>c</em><sub>2 </sub>starts with <em>c</em><sub>1</sub><em>c</em><sub>2</sub><em>c</em><sub>3</sub>; in case <em>c</em><sub>3 </sub>is the end of word marker then <em>k </em>= 2.</li>

 <li><em>c</em><sub>4 </sub>is generated following the probability that, according to txt, a word that contains <em>c</em><sub>1</sub><em>c</em><sub>2</sub><em>c</em><sub>3 </sub>contains <em>c</em><sub>1</sub><em>c</em><sub>2</sub><em>c</em><sub>3</sub><em>c</em><sub>4</sub>; in case <em>c</em><sub>4 </sub>is the end of word marker then <em>k </em>= 3.</li>

 <li><em>c</em><sub>5 </sub>is generated following the probability that, according to txt, a word that contains <em>c</em><sub>2</sub><em>c</em><sub>3</sub><em>c</em><sub>4 </sub>contains <em>c</em><sub>2</sub><em>c</em><sub>3</sub><em>c</em><sub>4</sub><em>c</em><sub>5</sub>; in case <em>c</em><sub>5 </sub>is the end of word marker then <em>k </em>= 4.</li>

 <li><em>c</em><sub>6 </sub>is generated following the probability that, according to txt, a word that contains <em>c</em><sub>3</sub><em>c</em><sub>4</sub><em>c</em><sub>5 </sub>contains <em>c</em><sub>3</sub><em>c</em><sub>4</sub><em>c</em><sub>5</sub><em>c</em><sub>6</sub>; in case <em>c</em><sub>6 </sub>is the end of word marker then <em>k </em>= 5.</li>

 <li>…</li>

</ul>

The program should indicate whether the word that has been generated has been invented (because it does not occur in dictionary.txt), or whether it has been rediscovered (because it does occur in dictionary.txt). Here is a possible interaction.

$ python3 markov_chains_for_word_generation.py

What n to use to let an n-gram determine the next character? 2

How many words do you want to generate? 10

Rediscovered ADS

Invented ENTRAMER

Invented LER

Invented EQUILIZED

Invented CIATTLY

Invented GRECOND

Rediscovered ASS

Invented WINCOT

Invented PEENIAR

Rediscovered ANTS

$ python3 markov_chains_for_word_generation.py

What n to use to let an n-gram determine the next character? 3

How many words do you want to generate? 10

Invented ROYAN

Rediscovered THING

Invented AGGREEABLE

Rediscovered RECEPTION

Invented LISHED

Invented CONTERMING

Invented TUSCUSTIVE

Invented INISM

Invented SWORTHUST

Invented BENTHANGE

$ python3 markov_chains_for_word_generation.py

What n to use to let an n-gram determine the next character? 4

How many words do you want to generate? 10

Invented REFORMEDITOR

Invented DIFFICE

Invented SEMITTERING

Invented INAPPERS

Invented PROPOLDVILLED

Invented KINGBIRDIED

Rediscovered SUBSCRIBED

Invented SCHED

Invented DEGRADIC

Rediscovered MILLION

$ python3 markov_chains_for_word_generation.py

What n to use to let an n-gram determine the next character? 5

How many words do you want to generate? 10

Rediscovered APPEARS

Rediscovered LOWS

Rediscovered SPORTS

Invented CROWDERPUFF

Invented BIRTHRIGHTNESS

Invented BREAKFASTERFUL

Rediscovered DREAMY

Rediscovered JACOB

Rediscovered BRUNHILDE Invented REORGANISM