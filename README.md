<h1> Migration Dosyası Oluşturma Komutu:  </h1>

php artisan make:migration create_users_table

<h1>Yeni bir tablo oluşturarak migration oluşturma</h1>
php artisan make:migration create_users_table --create=users

php artisan make:migration add_votes_to_users_table --table=users

<h1> Migration Çalıştırma Komutu:  </h1>
php artisan migrate

<h1> Yanlış Yapılan Migration İşlemini Geri Alma Komutu:  </h1>
<p> En son database tablo işlemini geri almak için geri alma rollback komutunu kullanabilirsiniz. </p>
php artisan migrate:rollback

<h1> Yanlış Yapılan Son 2 Migration İşlemini Geri Alma Komutu:  </h1>
php artisan migrate:rollback --step=2 
<p> --step'ten sonra kaç işlemi geri almak istersen o kadar değer yazabilirsin. </p>