# Modul 8 - Publisher
**Samuel Farrel Bagasputra - 2206826614 - Adpro C**
<br><br>

## How many data your publisher program will send to the message broker in one run?
Pada program publisher ini, dalam satu run, program mengirimkan sebanyak 5 `UserCreatedEventMessage` ke message broker karena terdapat 5 kali pemanggilan method `publish_event` dimana setiap pemanggilan akan melakukan pengiriman sebanyak 1 kali.<br><br>

## The url of: `amqp://guest:guest@localhost:5672` is the same as in the subscriber program, what does it mean?
Dengan url yang digunakan sama oleh subscriber dan publisher, berarti mereka memiliki akses AMQP yang sama sehingga kedua program berkomunikasi melalui broker yang sama.<br><br>

## RabbitMQ as message broker
### Running RabbitMQ as message broker
<img src = "images/runningRabbitMQ.png"> <br>

### Sending and Processing Event
<img src = "images/SendingAndProcessing.png">

Pada saat kita menjalankan `cargo run` pada `publisher` dan `subscriber`, maka publisher akan mengirimkan data ke message broker (RabbitMQ) dan message broker (RabbitMQ) akan meneruskannya ke subscriber. Subscriber akan menerima data tersebut dan melakukan proses sesuai dengan data yang diterima. Proses tersebut dapat kita lihat dari screenshot console diatas.<br>

### Monitoring Chart Based on Publisher
<img src = "images/MonitoringChart.png">

Saat menjalankan percobaan, semakin sering saya `cargo run` publisher, spike akan semakin tinggi dan sebaliknya spike akan rendah/datar ketika saya tidak menjalankan publisher untuk beberapa waktu. Jadi, spike ini menunjukkan peningkatan message rate yang terjadi karena publisher mengirimkan data ke message broker.<br>
