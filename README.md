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

<ul>
  <li>->nullable();  bu sütun boş olabilir.</li>
  <li>->nullable();  bu sütun boş olabilir.</li>
  <li>->unsigned(); bu sütun negatif olamaz. INTEGER olarak ayarlandı.</li>
  <li>->after('column'); belirli bir sütundan sonra oluşturulsun.</li>
  <li>->autoIncrement(); otomatik artış</li>
  <li>->unique(); benzersiz olmalı email için kullanılır.</li>
  <dt>$table->string('email')->unique();</dt>
  <dt>$table->unique('email');</dt>
</ul>
<h1>Seeder Dosyası Create Oluşturma</h1>
<dt>php artisan make:seeder UsersTableSeeder</dt>

<dt>Run : Çalıştırmak için örnek kodlar:</dt>

 <dt>DB::table('users')->insert([</dt>
            <dt>'name' => Str::random(10),</dt>
            <dt>'email' => Str::random(10).'@gmail.com',</dt>
            <dt>'password' => Hash::make('password'),</dt>
        <dt>]);</dt>
<dt>Bu kodları yazdıktan sonra DatabaseSeader.php dosyasının içerisinde run() fonksiyonuna class adını</dt> 

 <dt>public function run()</dt>
    <dt>{</dt>
       <dt> // $this->call(UsersTableSeeder::class);</dt>
   <dt> }</dt>