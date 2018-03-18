# Minimal alpine R install
# Taken from conoria/alpine-r and juypter docker-stacks

FROM alpine:edge

MAINTAINER Conor I. Anderson <conor@conr.ca>

RUN apk add --no-cache R R-dev R-doc curl libressl-dev curl-dev libxml2-dev gcc g++ git coreutils bash ncurses

RUN git clone https://github.com/ropensci/git2r.git &&\
          R CMD INSTALL --configure-args="--with-libssl-include=/usr/lib/" git2r &&\
            rm -rf git2r /tmp/*

RUN R -q -e "install.packages(c('devtools', 'covr', 'roxygen2', 'testthat'), repos = 'https://cloud.r-project.org/')" &&\
    rm -rf /tmp/*

# From Juypter    
RUN R -q -e "install.packages(c('plyr', 'tidyverse'), repos = 'https://cloud.r-project.org/')" &&\
    rm -rf /tmp/*

# ERROR: compilation failed for package ‘httpuv’    
RUN R -q -e "install.packages(c('shiny', 'rmarkdown', 'forecast'), repos = 'https://cloud.r-project.org/')" &&\
    rm -rf /tmp/*
# packages ‘rsqlite’, ‘rcurl’ are not available (for R version 3.4.3)
RUN R -q -e "install.packages(c('rsqlite', 'reshape2', 'nycflights13', 'caret', 'rcurl'), repos = 'https://cloud.r-project.org/')" &&\
    rm -rf /tmp/*
RUN R -q -e "install.packages(c('crayon', 'randomForest', 'htmltools'), repos = 'https://cloud.r-project.org/')" &&\
    rm -rf /tmp/*
# sparklyr fails with httpuv not building
#RUN R -q -e "install.packages(c('sparklyr'), repos = 'https://cloud.r-project.org/')" &&\
#    rm -rf /tmp/*
RUN R -q -e "install.packages(c('dplyr', 'lubridate', 'igraph', 'knitr', 'readr', 'ggplot2', 'stringr'), repos = 'https://cloud.r-project.org/')" &&\
    rm -rf /tmp/*
RUN R -q -e "install.packages(c('dplyr'), repos = 'https://cloud.r-project.org/')" &&\
    rm -rf /tmp/*

CMD ["R"]
