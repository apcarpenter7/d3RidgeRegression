# Ridge Regression

This repository shows an example of ridge regression solved in the math.js libraray and then visualized with D3.js


## Ridge Regression Overview

Ridge regression adds a penatly term $\lambda$ to perform L2 regularization on vanilla linear regression. 

$$ min  \lVert y - X \beta \rVert_2^2 + \lambda \lVert \beta \rVert_2^2 $$

The L2 pentalty term aims to shrink the coefficients as much as possible to prevent overfitting and multicollinearity. The closed form solution to this equation follows as

$$ \lVert y - X \beta \rVert_2^2 + \lambda \lVert \beta \rVert_2^2  = (y - X \beta)^T (y - X \beta ) + \lambda \beta^2 $$ 

$$ (y - X \beta)^T (y - X \beta) + \lambda \beta^2 = (y^T - \beta^T X^T) (y - X \beta) +  \lambda \beta^2$$ 

$$ (y^T - \beta^T X^T) (y - X \beta) +  \lambda \beta^2 = y^Ty - 2\beta X^ T y + \beta^T X^T X \beta + \lambda \beta^2 $$

Next we take the derivative with respect to $\beta$ and set equal to zero to minimize the objective function

$$ \frac{\partial{}} {\partial{\beta}} = 0 = -2X^Ty + 2\beta X^TX + 2 \lambda \beta$$

$$ \beta (X^TX + \lambda I) = X^Ty $$

$$ \beta = (X^TX + \lambda I)^{-1} X^T y$$


## Code

The code in index.html generates a 5th degree polynomial and adds random noise to the function. Next, it uses the math.js library to solve the closed form solution to the equation above. The initial best fit line is set as $\lambda$ = 0, or ordinary linear regression. The slider under the graph can be used to change the value of $\lambda$. The corresponding changes to the coefficients and best fit line are then dynamically rendered on the page. You can see how ridge regression shrinks higher order coeffieints as $\lambda$ increases. 

Use the following steps to run the code and visualize:

1. Create folder 

    ```
    $ mkdir RidgeRegression
    ```
    
2. Clone the repository 

    ```
    (RidgeRegression) $ git clone https://github.com/apcarpenter7/d3RidgeRegression.git
    ```
    
3. Start a local web server and then open the file index.html. The easiest way to do this is open the folder in VS code, and run with the extension Live Server. Another option is start a local server with python or node.js

   Python
   <br>
    ```
    (RidgeRegression) $ python -m http.server
    ```
    
   Node
   <br>
    ```
    (RidgeRegression) $ npm install -g http-server
    (RidgeRegression) $ http-server
    ```
    
    Finally, copy the local server created by python or node.js and paste into the browsers. Add /index.html to the end and press enter to start webpage. 
    <br>
    <br>
    Examples:
    <br>
    Python:  http://localhost:8000/index.html
             <br>
             <br>
             Node.js: http://10.66.123.212:8080/index.html 





