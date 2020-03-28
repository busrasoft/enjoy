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
<p> --step'ten sonra kaç işlemi geri almak istersen o kadar değer yazabilirsin. </p>
php artisan migrate:rollback --step=2 

<h1>Migrate: reset komutu, uygulamanızın tüm database işlemlerini geri alır ve veriler silinir:</h1>
php artisan migrate:reset

<h1>Migrate: refresh komutu tüm database işlemlerinizi geri alır ve ardından migrate komutunu yürütür.</h1>
php artisan migrate:refresh

<h1>Veritabanını yenileyin ve tüm veritabanı verilerini yükleyin</h1>
php artisan migrate:refresh --seed

<h>Modifier Database Sütun Düzenleyiciler </h1>
->nullable();  bu sütun boş olabilir.
->unsigned(); bu sütun negatif olamaz. INTEGER olarak ayarlandı.
->after('column'); belirli bir sütundan sonra oluşturulsun. 
->autoIncrement(); otomatik artış
->unique(); benzersiz olmalı email için kullanılır.
$table->string('email')->unique();
$table->unique('email');

<h1>Seeder Dosyası Create Oluşturma</h1>
php artisan make:seeder UsersTableSeeder

Run : Çalıştırmak için örnek kodlar:

 DB::table('users')->insert([
            'name' => Str::random(10),
            'email' => Str::random(10).'@gmail.com',
            'password' => Hash::make('password'),
        ]);
Bu kodları yazdıktan sonra DatabaseSeader.php dosyasının içerisinde run() fonksiyonuna class adını 

 public function run()
    {
        // $this->call(UsersTableSeeder::class);
    }