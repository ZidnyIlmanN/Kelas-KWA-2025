## Christmas Special

## Referensi

[Score Board Injection Challenge](http://localhost:3000/#/score-board?categories=Injection&showDisabledChallenges=false)

## Bukti Pengerjaan

<img width="1920" height="1080" alt="Screenshot 2025-09-11 022431" src="https://github.com/user-attachments/assets/aa3f94df-d2e6-431b-a9c3-7660e0158985" />

### Langkah-langkah

<img width="1919" height="965" alt="Screenshot 2025-09-11 015016" src="https://github.com/user-attachments/assets/297674ad-897e-4a97-81c4-fce1cbe9e006" />

1. Pada challenge ini kita diminta mencari **produk tersembunyi** yang tidak muncul di katalog normal. Jika mencoba `/rest/products/search?q=')`, hasilnya tetap kosong. Hal ini karena item *Christmas Special* memang ada di database, tetapi ditandai dengan flag `deletedAt` (soft-delete). Akibatnya, pencarian `?q=christmas` tidak menampilkan hasil. Untuk itu perlu payload khusus.
   <img width="1919" height="965" alt="Screenshot 2025-09-11 015016" src="https://github.com/user-attachments/assets/92785712-d34d-4f34-8493-a7efc5f7a813" />

2. Untuk menampilkan produk yang disembunyikan, kita bisa menyisipkan payload berikut pada parameter `q`:

   ```
   test')) UNION SELECT * FROM Products WHERE deletedAt IS NOT NULL--
   ```

   <img width="1920" height="1080" alt="Screenshot 2025-09-11 021351" src="https://github.com/user-attachments/assets/960923a7-7b9d-4c51-8aee-bab0e1088b58" />


3. Setelah mengetahui data produk, kita bisa menambahkannya ke dalam bucket dengan melakukan injection pada `id` produk *Christmas Special* (id = 10).
   <img width="1920" height="1080" alt="Screenshot 2025-09-11 022431" src="https://github.com/user-attachments/assets/3e08b4e3-8b8c-4084-9a78-bf740f471b25" />
