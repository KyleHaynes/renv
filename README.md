# renv (UNDER DEVELOPMENT)


## Overview

Create and bind projects to R virtual environments. With `renv`, you can bind
particular R projects to different virtual environments, each containing its own
set of R libraries. This enables a variety of workflows:

1. Projects under active development can use a 'development' set of R packages,
   while projects used more widely in production can use a 'production' set of
   R packages. This way, changes made in the 'development' library won't affect
   other projects.

2. Projects can use their own private library, similar to the
   [Packrat](https://rstudio.github.io/packrat/) model.

3. Projects can more easily share and overlay libraries, so that users can
   build their own R library of packages on top of a 'base' set of packages.
   This is similar to the model already available in R with site libraries and
   user libraries, but this package normalizes and standardizes the model
   across different platforms.

## Usage

Sample API sketched out.

``` r
library(renv)

# create a virtual environment with this configuration
renv_create("my-renv", r_libs = c("base", "dev"))

# activate this virtual environment in the active project
renv_activate("my-renv")

# session restarts; new library paths are loaded; work as usual ...

# deactivate when we're done
renv_deactivate("my-renv")
```
