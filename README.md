### Introduction
##### To construct exact samplers for Binomial(10, 1/3) and Poisson(t) using only Uniform(0,1) inputs, and to empirically validate estimators of 𝐸[𝑋],via elementary Monte Carlo (MC) with CLT-based uncertainty quantification.
#### Sample from Binomial distribution
##### To draw sample from a Binomial(10, 1/3) distribution by using the inversion method for a discrete distribution. Let the support be x∈{0,1,…,10}with pmf p(x)=Pr⁡(X=x)and CDF F(x)=∑_(j≤x)▒p(j) . For each draw, generate u∼Unif(0,1)and we use  pseudo-inverse of the cumulative distribution function. Then use it to  draw x from our target distribution using the generalized (quantile) inverse
##### F^(-1) (u)= inf⁡{x:"  " F(x)≥u}.
##### Here, U is the random variable(s) drawn from a Uniform (0,1) distribution that we transform into Bernoulli trials. 
##### Let U_ij∼iid Unif(0,1), p=1/3, i=1,…,n, j=1,…,10.
##### Define Bernoulli trials by inversion:
##### B_ij=1{U_ij≤p}.
##### Then Pr⁡(B_ij=1)=Pr⁡(U_ij≤p)=p⇒B_ij∼"Bernoulli" (p), independent.
##### Now we generate 100 Binomial(10, 1/3) samples using the combo method and computes the Monte Carlo mean, its standard error, and the 95% CLT confidence interval. Here, we state those steps in short-
	##### Draw x_1,…,x_100  i.i.d. from Binomial(10,1/3).
	##### Monte Carlo estimator of E[X]: μ ̂=xˉ=1/100 ∑_(i=1)^100▒x_i .
	##### Standard error of μ ̂(sample sd): se(μ ̂ )=s_x/√100.
	##### 95% CLT CI: xˉ ±  z_0.975 se(μ ̂ )         with z_0.975≈1.96.
#### Sample from Poisson distribution
##### We know that if  X ~ Binomial(n, p), the mean is E[X] = n p. As per Poisson approximation: when n is large and p is small with λ = n p fixed then Binomial (n, p) ≈ Poisson(λ). In a Poisson process of rate 1, the count over an interval of length t is N(t) ~ Poisson(λ) with λ = t. Hence, when relating to Binomial and Poisson process viewpoints, we match means via n p = λ = t.
##### Method one: Poisson process (transformation via interarrivals)
##### Method two: Direct inverse CDF for the Poisson (discrete pseudo-inverse)
#### Conclusion
##### Using inversion on Uniform (0,1) to obtain i.i.d. Bernoulli(p) trials and then the transformation exactly X_i ~ Binomial (10, p).
##### Sample mean and variance of (Binomial(10, 1/3)) for n = 1000 samples are μ ̂=3.353and σ ̂^2=2.185.From the above result we can say our combo samples reflects the theoretical Binomial(10, 1/3) distribution. Because here with 1000 draws we obtained μ ̂=3.353and σ ̂^2=2.185 which is close to close to the theoretical mean and variance respectively 3.333and 2.222.


