# chapter 2 : functional thinking in action 

## summary
	1. see examples of functional thinking in action 
	2. understading why stratified design can  organize your software 3. learn how actions can be vizualized in timelilnes
	4. see how timelines help you discover and resolve problems related to timing

## welcome to toni's pizza 

### a system example
part 1 distinguishing actions from calculations and data
distinguish code that uses ingredients and other resources from code that doesn't.
part 2 using first class abstractions 
a distributed system (multiple robots) 
actions
anything that depend on when they are called or how many times they are called. it uses ingredients and other resources like the oven.
computations
represent decisions or planning. they don't affect the world when they run !
data
represents things such as accounting, inventory, and the recipes for their pizza 

### Organizing code by the rate of change
a over time the pizza software has hasd to change and grow with the business. we need to organize the code to minmizee the cost of making changes
to optimize this imagine we draw a spectrum, on the bottom we put things that changes the lesat on the top things that changes frequently.
certainly the programming language channge the least in the toni pizza example , so the built-in language constructs shouldn't change much
on the middle all things related about making pizza. 
then on the top things like what is on the menu this week.
then we can analyze this for all our business layers. 
then we have what we call business rules, domain rules and tech stack
each of this category is built on the cateagory beneath it
this architectural pattern is called stratified design

## First class abstractions

pizza making timeline
every step in a timeline is  an action 
### timelines vizualize distributed systems
