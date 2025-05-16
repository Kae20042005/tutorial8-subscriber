# Module 09 Reflection

## Understanding subscriber and message broker

1. AMQP merupakan singkatan dari Advanced Message Queuing Protocol. AMQP merupakan protokol standar terbuka untuk 
   middleware berbasis pesan. Dengan protokol ni, sistem yang berbeda dapat saling berkomunikasi dengan mengirim pesan
   secara asinkron dan independen dari platform
2. Arti dari guest:guest@localhost:5672. guest pertama merupakan username untuk autentikasi, kemudian username kedua
   merupakan password yang sesuai dengan password, localhost:6572 menandakan bahwa server berjalan dalam mesin lokal pada
   port 5672.

## Simulation slow subscriber

![slow subscriber chart screenshot](/assets/images/rabbitmq_queue_chart.png)
Ketika publisher di run secara berulang, messages yang masih menunggu delay akan ditaro pada message queue, sehingga muncul
pada grafik queue messages dengan angka tertinggi pada 12 message, ini berarti ada 12 message yang sempat masuk ke
antrian sebelum akhirnya dikirim ke subscriber

## Running at least three subscribers

![multiple subscriber console screenshot](/assets/images/multiple_subscriber_console.png)
![multiple subscriber chart screenshot](/assets/images/rabbitmq_queue_chart_multiple.png)
Ketika 3 subscriber dijalankan secara bersamaan dapat terlihat bahwa pesan yang didapat dibagi menjadi 3 untuk pengerjaannya.
Dengan ini, proses penerimaan message menjadi lebih cepat, dengan terlihatnya grafik message queue yang menurun lebih cepat.

## Reflection

1. Pada subscriber dapat menambahkan pencatatan waktu mulai dan selesai agar dapat dilakukan profiling performa
2. Pada publisher dapat menggunakan lup untuk pembuatan messagenya sehingga memiliki scalability yang lebih baik