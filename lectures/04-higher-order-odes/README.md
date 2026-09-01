# HMTH113 — Ordinary Differential Equations

## Chapter 4: Higher-Order Differential Equations

Higher-order differential equations are differential equations involving derivatives of order two or higher. They are fundamental in mathematical modelling because many physical, engineering, biological, and economic systems naturally involve acceleration, higher rates of change, or interactions between several derivatives.

This chapter develops systematic methods for solving **higher-order linear ordinary differential equations**, with particular emphasis on equations with constant coefficients.

---

## 📚 Learning Objectives

By the end of this chapter, you should be able to:

* Define and identify the order of a differential equation.
* Distinguish between homogeneous and non-homogeneous higher-order ODEs.
* Write higher-order linear ODEs in standard form.
* Solve homogeneous linear ODEs with constant coefficients.
* Construct and solve the **characteristic equation**.
* Handle distinct, repeated, and complex roots.
* Solve non-homogeneous equations using appropriate methods.
* Find particular solutions using **undetermined coefficients**.
* Apply the **annihilator method** where appropriate.
* Use variation of parameters to find particular solutions.
* Apply initial conditions to obtain unique solutions.
* Verify solutions by substitution.
* Model physical systems such as mechanical vibrations and electrical circuits.

---

# 1. Introduction to Higher-Order Differential Equations

A differential equation is called a **higher-order differential equation** if its highest derivative is of order two or greater.

For example,

$$y''+4y'+3y=0$$

is a second-order differential equation.

Similarly,

