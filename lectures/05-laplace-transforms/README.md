# HMTH113 — Ordinary Differential Equations

## The Laplace Transform

The **Laplace transform** is one of the most powerful techniques for solving ordinary differential equations, particularly **initial-value problems**.

Instead of solving a differential equation directly in the time domain, the Laplace transform converts the problem into an algebraic equation in the transform variable \(s\). After solving the algebraic equation, the **inverse Laplace transform** is used to return to the original time domain.

This makes the method particularly useful for problems involving:

* Initial conditions
* Discontinuous functions
* Step functions
* Impulsive or piecewise-defined inputs
* Electrical circuits
* Mechanical systems
* Control systems
* Convolution and integral equations

---

# 📚 Learning Objectives

By the end of this chapter, you should be able to:

* Define the Laplace transform.
* Calculate Laplace transforms of common functions.
* Apply the linearity property.
* Find inverse Laplace transforms.
* Use partial fractions to simplify rational functions.
* Apply the first and second translation theorems.
* Work with unit step functions.
* Find the Laplace transforms of derivatives.
* Use Laplace transforms to solve initial-value problems.
* Understand and apply the convolution theorem.
* Model discontinuous forcing functions using unit step functions.
* Interpret solutions in the time domain.

---

# 1. Introduction to the Laplace Transform

The Laplace transform converts a function of time \(t\) into a function of a new variable \(s\).

For a suitable function \(f(t)\), the Laplace transform is defined by

$$\boxed{\mathcal{L}\{f(t)\}=\int_0^\infty e^{-st}f(t)\,dt}$$

and is usually written as

$$\boxed{F(s)=\mathcal{L}\{f(t)\}.}$$

Thus,

$$f(t) \quad \xrightarrow{\mathcal L}\quad F(s).$$

The original function $\(f(t)\)$ is called the **time-domain function**, while $\(F(s)\)$ is its representation in the **\(s\)-domain**.

---

## Why Use the Laplace Transform?

Consider an initial-value problem such as

$$
y''+3y'+2y=f(t),
$$

with

$$
y(0)=y_0,
\qquad
y'(0)=y_1.
$$

Direct solution requires finding a complementary solution, finding a particular solution, and then applying the initial conditions.

The Laplace transform takes a different approach:

$$
\text{Differential equation}
$$

$$
\downarrow \mathcal L
$$

$$
\text{Algebraic equation in }Y(s)
$$

$$
\downarrow \mathcal L^{-1}
$$

$$
\text{Solution }y(t).
$$

One major advantage is that the **initial conditions appear automatically when derivatives are transformed**.

---

# 2. Conditions for the Laplace Transform

The Laplace transform is typically defined for functions that are:

1. **Piecewise continuous** on every finite interval $\(0\le t\le A\)$.
2. Of **exponential order**, meaning there exist constants $\(M\), \(c\)$, and $\(T\)$ such that

$$
|f(t)|\le Me^{ct}
$$

for $\(t>T\)$.

These conditions ensure that the improper integral defining the Laplace transform converges for sufficiently large \(s\).

For most functions encountered in an introductory ODE course, these conditions are satisfied.

---

# 3. Linearity Property

The Laplace transform is a linear operator.

If

$$
\mathcal L\{f(t)\}=F(s)
$$

and

$$
\mathcal L\{g(t)\}=G(s),
$$

then

$$\boxed{\mathcal L\{\alpha f(t)+\beta g(t)\}=\alpha F(s)+\beta G(s).}$$

This property allows complicated functions to be transformed term by term.

### Example

Find

$$
\mathcal L\{3t^2-4e^{2t}+5\}.
$$

Using linearity,

$$\mathcal L\{3t^2-4e^{2t}+5\}=3\mathcal L\{t^2\}-4\mathcal L\{e^{2t}\}+5\mathcal L\{1\}.$$

Using the standard transform formulas,

$$
\mathcal L\{t^2\}=\frac{2}{s^3},
$$

