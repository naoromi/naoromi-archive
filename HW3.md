# Exercise 1
A)
We are given $\sum_{j=1}^{k}n \frac{(\bar{Y}_{.j}-\mu_{j})^{2}}{\sigma^{2}_{j}}$

Consider that a $\chi^{2}_{\nu}$ distribution may be defined as the sum of squared $\nu$ standard normal distributions. That is, $\sum_{i=1}^{\nu}(Z_{i})^{2}\sim \chi^{2}_{\nu}$ where $Z\sim N(0,1)$. 

We must deduce that $\sum_{j=1}^{k}n \frac{(\bar{Y}_{.j}-\mu_{j})^{2}}{\sigma^{2}_{j}}$ is the sum of squared independent standard normals. 

Begin by finding the distribution of $\bar{Y}_{.j}$. 

We are given $\bar{Y}_{.j}=\frac{1}{n}\sum_{i=1}^{n}Y_{ij}$, and since $Y_{ij}$ is normal, then $\bar{Y}_{.j}$ is simply the linear combination of normals. Thus, $\bar{Y}_{.j}\sim N$.

We now find $E[\bar{Y}_{.j}]$. $$
\begin{align}
E[\bar{Y}_{.j}] & =\frac{1}{n}\sum_{i=1}^{n}E[Y_{ij}] \\
 & =\frac{1}{n}\sum_{i=1}^{n}\mu_{j} \\
  & =\mu_{j}
\end{align}
$$
Next, find $Var(\bar{Y}_{.j})$
$$
\begin{align}
Var(\bar{Y}_{.j}) & =Var\left( \frac{1}{n}\sum_{i=1}^{n}Y_{ij} \right) \\
 & =\frac{1}{n^{2}}\sum_{i=1}^{n}Var(Y_{ij})  & Y_{ij}\text{ are independent} \\
  & =\frac{1}{n^{2}}\sum_{i=1}^{n}\sigma^{2}_{j}  \\
 & =\frac{\sigma^{2}_{j}}{n}
\end{align}
$$

So we can write $\bar{Y}_{.j}\sim N\left( \mu_{j},\frac{\sigma^{2}_{j}}{n} \right)$

Let $Z_{j}$ be the standardized $\bar{Y}_{.j}$
$$
\begin{align}
Z_{j}=\frac{\bar{Y}_{.j}-\mu_{j}}{\sqrt{ \frac{\sigma^{2}_{j}}{n} }}
\end{align}
$$
We then square our standard $Z$
$$
\begin{align}
Z_{j}^{2} & =\left( \frac{\bar{Y}_{.j}-\mu_{j}}{\sqrt{ \frac{\sigma^{2}_{j}}{n} }} \right) ^{2} \\
 & =\frac{(\bar{Y}_{.j}-\mu_{j})^{2}}{\sqrt{ \frac{\sigma^{2}_{j}}{n}  }^{2}} \\
  & =\frac{(\bar{Y}_{.j}-\mu_{j})^{2}}{\frac{\sigma^{2}_{j}}{n} }  \\
Z_{j}^{2} & =n\frac{(\bar{Y}_{.j}-\mu_{j})^{2}}{{\sigma^{2}_{j}} } 
\end{align}
$$

Our calculated $Z^{2}_{j}$ is precisely the expression found in the given summation $\sum_{j=1}^{k}n \frac{(\bar{Y}_{.j}-\mu_{j})^{2}}{\sigma^{2}_{j}}$.

We may rewrite the given statement as $$
\begin{align}
\sum_{j=1}^{k}Z_{j}^{2}
\end{align}
$$
Notice that this is the exact definition of a $\chi^{2}$ distribution. As well, $Z_{j}^{2}$ are all independence since $Y_{ij}$ are independent across all $j$. Therefore, 
$$
\begin{align}
\sum_{j=1}^{k}Z^{2}_{j}\sim \chi^{2}_{k}
\end{align}
$$

Which implies that 
$$
\sum_{j=1}^{k}n \frac{(\bar{Y}_{.j}-\mu_{j})^{2}}{\sigma^{2}_{j}}\sim \chi^{2}_{k}
$$

B)

We take a different proof approach with moment generating functions. Specifically, we make use of the fact that functions with the same MGF are the same distribution.

