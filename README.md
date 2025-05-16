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