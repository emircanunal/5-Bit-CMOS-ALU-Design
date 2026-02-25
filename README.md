# 5-Bit CMOS Adder-Subtractor (VLSI Layout Design) 

Bu proje, 0.25 µm CMOS teknolojisi kullanılarak L-Edit ortamında fiziksel seviyede (layout) tasarlanmış ve T-Spice ile doğrulanmış 5-bitlik bir Toplayıcı/Çıkarıcı (Adder/Subtractor) devresidir.

##  Proje Hakkında
Tasarım, "Ripple Carry Adder" (Zincirleme Toplayıcı) mimarisine dayanmaktadır. Devre, dışarıdan verilen bir **Mode (M)** sinyali ile iki farklı işlem yapabilmektedir:
* **M = 0:** A ve B sayılarını toplar.
* **M = 1:** A sayısından B sayısını çıkarır (2'ye tamlama - 2's complement yöntemiyle).

##  Tasarım Hiyerarşisi (Design Hierarchy)
Bu proje, tasarımda standardizasyonu sağlamak amacıyla **Evrensel Kapı (Universal Gate)** mantığıyla, tamamen NAND kapıları kullanılarak aşağıdan yukarıya (bottom-up) inşa edilmiştir:

1. **NAND Kapısı:** 4 adet transistör (2 PMOS, 2 NMOS) kullanılarak temel NAND2 hücresi çizildi (DRC hatasız).
2. **XOR Kapısı:** 4 adet NAND kapısı birleştirilerek çıkarma işleminde B bitlerini ters çevirecek XOR hücresi tasarlandı.
3. **Full Adder (Tam Toplayıcı):** NAND kapıları ve XOR hücresi kullanılarak 1-bitlik Full Adder oluşturuldu.
4. **5-Bit ALU (Final):** 5 adet Full Adder ve 5 adet XOR kapısı yan yana dizilerek, elde bitleri (Carry) zincirlendi ve ana mimari tamamlandı.

##  Kullanılan Araçlar ve Teknolojiler
* **Layout Tasarımı:** Tanner L-Edit
* **Teknoloji Düğümü:** SCN 0.25µm CMOS
* **Simülasyon ve Analiz:** Tanner T-Spice / W-Edit

##  Simülasyon ve Test (Waveform)
Devrenin doğruluğu T-Spice üzerinde yazılan SPICE netlist senaryoları ile test edilmiştir. Hem toplama (örn: 10+5=15) hem de çıkarma (örn: 9-2=7) senaryoları simüle edilmiş ve S0-S4 çıkış bitlerinde beklenen Binary (İkilik) sonuçlar kusursuz olarak gözlemlenmiştir.
## Layout Tasarımı
<img width="1525" height="552" alt="5bit adder substractor design with L-Edit" src="https://github.com/user-attachments/assets/b03dbffa-ec31-4506-aa38-d0eebc6ac470" />
## Waveform 
<img width="1534" height="854" alt="waveform" src="https://github.com/user-attachments/assets/1960d602-82c4-4f28-8e76-2166c8d37b6f" />
## T-Spice kodları
<img width="1293" height="437" alt="1" src="https://github.com/user-attachments/assets/6e079528-f00a-4d9b-b92e-f50ca4e914f7" />
<img width="982" height="482" alt="2" src="https://github.com/user-attachments/assets/b3cf8a82-ca4e-474b-a6d2-1fe134f2576a" />


