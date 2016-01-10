FROM debian:jessie
MAINTAINER Simon Hönscheid "simon@hoenscheid-itconsulting.com"
ENV HOSTNAME puppet-agent

RUN apt-get update
RUN apt-get install -y apt-utils 
RUN apt-get install -y wget openssh-server
RUN wget https://apt.puppetlabs.com/puppetlabs-release-pc1-jessie.deb
RUN dpkg -i puppetlabs-release-pc1-jessie.deb
RUN apt-get update
RUN apt-get install -y  puppet-agent
