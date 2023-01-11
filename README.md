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