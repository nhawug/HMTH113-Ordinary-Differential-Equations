# HMTH113 — Ordinary Differential Equations

## Chapter 2: Introduction to Differential Equations

Welcome to **Chapter 2 of HMTH113: Ordinary Differential Equations**.

This chapter introduces the fundamental concepts and terminology used throughout the study of ordinary differential equations (ODEs), including their classification, solutions, and initial- and boundary-value problems.

---

## 📚 Learning Objectives

By the end of this chapter, you should be able to:

* Define a differential equation and an ordinary differential equation.
* Identify the **order** and **degree** of a differential equation.
* Distinguish between **linear** and **nonlinear** ODEs.
* Identify **homogeneous** and **non-homogeneous** linear differential equations.
* Explain the difference between general, particular, singular, and complete solutions.
* Distinguish between **initial-value problems (IVPs)** and **boundary-value problems (BVPs)**.
* Recognize the standard form of an \(n\)-th-order linear ODE.

---

## 1. Fundamentals of Differential Equations

A **differential equation** is an equation that expresses a relationship between variables and their rates of change, represented by derivatives.

For example,

$$
\frac{dy}{dx}=3x^2
$$

is a differential equation because it relates the dependent variable \(y\), the independent variable \(x\), and the derivative of \(y\).

### Ordinary Differential Equation (ODE)

An **ordinary differential equation** is a differential equation involving:

* one real independent variable \(x\),
* a dependent variable \(y\), and
* one or more derivatives of \(y\).

For example,

$$
y''+3y'-4y=0
$$

