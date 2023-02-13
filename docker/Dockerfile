FROM docker.io/centos:8.4.2105

LABEL devops.grababyte.image.authors="GrabAByte"

ENV USER centos
ENV UID 1000
ENV GID 1000

RUN \
  sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-* && \
  sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-* && \
  dnf install -y \
    gcc-8.5.0 \
    git-2.27.0 \
    jq-1.5 \
    openssh-8.0p1 \
    sudo-1.8.29 \
    unzip-6.0 \
    zip-3.0 && \
  dnf clean all && \
  groupadd -g "${GID}" "${USER}" && \
  useradd -l -m -u "${UID}" -g "${GID}" "${USER}" && \
  echo "${USER} ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers

USER "${USER}"
