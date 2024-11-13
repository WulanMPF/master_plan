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

## PRAKTIKUM 2

### Langkah 1: Buat file plan_provider.dart
Buat folder baru provider di dalam folder lib, lalu buat file baru dengan nama plan_provider.dart berisi kode seperti berikut.

![Praktikum](/images/p2_langkah1.png)

### Langkah 2: Edit main.dart
Gantilah pada bagian atribut home dengan PlanProvider seperti berikut. Jangan lupa sesuaikan bagian impor jika dibutuhkan.

![Praktikum](/images/p2_langkah2.png)

### Langkah 3: Tambah method pada model plan.dart
Tambahkan dua method di dalam model class Plan seperti kode berikut.

![Praktikum](/images/p2_langkah3.png)

### Langkah 4: Pindah ke PlanScreen
Edit PlanScreen agar menggunakan data dari PlanProvider. Hapus deklarasi variabel plan (ini akan membuat error). Kita akan perbaiki pada langkah 5 berikut ini.

![Praktikum](/images/p2_langkah4.png)

### Langkah 5: Edit method _buildAddTaskButton
Tambahkan BuildContext sebagai parameter dan gunakan PlanProvider sebagai sumber datanya. Edit bagian kode seperti berikut.

![Praktikum](/images/p2_langkah5.png)

### Langkah 6: Edit method _buildTaskTile
Tambahkan parameter BuildContext, gunakan PlanProvider sebagai sumber data. Ganti TextField menjadi TextFormField untuk membuat inisial data provider menjadi lebih mudah.

![Praktikum](/images/p2_langkah6.png)

### Langkah 7: Edit _buildList
Sesuaikan parameter pada bagian _buildTaskTile seperti kode berikut.

![Praktikum](/images/p2_langkah7.png)

### Langkah 8: Tetap di class PlanScreen
Edit method build sehingga bisa tampil progress pada bagian bawah (footer). Caranya, bungkus (wrap) _buildList dengan widget Expanded dan masukkan ke dalam widget Column seperti kode pada Langkah 9.

![Praktikum](/images/p2_langkah8.png)

### Langkah 9: Tambah widget SafeArea
Terakhir, tambahkan widget SafeArea dengan berisi completenessMessage pada akhir widget Column. Perhatikan kode berikut ini.

![Praktikum](/images/p2_langkah9a.png)

Akhirnya, run atau tekan F5 jika aplikasi belum running. Tidak akan terlihat perubahan pada UI, namun dengan melakukan langkah-langkah di atas, Anda telah menerapkan cara memisahkan dengan baik antara view dan model. Ini merupakan hal terpenting dalam mengelola state di aplikasi Anda.

## TUGAS PRAKTIKUM 2

### Jelaskan mana yang dimaksud InheritedWidget pada langkah 1 tersebut! Mengapa yang digunakan InheritedNotifier?

**Jelaskan mana yang dimaksud InheritedWidget pada langkah 1 tersebut!**

- Pada langkah 1, PlanProvider adalah sebuah kelas yang digunakan untuk berbagi data antar widget di dalam aplikasi Flutter. Kelas ini adalah turunan dari InheritedNotifier, yang mirip dengan InheritedWidget. Tujuan dari InheritedNotifier adalah agar data tertentu bisa diakses oleh widget lain tanpa harus dikirimkan terus-menerus dari satu widget ke widget lainnya.

**Mengapa yang digunakan InheritedNotifier?**

- InheritedNotifier adalah versi khusus dari InheritedWidget yang bisa digunakan ketika data di dalamnya mungkin berubah. Karena data Plan bisa berubah, InheritedNotifier cocok karena ketika data diubah, InheritedNotifier akan secara otomatis memberi tahu semua widget yang tergantung pada data ini untuk memperbarui tampilannya.
- Dalam kode PlanProvider, ValueNotifier<Plan> adalah tempat penyimpanan data Plan. Dengan cara ini, jika data Plan berubah, semua widget yang menggunakan PlanProvider akan otomatis diperbarui sesuai perubahan data.

### Jelaskan maksud dari method di langkah 3 pada praktikum tersebut! Mengapa dilakukan demikian?

**Jelaskan maksud dari method di langkah 3 pada praktikum tersebut!**

