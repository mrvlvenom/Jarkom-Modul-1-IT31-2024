# Jarkom-Modul-1-IT31-2024

| No | Nama | NRP |
|---|---|---|
| 1 | M. Januar Eko Wicaksono | 50272221006 |
| 2 | SUbkhan Mas Udi | 50272221044 |

## Pengerjaan Soal
### 1. ATM or ATP ot FTP ?
---
### Problem
Pradityo mencoba mengembangkan server ftp, tetapi seseorang mencoba melakukan bruteforce login, bisakah Anda menganalisis apa yang terjadi?

author: youdaemon

nc 10.15.40.20 10004
No 4:                                                                                         Pertanyaan: Apa password yang berhasil didapatkan oleh hacker setelah melakukan bruteforce login ftp?                   
Format: strings                     
### Solution
Untuk problem tersebut kita menggunakan
```bash
frame contains "successful"
```
karena pada soal terdapat poin yang berhasil untuk login, jadi kita langsung mencari kata "successful" yang merujuk pada "login successful", seperti gambar dibawah ini:
![](https://github.com/mrvlvenom/Jarkom-Modul-1-IT31-2024/blob/main/img/atm1.png)

Kemudian kami melihat Follow TCP Stream, dan menemukan password hacker yang berhasil melakukan bruteforce login.
![](https://github.com/mrvlvenom/Jarkom-Modul-1-IT31-2024/blob/main/img/atm2.png)

Setelah itu, kita masukkan password tersebut ke dalam terminal linux untuk mendapatkan flag yang dituju:
![](https://github.com/mrvlvenom/Jarkom-Modul-1-IT31-2024/blob/main/img/atm.png)

Kemudian, kami berhasil menemukan flag yang diinginkan, dan saat kami submit di CTFd, ternyata benar untuk flag tersebut.

### 2. How Many packets?
---
### Problem
Sebagai kewajiban untuk laporan, aku diminta untuk mencari tahu berapa kali attempt login yang dilakukan oleh hacker. Dapatkah kamu membantuku untuk menganalisanya?

attachment: same as ATM or ATP or FTP ? 🤔

author: youdaemon

nc 10.15.40.20 10005
No 5:                                                                                      Pertanyaan: Berapa total attempt login(bruteforce) yang dilakukan oleh hacker?                Format: number
### Solution
Untuk problem ini kita menggunakan hal yang sama seperti soal sebelumnya, tetapi dengan kata "Incorrect" karena pada soal diminta total attempt untuk login (bruteforce) yang dilakukan oleh hacker
```bash
frame contains "Incorrect"
```
Kemudian muncul seperti pada gambar dibawah:


### 3. Trace him
---
### Problem
Selain menghitung jumlah packet, coba lacak juga ip penyerang tersebut!

attachment: same as ATM or ATP or FTP ? 🤔

author: youdaemon

nc 10.15.40.20 10006

### 4. Creds
---
### Problem
Attacker menyadari jika dia bisa membuat clone ftp server dari target, temukan kredensialn dari server ftp yang dibuat oleh attacker

author: youdaemon

nc 10.15.40.20 10007

### Solution

### 5. Malwleowleo
---
### Problem
Dapatkah kamu menemukan file malware yang dikirim oleh attacker melalui ftp?

attachment: same as creds

author: youdaemon

nc 10.15.40.20 10008

### Solution

### 6. Whoami
---
### Problem
Dapatkah kamu menemukan siapa identitas attacker?

attachment: same as creds

author: youdaemon

nc 10.15.40.20 10009

### Solution

### 7. Secret
---
### Problem
Temukan pesan rahasia dari attacker

attachment: same as creds

author: youdaemon

nc 10.15.40.20 10010

### Solution

### 8. Evidence
---
### Problem
Perusahaan nanomate baru saja kebobolan. Mereka menyewamu untuk mencari tahu bagaimana caranya pelaku bisa masuk.

Attachment: attachment Author: kiseki

nc 10.15.40.20 10002

### Solution

### 9. Fuzz
---
### Problem
My website got hacked. Can you analyze this network traffic to help me track the attacker?

Attachment: here

Author: kiseki

nc 10.15.40.20 10001

### Solution
