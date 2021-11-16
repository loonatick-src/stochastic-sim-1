# TODO
## Summary
- [ ] chi-square test for orthogonal and LHC sampling methods
- [ ] Welch-test for choosing i-value
- [ ] Confidence interval for s-value

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
