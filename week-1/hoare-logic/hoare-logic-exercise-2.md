### Hoare Logic

#### Exercise 2

```

1 │ {          }
2 │   b := 2 − a
3 │ {          }
4 │   c := b ∗ 2 
5 │ {          }
6 │   d := c + 1
7 │ { d = 5 }

   (Figure 1)

```

Look at the code in Figure 1. Fill in all assertions. 

```
1 │ { 2-a=2 ⟺ a=0}         
2 │   b := 2−a
3 │ { 2b=4 ⟺ b=2 }
4 │   c := 2b
5 │ { c+1=5 ⟺ c=4}
6 │   d := c + 1
7 │ { d=5 }
```
---
