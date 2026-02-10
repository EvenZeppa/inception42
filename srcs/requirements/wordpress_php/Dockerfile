FROM debian:trixie

RUN apt update && \
	apt install -y \
	php8.4-fpm \
	&& rm -rf /var/lib/apt/lists/*

COPY ./conf/www.conf /etc/php/8.4/fpm/pool.d/www.conf

CMD ["php-fpm8.4", "-F"]