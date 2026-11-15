# JOBSHEET 9 - ARRAY 1 DIMENSI

**Identitas Mahasiswa:**
* **Nama:** Mochamad Razan Al Baasith
* **NIM:** 264107020145
* **Kelas / No. Presensi:** TI-1D / 19

---

## 1: TUJUAN PRAKTIKUM

1. Mahasiswa mampu memahami konsep array 1 dimensi serta cara mendeklarasikan, menginisialisasi, dan mengakses elemennya dalam bahasa pemrograman Java 
2. Mahasiswa mampu membuat program yang memanfaatkan array 1 dimensi untuk menyimpan dan mengolah data, termasuk menggunakan perulangan for dan foreach.
3. Mahasiswa mampu menerapkan operasi aritmatika pada elemen array, seperti menghitung total, rata-rata, nilai tertinggi, dan nilai terendah.
4. Mahasiswa mampu menerapkan algoritma pencarian (searching) dan pengurutan (sorting) sederhana pada array 1 dimensi.
5. Mahasiswa mampu menerapkan array 1 dimensi untuk menyelesaikan studi kasus yang relevan dengan kehidupan kampus dan sehari-hari.

---

## 2: Praktikum

### 2.1 Percobaan 1: Deklarasi, Inisialisasi, Mengisi, dan Menampilkan Elemen Array

#### 2.1.1 Kode Program Java
```java
import java.util.Arrays;

public class ArrayBilangan19 {
    public static void main(String[] args) {
        int[] bil = new int[4];
        bil[0]=5;
        bil[1]=13;
        bil[2]=-7;
        bil[3]=17;

        for (int i = 0; i < bil.length; i++) {
            System.out.println("bil[" + i + "] = " + bil[i]);
        }
        for (int nilai : bil) {
            System.out.println(nilai);
        }
        System.out.println(Arrays.toString(bil));
    }
}
```

#### 2.1.2 Hasil Running / Screenshot Output

![Output Percobaan 1](<Output .png>)

#### 2.1.3 Jawaban Pertanyaan / Pertanyaan Refleksi
* **Pertanyaan 1:** Jika isi masing-masing elemen array bil diubah dengan angka 5.0, 12867, 7.5, 2000000, apa yang terjadi? Mengapa bisa demikian?
  * **Jawab:** .
* **Pertanyaan 2:** Modifikasi kode program di atas dengan melakukan inisialisasi elemen array sekaligus pada saat deklarasi array (tanpa new int[4] dan pengisian satu per satu).
![Output Percobaan](<Output .png>)
  * **Jawab:** .
* **Pertanyaan 3:** Ubah statement penampilan pada langkah ke-4 menjadi seperti berikut: System.out.println("bil[" + i + "] = " + bil[i] + ", double = " + (bil[i] * 2)); Apa keluaran dari program? Jelaskan maksud dari statement
tersebut.
   * **Jawab:** .
* **Pertanyaan 4:** Jika kondisi pada statement for-loop di atas diubah menjadi i <= 4, apa keluaran dari program? Mengapa demikian?
  * **Jawab:**  .
* **Pertanyaan 5:** Apa perbedaan antara menampilkan array menggunakan for loop, foreach loop, dan Arrays.toString() pada langkah ke-5? Kapan sebaiknya masing-masing digunakan?
  * **Jawab:** .
    
---

### 2.2 Percobaan 2: Studi Kasus SIAKAD — Input Nilai Mahasiswa dan Status Kelulusan

#### 2.2.1 Kode Program
```java
import java.util.Scanner;

public class ArrayNilai19 {
    public static void main(String[] args) {
        int[] nilaiAkhir = new int[10];
        Scanner input = new Scanner(System.in);

        for (int i = 0; i < nilaiAkhir.length; i++) {
            System.out.print("Masukkan nilai mahasiswa ke-" + (i + 1) + ": ");
            nilaiAkhir[i] = input.nextInt();
        }

        for (int i = 0; i < nilaiAkhir.length; i++) {
            String status = (nilaiAkhir[i] > 70) ? "LULUS" : "TIDAK LULUS";
            System.out.println("Mahasiswa ke-" + (i + 1) + ": " + nilaiAkhir[i] + " (" + status + ")");
        }

    }
}

```

#### 2.2.2 Hasil Running

![Output Percobaan 2](<Output .png>)

