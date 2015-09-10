####################
# bulid base nginx #
####################
FROM ubuntu:12.04
#writer Rmao
MAINTAINER Rmao
#copy sources to /etc/apt/sources.list
COPY sources.list /etc/apt/sources.list
#update sources
RUN apt-get update
#install nginx
RUN apt-get install -y nginx && \
    rm -rf /var/lib/apt/lists/*

#rm nginx.conf
#RUN mv /etc/nginx/nginx.conf /etc/nginx/nginx.conf.bak
#cp new nginx.conf
#COPY nginx.conf /etc/nginx/nginx.conf
# forward request and error logs to docker log collector
RUN ln -sf /dev/stdout /var/log/nginx/access.log
RUN ln -sf /dev/stderr /var/log/nginx/error.log
#use 80 and 443 port
EXPOSE 80
#set volume
#VOLUME ["/var/www/html"]
#run nginx server
CMD ["nginx", "-g", "daemon off;"]
