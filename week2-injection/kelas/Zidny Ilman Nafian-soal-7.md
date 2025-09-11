# NoSQL Manipulation
Dalam challenge ini, tugas kita adalah memodifikasi beberapa review produk secara bersamaan. Proses penyelesaiannya dilakukan dengan memanipulasi endpoint `/rest/products/reviews`, di mana tersedia sejumlah parameter yang bisa dimanfaatkan untuk melakukan perubahan.

## Referensi

[Juice Shop Score Board – Injection](https://juice-shop.herokuapp.com/#/score-board?categories=Injection&showDisabledChallenges=false)

## Bukti Pengerjaan

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/97add83a-137b-4702-941a-ca2b6135ecbe" />

### Langkah-langkah

<img width="439" height="186" alt="image" src="https://github.com/user-attachments/assets/0eeacc86-5851-411c-b9a5-8d1da43712f4" />

1. Pada challenge ini kita diminta untuk melakukan **update review produk** secara serentak. Untuk melakukannya, kita bisa memanfaatkan Burp Suite sebagai media intercept dan modifikasi request.
   <img width="1920" height="1080" alt="Screenshot 2025-09-11 130032" src="https://github.com/user-attachments/assets/d5440014-fe76-46b2-b752-6f62fe4fd7e2" />

2. Saat form komentar dikirim, request berhasil ditangkap oleh Burp Suite.
   <img width="1920" height="1080" alt="Screenshot 2025-09-11 123543" src="https://github.com/user-attachments/assets/3c93473b-6482-4ee1-9f64-52956e3cc8f6" />

3. Dari request tersebut terlihat ada field `message` serta header **Bearer Authentication** yang ikut dikirim.
   <img width="1920" height="1080" alt="Screenshot 2025-09-11 123637" src="https://github.com/user-attachments/assets/1226e873-903d-4be0-ad79-1304567dff4d" />

4. Request lalu dikirim ke **Repeater**. Di bagian **Inspector**, metode awal `PUT` diubah menjadi `PATCH`. Selanjutnya, field `message` dimodifikasi dan parameter `productId` dihapus, sesuai payload yang diperlukan.
   <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/b540453b-ba5d-4a23-8eff-e2d85306ec6b" />
