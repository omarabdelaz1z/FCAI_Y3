## Asymptotic Notations

$$
1 < log(n) < sqrt(n) < n < n*logn < n^2 < n^3 < 2^n < 3^n < n! < n^n
$$

### Upper Bound - Big O
- Notation: **F(n) = O(G(n))** 

- A function F(n) is upper-bounded by G(n) such that 
  $$
  F(n) <= c * G(n)
  $$

- Note: write the G(n) that is closest to F(n)
### Lower Bound - Big Omega
- Notation: **F(n)= Ω(G(n))**

- A function F(n) is lower-bounded by G(n) such that
  $$
  F(n) >= c * G(n)
  $$
### Average Bound - Theta
- Notation: **F(n) = Θ(G(n))**

- A function F(n) is bounded by G(n) such that it can be sandwiched between
  $$
  0 ≤ c1g(n) ≤ f(n) ≤ c2g(n)
  $$

Note: c, c1, c2 are all positive constants.

## Asymptotic Notations Properties

- Reflexivity 

  ```
  if f(n) is given then:
      f(n) = O(f(n)) 
      f(n) = Ω(f(n)) 
      f(n) = Θ(f(n))
```
  
- Symmetry

  ```
  f(n) = Θ(g(n)) if and only if g(n) = Θ(f(n))
  
  example:
      f(n) = n^2 
      g(n) = n^2
      then f(n) = Θ(n2) and g(n) = Θ(n2)
  ```

- Transitivity

  ```
  f(n) = O(g(n)) and g(n) = O(h(n)) ⇒ f(n) = O(h(n))
  example:
      f(n) = n 
      g(n) = n^2 
      h(n) = n^3
      
  	n is O(n^2) 
      n^2 is O(n^3)
  then 
      n is O(n^3)
  ```

- Transpose Symmetry

  ```
  f(n) = O(g(n)) if and only if g(n) = Ω(f(n))
  
  - If f(n) = n and g(n) = n2 then n is O(n2) and n2 is Ω(n)
  ```

## Logarithmic Rules

$$
log(a*b) = log(a) + log(b)
\\
log(a/b) = log(a)-log(b)
\\
log(a^b) = b * log(a)
\\
a^{\log _c\left(b\right)} = b^{\log _c\left(a\right)}
\\ a^b = n\\∴b = \log _a\left(n\right)
$$

## Some Arithmetic Rules

![Summation From One to N](C:\Users\omara\Documents\Typora\2e9ef5f601b25cef7278a83960a9f8f5.png)

![Series](C:\Users\omara\Documents\Typora\series.png)

## Recurrences

### Substitution Method

#### [Explanation](https://youtu.be/jz1GQ4wJcYA)

#### Steps

- Guess a solution.
  - T(n) = O(g(n))

- Use induction to prove that the solution works.
  - Simple Case.
  - Induction hypothesis. Relation is valid at k where T(k) <= c * g(k)
  - induction goal (apply the definition of the asymptotic notation)

#### Examples

### Iterative Method

- [Plug-and-chug by John Bowers](https://youtu.be/Ob8SM0fz6p0)

### Recursion Tree

- [Recurrence Tree by John Bowers](https://youtu.be/sLNPd_nPGIc)

### Master Method

- The master method applies to recurrences of the form

$$
T(n) = a * T(n/b) + f(n)
$$

​	where a >=1, b > 1 and f(n) > 0

#### Case 1

$$
∵ n^{\log _b\left(a\right)} > f(n)\\
∴ T(n) = Θ(n^{\log _b\left(a\right)}))
$$

#### Case 2

$$
∵ n^{\log _b\left(a\right)} = f(n)\\
∴ T(n) = Θ(n^{\log _b\left(a\right)}*log(n)))
$$

#### Case 3

Regularity condition must be met

Condition: a * f(n/b) <= c * f(n) for some c < 1
$$
∵ n^{\log _b\left(a\right)} < f(n)\\
∴ T(n) = Θ(f(n)\\
$$

#### Steps

1. Compute a, b, f(n), and c, where  logb(a) {log a base b}
2. Get n^(logb(a))
3. Compare (2) with f(n)
4. Determine the appropriate case

#### Examples

![image-20201209024459593](C:\Users\omara\Documents\Typora\image-20201209024459593.png)

![image-20201209031319096](C:\Users\omara\Documents\Typora\image-20201209031319096.png)