$$y'''-2y''+y'=0$$

is a third-order differential equation.

And

$$y^{(4)}+5y''-6y=x$$

is a fourth-order differential equation.

In general, an \(n\)-th order differential equation can be written as

$$F\left(x,y,y',y'',\ldots,y^{(n)}\right)=0.$$

---

# 2. Linear Higher-Order Differential Equations

An \(n\)-th order linear differential equation has the general form

$$
{a_n(x)y^{(n)}+a_{n-1}(x)y^{(n-1)}+\cdots+a_1(x)y'+a_0(x)y=g(x)}$$

where the coefficients $\(a_i(x)\)$ and forcing function $\(g(x)\)$ are known functions.

The equation is **linear** because:

* $\(y\)$ and its derivatives occur only to the first power.
* Products such as $\(yy'\)$ do not occur.
* Nonlinear functions such as $\(e^y\), \(\sin y\)$, or $\(y^2\)$ do not occur.

### Example: Linear

$$
y''+3xy'-2y=\cos x.$$

### Example: Nonlinear

$$y''+y^2=0.$$

The second equation is nonlinear because $\(y\)$ appears as $\(y^2\)$.

---

# 3. Homogeneous and Non-Homogeneous Equations

A linear higher-order ODE has the form

$$L[y]=g(x).$$

## 3.1 Homogeneous Equation

If

$$
g(x)=0,
$$

the equation is homogeneous:

$${L[y]=0}.$$

For example,

$$
y''-5y'+6y=0.
$$

---

## 3.2 Non-Homogeneous Equation

If

$$
g(x)\neq0,
$$

the equation is non-homogeneous:

$${L[y]=g(x)}.$$

For example,

$$
y''-5y'+6y=e^x.
$$

---

# 4. The Principle of Superposition

For a homogeneous linear differential equation, if $\(y_1\)$ and $\(y_2\)$ are solutions, then any linear combination

$$
\boxed{y=c_1y_1+c_2y_2}$$

is also a solution.

More generally, if

$$y_1,y_2,\ldots,y_n$$

are linearly independent solutions of an \(n\)-th-order homogeneous linear ODE, then the general solution is

$$\boxed{y=c_1y_1+c_2y_2+\cdots+c_ny_n.}$$

This principle is fundamental to solving higher-order linear equations.

---

# 5. Linear Independence

Solutions must be **linearly independent** in order to form a fundamental set of solutions.

Functions $\(y_1,y_2,\ldots,y_n\)$ are linearly independent on an interval if

$$c_1y_1+c_2y_2+\cdots+c_ny_n=0$$

implies

$$c_1=c_2=\cdots=c_n=0.$$

For two functions, the **Wronskian** provides a useful test:

$$
\boxed{
W(y_1,y_2)=
\begin{vmatrix}
y_1 & y_2\\
y_1' & y_2'
\end{vmatrix}
}
$$

or

$$W(y_1,y_2)=y_1y_2'-y_2y_1'.$$

If

$$W(y_1,y_2)\neq0,$$

the functions are linearly independent at that point.

---

# 6. Higher-Order Equations with Constant Coefficients

One of the most important classes of higher-order ODEs is

$$
\boxed{a_ny^{(n)}+a_{n-1}y^{(n-1)}+\cdots+a_1y'+a_0y=0}$$

where all $\(a_i\)$ are constants.

These equations can be solved systematically using a **characteristic equation**.

---

# 7. The Characteristic Equation

Consider

$$ay''+by'+cy=0.$$

Assume a solution of the form

$$\boxed{y=e^{rx}}.$$

Then

$$y'=re^{rx}$$

and

$$y''=r^2e^{rx}.$$

Substituting into the differential equation gives

$$ar^2e^{rx}+bre^{rx}+ce^{rx}=0.$$

Since $\(e^{rx}\neq0\)$,

$$ar^2+br+c=0.$$

This is the **characteristic equation**.

---

# 8. Distinct Real Roots

Suppose the characteristic equation

$$
ar^2+br+c=0
$$

has two distinct real roots

$$
r_1\neq r_2.
$$

Then the general solution is

$$\boxed{y=c_1e^{r_1x}+c_2e^{r_2x}.}$$

## Worked Example 1

Solve

$$y''-5y'+6y=0.$$

### Step 1: Assume an exponential solution

$$
y=e^{rx}.
$$

### Step 2: Form the characteristic equation

$$
r^2-5r+6=0.
$$

### Step 3: Factor

$$
(r-2)(r-3)=0.
$$

Therefore,

$$
r_1=2,\qquad r_2=3.
$$

### Step 4: Write the general solution

$$\boxed{y=c_1e^{2x}+c_2e^{3x}.}$$

---

# 9. Repeated Real Roots

Suppose the characteristic equation has a repeated root

$$
r_1=r_2=r.
$$

A single function $\(e^{rx}\)$ is not enough to produce two linearly independent solutions.

The general solution becomes

$$\boxed{y=(c_1+c_2x)e^{rx}.}$$

## Worked Example 2

Solve

$$
y''-4y'+4y=0.
$$

### Step 1: Characteristic equation

$$
r^2-4r+4=0.
$$

### Step 2: Factor

$$
(r-2)^2=0.
$$

Therefore,

$$
r=2
$$

is a repeated root.

### Step 3: Write the solution

$$\boxed{y=(c_1+c_2x)e^{2x}.}$$

---

# 10. Complex Roots

Suppose the characteristic equation has complex roots

$$r=\alpha\pm\beta i,\qquad \beta\neq0.$$

Euler's formula gives

$$e^{i\beta x}=\cos(\beta x)+i\sin(\beta x).$$

Therefore, the two real-valued solutions can be written as

$$
e^{\alpha x}\cos(\beta x)
$$

and

$$
e^{\alpha x}\sin(\beta x).
$$

The general real solution is

$$\boxed{y=e^{\alpha x}\left[c_1\cos(\beta x)+c_2\sin(\beta x)\right].}$$

## Worked Example 3

Solve

$$
y''+4y'+13y=0.
$$

### Step 1: Characteristic equation

$$
r^2+4r+13=0.
$$

### Step 2: Use the quadratic formula

$$r=\frac{-4\pm\sqrt{16-52}}{2}.$$

Thus,

$$
r=-2\pm3i.
$$

Therefore,

$$
\alpha=-2,\qquad\beta=3.
$$

### Step 3: Write the general solution

$$\boxed{y=e^{-2x}\left(c_1\cos3x+c_2\sin3x\right).}$$

---

# 11. Summary of Second-Order Characteristic Roots

For

$$
ay''+by'+cy=0,
$$

the characteristic equation is

$$
ar^2+br+c=0.
$$

The discriminant

$$
\Delta=b^2-4ac
$$

determines the type of roots.

| Discriminant | Roots                   | General Solution                                |
| ------------ | ----------------------- | ----------------------------------------------- |
| $\(\Delta>0\)$ | Two distinct real roots | $\(c_1e^{r_1x}+c_2e^{r_2x}\) $                    |
| $\(\Delta=0\)$ | Repeated real root      | $\((c_1+c_2x)e^{rx}\) $                           |
| $\(\Delta<0\)$ | Complex conjugate roots | $\(e^{\alpha x}(c_1\cos\beta x+c_2\sin\beta x)\)$ |

---

# 12. Higher-Order Characteristic Equations

The same method applies to higher-order constant-coefficient equations.

Consider

$$\boxed{a_ny^{(n)}+\cdots+a_1y'+a_0y=0.}$$

Assuming

$$
y=e^{rx}
$$

produces the characteristic polynomial

$$\boxed{a_nr^n+\cdots+a_1r+a_0=0.}$$

The roots of this polynomial determine the general solution.

---

# 13. Repeated Roots of Higher Multiplicity

Suppose $\(r\)$ is a root of multiplicity $\(m\)$.

Then the corresponding solutions are

$$e^{rx},\quad xe^{rx},\quad x^2e^{rx},\quad \ldots,\quad x^{m-1}e^{rx}.$$

Thus, the contribution to the general solution is

$$\boxed{e^{rx}\left(c_1+c_2x+\cdots+c_mx^{m-1}\right).}$$

### Example

Suppose the characteristic polynomial is

$$
(r-2)^3(r+1)=0.
$$

The root $\(r=2\)$ has multiplicity $\(3\)$, while $\(r=-1\)$ has multiplicity $\(1\)$.

Therefore,

$$\boxed{y=(c_1+c_2x+c_3x^2)e^{2x}+c_4e^{-x}.}$$

---

# 14. Non-Homogeneous Higher-Order Equations

A non-homogeneous linear equation has the form

$$\boxed{L[y]=g(x).}$$

Its general solution can be written as

$$\boxed{y=y_c+y_p,}$$

where:

* $\(y_c\)$ is the **complementary solution** or complementary function.
* $\(y_p\)$ is a **particular solution**.

This is one of the most important ideas in the chapter.

---

# 15. Complementary Solution

The complementary solution is obtained by solving the associated homogeneous equation

$$L[y]=0.$$

For example,

$$
y''-5y'+6y=e^x
$$

has associated homogeneous equation

$$
y''-5y'+6y=0.
$$

From the characteristic equation,

$$
(r-2)(r-3)=0,
$$

we obtain

$$\boxed{y_c=c_1e^{2x}+c_2e^{3x}.}$$

---

# 16. Particular Solution

The **particular solution** $\(y_p\)$ is any one solution of

$$L[y]=g(x).$$

The complete solution is

$$\boxed{y=y_c+y_p.}$$

There are several methods for finding $\(y_p\)$.

Two important methods are:

1. **Method of undetermined coefficients**
2. **Variation of parameters**

---

# 17. Method of Undetermined Coefficients

The method of undetermined coefficients is particularly effective when $\(g(x)\)$ consists of functions such as:

* Polynomials
* Exponentials
* Sines and cosines
* Products of these functions

The basic strategy is:

1. Find the complementary solution.
2. Choose an appropriate form for $\(y_p\)$.
3. Substitute $\(y_p\)$ into the differential equation.
4. Determine the unknown coefficients.
5. Combine $\(y_c\)$ and $\(y_p\)$.

---

# 18. Example: Polynomial Forcing

Solve

$$
y''-3y'+2y=x.
$$

### Step 1: Solve the homogeneous equation

$$
y''-3y'+2y=0.
$$

Characteristic equation:

$$
r^2-3r+2=0.
$$

Factor:

$$
(r-1)(r-2)=0.
$$

Thus,

$$\boxed{y_c=c_1e^x+c_2e^{2x}.}$$

### Step 2: Assume a particular solution

Since the forcing function is $\(x\)$, try

$$y_p=Ax+B.$$

Then

$$y_p'=A,\qquad y_p''=0.$$

### Step 3: Substitute

$$
0-3A+2(Ax+B)=x.
$$

Therefore,

$$
2Ax+(2B-3A)=x.
$$

Compare coefficients:

$$
2A=1
$$

so

$$
A=\frac{1}{2}.
$$

And

$$
2B-3A=0.
$$

Thus,

$$
B=\frac{3}{4}.
$$

Therefore,

$$
y_p=\frac{x}{2}+\frac{3}{4}.
$$

### Step 4: General solution

$$\boxed{y=c_1e^x+c_2e^{2x}+\frac{x}{2}+\frac34.}$$

---

# 19. Example: Exponential Forcing

Consider

$$
y''-3y'+2y=e^{3x}.
$$

The complementary solution is

$$
y_c=c_1e^x+c_2e^{2x}.
$$

Since \(e^{3x}\) is not part of \(y_c\), assume

$$
y_p=Ae^{3x}.
$$

Then

$$
y_p'=3Ae^{3x}
$$

and

$$
y_p''=9Ae^{3x}.
$$

Substitute:

$$9Ae^{3x}-9Ae^{3x}+2Ae^{3x}=e^{3x}.$$

Therefore,

$$
2A=1
$$

and

$$
A=\frac12.
$$

Hence,

$$
\boxed{
y=c_1e^x+c_2e^{2x}+\frac12e^{3x}.
}
$$

---

# 20. Resonance and Modification of the Trial Solution

A common difficulty occurs when the proposed particular solution duplicates part of the complementary solution.

Consider

$$
y''-3y'+2y=e^x.
$$

The complementary solution is

$$
y_c=c_1e^x+c_2e^{2x}.
$$

If we tried

$$
y_p=Ae^x,
$$

it would duplicate a term already present in \(y_c\).

Therefore, multiply by \(x\):

$$\boxed{y_p=Axe^x.}$$

More generally, if the proposed trial function corresponds to a characteristic root of multiplicity $\(m\)$, multiply the trial function by

$$
x^m.
$$

### Resonance Rule

| Situation                                                           | Modification        |
| ------------------------------------------------------------------- | ------------------- |
| Trial function not in $\(y_c\)$                                       | No modification     |
| Trial function corresponds to a simple root                         | Multiply by $\(x\)$   |
| Trial function corresponds to a repeated root of multiplicity $\(2\) $| Multiply by $\(x^2\)$ |
| Trial function corresponds to multiplicity $\(m\)$                    | Multiply by $\(x^m\)$ |

---

# 21. Trigonometric Forcing

Consider

$$
y''+4y=\cos(3x).
$$

The homogeneous equation is

$$
y''+4y=0.
$$

Its characteristic equation is

$$
r^2+4=0,
$$

giving

$$
r=\pm2i.
$$

Therefore,

$$
y_c=c_1\cos2x+c_2\sin2x.
$$

Since $\(\cos3x\)$ is not part of the complementary solution, assume

$$
y_p=A\cos3x+B\sin3x.
$$

Substitute into the equation and solve for $\(A\)$ and $\(B\)$.

In this case,

$$
y_p=-\frac15\cos3x.
$$

Hence,

$$\boxed{y=c_1\cos2x+c_2\sin2x-\frac15\cos3x.}$$

---

# 22. Variation of Parameters

The method of undetermined coefficients is powerful but does not work conveniently for every forcing function.

For a second-order equation

$$
y''+P(x)y'+Q(x)y=g(x),
$$

suppose $\(y_1\)$ and $\(y_2\)$ form a fundamental set of solutions of the homogeneous equation.

A particular solution can be obtained using **variation of parameters**.

The standard formulas are

$$\boxed{u_1'=-\frac{y_2g}{W}}$$

and

$$\boxed{u_2'=\frac{y_1g}{W},}$$

where

$$
W=y_1y_2'-y_2y_1'
$$

is the Wronskian.

Then

$$
y_p=u_1y_1+u_2y_2.
$$

### When to Use Variation of Parameters

This method is useful when the forcing function contains expressions such as

$$
\ln x,\qquad
\tan x,\qquad
\sec x,\qquad
\frac{1}{x},
$$

or other functions for which undetermined coefficients is not appropriate.

---

# 23. Initial-Value Problems

A higher-order initial-value problem consists of a differential equation together with initial conditions.

For an $\(n\)$-th-order equation, we generally require $\(n\)$ independent initial conditions.

For example,

$$
y''-5y'+6y=0
$$

with

$$
y(0)=2,
\qquad
y'(0)=1.
$$

The general solution is

$$
y=c_1e^{2x}+c_2e^{3x}.
$$

Differentiate:

$$
y'=2c_1e^{2x}+3c_2e^{3x}.
$$

Apply $\(y(0)=2\)$:

$$
c_1+c_2=2.
$$

Apply $\(y'(0)=1\)$:

$$
2c_1+3c_2=1.
$$

Solving simultaneously gives

$$
c_1=5,\qquad c_2=-3.
$$

Therefore,

$$\boxed{y=5e^{2x}-3e^{3x}.}$$

---

# 24. Operator Notation

Higher-order differential equations can be written compactly using the differential operator

$$
D=\frac{d}{dx}.
$$

For example,

$$
y''-5y'+6y=0
$$

can be written as

$$
(D^2-5D+6)y=0.
$$

Factoring,

$$
(D-2)(D-3)y=0.
$$

This notation provides a useful connection between differential equations and polynomial algebra.

For constant-coefficient equations,

$$
P(D)y=0
$$

corresponds directly to the characteristic polynomial

$$
P(r)=0.
$$

---

# 25. Applications of Higher-Order ODEs

Higher-order differential equations appear in many areas of science and engineering.

## 25.1 Mechanical Vibrations

A mass-spring-damper system can be modelled by

$$\boxed{mx''+cx'+kx=F(t)}$$

where:

* $\(m\)$ = mass,
* $\(c\)$ = damping coefficient,
* $\(k\)$ = spring constant,
* $\(x(t)\)$ = displacement,
* $\(F(t)\)$ = external force.

This is a second-order linear ODE.

---

## 25.2 Undamped Vibrations

If there is no damping and no external force,

$$
mx''+kx=0.
$$

Dividing by \(m\),

$$
x''+\frac{k}{m}x=0.
$$

The characteristic equation is

$$
r^2+\frac{k}{m}=0.
$$

Thus, the motion is oscillatory.

---

## 25.3 Electrical Circuits

A series RLC circuit can be modelled by

$$\boxed{Lq''+Rq'+\frac{1}{C}q=E(t).}$$

This has the same mathematical structure as the mass-spring-damper system:

$$
m x''+cx'+kx=F(t).
$$

This mathematical similarity allows techniques from one field to be applied to the other.

---

# 26. Common Mistakes

### ❌ Mistake 1: Forgetting the complementary solution

For a non-homogeneous equation,

$$
y=y_c+y_p.
$$

Do not report $\(y_p\)$ alone.

---

### ❌ Mistake 2: Using the wrong characteristic equation

For

$$
ay''+by'+cy=0,
$$

the characteristic equation is

$$
ar^2+br+c=0.
$$

Make sure the signs and coefficients are copied correctly.

---

### ❌ Mistake 3: Ignoring repeated roots

If

$$
(r-r_0)^2=0,
$$

the solution is not simply

$$
c_1e^{r_0x}+c_2e^{r_0x}.
$$

Instead,

$$\boxed{y=(c_1+c_2x)e^{r_0x}.}$$

---

### ❌ Mistake 4: Forgetting the $\(e^{\alpha x}\)$ factor

For complex roots

$$
r=\alpha\pm\beta i,
$$

the real solution is

$$
e^{\alpha x}
(c_1\cos\beta x+c_2\sin\beta x).
$$

---

### ❌ Mistake 5: Not checking resonance

Before selecting $\(y_p\)$, compare the trial function with the complementary solution.

If there is overlap, multiply the trial function by an appropriate power of $\(x\)$.

---

### ❌ Mistake 6: Applying initial conditions too early

It is usually easier to:

1. Find the general solution.
2. Differentiate as needed.
3. Apply all initial conditions.
4. Solve for the constants.

---

# 27. Solution Strategy

When solving a higher-order linear ODE, use the following workflow:

```text
              Start
                │
                ▼
      Identify the order
                │
                ▼
       Is the equation linear?
          │             │
         No            Yes
          │             │
          ▼             ▼
   Use an appropriate   Is it homogeneous?
   nonlinear method      │          │
                        Yes         No
                         │           │
                         ▼           ▼
                  Find yc       Find yc
                         │           │
                         │           ▼
                         │       Find yp
                         │           │
                         └─────┬─────┘
                               ▼
                         y = yc + yp
                               │
                               ▼
                    Apply initial conditions
                               │
                               ▼
                         Verify solution
```

---

# 28. Method Selection Guide

| Equation Type                      | Recommended Method                     |
| ---------------------------------- | -------------------------------------- |
| Homogeneous constant coefficients  | Characteristic equation                |
| Distinct real roots                | Exponential solutions                  |
| Repeated roots                     | Multiply by powers of $\(x\) $           |
| Complex roots                      | Sine-cosine form                       |
| Polynomial forcing                 | Undetermined coefficients              |
| Exponential forcing                | Undetermined coefficients              |
| Sinusoidal forcing                 | Undetermined coefficients              |
| Polynomial × exponential           | Undetermined coefficients              |
| Forcing function unsuitable for UC | Variation of parameters                |
| Initial conditions present         | Apply after obtaining general solution |

---

# 🧠 Key Formulas

### General Linear ODE

$$\boxed{a_ny^{(n)}+\cdots+a_1y'+a_0y=g(x)}$$

### Homogeneous Solution

$$\boxed{L[y]=0}$$

### Non-Homogeneous Solution

$$\boxed{y=y_c+y_p}$$

### Characteristic Equation

For

$$
a_ny^{(n)}+\cdots+a_1y'+a_0y=0,
$$

use

$$\boxed{a_nr^n+\cdots+a_1r+a_0=0.}$$

### Repeated Root

For a root $\(r\)$ of multiplicity $\(m\)$,

$$\boxed{e^{rx},xe^{rx},\ldots,x^{m-1}e^{rx}}$$

are the corresponding independent solutions.

### Complex Roots

For

$$
r=\alpha\pm\beta i,
$$

$$\boxed{y=e^{\alpha x}(c_1\cos\beta x+c_2\sin\beta x).}$$

### Variation of Parameters

$$
\boxed{
u_1'=-\frac{y_2g}{W},
\qquad
u_2'=\frac{y_1g}{W}.
}
$$

---

# ✏️ Practice Problems

## Problem 1 — Distinct Real Roots

Solve

$$
y''-7y'+12y=0.
$$

---

## Problem 2 — Repeated Root

Solve

$$
y''+6y'+9y=0.
$$

---

## Problem 3 — Complex Roots

Solve

$$
y''+2y'+5y=0.
$$

---

## Problem 4 — Third-Order Equation

Solve

$$
y'''-3y''+3y'-y=0.
$$

