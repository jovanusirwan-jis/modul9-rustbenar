a. How much data will the publisher program send to the message broker in one run?

Program publisher tersebut akan mengirim 5 message/event ke message broker (RabbitMQ).

Hal ini karena terdapat 5 pemanggilan:

p.publish_event(...)

yaitu untuk data:

Amir Budi Cica Dira Emir

Jadi dalam satu kali program dijalankan:

Total message sent = 5 messages

Semua message tersebut dikirim ke event/queue "user_created".

b. The URL “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?

Itu berarti publisher dan subscriber terhubung ke RabbitMQ server yang sama.

Penjelasannya:

amqp://guest:guest@localhost:5672

memiliki arti:

amqp:// → menggunakan protokol AMQP guest pertama → username guest kedua → password localhost → server RabbitMQ berjalan di komputer yang sama 5672 → port RabbitMQ

Karena URL pada publisher dan subscriber sama, maka:

publisher mengirim message ke RabbitMQ yang sama, subscriber menerima message dari RabbitMQ yang sama.

Dengan begitu subscriber dapat menerima event yang dikirim publisher.

![Yang run 1 kali aja](<Screenshot 2026-05-12 182625.png>)
![gambar grafik 1 kali aja](<Screenshot 2026-05-12 182801.png>)