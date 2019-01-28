# Object-Oriented Programming (OOP)
##### &copy; Jaclyn Zetta Cohen 2018.

----------
# Agenda
- Introduce some motivations for Object-Oriented Programming (OOP) - ~*10 minutes*
- Examine and understand code for defining objects in Python (as a first example) - ~*15 minutes*
- Unpack some useful analogies for OOP & review fundamental ideas behind OOP  - ~*20 minutes*
- Review our goals for object-oriented programming - ~*5 minutes*
- Examine implementation of an object in a program - *~20 minutes*
- Wrap-up and preview of our next goals - *~10 minutes*


# OK: What would you do if you wanted to write a program about real estate?
> Real estate means about housing / apartments, buying/selling/renting, etc.


## Let’s say these are our program expectations
- Your program should be able to show lists of different kinds of available housing in this city.
- Your program should be able to show average prices among different kinds of housing in the city.
- Your program should be able to compare pricing, size, quality, roof materials, number of bathrooms, number of bedrooms (and maybe even more factors) between different areas in the city.
- Your program should be able to calculate the ratio of the number of bedrooms to the total square feet of each living space.
- You should be able to add to this program easily — it’s a big real estate endeavor you’re working on!


## And here’s our plan
- Use a Python dictionary to represent each house.
- Define functions that get a bunch of information — e.g. a function that accepts a list of dictionaries as input, and determines the average price of houses…


## What’s the **problem** with this plan?

It’s really complicated!


- **You have to make sure each dictionary that “represents” a house or apartment has the same keys!**
  - And you have to remember or keep note of what all those keys are in order to write your code.
  - Despite this, it’s still possible to make a mistake such that dictionaries will differ in a non-systematic way.

- **You have to make sure the functions are available and that you’re invoking them on the right things…**


- **If you change something about how dictionaries ought to be structured, you have to either:**
  - Ensure you have a script that does that for you and test it out
  - Re-write your program so that the dictionaries are *each* structured in a new way.


> It sure would be nice to have a type **House** *in Python or a type* **Apartment** *in Python that you could use in a program structure — just like you have* **Strings** *and* **Lists** *and* **Dictionaries** for use inside programs you’ve written before.


# Code that defines objects (AKA “classes”) in Python

You should take a look at this code together and think about what is familiar about it, and what is *not* familiar about it.


- What parts of these code snippets look like things you’ve seen before in programs?


- What parts of these code snippets *don’t* look like things you’ve seen before?


- What parts of these code do you find confusing or tricky to understand?


- What do you think some of these code snippets do? What do they remind you of?

    ```python
    class Rabbit:
        def __init__(self, name, color):
            self.name = name
            self.color = color

        def hop(self):
            print("The rabbit named {} just hopped!".format(self.name))
    ```

    ```python
    class Skeleton:
        def __init__(self):
            self.adult = True
            self.number_bones = 206

        def remove_bone(self):
            self.number_bones = self.number_bones - 1
    ```

    ```python
    new_skeleton = Skeleton()
    rabbit_friend = Rabbit("Fluffy","brown")
    another_rabbit = Rabbit("Bugs Bunny", "gray")
    rabbit_friend.hop()
    another_rabbit.hop()
    print(new_skeleton.remove_bone())
    print(new_skeleton.adult)
    print(another_rabbit.name)
    print(another_rabbit.name)
    ```


> Key points to highlight:
  > Methods are functions — specific to an object definition

  > The double underscores in the constructor — what do they mean? Something special?

  > There are `__init__` methods in both class definitions

  > Class definitions start with the word `class` and then a capitalized name (convention)

  > What is the `self` doing? Why is it everywhere in the class definitions?

  > The code that instantiates instances and uses methods looks like running functions/methods we’ve seen before, as well as

  >> Methods are functions and must run with () , inst var vals are values and aren’t callable

  >> Some methods take inputs and others don’t

  >> Why isn’t there any `self` in code that seems to use the class definitions

  >> What is the function `Skeleton()`? What about `Rabbit( ... )`?

  >> Why does `Rabbit` the (constructor / that function thing) have input while Skeleton doesn't?

  >> We've always been able to figure out what type a variable is being assigned in previous programs when we look at the program / assignment stmt — what type is `another_rabbit`? `rabbit_friend`? `new_skeleton`?

