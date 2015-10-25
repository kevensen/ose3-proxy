# Using CentOS7 Image, create a web proxy for the OSE3 master.
# Version 1

# Pull the rhel image from the local repository
FROM centos:latest
USER root

MAINTAINER Kenneth D. Evensen <kevensen@redhat.com>

# Fix per https://bugzilla.redhat.com/show_bug.cgi?id=1192200 
RUN yum -y install deltarpm yum-utils httpd mod_ssl && yum update; yum clean all; rm -rf /var/cache/yum/*

# Add configuration file
RUN echo "The Web Server is Running" > /var/www/html/index.html
EXPOSE 80
EXPOSE 443
# Start the service
CMD ["-D", "FOREGROUND"]
ENTRYPOINT ["/usr/sbin/httpd"]
