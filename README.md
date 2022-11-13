# SIG-Teori-Modul13-DigitizingMapData

## Data

Silahkan unduh data berikut :

[BX24_GeoTifv1-02-clip.tif](https://www.qgistutorials.com/downloads/BX24_GeoTifv1-02-clip.tif)

## Prosedur

1. Di QGIS, mari kita memuat file gambar. Pergi ke Layer Add Layer Add Raster Layer .

2. Dalam dialog Pengelola Sumber Data pilih Raster. Di bawah Sumber klik ...dan cari yang diunduh BX24_GeoTifv1-02.tifdan klik Buka . Kemudian klik Tambah diikuti dengan Tutup.

3. Ini adalah file raster yang besar, dan Anda mungkin memperhatikan bahwa saat Anda memperbesar atau menggeser peta, peta membutuhkan sedikit waktu untuk merender gambar. QGIS menawarkan solusi sederhana untuk membuat raster memuat lebih cepat dengan menggunakan Piramida Gambar . QGIS membuat ubin pra-render pada resolusi berbeda, dan ini disajikan kepada Anda alih-alih raster penuh. Ini membuat navigasi peta cepat dan responsif. Klik kanan BX24_GeoTifv1-02layer dan pilih Properties .

4. Dalam dialog Properti Lapisan , Pilih tab Piramida . Tahan Ctrltombol dan pilih semua resolusi yang ditawarkan di panel Resolusi . Biarkan opsi lain ke default dan klik Bangun piramida .

5. Setelah proses selesai, kotak dialog akan menampilkan piramida tanpa tanda silang. Ini menandakan pembangunan Piramida Gambar sudah selesai. Klik Oke .

6. Sebelum kita mulai, kita perlu mengatur Opsi Digitizing default . Buka Pengaturan Opsi… .

7. Pilih tab Digitalisasi di dialog Opsi . Centang Enable snapping by default di bawah bagian Snapping . Dalam mode snap Default pilih Vertex . Ini akan memungkinkan Anda untuk menjepret ke simpul terdekat. Saya juga lebih suka menyetel toleransi gertakan default dan Radius pencarian untuk suntingan titik dalam piksel daripada unit peta. Ini akan memastikan bahwa jarak jepretan tetap konstan terlepas dari tingkat zoom. Tergantung pada resolusi layar komputer Anda, Anda dapat memilih nilai yang sesuai. Klik Oke .

8. Sekarang kita siap untuk memulai digitalisasi. Pertama-tama kita akan membuat layer jalan dan mendigitalkan jalan di sekitar area taman. Klik Layer Create Layer New GeoPackage Layer… icon dari Panels. GeoPackage adalah format data terbuka, non-proprietary, platform-independen, dan berbasis standar untuk sistem informasi geografis yang diimplementasikan sebagai wadah database SQLite. Ini membuatnya lebih mudah untuk memindahkannya daripada sekumpulan shapefile. Dalam tutorial ini, kami membuat beberapa lapisan poligon dan lapisan garis sehingga GeoPackage akan lebih cocok. Anda selalu dapat memuat GeoPackage dan mengekspor layer sebagai shapefile atau format lain yang Anda inginkan.

9. Dalam dialog Lapisan GeoPackage Baru , klik tombol … dan simpan database GeoPackage baru bernama digitizing.gpkg. Pilih nama Tabel sebagai Roadsdan pilih LineStringsebagai jenis Geometri . Peta topografi dasar adalah CRS.EPSG:2193 - NZGD 2000.

10. Saat membuat lapisan GIS, Anda harus memutuskan atribut masing-masing fitur. Karena ini adalah lapisan jalan, kita juga akan memiliki dua atribut utama - Nama dan Kelas. Di Bidang Baru Masukkan Namejenis data Teks, dengan 50sebagai Panjang maksimum dan klik Tambahkan ke daftar atribut. Sekarang buat atribut baru Classdengan tipe data Teks , dengan 50panjang Maksimum . Klik Oke.

11. Setelah Roadslapisan dimuat, klik tombol Toggle Editing untuk menempatkan lapisan dalam mode pengeditan.

12. Klik tombol Tambahkan Fitur Garis . Klik pada kanvas peta untuk menambahkan simpul baru. Tambahkan simpul baru bersama dengan fitur jalan. Setelah Anda mendigitalkan ruas jalan, klik kanan untuk mengakhiri fitur.

----------------------------------

Catatan :

Anda dapat menggunakan roda gulir mouse untuk memperbesar atau memperkecil saat melakukan digitasi. Anda juga dapat menahan tombol gulir dan menggerakkan mouse untuk menjelajah

---------------------------------

13. Setelah Anda mengklik kanan untuk mengakhiri fitur, Anda akan mendapatkan dialog pop-up bernama Road - Feature Attributes . Di sini Anda dapat memasukkan atribut dari fitur yang baru dibuat. Lewati memasukkan nilai apa pun untuk fid karena ini adalah id berurutan yang akan dibuat secara otomatis. Masukkan nama jalan seperti yang muncul di peta topo. Secara opsional, tetapkan nilai Kelas Jalan juga. Klik Oke .

14. Gaya default dari layer garis baru adalah garis tipis. Mari kita ubah untuk lebih melihat fitur digital di kanvas. Pilih Roadslayer dan klik Layer Styling Panel .

15. Di Layer Styling Panel , cari gaya layer jalan yang berbeda. Pilih . Klik Oke .topo road.

16. Sekarang lapisan jalan akan terlihat jelas. Jika Anda puas dengan pekerjaannya, klik tombol Save Layer Edits untuk menyimpan perubahan.

17. Sebelum kita mendigitalkan jalan yang tersisa, penting untuk memperbarui beberapa pengaturan snap penting lainnya untuk membuat lapisan bebas kesalahan. Klik kanan pada ruang mana pun di area bilah alat dan aktifkan bilah alat Snapping.

18. Sekarang Enable Snapping (Magnet Icon) akan muncul di panel. Klik untuk mengaktifkannya dan pilih All Layers dan pilih .Open Snapping Options..

19. Dalam dialog Snapping options , klik Snapping on Intersection , yang memungkinkan Anda menjepret perpotongan lapisan latar belakang.

20. Sekarang Anda dapat mengklik tombol Tambahkan fitur dan mendigitalkan jalan lain di sekitar taman. Pastikan untuk mengklik Simpan Hasil Editan setelah menambahkan fitur baru untuk menyimpan pekerjaan Anda. Alat yang berguna untuk membantu Anda mendigitalkan adalah Alat Vertex . Klik tombol Alat Vertex dan pilih .Vertex Tool (Current Layer).

21. Setelah alat simpul diaktifkan, klik fitur apa saja untuk menampilkan simpul. Klik pada sembarang titik untuk memilihnya. Titik akan berubah warna setelah dipilih. Sekarang Anda dapat mengklik dan menyeret mouse Anda untuk memindahkan vertex. Ini berguna ketika Anda ingin melakukan penyesuaian setelah fitur dibuat. Anda juga dapat menghapus simpul yang dipilih dengan mengklik Deletetombol. ( di mac)Option+Delete.

22. Setelah Anda selesai mendigitalkan semua jalan, klik tombol Toggle Editing . Klik Simpan .

23. Sekarang kita akan membuat layer lain untuk mendigitalkan taman sebagai poligon. Klik Layer Create Layer New GeoPackage Layer… icon dari Panels. Pada dialog New GeoPackage Layer , klik tombol … dan pilih database GeoPackage bernama digitizing.gpkg. Beri nama layer baru sebagai atribut yang disebut Parks. Pilih MultiPolygonsebagai Jenis . Peta topografi dasar adalah CRS. Klik Oke . Di Bidang Baru Masukkan , dan ketik sebagai Data teks , dengan Panjang maksimum dan klik :guilabel:` Tambahkan ke Daftar Bidang.`. Klik Oke .EPSG:2193 - NZGD 2000Name50.

--------------------------------

Catatan :

Poligon vs Multi-Poligon

Polygon - Planar Permukaan didefinisikan oleh 1 batas eksterior dan 0 atau lebih batas interior. Setiap batas interior mendefinisikan sebuah lubang di Poligon.

Multi-Polygon - Digunakan untuk mewakili area dengan lubang di dalam atau terdiri dari beberapa area yang terputus-putus. Misalnya, 3 poligon diskontinyu dapat digambar dan dikelompokkan sebagai fitur tunggal.

------------------------------------

24. Dialog pop-up akan muncul. Pilih tombol Tambahkan Lapisan Baru .

25. Sekarang pilih layer Parkslalu klikroad Toggle Editing dan klik tombol Add feature dan klik pada kanvas peta untuk menambahkan simpul poligon. Digitalkan poligon yang mewakili taman. Pastikan Anda menjepret simpul jalan sehingga tidak ada celah antara poligon taman dan garis jalan. Klik kanan untuk menyelesaikan poligon.

26. Masukkan nama taman di jendela pop-up Taman - Atribut Fitur .

27. Sekarang mendigitalkan wilayah atas taman. Masukkan nama taman dan simpan perubahannya.

28. Sekarang, sebelum mendigitalkan poligon dalam, mari atur pengaturan yang dapat memudahkan pekerjaan ini. Lapisan Multi-Poligon menawarkan pengaturan berguna lainnya yang disebut Hindari persimpangan poligon baru . Pilih Enable Snapping (Magnet Icon), klik untuk mengaktifkannya, dan klik All Layers dan pilih .Advanced Configuration.

29. Klik tombol di bilah alat gertakan.Avoid Overlap on Active layers.

30. Sekarang di Edit Konfigurasi Lanjutan , pilih Unit sebagai pixels.

31. Centang kotak di kolom Hindari Tumpang tindih di baris untuk Parkslapisan.

32. Klik Tambahkan fitur untuk menambahkan poligon. Dengan Avoid Overlap , Anda akan dapat dengan cepat mendigitalkan poligon baru tanpa khawatir akan menjepret tepat ke poligon tetangga.

33. Klik kanan untuk menyelesaikan poligon dan masukkan atribut. Ajaibnya poligon baru menyusut dan tersentak tepat ke batas poligon tetangga! Ini sangat berguna saat mendigitalkan batas kompleks di mana Anda tidak perlu tepat dan masih memiliki poligon yang benar secara topologi. Klik Toggle Editing untuk menyelesaikan pengeditan Parkslayer.

34. Sekarang saatnya untuk mendigitalkan layer bangunan. Buat layer poligon baru bernama Buildingsdengan mengklik Layer Create Layer New GeoPackage Layer… icon dari Panels. Atur Buildings dan MuiltiPolygon . Pilih CRS sebagai . Klik Oke .EPSG:2193 - NZGD 2000

35. Setelah Buildingslapisan ditambahkan, matikan lapisan Parksdan Roadsuntuk membuat peta topo dasar terlihat. Pilih Buildingslayer dan klik Toggle Editing .

36. Mendigitalkan bangunan bisa menjadi tugas yang rumit, dan juga menantang untuk menambahkan simpul secara manual sehingga ujung-ujungnya tegak lurus dan membentuk persegi panjang. Kami akan menggunakan toolbar QGIS yang disebut Shape Digitizing untuk membantu tugas ini. Klik kanan pada ruang kosong mana pun di area bilah alat dan aktifkan file .Shape Digitizing Toolbar.

37. Aktifkan pengeditan dengan menekan ikon pensil Toggle Editing .

38. Sekarang di bawah Add Rectangle dropdown pilih Add Rectangle from Extent tombol.

39. Perbesar ke area dengan bangunan. Klik dan seret mouse untuk menggambar persegi panjang yang sempurna. Demikian pula, tambahkan bangunan yang tersisa.

40. Anda akan melihat bahwa beberapa bangunan tidak vertikal, dan kita perlu menggambar persegi panjang pada sudut yang sesuai dengan tapak bangunan. Di bawah Add Rectangle dropdown pilih Add Rectangle from Center dan tombol Point .

41. Perbesar ke area bangunan berbentuk wajik. Klik di tengah untuk menjatuhkan titik dan seret mouse untuk menggambar persegi panjang.

42. Kita perlu memutar persegi panjang ini agar sesuai dengan gambar pada peta topo. Alat putar tersedia di toolbar Advanced Digitizing . Klik kanan pada area kosong pada bagian toolbar dan aktifkan toolbar Advanced Digitizing .

43. Klik tombol Putar Fitur .

44. Gunakan alat fitur Select Single untuk memilih poligon yang ingin Anda putar. Setelah alat Fitur Putar diaktifkan, Anda akan melihat garis bidik di tengah poligon. Klik tepat pada garis bidik itu dan seret mouse sambil menahan tombol klik kiri. Pratinjau fitur yang diputar akan muncul. Lepaskan tombol mouse saat poligon sejajar dengan tapak bangunan.

45. Simpan hasil edit layer dan klik Toggle Editing setelah Anda selesai mendigitalkan semua bangunan. Anda dapat menyeret lapisan untuk mengubah urutan penampilannya. Tugas digitalisasi sekarang selesai. Anda dapat bermain dengan opsi penataan dan pelabelan di properti lapisan untuk membuat peta yang tampak bagus dari data yang Anda buat.

46. Selesai.
