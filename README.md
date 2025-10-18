### Introduction
##### To construct exact samplers for Binomial(10, 1/3) and Poisson(t) using only Uniform(0,1) inputs, and to empirically validate estimators of 𝐸[𝑋],via elementary Monte Carlo (MC) with CLT-based uncertainty quantification.
#### Sample from Binomial distribution
##### To draw sample from a Binomial(10, 1/3) distribution by using the inversion method for a discrete distribution. Let the support be x∈{0,1,…,10}with pmf p(x)=Pr⁡(X=x)and CDF F(x)=∑_(j≤x)▒p(j) . For each draw, generate u∼Unif(0,1)and we use  pseudo-inverse of the cumulative distribution function. Then use it to  draw x from our target distribution using the generalized (quantile) inverse
##### F^(-1) (u)"  "="  "  inf⁡{x:"  " F(x)≥u}.
