# OSI MODELİ NEDİR ?

OSI(Open Systems Interconnection) modeli ; iki bilgisayar arasındaki iletişimin
nasıl olacağını tanımlayan ve bu tanımlamayı 7 katman biçiminde açıklayan bir
modelleme sistemidir.

Bu modelin ortaya çıkmasındaki ihtiyaç ; bilgisayar ağlarının ortaya ilk çıktığı
zamanlarda aynı üreticiye sahip cihazların sadece kendi aralarında iletişim
kurabiliyor olmasıydı.Bu sorunu ortadan kaldırmak için
ISO (International Organization for Standardization) tarafından OSİ modellemesi
oluşturuldu ve farklı üreticilerin ürettiği cihazlar aynı ağ üzerinden
haberleşme ve iletişim sağlayabilecek duruma geldiler.

Osi ile ilgili ayrıntılı bilgiye sahip olmak için ;

[Buraya tıklayınız..](https://tr.wikipedia.org/wiki/OSI_modeli#cite_note-a1-1)

Bu yazımızda OSİ modelinin 4. katmanı olan Taşıma/İletim katamanına değineceğiz.

# TAŞIMA İLETİM KATMANI

Taşıma-iletim katmanı uzunlukları değişken olan verilerin kaynak cihazdan
hedef cihaza bir ağ (birden çokta olabilir) üzerinden içerik verileri
koruyarak güvenli bir şekilde iletimini amaçlar.

Bu iletimi yaparken verilen bağlantı üzerinden verileri parçalara bölüp sonra bu
parçaları tekrar birleştirerek veri iletimini sağlar.Bu bölme ve birleştirme
işlemleri iletilen verilerin daha güvenli ve doğru iletimine olanak sağlar.

Bu katmanda iletilen verilerin hata kontrolleri yapılır ve iletimin başarısız
olması durumunda tekrar veri aktarımı, iletimin başarılı olması durumunda ise
verinin akratıldığına dair başarı mesajı olur.

Şimdi bu aktarımda rol oynayan protokolleri listeleyelim.

- TCP Protokolü

- UDP Protokolü
