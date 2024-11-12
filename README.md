# JOBSHEET 10

Nama: Wulan Maulidya P. F

Kelas: TI-3H

No. Absen: 27

NIM: 2241720174

---

## PRAKTIKUM 1

### Langkah 1: Buat Project Baru
Buatlah sebuah project flutter baru dengan nama master_plan di folder src week-10 repository GitHub Anda atau sesuai style laporan praktikum yang telah disepakati. Lalu buatlah susunan folder dalam project seperti gambar berikut ini.

### Langkah 2: Membuat model task.dart
Praktik terbaik untuk memulai adalah pada lapisan data (data layer). Ini akan memberi Anda gambaran yang jelas tentang aplikasi Anda, tanpa masuk ke detail antarmuka pengguna Anda. Di folder model, buat file bernama task.dart dan buat class Task. Class ini memiliki atribut description dengan tipe data String dan complete dengan tipe data Boolean, serta ada konstruktor. Kelas ini akan menyimpan data tugas untuk aplikasi kita. Tambahkan kode berikut:

![Praktikum](/images/p1_langkah2.png)

### Langkah 3: Buat file plan.dart
Kita juga perlu sebuah List untuk menyimpan daftar rencana dalam aplikasi to-do ini. Buat file plan.dart di dalam folder models dan isi kode seperti berikut.

![Praktikum](/images/p1_langkah3.png)

### Langkah 4: Buat file data_layer.dart
Kita dapat membungkus beberapa data layer ke dalam sebuah file yang nanti akan mengekspor kedua model tersebut. Dengan begitu, proses impor akan lebih ringkas seiring berkembangnya aplikasi. Buat file bernama data_layer.dart di folder models. Kodenya hanya berisi export seperti berikut.

![Praktikum](/images/p1_langkah4.png)

### Langkah 5: Pindah ke file main.dart
Ubah isi kode main.dart sebagai berikut.

![Praktikum](/images/p1_langkah5.png)

### Langkah 6: buat plan_screen.dart
Pada folder views, buatlah sebuah file plan_screen.dart dan gunakan templat StatefulWidget untuk membuat class PlanScreen. Isi kodenya adalah sebagai berikut. Gantilah teks ‘Namaku' dengan nama panggilan Anda pada title AppBar.

![Praktikum](/images/p1_langkah6.png)

### Langkah 7: buat method _buildAddTaskButton()
Anda akan melihat beberapa error di langkah 6, karena method yang belum dibuat. Ayo kita buat mulai dari yang paling mudah yaitu tombol Tambah Rencana. Tambah kode berikut di bawah method build di dalam class _PlanScreenState.

![Praktikum](/images/p1_langkah7.png)

### Langkah 8: buat widget _buildList()
Kita akan buat widget berupa List yang dapat dilakukan scroll, yaitu ListView.builder. Buat widget ListView seperti kode berikut ini.

![Praktikum](/images/p1_langkah8.png)

### Langkah 9: buat widget _buildTaskTile
Dari langkah 8, kita butuh ListTile untuk menampilkan setiap nilai dari plan.tasks. Kita buat dinamis untuk setiap index data, sehingga membuat view menjadi lebih mudah. Tambahkan kode berikut ini.

![Praktikum](/images/p1_langkah9a.png)

Run atau tekan F5 untuk melihat hasil aplikasi yang Anda telah buat. Capture hasilnya untuk soal praktikum nomor 4.

![Praktikum](/images/p1_langkah9b.gif)

### Langkah 10: Tambah Scroll Controller
Anda dapat menambah tugas sebanyak-banyaknya, menandainya jika sudah beres, dan melakukan scroll jika sudah semakin banyak isinya. Namun, ada salah satu fitur tertentu di iOS perlu kita tambahkan. Ketika keyboard tampil, Anda akan kesulitan untuk mengisi yang paling bawah. Untuk mengatasi itu, Anda dapat menggunakan ScrollController untuk menghapus focus dari semua TextField selama event scroll dilakukan. Pada file plan_screen.dart, tambahkan variabel scroll controller di class State tepat setelah variabel plan.

![Praktikum](/images/p1_langkah10.png)

### Langkah 11: Tambah Scroll Listener
Tambahkan method initState() setelah deklarasi variabel scrollController seperti kode berikut.

![Praktikum](/images/p1_langkah11.png)

### Langkah 12: Tambah controller dan keyboard behavior
Tambahkan controller dan keyboard behavior pada ListView di method _buildList seperti kode berikut ini.

![Praktikum](/images/p1_langkah12.png)

### Langkah 13: Terakhir, tambah method dispose()
Terakhir, tambahkan method dispose() berguna ketika widget sudah tidak digunakan lagi.

![Praktikum](/images/p1_langkah13.png)

### Langkah 14: Hasil
Lakukan Hot restart (bukan hot reload) pada aplikasi Flutter Anda. Anda akan melihat tampilan akhir seperti gambar berikut. Jika masih terdapat error, silakan diperbaiki hingga bisa running.

![Praktikum](/images/p1_langkah14.gif)

## TUGAS PRAKTIKUM 1

