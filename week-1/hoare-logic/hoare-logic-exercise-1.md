### Hoare Logic

#### Exercise 1

```
1 │ { true }
2 │ x := 10                     
3 │ { x > 1 }                   
4 │ y := 42                     
5 │ { x > 1 /\ y > 1 }   
6 │ z := n, {n ε N | n > 3}                  
7 │ { z>3 /\ x>1 /\ y>1 }
```

Conceptual questions: 

(a) In the latter example, how could we change the code without 
altering the post-condition?
___

Any implementation need only satisfy the post-condition.  We 
can achieve that with a pre-condition that acts like a no-op:


```
{ z > 1 }
```

If we eliminate the remaining lines, then the post-condition 
still holds:

```
1 │ { z > 1 }
2 │  z := n, {n ε N | n > 3} (N is the set of Natural numbers)
3 │ { z > 1 }
```
___

(b) How does the “forgetting” of assertions correspond to a 
form of modularity?
___

For a given module, forgetting assertions correspond to 
different implementations of that module, each one of which 
achieves the same post-condition.  In that way, the 
implementations can change without affecting any client modules.

___
