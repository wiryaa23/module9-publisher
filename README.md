# QUESTION

- How much data your publisher program will send to the message broker in one run?
> Program publisher akan mengirim 5 data pesan ke message broker RabbitMQ dalam satu kali dijalankan. Tiap pesan berisi informasi berupa user_id an user_name yang dikemas dalam bentuk struct `UserCreatedEventMessage`, dan dikirim ke queue `user_created`.

- The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?
> URL `amqp://guest:guest@localhost:5672` di program publisher sama dengan yang di program subscriber, yang menunjukkan bahwa keduanya berkomunikasi dengan terhubung ke broker RabbitMQ yang sama di komputer lokal. Karena menggunakan alamat yang sama, publisher dapat mengirim pesan dan subscriber dapat menerima pesan dari queue yang sama melalui broker tersebut.
> - guest pertama merupakan username yang digunakan untuk login ke broker.
> - guest kedua merupakan password untuk username tersebut.
> - localhost menunjukkan bahwa server RabbitMQ berjalan di computer lokal.
> - 5672 merupakan port default yang digunakan oleh protokol AMQP.

- Tampilan ketika menjalankan RabbitMQ adalah sebagai berikut.
![RabbitMQ](images/RabbitMQ.png)

- Sending and Processing Event

Publisher:
![Sending_Publisher](images/Sending_Publisher.png)
Subscriber:
![Sending_Subscriber](images/Sending_Subscriber.png)
  Kita dapat melihat dari gambar bahwa ketika publisher mengirimkan data, maka subscriber akan menerima data yang dikirimkan. Karena saya menjalankan proses sebanyak dua kali, maka subscriber menerima sebanyak 10 event dari publisher.

- Monitoring Chart Based On Publisher
![Chart_RabbitMQ](images/Chart_RabbitMQ.png)
  Grafik ungu pada message rates menunjukkan lonjakan karena publisher dijalankan dan mengirim pesan ke broker, yang merupakan konfirmasi dari subscriber bahwa pesan berhasil diterima dan diproses.