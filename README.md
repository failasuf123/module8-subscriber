"# module8-publisher" 
### Excercie
1. AMQP (Advanced Message Queuing Protocol) adalah sebuah protokol komunikasi yang      digunakan untuk pertukaran pesan antara aplikasi atau sistem yang berbeda. Protokol ini biasanya digunakan dalam sistem antrian pesan (message queuing) untuk mengatur pengiriman pesan antara komponen-komponen dalam sebuah sistem terdistribusi.

2. Pada contoh guest:guest@localhost:5672, ini mengacu pada URL atau alamat AMQP yang digunakan untuk menghubungkan aplikasi  dengan broker AMQP (dalam tutorial ini RabbitMQ).

    "guest:guest" adalah username dan password yang digunakan untuk koneksi ke broker AMQP. Ini adalah nilai default yang sering digunakan untuk pengembangan dan pengujian.
    "localhost:5672" menunjukkan host dan port tempat broker AMQP berjalan. "localhost" mengarah ke komputer lokal di mana  RabbitMQ dijalankan, sedangkan "5672" adalah port default untuk koneksi AMQP.
    Dalam kode pada tutorial ini terdapat penggunaan CrosstownBus::new_queue_listener("amqp://guest:guest@localhost:5672".to_owned()), di mana kita membuat listener untuk mendengarkan antrian pesan dengan URL AMQP yang sesuai. Kemudian 
    kita menggunakan CrosstownBus untuk mengirim dan menerima pesan menggunakan protokol AMQP.

### Tutorial Screenshoot
4. Simulating slow subscriber
    ![RabbitMq2 Image](/images/rabbitmq2.png)

    Pada kode di subsciber erdapat penggunaan thread dengan fungsi thread::sleep(ten_millis) di dalam metode handle() yang merupakan bagian dari implementasi MessageHandler untuk UserCreatedHandler. Fungsi thread::sleep() digunakan untuk memberikan jeda atau delay selama 1000 milidetik (1 detik) sebelum pesan berhasil diproses dan dicetak ke konsol.

    Ketika kita menjalankan aplikasi dengan kode tersebut, setiap kali listener mendapatkan pesan baru dengan topik "user_created", handler (UserCreatedHandler) akan dipanggil untuk memproses pesan tersebut. Namun, karena menambahkan jeda 1 detik menggunakan thread::sleep(ten_millis), proses pemrosesan pesan akan membutuhkan waktu lebih lama, terutama jika ada banyak pesan yang harus diproses.


5. multipler publisher
    ![RabbitMq3 Image](/images/rabbitmq3.png)

    Yaa terdapat peningkatan queue nya menjadi 2 dimana saya hanya membuka 3 buah cmd dan terminal untuk melakukan "cargo run" pada publisherr"
