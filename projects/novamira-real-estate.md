# NovaMira Real Estate

Live site: [novamirarealestate.com](https://novamirarealestate.com)

NovaMira Real Estate, emlak ilanlarının web üzerinden yayınlanması ve yönetilmesi için geliştirdiğim ticari bir real estate platformudur. Projede public tarafta ilan listeleme, ilan detayları, arama/filtreleme ve kurumsal sayfalar bulunurken; yönetim tarafında ilan, kategori, medya, kullanıcı ve site ayarları için ayrı bir admin deneyimi tasarlandı.

Kaynak kod ticari proje kapsamında private tutulmaktadır. Bu doküman, projenin teknik kapsamını ve geliştirilen ana parçaları özetler.

## Scope

- Emlak ilan listeleme ve ilan detay sayfaları
- Kategori ve alt kategori yönetimi
- Dinamik ilan alanları ve kategoriye göre değişen form yapısı
- Görsel/video medya yükleme akışı
- İlan durumu yönetimi
- Admin dashboard
- Kullanıcı, rol ve profil yönetimi
- Site ayarları, iletişim ve hakkımızda içerikleri
- Türkiye il/ilçe/mahalle verileriyle lokasyon seçimi
- Arama ve filtreleme davranışlarının loglanması

## Architecture

NovaMira iki ayrı yapıdan oluşur:

- `NovaMiraServer`: Backend API, domain modeli, application katmanı, persistence ve infrastructure servisleri.
- `NovaMiraUI`: Public web sitesi ve admin paneli için ASP.NET Core MVC tabanlı arayüz.

Backend tarafında Clean Architecture yaklaşımına yakın bir ayrım kullanıldı:

- `Domain`: Entity, enum ve temel domain sınıfları
- `Application`: CQRS/MediatR handlerları, DTO'lar, validation, servis sözleşmeleri
- `Persistence`: Entity Framework Core, repository, unit of work, entity configuration
- `Infrastructure`: Auth, token, storage ve dış servis entegrasyonları
- `Presentation/API`: REST endpointleri ve Swagger/OpenAPI katmanı

## Technical Highlights

- ASP.NET Core 8
- Entity Framework Core ve SQL Server
- MediatR ile command/query ayrımı
- FluentValidation pipeline davranışı
- JWT tabanlı authentication
- ASP.NET Identity ile kullanıcı yönetimi
- Repository ve Unit of Work pattern
- AutoMapper ile DTO mapping
- ImageSharp ile görsel işleme
- FFMpegCore ile video/medya tarafı için altyapı
- Swagger/OpenAPI dokümantasyonu
- API versioning

## Main Modules

- Auth: login, token refresh, current user bilgisi
- Users: kullanıcı oluşturma, rol oluşturma, profil güncelleme, şifre değiştirme
- Categories: ana kategori, alt kategori ve dinamik alan yönetimi
- Listings: ilan oluşturma, güncelleme, silme, durum değiştirme, slug/detail, filtreleme
- Files: görsel yükleme
- Dashboard: ilan, kullanıcı, lokasyon ve arama istatistikleri
- Turkey data: il, ilçe, mahalle, köy ve lokasyon verileri

## Result

Proje, emlak işletmesinin ilanlarını merkezi bir panelden yönetmesini ve ziyaretçilerin güncel ilanları filtreleyerek incelemesini sağlayan canlı bir platform olarak yayına alındı.
