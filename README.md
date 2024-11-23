# Praktikum5
## Deskripsi tugas
Buat program sederhana yang akan menampilkan daftar nilai mahasiswa, dengan ketentuan:
- Program dibuat dengan menggunakan dictionary
- Tampilkan menu pilihan: (Tambah data, ubah data, hapus data, tampilkan data, cari data)
- Nilai akhir diambil dari perhitungan 3 konmponen nilai (tugas: 30%, uts: 35%, uas:35%)

## Code program
```python
# Program Manajemen Nilai Mahasiswa

def hitung_nilai_akhir(tugas, uts, uas):
    return round((tugas * 0.3) + (uts * 0.35) + (uas * 0.35), 2)

data_mahasiswa = {}

def tambah_data():
    nim = input("Masukkan NIM: ")
    if nim in data_mahasiswa:
        print("NIM sudah terdaftar!")
        return
    nama = input("Masukkan Nama: ")
    tugas = float(input("Masukkan Nilai Tugas: "))
    uts = float(input("Masukkan Nilai UTS: "))
    uas = float(input("Masukkan Nilai UAS: "))
    nilai_akhir = hitung_nilai_akhir(tugas, uts, uas)
    data_mahasiswa[nim] = {
        "Nama": nama,
        "Tugas": tugas,
        "UTS": uts,
        "UAS": uas,
        "Nilai Akhir": nilai_akhir
    }
    print("Data berhasil ditambahkan!")

def ubah_data():
    nim = input("Masukkan NIM yang akan diubah: ")
    if nim not in data_mahasiswa:
        print("Data tidak ditemukan!")
        return
    print("Data lama:", data_mahasiswa[nim])
    nama = input("Masukkan Nama baru: ")
    tugas = float(input("Masukkan Nilai Tugas baru: "))
    uts = float(input("Masukkan Nilai UTS baru: "))
    uas = float(input("Masukkan Nilai UAS baru: "))
    nilai_akhir = hitung_nilai_akhir(tugas, uts, uas)
    data_mahasiswa[nim] = {
        "Nama": nama,
        "Tugas": tugas,
        "UTS": uts,
        "UAS": uas,
        "Nilai Akhir": nilai_akhir
    }
    print("Data berhasil diubah!")

def hapus_data():
    nim = input("Masukkan NIM yang akan dihapus: ")
    if nim in data_mahasiswa:
        del data_mahasiswa[nim]
        print("Data berhasil dihapus!")
    else:
        print("Data tidak ditemukan!")

def tampilkan_data():
    if not data_mahasiswa:
        print("Tidak ada data untuk ditampilkan!")
        return
    print(f"{'NIM':<10} {'Nama':<20} {'Tugas':<10} {'UTS':<10} {'UAS':<10} {'Nilai Akhir':<12}")
    print("-" * 70)
    for nim, info in data_mahasiswa.items():
        print(f"{nim:<10} {info['Nama']:<20} {info['Tugas']:<10} {info['UTS']:<10} {info['UAS']:<10} {info['Nilai Akhir']:<12}")

def cari_data():
    nim = input("Masukkan NIM yang dicari: ")
    if nim in data_mahasiswa:
        info = data_mahasiswa[nim]
        print(f"NIM: {nim}")
        print(f"Nama: {info['Nama']}")
        print(f"Nilai Tugas: {info['Tugas']}")
        print(f"Nilai UTS: {info['UTS']}")
        print(f"Nilai UAS: {info['UAS']}")
        print(f"Nilai Akhir: {info['Nilai Akhir']}")
    else:
        print("Data tidak ditemukan!")

while True:
    print("\nMenu:")
    print("1. Tambah Data")
    print("2. Ubah Data")
    print("3. Hapus Data")
    print("4. Tampilkan Data")
    print("5. Cari Data")
    print("6. Keluar")
    pilihan = input("Pilih menu (1-6): ")

    if pilihan == '1':
        tambah_data()
    elif pilihan == '2':
        ubah_data()
    elif pilihan == '3':
        hapus_data()
    elif pilihan == '4':
        tampilkan_data()
    elif pilihan == '5':
        cari_data()
    elif pilihan == '6':
        print("Program selesai. Terima kasih!")
        break
    else:
        print("Pilihan tidak valid, silakan coba lagi.")
```
## Output program
![Screenshot 2024-11-23 183508](https://github.com/user-attachments/assets/4066646d-24d0-4324-9dd9-d648a0bbd3aa)
![Screenshot 2024-11-23 183604](https://github.com/user-attachments/assets/9fd4b720-88cc-406d-b238-69e8b10537ec)
![Screenshot 2024-11-23 183628](https://github.com/user-attachments/assets/a02c7585-b0aa-471b-ab1e-3b93a1d71216)
![Screenshot 2024-11-23 183715](https://github.com/user-attachments/assets/23013c8f-5a56-417f-afd7-3b85fa412aed)
![Screenshot 2024-11-23 183733](https://github.com/user-attachments/assets/0383147e-9be9-47b0-b1d1-f37fc880a8c0)
![Screenshot 2024-11-23 183742](https://github.com/user-attachments/assets/7605ad98-7a3c-4c0f-9d47-753eceb6f3dc)
## Penjelasan program
1. Dictionary data_mahasiswa digunakan untuk menyimpan data mahasiswa dengan NIM sebagai kunci dan nilai berupa dictionary yang berisi nama, nilai tugas, UTS, UAS, dan nilai akhir.
2. Fungsi hitung_nilai_akhir menghitung nilai akhir berdasarkan bobot tugas, UTS, dan UAS.
3. Menu Pilihan:
  - Tambah Data: Menambahkan data mahasiswa baru.
  - Ubah Data: Mengubah data mahasiswa berdasarkan NIM.
  - Hapus Data: Menghapus data mahasiswa berdasarkan NIM.
  - Tampilkan Data: Menampilkan seluruh data mahasiswa.
  - Cari Data: Menampilkan data mahasiswa berdasarkan NIM.
  - Keluar: Menghentikan program.
4. Validasi dilakukan untuk memastikan NIM unik saat menambah data atau keberadaan NIM saat mengubah/menghapus/cari data.
## Flowchart
![Screenshot 2024-11-23 191912](https://github.com/user-attachments/assets/79fc306a-9d81-4ee4-9101-3a0f772aa23c)
