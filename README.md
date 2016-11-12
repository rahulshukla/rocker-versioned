[![CircleCI](https://circleci.com/gh/rocker-org/rocker-versioned.svg?style=svg)](https://circleci.com/gh/rocker-org/rocker-versioned) [![license](https://img.shields.io/badge/license-GPLv2-blue.svg)](https://opensource.org/licenses/GPL-2.0)


## Version-stable Rocker images

![rocker](https://avatars0.githubusercontent.com/u/9100160?v=3&s=200)


image            | description                               | badges 
---------------- | ----------------------------------------  | ------ 
r-ver            |  Version-stable base R & src build tools  | [![](https://images.microbadger.com/badges/image/rocker/r-ver.svg)](https://microbadger.com/images/rocker/r-ver) [![](https://img.shields.io/badge/Dockerfile-v3.3.2-blue.svg)](https://github.com/rocker-org/rocker-versioned/blob/master/r-ver/3.3.2/Dockerfile)  [![](https://img.shields.io/badge/Dockerfile-latest-blue.svg)](https://github.com/rocker-org/rocker-versioned/blob/master/r-ver/Dockerfile)
rstudio          |  Adds rstudio                             | [![](https://images.microbadger.com/badges/image/cboettig/rstudio.svg)](https://microbadger.com/) [![](https://img.shields.io/badge/Dockerfile-v3.3.2-blue.svg)](https://github.com/rocker-org/rocker/blob/master/rstudio/3.3.2/Dockerfile)  
tidyverse        |  Adds tidyverse & devtools                | [![](https://images.microbadger.com/badges/image/rocker/tidyverse.svg)](https://microbadger.com/images/rocker/tidyverse) [![](https://img.shields.io/badge/Dockerfile-v3.3.2-blue.svg)](https://github.com/rocker-org/rocker-versioned/blob/master/tidyverse/3.3.2/Dockerfile)  
verse            |  Adds tex & publishing-related packages   | [![](https://images.microbadger.com/badges/image/rocker/verse.svg)](https://microbadger.com/images/rocker/verse) [![](https://img.shields.io/badge/Dockerfile-v3.3.2-blue.svg)](https://github.com/rocker-org/rocker-versioned/blob/master/verse/3.3.2/Dockerfile)  


Notes
-----

- All `rocker-versioned` images build on `debian:jessie`, the current stable release of Debian. (`r-base` and all `:latest`-tagged rocker images build from `debian:testing` and `debian:unstable` repos, which provide more recent versions of libraries and compilers, but the regular updates to these can break dependent packages).
- `rstudio` image builds with rstudio v 1.0.44 by default. This can be customized by specifying the desired version in `--build-arg RSTUIO_VERSION=<VERSION>` if building locally from the `rstudio` Dockerfile.
- `tidyverse:3.3.2` and `verse:3.3.2` images install all packages from an MRAN snapshot of CRAN on the 2016-11-08.  Users can ensure any additional packages they install use this snapshot by passing the argument `repos=getOption('repos')[['MRAN']]` to `install.packages`; otherwise `install.packages` will default to installing the most recent version available from the RStudio CRAN mirror (<https://cran.rstudio.com>)
- Users can set a custom snapshot date for the `tidyverse` image by using `--build-arg BUILD_DATE=<DATE>` if building locally from the `tidyverse` Dockerfile.
- `tidyverse:latest` will install all packages from the latest snapshot of CRAN.  Users can install additional packages from this same snapshot with the same additional argument mentioned above. 