$$
\mathcal L\{e^{2t}\}=\frac{1}{s-2},
$$

and

$$
\mathcal L\{1\}=\frac{1}{s}.
$$

Therefore,

$$\boxed{\mathcal L\{3t^2-4e^{2t}+5\}=\frac{6}{s^3}-\frac{4}{s-2}+\frac{5}{s}.}$$

---

# 4. Laplace Transforms of Basic Functions

The following transforms form the foundation of most Laplace-transform calculations.

| Function \(f(t)\) | Laplace Transform \(F(s)\)           |
| ----------------- | ------------------------------------ |
|$ \(1\) $            | $\(\displaystyle \frac1s\)$            |
| $\(t\) $            | $\(\displaystyle \frac1{s^2}\) $       |
| $\(t^n\)$           | $\(\displaystyle \frac{n!}{s^{n+1}}\)$ |
| $\(e^{at}\)$        | $\(\displaystyle \frac1{s-a}\)$        |
| $\(\sin kt\)$       | $\(\displaystyle \frac{k}{s^2+k^2}\) $ |
| $\(\cos kt\)$       | $\(\displaystyle \frac{s}{s^2+k^2}\)$  |
| $\(\sinh kt\)$      | $\(\displaystyle \frac{k}{s^2-k^2}\)$  |
| $\(\cosh kt\)$      | $\(\displaystyle \frac{s}{s^2-k^2}\)$  |

For the power function,

$$\boxed{\mathcal L\{t^n\}=\frac{n!}{s^{n+1}},\qquad n=0,1,2,\ldots}$$

---

# 5. Worked Example: Basic Transforms

Find

$$
\mathcal L\{2\cos(3t)-5\sin(2t)\}.
$$

Using linearity,

$$\mathcal L\{2\cos(3t)-5\sin(2t)\}=2\mathcal L\{\cos(3t)\}-5\mathcal L\{\sin(2t)\}.$$

Now,

$$\mathcal L\{\cos(3t)\}=\frac{s}{s^2+9},$$

and

$$\mathcal L\{\sin(2t)\}=\frac{2}{s^2+4}.$$

Therefore,

$$\boxed{\mathcal L\{2\cos(3t)-5\sin(2t)\}=\frac{2s}{s^2+9}-\frac{10}{s^2+4}.}$$

---

# 6. The Inverse Laplace Transform

The inverse Laplace transform reverses the transformation process.

If

$$
F(s)=\mathcal L\{f(t)\},
$$

then

$$\boxed{f(t)=\mathcal L^{-1}\{F(s)\}.}$$

The main strategy is to rewrite $\(F(s)\)$ in terms of familiar transform pairs.

---

## 6.1 Example: Inverse Transform

Find

$$
\mathcal L^{-1}{\frac{5}{s^2+25}}.
$$

Recall

$$\mathcal L\{\sin kt\}=\frac{k}{s^2+k^2}.$$

Here,

$$
k=5.
$$

Therefore,

$$\boxed{\mathcal L^{-1}{\frac{5}{s^2+25}}=\sin(5t).}$$

---

# 7. Partial Fractions

Partial fraction decomposition is one of the most important algebraic tools used with inverse Laplace transforms.

Suppose

$$
F(s)=
\frac{3s+5}{(s+1)(s+2)}.
$$

Write

$$\frac{3s+5}{(s+1)(s+2)}=\frac{A}{s+1}+\frac{B}{s+2}.$$

Multiplying by $\((s+1)(s+2)\)$,

$$
3s+5=A(s+2)+B(s+1).
$$

Expanding,

$$
3s+5=(A+B)s+(2A+B).
$$

Comparing coefficients,

$$
A+B=3,
$$

$$
2A+B=5.
$$

Therefore,

$$
A=2,\qquad B=1.
$$

Thus,

$$
F(s)=
\frac2{s+1}
+
\frac1{s+2}.
$$

Taking the inverse transform,

