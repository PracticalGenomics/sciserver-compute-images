FROM sciserver-rstudio:2023.06.2-561

RUN apt-get update \
    && apt-get install -y \
        libgdal-dev \
        libproj-dev \
        libgeos-dev \
    && rm -rf /var/lib/apt/lists/*

USER idies

WORKDIR /home/idies

RUN Rscript -e "install.packages('BiocManager'); BiocManager::install(version = '3.17')"
RUN Rscript -e "install.packages('learnr')"

USER root
