# **Program Daftar Nilai Mahasiswa**

Program ini adalah aplikasi sederhana berbasis teks untuk mengelola daftar nilai mahasiswa. Program ini dibuat menggunakan **Python** dan mengaplikasikan konsep **class** dan **object-oriented programming (OOP)**.  

## **Fitur Program**
1. **Tambah Data**  
   Menambahkan data mahasiswa baru (nama dan nilai) ke dalam daftar.
2. **Tampilkan Data**  
   Menampilkan semua data mahasiswa dalam daftar.
3. **Hapus Data**  
   Menghapus data mahasiswa berdasarkan nama.
4. **Ubah Data**  
   Mengubah nilai mahasiswa berdasarkan nama.
5. **Keluar Program**  
   Mengakhiri program.
---

# **Input**
```python
class DaftarNilaiMahasiswa:
    def __init__(self):
        self.data_mahasiswa = []

    def tambah(self, nama, nilai):
        """Menambahkan data mahasiswa baru."""
        self.data_mahasiswa.append({"nama": nama, "nilai": nilai})
        print(f"Data {nama} berhasil ditambahkan.")

    def tampilkan(self):
        """Menampilkan semua data mahasiswa."""
        if not self.data_mahasiswa:
            print("Belum ada data mahasiswa.")
        else:
            print("Daftar Nilai Mahasiswa:")
            for idx, mahasiswa in enumerate(self.data_mahasiswa, start=1):
                print(f"{idx}. Nama: {mahasiswa['nama']}, Nilai: {mahasiswa['nilai']}")

    def hapus(self, nama):
        """Menghapus data mahasiswa berdasarkan nama."""
        for mahasiswa in self.data_mahasiswa:
            if mahasiswa["nama"].lower() == nama.lower():
                self.data_mahasiswa.remove(mahasiswa)
                print(f"Data {nama} berhasil dihapus.")
                return
        print(f"Data dengan nama {nama} tidak ditemukan.")

    def ubah(self, nama, nilai_baru):
        """Mengubah data nilai mahasiswa berdasarkan nama."""
        for mahasiswa in self.data_mahasiswa:
            if mahasiswa["nama"].lower() == nama.lower():
                mahasiswa["nilai"] = nilai_baru
                print(f"Nilai {nama} berhasil diubah menjadi {nilai_baru}.")
                return
        print(f"Data dengan nama {nama} tidak ditemukan.")

# Contoh Penggunaan
if __name__ == "__main__":
    daftar_nilai = DaftarNilaiMahasiswa()

    while True:
        print("\n=== Menu ===")
        print("1. Tambah Data")
        print("2. Tampilkan Data")
        print("3. Hapus Data")
        print("4. Ubah Data")
        print("5. Keluar")

        pilihan = input("Pilih menu (1/2/3/4/5): ")

        if pilihan == "1":
            nama = input("Masukkan nama: ")
            nilai = int(input("Masukkan nilai: "))
            daftar_nilai.tambah(nama, nilai)
        elif pilihan == "2":
            daftar_nilai.tampilkan()
        elif pilihan == "3":
            nama = input("Masukkan nama yang ingin dihapus: ")
            daftar_nilai.hapus(nama)
        elif pilihan == "4":
            nama = input("Masukkan nama yang ingin diubah: ")
            nilai_baru = int(input("Masukkan nilai baru: "))
            daftar_nilai.ubah(nama, nilai_baru)
        elif pilihan == "5":
            print("Keluar dari program.")
            break
        else:
            print("Pilihan tidak valid. Silakan coba lagi.")
```
# **Penjelasan Program**
 # 1. Kelas  **DaftarNilaiMahasiswa**:
 - `__init__` : Konstruktor untuk menginisialisasi atribut `data_mahasiswa` sebagai list kosong, yang digunakan untuk menyimpan data mahasiswa.
 - `tambah` : Metode ini untuk menambahkan data mahasiswa baru ke dalam list `data_mahasiswa`. Data disimpan dalam bentuk dictionary dengan dua key: 'nama' dan 'nilai'.
 - `tampilkan` : Metode ini digunakan untuk menampilkan semua data mahasiswa yang telah dimasukkan. Jika data mahasiswa kosong, program akan menampilkan pesan bahwa data belum ada.
 - 'hapus` : Metode ini menghapus data mahasiswa berdasarkan nama. Nama yang dimasukkan akan dicocokkan dengan nama di dalam data mahasiswa (case-insensitive). Jika nama ditemukan, data akan dihapus.
 - 'ubah' : Metode ini untuk mengubah nilai mahasiswa berdasarkan nama. Jika nama ditemukan, nilai mahasiswa tersebut akan diperbarui dengan nilai baru yang dimasukkan.
 # 2. **Program Utama**