#### 2.2.3 Jawaban Pertanyaan / Pertanyaan Refleksi
* **Pertanyaan 1:** Apa yang dimaksud dengan kondisi i < nilaiAkhir.length pada perulangan di atas?
  * **Jawab:** 
* **Pertanyaan 2:** Modifikasi program agar hanya menampilkan nilai mahasiswa yang lulus saja (nilai > 70), tanpa menampilkan yang tidak lulus. Jelaskan alur programnya!
  * **Jawab:** 
* **Pertanyaan 3:** Ubah perulangan pada langkah ke-4 dan ke-5 dari for loop menjadi foreach loop. Apakah seluruh bagian program dapat diubah menjadi foreach? Jelaskan bagian mana yang bisa dan tidak bisa, beserta alasannya.
  * **Jawab:** 
* **Pertanyaan 4:**  Modifikasi program agar turut menghitung dan menampilkan jumlah mahasiswa yang lulus dan jumlah mahasiswa yang tidak lulus di akhir program.
  * **Jawab:** 

![Output Modif Percobaan](<Output.png>)

---

### 2.3 Percobaan 3: Operasi Aritmatika pada Array — Total, Rata-rata, Nilai Tertinggi dan Terendah

#### 2.3.1 Kode Program Java
 ```java
import java.util.Scanner;

public class ArrayRataNilai19 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        int[] nilaiMhs = new int[10];
        int total = 0;
        double rata2;

        for (int i = 0; i < nilaiMhs.length; i++) {
            System.out.print("Masukkan nilai mahasiswa ke-" + (i + 1) + ": ");
            nilaiMhs[i] = input.nextInt();
            total += nilaiMhs[i];
        }
        rata2 = (double) total / nilaiMhs.length;
        System.out.println("Total nilai: " + total);
        System.out.println("Rata-rata: " + rata2);

        int tertinggi = nilaiMhs[0];
        int terendah = nilaiMhs[0];
        for (int i = 1; i < nilaiMhs.length; i++) {
            if (nilaiMhs[i] > tertinggi) tertinggi = nilaiMhs[i];
            if (nilaiMhs[i] < terendah) terendah = nilaiMhs[i];
        }
        System.out.println("Nilai tertinggi: " + tertinggi);
        System.out.println("Nilai terendah: " + terendah);

        if (rata2 >= 85) {
            System.out.println("Predikat kelas: SANGAT BAIK");
        } else if (rata2 >=70) {
            System.out.println("Predikat kelas: BAIK");
        } else {
            System.out.println("Predikat kelas: PERLU PENDAMPINGAN");
        }
    }
}

```
#### 2.3.2 Hasil Running

![Output Percobaan 3](<Output .png>)

#### 2.3.3 Jawaban Pertanyaan / Pertanyaan Refleksi
* **Pertanyaan 1:** Modifikasi kode program di atas agar dapat menampilkan banyaknya mahasiswa yang lulus, yaitu mahasiswa yang memiliki nilai lebih besar dari 70 (> 70)..
  * **Jawab:**
![Output Modif Percobaan](<Output.png>)

* **Pertanyaan 2:** Modifikasi program di atas sehingga program menerima jumlah elemen array berdasarkan input dari pengguna (tidak selalu 10), lalu tetap dapat menghitung total, rata-rata, nilai tertinggi, dan nilai terendah dengan benar.
  * **Jawab:**
![Output Modif Percobaan](<Output.png>)

* **Pertanyaan 3:** Mengapa pada perhitungan rata-rata digunakan (double) total / nilaiMhs.length, bukan langsung total / nilaiMhs.length? Jelaskan!.
  * **Jawab:** 

### 2.4 Percobaan 4: Pencarian (Searching) dan Pengurutan (Sorting) Sederhana

#### 2.4.1 Kode Program Java: Bagian A - Linear Search
```java
public class SearchNilai19 {
    public static void main(String[] args) {
        int[] nilai = {78, 65, 90, 55, 88, 72};
        int key = 90;
        boolean ditemukan = false;

        for (int i = 0; i < nilai.length; i++) {
            if (nilai[i] == key) {
                System.out.println("Nilai " + key + " ditemukan pada indeks ke-" + i);
                ditemukan = true;
                break;
            }
        }
        if (!ditemukan) {
            System.out.println("Nilai " + key + " tidak ditemukan.");
        }
    }
}

```
#### Kode Program: Bagian B - Bubble Sort
```java
import java.util.Arrays;

public class SortNilai19 {
    public static void main(String[] args) {
        int[] nilai = {78, 65, 90, 55, 88, 72};
        for (int i = 0; i < nilai.length - 1; i++) {
            for (int j = 0; j < nilai.length - 1 - i; j++) {
                if (nilai[j] > nilai[j + 1]) {
                    int temp = nilai[j];
                    nilai[j] = nilai[j + 1];
                    nilai[j + 1] = temp;
                }
            }
        }
        System.out.println(Arrays.toString(nilai));
    }
}

```

