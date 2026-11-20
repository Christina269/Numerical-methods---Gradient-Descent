# Gradient Descent and Optimization Algorithms


An undergraduate Numerical Methods in Statistics project examining first-order optimization on quadratic and Griewank functions and a synthetic linear regression example (10,000 observations, three predictors).

## Methods
Numerical gradient and Hessian, fixed-step gradient descent, golden-section line search, batch and stochastic gradient descent, mini-batch SGD, Momentum, Nesterov, AdaGrad, adaptive squared-gradient averaging and Adam.

## Run
```sh
python -m pip install -r requirements.txt
jupyter notebook gradient_descent.ipynb
```
Run all cells. No external data are required.

## Evaluation and limitations
The experiments use a fixed random seed, mean squared error and numerical derivatives. The adaptive squared-gradient averaging method is an RMSProp-style update, not canonical AdaDelta. Sampled mini-batch losses are noisy and are not directly comparable to full-data loss. The full-data MSE comparison uses equal parameter-update budgets, not equal computation cost.

## References
- Ruder, S. (2016). *An overview of gradient descent optimization algorithms*. arXiv:1609.04747.
- Lan, G. (2020). *First-order and stochastic optimization methods for machine learning*. Springer.

## Academic context
Undergraduate coursework. Confirm publication permission for any course-provided code.

## Reproduced results (100 parameter updates)
| Method | Full-data MSE | Parameter L2 error |
|---|---:|---:|
| Batch GD | 0.016043 | 0.271326 |
| SGD | 0.017215 | 0.258290 |
| Mini-batch | 0.015259 | 0.252869 |
| Momentum | 0.010611 | 0.068690 |
| Nesterov | 0.010371 | 0.061800 |
| AdaGrad | 0.307023 | 1.364093 |
| RMSProp-style | 0.011113 | 0.038078 |
| Adam | 0.013227 | 0.192552 |

These values depend on the selected learning rates and random seed and should not be read as a universal ranking.
