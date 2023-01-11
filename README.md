# Project-UAS-UPB
# Profil
Nama: Yudha Eka P
NIM: 312210362
Kelas: TI.22.A4
Mata Kuliah: Bahasa Pemrograman
# UAS
# Buatlah package dan modul dengan struktur seperti berikut:
   - daftar_nilai.py berisi modul untuk: tambah_data, ubah_data, hapus_data, dan cari_data
   - view_nilai.py berisi modul untuk: cetak_daftar, cetak_pencarian
   - input_nilai.py berisi modul untuk: input_data, yang meminta pengguna memasukkan data.
   - main.py berisi program utama (menu pilihan yang memanggil semua menu yang ada)
# main.py Berisi program utama dengan menu, menu = input("[(T)ambah, (I)nputNilai, (L)ihat, (C)ari, (H)apus, (K)eluar] : ")

~~~sh
import Modul as m
import view as v
import os



print("="*20)
print("|PROGRAM INPUT DATA|")
print("="*20)

while True: 
    print()
    menu = input("[(T)ambah, (L)ihat, (C)ari, (H)apus, (U)bah, (K)eluar] : ")
    print("~"*78)
    print()
    os.system("cls")

    if menu.lower() == 't':
        m.tambah_data()

    elif menu.lower() == "l":
        v.cetak_daftar()

    elif menu.lower() == 'c':
        m.cari_data()
        v.cetak_pencarian()

    elif menu.lower() == "h":
        m.hapus_data()

    elif menu.lower() == "u":
       m.ubah_data()

    elif menu.lower() == "k":
        print("Program selesai, Terima Kasih :) ")
        break

    else:
        print("\n INPUT {} TIDAK ADA!, Silakan pilih [T/L/I/H/U/K] untuk menjalankan program!".format(menu))
~~~

# Penjelasan

Di program utama ini terdapat modul yang di import ke file form view import input_nilai, view_nilai & from model import daftar_nilai. Modul memungkinkan anda menulis kode yang terdiri dari beberapa file dan membaginya menjadi bagian-bagian yang lebih kecil, yang dapat sesuai diimport sesuai kebutuhan.

# Contoh tampilan menu


![img](gambar/RB%2013.jpeg)

# 2. daftar_nilai.py
  
  Di dalam file daftar nilai ini terdapat sourcecode input("[(T)ambah, (C)ari, (H)apus, (U)bah] ")

  ~~~sh
  import view as v 
import Modul as m
Data={}
def tambah_data(): 
    print ("TAMBAH_DATA")
    v.input_data()
    print("DATA BERHASIL DI TAMBAHKAN")
def ubah_data():
    print ("UBAH_DATA")
    cari = str(input("MASUKAN NAMA: "))
    if cari in m.Data.keys():
        v.input_data()
        print("DATA BERHASIL DI UBAH")

    else: 
        print("DATA TIDAK DITEMUKAN")
def hapus_data():
    print ("HAPUS_DATA")
    cari = str(input("MASUKAN NAMA: "))
    if cari in m.Data.keys():
        del m.Data[cari]
        print("DATA BERHASIL DI HAPUS")

    else: 
        print("DATA TIDAK DITEMUKAN")
    
def cari_data():
   print ("CARI DATA") 
   v.cetak_pencarian
  ~~~

  # Penjelasan 
    Pada bagian dari daftar_nilai.py berisi program dengan perintah menambahkan data, hapus data, ubah nim, dan mencari salah satu data yang sudah di input.

# Tampilkan output tambah data :

![img](gambar/RB%2013.jpeg)


# Tampilkan ubah data :

![img](gambar/RB%2014.jpeg)


# Tampilkan hapus data :


![img](gambar/RB%2015.jpeg)


# 3. view_nilai.py berisi sourcecode yang berfungsi menampilkan seluruh data 

~~~sh
import Modul as m
def cetak_daftar():
    if m.Data.items():
        print("="* 84)
        print(f"|{'DATA MAHASISWA':^82}|")
        print("="* 84)
        print(f"|{'N0':^4}|{'NAMA':^20}|{'NIM':^20}|{'TUGAS':^10}|{'UTS':^6}|{'UAS':^6}|{'AKHIR':^10}|")
        n = 0
        for i in m.Data.items():
            n += 1
            print(f"|{n:^4}|{i[1][0]:^20}|{i[1][1]:^20}|{i[1][2]:^10}|{i[1][3]:^6}|{i[1][4]:^6}|{i[1][5]:^10}|")
        print("="* 84)
    else:
        print("="* 84)
        print(f"|{'TIDAK ADA DATA':^82}|")
        print("="* 84)
def cetak_pencarian():
    cari = str(input('MASUKAN NAMA: '))
    if cari in m.Data.keys():
        print("="* 84)
        print(f"|{'DATA MAHASISWA':^82}|")
        print("="* 84)
        print(f"|{'N0':^4}|{'NAMA':^20}|{'NIM':^20}|{'TUGAS':^10}|{'UTS':^6}|{'UAS':^6}|{'AKHIR':^10}|")
        n = 0
        for i in m.Data.items():
            n += 1
            print(f"|{n:^4}|{m.Data[cari][0]:^20}|{m.Data[cari][1]:^20}|{m.Data[cari][2]:^10}|{m.Data[cari][3]:^6}|{m.Data[cari][4]:^6}|{m.Data[cari][5]:^10}|")
        print("="* 84)
    else:
        print("="* 84)
        print(f"|{'TIDAK ADA DATA':^82}|")
        print("="* 84)
~~~

# Penjelasan

Di program ini terdapat modul yg menyambungkan view_nilai.py kedalam file program daftar_nilai.py dengan syntax from model import daftar_nilai. Fungsi ny mirip seperti input = "[(C)ari]", tapi fitur ini menampilkan seluruh data yg sudah di input.

# input_nilai.py berisi code yang berfungsi untuk menginput data yaitu nilai

~~~sh
import Modul as m
def input_data():
    nama = str(input("nama\t\t: "))
    nim = str(input("nim\t\t: "))
    tugas =int(input("tugas\t\t: "))
    uts = int(input("uts\t\t: "))
    uas = int(input("uas\t\t: "))
    akhir = round(float(tugas * 0.30 + uts * 0.35 + uas * 0.35),2)
    m.Data [nama]=nama, nim, tugas, uts, uas, akhir
~~~

# Penjelasan

Di program ini terdapat modul yg menyambungkann input_nilai.py kedalam file program daftar_nilai.py dengan syntax from model import daftar_nilai. Fitur ini khusus untuk menginput nilai

