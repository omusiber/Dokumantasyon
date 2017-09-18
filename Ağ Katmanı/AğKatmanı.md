## Ağ Katmanı Nedir?

	Bilgisayar ağının 7 katmanlı OSI modelinde 3. katmana verilen isimdir.

## Ağ Katmanı ne işe yarar?
	
	Ağ katmanı komşu ağ düğümlerinin adresini bildiği için ara yönlendiriciler(router) aracılığıyla yönlendirme de dahil olmak üzere paket yönlendirme işlemlerinden sorumludur.Aynı zamanda hizmet kalitesini(QoS) yönetir ve yerel ana bilgisayar(localhost) mesajlarını Taşıma Katmanına(Transport Layer) iletir.Daha basit bir şekilde açıklamak gerekirse Ağ katmanı, servis fonksiyonlarının kalitesini korurken, değişken uzunlukta veri dizilerinin bir kaynaktan bir hedef ana bilgisayara ağlar vasıtasıyla aktarılmasının işlevsel yollarını sağlayan OSI modelinin bir bölümüdür.

## Ağ katmanında işler nasıl ilerler?

### Adresleme (Addressing)
    Ağ katmanı, veriyi gönderecek olan kaynak cihaz ve veriyi alacak olan hedef cihaz için bir adresleme mekanizması sağlar. Her bir veri parçasının doğru hedefe gönderilmesini sağlamak için her cihazın kendine özgü bir adresi olmalıdır. Ağ katmanında bu adresler IP (Internet Protocol) adresleridir. Bu adresler 3. katman başlığı (Layer 3 header) içinde segmentin üzerine enkapsülasyon işlemiyle yerleştirilir. Bu işlem sayesinde hedef cihaz gönderilen paketin kendisine geldiğini anlar ve hedefi yönlendirmek için kullanılan ara cihazlar, veriyi göndereceği yolu belirler.

### Enkapsülasyon (Encapsulation)
    Enkapsülasyon işleminde 4. katmandan alınan segmentin üzerine 3. katman başlığı(header) eklenir ve segment diye adlandırdığımız veri bütünü artık paket (packet) ismini alır. 3. katman başlığı, hedef adresi (destination address) ve kaynak adresi (source address) gibi bilgileri içerir.

### Yönlendirme(Routing)

#### Paket anahtarlaması(Packet Swicthing)
    Bu iletim yönteminde, kanal üzerinde gönderilecek olan bilgiler paketlere konularak iletilir. Örneğin uzun bir yazının karşı tarafa yollanacağını düşünelim. Bu durumda yazı paket boyutlarında kesilerek her pakete yazının bir kısmı konulur. Paketlerin üzerine kullanılan iletim yöntemlerine göre değişik bilgiler eklenmektedir. Bu eklenen bilgiler başlık (header)  olarak da isimlendirilmektedir ve paketin geldiği yer gideceği yer gibi bilgileri içerir.Bu paketler birbirinden ayrı hareket ederek ağda ilerler.Alıcı, paketi gönderenin gönderdiği sırada almayabilir.Bu durum icin alıcı bilgisayar ara belleğinde önce gelen paketi tutar ve digerlerini bekler.Verinin paketler halinde yollanmasının bir avantajı, herhangi bir şekilde hattın -bir veya birden fazla- kullanıcıya tahsis edilmemesidir. Yani hat kullanıcı tarafından kullanılmadığı zamanlarda başka kullanıcılar tarafından kullanılabilmektedir.

#### Devre Anahtarlama(Circuit Switching)
    Paket anahtarlanması yöntemine alternatiftir ve iki uç arasında (bağlantı yapan iki bilgisayar gibi), özel bir hat kurulmuş gibi çalışır. En klasik örneği ilkel telefon santrallerinde bir operatörün, konuşmak isteyen iki kişiyi tek bir kablo üzerinden bağlı hale getirmesi olarak düşünülebilir.2000lerin başındaki telefon hattı üzerinden internet kullanımı da buna örnek gösterilebilir. İnternet bağlantısı mevcutken telefon hattı çalışmazdı.Hat bir kere iki uç arasında tahsis edildikten sonra iletişim bitip bağlantı kapatılana kadar açık kalmak zorundadır, bu durum sistem kaynaklarının uzun süre bir bağlantıya tahsis edilmesinden dolayı kullanışsız olarak görülür, ancak uzun süre sabit hızda bağlantı kuran sistemlerde kullanışlı olabilir.

