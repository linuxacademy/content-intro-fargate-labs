FROM centos:7

# Install dependencies
RUN yum update -y
RUN yum install httpd -y

# Install app1
RUN rm -rf /var/www/html/*
ADD code /var/www/html

# Add logging
RUN ln -sf /dev/stdout /var/log/httpd/access_log
RUN ln -sf /dev/stderr /var/log/httpd/error_log

EXPOSE 80

CMD ["/usr/sbin/httpd", "-D", "FOREGROUND"]
