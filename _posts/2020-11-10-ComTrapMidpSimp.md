---
title: MatLab - Composite trapezoid rule/Composite midpoint rule/Composite Simpson’s Rule
categories: [Notes]
comments: true
---

```matlab

function In = trapezcomp(f,a,b,n)

% composite trapezoidal function integrator
%
% INPUTS:
% f: the function to integrate
% a: lower bound of integration
% b:upper bound of integration
% n:number of points
% Initialization

h=(b-a)/n ;
x=a;
%composite rule

In = f(a);
for k=2:n
x=x+h;
In = In + 2.*f(x);
end
In =( In + f(b) ) * h * 0.5;

% end of function
==========================================================
function MF=midpoint_rule(f,a,b,n)
h=(b-a)/n;
ci=linspace( a+h/2, b-h/2, n-1); % ci are your evaluation points
y = f(ci); % This evaluates the function f , which is another matlab function
MF=h*sum(y); % you can just add up the vector y and multiply by h
end

==========================================================

function simps(f,a,b,n)
h=(b-a)/n;
sum_even=0;
for i=1:n/2-1
x(i) = a + 2*i*h;
sum_even = sum_even + f(x(i));
end

sum_odd = 0;
for i=1:n/2
x(i) = a + (2*i-1)*h;
sum_odd = sum_odd + f(x(i));
end

integral = h*(f(a)+2*sum_even+4*sum_odd+f(b))/3; % this needs to be changed accordingly with the specific problem you have at hand , before proceeding the command line
function y = f(x)
y = exp(x);
```
