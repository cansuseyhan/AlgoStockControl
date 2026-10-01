# AlgoStockControl
Advanced Level Python Algorithm &amp; Data Structures Project 

Akıllı Spariş Yönetim Sistemi - Smart Order Manager

Bu proje ürün, stok ve sipariş süreçlerini yönetirken gelişmiş veri yapıları, algoritmik yaklaşımları ve standart kütüphane araçlarını kullandığım bir data structures projesidir.

İş Mantığı
- Ürünler sisteme kaydedilir.
- Ürün ID'si üzerinden ürün bilgilerine hızlı erişim sağlanır.
- Ürün adı, kategori, fiyat ve stok bilgileri tutulur.
- Siparişler oluşturulur.
- Her sipariş müşteri, ürünler, öncelik ve durum bilgilerini içerir.
- Sipariş doğrulanır.
- Ürün mevcut mu?
- Ürün satışa kapalı mı?
- Sipariş miktarı geçerli mi?
- Yeterli stok var mı?
- Siparişler öncelik sırasına göre işlenir.
- Priority Queue yapısı kullanılarak önceliği yüksek siparişler önce işlenir.
- Sipariş başarıyla tamamlanırsa stok otomatik olarak azaltılır.
- Satış ve stok raporları oluşturulur.
- Kategori bazında satış miktarları hesaplanır.
- En çok satılan ürünler belirlenir.
- Kritik seviyedeki stoklar tespit edilir.
- Ek veri analizleri gerçekleştirilir.
- Fiyata göre ürün sıralama
- Fiyat indeksleme
- Ürün kombinasyonları
- Müşteri kuyruğu yönetimi
- Kategori bazlı ürün işlemleri

Teknik Bölüm

Performans sebebiyle tüm verileri taramadan kolay erişim sağlamak amacıyla:
- dictionary/nested dictionary kullandım (Ürün verilerine	ID üzerinden eriştim - hash based)
- liste/nested list kullandım (Siparişlerin tutulması için sıralı veri ve iterasyonda sağladı)
- set kullandım (Satışa kapalı ürünlerde üyelik kontrolü daha kolay oldu)
- deque/Queue kullandım (Müşteri kuyruğu FIFO işlemlerinde popleft() ile soldaki ilk eleman üzerinden hızlı işlem sağladı)
- heap kullandım (Öncelikli siparişler için	Priority Queue ile siparişleri her işlemden önce tamamen sıralamadan işlemleri daha performanslı gerçekleşti)
- Counter/collections kullandım (Ürün satış adetlerinde	Frekans hesaplamayı kolaylaştırdı)
- defaultdict kullandım (Kategori satışlarında otomatik varsayılan değer yönetimi sağladı)
- bisect/Binary Search kullandım (Fiyatlar sıralanarak bisect sıralı veri üzerinde binary search mantığı ile konum araması daha performanslı gerçekleşti)
- chain()/Iterators / itertools kullandım (Birden fazla iterasyonu tek akışta işledim)
- combinations() kullandım (Ürünlerden benzersiz ikili kombinasyonlar oluşturdum)
- Generator Expression kullandım
sum( products[product_id]["price"] * quantity for product_id, quantity in items )
(Gereksiz bir ara liste oluşturmadan toplam hesapladım)
- Comprehension/Set-List Comprehension kullandım (Böylelikle daha kısa şekilde yazdım)
- itemgetter/sorted / operator kullandım
sorted(products.values(), key=itemgetter("price"))
(Sıralama anahtarını belirleyip, lambda kullanmadan sıraladım)
- *args ve **kwargs kullandım
report("stok", "satış", detay=True)
(Raporlama bölümünü esnek bir API mantığında tasarlayıp,farklı rapor bölümlerini dinamik olarak çalıştırabildim)
- Exception Handling kullandım (Geçersiz bir siparişin tüm sistemi durdurmasını engelleyerek hata yönetimi gerçekleştirdim)
- Aggregation kullandım (siparişlerdeki satış verilerini kategori ve ürün bazında gruplayarak toplam hesapladım)
category_sales[product["category"]] += quantity
product_counter[product["name"]] += quantity
