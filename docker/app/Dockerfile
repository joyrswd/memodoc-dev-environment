# Dockerfile for 'app' service

# PHP 8 FPMをベースにする
FROM php:8-fpm

# 必要なライブラリをインストール
RUN apt-get update && apt-get install -y \
    zip \
    unzip \
    git \
    curl \
    libpng-dev \
    libonig-dev \
    libxml2-dev \
    libzip-dev \
    libfreetype6-dev \
    libjpeg62-turbo-dev \
    libmcrypt-dev \
    libwebp-dev \
    libjpeg-dev \
    libpng-dev \
    libxpm-dev \
    cron \
    vim \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# PHPの拡張機能をインストール
RUN docker-php-ext-install pdo_mysql mbstring exif pcntl bcmath gd zip opcache sockets calendar intl soap mysqli

# Redis拡張をインストール
RUN pecl install redis && docker-php-ext-enable redis

# Composerをインストール
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# ワーキングディレクトリを設定
WORKDIR /var/www/html

# cronを起動させる
RUN service cron start

# ポート9000を公開
EXPOSE 9000