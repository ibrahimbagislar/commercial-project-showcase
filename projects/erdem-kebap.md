# Erdem Kebap

Canlı site: [erdemkebap.com](https://erdemkebap.com)

Erdem Kebap, restoranın dijital varlığını yönetmek için geliştirdiğim ticari web projesidir. Site tarafında restoran tanıtımı, menü, galeri, iletişim ve marka hikayesi öne çıkarılırken; admin tarafında ürün, kategori, paket menü, içerik ve iletişim mesajları yönetilebilecek şekilde yapı kuruldu.

Kaynak kod ticari proje kapsamında private tutulmaktadır. Bu doküman, projenin teknik kapsamını ve geliştirilen ana parçaları özetler.

## Proje Kapsamı

- Restoran ana sayfası
- Hakkımızda, galeri ve iletişim sayfaları
- Dijital menü / QR menü deneyimi
- Ürün ve kategori yönetimi
- Paket menü yönetimi
- Sayfa içeriklerini admin panelinden güncelleme
- Site ayarları ve görsel varlık yönetimi
- İletişim formu ve mesaj yönetimi
- Admin login ve yönetim arayüzü

## Mimari

Proje frontend ve backend olarak iki ana bölümden oluşur:

- `ErdemKebap.Frontend`: Public site ve admin paneli için ASP.NET Core MVC arayüzü.
- `ErdemKebap.Backend`: REST API, application servisleri, domain modelleri ve persistence katmanı.

Backend tarafı katmanlı yapıdadır:

- `Domain`: temel entity yapıları
- `Application`: servis arayüzleri ve iş kuralları
- `Infrastructure`: EF Core repositoryleri, cache ve görsel depolama servisleri
- `Api`: REST endpointleri, CORS, Swagger/OpenAPI ve uygulama giriş noktası

## Teknik Öne Çıkanlar

- ASP.NET Core 8
- Entity Framework Core ve SQL Server
- REST API
- Swashbuckle/Swagger
- In-memory cache
- ImageSharp ile görsel işleme altyapısı
- MVC/Razor Views ile public site ve admin arayüzü
- Admin API key yaklaşımı
- Responsive web arayüzü

## Ana Modüller

- Categories: menü kategorileri için CRUD işlemleri
- Products: ürün oluşturma, güncelleme, silme ve listeleme
- Package Menus: paket menü yönetimi
- Menu: public menü verisinin hazırlanması
- Page Contents: statik sayfaların içeriklerini dinamik yönetme
- Site Settings: telefon, adres, sosyal bağlantılar, çalışma saatleri ve görsel ayarlar
- Contact Messages: iletişim mesajlarını alma, okundu işaretleme ve silme
- Admin Frontend: ürün, kategori, içerik, görünüm, paket menü ve mesaj ekranları

## Sonuç

Proje, restoranın menüsünü ve temel site içeriklerini kod değişikliği gerektirmeden yönetebileceği, ziyaretçilerin de güncel menü ve iletişim bilgilerine hızlıca ulaşabileceği canlı bir web sistemi olarak yayına alındı.
