1. **Proje Oluşturma**
   - **API Metodu:** `POST /projects`
   - **Açıklama:** Kullanıcının yeni bir proje oluşturmasını sağlar. Kullanıcı proje adı ve açıklama gibi bilgileri girerek yeni bir proje tanımlayabilir. Oluşturulan proje veritabanına kaydedilir ve kullanıcıya ait projeler listesine eklenir.

2. **Proje Listeleme**
   - **API Metodu:** `GET /projects`
   - **Açıklama:** Kullanıcının mevcut projelerini listelemesini sağlar. Kullanıcıya ait tüm projeler sistemden çekilerek liste halinde gösterilir.

3. **Proje Güncelleme**
   - **API Metodu:** `PUT /projects/{projectId}`
   - **Açıklama:** Kullanıcının mevcut bir projeye ait bilgileri güncellemesini sağlar. Proje adı veya açıklaması gibi bilgiler değiştirilebilir. Güncellenen bilgiler veritabanında saklanır.

4. **Proje Silme**
   - **API Metodu:** `DELETE /projects/{projectId}`
   - **Açıklama:** Kullanıcının mevcut bir projeyi silmesini sağlar. Silinen proje ve projeye ait tüm görevler sistemden kalıcı olarak kaldırılır.

5. **Görev Oluşturma**
   - **API Metodu:** `POST /projects/{projectId}/tasks`
   - **Açıklama:** Kullanıcının belirli bir projeye yeni bir görev eklemesini sağlar. Görev başlığı, açıklaması ve başlangıç durumu belirlenerek görev oluşturulur ve ilgili projeye eklenir.

6. **Görev Listeleme**
   - **API Metodu:** `GET /projects/{projectId}/tasks`
   - **Açıklama:** Kullanıcının belirli bir projeye ait tüm görevleri listelemesini sağlar. Görevler proje bazında çekilerek kullanıcıya gösterilir.

7. **Görev Güncelleme**
   - **API Metodu:** `PUT /tasks/{taskId}`
   - **Açıklama:** Kullanıcının mevcut bir görevin bilgilerini güncellemesini sağlar. Görev başlığı, açıklaması veya diğer detayları değiştirilebilir.

8. **Görev Silme**
   - **API Metodu:** `DELETE /tasks/{taskId}`
   - **Açıklama:** Kullanıcının bir görevi sistemden silmesini sağlar. Silinen görev veritabanından kalıcı olarak kaldırılır.

9. **Görev Durumu Güncelleme**
   - **API Metodu:** `PUT /tasks/{taskId}/status`
   - **Açıklama:** Kullanıcının bir görevin durumunu değiştirmesini sağlar. Görev durumu "yapılacak", "devam ediyor" veya "tamamlandı" gibi değerler alabilir.

10. **Görev Filtreleme**
    - **API Metodu:** `GET /tasks?status={status}`
    - **Açıklama:** Kullanıcının görevleri durumlarına göre filtrelemesini sağlar. Belirtilen duruma sahip görevler listelenir ve kullanıcıya gösterilir.