### Jelaskan maksud dari langkah 4 pada praktikum tersebut! Mengapa dilakukan demikian?

**Jelaskan dari langkah 4!**

- Langkah 4 bertujuan untuk membuat sebuah file bernama data_layer.dart di dalam folder models. File ini akan berfungsi sebagai penghubung untuk mengekspor model-model yang telah dibuat sebelumnya, yaitu plan.dart dan task.dart.

**Mengapa dilakukan demikian?**

- Mengurangi Kerumitan Impor: Dengan menggunakan file data_layer.dart, dapat mengimpor semua model yang diperlukan hanya dengan satu pernyataan impor. Misalnya, daripada mengimpor plan.dart dan task.dart secara terpisah di setiap file yang membutuhkannya, cukup mengimpor data_layer.dart. Sehingga membuat kode lebih bersih dan lebih mudah dikelola.
- Pengelolaan Versi yang Mudah: Jika ada perubahan pada model (misalnya, menambahkan atribut baru), hanya perlu memperbarui file yang relevan, dan semua file yang mengimpor data_layer.dart akan mendapatkan pembaruan tersebut secara otomatis.

### Mengapa perlu variabel plan di langkah 6 pada praktikum tersebut? Mengapa dibuat konstanta ?

**Mengapa perlu variabel plan?**

- Menyimpan Status Rencana: Variabel plan digunakan untuk menyimpan data rencana yang sedang dikelola dalam aplikasi to-do. Dalam konteks aplikasi, plan merupakan objek dari kelas Plan, yang menyimpan nama rencana dan daftar tugas yang terkait. Dengan memiliki variabel ini dapat mengelola dan memodifikasi rencana dan tugas di dalamnya, dan menyimpan status dari rencana saat ini, sehingga pengguna bisa melihat dan mengedit tugas yang ada.
- Memungkinkan Pembaruan UI: Dengan variabel plan, dapat menggunakan metode setState() untuk memperbarui UI ketika ada perubahan. Misalnya, ketika pengguna menambahkan atau mengubah tugas, akan memperbarui plan dan memanggil setState() untuk memberitahukan Flutter bahwa UI harus diperbarui sesuai dengan data terbaru.

**Mengapa dibuat konstanta?**

- Immutabilitas: Dengan menyatakan plan sebagai const, memastikan bahwa nilai awal dari objek Plan tidak akan berubah setelah dibuat. Ini berarti bahwa objek tersebut tidak dapat diubah secara langsung, yang membantu menjaga integritas data.
- Kinerja: Menggunakan const dapat meningkatkan kinerja aplikasi. Flutter dapat mengoptimalkan objek konstanta dengan lebih baik karena mereka tidak akan berubah, sehingga mengurangi kebutuhan untuk membuat objek baru dan mengelola memori.
- Konsistensi: Mendeklarasikan plan sebagai konstanta juga memberikan kejelasan kepada pengembang lain bahwa objek ini seharusnya tidak diubah. Semua perubahan pada plan akan dilakukan dengan membuat salinan baru dari objek tersebut, yang menjaga data rencana yang lama tetap utuh dan memungkinkan pelacakan perubahan.

### Lakukan capture hasil dari Langkah 9 berupa GIF, kemudian jelaskan apa yang telah Anda buat!

![Praktikum](/images/p1_langkah9b.gif)

**Pada langkah 9, telah dibuat widget yaitu _buildTaskTile yang berfungsi untuk menampilkan setiap tugas dalam daftar rencana di aplikasi to-do.**

- Widget _buildTaskTile -> Widget ini menerima dua parameter yaitu Task task: objek yang mewakili tugas tertentu, dan int index: indeks dari tugas dalam daftar. Kedua parameter tersebut berfungsi untuk menampilkan tugas dalam bentuk ListTile, yang merupakan komponen UI dari Flutter untuk menampilkan informasi daftar.
- Checkbox untuk Status Tugas -> Pada bagian leading dari ListTile, terdapat Checkbox yang menunjukkan apakah tugas telah selesai (complete) atau belum. Ketika pengguna mengubah status checkbox akan dijalankan onChanged: ketika checkbox di-klik fungsi ini akan dipanggil, setState: memperbarui variabel plan dengan membuat salinan baru dari daftar tugas dan mengubah status complete dari tugas yang bersangkutan.
- TextFormField untuk Deskripsi Tugas -> Pada bagian title dari ListTile, terdapat TextFormField yang memungkinkan pengguna untuk mengedit deskripsi tugas. initialValue: menampilkan deskripsi tugas saat ini. onChanged: ketika pengguna mengubah teks dalam field, fungsi ini akan dipanggil. setState: memperbarui plan dengan deskripsi baru yang dimasukkan oleh pengguna.

### Apa kegunaan method pada Langkah 11 dan 13 dalam lifecyle state ?

- initState() -> Digunakan untuk inisialisasi yang memerlukan konteks dan pengaturan listener atau sumber daya yang diperlukan saat widget dibuat.

- dispose() -> Digunakan untuk membersihkan sumber daya dan listener ketika widget tidak lagi digunakan, menjaga performa aplikasi dan mencegah kebocoran memori.