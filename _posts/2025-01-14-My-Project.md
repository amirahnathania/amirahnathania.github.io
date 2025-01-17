---
title: 👩🏻‍💻 My Project 👩🏻‍💻
date: 2025-01-14 
categories: [project, me]
tags: [Project]             # TAG names should always be lowercase
media_subpath : /assets/media/
description: Haii, ini projek saya selama S1 
image:
    path: /Background.jpeg
---

Selama masa kuliah di jurusan informatika, saya aktif berpartisipasi dalam berbagai kegiatan dan proyek yang mendukung pengembangan keterampilan teknis dan kerja sama tim. Saya terlibat dalam kompetisi yang relevan dengan bidang teknologi, yang membantu saya memperdalam pengetahuan dan pengalaman praktid. Komitmen ini mencerminkan antusiasme saya terhadap inovasi dan kontribusi dalam dunia informatika.

## Project Buat Game 
#### 1. Tebak Angka 

```
import random

print ("Selamat datang di Game Tebak Angka :)")

# Masukkan jumlah pemain dan nama-nama pemain
jumlah_pemain = int(input("Masukkan jumlah pemain: "))
pemain = []
for i in range(jumlah_pemain):
    nama = input(f"Masukkan nama pemain {i + 1}: ")
    pemain.append(nama)

# Memilih angka target
target_number = random.randint(1, 100)
print("Sebuah angka telah dipilih antara 1-100. Siapakah yang dapat menebaknya?")

print("\nPermainan dimulai!")
tebakan_benar = False
turn = 0

while not tebakan_benar:
    pemain_sekarang = pemain[turn % jumlah_pemain] # Tentukan pemain yang sedang menebak
    tebak = int(input(f"{pemain_sekarang}, masukkan tebakan anda: "))

    if tebak == target_number:
        print(f"Selamat {pemain_sekarang}! Anda telah menebak angka yang benar: {target_number}")
        tebakan_benar = True
    elif tebak < target_number:
        print("Terlalu kecil! Coba lagi :(")
    else:
        print("Terlalu besar! Coba lagi :(")
    
    turn += 1       # Pindah ke giliran pemain berikutnyya

print("Permainan selesai. Terima kasih telah bermain :)")
```

Kode ini merupakan program permainan Tebak angka berbasis terminal (console) yang mendukung mode multi-pemain. Program ini dirancang untuk menghibur pemain dengan tantangan menebak angka acak antara 1 hingga 100. Tujuan dari game ini untuk memberikan pengalaman bermain game tebak angka secara interaktif, Melatih logika pemain dalam memperkirakan angka target berdasarkan petunjuk  ("Terlalu besar" atau "Terlalu kecil"), dan mendukung permainan dengan beberapa pemain secara bergantian. 

#### 2. TicTacToe

```
# Fungsi untuk mencetak papan permainan
def print_board(board):
    print("TICTACTOE")
    print("==========")
    print(f"|{board[0]}|{board[1]}|{board[2]}|")
    print("----------")
    print(f"|{board[3]}|{board[4]}|{board[5]}|")
    print("----------")
    print(f"|{board[6]}|{board[7]}|{board[8]}|")
    print()

# Fungsi untuk mengecek apakah ada pemenang
def check_win(board, player):
    win_conditions = [
        [0, 1, 2], [3, 4, 5], [6, 7, 8],  # Baris
        [0, 3, 6], [1, 4, 7], [2, 5, 8],  # Kolom
        [0, 4, 8], [2, 4, 6]              # Diagonal
    ]
    for condition in win_conditions:
        if board[condition[0]] == board[condition[1]] == board[condition[2]] == player:
            return True
    return False

# Fungsi utama untuk permainan
def tic_tac_toe():
    board = ['1', '2', '3', '4', '5', '6', '7', '8', ] # Untuk mewakili posisi yang dapat di pilih pemain
    players = ['X', 'O'] # Simbol untuk pemain
    turn = 0  # 0 untuk Player 1 (X), 1 untuk Player 2 (O)

    while True:
        print_board(board)
        current_player = players[turn % 2] 
        move = input(f"Player {turn % 2 + 1} ({current_player}): ")
        
        # Validasi input
        if move.isdigit() and int(move) in range(1, 10) and board[int(move) - 1] not in players:
            board[int(move) - 1] = current_player
        else:
            print("Pilihan tidak valid, silakan coba lagi.")
            continue

        # Mengecek kemenangan
        if check_win(board, current_player):
            print_board(board)
            print(f"Player {turn % 2 + 1} ({current_player}) WIN!!")
            break

        # Mengecek apakah papan penuh
        if turn == 8:  # 9 langkah tanpa pemenang berarti draw
            print_board(board)
            print("DRAW!")
            break

        turn += 1

# Menjalankan permainan
tic_tac_toe()
```

Kode ini adalah implementasi dari permainan Tic Tac Toe berbasis teks. Permainan ini dimainkan oleh dua pemain secara bergantian, dengan tujuan membuat garis lurus tiga simbol yang sama (baik horizontal, vertikal maupun diagonal) di papan permainan. Tujuan dari game ini untuk Membuat versi sederhana dari permainan Tic Tac Toe yang dapat dimainkan melalui terminal, Mengembangkan logika permainan berbasis giliran untuk dua pemain dan Menyediakan pengalaman bermain dengan validasi input dan deteksi kemenangan atau hasil imbang.

## Desain Prototype 
![Foto 6](/Prototype.png){: width="500" height="500" }
_Prototype Suara-Ku!_

Proyek ini melibatkan pengembangan prototype aplikasi Suara-Ku!, sebuah platform seluler yang membantu mendidik, mendukung dan mengadvokasi korban kekerasan, khususnya pada remaja. Pada aplikasi ini dikembang oleh tim dengan faktor yang kuat pada desain antarmuka pengguna (UI) yang intuitif dan fungsional. Aplikasi ini bertujuan untuk menciptakan solusi digital yang mendukung edukasi dan pemberdayaan komunitas, sekaligus memperhatikan kemampuan kerja sama tim dalam pengembangan produk tertentu. Berikut beberapa fitur utama yang ditampilkan dalam prototype:
1. Halaman Splash Screen 
2. Halaman Login
3. Dashboard Utama 
4. Halaman Form Data Pendamping 

Aplikasi ini dikembang oleh tim dengan pembagian tugas yang terstruk, dimana setiap anggota memiliki peran yang spesifik. Proses pengembangannya meliputi : 
1. Desain UI/UX yang dimana merancang layout yang user-friendly dan estetis untuk memberikan pengalaman pengguna yang optimal.
2. Impemenatasi Fitur yang dimana Mengintegrasi elemen fungsional, seperti autentikasi pengguna dab form pengisian data.
3. Pengujian Prototype yang dimana Memastikan fitur berjalan dengan baik sesuai kebutuhan pengguna target.

Sebagai bagian dari tim ini, saya turut berkontribusi dalam mengembangkan aplikasi yang efektif dan bermakna untuk mendukung solusi digital
