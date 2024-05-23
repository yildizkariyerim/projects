# Projects for Beginner
Bu çalışmalarda ilgili yazılım dilinin başlangıç seviyesinde olan herkesin pratik yapacağı projeler yer alıyor. Proje 1 haftalık günlük yapacağınız to-do listesini ve hazır veri setini içeriyor.

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











    
