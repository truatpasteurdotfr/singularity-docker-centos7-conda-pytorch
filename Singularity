Bootstrap: docker
From: centos:centos7

%post

# Pasteur setup, ymmv
mkdir -p /selinux /misc /net
mkdir -p /pasteur
mkdir -p /local-storage /mnt/beegfs /baycells/home /baycells/scratch /c6/shared /c6/eb /local/gensoft2 /c6/shared/rpm /Bis/Scratch2 /mnt/beegfs
mkdir -p /c7/shared /c7/scratch /c7/home
# 

# update and requirements for miniconda
yum -y update && \
yum -y install bzip2 && \
yum -y clean all

# install miniconda
curl -qsSLkO https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh \
&& bash Miniconda3-latest-Linux-x86_64.sh -b -p /opt/miniconda3 \
&& rm Miniconda3-latest-Linux-x86_64.sh
/opt/miniconda3/bin/conda update conda && /opt/miniconda3/bin/conda update --all

# https://pytorch.org/get-started/locally/
PATH=/opt/miniconda3/bin:$PATH
export PATH
/opt/miniconda3/bin/conda install pytorch torchvision cudatoolkit=11.3 -c pytorch

%environment
PATH=/opt/miniconda3/bin:$PATH
export PATH