$$\boxed{f(t)=2e^{-t}+e^{-2t}.}$$

---

# 8. First Translation Theorem

The first translation theorem, also called the **exponential shift theorem**, states that if

$$\mathcal L\{f(t)\}=F(s),$$

then

$$\boxed{\mathcal L\{e^{at}f(t)\}=F(s-a).}$$

Equivalently,

$$\boxed{\mathcal L^{-1}\{F(s-a)\}=e^{at}f(t).}$$

---

## Example

Find

$$\mathcal L^{-1}{\frac{1}{(s-3)^2+4}}.$$

Recall

$$\mathcal L\{\sin(2t)\}=\frac{2}{s^2+4}.$$

Therefore,

$$\frac{1}{s^2+4}=\frac12\frac{2}{s^2+4}.$$
Hence,

$$\mathcal L^{-1}{\frac1{s^2+4}}=\frac12\sin(2t).$$

Replacing $\(s\)$ with $\(s-3\)$ gives

$$\boxed{\mathcal L^{-1}{\frac1{(s-3)^2+4}}=\frac12e^{3t}\sin(2t).}$$

---

# 9. Unit Step Functions

The **unit step function**, also known as the Heaviside function, is defined by

$$ u(t-a)=0 \text{ for } t<a,\qquad u(t-a)=1 \text{ for } t\geq a. $$

It represents a signal, force, voltage, or other input that switches on at time $\(t=a\)$.

Graphically, the function changes from $\(0\)$ to $\(1\)$ at $\(t=a\)$.

---

## 9.1 Shifted Functions

A function such as

$$
u(t-a)f(t-a)
$$

represents the function $\(f\)$ beginning at $\(t=a\)$.

The second translation theorem states

$$\boxed{\mathcal L\{u(t-a)f(t-a)\}=e^{-as}F(s).}$$

Consequently,

$$\boxed{\mathcal L^{-1}\{e^{-as}F(s)\}=u(t-a)f(t-a).}$$

---

# 10. Example: Unit Step Function

Find the Laplace transform of

$$
f(t)=
\begin{cases}
0, & 0\le t<2,\\
t-2, & t\ge2.
\end{cases}
$$

This can be written as

$$
f(t)=u(t-2)(t-2).
$$

We know

$$\mathcal L\{t\}=\frac1{s^2}.$$

Therefore, using the second translation theorem,

$$\boxed{\mathcal L\{u(t-2)(t-2)\}=\frac{e^{-2s}}{s^2}.}$$

---

# 11. Writing Piecewise Functions Using Unit Steps

Unit step functions provide a systematic way to represent piecewise functions.

Suppose

$$f(t)=f_1(t), 0\le t<a,f_2(t),  t\geq a.$$

Then we can write

$$\boxed{f(t)=f_1(t)+u(t-a)\left[f_2(t)-f_1(t)\right].}$$

This form is especially useful when applying Laplace transforms.

---

# 12. Laplace Transforms of Derivatives

The major advantage of Laplace transforms for ODEs is their ability to transform derivatives into algebraic expressions.

Let

$$
Y(s)=\mathcal L\{y(t)\}.
$$

Then

