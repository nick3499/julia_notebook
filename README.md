# Jupyter `notebook` in Julia
With Julia interpreter running in Bash, execute the following: which imports `IJulia`, sets working directory, opens Jupyter notebook Dashboard in a browser window:

	using IJulia
	notebook(dir="/home/foo/Documents/jl")

The following is executed internally, *for example*:

	Process(setenv(`/root/.julia/v0.5/Conda/deps/usr/bin/jupyter notebook`; dir="/home/foo/Documents/JL"), ProcessExited(0))

# conditional execution

To execute a conditional statement, use `if`, `else` and `else`:

	weather = "sunny"

	if weather == "sunny" println("Enjoy the sunshine.")
	println("Put on your sunglasses.")
	elseif name == "cloudy" println("Relax in the shade.")
	else println("Sleeping.")  # same line: 'else', 'println'
	end

# iteration
To execute a *for loop*, use `for()` function to iterate through start/finish values, *for example*:

	for i in 1:3 println("i = $i ") end

Ref. [For loops and iteration](https://en.wikibooks.org/wiki/Introducing_Julia/Controlling_the_flow#For_loops_and_iteration)

# `DataFrames` package
Add `DataFrames` package to Julia:

	Pkg.add("DataFrames")

First import `DataFrames` package, then execute `DataFrame()` function:

	using DataFrames
	df = DataFrame(column_one=["Row 1", "Row 2"], column_two=[100, 200])

# `Plots` package
Add `Plots` package to Julia:

	Pkg.add("Plots")

First import `Plots` package, then execute `plot()` function to output sine wave display:

	using Plots
	plot(sin, -2pi, pi, label="sine function")

Julia `Plot.jl` couples *plotly-latest.min.js* to the `plot()` function. *For example* in the `.ipynb` file, the following executes internally:

	define('plotly', function(require, exports, module)...

# `nbconvert` to `html`
	ipython3 nbconvert --to html dataframe.ipynb

# `QuantEcon` library
Install the `QuantEcon` library:

    Pkg.add("QuantEcon")

Import `tauchen` function from the `QuantEcon` library, then calculate *stochastic matrix*:

    using QuantEcon: tauchen
    tauchen(4, 0.9, 1.0)

[![ko-fi](https://www.ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/R6R72LISM)
