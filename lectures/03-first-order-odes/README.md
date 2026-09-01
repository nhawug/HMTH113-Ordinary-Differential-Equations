# HMTH113 — Ordinary Differential Equations

## Chapter 3: First-Order Differential Equations

This chapter introduces the fundamental methods used to **formulate, classify, and solve first-order ordinary differential equations (ODEs)**.

First-order ODEs arise naturally in mathematical modelling and have applications in population dynamics, radioactive decay, thermal processes, mechanics, and electrical circuits.

---

## 📚 Learning Objectives

By the end of this chapter, you should be able to:

* Recognize and write first-order ODEs in different forms.
* Identify **separable differential equations** and solve them by integration.
* Recognize homogeneous first-order equations and use appropriate substitutions.
* Determine whether a differential equation is **exact**.
* Find and apply an **integrating factor** to solve linear equations.
* Transform and solve **Bernoulli equations**.
* Formulate and solve basic mathematical models involving growth, decay, cooling, motion, and electrical circuits.
* Interpret the resulting solutions in the context of an application.

---

# 1. Forms of First-Order Differential Equations

A first-order differential equation involves the first derivative of the dependent variable.

## 1.1 Standard Form

A first-order ODE can be written in the form

$$
\boxed{y'=f(x,y)}.
$$

For example,

$$
y'=x+y.
$$

This form is particularly useful when discussing existence and uniqueness of solutions.

---

## 1.2 Differential Form

A first-order differential equation can also be written as

$$
\boxed{M(x,y)dx+N(x,y)dy=0}.
$$

For example,

$$
(2xy+1)dx+x^2dy=0.
$$

This form is especially useful when studying **exact differential equations**.

---

## 1.3 Linear First-Order Form

A first-order ODE is linear if it can be expressed as

$$
\boxed{y'+p(x)y=q(x)}.
$$

For example,

$$
y'+2y=e^x.
$$

The principal method for solving a linear first-order equation is the **integrating factor method**.

---

# 2. Separable Differential Equations

A first-order ODE is **separable** if it can be rearranged so that all terms involving $\(y\)$ appear with $\(dy\)$, while all terms involving $\(x\)$ appear with $\(dx\)$.

It can be written as

$$
{A(x)dx+B(y)dy=0}.
$$

Equivalently, it may often be written as

$$
\frac{dy}{dx}=f(x)g(y).
$$

The variables can then be separated:

$$
\frac{1}{g(y)}dy=f(x)dx.
$$

Integrating both sides gives

$$ \int \frac{1}{g(y)}dy = \int f(x)dx+C. $$

### Example

Consider

$$
\frac{dy}{dx}=xy.
$$

Separating variables,

$$
\frac{1}{y}dy=xdx.
$$

Integrating,

$$
\ln|y|=\frac{x^2}{2}+C.
$$

Thus,

$$
y=Ce^{x^2/2}.
$$

---

# 3. Homogeneous First-Order Equations

The term **homogeneous** can refer to different concepts in differential equations. In this section, we consider first-order equations of the form

$$
M(x,y)dx+N(x,y)dy=0,
$$

where $\(M\)$ and $\(N\)$ are homogeneous functions of the **same degree**.

A function $\(f(x,y)\)$ is homogeneous of degree $\(\alpha\)$ if

$${f(tx,ty)=t^\alpha f(x,y)}.$$

For example,

$$
f(x,y)=x^2+xy+y^2
$$

is homogeneous of degree $\(2\)$, since

$$
f(tx,ty)=t^2f(x,y).
$$

---

## 3.1 Solving Homogeneous ODEs

A common substitution is

$${y=ux},$$

where

$$
u=\frac{y}{x}.
$$

Differentiating $\(y=ux\)$ with respect to $\(x\)$,

$$\frac{dy}{dx}=u+x\frac{du}{dx}.$$

The substitution transforms the original differential equation into a **separable equation** involving $\(u\)$ and $\(x\)$.

An alternative substitution is

$$x=vy.$$

---

# 4. Exact Differential Equations

Consider a first-order differential equation in differential form:

$${M(x,y)dx+N(x,y)dy=0}.$$

The equation is **exact** if there exists a function $\(F(x,y)\)$ such that

$$
dF=F_xdx+F_ydy
$$

and

$$
F_x=M,\qquad F_y=N.
$$

Therefore,

$$
dF=Mdx+Ndy.
$$

The solution can then be written as

$${F(x,y)=C}.$$

---

## 4.1 Test for Exactness

If \(M\) and \(N\) have continuous first partial derivatives in the region under consideration, the equation is exact when

$${\frac{\partial M}{\partial y}=\frac{\partial N}{\partial x}}.$$

### Example

Suppose

$$
M(x,y)=2xy+3,
\qquad
N(x,y)=x^2+4y.
$$

Then

$$
\frac{\partial M}{\partial y}=2x
$$

and

$$
\frac{\partial N}{\partial x}=2x.
$$

Since the two partial derivatives are equal, the equation is exact.

---

# 5. Linear First-Order Equations and Integrating Factors

A linear first-order ODE has the form

$$y'+p(x)y=q(x).$$

The key idea is to multiply the entire equation by a specially chosen function called an **integrating factor**.

## 5.1 Integrating Factor

The integrating factor is

$${\mu(x)=e^{\int p(x)dx}}.$$

Multiplying the differential equation by $\(\mu(x)\)$ gives

$$\mu(x)y'+\mu(x)p(x)y=\mu(x)q(x).$$

The left-hand side becomes the derivative of a product:

$$\frac{d}{dx}\left[\mu(x)y\right]=\mu(x)q(x).$$

Integrating,

$$\mu(x)y=\int \mu(x)q(x)dx+C.$$

Therefore,

$${y=\frac{1}{\mu(x)}\left[\int \mu(x)q(x)\,dx+C\right]}.$$

---

# 6. Bernoulli Equations

A **Bernoulli differential equation** has the form

$$
\boxed{
\frac{dy}{dx}+a(x)y=f(x)y^n
}
$$

where

$$
n\neq0,1.
$$

Although nonlinear, a Bernoulli equation can be transformed into a linear first-order equation.

## 6.1 Bernoulli Substitution

Use the substitution

$${z=y^{1-n}}.$$

Differentiating,

$$
\frac{dz}{dx}=(1-n)y^{-n}\frac{dy}{dx}.$$

After substitution and simplification, the equation becomes a **linear differential equation in $\(z\)$**.

The general procedure is:

1. Identify the Bernoulli equation.
2. Use $\(z=y^{1-n}\)$.
3. Transform the equation into a linear equation in $\(z\)$.
4. Find the integrating factor.
5. Solve for $\(z\)$.
6. Substitute back to obtain $\(y\)$.

---

# 7. Choosing a Solution Method

One of the most important skills in solving first-order ODEs is **recognizing the appropriate method**.

| Type of ODE     | Standard Form / Test | Main Method                      |
| --------------- | -------------------- | -------------------------------- |
| **Separable**   | $\(y'=f(x)g(y)\)$      | Separate variables and integrate |
| **Homogeneous** | $\(dy/dx=F(y/x)\)$     | Substitute $\(y=ux\) $             |
| **Exact**       | $\(M_y=N_x\)$          | Find $\(F(x,y)=C\)$                |
| **Linear**      | $\(y'+p(x)y=q(x)\)$    | Integrating factor               |
| **Bernoulli**   | $\(y'+a(x)y=f(x)y^n\)$| Substitute $\(z=y^{1-n}\)$         |

### 💡 Strategy

When given a first-order ODE:

1. **Simplify the equation.**
2. Check whether it is **separable**.
3. If not, check whether it is **linear**.
4. If written in differential form, check for **exactness**.
5. Check for a **homogeneous** structure.
6. Check whether it is a **Bernoulli equation**.
7. Apply the appropriate substitution or integrating factor.
8. Apply any initial or boundary conditions.
9. Verify the solution by substitution where appropriate.

---

# 8. Applications of First-Order ODEs

First-order differential equations provide mathematical models for many real-world phenomena.

## 8.1 Growth and Decay

A basic model for population growth or radioactive decay is

$${\frac{dN}{dt}=kN}.$$

Its general solution is

$${N(t)=N_0e^{kt}}.$$

where:

* $\(N(t)\)$ is the quantity at time $\(t\)$,
* $\(N_0\)$ is the initial quantity,
* $\(k\)$ is the growth or decay constant.

If $\(k>0\)$, the quantity grows.

If $\(k<0\)$, the quantity decays.

---

## 8.2 Newton's Law of Cooling

Newton's Law of Cooling models the temperature of an object relative to its surroundings:

$${\frac{dT}{dt}=-k(T-T_m)}$$

where:

* $\(T(t)\)$ is the temperature of the object,
* $\(T_m\)$ is the ambient temperature,
* $\(k>0\)$ is a constant.

The model describes how the temperature difference between an object and its surroundings decreases over time.

---

## 8.3 Falling Bodies with Air Resistance

A simplified model for the velocity of a falling object with linear air resistance is

$${\frac{dv}{dt}+\frac{k}{m}v=g}.$$

where:

* $\(v(t)\)$ is the velocity,
* $\(m\)$ is the mass,
* $\(k\)$ is the resistance coefficient,
* $\(g\)$ is gravitational acceleration.

This is a **linear first-order ODE**.

---

## 8.4 RL Electrical Circuits

For a series RL circuit, the current can be modelled by

$${\frac{dI}{dt}+\frac{R}{L}I=\frac{E}{L}}.$$

where:

* $\(I(t)\)$ is the current,
* $\(R\)$ is the resistance,
* $\(L\)$ is the inductance,
* $\(E\)$ is the applied electromotive force.

This is a **linear first-order differential equation**.

---

## 8.5 RC Electrical Circuits

For a series RC circuit, the charge can be modelled by

$${\frac{dq}{dt}+\frac{1}{RC}q=\frac{E}{R}}.$$

where:

* $\(q(t)\)$ is the charge,
* $\(R\)$ is the resistance,
* $\(C\)$ is the capacitance,
* $\(E\)$ is the applied voltage.

Again, this is a **linear first-order ODE**.

---

# 🧠 Key Formulas

### Separable Equations

$${\frac{dy}{dx}=f(x)g(y)}$$

Separate and integrate:

$${\int\frac{1}{g(y)}dy=\int f(x)dx+C}$$

### Homogeneous Equations

$${y=ux}$$

with

$${\frac{dy}{dx}=u+x\frac{du}{dx}}.$$

### Exact Equations

$${M(x,y)\,dx+N(x,y)\,dy=0}$$

Exactness test:

$${M_y=N_x}$$

### Linear Equations

$${y'+p(x)y=q(x)}$$

Integrating factor:

$${\mu(x)=e^{\int p(x)\,dx}}$$

### Bernoulli Equations

$${y'+a(x)y=f(x)y^n}$$

Substitution:

$${z=y^{1-n}}$$

---

# ✏️ Practice Problems

### Problem 1 — Separable

Solve

$$
\frac{dy}{dx}=3xy.
$$

---

### Problem 2 — Homogeneous

Solve

$$\frac{dy}{dx}=\frac{x+y}{x}.$$

Use the substitution

$$y=ux.$$

---

### Problem 3 — Exact

Determine whether

$$
(2xy+3)dx+(x^2+4y)dy=0
$$

is exact. If it is, find the general solution.

---

### Problem 4 — Linear

Solve

$$
y'+2y=e^{-x}.
$$

---

### Problem 5 — Bernoulli

Solve

$$
y'+y=xy^2.
$$

Identify the appropriate Bernoulli substitution.

---

### Problem 6 — Application

A population satisfies

$$
\frac{dN}{dt}=0.04N,
\qquad N(0)=500.
$$

Determine the population after $\(10\)$ units of time.

---

# 📌 Chapter Summary

In this chapter, we studied several important classes of first-order differential equations and their solution techniques.

The main methods are:

1. **Separation of variables** — separate the $\(x\)$ and $\(y\)$ terms and integrate.
2. **Homogeneous substitution** — use $\(y=ux\)$ to reduce the equation to a separable form.
3. **Exact equations** — verify $\(M_y=N_x\)$ and construct a potential function.
4. **Integrating factors** — solve linear first-order equations.
5. **Bernoulli substitution** — transform a nonlinear equation into a linear one.
6. **Mathematical modelling** — apply first-order ODEs to physical, biological, and engineering problems.

The central skill is not simply memorizing formulas, but **recognizing the structure of an equation and selecting the appropriate solution method**.

---

## 🔗 Topics Covered

* First-order ODEs
* Standard and differential forms
* Separable equations
* Homogeneous equations
* Exact differential equations
* Linear first-order equations
* Integrating factors
* Bernoulli equations
* Growth and decay models
* Newton's Law of Cooling
* Falling bodies with resistance
* RL circuits
* RC circuits

---

**Course:** HMTH113 — Ordinary Differential Equations
**Chapter:** 3 — First-Order Differential Equations
