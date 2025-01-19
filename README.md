# SQL_Odev3
lcw bootcamp sql 3.ödev reposudur.

-- 1. Country Tablosunda bulunan country sütunundaki ülke isimlerinden 'A' karakteri ile başlayıp 'a' karakteri ile sonlananları sıralama
SELECT country
FROM country
WHERE country LIKE 'A%a'
ORDER BY country;

-- 2. Country Tablosunda bulunan country sütunundaki ülke isimlerinden en az 6 karakterden oluşan ve sonu 'n' karakteri ile sonlananları sıralama
SELECT country
FROM country
WHERE LENGTH(country) >= 6
  AND country LIKE '%n'
ORDER BY country;

-- 3. Film Tablosunda bulunan title sütunundaki film isimlerinden en az 4 adet büyük ya da küçük harf farketmesizin 'T' karakteri içeren film isimlerini sıralama
SELECT title
FROM film
WHERE LOWER(title) LIKE '%t%' -- 't' veya 'T' harflerini içeren film isimlerini seçer
GROUP BY title
HAVING LENGTH(REPLACE(LOWER(title), 't', '')) <= LENGTH(title) - 4
ORDER BY title;

-- 4. Film Tablosunda bulunan tüm sütunlardaki verilerden title 'C' karakteri ile başlayan ve length 90'dan büyük olan ve rental_rate 2.99 olan verileri sıralama
SELECT *
FROM film
WHERE title LIKE 'C%'
  AND length > 90
  AND rental_rate = 2.99
ORDER BY title;

