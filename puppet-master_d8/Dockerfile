FROM debian:jessie
MAINTAINER Simon Hönscheid "simon@hoenscheid-itconsulting.com"
ENV HOSTNAME puppet
ENV DEBIAN_FRONTEND=noninteractive
EXPOSE 8140 8081

RUN apt-get update
RUN apt-get install -y apt-utils 
RUN apt-get install -y wget openssh-server bash-completion git vim
RUN cd /tmp && wget https://apt.puppetlabs.com/puppetlabs-release-pc1-jessie.deb && dpkg -i puppetlabs-release-pc1-jessie.deb
RUN apt-get update
RUN apt-get install -y puppetserver
RUN echo "EDITOR=vim" > /root/.bashrc; echo "PATH=\"/opt/puppetlabs/bin/:$PATH\"" >> /root/.bashrc; echo "# export LANG=de_DE@euro" >> /root/.bashrc; echo "umask 022" >> /root/.bashrc; echo "alias ll='ls -lah --color=auto'" >> /root/.bashrc; echo "alias grep='grep --color=auto'" >> /root/.bashrc; echo "alias rm='rm -r'" >> /root/.bashrc; echo "PS1='\[\033[01;31m\]\u\[\033[01;34m\]@\[\033[01;32m\]\h\[\033[01;34m\]:[\W] \$\[\033[00m\] '" >> /root/.bashrc; echo ". /etc/bash_completion" >> /root/.bashrc
RUN cd /etc/puppetlabs/code/environments/production && rm -rf hieradata manifests modules && mv environment.conf /tmp/ && git clone https://github.com/SimonHoenscheid/puppet4-workshop.git . && mv /tmp/environment.conf . && git pull && git status
