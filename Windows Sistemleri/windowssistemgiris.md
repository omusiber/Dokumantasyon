# CMD KOMUTLARI
## Windowsta cmd komutlarını anlatmaya başlamadan önce cmd nin ne olduğuna bakalım.
## NEDİR BU CMD?
Cmd(Ms-dos) : Bigisayarda bazı komutları uygulayabilmemizi sağlayan ms-dos tabanlı bir konsoldur.
Cmd yi açabimek için sırasıyla: Başlat=>Çalıştır=>cmd işlemleri yapılır.
Komut istemi, tüm Windows sürümlerinde aynıdır ve bir farklılık göstermez.        
*** MS-DOS(Microsoft Disk Operating System = Microsoft Disk İşletim Sistemi)

 Komut satırını açmayı öğrendiğimize göre yavaş yavaş cmd komutlarını öğrenip deneyebiliriz.

Bir dosya adı verildiğinde sadece onun içindeki bilgileri gosterir.

  ***C:\>DIR (Sabit diskin ana klasöründeki tüm dosyaları ve klasörleri listeler).
 C:\ODEV>DIR (Oyun klasörü altındaki dosya ve alt klasörleri listeler).

### 1- dir(Directory)

Dir komutu içinde bulunduğunuz dizindeki tüm dosya ve klasorleri,son degistirime zamanlarını ve dosya boyutlarını gosterir.
Dir komutunun birçok parametresi bulunmaktadır.Bu komutlar:

/A (Attrib): Niteliklerine göre dosyaları listeler.

Dosyalar 4 niteliğe sahip olabilir : h (Hidden-Gizli), a (Archive-Arşiv), s (System-Sistem), r (Read only- Sadece okunabilir).
*  dir /a
   dir komutuyla /a parametresi kullanıldığında gizli sistem dosya ve dizinler dahil,tümünü listeler.(/(a)ll)

*  dir /Aa
   dir komutuyla /Aa parametresi kullanıldığında arşiv dosyalarını listeler.
*  dir /Ah
   dir komutuyla /Ah parametresi kullanıldığında sadece gizli(/(h)idden) dosya ve klasörleri listeler.
