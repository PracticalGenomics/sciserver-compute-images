## Develop a Bioconductor 3.X image

1. Start with `sciserver-base` based off of Ubuntu 22.04 (e.g. `docker pull containers.repo.sciserver.org/sciserver-base:3.0`)
1. Build `sciserver-rstudio` with R, RStudio, tidyverse (e.g. `FROM sciserver-rstudio:2023.06.2-561`)
1. Build `bioconductor` with BiocManager and learnR (e.g. `FROM bioconductor:3.17`) and publish image as "Bioconductor 3.17 (RStudio)"
1. Build `singlecell` with bioc-intro, RNA-seq, OSCA and publish image as "Bioconductor 3.17 (RStudio/single cell)"

## Test RStudio Server

Access via `http://localhost:8888` after running

```
docker run -ti -p 8888:8888 singlecell:3.17 bash /opt/startup.sh
```