#### Message Switching(Mesaj Değiştirme)
    Mesaj değiştirme, verilerin kaynak düğümden hedef düğüme kadar yönlendirildiği bir ağ anahtarlama tekniğidir. İleti yönlendirme sırasında ağdaki her ara anahtar tüm iletiyi depolar. Şebekenin tüm kaynakları meşgulse veya şebeke engellenirse, mesaj santrali ağı, mesajın etkin bir şekilde aktarılması için yeterli sayıda kaynak mevcut hale gelene kadar mesajı saklar ve geciktirir.Paket anahtarlamadaki ilerlemelerden önce, mesaj değiştirme, devre anahtarlamanın verimli bir yerini almış gibi davrandı. Başlangıçta teleks şebekeleri ve kağıt kaset röle sistemleri gibi veri iletişiminde kullanıldı. Mesaj değişimi büyük oranda paket anahtarlama ile değiştirildi, ancak teknik hala geçici sunucular, askeri ağlar ve uydu iletişim şebekelerinde kullanılmaktadır.


### Route discovery and Selection(Yönlendirici keşfi ve seçimi)
    Yönlendiriciler, bir paketin hedef ip adresine dayalı olarak nasıl yönlendirileceğini anlamak için bir yönlendirme tablosu hazırlarlar.Bir yönlendirme protokolü aracılığıyla veya manuel olarak yapılandırılabilir. 
    Dilerseniz gelin bu protokollerden biraz bahsedelim.
 #### RIP (Router Information Protocol - Yönlendirme Bilgisi Protokolü) 
     Uzaklık vektör algoritmasıyla çalışan ve yönlendirmeleri hesaplamak için Bellman-Ford algoritmasını kullanan bir protokoldür. RIP, yönlendirici cihazların tablosunda Administrative Distance (Yönetim Mesafesi) 120 olarak yer alır. RIP yönlendiriciler, en iyi yol seçimini yaparken sadece geçtiği cihaz (hop)  sayısına  bakar. RIP en fazla 15 hop’u kabul eder. Bu sayı aşıldığı zaman (yani 16. hopa gelince) destination unreachable (kaynak bulunamadı) hatasını verir.

    RIP mesajları kapsüle edilmiş şekilde UDP (User Datagram Protocol – Kullanıcı Datagramı Protokolü) segmentinde 520’nci porttan yollanır. RIP kullanan yönlendiriciler, 30 saniyelik döngüler halinde komşu yönlendiricilere tüm routing (yönlendirme) tablosunu gönderir.

  	 RIP’in avantajları:

    • Küçük ağlarda çok kullanışlıdır.
    • Kullanımı ve uygulaması kolaydır.
    • Tüm topolojiyi bilmediğinden yönlendiricide az bellek tüketimini ve az işlemci yükünü sağlar.

    RIP’in dezavantajları:

    • RIP, büyük ve çok büyük ağlarda ölçekleme konusunda yetersiz kalır. 
    • RIP, en fazla 15 hop gidebilir. Ağ 15 cihazdan büyükse protokol ulaşılamaz hatası verir.
    • Büyük bir ağ içinde her yönlendirici RIP anonslarını yapması demek internette büyük bir trafiğin oluşması ve bant genişliğinin azalması anlamına gelmektedir.
    • RIP’in kurtarma (recovery) süresi uzundur, bu da değişen topolojinin tekrardan düzenlenebilmesini geciktirir ve ağda istenmeyen döngülere neden olur. Bu döngüler yüzünden de veriler  ulaşamaz, kullanıcıya teslim edilemez.