We would like to prove that we have the distribution $\chi^{2}_{k-1}$, which has the following MGF.
$$
M_{\chi^{2}_{k-1}}(t)=\begin{cases}
(1-2t)^{-(k-1)/2}, & t< \frac{1}{2} \\
\text{not exist}, & t\geq \frac{1}{2}
\end{cases}
$$
We will go on to prove that the MGF of $\sum_{j=1}^{^{k}}n \frac{(\bar{Y}_{.j}-\bar{Y}_{..})^{2}}{\sigma^{2}}$ is equal to the MGF of $\chi^{2}_{k-1}$

We are this time given $\sum_{j=1}^{^{k}}n \frac{(\bar{Y}_{.j}-\bar{Y}_{..})^{2}}{\sigma^{2}}$
Notice that this is actually $\frac{SSTR}{\sigma^{2}}$.

Since we know that $SSTOT=SSTR+SSE$, then it follows
$$
\frac{SSTOT}{\sigma^{2}}=\frac{SSTR}{\sigma^{2}}+\frac{SSE}{\sigma^{2}}
$$

Another proof tells us that $\frac{SSTOT}{\sigma^{2}}\sim \chi^{2}_{n-1}$.
As well, since we are told $\mu_{j}=\mu$ and $\sigma_{j}=\sigma$ for all $j$, then another proof tells us that $\frac{SSE}{\sigma^{2}}\sim \chi^{2}_{n-k}$ and SSE independent of SSTR. 

We may perform a moment generating transform on our $\frac{SSTOT}{\sigma^{2}}=\frac{SSTR}{\sigma^{2}}+\frac{SSE}{\sigma^{2}}$ equation. This transform makes use of the fact that SSE and SSTR are independent so that the moment generating transform may be written as a product.
$$
\begin{align}
M_{\frac{SSTOT}{\sigma^{2}}}(t) & =M_{\frac{SSTR}{\sigma^{2}}}(t)M_{\frac{SSE}{\sigma^{2}}}(t) \\
M_{\frac{SSTR}{\sigma^{2}}}(t) & =\frac{M_{\frac{SSTOT}{\sigma^{2}}}(t)}{M_{\frac{SSE}{\sigma^{2}}}(t)}
\end{align}
$$

So we have represented $M_{\frac{SSTR}{\sigma^{2}}}(t)$ in terms of both $M_{\frac{SSTOT}{\sigma^{2}}}(t)$ and $M_{\frac{SSE}{\sigma^{2}}}(t)$, which are the moment generating functions of a $\chi^{2}$ distribution.

Now consider the known moment generating function for $\chi^{2}$ distributions
$$
M_{\chi^{2}_{w}}(t)=\begin{cases}
(1-2t)^{-w/2} & t< \frac{1}{2} \\
\text{not exist} & t\geq \frac{1}{2}
\end{cases}
$$
Then we have 
$$
\begin{align}
M_{\frac{SSTR}{\sigma^{2}}}(t) & = \frac{(1-2t)^{-(n-1)/2}}{(1-2t)^{-(n-k)/2}} \\
 & =(1-2t)^{-(k-1)/2}
\end{align}
$$

If we also apply the restriction that $t < \frac{1}{2}$
$$
\begin{align}
M_{\frac{SSTR}{\sigma^{2}}}(t) & =(1-2t)^{-(k-1)/2} ,&t< \frac{1}{2}
\end{align}
$$
We will notice that this is exactly the definition of the MGF for a $\chi^{2}$ distribution. Specifically, $w=k-1$.
$$
M_{\frac{SSTR}{\sigma^{2}}}(t)=M_{\chi^{2}_{k-1}}(t)=\begin{cases}
(1-2t)^{-(k-1)/2}, & t< \frac{1}{2} \\
\text{not exist}, & t\geq \frac{1}{2}
\end{cases}
$$
We deduced the MGF of $\sum_{j=1}^{^{k}}n \frac{(\bar{Y}_{.j}-\bar{Y}_{..})^{2}}{\sigma^{2}}$ is precisely the MGF for $M_{\chi^{2}_{k-1}}$. 

Thus, $\sum_{j=1}^{^{k}}n \frac{(\bar{Y}_{.j}-\bar{Y}_{..})^{2}}{\sigma^{2}}\sim \chi^{2}_{k-1}$.

