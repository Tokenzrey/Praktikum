### 1
- Berapa banyak packet yang terekam pada file pcapng?
  ![image](https://github.com/user-attachments/assets/ef9e9957-5680-4fdb-aa53-c8e7be3ddd13)
  Terdapat tulisan Packets : 1089, yang menandakan bahwa terdapat 1089 packet yang terekam wireshark
- Ada berapa jenis protocol yang terekam pada traffic?
  Pilih "Statistics" > "Protocol Hierarchy" dari menu `Wireshark`
- Ada berapa jenis protocol yang terekam pada traffic?
  ![image](https://github.com/user-attachments/assets/165fb490-5cf0-4010-8f6d-6439980aec07)
  Dapat terihat ada 4 protocol yang ketlihatan yaitu ssdp,mdns,tcp,http
- sebutkan secara berurutan berdasarkan alfabet menurun dengan koma sebagai separator dan dalam bentuk uppercase
contoh: PROTOCOL1,PROTOCOL2
  HTTP,MDNS,SSDP,TCP
> Correct! Here is your flag: JARKOM24{K4mu_K3r3n_CIW9AL18UPDEPR5BKRA4TLHMTDEIWE0xL4ughn8hkowbbbx3betki0lrnaa7}

### 2
- Berapa banyak packet berbasis TCP yang memiliki flag [RST, ACK]?
  ```sh
  tcp.flags == 0x14
  ```
  ![image](https://github.com/user-attachments/assets/e401ccc2-b9b6-4b21-92aa-c707d059d79b)
  Terdapat tulisan Displayed : 411, yang menandakan bahwa terdapat 411 packet yang terfilter oleh wireshark
  
- Berapa banyak packet berbasis TCP yang hanya memiliki flag [SYN]?
  ```sh
  tcp.flags == 0x0002
  ``` 
  ![image](https://github.com/user-attachments/assets/f45a08eb-5318-4002-aa64-5b8f5e88bf02)
  Terdapat tulisan Displayed : 412, yang menandakan bahwa terdapat 412 packet yang terfilter oleh wireshark
  
- Berapa banyak packet berbasis TCP yang memiliki flag ack, tapi tidak memiliki syn, dan tidak memiliki rst
  ```sh
  tcp.flags.ack == 1 && tcp.flags.syn == 0 && tcp.flags.reset == 0
  ``` 
  ![image](https://github.com/user-attachments/assets/f3d1dd6b-644d-4d0f-a4c3-c511d6e508a6)
  Terdapat tulisan Displayed : 217, yang menandakan bahwa terdapat 217 packet yang terfilter oleh wireshark
> Correct! Here is your flag: JARKOM24{W0w_4nother_Sh0t_KSIIHRJWLWH0mptygejyqcuvuxucjcuziayeM4r124132861069059514272}

### 3
- Berapa banyak packet berbasis TCP yang memiliki flag [RST, ACK]?
  ```sh
  http
  ```
  ![image](https://github.com/user-attachments/assets/cb95553a-c6d6-4071-b330-df000e41e5b5)

  Pada `Get/ HTTP/1.1` terdapat info HOST di Hypertext Transfer Protocol. Terulis dia running di localhost:9282
  Artinya port = 9282
  
- Berapa jumlah file yang terdapat pada servers ?
  ```sh
  tcp.flags == 0x0002
  ``` 
  ![image](https://github.com/user-attachments/assets/f45a08eb-5318-4002-aa64-5b8f5e88bf02)
  Pada `/ HTTP/1.0 200 OK` terdapat info HTML yang dikirim dari server pada Line-Based text data
  Telrihat bahwa pada list direcotry nya terdapat 4 file
  
- Sebutkan nama filenya dalam urutan alphabet, lalu UPPERCASE, dan separator `,`
  file.pdf,hello.html,lion.jpg,present.pptx
> Correct! Here is your flag: JARKOM24{Y0u_4r3_4_g00d_4nalyz3r_GKTNKL1tsuixueu6e8411eqpqtzowcg}