$$
\boxed{\mathcal L\{y'(t)\}=sY(s)-y(0).}$$

For the second derivative,

$$\boxed{\mathcal L\{y''(t)\}=s^2Y(s)-sy(0)-y'(0).}$$

For the third derivative,

$$\boxed{\mathcal L\{y'''(t)\}=s^3Y(s)-s^2y(0)-sy'(0)-y''(0).}$$

In general,

$$\boxed{\mathcal L\{y^{(n)}(t)\}=s^nY(s)-s^{n-1}y(0)-s^{n-2}y'(0)-\cdots-y^{(n-1)}(0).}$$

---

# 13. Solving Initial-Value Problems Using Laplace Transforms

The standard procedure is:

### Step 1 — Take the Laplace transform

Transform every term in the differential equation.

### Step 2 — Substitute the initial conditions

Use the derivative formulas to incorporate the initial values.

### Step 3 — Solve for $\(Y(s)\)$

Rearrange the transformed equation algebraically.

### Step 4 — Simplify $\(Y(s)\)$

Use algebraic manipulation and partial fractions where necessary.

### Step 5 — Take the inverse Laplace transform

Find

$$
y(t)=\mathcal L^{-1}\{Y(s)\}.
$$

---

# 14. Worked Example: Solving an IVP

Solve

$$
y''-3y'+2y=0
$$

subject to

$$
y(0)=1,
\qquad
y'(0)=0.
$$

### Step 1: Take the Laplace transform

$$\mathcal L\{y''\}-3\mathcal L\{y'\}+2\mathcal L\{y\}=0.$$

Therefore,

$$s^2Y(s)-sy(0)-y'(0)-3[sY(s)-y(0)]+2Y(s)=0.$$

Substitute the initial conditions:

$$s^2Y-s-3sY+3+2Y=0.$$

Collect the $\(Y\)$-terms:

$$
(s^2-3s+2)Y=s-3.
$$

Hence,

$$Y(s)=\frac{s-3}{(s-1)(s-2)}.$$

### Step 2: Partial fractions

Write

$$\frac{s-3}{(s-1)(s-2)}=\frac{A}{s-1}+\frac{B}{s-2}.$$

Solving gives

$$
A=2,\qquad B=-1.
$$

Therefore,

$$Y(s)=\frac2{s-1}-\frac1{s-2}.$$

### Step 3: Take the inverse transform

$$\boxed{y(t)=2e^t-e^{2t}.}$$

This satisfies both the differential equation and the initial conditions.

---

# 15. Convolution

The **convolution** of two functions \(f\) and \(g\) is defined by

$$\boxed{(f*g)(t)=\int_0^tf(\tau)g(t-\tau)d\tau.}$$

Convolution is commutative:

$$\boxed{f*g=g*f.}$$

It is also associative and distributive under appropriate conditions.

---

# 16. Convolution Theorem

If

$$
\mathcal L\{f(t)\}=F(s)
$$

and

$$
\mathcal L\{g(t)\}=G(s),
$$

then

$$\boxed{\mathcal L\{f*g\}=F(s)G(s).}$$

Consequently,

$$\boxed{\mathcal L^{-1}\{F(s)G(s)\}=(f*g)(t).}$$

This theorem is particularly useful when a product $\(F(s)G(s)\)$ is difficult to invert using standard tables.

---

# 17. Example: Convolution

Find

$$\mathcal L^{-1}{\frac{1}{s(s^2+1)}}.
$$

Write

$$F(s)=\frac1s,\qquad G(s)=\frac1{s^2+1}.$$

We know

$$\mathcal L^{-1}{\frac1s}=1$$

and

$$\mathcal L^{-1}{\frac1{s^2+1}}=\sin t.$$

Therefore,

$$\mathcal L^{-1}{\frac1{s(s^2+1)}}=(1*\sin t)(t).$$

Using the definition of convolution,

$$(1*\sin t)(t)=\int_0^t1\cdot\sin(t-\tau)d\tau.$$

Let

$$
u=t-\tau.
$$

The integral becomes

$$
\int_0^t\sin udu=1-\cos t.$$

Thus,

$$\boxed{\mathcal L^{-1}{\frac1{s(s^2+1)}}=1-\cos t.}$$

---

# 18. Important Laplace Transform Theorems

| Theorem                 | Formula                                                            |
| ----------------------- | ------------------------------------------------------------------ |
| **Linearity**           | $\(\mathcal L\{\alpha f+\beta g\}=\alpha F+\beta G\)$                |
| **First Translation**   | $\(\mathcal L\{e^{at}f(t)\}=F(s-a)\)$                                |
| **Second Translation**  | $\(\mathcal L\{u(t-a)f(t-a)\}=e^{-as}F(s)\) $                        |
| **First Derivative**    | $\(\mathcal L\{y'\}=sY-y(0)\)$                                      |
| **Second Derivative**   | $\(\mathcal L\{y''\}=s^2Y-sy(0)-y'(0)\) $                            |
| **\(n\)-th Derivative** | $\(\mathcal L\{y^{(n)}\}=s^nY-\sum_{k=0}^{n-1}s^{n-1-k}y^{(k)}(0)\)$ |
| **Convolution**         | $\(\mathcal L\{f*g\}=FG\)$                                           |

---

# 19. Common Transform Pairs

A useful transform table for quick reference:

$$\boxed{\mathcal L\{1\}=\frac1s}$$

$$\boxed{\mathcal L\{t^n\}=\frac{n!}{s^{n+1}}}$$

$$\boxed{\mathcal L\{e^{at}\}=\frac1{s-a}}$$

$$\boxed{\mathcal L\{\sin at\}=\frac{a}{s^2+a^2}}$$

$$\boxed{\mathcal L\{\cos at\}=\frac{s}{s^2+a^2}}$$

$$\boxed{\mathcal L\{\sinh at\}=\frac{a}{s^2-a^2}}$$

$$\boxed{\mathcal L\{\cosh at\}=\frac{s}{s^2-a^2}}$$

---

# 20. Common Mistakes

### ❌ Mistake 1: Forgetting initial conditions

When transforming derivatives,

$$\mathcal L\{y'\}=sY-y(0).$$

The term $\(y(0)\)$ must not be omitted.

---

### ❌ Mistake 2: Incorrect second derivative formula

Remember:

$$\boxed{\mathcal L\{y''\}=s^2Y-sy(0)-y'(0).}$$

Both initial conditions are required.

---

### ❌ Mistake 3: Confusing $\(s-a\)$ and $\(s+a\)$

For

$$
e^{at},
$$

the transform is

$$
\frac1{s-a}.
$$

For example,

$$\mathcal L\{e^{-3t}\}=\frac1{s+3}.$$

---

### ❌ Mistake 4: Forgetting the coefficient in sine transforms

The correct formula is

$$\mathcal L\{\sin at\}=\frac{a}{s^2+a^2}.$$

Therefore,

$$\mathcal L\{\sin 5t\}=\frac5{s^2+25}.$$

---

### ❌ Mistake 5: Applying the second translation theorem incorrectly

The standard form is

$$
u(t-a)f(t-a),
$$

not simply

$$
u(t-a)f(t).
$$

Rewrite the function carefully before applying the theorem.

---

### ❌ Mistake 6: Forgetting to simplify before taking the inverse transform

Expressions such as

$$
\frac{3s+5}{(s+1)(s+2)}
$$

usually need partial fraction decomposition before the inverse transform can be applied.

---

# 21. A Practical Workflow

When solving a differential equation using Laplace transforms:

```text
             Start
               │
               ▼
      Write the IVP clearly
               │
               ▼
      Take the Laplace transform
               │
               ▼
    Transform all derivatives
               │
               ▼
     Insert initial conditions
               │
               ▼
        Solve for Y(s)
               │
               ▼
      Simplify Y(s)
               │
               ▼
    Partial fractions if needed
               │
               ▼
    Apply inverse Laplace transform
               │
               ▼
          Obtain y(t)
               │
               ▼
        Verify the solution
```

---

# 22. When Should You Use Laplace Transforms?

Laplace transforms are particularly effective when:

* Initial conditions are specified at $\(t=0\)$.
* The differential equation has constant coefficients.
* The forcing function is discontinuous.
* Unit step functions are present.
* The input changes at specified times.
* Impulsive inputs are involved.
* Direct solution methods become cumbersome.

For a simple homogeneous equation such as

$$
y''-5y'+6y=0,
$$

the characteristic equation may be faster.

For an equation involving a piecewise forcing function, the Laplace transform may be considerably more convenient.

---

# 23. Applications

The Laplace transform is widely used in applied mathematics and engineering.

### ⚙️ Mechanical Systems

For mass-spring-damper systems,

$$
mx''+cx'+kx=F(t),
$$

Laplace transforms can incorporate initial displacement and velocity while handling complicated external forces.

### ⚡ Electrical Circuits

For circuits involving resistors, inductors, and capacitors, Laplace transforms convert differential equations into algebraic equations involving impedance and circuit variables.

### 🎛️ Control Systems

Laplace transforms provide the mathematical foundation for:

* Transfer functions
* Block diagrams
* Feedback systems
* Stability analysis
* System response

### 📡 Signal Processing

The transform is useful for analysing signals that are:

* Piecewise defined
* Switched on or off
* Delayed
* Periodic
* Subject to impulses

---

# 🧠 Chapter Summary

The Laplace transform provides an alternative approach to solving differential equations by converting differentiation into algebraic operations.

The essential workflow is

$$
\boxed{
\text{ODE}
\rightarrow
\text{Laplace transform}
\rightarrow
\text{algebraic equation}
\rightarrow
Y(s)
\rightarrow
\mathcal L^{-1}
\rightarrow
y(t).
}
$$

The most important concepts are:

1. **Laplace transform**

$$\mathcal L\{f(t)\}=\int_0^\infty e^{-st}f(t)dt.$$

2. **Linearity**

$$\mathcal L\{\alpha f+\beta g\}=\alpha F+\beta G.$$

3. **Basic transform pairs** provide the foundation for calculations.

4. **Partial fractions** are frequently required when finding inverse transforms.

5. **Translation theorems** handle exponential shifts and delayed functions.

6. **Unit step functions** represent inputs that switch on or off.

7. **Derivative transforms** allow initial conditions to be incorporated directly.

8. **Convolution** converts products in the $\(s\)$-domain into convolutions in the time domain.

9. Laplace transforms are especially powerful for **initial-value problems and discontinuous forcing functions**.

---

# ✏️ Practice Problems

## Problem 1 — Basic Transform

Find

$$
\mathcal L\{4t^3-2e^{-t}+3\cos(2t)\}.
$$

---

## Problem 2 — Inverse Transform

Find

$$\mathcal L^{-1}{\frac{4}{s-2}+\frac{3}{s^2+9}}.$$

---

## Problem 3 — Partial Fractions

Find

$$\mathcal L^{-1}{\frac{2s+5}{(s+1)(s+3)}}.$$

---

## Problem 4 — Translation Theorem

Find

$$\mathcal L^{-1}{\frac{e^{-3s}}{s^2+4}}.$$

---

## Problem 5 — Unit Step Function

Express the function

$$
f(t)=
\begin{cases}
0, & 0\le t<2,\\
t-2, & t\ge2
\end{cases}
$$

using a unit step function and find its Laplace transform.

---

## Problem 6 — Initial-Value Problem

Solve

$$
y''+4y=0
$$

subject to

$$
y(0)=2,
\qquad
y'(0)=3
$$

using the Laplace transform.

---

## Problem 7 — Forced ODE

Solve

$$
y''+3y'+2y=e^{-t}
$$

subject to

$$
y(0)=0,
\qquad
y'(0)=1.
$$

---

## Problem 8 — Convolution

Use the convolution theorem to find

$$\mathcal L^{-1}{\frac{1}{s(s^2+4)}}.$$

---

## 🔗 Topics Covered

* Laplace transform
* Existence of Laplace transforms
* Linearity
* Basic transform pairs
* Inverse Laplace transforms
* Partial fractions
* First translation theorem
* Second translation theorem
* Unit step functions
* Piecewise functions
* Laplace transforms of derivatives
* Initial-value problems
* Convolution
* Convolution theorem
* Mechanical systems
* Electrical circuits
* Control systems
* Signal processing

---

**Course:** HMTH113 — Ordinary Differential Equations
**Topic:** The Laplace Transform
