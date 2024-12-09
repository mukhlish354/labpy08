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
