# Tutorial for Advance Programming Course 2023/2024

**Nama** : **Restu Ahmad Ar Ridho** <br/>
**NPM** : **2206028951** <br/>
**Kelas** : **Advance Programming - A**

## Module 10 - Asynchoronous Programming

#### Experiment 1.2: Understanding how it works.
![](static\images\image.png)
Dalam pemrograman asynchronous, eksekusi kode tidak harus berhenti dan menunggu suatu fungsi selesai sebelum melanjutkan. Ini berarti bahwa fungsi async pada Rust berjalan secara non-blocking. Dalam konteks kode tersebut, fungsi `main` memulai eksekusi dan membuat executor dan spawner. Kemudian, fungsi `main` membuat spawner task async yang mencetak "howdy!", kemudian menunggu selama 2 detik, dan mencetak "done!". Selanjutnya, akan mengeksekusi kode setelahnya yaitu adalah mencetak "hey hey". Kemudian spawner di `drop` untuk memberi tahu tidak ada lagi task yang akan diterima. Kemudian fungsi `main` menjalankan executor, yang akan menjalankan spawner task async yang telah dibuat sebelumnya. Task async tersebut kemudian mencetak "howdy!", kemudian menunggu selama 2 detik, dan kemudian mencetak "done!". Oleh karena itu, "hey hey" dapat dicetak terlebih dahulu sebelum "howdy!" dan "done!", karena `executor.run()` diletakan setelah "hey hey".