#### 2.4.2 Hasil Running: Bagian A 

![Output Percobaan 4](<Output.png>)

#### Hasil Running: Bagian B

![Output Percobaan 4](<Output.png>)

#### 2.4.3 Jawaban Pertanyaan / Pertanyaan Refleksi
* **Pertanyaan 1:** Jelaskan maksud dari statement break; pada kode program Bagian A di atas!
  * **Jawab:** 
* **Pertanyaan 2:** Modifikasi kode program Bagian A sehingga program dapat menerima input berupa banyaknya elemen array nilai, isi array, dan sebuah nilai (key) yang ingin dicari dari pengguna, lalu mencetak indeks posisi elemen dari nilai (key) tersebut.
  * **Jawab:**
* **Pertanyaan 3:** Modifikasi program Bagian A agar menampilkan pesan "Nilai yang dicari tidak ditemukan" dengan format pesan yang lebih informatif apabila nilai yang dicari (key) tidak ada di dalam array.
  * **Jawab:** .
* **Pertanyaan 4:** Jelaskan langkah demi langkah cara kerja algoritma bubble sort pada Bagian B menggunakan data ujicoba yang tersedia!
  * **Jawab:** 
* **Pertanyaan 5:** Modifikasi program Bagian B agar mengurutkan array dari nilai terbesar ke terkecil (descending),
bukan dari terkecil ke terbesar.
  * **Jawab:** 



## 3: TUGAS MANDIRI
   1. Tugas 1 - Pengelolaan Nilai Mahasiswa: Buatlah program yang dapat menyimpan dan mengelola nilai mahasiswa (bilangan bulat). Program harus
menyediakan fitur untuk:
• Memasukkan banyaknya nilai mahasiswa yang akan diinput.
• Memasukkan setiap nilai mahasiswa satu per satu.
• Menghitung nilai rata-rata dari seluruh nilai yang dimasukkan.
• Menampilkan nilai tertinggi dan nilai terendah.
• Menampilkan semua nilai yang telah dimasukkan, beserta status kelulusannya (LULUS / TIDAK LULUS).
   * **Kode Program java**
```java


```
   * **Hasil Running**

![Output Tugas 1](<Output Tugas 1.png>)

   2. Tugas 2 - Aplikasi Pemesanan Kafe Kampus: Buat program yang dapat mengelola pemesanan makanan dan minuman di kafe kampus. Program
menyediakan daftar menu yang sudah ditentukan, memungkinkan pengguna memilih menu melalui fitur pencarian, mencatat pesanan, serta menghitung total biaya.

Daftar menu kafe (inisialisasi array of String saat deklarasi):
```java
String[] menu = {"Nasi Goreng", "Mie Goreng", "Roti Bakar", "Kentang Goreng", "Teh Tarik", "Cappucino", "Chocolate Ice"};
int[] harga = {15000, 13000, 10000, 12000, 8000, 18000, 20000};
```
Program yang dibuat wajib mencakup ketentuan berikut:
• Fitur pencarian menu: pengguna memasukkan nama makanan/minuman yang ingin dipesan, program
mencari nama tersebut di dalam array menu menggunakan algoritma linear search. Apabila
ditemukan, tampilkan harganya; apabila tidak ditemukan, beri tahu pengguna bahwa menu tersebut
tidak tersedia.
• Fitur pemesanan: pengguna memasukkan jumlah item yang ingin dipesan, lalu untuk setiap item
memilih nama menu (yang harus tervalidasi ada dalam daftar menu). Simpan nama pesanan dalam
array satu dimensi terpisah dari array menu utama.
• Hitung dan tampilkan total biaya dari seluruh pesanan yang dimasukkan pengguna.
• Tampilkan daftar pesanan yang telah dibuat beserta total biayanya, dengan format tampilan yang rapi
dan mudah dibaca.

   * **Kode Program Java**
```java


```


   * **Hasil Running**

![Output Tugas 2](<Output Tugas 2.png>)

  
