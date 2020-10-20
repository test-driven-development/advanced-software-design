### Hoare Logic

#### Exercise 3

```
 1 │ { true }
 2 │ d := (2−(a+1)/a)/2
 3 │ {       }
 4 │ m := d * 2 + (1−d) * 3
 5 │ {       }
 6 │ x := b * 2
 7 │ {       }
 8 │ x := x * 2
 9 │ {       }
10 │ x := m * x
11 │ {       }
12 │ x := x + 1
13 │ { ((a<=0) => x=8*b+1) /\ ((a>0) => x=12*b+1) }

   (Figure 2)

```

In this exercise, assume all variables are integers, all division is integer division (rounds toward 0), and that x/0 == 0 for all x.

(a) Look at the code in Figure 2. Fill in the assertions between each line. We have done the last and first ones for you.

Let's simplify the code algebraically*:

```    
 1 │ { true }
 2 │ d := 0 
 3 │ {       }
 4 │ m := 3-d
 5 │ {       }
 6 │ x := 2b 
 7 │ {       }
 8 │ x := 2x
 9 │ {       }
10 │ x := mx
11 │ {       }
12 │ x := x + 1
13 │ { ((a<=0) => x=8b+1) /\ ((a>0) => x=12b+1) }

```
 Working backwards, and simplifying along the way, we obtain:
```
 1 │ { true }
 2 │ d := 0 
 3 │ { ((a<=0) => 3-d=2 ⟺ d=1) /\ ((a>0) => 3-d=3 ⟺ d=0) }
 4 │ m := 3-d
 5 │ { ((a<=0) => m2b=4b ⟺ m=2) /\ ((a>0) => m2b=6b ⟺ m=3) }
 6 │ x := 2b 
 7 │ { ((a<=0) => m2x=8b ⟺ mx=4b) /\ ((a>0) => m2x=12b ⟺ mx=6b) }
 8 │ x := 2x
 9 │ { ((a<=0) => mx=8b) /\ ((a>0) => mx=12b) }
10 │ x := mx
11 │ { ((a<=0) => x+1=8b+1 ⟺ x=8b) /\ ((a>0) => x+1=12b+1 ⟺ x=12b) }
12 │ x := x+1
13 │ { ((a<=0) => x=8b+1) /\ ((a>0) => x=12b+1) }
```
---

(b) In what sense does this code contain a conditional?
___

The first 3 lines simplify as follows:

```
 1 │ { true }
 2 │ d := 0 
 3 │ { ((a<=0) => d=1) /\ ((a>0) => d=0) }
```          

On line 3, let P be the first term of the conjunction, let Q be the second, and note that d=0.

When a<=0, then P is false.   

However, when a>0, Q is true.

We see that lines 2 and 3 act as a conditional that determines which of P or Q is true, i.e., which branch of code will execute.

---

___


```

'*'
 2 │ d := (2−(a+1)/a)/2 
        = (2-(1+1/a)/2 
        = (1+1/a)/2 
        = 1/2 + 1/2a
        = 1/2a (integer division)
        = 0    (integer division)
 4 │ m := d * 2 + (1−d) * 3
        = 2d + 3(1-d)
        = 2d + 3-3d
        = 3-d
```
