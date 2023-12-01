# Implementasi GA Pada Dataset PCOS
Pada percobaan kali ini kelompok kami menggabungkan Algoritma Genetik dan Algoritma Random Forest untuk mendapatkan fitur-fitur terbaik yang dapat digunakan sebagai faktor klasifikasi PCOS.
Dengan memperhatikan dataset pada https://www.kaggle.com/datasets/shreyasvedpathak/pcos-dataset, kami menentukan kolom PCOS (Y/N) sebagai label, dan membuang beberapa fitur yang dirasa kurang penting dalam pengklasifikasian PCOS

![image](https://github.com/bapakloe/GeneticAlgorithm/assets/149106644/4f9dcc50-ff64-4b69-a019-4f9ed4390839)

maka, fitur yang tersisa hanya sebanyak 39 fitur. Selain itu kami juga mengubah beberapa fitur ke dalam bentuk boolean (True/False) untuk memudahkan pemrosesan.

### Perancangan GA
Untuk menerapkan GA kami menentukan kromosom pada populasi ke dalam bentuk boolean (True/False) dan menentukan 30% fitur pertama sebagai False kemudian mengacak kromosom tersebut agar beragam.

![image](https://github.com/bapakloe/GeneticAlgorithm/assets/149106644/fad00441-ecea-4e73-94f2-741bffe974fa)

Setelah itu, nilai kecocokan diukur dengan mencocokkan prediksi dari hasil data training dengan data test yang kemudian nilai kecocokan tersebut disimpan ke dalam array.

![image](https://github.com/bapakloe/GeneticAlgorithm/assets/149106644/b4e97a22-3b64-47f9-8bb7-fd5cb1475b03)

Kemudian kromosom serta nilai kecocokan dimasukkan ke dalam array populasi generasi selanjutnya, dan diproses crossover dengan menggabungkan setengah kromosom pertama dan setengah kromosom kedua pada populasi yang berjarak 2 sehingga menghasilkan generasi baru.

![image](https://github.com/bapakloe/GeneticAlgorithm/assets/149106644/b2d19660-fe54-4631-9a55-b90d84c626ac)

Selanjutnya mutasi dilakukan dengan mentoggle atau membalik fitur-fitur secara random kemudian data tersebut dimasukkan ke dalam array populasi generasi selanjutnya

![image](https://github.com/bapakloe/GeneticAlgorithm/assets/149106644/75e1523b-3d97-436a-80d5-376bc4a23676)

Menginisialisasi populasi, mengevaluasi skor kebugaran, memilih orang tua, melakukan operasi crossover dan mutasi, dan melacak kromosom dengan kinerja terbaik dan skornya selama jumlah generasi tertentu. Fungsi ini juga mencetak dan menampilkan informasi tentang setiap generasi.

![image](https://github.com/bapakloe/GeneticAlgorithm/assets/149106644/fe22417a-e7c0-4a33-9a7a-62f1b68e966b)

Selanjutnya menggunakan Random Forest untuk membuat banyak decission tree dari hasil algoritma genetik yang telah dijalankan kemudian diambil mayoritas hasil yang benar

![image](https://github.com/bapakloe/GeneticAlgorithm/assets/149106644/db50dd9e-cef5-4e08-8230-5e3bc36ab3bb)

didapatkan hasil

![image](https://github.com/bapakloe/GeneticAlgorithm/assets/149106644/e39177be-5497-47a3-871d-261eac166f1d)

dengan grafik score tiap generasi

![image](https://github.com/bapakloe/GeneticAlgorithm/assets/149106644/3c5216b8-5c73-47b9-9f7d-189d6cbc5b2a)
