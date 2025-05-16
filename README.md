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