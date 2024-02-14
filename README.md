<h1>Refleksi 1</h1>

Saya sudah mengikuti prinsip clean code dalam tutorial ini. Saya sudah memberi nama variabel yang sesuai dengan data yang direpresentasikan. Saya juga sudah memberi nama fungsi yang jelas dengan tujuan masing-masing. Fungsi dalam controller sudah singkat dan hanya memiliki satu tanggung jawab. Fungsi dalam ProductRepository juga tetap menjalankan operasi CRUD untuk entitas produk.

Kode saya tidak banyak mengandung komentar, tapi masih mudah dipahami karena nama fungsi dan variabel yang deskriptif. Kode saya juga sudah rapi dalam hal tata letak dan format. Hal ini membuat kode lebih mudah dimengerti dan dibaca. Saya juga menggunakan struktur objek yang tepat.

Namun, saya juga membuat beberapa kesalahan. Kode saya mengalami error karena menggunakan fitur-fitur Thymeleaf dalam aplikasi Spring Boot. Solusinya adalah dengan menambahkan implementation("org.springframework.boot:spring-boot-starter-thymeleaf") pada build.gradle.kts. Selain itu, saya juga salah menempatkan test functions ke dalam folder main sehingga Code Editor tidak bisa mendeteksi penggunaan JUnit. Solusinya adalah dengan menempatkan test functions ke dalam folder test. <br>

<h1> Refleksi 2 </h1>

Saya merasa lebih percaya diri bahwa kode yang saya ketik bisa berjalan sesuai harapan. Sebenarnya, tidak ada jawaban yang pasti untuk jumlah unit test yang harus dibuat dalam satu class. Hal ini tergantung pada beberapa faktor, seperti kompleksitas class, ukuran proyek, dan lainnya. Namun, disarankan untuk menulis unit test yang cukup untuk menguji semua fungsionalitas kelas.

Untuk memastikan bahwa unit test cukup menguji program adalah dengan menggunakan konsep code coverage. Code coverage ini digunakan untuk mengukur persentase kode dalam program yang diuji oleh unit-test. Selain itu, kita juga harus menguji setiap fitur yang ada dalam program agar tidak ada kasus yang terlewat. Menurut saya, 100% code coverage tidak menjamin bahwa kode bebas dari kesalahan atau bug. Oleh karena itu, penting juga untuk memastikan kualitas kode kita.

Ada duplikasi kode pada fungsi CreateProduct_isCorrect(). Hal ini bisa menyulitkan perawatan kode jika ingin melakukan perubahan. Solusinya adalah dengan mengekstraksi kode yang sama ke dalam fungsi utilitas dan memanggilnya dari fungsi tersebut.

<h1>Refleksi Module 2 2</h1>

## List the code quality issue(s) that you fixed during the exercise and explain your strategy on fixing them.
1. *Modifier* tidak diperlukan. Idealnya, *class* dan metode pengujian JUnit5 seharusnya memiliki visibilitas *default*. Penggunaan *modifier public* pada *class* atau metode bukanlah pilihan terbaik. Dengan menjadikan visibilitasnya *default*, ini dapat membantu dalam menjaga isolasi pengujian dan mencegah akses yang tidak diharapkan.

**Solusi:** Ubah visibilitasnya dengan menghilangkan kata kunci *public* atau *protected* sehingga menjadi *modifier default*.
<br>

2. *Import* yang tidak diperlukan sebaiknya dihindari. Kehadiran *unnecessary import* dapat menimbulkan berbagai masalah, termasuk meningkatnya kompleksitas kode, memperlambat proses kompilasi, dan membuat kode menjadi sulit untuk dipahami.

**Solusi:** Hapus *import* yang tidak diperlukan dan tambahkan *import* secara manual yang benar-benar dibutuhkan dalam kode kita.
<br>

3. *Framework* dependensi Spring memerlukan *dependency injection* melalui anotasi @Inject dan @Autowired. Anotasi ini digunakan untuk menginjeksi *beans* melalui konstruktor, *setter*, dan *field injection*. Hal ini dapat menimbulkan berbagai masalah terkait dengan mutabilitas dan *behavior* yang tidak dapat diprediksi.

**Solusi:** Ganti objek yang menggunakan injeksi @Autowired dengan menginisialisasi *class*-nya secara langsung.
<br>

## Look at your CI/CD workflows (GitHub)/pipelines (GitLab). Do you think the current implementation has met the definition of Continuous Integration and Continuous Deployment? Explain the reasons (minimum 3 sentences)!
Menurut pendapat saya, implementasi yang telah dilakukan sudah sesuai dengan prinsip-prinsip Continuous Integration dan Continuous Deployment (CI/CD). Dalam workflows GitHub, proyek saya telah melakukan Continuous Integration (CI) secara otomatis dengan melakukan pengujian dan pemindaian kode menggunakan SonarCloud setiap kali ada push ke repositori GitHub. Ini memastikan bahwa setiap perubahan kode yang di-push ke repositori telah melalui proses pengujian dan analisis yang cukup sebelum diintegrasikan ke dalam proyek.

Selain itu, sistem otomatisasi Continuous Deployment (CD) akan mengatur proses deployment ke platform Koyeb secara otomatis setiap kali ada push atau pull request ke suatu branch di repositori GitHub saya. Dengan demikian, setiap kali ada perubahan atau permintaan perubahan kode, sistem akan secara otomatis mengatur proses deployment tanpa perlu campur tangan dari developer.

Dengan kata lain, implementasi tidak hanya mematuhi prinsip-prinsip CI/CD dengan baik, tetapi juga mengintegrasikan alur kerja otomatis yang efisien dan dapat diandalkan. Kita juga harus memastikan kualitas dan keamanan kode yang dihasilkan.

<br>

</details>
