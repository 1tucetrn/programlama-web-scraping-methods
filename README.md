Web Scraping Yöntemlerinin Karşılaştırılması
Projenin Amacı
Bu projenin temel amacı, Python kullanarak farklı web scraping yöntemlerini uygulamak ve bu yöntemleri karşılaştırmaktır.
Projede kullanılan yöntemler:
BeautifulSoup ile klasik web scraping
Selenium ile tarayıcı otomasyonu kullanarak web scraping
Scrapling ile modern web scraping
Her yöntemle kitap verileri çekilmiş, CSV dosyası olarak kaydedilmiş ve daha sonra veri temizleme işlemleri uygulanmıştır.
Kullanılan Veri Kaynağı
Site:https://books.toscrape.com/ Books to Scrape
Veri türü: Kitap bilgileri
Çekilen kayıt sayısı: 100
Çekilen sayfa sayısı: 5
Her sayfada yaklaşık 20 kitap bulunmaktadır.

1.BeautifulSoup Yöntemi
BeautifulSoup yöntemi projede en kolay ve en kısa uygulanan yöntem olmuştur. Books to Scrape sitesi statik HTML yapısına sahip olduğu için BeautifulSoup ile veri çekme işlemi doğrudan yapılabilmiştir.
Bu yöntemde `requests` kütüphanesi ile sayfanın HTML içeriği alınmış, ardından `BeautifulSoup` ile HTML etiketleri ayrıştırılmıştır.
BeautifulSoup Yönteminin Avantajları
Kurulumu kolaydır.
Kod yapısı kısadır.
Statik sayfalarda hızlı çalışır.
Tarayıcı açmadığı için bilgisayarı yormaz.
CSV çıktısı almak kolaydır.
BeautifulSoup Yönteminin Dezavantajları
Dinamik sitelerde tek başına yeterli olmayabilir.
JavaScript ile sonradan yüklenen verileri çekemez.
HTML yapısı değişirse kodun güncellenmesi gerekir.
Bu Projedeki Sonuç
BeautifulSoup ile 5 sayfadan toplam 100 kitap kaydı başarılı şekilde çekilmiştir. Bu proje için en sade ve kullanımı en kolay yöntem BeautifulSoup olmuştur.
2. Selenium Yöntemi
Selenium yöntemi, tarayıcı otomasyonu kullanarak veri çekme işlemidir. Bu yöntemde Chrome tarayıcısı otomatik olarak açılmış ve sayfalar gerçek kullanıcı gibi gezilmiştir.
Kodda `webdriver.Chrome()` kullanılmıştır.
Selenium Kurulumu ve Çalıştırma Durumu
Selenium kurulumu genel olarak hızlıdır. Local bilgisayarda çalıştırıldığında tarayıcı açılarak veri çekme işlemi başarılı şekilde yapılmıştır.
Selenium bulut ortamlarında, özellikle Google Colab gibi sistemlerde daha fazla hata verebilir. Bunun sebebi Selenium’un tarayıcı ve driver bağlantısına ihtiyaç duymasıdır. Local bilgisayarda Chrome tarayıcısı ve ChromeDriver uyumlu olduğunda daha rahat çalışır.
Selenium Yönteminin Avantajları
Dinamik web sitelerinde kullanılabilir.
JavaScript ile yüklenen içerikleri görebilir.
Gerçek tarayıcı üzerinden işlem yaptığı için kullanıcı davranışına yakın çalışır.
Buton, sayfa geçişi, filtreleme gibi işlemleri otomatikleştirebilir.
Selenium Yönteminin Dezavantajları
BeautifulSoup’a göre daha yavaştır.
Tarayıcı açtığı için daha fazla kaynak tüketir.
Bulut ortamlarında driver ve tarayıcı hatası verebilir.
Kurulum ve ortam ayarı daha dikkat ister.
Bu Projedeki Sonuç
Selenium ile de toplam 100 kitap kaydı başarılı şekilde çekilmiştir. Local ortamda çalışması daha uygun görülmüştür. Dinamik sitelerde güçlü bir yöntemdir, fakat bu proje gibi statik bir sitede BeautifulSoup’a göre daha uzun ve daha ağır bir çözümdür.

