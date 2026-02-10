FROM debian:trixie

RUN apt update && \
	apt install -y \
	mariadb-server \
	&& rm -rf /var/lib/apt/lists/*

CMD [ "sleep", "infinity" ]

#CMD ["mysqld", "--bind-address=0.0.0.0", "--user=mysql"]