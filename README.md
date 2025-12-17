# Euler-Formulas
Contains functions to deploy the Forward Euler's Method, Heun's Method, and Runge-Kutta Method. All you have to do is input your derivative formula, method, step size, initial values, and how many iterations. It will output a chart of all iterations.

# RStudio Version
In the first block, enter in your formula in the theformula variable. The file accepts t and y variables (substitute the x variable with the t variable). For example enter $y'=1+y^2+x$ like this:
  ```{r}
y_derive=function(t,y){
#enter your fomula below in theformula varible!
  theformula=1+y^2+x
  }
```
Note: Make sure to use "^" for exponents, "*" for multiplication, and "/" for division!

Then run the Forward Euler's Method block, Improved Euler's Method Block, and Runge-Kutta (no need to edit these blocks). In the last block add in your function in the order as follows: function(step size, n, initial t, initial y, "table").
- **Step size** refers to $h$
- **n** refers to $t_1$ or $x_1$
- **initial t refers** to $t_0$ or $x_0$
- **initial y** refers to $y_0$

Enter in your desired function like this:
This example includes the stepsize of $h=1$, with the initial point of $y(0)=2$, and estimating from $t=0$ to $t=5$:

Using Euler's Method

    Euler(1,5,0,2,"table")

Output:

    > t	y
    
    > 1	7.000000e+00	

    > 2	5.800000e+01	

    > 3	3.425000e+03	

    > 4	1.173405e+07	

    > 5	1.376880e+14	

Using Improved Euler's or Heun's Method

    Heun(1,5,0,2,"table") 

Output:

    > t	y
    
    > 1	2.750000e+01	

    > 2	3.087305e+05	

    > 3	3.425000e+03	

    > 4	2.128799e+86	

    > 5	Inf	


Using Runge-Kutta Method

    RungeKutta(1,5,0,2,"table")

Output:

    > t kn1 kn2 kn3 kn4 y

    > 1	5.000000e+00	2.175000e+01	1.672656e+02	2.865285e+04	4.841314e+03

    > 2	2.343832e+07	1.374522e+14	4.723279e+27	2.230936e+55	3.718227e+54

    > 3	1.382521e+109	4.778412e+217	Inf	Inf	Inf

    > 4	Inf	Inf	Inf	Inf	Inf

    > 5	Inf	Inf	Inf	Inf Inf


Run the block containing any three of those functions and it should output a table containing the $t$ with the step value added and the $y$ output. 

If you would rather only see the estimated amount output rather than the whole table breakdown, you can redact "table" from the function like this:

Using Euler's Method (no table)

    Euler(1,5,0,2,"") 

Output

    > [1] "Euler"
    > [1] 1 #Stepsize
    >          y 
    > 137688035008975 #Final y

Using Improved Euler's or Heun's Method (no table)

    Heun(1,5,0,2,"")

Output:

    Error #it is due to the final y being out of range for R to handle, 

if this error occurs, try adding "table" the function as opposed to "".

Using Runge-Kutta Method (no table)

    RungeKutta(1,5,0,2,"")

Output:

    > [1] "Runge-Kutta"
    > [1] 1 #Stepsize
    >  y 
    > Inf #Final y

# Jupyter Notebook Version
You will need to edit Block 1a to add in your step size, h, either your final t/x or numbrt of iterations, n, and your initial t/x (initial_t) or initial y (initial_y).
Example:

  h=0.5
  n=10
  initial_t=0
  initial_y=2

If in n you entered a final x/t, you must untag this line:

    iteration=n/h

If n is just the number of iterations you would like, you can ignore Block 1b

Then run the Block 1 and make sure your iteration is accepted and it has your desire number of iterations.

In Block 2, add your derivative formula in theformula variable. It only accepts variables of t and y. If you have x and y, substitute the x for t. For example, you would enter $x^2+y+1$ in theformula like this:

      def y_derive(t,y):
        theformula=x**2+y+1
        return theformula
Note: Make sure you use Python language for math formulas such as "\*" for multiplication, "/" for division, and "\*\*" for exponents. You can represent square roots like this "\*\*(1/2)"

Block 3, you can test your derivative equation, you can enter any number in the varibles t and y. Make sure to get the output of "formula test passed"

For Block 4, untag the method you would like to use, for example if you would like to use Runge-Kutta Method, have your code look like this:

    #func=Euler(h,int(iteration),initial_t,initial_y)
    #func=Heun(h,int(iteration),initial_t,initial_y)
    func=RungeKutta(h,int(iteration),initial_t,initial_y)

Block 5 will give you the results for each iteration and Block 6 will give you the solution.

# Limitations

Keep in mind about the limitation about what minimum and maximum values RStudio and Python/Jupyter Notebook can handle. If your output is "Inf" (in R) or "Overflow" (in Jupyter Notebook), that is because the value is out of range for R to handle.
- From what I have tested, I got R to handle a value up to $1.797693*10^{308}$.
