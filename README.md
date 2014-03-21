NodeJS-OLS
=========

A linear algebra implementation of ordinary least squares regression as a Node JS module with optional controls for heterskedasticity

Note: Although I have tested this for accuracy, please do not base any work on it without first testing it yourself.

## Dependencies

NodeJS: http://nodejs.org/
Sylvester: https://github.com/NaturalNode/node-sylvester

## Implementation

Just make sure you have NodeJS installed.

``` javascript
var ols = require('./ols.js'),
    sylvester = require('sylvester');
```

Your dependent variable must be in a matrix of the dimensions N x 1 where N is the number of observations, and your independent variables must be in a matrix of the dimensions N x K where K is your number of parameters.

``` javascript
var Y = $M([1],[2],[3]),
    X = $M([1,2,3],[1,2,3],[1,2,3]);
```

After that point, you can perform an OLS regression in the following way:

``` javascript
ols.reg(Y,X)
```

The third optional parameter allows for heteroskedasticity robust standard errors, T-statistics, and P-values. It is called in the following way:

``` javascript
ols.reg(Y,X,true)
```