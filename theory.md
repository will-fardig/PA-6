# Will Fardig Theory

## Question 1
FRAME 1: factorial, n=1
- Return address is factorial(2)
- Dynamic link is factorial(2)
- Static link is main

FRAME 2: factorial, n=1
- Return address is factorial(3)
- Dynamic link is factorial(3)
- Static link is main

FRAME 3: factorial, n=1
- Return address is factorial(4)
- Dynamic link is factorial(4)
- Static link is main

FRAME 4: factorial, n=1
- Return address is line 5, like the end
- Dynamic link is just main
- Static link is STILL main

When it unwinds, it just goes factorial(1) returning 1, factorial(2) returns 2\*1, factorial(3) returns 3\*2, factorial(4) returns 4\*6 or 24 on line 5.


## Question 2
func outside() {
    let x=5000000000;
    func inside() {
        return x;
    }
    func further_inside() {
        return inside();
    }
}
call outside();

I had this question in class tbh but looking it up and looking at slides, static link is the home of the freed up variables if I understand right? Otherwise there is no reason for it to be tracked. Dynamic link is essentialy where it returns to but static link is where it looks for variable values if there isn't one already i think


## Question 3
Okay uh let's see

Stack size of S

Record side of R

We shall call depth D

D * R [LEQ] S I guess. But if you want an inequality you can divide by R so the inequality is D = S/R.

Tail-recursion doesn't help cos it just does returns basedo n where it is, still growing the stack by 1 each time since it doesn't read stack size beforehand? I think.