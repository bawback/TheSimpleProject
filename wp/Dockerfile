FROM wordpress:latest

RUN apt-get update && apt-get install -y \
    wget \
    unzip \
 && rm -rf /var/lib/apt/lists/*

RUN wget https://github.com/kevinoid/postgresql-for-wordpress/archive/refs/heads/master.zip -O /tmp/pg4wp.zip \
    && unzip /tmp/pg4wp.zip -d /tmp \
    && mv /tmp/postgresql-for-wordpress-master /usr/src/wordpress/wp-content/plugins/pg4wp \
    && rm /tmp/pg4wp.zip

RUN cp /usr/src/wordpress/wp-content/plugins/pg4wp/db.php /usr/src/wordpress/wp-content

ENV WORDPRESS_DB_HOST=db:5432
ENV WORDPRESS_DB_NAME=wordpress
ENV WORDPRESS_DB_USER=wordpress
ENV WORDPRESS_DB_PASSWORD=wordpress
