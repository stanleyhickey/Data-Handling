# Graham-scan
This Graham scan algorithm can be used to find the convex hull of a set of data points!

In this project, I create my own version of the Graham scan algorithm for computing the convex hull of a set of data points. This code takes the form of a function get_hull() which takes as argument a  2×𝑁 array of point coordinate pairs  (𝑥,𝑦) and returns the subset of those points which would make up the vertices of the convex hull.

To ensure the code completes this task successfully, I test that it can complete the following tasks:
1. The get_hull() function returns a variable of the correct type.
2. The returned variable has correct size and shape.
3. The correct subset of initial points are given in the hull.
4. The function returns the trivial hull of 3 points.

The Code for this can be seen in the Graham-scan file

# Data Interpolation


Interpolation is valuable for approximating complex curves using a set of given data points. The resulting function, which fits these known data points, can be used to estimate values at new points within the same interval. This project contains 3 parts:

1. The establishment of a function which performs piecewise Lagrange polynomial interpolation;
2. An interactive plot wherein the user can vary the degree of a non-piecewise interpolation;
3. Making use of the interpolation functions to extrapolate missing information from a data txt file about water level in a wave tank.

## Part 1 

Interpolation like this is used often on data sets where there are missing data points which need to be estimated. The code in part 1 creates a function that does exactly that. The reason we use the piecewise polynomial rather than a higher degree single polynomial is to avoid Runge’s Phenomenon which can add large errors to high degree polynomials. This is created this as a callable function so it can be easily accessed throughout the rest of the project instead of having to repeat the code whenever it is used. The created function is then tested on f(x) = e^x cos(10x). The interpolation is printed along with its error from the actual function.

## Part 2 

Here I create an interactive plot that allows the user to vary the degree of the Lagrangian polynomial for selected knots.
This interactive feature is particularly useful for illustrating and understanding the method of Lagrange Polynomials. It allows users to visually and practically explore how Lagrange Polynomials are constructed and how they interpolate a given set of data points. The code makes use of the interactive features from the ipywidgets package.

## Part 3


Part 3 of the project involves applying the previous work to experimental data. This section addresses missing data points in the dataset provided (wave_data1.txt) and uses interpolation to generate a new set of uniformly spaced data. This approach directly demonstrates the utility of interpolation by estimating values where data is missing and comparing how different interpolation methods address these gaps.

The investigation includes piecewise cubic interpolation and cubic spline interpolation. For piecewise cubic interpolation, the function from Part 1 is used to fit a cubic polynomial to consecutive sets of knots, combining these to form a polynomial for the entire dataset. Cubic spline interpolation works similarly but ensures that the second derivatives are continuous, resulting in a smoother graph.

