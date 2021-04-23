# CFG2CNF
### Python tool able to convert a Context Free Grammar in Chomsky Normal Form
it's modified version of this project
Link : [LInk](https://github.com/adelmassimo/CFG2CNF)
## 1 Goals
The main purpose of this project is to provide a strategy for converting a Context Free Grammar in his Chomsky Normal Form
## 2 How to use
The script must be called in a form like ``python CFG2CNF.py sgninput.txt``, and it produces an ``out.txt`` file.
The Grammar G=(V, T, P, S) is read by a `.txt` file, so need a certain formattation, that follow:
```
Terminals:
a b        //small letters 
Variables:
A B C     // capital non-terminals
Productions:
S -> A S A | a B;
A -> B | S;
B -> e | b 
```
Is important to:
* Use spaces between symbols, one space, not more
* use te ';' character to separate rows in productions: don't use for the last.
Where is obvious how T, V and P are loaded (text after *Terminals/Variables/Productions:*), maybe less obviously is selected S as the first Variable from the left.
**N.B.** the ε-rule symbol is fixed and it's simplly ``e``
The output corresponding to the above example is:
```
S -> Z B | A A1 | a
A1 -> S A
Z -> a
Y -> b
B -> Y 
A -> Y  | Z B | A A1 | a
S0 -> Z B | A A1 | a
```
## 3 The Routine
The routine follows [Wikipedia](https://en.wikipedia.org/wiki/Chomsky_normal_form) formulation of this algorthm, in particular:
1. **START**: add ``S0->S`` production
2. **TERM**: replace terminal symbols with variables in production containing boht on the right
3. **BIN**: make rules binaries, in other words break in more parts rules which right side is longer than 2
4. **DEL**: eliminate ε-rules and eventually rearrange other productions
5. **UNIT**: remove all production which the right side is only a variable

## 4 improoved part

**DEL** remove eplilone production
**TERM** 
**you can mathch both result from old project and my**
1. **DEL** remove eplilone production
2. **TERM** 
3. **you can mathch both result from old project and my**
