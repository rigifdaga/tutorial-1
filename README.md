<h1>Refleksi 1</h1>

Saya sudah mengikuti prinsip clean code dalam tutorial ini. Saya sudah memberi nama variabel yang sesuai dengan data yang direpresentasikan. Saya juga sudah memberi nama fungsi yang jelas dengan tujuan masing-masing. Fungsi dalam controller sudah singkat dan hanya memiliki satu tanggung jawab. Fungsi dalam ProductRepository juga tetap menjalankan operasi CRUD untuk entitas produk.

Kode saya tidak banyak mengandung komentar, tapi masih mudah dipahami karena nama fungsi dan variabel yang deskriptif. Kode saya juga sudah rapi dalam hal tata letak dan format. Hal ini membuat kode lebih mudah dimengerti dan dibaca. Saya juga menggunakan struktur objek yang tepat.

Namun, saya juga membuat beberapa kesalahan. Kode saya mengalami error karena menggunakan fitur-fitur Thymeleaf dalam aplikasi Spring Boot. Solusinya adalah dengan menambahkan implementation("org.springframework.boot:spring-boot-starter-thymeleaf") pada build.gradle.kts. Selain itu, saya juga salah menempatkan test functions ke dalam folder main sehingga Code Editor tidak bisa mendeteksi penggunaan JUnit. Solusinya adalah dengan menempatkan test functions ke dalam folder test. <br>

<h1> Refleksi 2 </h1>

Saya merasa lebih percaya diri bahwa kode yang saya ketik bisa berjalan sesuai harapan. Sebenarnya, tidak ada jawaban yang pasti untuk jumlah unit test yang harus dibuat dalam satu class. Hal ini tergantung pada beberapa faktor, seperti kompleksitas class, ukuran proyek, dan lainnya. Namun, disarankan untuk menulis unit test yang cukup untuk menguji semua fungsionalitas kelas.

Untuk memastikan bahwa unit test cukup menguji program adalah dengan menggunakan konsep code coverage. Code coverage ini digunakan untuk mengukur persentase kode dalam program yang diuji oleh unit-test. Selain itu, kita juga harus menguji setiap fitur yang ada dalam program agar tidak ada kasus yang terlewat. Menurut saya, 100% code coverage tidak menjamin bahwa kode bebas dari kesalahan atau bug. Oleh karena itu, penting juga untuk memastikan kualitas kode kita.

Ada duplikasi kode pada fungsi CreateProduct_isCorrect(). Hal ini bisa menyulitkan perawatan kode jika ingin melakukan perubahan. Solusinya adalah dengan mengekstraksi kode yang sama ke dalam fungsi utilitas dan memanggilnya dari fungsi tersebut.