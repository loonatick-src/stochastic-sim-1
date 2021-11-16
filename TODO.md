# TODO
## Summary
- [ ] chi-square test for orthogonal and LHC sampling methods
- [ ] Welch-test for choosing i-value
- [ ] Confidence interval for s-value
- [ ] Rewrite the way of how data of simulations is saved
- [ ] Change line plots by adding the second Y-axis with difference |A(i,s) - A(j,s)|
- [ ] Box-plot (with a specific values of i and s) post 3 simulations (different sampling)
- [ ] F-test(Fischer) to compare the variance of the three sampling techniques given the same i and s
- [ ] Formulate final set of simulations for variance reduction
- [ ] Compare the final set of simulation -? with the other three methods by means of statistical tests -?

## Writing to do:
- [ ] Change sections



## Statistical Tests
### Orthogonal and LHC Sampling
Use chi-square test to verify that they resemble uniform distribution for large N
### Choosing an i-value 
We want to choose an i value such that |A(i,s) - A(j,s)| is small
for some j < i. So, we would like to test for E(A(i,s)) = E(A(j,s))
for a given s-value (this i-value will be used to report the final
result for A_M).

Welch-test appears to be suitable for this, provided we have settled
on a good s-value.

### Choosing an s-value
We could stick to 10^8 and report the corresponding 95% confidence
interval. Or we could choose a desired confidence interval and
keep producing samples till we get the desired confidence interval.
If s ~ 10^9, then some refactoring will be required, since we can
no longer generate all random samples in one shot. Options:
- Write your JIT uniform(0,1) to be able to generate uniform RV samples
within other JIT functions
- Refactor implementations to produce samples in smaller batches and
accumulate the results

The former should be easier.

### F-test(Fischer) to compare the variance of three sampling methods

## Experiments and data:
Save data in a different way that allows to make box-plots - discuss. CPU count -?
Run simulations (three sampling methods, and a formulated method for further variance reduction).

## Plots:
We change the line plots by adding the second y-axis corresponding to the difference |A(i,s) - A(j,s)|. 

Box plots are to be constructed with the data obtained from the simulations (after rewriting how data in simulations is saved).

We need to consider how to visualise results of the further variance reduction method. As one option, create and extra box plot and compare the variance. 

