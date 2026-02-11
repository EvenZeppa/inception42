FROM debian:trixie

RUN apt update && \
	apt install -y \
	php8.4-fpm \
	php8.4-mysqli \
	php8.4-curl \
	php8.4-dom \
	php8.4-exif \
	php8.4-fileinfo \
	php8.4-mbstring \
	php8.4-xml \
	php8.4-zip \
	wget \
	mariadb-client \
	netcat-traditional \
	&& rm -rf /var/lib/apt/lists/*

RUN wget https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar \
	&& chmod +x wp-cli.phar \
	&& mv wp-cli.phar /usr/local/bin/wp

COPY ./conf/www.conf /etc/php/8.4/fpm/pool.d/www.conf

COPY ./tools/setup.sh /usr/local/bin/
RUN chmod +x /usr/local/bin/setup.sh

WORKDIR /var/www/ezeppa.42.fr/html

#ENTRYPOINT ["/usr/local/bin/setup.sh"]

CMD ["php-fpm8.4", "-F"]