#### OSPF (Open Shortest Path First - İlk Açık Yöne Öncelik) Protokolü 

    OSPF (Open Shortest Path First - İlk Açık Yöne Öncelik), RIP (Routing Information Protocol - Yönlendirme Bilgisi Protokolü) protokolünde bulunan bazı eksik yanları geliştirmek ve düzeltmek için  geliştirilmiş bir protokoldür. RIP'in aksine OSPF, Link-state (Hat Durumu) protokolü olarak tasarlanmıştır. Link-state yönlendirme protokolleri, topolojinin tamamını görebildiği gibi, ağ değişikliklerinde Triggered update (Tetiklenmiş Güncelleme) gönderir. Buna göre yönlendiriciler ağdaki iki nokta arasında bulunan tüm yolların bilgisine ulaştıktan sonra SPF (Shortest Path First - Önce En Kısa Yol) algoritmalarını kullanarak hangi yolun en iyisi olduğuna karar verirler. Ayrıca Link-state Refresh (Hat Durumu Güncellemesi) olarak bilinen, 30 dakikada bir periyodik güncellemeler gönderir. 

    ###OSPF'in Çalışma Yapısı

    OSPF, ağda bir değişiklik olduğu zaman güncelleme paketi üretir. Bir bağlantının durumu değiştiğinde, bunu tespit eden yönlendirici, LSA (Link-State Advertisement - Hat Durumu İlanı) denilen paketi yayınlar. LSA paketi, bütün komşulara iletilir. Her yönlendirici cihaz LSA’nın bir kopyasını alır, LSDB (Link-State Database - Hat Durumu Veritabanı) ‘ yi günceller ve LSA’yı komşu yönlendiricilere iletir. Gönderilen bu LSA sayesinde bütün ağ, ağdaki değişikliği algılayıp bunu yeni topolojiye yansıtır. LSDB, hedef ağa giden en iyi yolu hesaplamak için kullanılır.

#### EIGRP (Enhanced Interior Gateway Routing Protocol – Artırılmış Dahili Ağ Geçidi Yönlendirme Protokolü)

    EIGRP Cisco tarafından IGRP protokolünün yetersiz kalmaya başlamasıyla geliştirilmiş birçok yönden IGRP protokolüne benzemesine rağmen, geliştirilmiş özellikleri sayesinde Cisco cihazların oluşturduğu ağlarda oldukça tercih edilen bir protokoldür. Bu protokol aynı anda Uzaklık Vektörü ve Hat Durumu protokollerinin özelliklerine sahip olduğu için Hybrid (Melez) olarak da adlandırılmaktadır.

    EIGRP’de olabilecek en büyük "hop count" (basamak sayısı - paketin ulastigi yönlendirici sayisi) değeri 224’dir. EIGRP metrik hesaplarken IGRP gibi hat gecikmesi, bant genişliği, güvenilirlik ve yük durumunu metrik olarak kullanır. Buna ek olarak MD5 kripto algoritması kullanılarak yönlendiriciler arasında şifreli kimlik doğrulama ile güvenlik artırılabilir.
    Bu protokolun getirdiği en önemli avantajlardan birisi alternatif yollar arasında yüksek bir geçiş hızı sunmasıdır. EIGRP protokol algoritması olarak DUAL (Diffusing Update Algorithm – Yayılma Güncellemesi Algoritması) algoritmasını kullanır. Bu algoritmayla yönlendirme hesaplanır ve bir problem oluşması durumunda önceden hesaplanmış yedek yönlendirmeye geçer. Diğer yönlendirme protokollerinde böyle bir özellik söz konusu değildir. Bu özellik EIGRP’ye büyük bir hız kazandırır.

    Bu protokolün IGRP’den en önemli farklarından birisi IGRP gibi periodik bir güncelleme yapmamasıdır.  Yönlendirme tablosunda bir değişiklik olduğu zaman ise bütün tablo değil, yalnızca değişiklik olan kısmı diğer yönlendiricilere gönderilir ve bant genişliği en az şekilde kullanılarak ağ trafiği hızlandırılır.

