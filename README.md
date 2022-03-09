########### DESCRIPTION ############

Each directory has two databases `O.csv` (original) and `R.csv` (Reintroduce), we perform the previously mentioned regression on O.csv determining a *baseline regression value* for each coefficient, which can be found in `database/Baseline_regression_values.csv`

The database `data.csv` has been created by reintroducing each datapoint from R into O one at a time, and then performing the regression. That is to say, each data point in the file `data.csv` describes a regression performed on a database with one point differing each time.


########### PROBLEM ############

- For each coefficient of the regression, we choose a value $`x_i`$, such that, any point which deviates from the *baseline regression value* by $`x_i`$ is considered a deviation point.
- Once we have seperated `data.csv` into `deviation` and `no deviation` sets, we redo the regression on: 

	* original database + deviation
	* original database + no deviation

The objective is to minimize the cardinality of the deviation set, while maximizing the relative magnitude between the $`\alpha_R`$

- Determine a loss function which characterizes this goal.
- Find the set of nine values (one for each coefficient of the regression) which minimizes this loss function.

Bear in mind that the loss function you come up with may have many local minimums. We are looking for the global minimum.
