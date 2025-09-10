  # CMPS 6610 Problem Set 02
## Answers

**Name: Qi An


Place all written answers from `assignment-01.md` here for easier grading.

1. **Asymptotic notation**

${log(n!)}$ = log(1) + log(2) + ... = $\sum_{k=1}^{n}log(k)$ ${\leq}$ $\sum_{k=1}^{n}log(n)  =  nlog(n)$ Hence, ${log(n!) = O(n \log n)}$.

For the larger half, [n/2, n], there are n/2 terms, so $log(n!) \geq \frac{n}{2} log(\frac{n}{2}) = \frac{n}{2}(log(n) - log(2))$ Hence, ${log(n!) = \Omega(n \log n)}$.

${log(n!) = O(n \log n) = \Omega(n \log n)}$.

Hence ${log(n!) = \Theta(n \log n)}$

2. 
- leaf dominated, $T(n) = O(n^{log_6 2}) $
- leaf dominated $T(n) = O(n^{log_4 6}) $
- balanced $T(n) = O(nlog_7 n) $
- root dominated $T(n) = O(n^2) $
- root dominated $T(n) = O(n^3) $
- root dominated $T(n) = O(n^{3/2}log(n)) $
- balanced $T(n) = O(n) $
- balanced $T(n) = O(n^{c+1}) $
- balanced $T(n) = O(log_2 log_2 n) $



3. 

${W_A(n)} = 2{W_A(n/5)} + n^2$ 

${S_A(n)} = {S_A(n/5)} + n^2$ 

Both the work and span are root dominated, $O(n^2)$

${W_B(n)} = {W_B(n - 1)} + log(n) $

${S_B(n)} = {S_B(n - 1)} + log(n) $

Both work and span have same asymp time and balanced recurrence, $O(nlogn)$

${W_C(n)} = {W_C(\frac{n}{3})} + {W_C(\frac{2n}{3})} + n^{1.1}$

${S_C(n)} = O(n^{1.1})$

Both work and span root dominated,  $O(n^{1.1})$

i would choose algorithm B as it has the smallest work and span asymptotically.

4. 

${W_A(n)} = 5{W_A(n/2)} + n$ 
Leaf dominated, ${W_A(n)} = O(n^{log_2 5})$

${S_A(n)} = {S_A(n/2)} + n$  Root dominated, ${S_A(n)} = O(n)$

${W_B(n)} = 2{W_B(n - 1)} + 1 $ Leaf Dominated $W_B(n) = O(2^n)$

${S_B(n)} = {S_B(n - 1)} + 1 $ 
Balanced, ${S_B(n)} = O(n)$

${W_C(n)} = 9{W_C(\frac{n}{3})}+ n^{2}$ Balanced $W_C(n) = O(n^2 log n)$

${S_C(n)} = {S_C(\frac{n}{3})}+ n^{2}$ Root Dominated ${S_C(n)} = O(n^2)$

i would choose algorithm A as it has the smallest work and span asymptotically.


5.
For Quadratics,
$ W(n) = 4W(n/2) + O(n^2)= O(n^2)$

For karatsuba, 
$ W(n) = 3W(n/2) + O(n)= O(n^{log_2 3})$

|          n |   quadratic |   subquadratic |
|------------|-------------|----------------|
|         10 |       0.063 |          0.022 |
|        100 |       0.029 |          0.048 |
|       1000 |       0.064 |          0.135 |
|      10000 |       0.071 |          0.163 |
|     100000 |       0.129 |          0.203 |
|    1000000 |       0.220 |          0.245 |
|   10000000 |       0.164 |          0.255 |
|  100000000 |       0.302 |          0.415 |
| 1000000000 |       0.333 |          0.540 |

For large inputs, Karatsuba scales better, shorter time taken. 

6.
a) If more than half the students are black hats, they can conspire and give the same results as the white hat. Since there are more black hats than white hats, unable to distinguish truth from lies, white hats from black hats.

b) The algorithm is as follows, do the pairwise interview. For each pair, if both students say that the other studnet is a white hat, they must have the same colored hat hence retain one of the student for the next round. If not, dont retain any of the 2 student, continue interview with another pair. Since the number of whites are more than half initially, by interviewing n/2 pairs, there is at most n/2 survivors, reducing the size of the problem by half. This is because pairings that survive are of the same color but because white is majority at the start, a white candidate is definitely in remaining students.

c) Using the algorithm aboce, each pass uses O(size) interviews, and cuts the size of the oroblem by half. After log(n) pass, the problem has been reduced to constant. So total interviews is n + n/2 + n/4 + ... which adds up to $\theta$(n) interviews.