3.Scrapling Modern Yöntemi
Scrapling, modern web scraping araçlarından biridir. Bu projede klasik yöntemlere alternatif olarak kullanılmıştır. Scrapling ile CSS seçicileri kullanılarak kitap kartları bulunmuş ve veriler çekilmiştir.
Scrapling Kurulum Deneyimi
Bu projede Scrapling kurulumu BeautifulSoup ve Selenium’a göre daha uğraştırıcı olmuştur. Hem local ortamda hem de bulut ortamında modül hataları alınmıştır.
Özellikle şu sorunlar yaşanmıştır:
Modül eksikliği hataları
Paketlerin tam yüklenmemesi
Ortam uyumsuzluğu
Aynı kurulumun birkaç kez tekrar edilmesi gerekmesi
Scrapling üç defa modül hatası verdikten sonra, gerekli tüm modüller birlikte yüklenerek sorun çözülmüştür. Bu nedenle Scrapling modern bir yöntem olmasına rağmen kurulum açısından daha zorlayıcı olmuştur.
Scrapling Yönteminin Avantajları
Modern bir web scraping aracıdır.
CSS seçicileri ile okunabilir bir kullanım sunar.
Veri çekme işlemi mantıksal olarak kısa yazılabilir.
Yeni nesil scraping araçlarını tanımak açısından faydalıdır.
Scrapling Yönteminin Dezavantajları
Kurulumu bazı ortamlarda sorun çıkarabilir.
Modül hataları yaşanabilir.
Local ve bulut ortamlarında farklı davranabilir.
Yeni bir araç olduğu için hata çözümü BeautifulSoup kadar kolay değildir.
Bu Projedeki Sonuç
Scrapling ile veri çekme işlemi sonunda toplam 100 kitap kaydı alınmıştır. Ancak kurulum süreci diğer yöntemlere göre daha fazla zaman almıştır. Bu nedenle Scrapling, modern ve kullanışlı görünmesine rağmen bu proje özelinde en uğraştırıcı yöntem olmuştur.
Genel Değerlendirme
Bu proje sonucunda üç farklı web scraping yöntemi denenmiştir. Aynı veri kaynağı üzerinde yapılan testlerde üç yöntemle de 100 kayıt çekilebilmiştir. Ancak yöntemlerin kullanım kolaylığı ve hata verme durumları farklı olmuştur.
BeautifulSoup, bu proje için en pratik yöntem olmuştur. Çünkü site statik yapıdadır ve veriler doğrudan HTML içinde yer almaktadır. Kod kısa, anlaşılır ve hızlıdır.
Selenium, özellikle dinamik siteler için daha güçlüdür. Fakat bu projede kullanılan site statik olduğu için Selenium kullanmak zorunlu değildir. Selenium local bilgisayarda çalışmıştır, ancak bulut ortamlarında tarayıcı ve driver ayarları nedeniyle hata verme ihtimali daha yüksektir.
Scrapling, modern bir yöntem olarak denenmiştir. Kod yapısı anlaşılırdır fakat kurulum süreci problemli olmuştur. Local ve bulut ortamında modül hataları yaşanmış, sorun ancak tüm gerekli modüller yüklendikten sonra çözülmüştür.
Bu nedenle proje kapsamında en uygun yöntem BeautifulSoup olarak değerlendirilmiştir. Eğer site dinamik yapıda olsaydı Selenium daha uygun olurdu. Scrapling ise modern scraping araçlarını öğrenmek açısından faydalıdır, ancak kurulum ve ortam uyumluluğu açısından daha dikkatli kullanılmalıdır.
Sonuç
Bu projede Python ile klasik ve modern web scraping yöntemleri uygulanmıştır. BeautifulSoup, Selenium ve Scrapling yöntemleri aynı veri kaynağı üzerinde test edilmiştir. Veri çekme, CSV dosyasına kaydetme, temel veri temizleme ve yöntem karşılaştırması yapılmıştır.
Proje sonucunda:
BeautifulSoup en kolay ve hızlı yöntem olmuştur.
Selenium dinamik siteler için daha uygun görülmüştür.
Scrapling modern bir araç olmasına rağmen kurulum süreci zorlayıcı olmuştur.
Toplam 100 kayıt içeren temiz veri seti oluşturulmuştur.
