# NoSQL Manipulation

## Referensi

[Juice Shop Score Board – Injection](https://juice-shop.herokuapp.com/#/score-board?categories=Injection&showDisabledChallenges=false)

## Bukti Pengerjaan

![nosql](../../img/nosql_manipulation/done.png)

### Langkah-langkah

<img width="439" height="186" alt="image" src="https://github.com/user-attachments/assets/0eeacc86-5851-411c-b9a5-8d1da43712f4" />

1. Pada challenge ini kita diminta untuk melakukan **update review produk** secara serentak. Untuk melakukannya, kita bisa memanfaatkan Burp Suite sebagai media intercept dan modifikasi request.
   ![nosql](../../img/nosql_manipulation/comment.png)

2. Saat form komentar dikirim, request berhasil ditangkap oleh Burp Suite.
   ![nosql](../../img/nosql_manipulation/burp.png)

3. Dari request tersebut terlihat ada field `message` serta header **Bearer Authentication** yang ikut dikirim.
   ![nosql](../../img/nosql_manipulation/edit.png)

4. Request lalu dikirim ke **Repeater**. Di bagian **Inspector**, metode awal `PUT` diubah menjadi `PATCH`. Selanjutnya, field `message` dimodifikasi dan parameter `productId` dihapus, sesuai payload yang diperlukan.