C)
We specifically require $\mu_{j}=\mu$ and $\sigma_{j}=\sigma$ for all $j$ to ensure that $\frac{SSTOT}{\sigma^{2}}$ is indeed a $\chi^{2}_{n-1}$ distribution. 

D)
The proof for part A primarily relies on the definition of a $\chi^{2}$, the sum of squared standard normals. We started from a known normal distribution applied transformations such that it resembled the given. 
The proof for part B instead relies on moment generating functions and the property that functions with the same MGF must have the same distribution. Hence, we worked to transform the given into a state such that its MGF precisely matched the MGF of a $\chi^{2}_{k-1}$.

E)
Consider that degrees of freedom will decrease by how many population parameters were estimated. 
When comparing part A and part B, we notice that part A uses $\mu_{j}$ while part B uses $\bar{Y}_{..}$.
Part A
$$
\sum_{j=1}^{k}n \frac{(\bar{Y}_{.j}-\mu_{j})^{2}}{\sigma^{2}_{j}}
$$
Versus
Part B
$$
\sum_{j=1}^{^{k}}n \frac{(\bar{Y}_{.j}-\bar{Y}_{..})^{2}}{\sigma^{2}}
$$

So part A does not estimate its population mean and keeps its full degree. But part B must estimate $\mu$, and estimating one parameter results in degrees of freedom decreasing by one.

# Exercise 2
We are given $Y_{ij}=\mu_{j}+\beta_{i}+\epsilon_{ij}$, but since $\mu_{1}=\dots=\mu_{k}$, then we can actually simplify to $Y_{ij}=\mu+\beta _i+\epsilon_{ij}$ where $\epsilon_{ij}\sim N(0,\sigma^{2}_{i})$. In this way, $Y_{ij}$ are independent but not identically distributed since the variance is not constant between blocks. 
But notice that $\epsilon_{ij}\sim N(0,\sigma^{2}_{i})$ is only summed across blocks. So for a fixed block $i_{0}$, the errors $\epsilon_{i_{0}j}$ are i.i.d. for all $j$ . Within a fixed, arbitrary block $i_{0}$, we have $Y_{ij}=\mu+\beta_{i_{0}}+\epsilon_{i_{0}j}$. That is to say, $Y_{i_{0}j}$ is i.i.d. for all $j$ with a fixed block $i_{0}$.  

Therefore, our proof will center around showing that $\sum_{i=1}^{b}\sum_{j=1}^{k} \frac{(Y_{ij}-\bar{Y}_{i.})^{2}}{\sigma^{2}_{i}}$ can be represented as $\sum_{i=1}^{b}U_{i}$ where $U_{i}\sim \chi^{2}_{\nu_{i}}$. As well, the sum of independent $\chi^{2}$ distributions is itself a $\chi^{2}$ distribution with the summed degrees of freedom. That is, $\sum_{i=1}^{b}U_{i}\sim \chi^{2}_{\sum_{i=1}^{n}\nu_{i}}$.

It may be convenient to work on the inner summation in isolation and with a fixed, arbitrary $i_{0}$ such that $$\sum_{j=1}^{k} \frac{(Y_{i_{0}j}-\bar{Y}_{i_{0}.})^{2}}{\sigma^{2}_{i_{0}}}$$
In this way, we might notice that we can work towards an identity involving $\frac{(n-1)S^{2}}{\sigma^{2}}\sim \chi^{2}_{n-1}$ 
We multiply by $\frac{(k-1)}{(k-1)}$
$$
\begin{align}
 \sum_{j=1}^{k} \frac{(Y_{i_{0}j}-\bar{Y}_{i_{0}.})^{2}}{\sigma^{2}_{i_{0}}}\left( \frac{k-1}{k-1} \right)  & \implies \frac{k-1}{\sigma^{2}_{i_{0}}} \left( \frac{1}{k-1} \sum_{j=1}^{k}[(Y_{i_{0}j}-\bar{Y}_{i_{0}.})^{2}] \right)
\end{align}
$$
Since $Y_{i_{0}j}$ is i.i.d., we may use the definition $S^{2}$ to write $S_{i_{0}}^{2}=\frac{1}{k-1}\sum_{j=1}^{k}[(Y_{i_{0}j}-\bar{Y}_{i_{0}.})^{2}]$ to write
$$
\begin{align}
\frac{(k-1)S^{2}_{i_{0}}}{\sigma^{2}_{i_{0}}}
\end{align}
$$