- completedCount -> Method ini menghitung jumlah tugas yang telah selesai (complete). tasks adalah daftar semua tugas dalam Plan. Method ini menggunakan where untuk memfilter hanya tugas yang status complete-nya bernilai true, kemudian menghitung jumlahnya dengan length. completedCount memberi informasi tentang berapa banyak tugas yang sudah selesai dalam plan tersebut.
- completenessMessage -> Method ini membuat pesan yang menjelaskan status kemajuan plan secara keseluruhan. Pesan tersebut menunjukkan jumlah tugas yang sudah selesai (completedCount) dari total tugas (tasks.length). Sebagai contoh, jika ada 3 tugas selesai dari 5 tugas total, maka pesan ini akan berbunyi: "3 out of 5 tasks". Bertujuan untuk memberikan ringkasan yang mudah dibaca tentang kemajuan plan, yang dapat ditampilkan kepada pengguna dalam antarmuka aplikasi.

**Mengapa dilakukan demikian?**

- Kemudahan Akses: Dengan adanya completedCount, kita bisa langsung tahu jumlah tugas yang selesai tanpa harus menghitungnya berulang kali di berbagai bagian aplikasi. Sehingga membuat kode lebih rapi dan efisien.
- Memberikan Informasi Kemajuan: completenessMessage memberikan pesan yang ringkas dan mudah dimengerti tentang kemajuan, yang bermanfaat untuk tampilan antarmuka, sehingga pengguna bisa langsung melihat status penyelesaian dari rencana tersebut.

### Lakukan capture hasil dari Langkah 9 berupa GIF, kemudian jelaskan apa yang telah Anda buat!

![Praktikum](/images/p2_langkah9b.gif)

- **PlanProvider** adalah widget yang menyediakan data Plan dan menggunakan InheritedNotifier untuk memastikan widget-widget yang bergantung pada data ini otomatis diperbarui saat ada perubahan.
- **PlanScreen** menampilkan daftar tugas yang ada dalam Plan dan menggunakan PlanProvider untuk mengakses data Plan di seluruh bagian layar.
- Di bagian bawah layar, ada tampilan progres yang menunjukkan berapa banyak tugas yang sudah diselesaikan dalam bentuk pesan seperti "X out of Y tasks" menggunakan completenessMessage.
- **_buildAddTaskButton** menyediakan tombol untuk menambahkan tugas baru ke daftar. Ketika ditekan, tombol ini akan membuat tugas baru dan memperbarui data Plan.
- **_buildTaskTile** menampilkan masing-masing tugas dengan Checkbox untuk menandai apakah tugas selesai dan TextFormField untuk mengedit deskripsi tugas secara langsung.
- **_buildList** menampilkan daftar tugas yang dibuat dalam bentuk ListView.builder.
- Pada **langkah 9**, progres dari tugas ditampilkan di bagian bawah layar menggunakan SafeArea untuk memastikan teks completenessMessage tetap berada dalam area yang aman dari elemen-elemen seperti tombol navigasi atau tepi layar.

## PRAKTIKUM 3

### Langkah 1: Edit PlanProvider
Perhatikan kode berikut, edit class PlanProvider sehingga dapat menangani List Plan.

![Praktikum](/images/p3_langkah1.png)

### Langkah 2: Edit main.dart
Langkah sebelumnya dapat menyebabkan error pada main.dart dan plan_screen.dart. Pada method build, gantilah menjadi kode seperti ini.

![Praktikum](/images/p3_langkah2.png)

### Langkah 3: Edit plan_screen.dart
Tambahkan variabel plan dan atribut pada constructor-nya seperti berikut.

![Praktikum](/images/p3_langkah3.png)

### Langkah 4: Error
Itu akan terjadi error setiap kali memanggil PlanProvider.of(context). Itu terjadi karena screen saat ini hanya menerima tugas-tugas untuk satu kelompok Plan, tapi sekarang PlanProvider menjadi list dari objek plan tersebut.

### Langkah 5: Tambah getter Plan
Tambahkan getter pada _PlanScreenState seperti kode berikut.

![Praktikum](/images/p3_langkah5.png)

### Langkah 6: Method initState()
Pada bagian ini kode tetap seperti berikut.

![Praktikum](/images/p3_langkah6.png)

### Langkah 7: Widget build
Pastikan Anda telah merubah ke List dan mengubah nilai pada currentPlan seperti kode berikut ini.

![Praktikum](/images/p3_langkah7.png)

### Langkah 8: Edit _buildTaskTile
Pastikan ubah ke List dan variabel planNotifier seperti kode berikut ini.

![Praktikum](/images/p3_langkah8a.png)

**Kode lengkap plan_screen.dart (ada beberapa yang dimodifikasi dikarenakan error)**

![Praktikum](/images/p3_langkah8b.png)

