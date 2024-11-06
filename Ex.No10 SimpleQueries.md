# Ex.No: 10  Logic Programming –  Simple queries from facts and rules
### DATE: 23/09/24                                                                        
### REGISTER NUMBER : 212222040103
### NAME: MOHAMMED MUZAMMIL A
### AIM: 
To write a prolog program to find the answer of query. 
###  Algorithm:
 Step 1: Start the program <br> 
 Step 2: Convert the sentence into First order Logic  <br> 
 Step 3:  Convert the sentence into Horn clause form  <br> 
 Step 4: Add rules and predicates in a program   <br> 
 Step 5:  Pass the query to program. <br> 
 Step 6: Prolog interpreter shows the output and return answer. <br> 
 Step 8:  Stop the program.
### Program:
### Task 1:
Construct the FOL representation for the following sentences <br> 
1.	John likes all kinds of food.  <br> 
2.	Apples are food.  <br> 
3.	Chicken is a food.  <br> 
4.	Sue eats everything Bill eats. <br> 
5.	 Bill eats peanuts  <br> 
   Convert into clause form and Prove that John like Apple by using Prolog. <br> 
### Program:
```
% John likes all food
likes(john, X) :- food(X).

% Apples and chicken are food
food(apple).
food(chicken).

% Sue eats everything Bill eats
eats(sue, X) :- eats(bill, X).

% Bill eats peanuts
eats(bill, peanuts).
```
### Query 
?- likes(john, apple).

### Output:

<img src = "https://github.com/user-attachments/assets/231b44e3-3a1c-4806-8bfa-4e1b225d7680" width="600">

### Task 2:
Consider the following facts and represent them in predicate form: <br>              
1.	Steve likes easy courses. <br> 
2.	Science courses are hard. <br> 
3. All the courses in Have fun department are easy <br> 
4. BK301 is Have fun department course.<br> 
Convert the facts in predicate form to clauses and then prove by resolution: “Steve likes BK301 course”<br> 

### Program:

```
% Steve likes easy courses
likes(steve, X) :- course(X), easy(X).

% Science courses are hard
hard(X) :- science_course(X).

% All courses in the Have Fun department are easy
easy(X) :- course(X), department_have_fun(X).

% BK301 is a Have Fun department course
course(bk301).
department_have_fun(bk301).
```
### Query 
?- likes(steve, bk301).

### Output:

<img src = "https://github.com/user-attachments/assets/6a8f07dd-4184-4634-b128-119c42e9a194" width="600">

### Task 3:
Consider the statement <br> 
“This is a crime for an American to sell weapons to hostile nations. The Nano , enemy of America has some missiles and its missiles were sold it by Colonal West who is an American” <br> 
Convert to Clause form and prove west is criminal by using Prolog.<br> 
### Program:

```
% It's a crime for an American to sell weapons to hostile nations
criminal(X) :- american(X), weapon(Y), sells(X, Y, Z), hostile(Z).

% Nano has missiles
owns(nano, missile).

% Enemies of America are hostile
hostile(X) :- enemy(X, america).

% Colonel West, an American, sold missiles to Nano
sells(colonel_west, missile, nano).

% Colonel West is an American
american(colonel_west).

% Nano is an enemy of America
enemy(nano, america).

% Missiles are weapons
weapon(missile).
```
### Query 
?- criminal(colonel_west).

### Output:

<img src = "https://github.com/user-attachments/assets/b662529b-9c7a-4d5a-8505-d3016527605a" width="600">

### Result:
Thus the prolog programs were executed successfully and the answer of query was found.