## Dekapsülasyon (Decapsulation)
    Paket hedef cihaza vardığında çeşitli işlemlerden geçerek OSI’nin 3. katmanı olan ağ katmanına ulaşır. Bu katmanda hedef adresi kontrol edilir ve paketin doğru hedefe ulaştığı doğrulanır. Doğrulama işleminden sonra paket dekapsülasyon işleminden geçerek 3. katman başlığı atılır ve 4. katman olan taşıma katmanına geçer.Böylece Ağ Katmanının görevi burada son bulur.


## Ağ Katmanında hangi protokoller mevcut?

#### AppleTalk
	
    AppleTalk protokolü Apple Computer Corporation tarafından geliştirilmiştir. 		Macintosh bilgisayarlarla iletişim kurmak için kullanılır.
	
	
	 	 
#### IPV4-IPV6 (Internet Protocol Version 4-6-İnternet Protokolü)

    IPv4 protokolü, günümüzde bilgisayarların iletişiminin sağlanmasının temelini oluşturur. IPv4 adresleri 8'er bitten oluşan 4 bloktan meydana gelir. Bu da 32 bitlik bir adres demektir. Bu adres bizim internetteki kimliğimizdir. 2^32 tane farklı IPv4 adresi vardır, fakat günümüzün değişen ve gelişen şartlarında bu adresler artık yetmemeye başlamış, bu yüzden IPv6 protokolü oluşturulmuştur. Yakın zaman içersinde IPv4 adreslerinin yerini IPv6 adreslerinin alması beklenmektedir. IPv6 protokolünün IPv4 protokolüne göre birçok avantajı vardır. Bu avantajlar; sağladığı 2^128 tane IP adresi sayesinde daha geniş IP adres alanı, yeni güvenlik özellikleri, paketlerin daha hızlı iletilebilmesini sağlayacak sadeleştirilmiş başlık yapısı, adres atama sunucusu ihtiyacını ortadan kaldıracak olan otomatik adres yapılandırması gibi özellikleri içerir.

#### ICMP (Internet Control Message Protocol - İnternet Kontrol Mesaj Protokolü)
    


    ICMP (Internet Control Message Protocol - İnternet Kontrol Mesaj Protokolü), hata mesajları ve TCP/IP yazılımının kendi mesaj trafiği amaçları için kullanılır. Kontrol amaçlı bir protokoldür. Genel olarak sistemler arası kontrol mesajları IP yerine ICMP üzerinden aktarılır. ICMP, IP ile aynı düzeyde olmasına karşın aslında kendisi de IP’yi kullanır. ICMP, TCP/IP' nin işleyişine yardımcı olan bir protokoldür. Her istemcide mutlaka ICMP protokolü çalışır. Hata durumunda istemci tarafından geri bilgilendirmeyi sağlar. UDP’ye göre daha basit bir yapıdadır. Başlık bilgisinde port numarası bulundurmaz. Bütün ICMP mesajları ağ yazılımı tarafından kendince yorumlanır, ICMP mesajının nereye gideceği ile ilgili bir port numarasına gerek yoktur. ICMP ‘yi kullanan en popüler İnternet uygulaması "PING" komutudur.


#### IGMP(Internet Group Management Protocol - İnternet Grup Yönetim Protokolü)


    IGMP (Internet Group Management Protocol - İnternet Grup Yönetim Protokolü), TCP/IP'de çoklu dağıtım (multicast) üyelerini yönetmek için kullanılan bir iletişim protokolüdür. Taşıma protokolü gibi davranmamasına rağmen, ağ katmanının üzerinde çalışması IP çoklu dağıtımın önemli bir özelliğidir. Tekli dağıtım (unicast) bağlantılardaki ICMP’ye benzerdir. IGMP, internet üzerinden izlenilen videolarda (online streaming video) ve oyunlarda kullanılabilir. Bu tip uygulamaları desteklerken kaynaklarının daha verimli şekilde kullanılmasını sağlar. IGMP istemciyi yerel çoklu dağıtım yapan bir yönlendiriciye bağlamak için hem istemci hem de bitişiğindeki ağ anahtarlayıcıları tarafından kullanılır. PIM (Protocol Independent Multicast – Protokolden bağımsız çoklu dağıtım), daha sonra video sunucusundan birçok çokludağıtım istemcisine trafiği yönlendirmek için, yerel ve uzaktaki çoklu dağıtım yapan yönlendiriciler arasında kullanılır.

