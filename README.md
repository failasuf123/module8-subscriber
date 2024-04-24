"# module8-publisher" 
### Excercie
1. AMQP (Advanced Message Queuing Protocol) adalah sebuah protokol komunikasi yang      digunakan untuk pertukaran pesan antara aplikasi atau sistem yang berbeda. Protokol ini biasanya digunakan dalam sistem antrian pesan (message queuing) untuk mengatur pengiriman pesan antara komponen-komponen dalam sebuah sistem terdistribusi.

2. Pada contoh guest:guest@localhost:5672, ini mengacu pada URL atau alamat AMQP yang digunakan untuk menghubungkan aplikasi  dengan broker AMQP (dalam tutorial ini RabbitMQ).

"guest:guest" adalah username dan password yang digunakan untuk koneksi ke broker AMQP. Ini adalah nilai default yang sering digunakan untuk pengembangan dan pengujian.
"localhost:5672" menunjukkan host dan port tempat broker AMQP berjalan. "localhost" mengarah ke komputer lokal di mana  RabbitMQ dijalankan, sedangkan "5672" adalah port default untuk koneksi AMQP.
Dalam kode pada tutorial ini terdapat penggunaan CrosstownBus::new_queue_listener("amqp://guest:guest@localhost:5672".to_owned()), di mana kita membuat listener untuk mendengarkan antrian pesan dengan URL AMQP yang sesuai. Kemudian kita menggunakan CrosstownBus untuk mengirim dan menerima pesan menggunakan protokol AMQP.