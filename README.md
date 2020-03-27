<h1> Migration Dosyası Oluşturma Komutu:  </h1>

php artisan make:migration create_users_table

<h1>Yeni bir tablo oluşturarak migration oluşturma</h1>
php artisan make:migration create_users_table --create=users

php artisan make:migration add_votes_to_users_table --table=users

<h1> Migration Çalıştırma Komutu:  </h1>
php artisan migrate
