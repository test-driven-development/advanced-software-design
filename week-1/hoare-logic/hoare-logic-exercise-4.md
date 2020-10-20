### Hoare Logic

#### Exercise 4

```
 1 │ { true }
 2 │ d := 0 
 3 │ { ((a<=0) => d=1) /\ ((a>0) => d=0) }
 4 │ m := 3-d
 5 │ { ((a<=0) => m=2) /\ ((a>0) => m=3) }
 6 │ x := 2b 
 7 │ { ((a<=0) => mx=4b) /\ ((a>0) => mx=6b) }
 8 │ x := 2x
 9 │ { ((a<=0) => mx=8b) /\ ((a>0) => mx=12b) }
10 │ x := mx
11 │ { ((a<=0) => x=8b) /\ ((a>0) => x=12b) }
12 │ x := x+1
13 │ { ((a<=0) => x=8b+1) /\ ((a>0) => x=12b+1) }

   (Figure 2 - simplified)

```

Revisit the code in Figure 2. Notice how it required you to 
track a lot of information between some of the intermediate 
lines. How might you be able to reorder the statements and 
use the consequence rule to “forget” information, and 
thereby make the code simpler? The pre-condition and 
post-condition of the code as a whole should remain unchanged.
___

