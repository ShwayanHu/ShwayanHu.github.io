---
title: "Notes: Addressing Multiple Detection Limits with Semiparametric Cumulative Probability Models"
date: 2024-08-27
collection: portfolio
---

>    Source paper citation: Tian, Y., Li, C., Tu, S., James, N. T., Harrell, FrankE., & Shepherd, BryanE. (2024). Addressing Multiple Detection Limits with Semiparametric Cumulative Probability Models. *Journal of the American Statistical Association*, *119*(546), 864–874. https://doi.org/10.1080/01621459.2024.2315667

-   Main idea: a new approach to deal with multiple Detection Limits (DLs) based on a widely used ordinal regression model, the cumulative probability model (CPM)

-   Feature of CPM

    -   rank-based: easy to add label to censored data below or above DLs, without specifying value and distributions beyond DLs
    -   semiparametric: only assumption is the link function $G$: $G[F(y|X)]=\alpha(y)-\beta'X$
    -   able to handle mixed distributions of continues and discrete outcome variables, through selecting proper anchor points

-   Cumulative Probability Models (CPM)

    Outcome is modeled as $Y=H(\beta'X+\epsilon)$, where $H$ is monotonically increasing transformation, $X$ is vector of covariates, $\epsilon$ follows a known distribution with CDF $F_\epsilon$.

    Let $G=F_\epsilon^{-1}$, $\alpha=H^{-1}$, then 
    $$
    G[F(y|X)]=\alpha(y)-\beta'X
    $$
    

    which is CPM.

-   Nonparametric likelihood

    Data: ${(y_i,x_i): i=1,...,n}$

    Nonparametric likelihood is 
    $$
    \prod_{i=1}^{n}[F(y_i|x_i)-F(y_i^-|x_i)]
    $$
    where $F(y_i^-|x_i)=\lim_{t\rightarrow y_i^{-}F(t|x_i)}$.

    Using the right continuity of CDF, the nonparametric likelihood can be derived by replacing $y_i^-$ in  $F(y_i^-|x_i)$ with the next smallest anchor point.

    
