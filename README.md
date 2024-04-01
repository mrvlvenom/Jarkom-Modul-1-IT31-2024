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

No 4:                                                                                     

Pertanyaan: Apa password yang berhasil didapatkan oleh hacker setelah melakukan bruteforce login ftp?                   

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

No 5:                                                                                      

Pertanyaan: Berapa total attempt login(bruteforce) yang dilakukan oleh hacker?               

Format: number

### Solution
Untuk problem ini kita menggunakan hal yang sama seperti soal sebelumnya, tetapi dengan kata "Incorrect" karena pada soal diminta total attempt untuk login (bruteforce) yang dilakukan oleh hacker
```bash
frame contains "Incorrect"
```
Kemudian muncul seperti pada gambar dibawah:
![](https://github.com/mrvlvenom/Jarkom-Modul-1-IT31-2024/blob/main/img/hmp1.png)

Dan kami menentukan untuk jumlahnya dari packets dibawah pojok kanan bawah tersebut yang berjumlah 934, jadi hasil keseluruhannya adalah 934 attempt untuk login (bruteforce) oleh hacker. 

Kemudian kita coba memasukkan ke dalam terminal linux, dan berhasil mendapat flag yang diiinginkan. Dan saat kami submit di CTFd, ternyata benar untuk flag tersebut.
![](https://github.com/mrvlvenom/Jarkom-Modul-1-IT31-2024/blob/main/img/hmp.png)

### 3. Trace him
---
### Problem
Selain menghitung jumlah packet, coba lacak juga ip penyerang tersebut!

attachment: same as ATM or ATP or FTP ? 🤔

author: youdaemon

nc 10.15.40.20 10006

No 6:                     

Pertanyaan: Alamat IP attacker?  

Format: xxx.xxx.xxx.xxx

### Solution
Untuk menemukan alamat dari IP attacker kita mencoba menggunakan Destination IP Attacker yang selalu sama setiap login seperti gambar dibawah ini:
![](https://github.com/mrvlvenom/Jarkom-Modul-1-IT31-2024/blob/main/img/hmp1.png)

Jadi kami mencoba untuk memasukkan ke dalam terminal linux, dan ternyata berhasil menemukan flag yang diinginkan, kemudian kita submit di CTFd, dan ternyata benar untuk flag tersebut.
![](https://github.com/mrvlvenom/Jarkom-Modul-1-IT31-2024/blob/main/img/th.png)

### 4. Creds
---
### Problem
Attacker menyadari jika dia bisa membuat clone ftp server dari target, temukan kredensialn dari server ftp yang dibuat oleh attacker

author: youdaemon

nc 10.15.40.20 10007

No 1:                     

Pertanyaan: Apa Username FTP yang digunakan oleh attacker?                                   

Format: USER:username

No 2:

Pertanyaan: Apa Password FTP yang digunakan oleh attacker?

Format: PASS:password

### Solution
1. Untuk problem nomor 1 kita mencoba mencari username nya sama seperti soal ATM, yaitu dengan :
```bash
frame contains "successful"
```
Kemudian kita mendapatkan hasil seperti gambar dibawah ini:
![](https://github.com/mrvlvenom/Jarkom-Modul-1-IT31-2024/blob/main/img/Creds2.png)

Dan kita coba berhasil (Hasil di akhir), sehingga lanjut ke soal nomor 2

2. Untuk menemukan password dari attacker itu sendiri sama seperti nomor 1 langsung ketemu username dan passwordnya seperti gambar dibawah ini:
![](https://github.com/mrvlvenom/Jarkom-Modul-1-IT31-2024/blob/main/img/Creds1.png)

Kemudian berhasil menemukan flag yang diinginkan, dan kita coba untuk submit, dan hasilnya benar untuk flag nya.
![](https://github.com/mrvlvenom/Jarkom-Modul-1-IT31-2024/blob/main/img/Creds.png)

### 5. Malwleowleo
---
### Problem
Dapatkah kamu menemukan file malware yang dikirim oleh attacker melalui ftp?

attachment: same as creds

author: youdaemon

nc 10.15.40.20 10008

No 8:                     

Pertanyaan: Apa nama malware yang dikirim oleh attacker ke korban?                        

Format: strings 

### Solution
Untuk mencari nama malware itu sendiri kita mendapatkannya dari stream yang sama, seperti foto di soal creds diatas, dengan hasil seperti gambar dibawah ini:
![](https://github.com/mrvlvenom/Jarkom-Modul-1-IT31-2024/blob/main/img/mlamewe1.png)

Kemudian kita coba untuk dimasukkan ke dalam terminal linux, dan ternyata berhasil mendapatkan flag yang diinginkan. Setelah itu kita coba untuk submit di CTFd, dan berhasil di submit.
![](https://github.com/mrvlvenom/Jarkom-Modul-1-IT31-2024/blob/main/img/mlamewe.png)

### 6. Whoami
---
### Problem
Dapatkah kamu menemukan siapa identitas attacker?

attachment: same as creds

author: youdaemon

nc 10.15.40.20 10009

No 9:                     

Pertanyaan: Siapa nama attacker yang sudah melakukan serangan ini?                            

Format: FirstName_LastName 

### Solution
Untuk problem diatas, kita melakukan pencarian dengan menggunakan:
```bash
tcp.streaem eq "nomor"
```
Kemudian ketemu pada saat stream 7, dengan hasil seperti gambar dibawah ini:
![](https://github.com/mrvlvenom/Jarkom-Modul-1-IT31-2024/blob/main/img/whoami1.png)

Karena formatnya seperti base64, kita mencoba untuk men-decode menggunakan decode base64 dari web (online), dan hasilnya seperti gambar dibawah:
![](https://github.com/mrvlvenom/Jarkom-Modul-1-IT31-2024/blob/main/img/whoami2.png)

Dan hasil namanya adalah Paul Atreides,  kita langsung masukkan sesuai format yaitu Paul-Atreides. Dan mendapatkan flag yang diinginkan. Setelah itu di submit di CTFd, dan hasilnya benar.
![](https://github.com/mrvlvenom/Jarkom-Modul-1-IT31-2024/blob/main/img/whoami.png)

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
