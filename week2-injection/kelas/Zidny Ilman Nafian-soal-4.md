# Database Schema
Dalam challenge ini, tugas kita adalah memperoleh seluruh skema database dengan memanfaatkan teknik SQL Injection, sehingga detail struktur sensitif dari database dapat diungkap.

## Referensi

* [Juice Shop Score Board](https://juice-shop.herokuapp.com/#/score-board?categories=Injection&showDisabledChallenges=false)
* [OWASP Juice Shop Companion Guide](https://pwning.owasp-juice.shop/companion-guide/latest/appendix/solutions.html#_retrieve_a_list_of_all_user_credentials_via_sql_injection)

## Bukti Pengerjaan

<img width="1920" height="1080" alt="Screenshot 2025-09-11 011207" src="https://github.com/user-attachments/assets/fe7d8f86-ce4b-4cb1-9382-23c2cd44ffc6" />

### Langkah-langkah
Langkah awal yang dilakukan yaitu menemukan parameter pada aplikasi yang rawan terhadap SQL Injection. Pada kasus ini, fitur pencarian produk di `https://juice-shop.herokuapp.com/#/search?q=Apple` dapat dimanfaatkan karena parameter `q` terbukti memiliki celah.

<img width="439" height="203" alt="image" src="https://github.com/user-attachments/assets/8273b4b3-2f8f-463c-acdd-ad9d71799ddf" />

1. Pada challenge ini diberikan petunjuk untuk mencari endpoint yang memiliki fungsi **filter/search**. Untuk itu, digunakan Burp Suite agar bisa menganalisis request yang lewat.
   <img width="1920" height="1080" alt="Screenshot 2025-09-11 011223" src="https://github.com/user-attachments/assets/a23c9a4b-6003-4cac-9655-e928d2641f33" />

2. Dari hasil capture, ditemukan request `GET /rest/products/search?q= HTTP/1.1`. Parameter `q` di sini adalah query pencarian yang bisa dimanipulasi untuk menguji SQL Injection.

3. Selanjutnya request dikirim ke **Repeater** untuk melakukan injection. Dari percobaan, jumlah kolom terdeteksi sebanyak 9. Payload yang digunakan:

   ```
   /rest/products/search?q=')) UNION SELECT 1,2,3,4,5,6,7,8,9 FROM sqlite_schema--
   ```

   <img width="1920" height="1080" alt="Screenshot 2025-09-11 011207" src="https://github.com/user-attachments/assets/80cff655-848c-45f7-8b09-3496f638a8d8" />
   <img width="1919" height="862" alt="image" src="https://github.com/user-attachments/assets/92eac987-3bdf-42ad-b424-7a88217740d5" />


4. Agar lebih mudah dibaca, response diformat dari **raw** ke **parsed** sehingga struktur database dari Juice Shop dapat terlihat jelas.
