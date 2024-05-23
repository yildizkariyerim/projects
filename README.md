# Başlangıç Seviye Projeler / GitHub ve LinkedIn Paylaşım Kılavuzu

Bu çalışmalarda ilgili yazılım dilinin başlangıç seviyesinde olan herkesin pratik yapacağı projeler yer alıyor. 
Proje 1 haftalık günlük yapacağınız to-do listesini ve hazır veri setini içeriyor.
En sonda bu yaptığınız projeyi github'a yükleyebilmek adına yönlendirme bulunuyor.
Github projenizi LinkedIn'de paylaşmak isterseniz Türkçe ve İngilizce paylaşım taslağına da ulaşabilirsiniz.
Kolaylıklar.

## 1 Haftalık SQL Eğitim Projesi

### Proje Konusu: Kitap Satış Analizi
Bu proje, bir kitap satış mağazasının veritabanını kullanarak çeşitli SQL sorgulamalarını ve analizlerini içerecek.

### Örnek Veri Seti

Tables:
  Books: Kitap bilgileri
    book_id (INT, Primary Key)
    title (VARCHAR)
    author (VARCHAR)
    genre (VARCHAR)
    price (DECIMAL)
  Sales: Satış bilgileri
    sale_id (INT, Primary Key)
    book_id (INT, Foreign Key)
    sale_date (DATE)
    quantity (INT)

## Günlük To-Do Listesi
### Gün 1: Veritabanı Kurulumu ve Veri Girişi

- SQL veritabanı oluşturma.
- Books ve Sales tablolarını oluşturma.
- Örnek veri ekleme.

```sql
CREATE TABLE Books (
    book_id INT PRIMARY KEY,
    title VARCHAR(100),
    author VARCHAR(100),
    genre VARCHAR(50),
    price DECIMAL(5, 2)
);

CREATE TABLE Sales (
    sale_id INT PRIMARY KEY,
    book_id INT,
    sale_date DATE,
    quantity INT,
    FOREIGN KEY (book_id) REFERENCES Books(book_id)
);

INSERT INTO Books (book_id, title, author, genre, price) VALUES
(1, 'Book A', 'Author X', 'Fiction', 10.99),
(2, 'Book B', 'Author Y', 'Non-Fiction', 12.99),
(3, 'Book C', 'Author Z', 'Fiction', 8.99);

INSERT INTO Sales (sale_id, book_id, sale_date, quantity) VALUES
(1, 1, '2023-05-01', 2),
(2, 2, '2023-05-02', 1),
(3, 3, '2023-05-03', 4);
```
### Gün 2: Temel SQL Sorguları

- SELECT, FROM, WHERE kullanarak basit sorgular yazma.
- Örneğin, belirli bir yazarın kitaplarını listeleme.

```sql
SELECT * FROM Books WHERE author = 'Author X';
```

### Gün 3: Veri Filtreleme ve Sıralama

ORDER BY ve LIMIT kullanımı.
Fiyatı en yüksek 3 kitabı listeleme.

```sql
SELECT * FROM Books ORDER BY price DESC LIMIT 3;
```

### Gün 4: Veri Gruplama ve Toplama Fonksiyonları

- GROUP BY ve toplama fonksiyonları (COUNT, SUM, AVG).
- Her türe göre toplam kitap sayısını listeleme.

```sql
SELECT genre, COUNT(*) AS total_books FROM Books GROUP BY genre;
```

### Gün 5: Tabloları Birleştirme

- JOIN kullanımı.
- Satışlarla ilgili kitap bilgilerini birleştirme ve listeleme.

```sql
SELECT Books.title, Sales.sale_date, Sales.quantity
FROM Sales
JOIN Books ON Sales.book_id = Books.book_id;
```

### Gün 6: Gelişmiş Sorgular ve Alt Sorgular

- Alt sorgular ve CASE ifadeleri.
- Belirli bir tarihten sonra en çok satan kitabı bulma.

```sql
SELECT title FROM Books WHERE book_id = (
    SELECT book_id FROM Sales WHERE sale_date > '2023-05-01' ORDER BY quantity DESC LIMIT 1
);
```

### Gün 7: Proje Raporu ve Sonuç Çıkarımları

- Elde edilen verileri analiz etme.
- Rapor hazırlama ve sonuçları çıkarma.

```sql
-- Örneğin, en çok satan kitap türü:
SELECT genre, SUM(quantity) AS total_sold FROM Sales
JOIN Books ON Sales.book_id = Books.book_id
GROUP BY genre
ORDER BY total_sold DESC;
```

## GitHub'da Proje Paylaşımı

### Adım 1: GitHub Hesabı Oluşturma ve Yeni Repo Açma

- GitHub hesabı oluşturun.
- Yeni bir repository (repo) oluşturun.

### Adım 2: Proje Dosyalarını Hazırlama

- SQL dosyalarını (schema.sql, data.sql, queries.sql) yerel makinenizde oluşturun.
- Proje açıklaması için bir README.md dosyası yazın.

### Adım 3: Dosyaları GitHub'a Yükleme

- Git Bash veya terminal kullanarak yerel dosyaları repo'ya yükleyin.

```sql
cd /path/to/your/project
git init
git remote add origin https://github.com/yourusername/your-repo-name.git
git add .
git commit -m "Initial commit"
git push origin master
```

## LinkedIn Paylaşım Taslağı

### Türkçe

**Başlık:** SQL Eğitim Projemi Tamamladım!


**İçerik:**

Merhaba,

Son bir haftadır SQL eğitimime odaklandım ve sonunda ilk projemi tamamladım! 🎉

Bu projede bir kitap satış mağazasının veritabanını oluşturdum ve çeşitli SQL sorguları ile analizler yaptım. Veritabanı oluşturma, veri sorgulama, gruplama ve tabloları birleştirme gibi temel SQL konularında pratik yaptım.

Projemi GitHub'da paylaştım. İncelemek isterseniz işte link: [GitHub Proje Linki]

Bu deneyim benim için çok öğretici oldu ve SQL becerilerimi geliştirmeme yardımcı oldu. Destek olan herkese teşekkür ederim!

#SQL #DataAnalysis #VeriBilimi #Eğitim #Proje

### English

**Title:** Completed My SQL Learning Project!

**Content:**

Hello,

Over the past week, I've been deeply engaged in enhancing my SQL skills and I'm thrilled to share that I've completed my first SQL project! 🎉

In this project, I developed a database for a book sales store and performed various SQL queries and analyses. I practiced essential SQL topics such as database creation, data querying, grouping, and table joins.

I've shared my project on GitHub. Feel free to check it out: [GitHub Project Link]

This experience has been incredibly educational and has significantly boosted my SQL proficiency. Many thanks to everyone who supported me along the way!

#SQL #DataAnalysis #DataScience #LearningJourney #Project

Paylaşımlarınızda beni etiketleyerek çalışmalarım hakkında geri bildirimlerinizi de paylaşırsanız çok sevinirim.

**İletişim Bilgilerim:**
Instagram: @edayaldz
https://www.linkedin.com/in/edayaldz/
