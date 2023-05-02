Download Link: https://assignmentchef.com/product/solved-cop3502c-homework-1
<br>
For this problem, we’ll look at a fairly simplified version of Scrabble scoring. We’ll assume that a player  will  form  a  word  with  their  tiles  only  and  that  the  scoring  rules  will  be  based  on  tile positions.  For  example,  the  third  tile  might  multiply the  tile  score  by 2  and  the  fifth tile  may multiply the whole word score by 3. For the purposes of this problem, we’ll assume that only one grid square will utilize a rule of the second type.




The tile scores by letter will be given in this constant array. Please copy and paste this into your program before main:




const int VALUES[] =

{1,4,2,1,2,2,4,9,10,5,1,1,2,2,4,3,6,7,1,2,8,2,10,1,2,5};




Namely,  if  an  uppercase  letter  is  stored  in  the  variable  let,  then  VALUES[let-‘A’] represents the score of a tile with the  letter let  on it.  Recall that the Ascii values of uppercase letters are contiguous, so  if you take an uppercase  letter and subtract  ‘A’ from it,  you’ll get  an integer in between 0 and 25, inclusive. Namely, ‘A’ – ‘A’ = 0, ‘B’ – ‘A’ = 1, and so forth. The array above is arranged so that index 0 stores the score for ‘A’, index 1 stores the score for ‘B’, etc.




The problem you’ll solve will be as follows. Given the following:




<ol>

 <li>List of the letters on each of the tiles a player has</li>

 <li>The positions of the special squares and the types of those squares</li>

 <li>A full dictionary of words</li>

</ol>




you must write a program to determine the maximum score the player can achieve.




<strong><u>An Example Worked Out</u></strong>

Let the player have the following letter tiles: T, O, I, N, E, M, and A.




Let the dictionary of valid words contain these 10 words:

AMNIOTE, MEAT, DOG, EAT, PAPER, AIM, NAME, GOAT, ONE, and TABLE.

Let  the second  square position double the  score of the whole word, the  fourth square position

triple the score of the tile on it and the sixth square position double the score of the tile on it.




Of all the words in the dictionary, the paper has the necessary tiles to form the following words: ONE, AIM, EAT, AMINOTE, NAME, AND MEAT

Here is the score of each of these words:




ONE= (4 + 2 + 2)*2 = 16 (only a double word Score) AIM = (1 + 10 + 2)*2 = 26 (only a double word score) EAT = (2 + 1 + 2)*2 = 10 (only a double word score)

AMNIOTE = (1 + 2 + 2 + 3*10 + 4 + 2*2 + 2)*2 = 86 (apply triple letter on I, double letter on

T, then double the whole score at the end)

NAME = (2 + 1 + 2 + 3*2)*2 = 22 (triple the E first, then double the whole score)

MEAT= (2 + 2 + 1 + 3*2)*2 = 2 (triple the T, then double the whole score) Of these options, the highest scoring one is AMNIOTE, worth 86 points.

Design wise,  it’s good to have a  function that  takes in two  strings (one with a word, the other with the tiles) and determines if the word can be formed using the tiles.




It’s also good to have another function that takes in a word and scoring information and returns the score of the word.










<strong><u>The Input (read from standard input)</u></strong>

The first line of input will contain a single positive integer, <em>c </em>(<em>c ≤ 20)</em>, representing the number of

input cases. The first line of each input case will contain a single positive integer, <em>n </em>(<em>n </em>≤ 100), the number of words in the dictionary. The following <em>n </em>lines will each contain a single word in the dictionary. Each word will consist of upper case letters and be no more than 7 letters long. The next line of each input case will contain a string of seven uppercase letters, representing the tiles the  player  holds  for  the  input  case.  The  following  line  will  contain  seven  space-separated integers, each 1, 2 or 3, representing the letter multiplier for that square position. (Thus, normal squares will be  indicated with 1 and the special squares with 2 and 3. Note that  by giving the input in this way, no square is actually special and you can treat each square the same. The last line will contain seven space-separated integers, each 1, 2 or 3 representing that square’s word multiplier. It’s guaranteed that  at  least  6 of the 7  values are 1  and that  no  square with a  letter multiplier greater than 1 will have a word multiplier greater than 1.




<strong><u>The Output (to standard out)</u></strong>

For  each  input  case,  output  a  single  integer,  on  a  line  by  itself,  representing  the  maximum

possible score for the input case.




<strong><u>Sample Input</u></strong><strong>                                                             <u>Sample Output</u></strong>

1                                     86

10

AMNIOTE

MEAT

DOG

EAT

PAPER

AIM

NAME

GOAT

ONE

TABLE

TOINEMA

1 1 1 3 1 2 1

1 2 1 1 1 1 1










<ol>

 <li>Scoring options  should  NOT  be  hard-coded.  Your  code  should  work  even  if  the  letter multipliers aren’t all 1, 2 or 3 and if the word multiplier is something other than 2 or 3.</li>

</ol>




<ol start="2">

 <li>No use of dynamically allocated memory is needed. The dictionary can be stored in a statically allocated array of size 100 by 8. (Recall that we need 1 extra space to store the NULL character.)</li>

</ol>




<ol start="3">

 <li>Good functional design is required. Programs written all in main will NOT get full credit. For this assignment, a couple suggestions were given for possible functions, but largely, students will be free to design their own functions. If their design shows a lack of understanding of the use of functions, credit may be taken off. (An example is when a student writes two functions that do the exact same thing with different formal parameter names which match their actual parameter names exactly.)</li>

</ol>




<ol start="4">

 <li>Nearly ALL variables must be defined INSIDE the main case loop. At least 10% will be taken off for students who store the  input  for  ALL cases simultaneously.  When processing  multiple independent  cases,  it’s  generally  better  to  process  each  case  individually  and  to  reuse  these variables by simply defining them inside the case loop.</li>

</ol>




<ol start="5">

 <li>There must be good programming style. This means the following:</li>

</ol>




<ol>

 <li>a) Header Comment</li>

 <li>b) Good Use of White Space</li>

 <li>c) Meaningful Variable Names</li>

 <li>d) Reasonable Internal Comments</li>

 <li>e) Comment for each Function indicating what it takes in and what it does/returns.</li>

</ol>








