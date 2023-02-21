FROM docker.io/centos:8.4.2105

LABEL devops.grababyte.image.authors="GrabAByte"

ARG USER=centos
ENV ID=1000

RUN \
  sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-* && \
  sed -i 's|#baseurl=http://mirror.centos.org|baseurl=https://vault.centos.org|g' /etc/yum.repos.d/CentOS-* && \
  dnf install -y \
    gcc-8.5.0 \
    git-2.27.0 \
    jq-1.5 \
    nodejs-10.24.0 \
    npm-6.14.11 \
    openssh-8.0p1 \
    python36-3.6.8 \
    ruby-2.5.9 \
    sudo-1.8.29 \
    unzip-6.0 \
    zip-3.0 && \
  dnf clean all && \
  pip3 install --no-cache-dir --upgrade \
    pip==21.3.1 \
    setuptools==59.6.0 && \
  groupadd -g "${ID}" "${USER}" && \
  useradd -l -m -u "${ID}" -g "${USER}" "${USER}" && \
  echo "${USER} ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers

USER "${USER}"
