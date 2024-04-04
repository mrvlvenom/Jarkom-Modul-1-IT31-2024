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
3. 
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

No 10:         

Pertanyaan: Ternyata attacker menyisipkan file lainnya selain dari file malware, temukan pesan yg dikutip oleh attacker?

Format: strings 

### Solution
Untuk problem tersebut kita mencari nya sama seperti sebelumnya, dan mendapatkan kejanggalan pada stream 14, yang dimana ada sebuah file foto. Kita mencoba untuk mendownloadnya, dengan export object -> FTP-DATA dan di save.

![](https://github.com/mrvlvenom/Jarkom-Modul-1-IT31-2024/blob/main/img/secret2.png)
Setelah itu kita buka dan hasil dari pesan yang dikutip seperti ini:

![](https://github.com/mrvlvenom/Jarkom-Modul-1-IT31-2024/blob/main/img/secret1.png)

Kemudian kita mencoba untuk memasukkan dalam terminal linux dan berhasil menemukan flagnya, Setelah itu di submit di CTFd, dan benar hasilnya.

![](https://github.com/mrvlvenom/Jarkom-Modul-1-IT31-2024/blob/main/img/secret.png)

### 8. Evidence
---
### Problem
Perusahaan nanomate baru saja kebobolan. Mereka menyewamu untuk mencari tahu bagaimana caranya pelaku bisa masuk.

Attachment: attachment Author: kiseki

nc 10.15.40.20 10002

No 1:             

Pertanyaan: Apa domain milik korban?

Format: xxxxxx.xxx: e.g. google.com 

No 2:             

Pertanyaan: Apa web server yang digunakan oleh korban?

Format: name-version: e.h. nginx-1.18.0 

No 3:             

Pertanyaan: Apa endpoint yang digunakan untuk login sebagai user biasa?

Format: /path/to/endpoint

No 4:             

Pertanyaan: Apa email dan password yang berhasil digunakan untuk login sebagai user biasa?

Format: email:password 

### Solution

1. Untuk solusi soal pertama, karena yang dipertanyakan adalah domain milik korban, jadi kita mencari "Host" nya langsung, dan langsung ketemu domainnya yaitu nanomate-solution.com. Seperti gambar dibawah:

![](https://github.com/mrvlvenom/Jarkom-Modul-1-IT31-2024/blob/main/img/evidence1.png)

Setelah ketemu, langsung dimasukkan ke dalam terminal linux, dan benar. Kemudian lanjut ke soal berikutnya.

2. Untuk solusi soal kedua, untuk web server itu sendiri sama seperti foto sebelumnya, terdapat nama server disana yaitu apache dengan versi 2.4.56.

![](https://github.com/mrvlvenom/Jarkom-Modul-1-IT31-2024/blob/main/img/evidence1.png)

Setelah ketemu, langsung dimasukkan ke dalam terminal linux, dan benar. Kemudian lanjut ke soal berikutnya.
   
3. Untuk solusi soal ketiga, karena diminta endpoint untuk login sebagai user biasa. Dan ketika dilihat itu sebagian besar web. Jadi, untuk endpointnya bisa didapatkan dari "POST" suatu web. Karena login dari user akan masuk ke dalam "POST suatu web, dan includes/masuk ke database web nya. Jadi pertama kita cari memakai:

```bash
frame contains "POST"
```
Dan setelah menemukan banyak POST dalam source Wireshark tersebut, kami mencari yang terkait dengan CSS-login pada situs web tersebut. Kami kemudian menemukan jalur "/app/includes/process_login.php" yang berisi data POST dari login situs web tersebut yang berhubungan dengan database.

![](https://github.com/mrvlvenom/Jarkom-Modul-1-IT31-2024/blob/main/img/evidence2.png)
Jadi langsung kita coba ke terminal, dan akhirnya berhasil. Kemudian lanjut ke soal berikutnya.

4. Untuk solusi soal keempat, disitu terdapat poin jika user berhasil login sebagai user biasa. Berarti langsung kita cari mana login yang berhasil/succesfull tetapi tetep mencari di "POST" path login, dengan cara yang sama seperti sebelumnya:

```bash
frame contains "POST"
```
Dan kita langsung menemukan yang login successfull seperti gambar dibawah:

![](https://github.com/mrvlvenom/Jarkom-Modul-1-IT31-2024/blob/main/img/evidence3.png)

Setelah kita menemukan jawaban yang benar pada soal nomor 4, kemudian kita masukkan ke terminal linux sesuai format yang benar, Dan kita mendapatkan flag yang diinginkan. Kemudian di submit di CTFd, dan hasilnya benar.

![](https://github.com/mrvlvenom/Jarkom-Modul-1-IT31-2024/blob/main/img/evidence.png)

### 9. Fuzz
---
### Problem
My website got hacked. Can you analyze this network traffic to help me track the attacker?

Attachment: here

Author: kiseki

nc 10.15.40.20 10001

No. 1:

Pertanyaan: Apa IP Adress milik attacker?
Format: xxx.xxx.xxx.xxx

No. 2:

Pertanyaan: Apa port yang digunakan sebagai web server korban?
Format: xxxx: e.g. 22

No.3:

Pertanyaan: Apa endpoint yang digunakan untuk login?
Format: /path/to/endpoint

No 4: 

Pertanyaan: Apa tool yang digunakan oleh attacker untuk bruteforce login?
Format: toolsname-version: e.g. hydra-v9.0-dev

No 5:

Pertanyaan: Apa username dan password yang berhasil digunakan oleh attacker?
Format: username:password

### Solution

1. Untuk soal pertama, kita mencoba untuk mencoba untuk melakukan port yang sering muncul (dan selalu ada login nya. Berarti kita mengiranya itu IP Address untuk attacker. Lalu kita coba dan akhirnya dapat flag yang diinginkan.

![](https://github.com/mrvlvenom/Jarkom-Modul-1-IT31-2024/blob/main/img/fuzz3.png)
 
2. Untuk soal nomor 2, yang ditanya adalah web server, dan pada saat di cek di salah satu source port sesuai soal pertama (TCP), dia menggunakan wes server HTPP, berarti menggunakan web server 80. Dan pada saat dimasukkan ke dalam soal, benar dan lanjut ke soal berikutnya.

![](https://github.com/mrvlvenom/Jarkom-Modul-1-IT31-2024/blob/main/img/fuzz4.png)

3. Untuk soal nomor 3, Untuk path itu sendiri, kita liat dari stream sebelumnya yang paling atas, Bahwa pada stream tersebut POST / , merupakan path endpoint yang digunakan untuk login ke dalam web tersebut.

![](https://github.com/mrvlvenom/Jarkom-Modul-1-IT31-2024/blob/main/img/fuzz4.png)

4. Untuk soal nomor 4, tool yang digunakan selalu untuk attacker melakukan bruteforce login adalah Fuzz Faster U Fool v2.0.0-dev pada user-agent. Karena yang diminta formatnya adalah nama singkatannya, jadi kita mencari di google untuk singkatan dari tools tersebut adalah "FFUF", dan sesuai format adalah ffuf-v2.0.0-dev, dan benar pada soal, kemudian lanjut ke soal berikutnya.

![](https://github.com/mrvlvenom/Jarkom-Modul-1-IT31-2024/blob/main/img/fuzz4.png)

5. Untuk soal nomor 5, 
