HW4-Problem-3
=============

<p><b>
Find my secret rational number. 
I made up a rational number alpha whose numerator and denominator each have 7 digits. 
Here's two facts about that rational number: (1) it is congruent to 372806624339965 modulo 37+10^15; 
(2) its decimal expansion begins 0.13869616280169693.... What do you think my rational number is?
</b></p>

I used the following sage code to find some candidates for the rational number. <br>

sage: c = continued_fraction(0.13869616280169693) <br>
sage: c.convergents() <br>
[0, 1/7, 4/29, 5/36, 19/137, 100/721, 2019/14557, 2119/15278,
4138/29835, 6257/45113, 16652/120061, 56213/405296, 72865/525357,
129078/930653, 1105489/7970581, 1234567/8901234]

<br>
I knew it had to be either 1105489/7970581 or 1234567/8901234, because they were the only
rational numbers with 7 digits in both the numerator and the denominator.
<br>

I knew it was most likely the ultra-contrived-looking 1234567/8901234 and the following code confirmed it. Based on the
congruency that was given.

sage: (1234567/8901234)%1000000000000037==372806624339965%1000000000000037 <br>
output: True

Therefore the number is 1234567/8901234