> These questions over all aren’t all necessary but may be good key points for accompanying documents for instructors, for example.


# Unpacking some useful analogies for OOP
- An outline
- A concept
- A factory



![Copyright Steve Oney and Jackie Cohen 2016-2018](https://d2mxuefqeaa7sj.cloudfront.net/s_6196E07E896708A829F708902EE7A4A1A1ABE99366879094864EBBEFC6BADBDB_1488321326957_file.png)



# A few fundamental points about Object-Oriented Programming


----------
## Summary
- OOP is a *pattern* to understand, applicable to many languages
- For many languages, OOP is a way to build upon *data types* in a language within one program
- You can create many different *instances* of one type (and you’ve already seen this idea before)
- Different objects can *do* different things
- And the key: YOU, the programmer, can decide what a new object can do and why it is useful
----------
## >> “OOP” is a pattern to understand
- Useful in many languages
- We’ll use Python for our examples, since that’s the language you have been working with so far.
  - In which, as you know, every noun you can discuss or print out a representation of…
  - …is an object!
- Each of those definitions of *classes* that you see in each code snippet above is *one object* definition.
- “OOP” means that a program structure is focused on the **objects** available in the program — like the *nouns* — and what they can each do and what can be done with them.



> There are alternatives to OOP — one example is focusing not on **objects**, but on actions — on building functions that can work on simple objects or on writing code that uses control structures like loops and conditionals to move through a set of actions and complete computations.


> Let’s also note some similarities and differences between object definitions and function definitions, which you’ve seen and used before!



## >> OOP is a way to build upon the data types in a language

When you define a class, you’re defining a *new type* for *the program* *universe* in which you are working. e.g.

  - A type `House`
  - A type `Rabbit`
  - A type `Skeleton`
  - A type `BoringThing`


> Some detail on what you might use each of these for.


## >> You can create many instances of one type (AKA one type of object)
- Each instance has the same attributes, but MAY have different values of data

**For example…**

**What does every house have?**

*Discuss and come up with an instructor-reviewed list together, likely in a pair-and-share format.*


**What might be different among several different houses?**

*Discuss and come up with an instructor-reviewed list together, likely in a pair-and-share format.*



## >> Different objects can *do* different things
- Different methods can be invoked upon different types
  - **You already know this!** e.g. `String` methods vs `List` methods vs `Dictionary` methods

- Similarly, each `House` instance (you can think of it as “one house”) in a program may be able to print out its ratio of **# of windows / total sq feet**, but …


  - a `Rabbit` instance (you can think of it as “one Rabbit”) in your program definitely can’t print out *its own* *ratio of # windows/square feet* — that doesn’t even make sense for rabbits

  - Just like it doesn’t make sense to do something to get a string’s keys with `.keys()` — dictionaries have keys, but strings don’t have any!



## >> The real key point: YOU (the programmer) can decide
- What attributes (AKA “instance variables”) any instance of one class can have
  - Define those possibilities *in the object definition*
- What any instance of one class can do
  - What methods *are defined in the class*
  - Let’s check them out in the code you saw above — just functions!
    - Defined in a particular place — *inside* an object definition:

    ```python
    class Rabbit:
        def __init__(self, name, color):
            self.name = name
            self.color = color

        def hop(self):
            print("The rabbit named {} just hopped!".format(self.name))
    ```

    ```python
    class Skeleton:
        def __init__(self):
            self.adult = True
            self.number_bones = 206

        def remove_bone(self):
            self.number_bones = self.number_bones - 1
    ```


# So why should you use object definitions & OOP?


- We know that objects can make complex programs, like our real estate idea, a little easier to manage.
- But mostly, you know that because we told you.
- What does “easier” even mean?
  - Less complex to build on
  - Easier for other programmers to use your code once you’ve written it
  - Easier for future-you to understand and use your own code
  - Ability to modify code in only *one* place and have the effect perpetuate (as opposed to going through a lot of code carefully and doing the same thing in multiple places/for multiple dictionaries — **D** on't **R** epeat **Y** ourself)


> Looking at some code that relies upon programmers’ object definitions AND code that requires defining an object can make the motivation much clearer.


# Our immediate goals
- 1 - Understand what questions to ask in order to formulate a new object definition in Python
- 2 - Understand what structure to expect to plan and implement an object definition in Python
- 3 - Understand how and why to use & take advantage of code that defines objects in Python
- 4 - Be able to look at code that relies upon objects being defined and work backward to
  - (a) Implement code correctly
  - (b) Debug code that is encountering problems


## Today, based on what you’ve learned so far, we’ll look at goals (1) & (2).


  What do you need to know, and decide, in order to **define a new object**?
  What do you need to know to *implement a new type* inside a program you are writing?


# What do you need to decide to define a new object?
- **What input does the constructor of the object require?**

AKA what has to go into the factory — the class definition — to create a new instance?

- **What will one instance of your class represent?**

One song? One car? One rabbit? One skeleton?  One house? The answer to this question should help you decide what to call the class you define.

- **What information should each instance have as instance variables?**

AKA what are nouns each instance should have, whose *values* might be different, in the “program universe” you’re defining? *e.g. each car has a color, a make, and a model. Each rabbit has a name and a color. Each skeleton has a number of bones, an age at time of death, a sex, a species.*

- **What should each instance be able to** *do* **?**

AKA What instance methods should each instance have? What functions should be able to be invoked on ONE instance of this class?

- **What should the printed version of an instance look like?**

This question will help you determine how to write the very special  `__str__` “string” method that lets you *print out* the representation of an instance in an understandable way. Maybe, *Each Car printed out will show the car’s color, make, and model.* e.g. `Green Toyota Camry` or `Blue Subaru Legacy` if you are defining a class `Car`.



# How can you structure & implement a new object?
## For example,

I changed my mind about a real estate program that we talked about before. I’m going to start with something a little different, based on my `Skeleton` code from up above.

I want to write a program about different ancient skeletons that were found and are being pieced together by museums.

I don’t think the `Skeleton` I defined above is going to do the job.

Let’s define it again — asking and answering questions we need as we go.


## Answering our questions
- What input does the constructor of the object require?
- What will one instance of your class represent?
- What information should each instance have as instance variables?
- What should each instance be able to *do*?
- What should the printed version of an instance look like?


## Writing code based on those questions

```python
class HumanSkeleton:
    def __init__(
```



> This process should be live-code — if handleable — with guidance, led by what students are asking and suggesting, and what we decide about the program.
>
> It should be accompanied, in a lesson plan to give away, by a set of different explanations and suggested solutions that could accompany each explanation, and:
> - common misconceptions students may have,
> - common reasons for those misconceptions,  
> - ways of redirecting questions likely to come up that are not useful to achieve useful teaching examples,
> - suggested methods for encouraging specific questions that can lead to useful code examples


> One possible solution that will hammer home some useful concepts with some guidance — depending on students’ speed of understanding as to how much an instructor fills in and walks through, etc — is as follows. Of course, this is something that could be cleaned up as the students continue to learn, but this solution will clarify some of the key points of class definition.

```python
class HumanSkeleton:
    def __init__(self, specimen_name, age_at_ToD, num_bones_missing):
        self.specimen = specimen_name
        self.age_ToD = age_at_ToD,
        self.num_bones = 206 - num_bones_missing
        self.current_museum = None
        self.on_display = False

    def send_to_museum(self, museum_name):
        self.current_museum = museum_name

    def put_on_display(self):
        if self.current_museum is not None:
            self.on_display = True
        else:
            print("Cannot place on display if not at museum.")

    def __str__(self):
        s = "Skeleton specimen {} - {} at time of death - total of {} bones.".format(self.specimen, self.age_ToD, self.num_bones)
        return s
```


# Wrap-up: Conceptualizing objects in a program
- **Think about things (nouns)**
  - What those things *have* (not tangibly)
  - What those things *can do*
- **Think about why this is difficult!**
  - Not things you can see and touch
  - All ideas — from big generic “factory” ideas to specifics
  - You’re used to relying on *types* being something that exist in a program YOU work with, and now you’re defining your own


# Next time
## Goals (3) and (4) --
- Understand how and why to use & take advantage of code that defines objects in Python
- Gain practice looking at code that relies upon objects being defined, and work backward to
  - (a) Implement code that relies on objects correctly
  - (b) Debug code that is encountering problems
