FROM heasoft:latest

ARG version=4.14
ARG heasoft_version=6.31
ARG headata=/home/idies/workspace/headata/FTP
ARG user=idies
ARG pythonenv=ciao



## ------------------------------ ##
## Install the ciao conda package ##
## remove xspec modelData and make a link
USER $user
# note that numpy=1.24 breaks some tasks, so force 1.23 until ciao fixes it.
RUN mamba create -n ${pythonenv} -y -c conda-forge \
  -c https://cxc.cfa.harvard.edu/conda/ciao \
  ciao=${version} sherpa ciao-contrib marx numpy=1.23 \
  \
 && conda clean -y --all \
 && rm -rf /home/$user/miniconda3/pkgs/* \
 && rm -rf /home/${user}/miniconda3/envs/${pythonenv}/spectral/modelData \
 && ln -sf $headata/software/lheasoft/lheasoft${heasoft_version}/heasoft-${heasoft_version}/Xspec/src/spectral/modelData /home/${user}/miniconda3/envs/${pythonenv}/spectral/modelData \
 \
 && rm -rf /home/${user}/miniconda3/envs/${pythonenv}/CALDB \
 && ln -s ${headata}/caldb /home/${user}/miniconda3/envs/${pythonenv}/CALDB
## ------------------------------ ##


# reset 
WORKDIR /home/${user}
