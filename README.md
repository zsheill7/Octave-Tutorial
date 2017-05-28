## Guide to Common Octave Commands

<p>I learned all of this from Andrew Ng's course on Coursera - be sure to check it out if you want to learn more!</p>
<a href="https://www.coursera.org/learn/machine-learning">Machine Learning Course</a>

<p>If you have not yet downloaded Octave, use the following link:<p>
<a href = "https://sourceforge.net/projects/octave/files/Octave%20MacOSX%20Binary/2013-12-30%20binary%20installer%20of%20Octave%203.8.0%20for%20OSX%2010.9.1%20%28beta%29/GNU_Octave_3.8.0-6.dmg/download">Octave Download</a>


<h2>Basic operations</h2>
<p>Note: Do not enter the ">>".  This is just a prompt. </p>


```

>> 5+6
ans = 11
>> 3-2
ans = 1
>> 4*3
ans = 12
>> 2/3
ans = 0.66667
>> 2*5
ans = 32

```

<h2>Boolean Operations</h2>
<p>Octave can also be used to handle boolean operations.  Octave uses 0 for false and 1 for true </p>

```
>> 1 == 2
ans = 0
>> 1 == 1
ans = 1
>> 1 && 2
>> ans = 0
1 || 0 
>> ans = 1

```
<h2></h2>
<p>The default prompt is octave:1>, but you can change this default prompt with the following command: </p>

```
PS1('>> ');
```

The string in quotes will be the new default prompt.
<h2>Assigning variables</h2>

<p></p>

```
>> a = 2
a = 3
```

You can make sure the console doesn't print any output by including semicolons

```
>> a = 2;
```

<h2></h2>
<p>Then, print the variable by typing it in. </p>

```
>> a
a = 2
```

<p>Print out numbers with a certain number of decimal places with the following command:</p>

```
disp(sprintf('2 decimals: %0.2f', a))
```

<p>Change the format of decimals with the following command</p>

```
>> format short
>> format long
```

<h2>Matrices</h2>
<p>You can create matrices using the following commands.  Semicolons separate rows:</p>

```
>> A = [1 2; 3 4; 5 6] 
A = 

  1   2
  3   4
  5   6
  
>> A = [1 2;
> 3 4;
> 5 6]

A = 

  1   2
  3   4
  5   6
  
```

<h2></h2>
<p>You can also create vectors (matrices with only one column)</p>

```
v = [1; 2; 3]
v =
  1
  2
  3
  
```
  <p>The code below initializes a matrix with numbers from 1 to 2, incremented by 0.2. </p>

```
  
>> 1:0.2:2 

ans =

    1.0000    1.2000    1.4000    1.6000    1.8000    2.0000
    
 >>v = 1:6
 v =

   1   2   3   4   5   6
```

<h2></h2>
<p>You can also perform matrix operations:</p>

```
>> ones(2,3)
ans =

   1   1   1
   1   1   1

>> C = 2*ones(2,3)
C =

   2   2   2
   2   2   2


>> w = zeros(1,3)
w =

   0   0   0

```

<p>You can also use random values to generate a matrix:</p>

```

>> w = rand(1,3)
w =

   0.78627   0.52859   0.11786

>> rand(3,3)
ans =

   0.21298   0.86839   0.94668
   0.50902   0.95247   0.34806
   0.80769   0.55453   0.56063

```

<p>Identity Matrix:</p>

```
>> eye(4)
ans =

Diagonal Matrix

   1   0   0   0
   0   1   0   0
   0   0   1   0
   0   0   0   1
```
<h2>Size and Length</h2>

```
>> A
A =

   1   2
   3   4
   5   6

>> size(A)
ans =

   3   2

>> sz = size(A)
sz =

   3   2

>> size(sz)
ans =

   1   2

>> size(A,1)
ans =  3
>> size(A,2)
ans =  2
>> v = [1 2 3 4]
v =

   1   2   3   4

>> length(v)
ans =  4

```

<h2>Working with Files</h2>

```
>> pwd
ans = /Users/zoe
>> 
>> cd /Users/zoe/Documents 
>> pwd
ans = /Users/zoe/Documents
>> ls
PDXprecip.dat
>> load PDXprecip.dat
>> who
Variables in the current scope:

A          PDXprecip  ans        v
C          a          sz         w

>> size(PDXprecip)
ans =

   12    2

>> whos
Variables in the current scope:

   Attr Name           Size                     Bytes  Class
   ==== ====           ====                     =====  ===== 
        A              3x2                         48  double
        C              2x3                         48  double
        PDXprecip     12x2                        192  double
        a              1x1                          8  double
        ans            1x2                         16  double
        sz             1x2                         16  double
        v              1x4                         32  double
        w              1x10000                  80000  double

Total is 10045 elements using 80360 bytes

>> clear sz
>> v = PDXprecip(1:5)
v =

   1   2   3   4   5

>> save file.mat v;
>> clear
>> load file.mat
>> save hello.txt v -ascii

```

<h2>More Matrix Operations</h2>


```
>> A=[1 3; 4 6; 8 9]
A =

   1   3
   4   6
   8   9

>> A(3,2)
ans =  9

```

```
>> A(2,:)
ans =

   4   6

```

```
>> A(:,2)
ans =

   3
   6
   9

>> 
>> A([1 3], :)
ans =

   1   3
   8   9
```

```
>> A(:,2) = [10; 11; 12]
A =

    1   10
    4   11
    8   12

>> A = [A, [45; 46; 47]]
A =

    1   10   45
    4   11   46
    8   12   47

>> size(A)
ans =

   3   3
   
```


```

>> A(:)
ans =

    1
    4
    8
   10
   11
   12
   45
   46
   47

>> 
>> 

```

```

>> A = [1 2; 3 4; 5 6]
A =

   1   2
   3   4
   5   6

>> B = [10 11; 12 13; 14 15]
B =

   10   11
   12   13
   14   15
   
   
```

```


>> C = [A; B]
C =

    1    2
    3    4
    5    6
   10   11
   12   13
   14   15


```

```
>> C = [A B]
C =

    1    2   10   11
    3    4   12   13
    5    6   14   15

>> 

```


```

```

```

```

```

```

```



