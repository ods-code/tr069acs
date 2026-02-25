# TR069 ACS — Auto Configuration Server

[English](README_EN.md)

---

## Hakkinda

TR069 ACS, modemlerin TR-069 (CWMP) protokolü üzerinden uzaktan yönetmenizi saglayan bir Windows uygulamasidir. Modem parametrelerini okuyabilir, yazabilir ve cihazlari uzaktan yapilandirabilirsiniz.

TR-069 protokolü, internet servis saglayicilarinin (ISP) müsteri modemlerini merkezi olarak yönetmek için kullandigi standart bir protokoldür. Bu uygulama, bu protokolü kullanarak tek bir bilgisayardan modemlere baglanmanizi ve onlari yönetmenizi saglar.

---

## Ne Ise Yarar?

Uygulama, bilgisayarinizi bir ACS (Auto Configuration Server) sunucusuna dönüstürür. Modeminizi Ethernet kablosu ile bilgisayariniza bagladiginizda, uygulama otomatik olarak gerekli ag altyapisini olusturur ve modemle iletisim kurar.

**DHCP Sunucu** — Modeme otomatik olarak IP adresi atar. Modem baglanti sagladiginda DHCP sunucusu devreye girer ve modeme 10.116.13.101 adresini verir. Böylece modem ile bilgisayar arasinda ag iletisimi baslar.

**PPPoE Sunucu** — Bazi modemlerin internet baglantisi kurmak için PPPoE oturumu baslatmasi gerekir. Bu sunucu, modemin PPPoE isteklerini karsilar ve oturum açmasina izin verir.

**VLAN Mirroring** — Modemler farkli VLAN etiketleri ile trafik gönderebilir. Bu özellik, modemin kullandigi VLAN etiketlerini otomatik olarak algilar ve aynalayarak iletisimin kesilmemesini saglar.

**DNS Yönlendirme** — DNS yönlendirme, tüm DNS isteklerini yakalayarak modemin sizin bilgisayariniza baglanmasini saglar.

**TR-069 / CWMP Motoru** — Modem baglanti kurduktan sonra, TR-069 protokolü üzerinden modemle haberlesme baslar. Modem Inform mesaji göndererek kendini tanitir. Ardindan GetParameterNames ile modemin destekledigi parametreleri, GetParameterValues ile mevcut degerlerini sorgulayabilir, SetParameterValues ile degerleri degistirebilirsiniz.

**Gercek Zamanli Izleme** — Tüm bu islemler web arayüzünde anlik olarak takip edilir. Modem baglandiginda, parametre sorguladiginda veya bir hata olusugunda aninda bildirim alinir.

---

## Nasil Calisir?

1. Uygulamayi baslatin. Web arayüzü tarayicinizda otomatik olarak açilir.

2. Sol panelden modeminizin bagli oldugu ag arayüzünü (Ethernet portu) seçin.

3. DHCP sunucusunu etkinlestirin. Modem otomatik olarak IP adresi alacaktir.

4. DNS yönlendirmeyi etkinlestirin. Modem ACS sunucusunu bulmaya çalistiginda, istekler bilgisayariniza yönlendirilecektir.

5. Modeminizi yeniden baslatin veya modem üzerinden ACS baglantisini tetikleyin. Modem, TR-069 protokolü üzerinden sunucunuza Inform mesaji gönderecektir.

6. Dashboard ekraninda baglanan modemi göreceksiniz. Buradan parametre okuma, yazma ve cihaz yönetimi islemlerini yapabilirsiniz.

---

## Ag Yapilandirmasi

Uygulama asagidaki ag yapilandimasini otomatik olarak olusturur:

- Bilgisayar IP adresi: 10.116.13.100
- Modem IP adresi: 10.116.13.101 (DHCP ile atanir)
- Web arayüzü: port 80
- ACS sunucu portlari: 7547, 8000, 8010, 8015

Birden fazla ACS portu, farkli modemlerin farkli portlara baglanmasi durumunda esneklik saglar.

---

## Sistem Gereksinimleri

- Windows 10 veya Windows 11
- Modeme dogrudan Ethernet baglantisi
- Yönetici yetkisi (port 80 ve raw socket erisimi için)

---

Powered by **OnDiso**
https://ondiso.net
