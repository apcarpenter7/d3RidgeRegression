# Ridge Regression

## This repository shows an example of ridge regression visualized with D3.js

Ridge regression adds a penatly term $\lambda$ to perform L2 regularization on vanilla linear regression. 

$$ min ;/;/ \lVert y - X \beta \rVert_2^2 + \lambda \lVert \beta \rVert_2^2 $$

The L2 pentalty term aims to shrink the coefficients as much as possible to prevent overfitting and multicollinearity. The closed form solution to this equation follows as

$$ \lVert y - X \beta \rVert_2^2 + \lambda \lVert \beta \rVert_2^2  = (y - X \beta)^T (y - X \beta ) + \lambda \beta^2 $$ <br>

$$ (y - X \beta)^T (y - X \beta) + \lambda \beta^2 = (y^T - \beta^T X^T) (y - X \beta) +  \lambda \beta^2$$ <br>

$$ (y^T - \beta^T X^T) (y - X \beta) +  \lambda \beta^2 = y^Ty - 2\beta X^ T y + B^T X^T X \beta + \lambda \beta^2 $$



$$(X^TX + \lambda I)^{-1} X^T y$$




