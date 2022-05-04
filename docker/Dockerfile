FROM docker.io/centos:8.4.2105

LABEL devops.grababyte.image.authors="GrabAByte"

RUN \
  sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-* && \
  sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-* && \
  yum install -y \
    gcc-8.5.0 \
    git-2.27.0 \
    jq-1.5 \
    openssh-8.0p1 \
    sudo-1.8.29 \
    unzip-6.0 \
    zip-3.0 && \
    yum clean all
