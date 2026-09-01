# Lecture 01 — Calculus Review

## Overview

Before studying ordinary differential equations, we review several fundamental concepts from calculus that are used throughout the course.

The review focuses on:

* Limits and continuity
* Derivatives
* Integrals
* Basic differentiation rules
* Basic integration techniques
* Mathematical notation used in differential equations

These concepts provide the foundation for understanding and solving differential equations.

---

## 1. Limits and Continuity

The limit of a function describes the value that the function approaches as the independent variable approaches a particular point.

For a function `f(x)`, we write

$$
\lim_{x\to a} f(x)=L.
$$

Informally, this means that `f(x)` approaches `L` as `x` approaches `a`.

A function `f(x)` is continuous at `x=a` when

$$
\lim_{x\to a}f(x)=f(a).
$$

The concepts of limits and continuity are important when considering the existence and behaviour of solutions to differential equations.

---

## 2. Derivatives

The derivative describes the rate of change of a function.

For a function `y=f(x)`, the derivative is written as

$$
\frac{dy}{dx}=f'(x).
$$

The derivative can be defined using the limit

$$
f'(x) =
\lim_{h\to0}
\frac{f(x+h)-f(x)}{h}.
$$

### Example

If

$$
y=x^3,
$$

then

$$
\frac{dy}{dx}=3x^2.
$$

---

## 3. Integrals

Integration is closely related to differentiation.

If `F'(x)=f(x)`, then `F(x)` is an antiderivative of `f(x)`, and we write

$$
\int f(x)\,dx=F(x)+C.
$$

The constant `C` represents the family of antiderivatives.

### Example

$$
\int 3x^2dx=x^3+C.
$$

Differentiating the result gives

$$
\frac{d}{dx}(x^3+C)=3x^2.
$$

---

## 4. Why Calculus Is Important for Differential Equations

Differential equations describe relationships involving unknown functions and their derivatives.

For example,

$$
\frac{dy}{dx}=2x
$$

is a first-order differential equation.

To solve it, we integrate:

$$
y=\int 2x\,dx=x^2+C.
$$

Thus, knowledge of differentiation and integration is fundamental to solving differential equations.

---

## 5. Key Notation

Different notations are used for derivatives.

For `y=f(x)`:

$$
y'=\frac{dy}{dx}.
$$

For a function of time `t`, Newton's notation is also common:

$$
\dot{y}=\frac{dy}{dt}.
$$

Higher derivatives can be written as

$$
y'',\qquad y''',\qquad y^{(n)}.
$$

They can also be expressed using Leibniz notation:

$$
\frac{d^2y}{dx^2},
\qquad
\frac{d^3y}{dx^3},
\qquad
\frac{d^ny}{dx^n}.
$$

---

## Learning Objectives

After completing this lecture, students should be able to:

* Explain the meaning of a limit.
* Determine whether a function is continuous at a point.
* Calculate derivatives using standard differentiation rules.
* Calculate basic indefinite integrals.
* Explain the relationship between differentiation and integration.
* Interpret common derivative notation.
* Explain why calculus provides the foundation for solving differential equations.

---

## Exercises

### Exercise 1

Evaluate:

$$
\frac{d}{dx}(x^4+3x^2-5x+7).
$$

### Exercise 2

Find:

$$
\int (4x^3+6x-2)dx.
$$

### Exercise 3

Determine whether the function

$$
f(x)=|x|
$$

is differentiable at `x=0`.

### Exercise 4

Solve the differential equation

$$
\frac{dy}{dx}=6x
$$

by integration.

---

## Further Topics

The next lecture introduces differential equations, including their definition, classification, order, degree, linearity, and initial- and boundary-value problems.

## Source

The material in this lecture is based on the course notes in:

`notes/odes2016notes.pdf`
