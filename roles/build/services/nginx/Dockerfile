FROM nginx:1.20-alpine

WORKDIR /etc/nginx

COPY ./conf/nginx.conf /etc/nginx/nginx.conf
COPY ./conf/dhparam.pem /etc/nginx/dhparam.pem

ADD ./sites/ /etc/nginx/sites-enabled
ADD ./certs/ /etc/nginx/ssl

EXPOSE 80 443

CMD ["nginx", "-g", "daemon off;"]
