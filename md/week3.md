# Week 3: Useful Programs and Algorithms

If you are interested in your marks as we go, you can [look here](https://docs.google.com/spreadsheets/d/e/2PACX-1vRpx7SE6am9_uszUVCzGmBfKWshvtcTYZp9oilhlKht2-r2YY9wgt-MmIja_20igkoEkeowzuaNQmap/pubhtml?gid=1672893348&single=true)

<iframe src="https://docs.google.com/spreadsheets/d/e/2PACX-1vRpx7SE6am9_uszUVCzGmBfKWshvtcTYZp9oilhlKht2-r2YY9wgt-MmIja_20igkoEkeowzuaNQmap/pubhtml?gid=1672893348&amp;single=true&amp;widget=true&amp;headers=false" width="100%" height="700px" frameless></iframe>

This is updated most days, so if you don't see your values changing, it's probably because you aren't `push`ing to GitHub.

It's important to note that this chart shows **un**weighted marks. I.e. it shows a longer bar for some parts than others. The mark you actually get is weighted, so don't get caught up in who's in what order, just use it to check that you're up to date.

What I _really_ want you to do with this graph is to use it as an opportunity to help people. You might be crushing this class, but you're going to spend 3 years with these people and sooner or later, you're going to need their help! Also, more than that, the better the average competence of your cohort is, the better you'll all do when you graduate. This is a _non zero sum game!_

This is the weighted graph, but it's not really worth looking at yet.

<iframe src="https://docs.google.com/spreadsheets/d/e/2PACX-1vRpx7SE6am9_uszUVCzGmBfKWshvtcTYZp9oilhlKht2-r2YY9wgt-MmIja_20igkoEkeowzuaNQmap/pubchart?oid=17662914&amp;format=interactive" width="100%" height="400px" frameless></iframe>

## Lecture

<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vSox_vZU2xprGNVi-fi_3cwwkLvAo6qfuYhITdgSawNbQNI5ckW2G-CThN4Ew6XAmSnojYBMpAIr-Qz/embed?start=false&loop=false&delayms=3000" frameborder="0" width="100%" height="569" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>

</iframe>

## Homework

Do these things in order, it'll be better that way, I promise.

1. Do the Khan Academy Algorithms Course: **Cormen, T. & Balkcom, D.**, [_Algorithms._](https://www.khanacademy.org/computing/computer-science/algorithms)

   Go through the Intro to algorithms, Binary search and Asymptotic notation sections, these guys have made it really simple to understand and it'll reinforce everything we've said in the lecture.

1. Complete the exercises in the week 3 folder.

   It looks like there's nothing to do to exercise 2, but actually that's a big deal! You need to work out a way to make a diagram of the code. It needs to be easy to understand, and help you keep track of what it's doing. There are lots of formal ways to diagram code ([UML](https://en.wikipedia.org/wiki/Unified_Modeling_Language), flow charts) but don't let that constrain you. Think about what makes the most sense to _you_ and also about how you could use it to explain it to someone else. Make sure that your diagram goes into your lab book. It will really help you to do the same thing for exercise 3 and 4 too.

1. listen to this podcast: **Galef, J.** (2016). [_Tom Griffiths and Brian Christian on "Algorithms to Live By"_. 🎧 Rationally Speaking](http://rationallyspeakingpodcast.org/show/rs-161-tom-griffiths-and-brian-christian-on-algorithms-to-li.html).

1. Read the _code reading experience_ section below. Write some thoughts in your lab book about why some of these solutions are better than others. Performance, readability, what else makes a function better.

---

# A code reading experience!

<style>
  h3 img {
    width: 10vw;
    float: right;
  }
  .language-python {}
</style>

With that out of the way, [let's talk about](https://www.youtube.com/watch?v=ydrtF45-y-g) week 2 exercise 3 `loops_7`. You probably struggled a fair bit with this one. These are the instruction:

---

> ## Make a pyramid.
>
> Return this:

```python
[
    [' ', ' ', ' ', ' ', '*', ' ', ' ', ' ', ' '],
    [' ', ' ', ' ', '*', '*', '*', ' ', ' ', ' '],
    [' ', ' ', '*', '*', '*', '*', '*', ' ', ' '],
    [' ', '*', '*', '*', '*', '*', '*', '*', ' '],
    ['*', '*', '*', '*', '*', '*', '*', '*', '*']
]
```

> or in more simple terms:

```
        *
      * * *
    * * * * *
  * * * * * * *
* * * * * * * * *
```

> (this is what will print when you test from inside this file) This is a hard problem. Use lots of experimentation and draw lots of diagrams!

---

Below are some solutions from a previous year that passed the test. This function has a very strict test so that means that all these functions do _exactly the same thing!_

_Reading_ code is _at least_ as important as writing it, take the time to go through these examples of different ways of doing the same thing and think about which you like. Which is most readable? Which is most elegant? This is a great example of what we mean by choosing a good algorithm. There are almost always _many_ ways to do things, so you need to be able to make a call about which one to pick and why.

You should read these examples and try to make sense of them. Reading code is an aesthetic experience, you'll like some of these better than others. Some will _perform_ better than others in terms of algorithmic complexity, but usually a readable function is better than a fast one.

### Rizo007 ![](https://github.com/Rizo007/code1161base/raw/master/mugshot.png)

```python
def loops_7():
    columns = []
    for x in range(5):
        rows = []
        for y in range(9):
            if abs(y-4) <= x:
                rows.append('*')
            else:
                rows.append(' ')
        columns.append(rows)

    print(columns)
    return columns
```

### pennypangCODE ![](https://github.com/pennypangCODE/code1161base/raw/master/mugshot.png)

```python
def loops_7():
    columns = []
    for x in range(5):
        rows = []
        for y in range(9):
            if abs(y-4) <= x:
                rows.append('*')
            else:
                rows.append(' ')
        columns.append(rows)

    print (columns)
    return columns
    pass
```

### FlimEden ![](https://github.com/FlimEden/code1161base/raw/master/mugshot.png)

```python
def loops_7():

    baseLength = 9
    starting = int(baseLength / 2)  # Get middle index
    printNum = 1
    height = starting + 1
    pyramidArray = []

    for i in range(height):
        printIterator = printNum
        pyramidArray.append([])

        for j in range(baseLength):
            if j >= starting and printIterator != 0:
                pyramidArray[i].append("*")
                printIterator -= 1
            else:
                pyramidArray[i].append(" ")

        printNum += 2
        starting -= 1

    return pyramidArray
```

### sheldakristie ![](https://github.com/sheldakristie/code1161base/raw/master/mugshot.png)

```python
def loops_7():
    ihatepyramids_box = []
    for i in range(5):
        ihatepyramids_inside = []
        for j in range(4-i):
            ihatepyramids_inside.append(" ")
        for j in range(1+i):
            ihatepyramids_inside.append("*")
        for j in range(0+i):
            ihatepyramids_inside.append("*")
        for j in range(4-i):
            ihatepyramids_inside.append(" ")
        ihatepyramids_box.append(ihatepyramids_inside)
    return ihatepyramids_box
```

### RangoRay ![](https://github.com/RangoRay/code1161base/raw/master/mugshot.png)

```python
def loops_7():
    numberfield = []
    for i in range(5):
        number = []
        for j in range(9):
            if j < 5 + i and j > 3 - i:
                number.append('*')
            else:
                number.append(' ')
        numberfield.append(number)
    return numberfield
```

### lorniashi ![](https://github.com/lorniashi/code1161base/raw/master/mugshot.png)

```python
def loops_7():
    pyramid = []
    for i in range(5):
        row = '{0}{1}{0}'.format(' '*(5-i-1), '*'*(i*2+1))
        pyramid.append(list(row))

    print (pyramid)
    return pyramid
```

### atiredturtle ![](https://github.com/atiredturtle/code1161base/raw/master/mugshot.png)

```python
def loops_7():
    HEIGHT = 5
    WIDTH = 9
    arr = []
    num_blanks = 4

    for i in range(HEIGHT):
        row = []
        for i in range(WIDTH):
            if i < num_blanks:
                row.append(" ")
            elif WIDTH - i <= num_blanks:
                row.append(" ")
            else:
                row.append("*")
        num_blanks -= 1
        arr.append(row)
    return arr
```

### alanw410 ![](https://github.com/alanw410/code1161base/raw/master/mugshot.png)

```python
def loops_7():

    pyramid = [0] * 5
    sp = 4
    sp2 = 5

    def v(num):
        if(num < sp or num >= sp2):
            return True
            pass
        else:
            return False
            pass
    for x in range(0, 5):
        pyramid[x] = (map(lambda x: ' ' if(v(x)) else '*', range(0, 9)))
        sp = sp - 1
        sp2 = sp2 + 1

    return(pyramid)
    pass
```

### Matchalism ![](https://github.com/Matchalism/code1161base/raw/master/mugshot.png)

```python
def loops_7():
    pyramidList = []
    for index in range(5):
        stacklist = []
        for j in range(9):
            if (5 - index - 2 < j and j < index + 5):
                stacklist.append("*")
            else:
                stacklist.append(" ")
        pyramidList.append(stacklist)
    return pyramidList
```

### TerryAg ![](https://github.com/TerryAg/code1161base/raw/master/mugshot.png)

```python
def loops_7():
    returnedList = []
    for i in range(0, 5)[::-1]:
        temp = [' ' for _ in range(9)]
", "        temp[i:9-i] = '*'*(9-2*i)
        returnedList.append(temp)
    return returnedList
```

### sherry0303 ![](https://github.com/sherry0303/code1161base/raw/master/mugshot.png)

```python
def loops_7():
    star_pyramid = []
    for i in range(5):
        row = list("*"*9)
        left_bound = int((9-1)/2 - i)
        right_bound = int((9+1)/2 + i)
        for j in range(0, left_bound):
            row[j] = " "
        for j in range(right_bound, 9):
            row[j] = " "
        star_pyramid.append(row)

    print(star_pyramid)
    return star_pyramid
```

### AkisukeY ![](https://github.com/AkisukeY/code1161base/raw/master/mugshot.png)

```python
def loops_7():
    pyramid = []
    blank = 4
    dot = 1
    for i in range(5):
        plane = []
        for j in range(blank):
            plane.append(" ")
        for j in range(dot):
            plane.append("*")
        for j in range(blank):
            plane.append(" ")
        blank -= 1
        dot += 2
        pyramid.append(plane)
    return pyramid
```

### 872815554 ![](https://github.com/872815554/code1161base/raw/master/mugshot.png)

```python
def loops_7():

    baseLength = 9
    starting = int(baseLength / 2)  ### Get middle index
    printNum = 1
    height = starting + 1
    pyramidArray = []

    for i in range(height):
        printIterator = printNum
        pyramidArray.append([])

        for j in range(baseLength):
            if j >= starting and printIterator != 0:
                pyramidArray[i].append("*")
                printIterator -= 1
            else:
                pyramidArray[i].append(" ")

        printNum += 2
        starting -= 1

    return pyramidArray
```

### dbisazza ![](https://github.com/dbisazza/code1161base/raw/master/mugshot.png)

```python
def loops_7():

    def isPointOnPyramid(i, j):
        if j == 4:
            row.append('*')
        if (j > 4 - (i+1)) & (j < 4 + (i)):
            row.append('*')
        else:
            row.append(' ')

    column = []

    for i in range(5):
        row = []
        for j in range(8):
            isPointOnPyramid(i, j)
        column.append(row)

    print(column)
    return column
    pass
```

### timtamtinyman999 ![](https://github.com/timtamtinyman999/code1161base/raw/master/mugshot.png)

```python
def loops_7():
    columns = []
    for x in range(5):
        rows = []
        for y in range(9):
            if abs(y-4) <= x:
                rows.append("*")
            else:
                rows.append(' ')
        columns.append(rows)

    return columns
```

### DarkPurple141 ![](https://github.com/DarkPurple141/code1161base/raw/master/mugshot.png)

```python
def loops_7():
    temp = []
    for i in range(5):
        new = [' ']*9
        for j, _ in enumerate(new):
            if j >= 4-i and j <= 4+i:
                new[j] = '*'

        temp.append(new)
    return temp
```

### zingjanet ![](https://github.com/zingjanet/code1161base/raw/master/mugshot.png)

```python
def loops_7():
    the_pyramid = []
    spine = ['*']
    for i in range(5):
        space = []
        tile = []
        for j in range(4-i):
            space.append(" ")
        for k in range(i):
            tile.append("*")
        the_pyramid.append(space + tile + spine + tile + space)

    return the_pyramid
```

### tomwyb ![](https://github.com/tomwyb/code1161base/raw/master/mugshot.png)

```python
def loops_7():

    pyr = []

    for i in range(5):
        row = []
        for x in range(9):
            if x < (4 - i) or x > (4 + i):
                row.append(" ")
            else:
                row.append("*")
        pyr.append(row)

    return pyr
```

### matthewpoytress ![](https://github.com/matthewpoytress/code1161base/raw/master/mugshot.png)

```python
def loops_7():
    pyramid = []
    for i in range(5):
        row = '{0}{1}{0}'.format(' '*(5-i-1), '*'*(i*2+1))
        pyramid.append(list(row))

    print (pyramid)
    return pyramid
```

### BaptisteHiggs ![](https://github.com/BaptisteHiggs/code1161base/raw/master/mugshot.png)

```python
def loops_7():
    pyramidList = []
    height = 5
    for y in range(height):
        tempLine = []
        for x in range(height*2-1):
            if x >= height - 1 - y and x <= height + y - 1:
                tempLine.append('*')
            else:
                tempLine.append(' ')
        pyramidList.append(tempLine)
    return pyramidList
```

### DanielHeh ![](https://github.com/DanielHeh/code1161base/raw/master/mugshot.png)

```python
def loops_7():
    pyr = []
    blank = 4
    dot = 1
    for i in range(5):
        plane = []
        for ii in range(blank):
            plane.append(" ")
        for ii in range(dot):
            plane.append("*")
        for ii in range(blank):
            plane.append(" ")
        blank -= 1
        dot += 2
        pyr.append(plane)
    return pyr
```

### OneMoreN ![](https://github.com/OneMoreN/code1161base/raw/master/mugshot.png)

```python
def loops_7():
    pyramidList = []
    for index in range(5):
        stackList = []
        for x in range(9):
            if (5 - index - 2 < x and x < index + 5):
                stackList.append("*")
            else:
                stackList.append(" ")
        pyramidList.append(stackList)
    return pyramidList
    pass
```