And we know that $\frac{(k-1)S^{2}_{i_{0}}}{\sigma^{2}_{i_{0}}}\sim \chi^{2}_{k-1}$. For convenience, we let $U_{i}=\frac{(k-1)S^{2}_{i}}{\sigma^{2}_{i}}$, where $U_{i}\sim \chi^{2}_{k-1}$
Returning to our original summation, we can make the following simplification
$$
\begin{align}
\sum_{i=1}^{b}\sum_{j=1}^{k} \frac{(Y_{ij}-\bar{Y}_{i.})^{2}}{\sigma^{2}_{i}}   & \implies \sum_{i=1}^{b} \frac{(k-1)S^{2}_{i}}{\sigma^{2}_{i}}  \\
 & \implies \sum_{i=1}^{b}U_{i}
\end{align}
$$
Recall that we are given $\epsilon_{ij}$ are independent. Then it follows that each $S_{i}^{2}$ is independent and therefore each $U_{i}$ are independent.
In this way, we have found a sum of independent $\chi^{2}$ distributions. 

Consider that the sum of independent $\chi^{2}$ distributions is itself $\chi^{2}$ distributed with the summed degrees of freedom.

For convenience, we again say that $U_{i}\sim \chi^{2}_{k-1}$ so that
$$
\begin{align}
\sum_{i=1}^{b}U_{i} & \sim \chi^{2}_{\sum_{i=1}^{b}[k-1]}  \\
 & \sim \chi^{2}_{bk-b}
\end{align}
$$

Thus, we have proven that 
$$
\sum_{i=1}^{b}\sum_{j=1}^{k} \frac{(Y_{ij}-\bar{Y}_{i.})^{2}}{\sigma^{2}_{i}}\sim \chi^{2}_{bk-b}
$$

# Exercise 3

A)
Let $\mu_{m},\mu_{w},\mu_{sa},\mu_{su}$ be the true means of the calories on each day. 

$H_{0}:\mu_{m}=\mu_{w}=\mu_{sa}=\mu_{su}$
$H_{1}:$ At least one $\mu_{\text{day}}$ is different.
$\alpha=0.05$

From R, we have the output
```
            Df    Sum Sq    Mean Sq   F value     Pr(>F)    
day          3 5176005.7 1725335.22 402.64637 1.4913e-14 ***
person       5    2804.8     560.97   0.13091    0.98284    
Residuals   15   64274.8    4284.99                         
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```

We can see that we calculated the test statistic to be $F=402.646$ with $df_{treatment}=3$, $df_{error}=15$, and p-value of 1.49e-14. 

As well, we have $SS_{day}=5176005.7$, $SS_{person}=2804.8$, and $SSE=64274.8$

p-value$=1.49\times10^{-14}<\alpha=0.05$
We reject null. It seems that at least one day has a difference in terms of average calorie.



```
calories = c(1464, 1376, 1451, 1408, 1398, 1413,
              1927, 1892, 2024, 2059, 1932, 1881, 
              2600, 2510, 2518, 2531, 2491, 2583,
              2501, 2595, 2416, 2496, 2607, 2559)

day = factor(rep(c("mon", "wed", "sat", "sun"), each = 6))
person = factor(rep(1:6, times = 4))

data = data.frame(
  calories = calories,
  day = day,
  person = person
)

summary(aov(calories ~ day + person, data))
```

B)
We know that $SSTOT=SSTR+SSB+SSE$
Which in our context is $SSTOT=SS_{day}+SS_{person}+SSE$

Thus,
$$
\begin{align}
SSTOT & =5176005.7+2804.8+64274.8 \\
 & =5243085.3
\end{align}
$$

C)
We can not conclude anything other than that the null hypothesis wrong. Thus, we can not conclude anything about any specific day, only that one day is different. Certainly we can use Bonferroni correction to test each sub-hypothesis, albeit in exchange for weaker tests. 

D)
Consider that ANOVA tests require that data are independent within and across groups. By choosing randomly, we hopefully have participants that are unrelated to each other and are thus independent.