- Menyediakan menu interaktif yang memungkinkan pengguna memilih salah satu dari lima pilihan:
   - `Tambah Data (1)`: Memasukkan nama dan nilai mahasiswa baru.
   - `Tampilkan Data (2)`: Menampilkan daftar seluruh mahasiswa yang sudah dimasukkan.
   - `Hapus Data (3)`: Menghapus data mahasiswa berdasarkan nama.
   - `Ubah Data (4)`: Mengubah nilai mahasiswa berdasarkan nama.
   - `Keluar (5)`: Menghentikan program.
   - Program terus berjalan hingga pengguna memilih untuk keluar (menu 5).
 # **Alur Program**
  1. Ketika dijalankan program menampilkan menu pilihan
  2. Pengguna memilih salah satu opsi:
     - `Tamabah Data` : Program meminta input nama dan nilai, kemudian menambahkannya ke dalam daftar.
     - `Tampilkan Data` : Program menampilkan semua data mahasiswa yang ada.
     - `Hapus Data` : Program meminta nama mahasiswa yang ingin dihapus, dan jika ditemukan data tersebut akan dihapus.
     - `Ubah Data` : Program meminta nama mahasiswa dan nilai baru, kemudian memperbarui nilai mahasiswa jika nama ditemukan.
   3. Program akan terus menampilkan menu hingga pengguna memilih **keluar**
# **Output**
```python

=== Menu ===
1. Tambah Data
2. Tampilkan Data
3. Hapus Data
4. Ubah Data
5. Keluar
Pilih menu (1/2/3/4/5): 1
Masukkan nama: aziz
Masukkan nilai: 89
Data aziz berhasil ditambahkan.

=== Menu ===
1. Tambah Data
2. Tampilkan Data
3. Hapus Data
4. Ubah Data
5. Keluar
Pilih menu (1/2/3/4/5): 4
Masukkan nama yang ingin diubah: aziz
Masukkan nilai baru: 98
Nilai aziz berhasil diubah menjadi 98.

=== Menu ===
1. Tambah Data
2. Tampilkan Data
3. Hapus Data
4. Ubah Data
5. Keluar
Pilih menu (1/2/3/4/5): 2
Daftar Nilai Mahasiswa:
1. Nama: aziz, Nilai: 98

=== Menu ===
1. Tambah Data
2. Tampilkan Data
3. Hapus Data
4. Ubah Data
5. Keluar
Pilih menu (1/2/3/4/5): 3
Masukkan nama yang ingin dihapus: aziz
Data aziz berhasil dihapus.

=== Menu ===
1. Tambah Data
2. Tampilkan Data
3. Hapus Data
4. Ubah Data
5. Keluar
Pilih menu (1/2/3/4/5): 5
Keluar dari program.
```
# flowchart

```mermaid
flowchart TD
    A[Mulai] --> B{Pilih Menu}
    B --> C[Tambah Data]
    B --> D[Tampilkan Data]
    B --> E[Hapus Data]
    B --> F[Ubah Data]
    B --> G[Keluar Program]

    C --> C1[Masukkan Nama dan Nilai]
    C1 --> C2[Tambahkan ke Daftar]
    C2 --> H[Kembali ke Menu]

    D --> D1{Apakah Data Kosong?}
    D1 -->|Ya| D2[Tampilkan Pesan: Belum Ada Data]
    D1 -->|Tidak| D3[Tampilkan Semua Data]
    D2 --> H
    D3 --> H

    E --> E1[Masukkan Nama]
    E1 --> E2{Nama Ditemukan?}
    E2 -->|Ya| E3[Hapus Data dari Daftar]
    E2 -->|Tidak| E4[Tampilkan Pesan: Nama Tidak Ditemukan]
    E3 --> H
    E4 --> H

    F --> F1[Masukkan Nama]
    F1 --> F2{Nama Ditemukan?}
    F2 -->|Ya| F3[Masukkan Nilai Baru]
    F3 --> F4[Perbarui Nilai di Daftar]
    F2 -->|Tidak| F5[Tampilkan Pesan: Nama Tidak Ditemukan]
    F4 --> H
    F5 --> H

    G --> I[Selesai]

    H --> B