#### IPsec VPN (Internet Protocol Security – İnternet Protokolü Güvenliği)


    IPSec, şifreleme ve güvenlik hizmetlerini kullanarak IP protokollerinin güvenlik ihtiyaçlarını karşılamak için IETF (Internet Engineering Task Force – İnternet Mühendisliği Görev Gücü) tarafından geliştirilmiş bir güvenlik protokolüdür. Bu protokol sayesinde veriler ağ üzerinde güvenli bir şekilde gitmesi gereken hedeflere ulaşır. IPSec ağ katmanında çalışarak IP paketlerinin IPSec aygıtları arasında korunmasını ve kimlik denetiminin gerçekleşmesini sağlar. IPSec ağ katmanında çalıştığı için uygulamadan bağımsız olarak her veriyi şifreler ve şifre sonrası oluşturduğu başlık ile verinin İnternette rahatlıkla yolculuk edebilmesini sağlar. Bu yüzden günümüzde VPN (Virtual Private Network - Sanal Özel Ağ) teknolojisinin altyapısını oluşturmaktadır. Genellikle IPsec ile VPN kavramları birbirleriyle karıştırılır. VPN iki uç nokta arasında bir sanal ağ kurmak için kullanılır. IPSec, oluşturulan VPN bağlantılarına güvenliği arttırıcı fonksiyonlar sağlar. VPN oluşturmak için katman 2 ve katman 3 de farklı yollar mevcuttur. IPSec bu yollardan sadece bir tanesidir. Günümüzde İnternet’in gelişmesiyle birlikte IPSec VPN bağlantılar kolaylıkla yapılabildiğinden bu iki kavram iç içe geçmiş durumdadır.

    IPSec protokolleri ağ katmanında çalıştığı için diğer güvenlik protokollerine göre daha esnektir. SSL (Secure Socket Layer - Güvenli Soket Katmanı), TLS (Transport Layer Security - Geçiş Katmanı Güvenliği), SSH (Secure Shell - Güvenli Kabuk) 4. ve daha üst katmanlarda çalışmaktadır. IPSec, içinde TCP ve UDP’nin de bulunduğu katman 4 ve yukarı katman protokolleri koruyabilir. IPSec’in diğer güvenlik protokollerinden bir üstünlüğü ise IPSec’in uygulama katmanından yani kullanıcıların yazılımlarından bağımsız çalışabilmesidir. Fakat diğer protokolleri (SSL gibi) kullanabilmek için kullanıcının yazılımının o protokolü desteklemesi gerekmektedir. 

	
#### ARP (Adres Çözümleme Protokolü)


    Yerel ağlarda kullanılan en yaygın arayüz Ethernettir. Ethernet arayüzüne sahip olan ağ kartları ile yerel ağlara kolayca bağlanılmaktadır. Bu arayüzler birbirlerine paket göndermek için kendilerine üretim aşamasında verilmiş 48 bit lik fiziksel adresleri (mac adresi) kullanırlar. TCP/IP protokolü ise veri gönderip almak için 32 bit lik IP adreslerini kullanır. Yerel ağda haberleşmek için veri alış-verişi yapılacak cihazın fiziksel adresi bilinmelidir. Bu işlem için kullanılan protokole, yani IP si bilinen cihazın fiziksel adresinin öğrenilmesi protokolüne Adres Çözümleme Protokolü (Address Resolution Protocol) denir. 
	




	