---

## Problem 5 — Non-Homogeneous Equation

Solve

$$
y''-4y'+4y=e^{2x}.
$$

Pay particular attention to resonance.

---

## Problem 6 — Polynomial Forcing

Solve

$$
y''-y'-2y=x+1.
$$

---

## Problem 7 — Initial-Value Problem

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

---

## Problem 8 — Application

A mass of $\(2\)$ kg is attached to a spring with spring constant $\(8\)$ N/m. Assuming no damping or external force, formulate and solve the differential equation governing the displacement $\(x(t)\)$.

---

# 📌 Chapter Summary

Higher-order differential equations extend the ideas introduced for first-order ODEs and provide powerful tools for modelling complex systems.

The most important ideas from this chapter are:

1. A higher-order ODE contains derivatives of order two or higher.
2. Linear equations contain $\(y\)$ and its derivatives only to the first power.
3. Homogeneous equations have zero forcing terms.
4. Constant-coefficient homogeneous equations can be solved using a **characteristic equation**.
5. Distinct real roots produce exponential solutions.
6. Repeated roots require multiplication by powers of $\(x\)$.
7. Complex roots produce exponentially modified sine and cosine solutions.
8. Non-homogeneous solutions have the structure

$$
\boxed{y=y_c+y_p}.
$$

9. **Undetermined coefficients** is useful for many standard forcing functions.
10. **Variation of parameters** provides a more general method for finding particular solutions.
11. Initial conditions determine the arbitrary constants.
12. Higher-order ODEs provide mathematical models for mechanical vibrations, electrical circuits, and many other physical systems.

---

## 🔗 Topics Covered

* Higher-order ordinary differential equations
* Linear higher-order ODEs
* Homogeneous equations
* Non-homogeneous equations
* Principle of superposition
* Linear independence
* Wronskian
* Constant-coefficient equations
* Characteristic equations
* Distinct real roots
* Repeated roots
* Complex roots
* Complementary solutions
* Particular solutions
* Undetermined coefficients
* Resonance
* Variation of parameters
* Initial-value problems
* Mechanical vibrations
* Electrical circuits

---

**Course:** HMTH113 — Ordinary Differential Equations
**Chapter:** 4 — Higher-Order Differential Equations
