# CS1200 - Calculate the 8th Mersenne prime.

The given MATLAB code is as such:
```MATLAB
clear ; clc ; close all ; format compact ;

tol = 1e-10;
nlimit = 2000000000;

primelist = primes(nlimit);
nprimes = length(primelist)
fprintf('\n');
mcount = 0;
for i=1:nprimes,
  twopow = log2(primelist(i)+1);
  if abs(twopow-round(twopow))<tol
    mcount = mcount + 1;
    fprintf('%7d %7d is a Mersenne prime with 2 exp of %4d\n',...
    mcount,primelist(i),twopow);
  end
end
twopow
```

#### Hypotheses:
The generation of primes(nlimit) contributers to the slow down, since it is
generating all primes, not just Mersenne primes. However what I reason what is
the cause for the main slow down is then the code checks each prime for it's
possible Mersenne counter part.

#### What I plan to try:
Mersenne primes only have appeared with a odd exponent with the exception of:
2^2 - 1 = 3. So I will generate a list/vector/array
(whatever it is called in the language I decide to use) with the follow idea:
```Haskell
oddNumbers = filter odd [1..200]
mersenneify n = (2^n) - 1
possibleMersennePrimes = map (mersenneify) oddNumbers
```
i.e. list of odd numbers raised to the order of two
then minus one. After that test each element with the
square root method talked about in the class.
