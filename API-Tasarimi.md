# API Tasarımı - OpenAPI Specification (OAS)

**Grello Projesi OpenAPI Spesifikasyon Dosyası:** [openapi.yaml](openapi.yaml)

Bu doküman, Grello Proje ve Görev Yönetimi sistemi için OpenAPI Specification (OAS) 3.0 standardına göre hazırlanmış API tasarımını ve mimari kararlarını içermektedir.

## 1. Mimari Kararlar ve Standartlar

API tasarımı yapılırken aşağıdaki modern yazılım mühendisliği standartları ve pratikleri uygulanmıştır:

- **Sığ Yönlendirme (Shallow Routing):** Görevler (Tasks) oluşturulurken bir projeye bağlıdır (`/api/projects/{projectId}/tasks`), ancak görevler oluştuktan sonra doğrudan kendi kimlikleri üzerinden yönetilir (`/api/tasks/{taskId}`). Bu sayede URL'lerin gereksiz uzamasının önüne geçilmiştir.
- **UUID Kullanımı:** Tahmin edilebilir ID'lerin yaratacağı güvenlik açıklarını engellemek ve çakışmaları önlemek amacıyla tüm kaynaklarda (Project ve Task) `UUID v4` formatı tercih edilmiştir.
- **Güvenlik (Authentication & Authorization):** Tüm uç noktalar JWT tabanlı kimlik doğrulama ile korunmaktadır. Kullanıcıların sadece kendi kaynaklarına erişebilmesi için `401 Unauthorized` ve `403 Forbidden` hata kontrolleri tüm endpoint'lere dahil edilmiştir.
- **API Ön Eki (API Routing):** Frontend ve backend çakışmalarını önlemek amacıyla tüm rotaların başına `/api` ön eki getirilmiştir.

## 2. API Uç Noktaları (Endpoints)

Sistemde toplam 10 adet fonksiyonel gereksinimi karşılayan uç noktalar bulunmaktadır:

### Proje Yönetimi
- `POST /api/projects` - Yeni Proje Oluşturma
- `GET /api/projects` - Mevcut Projeleri Listeleme
- `PUT /api/projects/{projectId}` - Proje Güncelleme
- `DELETE /api/projects/{projectId}` - Proje Silme

### Görev Yönetimi
- `POST /api/projects/{projectId}/tasks` - Projeye Yeni Görev Ekleme
- `GET /api/projects/{projectId}/tasks` - Projeye Ait Görevleri Listeleme
- `PUT /api/tasks/{taskId}` - Görev Güncelleme
- `DELETE /api/tasks/{taskId}` - Görev Silme
- `PUT /api/tasks/{taskId}/status` - Görev Durumu Güncelleme
- `GET /api/tasks?status={status}` - Görevleri Durumuna Göre Filtreleme

---