*  dir /s
   dir /s komutu cmd deki en önemli komutlardan biridir.Bu komutun iki görevi vardır:

     1-İçinde bulunulan klasörü tüm alt dizin ve klasörleriyle birlikte görüntüler.  C:\Windows>DIR /S (Windows klasörünün içerdiği dosya ve klasörlerin 
     (s)ülalesini gösterir.

     2-Sabit diskte herhangi bir dosyayı arar. C:\>DIR Dosya.exe /S (Dosya.exe dosyasını sabit diskte arar; bulursa yerini gösterir.)

*  dir /As
   dir komutu /As parametresiyle kullanıldığında sadece sistem dosya ve klasörlerini listeler.
*  dir /Ad
   dir komutu /Ad parametresiyle kullanıldığında yalnızca klasörleri listeler.
*  dir /Ar
   dir komutu /Ar parametresiyle kullanıldığında yalnızca okunabilir dosyaları listeler.

/P (Page): Dosya ve klasörlerin sayfa, sayfa listelenmesini sağlar.

/W: Dosya ve klasörleri 5 sütün halinde yan yana listeler. DIR /W.

***C:\> dir >sonuc.txt
dir komutu ve parametrelerinden sonra gelecek olan ">" karakteri ve 
sizin belirleyeceğiniz dosya ismiyle komuttan gelen listeyi o isimde bulunulan dizine kaydedebilirsiniz.

#### DIR Komutuyla İlgili Örnekler:

>C:\>DIR *.exe /On /p (Sabit diskin ana klasöründeki uzantısı exe olan dosyaları isme göre sıralı bir şekilde listeler.)

>A:\OYUN>DIR /Ah /Os /w (Diskette Oyun klasörü altındaki gizli dosyaları boyutuna göre küçükten büyüğe sıralı şekilde ve 5 sütun halinde listeler.)

>C:\> DIR A*.* /s (Sabit diskte isminin baş harfi A olan dosyaları arar ve yerini gösterir.)

>C:\> DIR A???.Bat /Ar /Od /p (Sabit diskin ana klasöründeki isminin baş harfi A olan ve ismi 4 harften oluşan,
 uzantısı bat olan sadece okunabilir dosyaları tarihe göre sıralı bir şekilde sayfa sayfa listeler.)

### 2-cd(Change Directory)

 Üzerinde bulunulan dizini değiştirmek için kullanılır.

       <ÖRNEK EKLENEBİLİR>

 * cd..

  cd komutuyla bir üst dizine çıkıyoruz.

 <CD.. ÖRNEĞİ>
       <SCREENSHOT>
  
  cd komutundan sonra direk bir dizin yolu (directory path) da girilebilir. (Yukarıdaki örnekte olduğu gibi) Farkındaysanız tüm yolu tırnak içine aldık, 
  çünkü “Program Files” klasörü boşluk karakteri içeriyordu.
    
 * cd\ komutu,hangi klasörde bulunulursa bulunulsun kök dizine pat diye çıkmak için kullanılır.
 Eğer kök dizinini(root directory) değiştirmek istiyorsanız direk dizin harfi ve : (iki nokta üst üste) yazmanız yeterli olacaktır.cd komutuna gerek duyulmaz.

### 3-md(Make Directory)


Klasör oluşturmak için kullanılır.

* C:\>md Oyun (Ana klasör altında oyun isimli klasör oluşturur.)

* C:\Windows> md \Oyun (Yukarıdaki örnekle farkı yoktur. Bu komut satırı da ana klasör altında Oyun isimli klasör oluşturur.

md komutunu kullanarak tek cümle ile iç içe dizinler oluşturmanız mümkündür.Örneğin:

    <SCREENSHOT>

### 4-del(Delete)

Dosyaları silmek için kullanılır.

>C:\Oyun>DEL Mario.exe (Oyun klasörü altındaki Mario.exe dosyasını siler).

>C:\Oyun>DEL *.EXE (Oyun klasörü altındaki uzantısı EXE olan dosyaları siler).

>C:\>DEL *.* (Ana klasör altındaki tüm dosyaları tek bir kalemde siler. Tehlikeli bir komuttur.
Bilgisayarın açılmamasına sebep olabilir. Çünkü açılış dosyaları ana klasör altındadır)

>C:\>DEL C:\Notlar\*.* (Notlar klasörü altındaki tüm dosyaları siler).

***Del komutuyla klasör silinemez,sadece dosya silinebilir.

### 5-rd(Remove Directory)

Klasör silmek (kaldırmak) için kullanılır.

Ancak tek başına rd komutuyla içinde herhangi bir şey olan bir klasörü silmeye çalışırsanız "Dizin boş değil" uyarısı alacaksınız.
Peki şimdi ne yapacağız?

* /s parametresi ile rd komutu, bir dizini boş olmasa bile siler.

* /q parametresi ise, “Emin misiniz (E/H)?” sorusunu cevaplamaktan sizi kurtarır.

### 6-deltree

Bir Klasörü içindeki tüm alt klasörlerle ve dosyalarla beraber siler. Yani klasörü tamamen kaldırır.

rd komutuna göre kullanımı çok daha kolay ve pratiktir.
Ancak Deltree bir dış komuttur.

Deltree.exe dosyası yanlışlıkla harddiskten silindiğinde RD komutu kullanılmak zorundadır.

### 7-ren

ren komutu, dosya ve klasörlerin isimlerini değiştirmemize yarar. Windows arayüzündeki karşılığı “Sağ Tuş Menü > Yeniden Adlandır” butonudur.
 Örnek kullanım:

    <SCREENSHOT>

### 8-move

move komutu, dosya ve klasörleri, bulunduğu dizinden başka bir dizine taşımamıza yarar. (Kes + Yapıştır gibi de düşünülebilir.)

>Örneğin, “C:\Downloads” dizininde bulunan “rapor.pdf” dosyasını, masaüstünün dizini olan “C:\Users\yigith\Desktop” klasörünün içine taşıyalım.
  
      <SCREENSHOT>

### 9-copy

copy komutu, dosya ve klasörleri, bulunduğu dizinden başka bir dizine kopyalamaya yarar. 
(Kopyala + Yapıştır gibi de düşünülebilir.)

>Örneğin, “C:\Downloads” dizininde bulunan “rapor.pdf” dosyasını, masaüstünün dizini olan “C:\Users\yigith\Desktop” klasörünün içine kopyalayalım:
     
     <SCREENSHOT>

### 10-xcopy

 Bir klasörü istenilen klasöre tüm dosya ve alt klasörleriyle birlikte kopyalar.
 
* xcopy komutu /s parametresiyle kullanıldığında boş olanların dışındaki klasör ve alt klasörleri kopyalar.

* xcopy komutu /e parametresiyle kullanıldığında boş olan klasörleri de kopyalar.

* xcopy Türkiye\*.* Türk (Türkiye klasörünü tüm alt klasör ve dosyalarıyla birlikte Türk klasörü içine kopyalar.)

### 10-format

Belirtilen disk ya da disketi DOS işletim sisteminin kullanımına hazır hale getirir. Yani disk ya da disketi biçimlendirir (formatlar.)
Formatlanan disk yada disket üzerindeki tüm bilgiler silinir.

* format komutu /v parametresiyle kullanıldığında formatlanan birime isim(etiket) verilir.

* format komutu /f parametresiyle kullanıldığında disket formatlarken formatlanan diskin kapasitesini belirtir.

* format komutu /s parametresiyle kullanıldığında önce disketi formatlar.
Sonrasında  sistem (başlangıç) dosyalarını diskete kopayalayarak disketi açılış (başlangıç-sistem) disketi yapar.

* format komutu /u parametresiyle kullanıldığında disk ya da disket koşulsuz olarak biçimlendirilir.Yani sektörler ve izler(track)  yeniden oluşturulur.
Bu şekilde formatlanan disk yada disket içindeki bilgiler kurtarılamaz.

* format komutu /q parametresiyle kullanıldığında hızlı formatlar.Sektör ve izleri yeniden oluşturmaz. Sadece disk yada disket üzerindeki bilgileri siler.

* Format C: (Sabit diski formatlar).

* Format A: (Disketi biçimlendirir ve başlangıç disketi yapar).

* Format A: /F:720 (720 KB’lık disketi biçimlendirir).

* Format C: /U /V:ANADOLU (Sabit diski koşulsuz olarak yeniden formatlar ve Etiketini (ismini) ANADOLU yapar.

* Format A: (Disketi hızlı biçimlendirir. Yani sadece içindeki bilgileri siler).


### 11-diskcopy

Bir disketin bire bir kopyasını başka bir diskete çıkarmak için kullanılır.
 Yani bir disketin aynısından bir tane daha oluşturur. 
Kopyalanacak disketlerin kapasiteleri birbirine eşit olmak zorundadır.Diskcopy A: A: nokta şeklide kullanılır.
 Bu komut verildikten sonra önce kaynak disket,disket sürücüye takılır.
Daha sonra bilgisayar boş olan hedef disketi takmanızı ister.

### 12-scandisk

 Disk yada disketi hatalara karşı tarar. Hata ile karşılaşırsa düzeltir.

 * scandisk A: (Disketi hatalara karşı tarar. Hata bulursa düzeltir)

 * scandisk C: (Sabit diski hatalara karşı tarar. Hata bulursa düzeltir)

### 13-attrib
 Dosyalara belirli nitelikleri (Özellikleri) kazandırmak için kullanılır.Bilgisayarınızda bir dosya ya da klasör üzerinde sağ tıkladığınızda
 "Özellikler" butonunu seçerseniz karşınıza aşağıdaki pencere gelecek. 

     <SCREENSHOT>                    
Ekranda görünen "Salt okunur","Gizli" gibi dosya ve klasör öznitelikleri (attributes) attrib komutu aracılığıyla değiştirilir.

Dosya öznitelikleri MS-DOS komut isteminde harflerle temsil edilir.Ancak hangi harflerle?

    <SCREENSHOT>
    <SCREENSHOT2>

 Yukarı +h ekindeki “+” ile  “Özel Resimlerim”  klasörüne, (h)idden/gizli özelliği atamış olduk.
     Bahsettiğimiz bu özniteliği “Özel Resimlerim” klasöründen kaldırmak için ise:(ÖRNEK DEĞİŞECEK)

      <SCREENSHOT>

   tahmin edeceğiniz üzere “-h” ekini kullanıyoruz.


    <ÖRNEK EKSİK>


### 14-sys

Başlangıç disketi oluşturmak için kullanılır. (Başlangıç disketini oluşturmanın bir diğer yolu format komutunun /s parametresini kullanmaktı.)

* SYS C: A: (Sabit diskteki açılış dosyalarını diskete aktararak başlangıç disketi oluşturur. Bu işlem bilgisayar göçmeden önce yapılmalıdır.
 Bilgisayar göçtükten sonra oluşturulan bu disket kullanarak bilgisayarın açılması sağlanır).(GÖÇMEK????)

* SYS A: C: (Disketteki açılış dosyalarını sabit diske aktarır. Bilgisayar göçtükten sonra başlangıç disketi ile açılır 
ve bu komut verilirse artık açılış disketine gerek kalmadan bilgisayar sabit diskten açılabilir.).

### 15-tree

Bir klasörün içerdiği dizinleri, soy ağacı şeklinde görüntüler.

    <SCREENSHOT>

### 16-date

Bilgisayarın sistem tarihini görüntülemek ve güncellemek için kullanılır.

    <ÖRNEK VER>

*  date komutu /t parametresiyle kullanıldığında sadece tarihi gösterir.

***Eğer date komutunu kullandıktan sonra tarihi değiştirmekten vazgeçerseniz hiçbir şey yazmadan sadece “enter” tuşuna basmanız yeterlidir.

### 17-time

Bilgisayarın sistem saatini görüntülemek ve güncellemek için kullanılır.

    <ÖRNEK VER>  

* time komutu /t parametresiyle kullanıldığında sadece saati gösterir.       

### 18-more

 Metin dosyalarının içeriğini görüntülemede kullanılır.

     <SCREENSHOT>

 Bu komut “C:\Windows\system.ini” dosyasının içeriği ekranda görüntüler.

Metin belgesinin içeriği ekrana sığmayacak kadar uzun ise içerik sayfalar halinde listelenir.

### 19-copy con

Metin belgesi oluşturmak için kullanılır.

### 20-ipconfig

ipconfig komutu, bilgisayarın sahip olduğu ağ bağdaştırıcılarının geçerli ağ yapılandırmasını listeler. 
Genellikle daha ayrıntılı görüntülemek için /all parametresi ile kullanılır.

     <SCREENSHOT>

### 21-print

Bir metin tabanlı belgeyi varsayılan yazıcınızla kağıda dökmek/yazdırmak için kullanılır.

* Eğer metin belgenizi belirli bir yazıcıya gönderecekseniz, /D: parametresini kullanmanız gerekmektedir.(D=Device)

### 22-cls(Clear Screen)

Ekranı temizlemek için kullanılır. Komut göstergeci ve imleç 1. satıra gelir.

### 23-exit

ms-dos komut istemcisinden çıkmak için kullanılır.

### 24-shutdown

shutdown komutu, bilgisayarı kapatmak (shutdown) veya yeniden başlatmak (restart) için kullanılır.

* Bilgisayarı kapatmak için /s parametresi ile kullanılır.

* Bilgisayarı yeniden başlatmak için /r parametresi ile kullanılır.

### 25-help

help komutu, tek başına kullanıldığında tüm ms-dos komutlarını ve görevlerini listeler.

    <SCREENSHOT>

Herhangi bir komutun, ne işe yaradığı ve hangi parametrelere sahip olduğunu öğrenmek istiyorsanız,
önce help sonra da komut ismini yazmanız yeterli olacaktır.

    <ÖRNEK VER>

Bu yazdığım 25 komutun haricinde de birçok cmd komutu vardır.Yukarıda help komutunu yazarken
belirttiğim gibi terminale help komutunu yazdığınızda hangi komutun ne işe yaradığını öğrenebilirsiniz.
Ancak  <www.hacker-okulu.blogspot.com> sitesinden de komutları inceleyebilirsiniz.



# Windows Dosya Ve Dizin Yapısı
##   KLASÖR NEDİR?
Ortak bir özelliğe sahip dosyaları bir arada bulunduran birimlere klasör (dizin) denir.
Klasörler günlük hayatta kullanılan dosya klasörlerine benzetilebilir.

#### Klasörle İlgili Bazı Özellikler
Bir klasör içerisinde aynı ada ve uzantıya sahip birden fazla dosya olamaz.

Bir klasör içerisinde aynı isme fakat farklı uzantıya sahip dosyalar bulunabilir.Mesela Çanakkale.avi filmi ile Çanakkale.txt şiiri aynı klasörde bulunabilir.
<ÇANAKKALE YERİNE ÖRNEK>

Bir klasör içerisinde aynı ada sahip başka bir klasör bulunamaz.

Dosya ve klasör adlarında büyük/küçük harfler aynı kabul edilir.Mesela HARRYPOTTER.AVI ile harrypotter.avi dosyaları aynıdır.

Bazı donanımlar üzerinde birden fazla sürücü oluşturulabilir, mesela tek bir sabit disk C: ve D: şeklinde 2 sürücüye ayrılabilir. 

## DOSYA NEDİR?

Bilgisayarda bilgilerin kaydedildiği birimlere dosya adı verilir.

Dosya içerisindeki bilgi; resim, yazı, çizim, ses gibi her şey olabilir.

Yazılımlar ürettiği bilgileri dosyalarda saklar.Mesela kaydettiğiniz bir sesi sonradan dinlemek istiyorsanız sesi,bir dosyaya kaydetmelisiniz.

Bilgisayarın nasıl çalıştığını öğrenmek için depocu veya kütüphaneci olduğunuzu hayal etmek işinizi kolaylaştırabilir.

Tıpkı bu mesleklerde olduğu gibi klasörleme işleminde de bazı basit kuralları uygulamak, dosyalarla daha verimli çalışabilmemizi mümkün kılar. 

Dosyalarla ilgili bilmemiz gereken ilk şey, onları nasıl organize edeceğimiz ve ihtiyaç duyduğumuzda onlara nasıl ulaşabileceğimizdir.

## Dosya Sistemi Nedir?
Bilgisayarlar bilgileri depolarken (harddisk, CD/DVD, USB bellek vs. ortamlarda) onlara daha hızlı ve kolay bir şekilde ulaşabilmek için bir takım düzenlemeler yapar.
Neyi nereye yazacağının, nereden okuyacağının kaydını tutar.
 Bilgileri depolarken kullandığı bu düzenlemeye dosya sistemi denir. Doğal olarak birbirinin yerine kullanılabilen pek çok dosya sistemi var. 

### Ne İşe Yarar Bu Dosya Sistemi?

 En sade şekliyle, dosyaların kayıt ortamında düzen içinde olmalarını sağlar. Sonradan aradığımız bilgiye kolay bir şekilde ulaşmamız,
dosyaları belli kriterlere göre gruplandırmamız (örn. klasörler) ve birtakım gelişmiş işlemler (paylaşım ve güvenlik gibi) dosya sisteminin görevidir.

### Ne Tür Dosya Sistemleri Var?

Tam olarak bir sayı vermek pek mümkün değil. Sonuçta ihtiyaçlar ne kadar değişiyorsa sistemler de o kadar değişiyor. 
Eğer isimlerini merak eden varsa bir kısmı:

 adfs, affs, autofs, cifs, coda, coherent, cramfs, debugfs, devpts, efs, exfat,  ext,  ext2,  ext3, ext4, 
fat16, fat32, hfs,  hfsplus, hpfs, iso9660, jfs, minix, msdos, ncpfs, nfs, nfs4, ntfs, proc, qnx4, ramfs, reiserfs, romfs, smbfs, sysv, tmpfs, udf, ufs, 
umsdos, usbfs, xenix, xfs, xiafs

### Dosya Sistemlerinden Önemli Olan Birkaç Tanesi:
***Dosya sistemlerinde FAT ve NTFS’nin daha rahat anlaşılabilmesi için öncelikle ‘sektör’ ve ‘küme’ kavramlarının açıklanması gerekiyor.

Sabit disklerdeki sektör kelimesini hemen hemen herkes duymuştur.Bilgisayara kaydedilen veri sabit disklerdeki bu sektörler üzerine yazılır.
Sektörlerde kendi aralarında ,yukarıdaki resimde de görüldüğü gibi, farklı farklı kümeler (clusters) oluştururlar.
Bu kümelerin her biri boyut olarak eşittir ancak değer olarak farklılık gösterirler.İşte dosya sistemi de tam olarak bu farklılığa işaret eder.
Yani bir dosya sisteminde sabit diskteki her bir küme 512byte ise başka bir dosya sisteminde bu boyut her bir küme için 1kb olabilmektedir.

### FAT (File Allocation Table – Dosya Yerleşim Tablosu) 

Aslında 1970’li  yıllarda Floopy Disk’lerde kullanılması için tasarlanmıştı.Daha sonradan MS-DOS ve Windows 9x için yeniden düzenlendi.
Günümüze yaklaştıkça sabit disklerin ve işletim sistemlerinin gelişmesiyle kullanım alanı giderek daralan FAT dosya sistemi halen flash diskler,
solid state driverler ve hafıza kartları gibi alanlarda kullanılmaktadır.

İlk olarak 1980 yılında FAT12 olarak geliştirilen bu sistem 1984 yılında IBM PC’ler ile FAT16, 1995 yılında Windows 95 ile de son, yani FAT32 halini almıştır.
##### Peki nedir bu sayılar ?


Bu arada hemen ‘bit’ faktöründen de bahsedelim.Yukarıda sürekli olarak adı geçen kümeleri oluşturan sektörlerin de bir alt kolu vardır.Bit bu alt kolun en dibinde yer alır.
Her 8 bit bir adet byte oluşturur.Diske kaydedilen veriler de aslında bu bytelar üzerine yazılır.Bit in depolama anlamında bir önemi yoktur.
Çünkü tüm veriler diske ‘byte’olarak yazılır.İşte bu byte’lar da birleşerek sektörleri(sectors) oluşturur ki en sonunda küme(cluster) denilen kavram ortaya çıkar.
 Yani bitler byte’lerı, bytler ise kilobyte ları oluşturarak kümelerin var olmasını sağlarlar.kilobyte>byte>(bit) ve küme>sektör>(bit)

 ***Fat dosya sisteminin 12,16 ve 32 olarak farklı isimlendirilmesinin sebebi girdileri farklı sayılarda bitlerden oluşmasıdır.

Fat dosya sisteminin ilk versiyonu olan FAT12 12 bitten oluşur.

* Fat16,Diğer ismiyle V-FAT, daha sonradan 1995’lerde Windows 95 için geliştirilmiştir.
Bu dosya sistemi 4095MB yani 4 GB dan fazla depolamaya izin vermiyor.
Ayrıca 4GB’a yaklaştıkça artan sektörlerin verisel büyüklüğü de diskin verimli kullanımı için oldukça elverişsiz.Tabiki bu eski bir dosya sistemi ve
günümüzde kullanılmıyor.

* FAT32 ise günümüzde NTFS’den sonra en çok kullanılan dosya sistemidir. Özellikle aynı disk üzerinde Linux işletim sistemini kullanıyor ve
 bazı dosyalara Windows’tan da ulaşıp değişiklik yapmak istediğinizde ihtiyaç duyacağınız bir dosya sistemi.
  En fazla 32 GB’lık volume’de destekler. Cluster kapasitesi 32 KB’tır. Tek bir diskte ise 2 Terabyte’a kadar destekliyor.

                                                <EKSİK?>
 ### iso9660
 
 CD'lerde kullanılan bir dosya sistemi. Eski/yeni hemen hemen her bilgisayarda kullanılabilir.
 CD'ler için standarttır denilebilir. Dosya isimlerinde 8+3 karakter, dosya boyutunda ise 4GB sınırlaması mevcuttur.

 UDF:
 
  iso9660 dosya sisteminin DVD'lerde kullanılan ve yeni bilgisayarlar için daha uygun olan yeni bir şekli denilebilir.
Eski bilgisayarlarda çalışmama ihtimali var.

 NTFS

Windows XP ve daha sonraki işletim sistemlerinde varsayılan olarak kullanılan, 1993 yılında ortaya çıkan dosya sistemi. 
Hem Windows hem Linux tarafından kullanılabiliyor (Mac OS da dahil aslında.) Önceden kullanılan FAT32'ye göre gelişmiş bir yapısı vardır.
16 EB (exabyte = 2^64 bayt) dosya boyutu, yaklaşık 4 milyar dosya sayısı, 255 karakter dosya ismi ve 256 TB disk boyutu sınırlaması bulunuyor.

NTFS, FAT sistemlerine göre birçok yenilik getirmekte. En önemli olanları arasında büyük sürücülerde depolama alanının optimum şekilde kullanımı,
çökmelerin ardından hata düzeltmeleri, yetkisiz bilgi erişimine karşı koruma, indeks servisi, sıkıştırma ve veri şifrelemesi sayılabilir.
NTFS’in kurtarma özellikleri de söz etmeye değer: Windows dosya sistemindeki tüm değişiklikleri belirli kurtarma noktaları oluşturarak gerçek zamanlı olarak kaydeder.
Zorunlu bir yeniden başlatma durumunda, sistem hatalarını düzeltmek için arka planda bu kurtarma noktalarını kullanır. 
NTFS yüzlerce terabyte (bir terabyte bir milyon megabyte eder) büyüklüğündeki bölmelerin yönetimini yapabilir.
Güvenlik bakımından ise sistem yöneticileri dosyalar ve klasörler için kullanıcı erişim kuralları belirleyebilir,
EFS (Şifreleme dosya sistemi) gibi bütünleşik koruma fonksiyonlarından yararlanabilirler.

***Birden çok işletim sisteminin kullanılması dışındaki tüm durumlarda önerilen dosya sistemi NTFS’dir.

ReFS (Esnek Dosya Sistemi)

 Şu anda Windows 8 Sunucuları için kullanılabilen Microsoft'ın en son gelişmesidir. Dosya sistemi mimarisi kesinlikle diğer Windows dosya sistemlerinden farklıdır
ve çoğunlukla bir B + -tree biçiminde düzenlenmiştir.ReFS, sisteme dahil edilen yeni özelliklere bağlı olarak arızalara karşı yüksek toleranslıdır.
 Ve, yani Yazma Üzerine Kopyalama (CoW):
Hiçbir meta veriler kopyalanmadan değiştirilir; Veriler mevcut verilerin üzerine değil, yeni disk alanına yazılır.
Herhangi bir dosya değişikliğinde, meta verilerin yeni bir kopyası serbest depolama alanına depolanır ve daha sonra sistem,
eski meta verilerden yeni meta verilerden birine bir bağlantı oluşturur.
Böylece, sistem, bu depolama alanı üzerine yazılmadıkça, kolay dosya kurtarma sağlayan farklı yerlerde önemli miktarda eski yedekleri saklar.

exfAT

exFAT dosya sistemi 2006 yılında kullanıma sunuldu ve flash sürücüler için geliştirildi. FAT32'nin geliştirilmiş sürümü olarak kabul edilen exFAT, 
boyut sınırlarına takılmıyor ve 4GB'tan büyük dosyalar ile 32GB'dan büyük disk bölümlerine imkan tanıyor. 
Yine bazı kısıtlamalar nedeniyle dahili depolama alanlarında tavsiye edilmiyor. Özellikle flash belleklerde exFAT sistemi,
 yer yer NTFS'den daha hızlı çalışabiliyor. 

exFAT sistemi hem Windows hem Mac işletim sistemlerinde kullanılabildiği için avantajlı durumda ancak yine eski konsollarda herhangi bir desteğe sahip değil. 
Linux platformları ve dijital kamera gibi bazı cihazlarda da yazılım desteği ile exFAT uyumu sağlanabiliyor. 

Dosya sistemlerine baktığımızda hem Windows hem Mac bilgisayarlarda kullanabilmek için, harici sürücülerinizi exFAT ile formatlamanız gerekiyor. 
Sadece Windows kullanıyorsanız NTFS yeterli olacaktır. Tüm platformlarda sorunsuz bir şekilde çalışan bir dosya sistemi mevcut değil. 

ext2/ext3:

 GNU/Linux dağıtımlarının en çok kullandığı dosya sistemi. Yazılan bilginin mümkün olduğunca tek parça halinde yazılmasını ve okuma/yazma veriminin
 yüksek olmasını sağlamak için günlük adlı özel bir sistem kullanır (aslında ext3, ext2'nin günlük eklenmiş halidir.)  
 Uzun dosya isimlerine (255 karaktere kadar), büyük (2TB'a kadar) dosyalara ve büyük (16TB'a kadar) depolama birimlerine destek verir.
  Bu avantajlarının yanında, Windows işletim sistemlerinde kullanılamaması bir nebze eksiklik diyebilirim.
   Zira, eğer benim gibi hem Linux hem Windows kullanıyorsanız, Linux'ta kullandığınız ve ext2 veya ext3 dosya sistemli diskinizi Windowsta kullanamayacağınız 
   anlamına geliyor. Böyle bir durumda her iki sistemde de kullanacağınız dosyaları, ikisinin de kullanabildiği bir sistemi kullanmanız gerekiyor.

## Windows Ve Linux İşletim Sisteminin Farkları

### Dosya yapısı

Linux sistemlerde klasörler “/” kök dizini ile başlar. Benzer özelliklere sahip dosyalar bir klasör altında toplanmıştır. 
Örneğin home dizini altında kullanıcıya ait ayar dosyaları ve kişisel bilgi ve belgeler , root klasörü altında root kullanıcısının dosyaları bulunur.
 Her kullanıcının ayar dosyaları kendi birimlerinde tutulduğundan bir kullanıcıya ait dosyalar zarar gördüğünde diğer kullanıcılar bundan etkilenmezler.
Windows'da sistem dosyalarını barındıran C birimi ile başlar. Kullanıcı kişisel verilerini gruplandırmak ve barındırmak için D diskini oluşturur.
 Sistem ayar dosyaları tüm Windowslar’da aynı olduğundan aslında önemli bir güvenlik açığıdır.

### Disk Kullanımı ve İhtiyacı

Linux işletim sistemi en az 8 GB boş disk alanına ihtiyaç duyar. Uygulama yükleme ihtiyacına binaen 15-20 GB yer ayırabilirsiniz. 
Linux sistemler Windows disklerinizi de görüntülediği (Dosya sistemi ntfs, fat, fat32..) ve veri alışverişine imkan tanıdığı için
 haricen bir disk alanı ayırmayabilirsiniz.
Windows 7 en az 25 GB’lık disk alanına ihtiyaç duyar. Verilerinizi depolamak için farklı bir alan kullanmanız faydalı olacaktır.
 Zaten çoğu bilgisayar kullanıcısı bu nedenle C diski haricinde D birimini de oluştururlar. Kişisel verilerini bu alanda saklarlar.
  Fakat sistem dosyaları C biriminde tutulduğundan bu birimde oluşacak bir sıkıntı verilerine ulaşmamıza engel olacaktır.

Biraz C ve D sürücülerinden bahsedelim.

 Bilgisayarın yapısı gereği elektrik enerjisi olmadığında kullanılamıyor olması, bilgilerin daha sonraki kullanımlar için saklanması gereğini ortaya çıkarmıştır.
  Bu ihtiyaçtan dolayı her bilgisayarda hem bilgilerin saklanması, hem de büyük yapıdaki programların kullanılabilmesi için harddiske ihtiyaç vardır.
   Harddisk hem bilgi depolama ünitesi hem de bir sürücü görevi yapmaktadır. Harddiskin bilgisayardaki karşılığı C: ile ifade edilmektedir.
 Bu sebepten harddiske C: sürücüsü de denilmektedir. Bazı bilgisayarlarda bir harddisk bölümlendirilerek kullanılabilir ya da birden fazla harddisk bulunabilir.
  Bu durumda bilgisayarda harddiskin diğer parçaları veya diğer harddisk ya da harddiskler sırası ile alfabenin harfleri ile ifade edilir.
Örneğin, bir bilgisayarda iki harddisk olduğunu ya da bir harddiskin iki parçaya bölündüğünü farzedelim.
Bu durumda birinci harddisk C: harfi ile diğeri ise D: harfi ile ifade edilir. Üçüncü veya dördüncü harddiskler ya da 
harddiskin diğer parçaları takip eden E: ve F: harfleri ile ifade edileceklerdir.

  C sürücüsünde genelde sistem dosyaları bulunur.İşletim sisteminin kurulu olduğu yerdir.Bu diske resimleri,yazıları vs koyduğumuzda bir süre sonra yer
 kalmayacaktır.Ayrıca bilgisayarınıza format atma gereği duyduğunuzda C diskinde tüm bilgileriniz gidecektir.Ancak özel dosya ve klasörlerinizi D diskinde
 sakladığınızda bilgisayarınıza format atsanız bile bilgileriniz kaybolmayacaktır.
  C ve D disklerinde ihtiyaç duyduğunuzda  yer genişletme,C'den D'ye aktarma,C ve D'yi birleştirme gibi türlü türlü işlemler yapabilirsiniz.
    
Demin C diskinde sistem dosyalarının bulunduğunu söylemiştik.En önemlilerinden biri olan system32'den bahsedelim.

### System32 Nerede?

 System32 klasörüne Bilgisayarım > Yerel Disk: C (veya Windows’un kurulu olduğu diğer bir disk) > Windows > System32 şeklinde ulaşabilirsiniz.

  Ayrıca herhangi bir klasördeyken  C:WindowsSystem32 yazısını adres çubuğuna yapıştırıp, Enter’a bastığınızda da System32 klasörüne giriş yapabilirsiniz.

C:WindowsSystem32 veya C:Winntsystem32 yollarıyla ulaşılabileceğiniz bu klasörde meydana gelen hatalar genellikle işletim sisteminin çalışmasını etkileyebilmektedir.

### System32 Nedir?

System32 dizinindeki en yaygın dosyalardan bazıları, Windows programları için birden çok kod ve yordamı barındıran programları ve
.dll (dinamik bağlantı kitaplığı) dosyalarını başlatan .exe (yürütülebilir) dosyalardır.
Bu dosyalar, Windows Media Player'ı çalıştırmak için gerekli olan MFPLAT.dll Internet seçenekleri uygulamasını çalıştırmak için gerekli olan inetcplc.dll 
 ve Outlook Express'i açmak için gereken acctres.dll'yi içerir. Windows Installer tarafından gerekli.
 Windows'u önyüklemek ve programları çalıştırmak için gereken diğer birçok dosya,
kullanıcıların bilgisayar sorunlarını gidermesine olanak tanıyan sistem yapılandırma yardımcı programı msconfig.exe gibi burada saklanır.
 System32'yi silmek bilgisayarın tamamen çalışmasını durdurmasına neden olur. 
 System32 olmadan, kullanıcının Windows'u yeniden yüklemesi gerekir ve düzgün yedeklenmemiş olan tüm dosyaları kaybedebilir.
 Yaygın bir İnternet dolandırıcılığı, sistemli bir yazılımın, zararlı bir bilgisayar virüsü olduğunu iddia eden sosyal medya sitelerini dolaştırdı ve
 kullanıcıları, bilgisayarlarını daha hızlı hale getirmek için dizini silmeye teşvik etti.

### Kayıt Defteri

Windows’da uygulama ayarlarını, donanım bilgilerini ve çok daha fazlasını tutan kayıt defteri (registry), Linux’da bulunmuyor.
Linux’da uygulamalar kendi ayarlarını kullanıcılar altında ayrı ayrı tutuyorlar. Dolayısıyla Linux’da temizlik gerektiren bir veritabanı bulunmuyor.
Önemli bir güvenlik açığı ortadan kalkmış oluyor.

### Uygulamalar ve Paket yöneticisi Kavramı

Windows’da bir programı kurabilmek için genellikle onun yükleme paketini internetten bulup indirmeniz gerekiyor.
 Birçok Linux sisteminde bununla uğraşmanız gerekmez Paket Yöneticisi (Synaptic PY, Yazılım Merkezi), size uygulamalar arasında dolaşabileceğiniz, 
 onları yükleyebileceğiniz ve kaldırabileceğiniz bir merkezi denetim alanı sunuyor.
Windows da kurulumda birçok kez uygulama ile eklentileri ayrı ayrı kurmak zorunda kalırsınız. Özellikle kayıt defterine oluşturduğunuz kayıtlar,
yerleştirdiği ayar dosyaları bir müddet sonra sistemi yavaşlatmaya başlar. Aslında kısmen güvenliği de etkiler. 
Bilgisayarınızın bilmediğiniz yerlerinde çalışan uygulamacıklar virüs programınında dikkatini çeker. 
Virüs programlarına ve güvenlik duvarına gün doğar. Linux'da uygulama kaldırma işleminde yükleme de olduğu gibi bütün eklentileri ile kaldırıldığından
sistemde gereksiz dosya bulundurmaz.

### Değiştirilebilir Arayüzler

  Windows işletim sistemi arayüzünde uzun zamandır çok büyük bir değişim gerçekleşmedi . 
  Windows 8 ile yeni bir akım başlatılsa da Linux bunu uzun zamandır yapmaktadır.
  Linux’da arayüz, çekirdek sistemden tamamen ayrı ve arayüz ortamınızı baştan yüklemelerle uğraşmadan değiştirebiliyorsunuz.
  KDE, Gnome, Cinnamon gibi çok kullanılan bazı arayüzleri araştırabilirsiniz.

### Komut Terminali
 Çoğunluğunu görselliğin oluşturduğu Windows da komut satırında yapacağınız çok fazla işlem de yoktur. Kullanıcı için bu büyük bir avantajdır.
 Linux’da Windows’a nazaran komutlarla işiniz daha fazla olacaktır. Çoğu kullanıcı bu yüzden Linux sistemlerden uzak durmaktadır.
 Hatta komutlarla sistem yöneticilerinin işinin olacağı, hacker’lerin komutlarla çalıştığı varsayımı vardır.
 Fakat komut satırına giren kullanıcı, bilgisayarın yöneticisinin kendisi olduğunu hissedecektir.

### Sürücü Ayarları

Windows’lu PC’ler çok yaygın olduğundan, sürücü geliştiricileri daha çok Windows’a odaklanıyorlar.
 Bu avantaj olsa da işletim sistemi kurulumundan sonra donanım sürücülerini tek tek kurmak avantajı dezavantaja çevirmektedir.
  Windows 7’den sonra kısmen bu sorun ortadan kalkmıştır.
Linux sistemlerde ise büyük çoğunlukla içerisinde sürücüleri barındırır. Çok düşük ihtimal olmakla beraber ekran kartı problemi ile karşılaşabilirsiniz.
 Bir de bazı donanım üreticileri Linux’a uygun driver üretmemektedirler. Linux kullanmak istiyorsanız donanımın desteği olup olmadığını araştırmalısınız.

### Maliyet

 Linux ücretsizdir.Windows'da ise neredeyse tüm adımlarda maliyet karşınıza çıkacaktır. Sistem temini ücretlidir. Korsan kullanım oldukça yaygındır.

### Hız 

 Windows'da ram bellek yetmediğinde uyarı verir. Sistem kullanılamaz hale gelir.
 Linux Takas Alanı (Swap) olarak bilinen bir teknoloji kullanır. Bu takas alanı genellikle RAM belleğin iki katı olarak harddiskten kullanılan alandır. 
 Yani ram bellek yetmediğinde bu alan devreye girer, uzun bir müddet sistemin açık kalmasını sağlar.Linux Takas Alanı olarak bilinen bir teknoloji kullanır.
  Bu takas alanı genellikle RAM belleğin iki katı olarak harddiskten kullanılan alandır. 
  Yani ram bellek yetmediğinde bu alan devreye girer, uzun bir müddet sistemin açık kalmasını sağlar.

### Güvenlik
 Windows bilgisayarın kayıt defteri gibi farklı yerlerine ayar dosyaları atar.
  Eğer program ile beraber bu ayarlar da silinmez ise bu dosyalar antivirüs programı ve güvenlik duvarını gereksiz bir şekilde yoracaktır.
  Bu da sizi formata veya temizleme programlarını satın almaya itecektir. İleriki aşamalarda virüs programı ve güvenlik duvarı kurmaya ihtiyaç duyacaksınız.
  Ve bütün kullanıcıların ayar dosyalarının bir arada bulunması olası güvenlik açığında bütün sistemi etkileyecektir.

  Linux için yazılan virüs sayısı yok denecek kadar azdır. Linux sistemlerin en büyük avantajı ayar dosyalarını kullanıcı bazlı ayırmasıdır.
  Bu nedenle bir kullanıcı sisteminde oluşan problem diğer sistemi etkilemez.

### Lisanslama

Windows’da işletim sistemi için lisans temini gerektiği gibi programlarda da lisans gerekir. 
 Genel Kamu Lisansı (GPL) linux sistemlerin ortak lisanslama modelidir. Birçok uygulama da bu lisanslama modeli ile lisanslıdır. 
       <TEKRAR OKU>

### Destek
Windows için resmi destek sitesi mevcuttur. Piyasadaki varlığı büyük olduğu için kişisel sayfalarda ve ticari sayfalarda da bilgi bulabilirsiniz.
Linux dağıtımlarının kendilerine ait siteleri mevcuttur. Yine kişisel sitelerde de doküman bulabilirsiniz.

### Pazar Payı
Yürüttüğü politikalar nedeniyle Windows’un pazar payı oldukça fazladır. Örneğin yeni çıkan her bilgisayar varsayılan olarak Windows türevi sistemleri barındırır. 
Kimi bilgisayar üreticileri de bunu fırsat bilerek kullanıcılar istemeden kurar ve fiyatlandırırlar.
Linux sistemler daha çok devlet eliyle yürütülen projelerle adını duyururlar. 

### Kurulum Süresi
Windows ise 20 dakika ile bir saat içerisinde kurulumu tamamlar.
 Daha sonra donanım sürücülerini tanıtma ve kişisel ve sistem uygulamalarını yükleme kullanıcıların vaktini alan şeylerdir. 
 Üzerinde yüklü olarak gelen program sayısı azdır.

  Linux sistemlerde 10 dakika ile 20 dakika arasında bir zaman alır. Donanım sürücülerini de bu süre içerisinde yükler.
  Birçok uygulamada yine bu süre içerisinde yüklenir.

### Sistem Gereksinimleri

Windows sistemler için sistem gereksinimleri resmi sitelerinde de paylaşılmıştır(2). Örneğin Windows 7 sistemler için;
*1 gigahertz (GHz) veya daha hızlı 32 bit (x86) ya da 64 bit (x64) işlemci
*1 gigabayt (GB) RAM (32 bit) veya 2 GB RAM (64 bit)
*16 GB (32 bit) veya 20 GB (64 bit) kullanılabilir sabit disk alanı

100 MB kadar düşen linux sürümleri var olduğu düşünüldüğünde sistem gereksinimini oldukça düşüktür. Sisteminize uygun sürümü bularak yükleyebilirsiniz.


### Oyun
Gerek pazar payı gerekse yürüttüğü politikalar nedeniyle piyasadaki oyunların büyük bir çoğunluğu Windows’a uygundur.
 Oyun şirketleri de piyasada yer tutabilmek için oyunlarını Windows tabanlı üretirler. Bu nedenle oyun noktasında Windows’da sıkıntı çekmezsiniz.
Linux sistemlerde de oyun oynayabilirsiniz ancak seçeneğiniz windowsdaki kadar çok olmayacaktır.




