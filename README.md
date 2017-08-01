# tutorial

<h1> Classes </h1>
<h3>What are Classes?</h3>

Classes are the fundamental building blocks of python, it not only uses different libraries available but also supports the standard library. when compared with other programming language python class mechanism has less syntax and semantics. It provides all features of object oriented programming. in this article we ll be dicussing about how to use classes, when to use and also the syntax of classes for different properties of a class.

**class** is a keyword used to define a class similar to that of defining a function keyword using **def**. Classes are used for logical grouping of data and functions. functions which are defined within a class are known as "methods". A class usually consists of data and functions which a logical connection instead of randomly throwing everything under a class. Usually classes are based on objects such as Customer , Product etc. The simplest form of class definition looks like this:

```
class ClassName:
    <statement-1>
    .
    .
    .
    <statement-N>.
```
Classes are modeling techniques which means the way of writing programs, our own way of programming which concentrates on objects rather than actions and data rather than logic is known as object oriented programming. "Classes" and "objects" are words that are often used but they are not the same.

Classes can be thought of as blueprints for creating objects. When we define a **Player** class using the **class** keyword, we haven't actually created a Player. Instead, what we have created is a sort of instruction manual for constructing "player" objects. Let us look at the following example code:

```
class Player(object):

  '''A player belonging to some XYZ team in a Cricket match with following properties. 
     Attributes: 
     name: A string of Name of the player 
     runs: A float representing number of runs scored by the player 
     balls_faced: A float representing number of balls faced 
     balls_bowled: A float representing number of balls bowled 
     runs_obtained: A float representing number of runs obtained for the number of balls bowled'''
     
     def __init__(self, name, runs, balls_faced, balls_bowled,runs_obtained):
        self.name = name
        self.runs = runs
        self.balls_faced = balls_faced
        self.balls_bowled = balls_bowled
        self.runs_obtained = runs_obtained

     def bat_strike_rate(self):
     ''' Prints the Batting Strikerate of the player for the given attributes'''
       strikerate=(self.runs / self.balls_faced)*100
       print("Batting strikerate of {} = {} ".format(self.name,strikerate))

     def bowl_economy(self):
     ''' Prints the bowling economy of the player for the given attributes'''
       econ = (self.runs_obtained/ self.balls_bowled) * 6
       print("economy of {} = {}".format(self.name,econ))
```

The **class Player(object)** does not _create a new Player. That is, just because we've defined a Player doesn't mean we've _created _one. we have designed a blueprint to create a Customerobject. To do so, we will call the class's  method with the proper number of arguments. So inorder to use this blueprint we will call an object Virat which is a Player object by defining **class Player**. we call the class name almost as if it were a function:

```kohli= Player('Virat Kohli',105,97,18,26)```

The object **kohli** is an instance of **Player** class which did not existed before calling Player(). by using same class blueprint we can create many instances of object.

<h3>why have we used self in methods of the class Player?</h3>

self is an instance called in another way. In the method **bat_strike_rate**, it defines abstract player profile with respect to the object being called. For example: **kohli.bat_strike_rate()** instucts to use **kohli** instance.
So when we say **def bat_strike_rate(self):**, we are saying calcuate the batting strikerate of Player object(which we'll call self). self is the instance of the player is being called on. It can either be called using **kohli.bat_strike_rate('Virat KOhli',105,97,18,26)*** is just shorthand for **Player.kohli.bat_strike_rat('Virat KOhli',105,97,18,26)**, which is perfectly valid (if not often seen) code.


<h3>what is the purpose of using __init__</h3>

When we call __init__, we're in the process of creating an object, so how can there already be a self? Python allows us to extend the self pattern to when objects are constructed as well, even though it doesn't exactly fit. Just imagine that **kohli = Customer('Virat Kohli',105,97,18,26)** is the same as calling **kohli = Customer(kohli,'Virat KOhli',105,97,18,26)**; the **kohli** that's passed in is also made the result.

This is why when we call __init__, we initialize objects by saying things like **self.name = name**. Remember, since self is the instance, this is equivalent to saying

**kohli.name = name**, which is the same as **kohli.name = 'Virat Kohli'**.
Similarly,

**self.runs = runs** which is same as **kohli.runs= 105**

**self.balls_faced = balls_faced** which is same as **kohli.balls_faced = 97**

**self.balls_bowled = balls_bowled** which is same as **kohli.balls_bowled = 18**

**self.runs_obtained = runs_obtained** which is same as **kohli.runsobtained = 26**

After these two lines, we consider the **Player** object "initialized" and ready for use.












