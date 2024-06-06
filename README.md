# Docker for Laravel
Docker compose setup untuk menjalankan framework Laravel.

## Cara menggunakan
### Hanya menggunakan file compose
1. Buatkan file `docker-compose.yml`
2. Copy isi file [docker-compose-client.yml](https://github.com/taufikmaulana405/docker-for-laravel/blob/master/docker-compose-client.yml) dari repository ini ke dalam file `docker-compose.yml` yang telah Anda buat.
3. Jalankan perintah berikut untuk menjalankan kontainer
    ```
    docker compose up -d --build
    ```
4. Akses aplikasi Laravel di http://localhost.

### Clone repository ini
1. Clone repository ini ke dalam mesin lokal Anda.
    ```
    git clone https://github.com/taufikmaulana405/docker-for-laravel.git
    ```
2. Masuk ke direktori proyek.
    ```
    cd docker-for-laravel
    ```
3. Jalankan perintah berikut untuk menjalankan kontainer
    ```
    docker compose up -d --build
    ```
4. Akses Laravel di `http://localhost`
## Cara umum untuk menginstall framework Laravel
1. Gunakan File compose dari repository ini atau clone repository ini
2. Jalankan perintah berikut di terminal untuk membuat container
    ```
    docker compose up -d --build
    ```
3. Masuk ke dalam container
    ```
    docker exec -it php bash
    ```
4. Install laravel
    ```
    composer create-project laravel/laravel .
    ```
5. Ubah Permission
    ```
    chmod -R 777 storage/*
    ```
6. Setting Database
    ```
    cp .env.example .env
    ```
7. Edit file `.env` sesuai dengan konfigurasi database
    ```
    nano .env
    ```
    Sesuaikan konfigurasi database dengan konfigurasi berikut:
    ```sh
    DB_CONNECTION=mysql
    DB_HOST=db
    DB_PORT=3306
    DB_DATABASE=laravel
    DB_USERNAME=root
    DB_PASSWORD=p455w0rd
    ```
8. Generate key di terminal
    ```
    php artisan key:generate
    ```
9. Migrate di terminal
    ```
    php artisan migrate
    ```
10. Seed di terminal
    ```
    php artisan db:seed
    ```
7. Akses aplikasi Laravel di http://localhost
## Konfigurasi
Anda dapat menyesuaikan setup Docker dengan mengubah file `docker-compose.yml`.
### Mengganti versi PHP
Untuk mengganti versi PHP yang digunakan, ubah `PHP_VERSION` pada file `.env`.
### Support Module PHP

| Module PHP                     | PHP 8.3 | PHP 8.2 | PHP 8.1 | PHP 8.0 | PHP 7.4 | PHP 7.3 | PHP 7.2 | PHP 7.1 |
| ------------------------------ | ------- | ------- | ------- | ------- | ------- | ------- | ------- | ------- |
| soap                           |   ✔️   |    ✔️   |   ✔️   |   ✔️    |    ✔️   |   ✔️   |    ✔️   |   ✔️   |
| exif                           |   ✔️   |    ✔️   |   ✔️   |   ✔️    |    ✔️   |   ✔️   |    ✔️   |   ✔️   |
| pcntl                          |   ✔️   |    ✔️   |   ✔️   |   ✔️    |    ✔️   |   ✔️   |    ✔️   |   ✔️   |
| intl                           |   ✔️   |    ✔️   |   ✔️   |   ✔️    |    ✔️   |   ✔️   |    ✔️   |   ✔️   |
| gmp                            |   ✔️   |    ✔️   |   ✔️   |   ✔️    |    ✔️   |   ✔️   |    ✔️   |   ✔️   |
| zip                            |   ✔️   |    ✔️   |   ✔️   |   ✔️    |    ✔️   |   ✔️   |    ✔️   |   ✔️   |
| pdo_mysql                      |   ✔️   |    ✔️   |   ✔️   |   ✔️    |    ✔️   |   ✔️   |    ✔️   |   ✔️   |
| pdo_pgsql                      |   ✔️   |    ✔️   |   ✔️   |   ✔️    |    ✔️   |   ✔️   |    ✔️   |   ✔️   |
| bcmath                         |   ✔️   |    ✔️   |   ✔️   |   ✔️    |    ✔️   |   ✔️   |    ✔️   |   ✔️   |
| redis                          |   ✔️   |    ✔️   |   ✔️   |   ✔️    |    ✔️   |   ✔️   |    ✔️   |   ❌   |
| mongodb                        |   ✔️   |    ✔️   |   ✔️   |   ✔️    |    ❌   |   ❌   |    ❌   |   ❌   |
| imagick                        |   ✔️   |    ✔️   |   ✔️   |   ✔️    |    ✔️   |   ✔️   |    ✔️   |   ✔️   |
| gd                             |   ✔️   |    ✔️   |   ✔️   |   ✔️    |    ✔️   |   ✔️   |    ✔️   |   ✔️   |
| gd --with-freetype --with-jpeg |   ✔️   |    ✔️   |   ✔️   |   ✔️    |    ❌   |   ❌   |    ❌   |   ✔️   |
| xdebug                         |   ✔️   |    ✔️   |   ✔️   |   ✔️    |    ❌   |   ❌   |    ❌   |   ❌   |
| memcached                      |   ✔️   |    ✔️   |   ✔️   |   ✔️    |    ✔️   |   ✔️   |    ✔️   |   ✔️   |
