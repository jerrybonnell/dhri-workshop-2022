FROM rocker/tidyverse:3.6.3
LABEL maintainer='jerry bonnell'
USER root
COPY . ${HOME}
RUN chown -R ${NB_USER} ${HOME}
USER ${NB_USER}

RUN installGithub.r 

RUN wget https://github.com/jerrybonnell/dhri-workshop-2022/raw/main/DESCRIPTION && R -e "options(repos = list(CRAN = 'http://mran.revolutionanalytics.com/snapshot/2021-09-03/')); devtools::install_deps()"

RUN rm DESCRIPTION.1; exit 0
