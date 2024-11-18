# Ex.No: 9  Logic Programming –  Computer Maintenance Expert System
### DATE: 07-10-2024
### NAME: MOHAMMED MUZAMMIL A
### REGISTER NUMBER : 212222040103
### AIM: 
Write a Prolog program to build a computer maintenance expert system.
###  Algorithm:
1. Start the program.
2. Write the rules for each fault in computer.
3. If system have printing problem, missing dots and no uniform printing then system fault on printer head.
4. If system have not printing, missing dots and spread inks then system fault on ribbon
5. If system have not printing, paper jam and out of paper then system fault on paper stuck in printer
6. Similarly define rules for all faults.
7. Define facts for system problems.
8. Find the fault of computer by passing query to system.
     
### Program:
```
% Defining faults based on symptoms (problems)
fault(printer_head) :-
    problem(not_printing),
    problem(missing_dots),
    problem(nonuniform_printing).

fault(ribbon) :-
    problem(not_printing),
    problem(missing_dots),
    problem(spread_ink).

fault(paper) :-
    problem(not_printing),
    problem(paper_jam),
    problem(out_of_paper).

fault(motherboard) :-
    problem(long_beep),
    problem(short_beep).

fault(hard_disc) :-
    problem(two_short_beeps),
    problem(blank_display).

% Example problems that occur in the system
problem(not_printing).
problem(missing_dots).
problem(spread_ink).
problem(two_short_beeps).
problem(blank_display).
```


### Output:

<img src = "https://github.com/user-attachments/assets/4ecfec54-b7ba-46c9-8393-681d50e9cdbb" width="600">

<img src = "https://github.com/user-attachments/assets/a4da75c8-9a7b-4013-b458-58cef6c5d0d3" width="600">


### Result:
Thus the simple omputer maintenance expert system was built sucessfully.
