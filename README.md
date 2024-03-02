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

<details>
<summary>Tutorial 3</summary>

### **Explain what principles you apply to your project!**
**Single Responsibility Principle (SRP):**
Awalnya saya menggabungkan CarController dan ProductController ke dalam `ProductController.java`. Setelah mengimplementasikan SRP, saya memisahkan CarController karena masing-masing memiliki fungsi yang berbeda. 
<br>

**Open Closed Principle (OCP):**
Pada `model`, saya menambahkan metode update sehingga pemanggilan metode tersebut akan menjadi lebih mudah. Hal ini memungkinkan pemanggilan metode yang lebih umum pada repository tanpa perlu modifikasi secara langsung. 
<br>

**Interface Segregation Principle (ISP):**
Saya memisahkan interface ProductService dan CarService sehingga dapat membedakan interface antara keduanya. Hal ini memungkinkan moduleritas yang lebih baik daripada menggabungkan keduanya menjadi satu. Pendekatan ini dapat meningkatkan efisiensi dalam mengimplementasikan metode abstrak dan struktur kode menjadi lebih fleksibel. 
<br>

**Dependency Inversion Principle (DIP):**
Pada `CarRepository`, saya mengganti objek dari CarServiceImpl yang merupakan kelas konkret menjadi CarService yang merupakan antarmuka. Jadi, prinsip ini memanfaatkan objek yang terhubung dengan antarmuka atau abstraksi, bukan kelas konkret. Hal ini dapat mengurangi atau menghilangkan hubungan antar komponen-komponen kelas konkret yang dapat disebut sebagai *decoupling*. 
<br>

### **Explain the advantages of applying SOLID principles to your project with examples.**
- **Single Responsibility Principle (SRP):** kode menjadi lebih terorganisir dengan cara memisahkan tanggung jawab tiap kelas, memudahkan pemeliharan, pemahaman dan komunikasi antar pengembang. 
<br>

- **Open Closed Principle (OCP):** dapat meningkatkan fleksibilitas dan meminimalkan dampak perubahan. Selain itu, memungkinkan penambahan fitur baru tanpa mengubah kode yang sudah ada. 
<br>

- **Liskov Substitution Principle (LSP):** dapat mengurangi ketergantungan antar kelas dan memungkinkan polimorfisme yang lebih baik.
<br>

- **Interface Segregation Principle (ISP):** sama seperti LSP, yaitu dapat memungkinkan polimorfisme yang lebih baik dan mengurangi ketergantungan antar kelas. 
<br>

- **Dependency Inversion Principle (DIP):** dapat membantu dalam mengurangi dampak perubahan pada satu bagian kode terhadap bagian kode lainnya. 
<br>

### **Explain the disadvantages of not applying SOLID principles to your project with examples.**
- **Risiko antara Controller dan Implementasi:** 
Jika tidak mengikuti DIP dan OCP, dapat mengakibatkan keterikatan yang kuat antara
controller dan implementasi. Hal ini dapat menghasilkan environment pengujian yang buruk dan sulit untuk beralih antara implementasi untuk pengujian. 
<br>

- **Kesulitan Pemahaman dan Pemeliharan Kode:**
Kesulitan dalam memahami dan memelihara kode karena ketidakpatuhan terhadap SRP dan penanganan banyak tanggung jawab oleh `controller`, `repository`, atau `model`. Hal ini dapat menyebabkan *bug*, meningkatkan kompleksitas, dan menyulitkan komunikasi. 
<br>

- **Ketergantungan Tinggi antara Modul atau Metode:** Jika tidak mengikuti ISP dan LSP, basis kode terikat erat dan kurang fleksibel karena antarmuka, abstraksi, atau kelas dasar dengan metode maupun dependensi yang tidak perlu. 
</details>

<details>

<summary>TUTORIAL 4</summary>

1. Pertama, mari kita bicara tentang keakuratan. Saya merasa cukup yakin dengan tes fungsional yang saya miliki. Saya merasa telah menguji semua kasus tepi dengan menyeluruh dan tes fungsional saya sudah cukup untuk memeriksa apakah semua komponen saya cocok dengan baik. Meski begitu, saya juga berpikir bahwa dengan tes terintegrasi, hal ini bisa diperiksa lebih menyeluruh. Kedua, tentang pemeliharaan. Saya merasa tes saya memberi saya kepercayaan diri untuk merombak kode saya tanpa rasa takut dan sering. Tes saya juga membantu saya untuk menghasilkan desain yang baik. Saya merasa jika jumlah tes unit atau tes terintegrasi saya kurang, saya akan menambahkan lebih banyak. Ketiga, tentang alur kerja produksi. Saya merasa siklus umpan balik saya sudah secepat yang saya inginkan. Saya merasa sudah cukup puas dengan peringatan tentang bug yang saya dapatkan. Saya merasa tidak perlu mengubah hal-hal dulu. Saya juga merasa bahwa dengan meninjau dan merombak tes secara rutin, saya bisa mendapatkan umpan balik lebih cepat. Saya bisa menjalankan sebagian dari suite tes lengkap saat saya membutuhkannya dan saya merasa tidak menghabiskan terlalu banyak waktu menunggu tes berjalan.

2. Tentang prinsip F.I.R.S.T. Saya merasa tes saya telah berhasil mengikuti prinsip ini. Tes saya berjalan sesegera mungkin sehingga tidak mengganggu alur kerja saya. Saya memisahkan tes saya menjadi tes unit dan tes fungsional. Tes saya tidak mengganggu, mengubah status fungsi, atau bergantung pada kasus tes lain. Saya juga menerapkan dummy, mock, setUp, dan tearDown untuk menghindari duplikasi dan membersihkan objek. Tes saya konsisten pada pengulangan. Jika fungsi saya melibatkan pemanggilan fungsi lain, maka saya menggunakan teknik Test Double. Tes saya memvalidasi dirinya sendiri karena mereka memiliki penegasan yang ketat. Tes saya menyeluruh dan tepat waktu karena mereka mencakup semua jalur bahagia dan tidak bahagia dan juga mencakup semua kesalahan dan hasil yang mungkin.

</details>
