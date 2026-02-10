FROM debian:trixie

RUN apt update && \
	apt install -y \
	nginx \
	openssl \
	&& rm -rf /var/lib/apt/lists/*

COPY ./conf/ezeppa.42.fr.conf /etc/nginx/sites-available/

RUN ln -s /etc/nginx/sites-available/ezeppa.42.fr.conf /etc/nginx/sites-enabled

RUN mkdir -p /etc/nginx/ssl \
	&& openssl req -x509 -nodes -days 365 -newkey rsa:2048 \
	-keyout /etc/nginx/ssl/ezeppa.42.fr.key \
	-out /etc/nginx/ssl/ezeppa.42.fr.crt \
	-subj "/C=FR/L=Paris/O=42/OU=ezeppa/CN=ezeppa.42.fr"

CMD ["nginx", "-g", "daemon off;"]