is an ODE involving the derivatives \(y'\) and \(y''\).

In general, an \(n\)-th-order ODE can be represented implicitly as

$$
F\left(x,y,y',y'',\ldots,y^{(n)}\right)=0.
$$

---

## 2. Order and Degree

### Order

The **order** of a differential equation is the order of the **highest derivative** appearing in the equation.

For example,

$$
y''+5y'-6y=0
$$

is a **second-order** differential equation because the highest derivative is \(y''\).

Similarly,

$$
\frac{d^4y}{dx^4}+2\frac{d^2y}{dx^2}+y=0
$$

is a **fourth-order** differential equation.

### Degree

The **degree** of a differential equation is the power of the highest-order derivative, provided the equation is algebraic in its derivatives.

For example,

$$
(y'')^3+2y'+y=0
$$

has:

* **Order:** \(2\)
* **Degree:** \(3\)

> **Note:** The degree is not defined when the differential equation cannot be expressed as a polynomial in its derivatives.

---

## 3. Classification of Differential Equations

Differential equations can be classified in several ways.

### 3.1 Linear and Nonlinear ODEs

An ODE is **linear** if the dependent variable \(y\) and all of its derivatives occur only to the first power and are not multiplied together.

A general \(n\)-th-order linear ODE has the form

$$
p_0(x)y^{(n)}
+p_1(x)y^{(n-1)}
+\cdots
+p_{n-1}(x)y'
+p_n(x)y
=r(x).
$$

For example,

$$
y''+3xy'-2y=\sin x
$$

is linear.

In contrast,

$$
y''+y^2=0
$$

is nonlinear because \(y\) appears as \(y^2\).

Another nonlinear example is

$$
yy'+y=x,
$$

because \(y\) and \(y'\) are multiplied together.

---

### 3.2 Homogeneous and Non-Homogeneous Equations

For a linear ODE

$$
p_0(x)y^{(n)}
+p_1(x)y^{(n-1)}
+\cdots
+p_n(x)y=r(x),
$$

the equation is:

#### Homogeneous

If

$$
r(x)=0,
$$

the equation is called **homogeneous**.

Example:

$$
y''+4y'+3y=0.
$$

#### Non-Homogeneous

If

$$
r(x)\neq0,
$$

the equation is called **non-homogeneous**.

Example:

$$
y''+4y'+3y=e^x.
$$

> **Important:** The terms *homogeneous* and *non-homogeneous* in this context refer specifically to the right-hand side of a **linear differential equation**.

---

## 4. Solutions of Differential Equations

A **solution** of a differential equation is a function that satisfies the equation on a specified interval \(J\).

For example, consider

$$
y'=2x.
$$

Integrating gives

$$
y=x^2+C,
$$

where \(C\) is an arbitrary constant.

Therefore,

$$
\boxed{y=x^2+C}
$$

represents the general solution.

### 4.1 General Solution

The **general solution** contains arbitrary constants and represents a family of solutions.

For an \(n\)-th-order ODE, the general solution typically contains \(n\) arbitrary constants:

$$
y=\phi(x,c_1,c_2,\ldots,c_n).
$$

For example,

$$
y''=0
$$

has the general solution

$$
y=c_1x+c_2.
$$

Because this is a second-order equation, two arbitrary constants appear.

---

### 4.2 Particular Solution

A **particular solution** is obtained from the general solution by assigning specific values to the arbitrary constants.

For example, from

$$
y=x^2+C,
$$

choosing \(C=4\) gives

$$
\boxed{y=x^2+4}.
$$

This is a particular solution.

---

### 4.3 Singular Solution

A **singular solution** is a solution that cannot be obtained from the general solution simply by assigning values to its arbitrary constants.

Singular solutions can arise in certain differential equations, particularly those where solving for the general family introduces an envelope or another exceptional solution.

---

### 4.4 Complete Solution

The **complete solution** refers to the collection of all solutions associated with a differential equation, including the general family and any additional solutions such as singular solutions when they exist.

---

## 5. Initial-Value Problems

An **initial-value problem (IVP)** consists of a differential equation together with conditions imposed on the unknown function and, where appropriate, its derivatives at the **same value** of the independent variable.

For example,

$$
y''+y=0,
$$

subject to

$$
y(0)=1,\qquad y'(0)=0.
$$

Both conditions are specified at

$$
x=0.
$$

This is therefore an **initial-value problem**.

For an \(n\)-th-order ODE, an IVP typically requires \(n\) initial conditions.

---

## 6. Boundary-Value Problems

A **boundary-value problem (BVP)** consists of a differential equation together with conditions specified at **different values** of the independent variable.

For example,

$$
y''+y=0,
$$

subject to

$$
y(0)=0,\qquad y(\pi)=0.
$$

The conditions are imposed at two different points:

$$
x=0
$$

and

$$
x=\pi.
$$

Therefore, this is a **boundary-value problem**.

---

## 7. IVP vs. BVP

| Feature          | Initial-Value Problem      | Boundary-Value Problem          |
| ---------------- | -------------------------- | ------------------------------- |
| Conditions       | Given at the same point    | Given at different points       |
| Typical notation | $\(y(x_0), y'(x_0),\ldots\)$ | $\(y(a), y(b),\ldots\)$           |
| Common context   | Evolution over time        | Spatial or equilibrium problems |
| Example          | $\(y(0)=1,\ y'(0)=2\)$       | $\(y(0)=0,\ y(1)=3\)$             |

---

## 🧠 Key Concepts at a Glance

| Concept                 | Definition                                                                        |
| ----------------------- | --------------------------------------------------------------------------------- |
| **ODE**                 | Differential equation involving one independent variable                          |
| **Order**               | Highest derivative appearing in the equation                                      |
| **Degree**              | Power of the highest derivative when the equation is algebraic in its derivatives |
| **Linear ODE**          | $\(y\)$ and its derivatives occur linearly                                          |
| **Homogeneous**         | Linear ODE with $\(r(x)=0\)$                                                        |
| **Non-homogeneous**     | Linear ODE with $\(r(x)\neq0\)$                                                     |
| **General solution**    | Solution containing arbitrary constants                                           |
| **Particular solution** | Solution obtained by assigning values to arbitrary constants                      |
| **Singular solution**   | Additional solution not contained in the general family                           |
| **IVP**                 | Conditions specified at the same independent-variable value                       |
| **BVP**                 | Conditions specified at different independent-variable values                     |

---

## ✏️ Quick Practice

Classify each of the following differential equations by **order, degree, linearity, and homogeneity** where applicable.

### Question 1

$$
y''+5y'-6y=0
$$

### Question 2

$$
(y'')^2+y'=x
$$

### Question 3

$$
y''+y^2=0
$$

### Question 4

$$
y''+4y=\cos x
$$

### Question 5

Determine whether the following is an IVP or BVP:

$$
y''-y=0,\qquad y(0)=1,\quad y(2)=3.
$$

---

## 📌 Summary

This chapter introduced the fundamental language of ordinary differential equations.

The key ideas to remember are:

1. An **ODE** involves one independent variable and derivatives of a dependent variable.
2. The **order** is determined by the highest derivative.
3. The **degree** is the power of the highest derivative when the equation is algebraic in its derivatives.
4. Linear ODEs have a standard linear structure in \(y\) and its derivatives.
5. A linear ODE is **homogeneous** when its right-hand side is zero.
6. A **general solution** contains arbitrary constants.
7. A **particular solution** results from assigning specific values to those constants.
8. An **IVP** specifies conditions at the same point.
9. A **BVP** specifies conditions at different points.


---

## 🔗 Related Topics

This chapter provides the foundation for subsequent topics in ordinary differential equations, including:

* First-order differential equations
* Separable equations
* First-order linear equations
* Exact differential equations
* Higher-order linear ODEs
* Systems of differential equations
* Numerical methods for ODEs

---

**Course:** HMTH113 — Ordinary Differential Equations
**Chapter:** 2 — Introduction to Differential Equations