### Langkah 9: Buat screen baru
Pada folder view, buatlah file baru dengan nama plan_creator_screen.dart dan deklarasikan dengan StatefulWidget bernama PlanCreatorScreen.

![Praktikum](/images/p3_langkah9a.png)

Gantilah di main.dart pada atribut home menjadi seperti berikut.

![Praktikum](/images/p3_langkah9b.png)

### Langkah 10: Pindah ke class _PlanCreatorScreenState
Kita perlu tambahkan variabel TextEditingController sehingga bisa membuat TextField sederhana untuk menambah Plan baru. Jangan lupa tambahkan dispose ketika widget unmounted seperti kode berikut.

![Praktikum](/images/p3_langkah10.png)

### Langkah 11: Pindah ke method build
Letakkan method Widget build berikut di atas void dispose. Gantilah ‘Namaku' dengan nama panggilan Anda.

![Praktikum](/images/p3_langkah11.png)

### Langkah 12: Buat widget _buildListCreator
Buatlah widget berikut setelah widget build.

![Praktikum](/images/p3_langkah12.png)

### Langkah 13: Buat void addPlan()
Tambahkan method berikut untuk menerima inputan dari user berupa text plan.

![Praktikum](/images/p3_langkah13.png)

### Langkah 14: Buat widget _buildMasterPlans()
Tambahkan widget seperti kode berikut.

![Praktikum](/images/p3_langkah14a.png)

**Kode lengkap plan_creator_screen.dart (ada beberapa yang dimodifikasi dikarenakan error)**

![Praktikum](/images/p3_langkah14b.png)

## TUGAS PRAKTIKUM 3

### Berdasarkan Praktikum 3 yang telah Anda lakukan, jelaskan maksud dari gambar diagram berikut ini!

![Tugas](/images/p3_tugas1.png)

Diagram tersebut menggambarkan arsitektur atau struktur aplikasi Master Plan yang sedang dikembangkan.

- MaterialApp: Merupakan root widget dari aplikasi yang mengatur tema, navigasi, dan lainnya.
- PlanProvider: Merupakan sebuah InheritedNotifier yang menyediakan daftar Plan ke seluruh aplikasi. Dengan menggunakan PlanProvider, widget-widget lain dapat mengakses dan memanipulasi daftar rencana tersebut.
- PlanScreen: Merupakan halaman utama aplikasi yang menampilkan detail dari satu Plan tertentu. Halaman ini menggunakan PlanProvider untuk mendapatkan dan memanipulasi data rencana.
- PlanCreatorScreen: Merupakan halaman baru yang ditambahkan untuk membuat rencana baru. Halaman ini juga menggunakan PlanProvider untuk menambahkan rencana baru ke daftar.
- Navigator Push: Ketika pengguna mengklik salah satu rencana di PlanCreatorScreen, maka aplikasi akan menampilkan halaman PlanScreen untuk rencana yang dipilih.

Secara keseluruhan, diagram ini menggambarkan bagaimana alur aplikasi bekerja, di mana PlanProvider berperan sebagai pusat penyedia data rencana yang dapat diakses oleh berbagai widget dalam aplikasi, termasuk halaman PlanScreen dan PlanCreatorScreen.

### Lakukan capture hasil dari Langkah 14 berupa GIF, kemudian jelaskan apa yang telah Anda buat!

![Tugas](/images/p3_tugas2.gif)

Pada langkah 14 dilakukan pembuatan fitur untuk menambahkan plan baru pada aplikasi Master Plan.

- Terdapat sebuah TextField di bagian atas layar yang memungkinkan pengguna untuk mengetikkan nama plan baru.
- Ketika pengguna mengetikkan nama plan dan menekan tombol "Enter", maka plan baru akan ditambahkan ke dalam daftar plan yang ditampilkan di bawahnya.
- Daftar plan ditampilkan menggunakan ListView, di mana setiap item dalam ListView menampilkan nama plan dan status kelengkapannya.
- Jika daftar plan masih kosong, maka akan ditampilkan pesan dan ikon yang menunjukkan bahwa belum ada plan yang dibuat.
- Ketika pengguna mengklik salah satu item plan di ListView, maka aplikasi akan berpindah ke halaman PlanScreen yang menampilkan detail dari plan yang dipilih.

Dengan fitur ini, pengguna aplikasi Master Plan dapat dengan mudah menambahkan plan-plan baru dan melihat daftar plan yang telah dibuat. Hal ini memudahkan pengguna untuk mengelola dan mengetahui progress dari plan-plan yang sedang dikerjakan.