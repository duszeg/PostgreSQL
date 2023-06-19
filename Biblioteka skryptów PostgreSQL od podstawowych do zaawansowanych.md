<h1>Biblioteka skrytpów PostgreSQL</h1>

<h2>Podstawowe skypty: </h2>
<br>

1. **Tworzenie tabeli:**
```sql
CREATE TABLE nazwa_tabeli (
    kolumna1 typ_danych,
    kolumna2 typ_danych,
    ...
);

```
<br>

2. **Wstawianie danych do tabeli:**
```sql
INSERT INTO nazwa_tabeli (kolumna1, kolumna2, ...)
VALUES (wartość1, wartość2, ...);

```
<br>

3. **Aktualizacja danych w tabeli:**
```sql
UPDATE nazwa_tabeli
SET kolumna = nowa_wartość
WHERE warunek;

```
<br>

4. **Usuwanie danych z tabeli:**
```sql
DELETE FROM nazwa_tabeli
WHERE warunek;

```
<br>

5. **Tworzenie indeksu:**
```sql
CREATE INDEX nazwa_indeksu
ON nazwa_tabeli (kolumna);
```
<br>

6. **Wykonywanie zapytań na tabelach:**
```sql
SELECT kolumna1, kolumna2, ...
FROM nazwa_tabeli
WHERE warunek
ORDER BY kolumna
LIMIT ilość;
```
<br>

7. **Łączenie tabel:**
```sql
SELECT kolumna1, kolumna2, ...
FROM tabela1
INNER/LEFT/RIGHT JOIN tabela2 ON tabela1.kolumna = tabela2.kolumna;
```
<br>

<h2>Zaawansowane skrypty:</h2>
<br>

1. **Tworzenie widoku**
```sql
CREATE VIEW nazwa_widoku AS
SELECT kolumna1, kolumna2, ...
FROM nazwa_tabeli
WHERE warunek;

```
<br>

2. **Tworzenie funkcji**
```sql
CREATE FUNCTION nazwa_funkcji (parametr typ_danych)
RETURNS typ_danych AS $$
BEGIN
    -- kod funkcji
END;
$$ LANGUAGE plpgsql;

```
<br>

3. **Wywoływanie funkcji**
```sql
SELECT nazwa_funkcji(parametr);

```
<br>

4. **Tworzenie procedury składowanej**
```sql
CREATE PROCEDURE nazwa_procedury (parametr typ_danych)
LANGUAGE plpgsql
AS $$
BEGIN
    -- kod procedury
END;
$$;

```
<br>

5. **Tworzenie triggera**
```sql
CREATE TRIGGER nazwa_trigera
BEFORE/AFTER INSERT/UPDATE/DELETE
ON nazwa_tabeli
FOR EACH ROW
EXECUTE FUNCTION nazwa_funkcji();

```
<br>

6. **Tworzenie indeksu na wielu kolumnach**
```sql
CREATE INDEX nazwa_indeksu
ON nazwa_tabeli (kolumna1, kolumna2, ...);

```
<br>

7. **Tworzenie indeksu z różnymi metodami sortowania**
```sql
CREATE INDEX nazwa_indeksu
ON nazwa_tabeli (kolumna)
USING metoda_sortowania;

```
<br>

8. **Tworzenie widoku z wykorzystaniem złączeń**
```sql
CREATE VIEW nazwa_widoku AS
SELECT t1.kolumna1, t2.kolumna2, ...
FROM tabela1 t1
INNER JOIN tabela2 t2 ON t1.klucz = t2.klucz;

```
<br>

9. **Tworzenie funkcji z parametrami opcjonalnymi**
```sql
CREATE FUNCTION nazwa_funkcji (parametr1 typ_danych, parametr2 typ_danych DEFAULT wartość_domyslna)
RETURNS typ_danych AS $$
BEGIN
    -- kod funkcji
END;
$$ LANGUAGE plpgsql;

```
<br>

10. **Tworzenie funkcji agregujących**
```sql
CREATE FUNCTION nazwa_funkcji (typ_danych)
RETURNS typ_danych AS $$
BEGIN
    -- kod funkcji
END;
$$ LANGUAGE plpgsql
AGGREGATE;

```
<br>

11. **Tworzenie procedur składowanych z parametrami wejściowymi i wyjściowymi**
```sql
CREATE PROCEDURE nazwa_procedury (IN parametr1 typ_danych, OUT parametr2 typ_danych)
LANGUAGE plpgsql
AS $$
BEGIN
    -- kod procedury
END;
$$;

```
<br>

12. **Tworzenie triggera wyzwalanego przez określone działania**
```sql
CREATE TRIGGER nazwa_trigera
AFTER INSERT/UPDATE/DELETE OF kolumna
ON nazwa_tabeli
FOR EACH ROW
WHEN (warunek)
EXECUTE FUNCTION nazwa_funkcji();

```
<br>

13. **Tworzenie indeksu pełnotekstowego**
```sql
CREATE INDEX nazwa_indeksu
ON nazwa_tabeli
USING gin (kolumna tsvector_column);

```
<br>

14. **Używanie zapytania RECURSIVE do wykonania rekurencyjnych operacji**
```sql
WITH RECURSIVE nazwa_cte (kolumna1, kolumna2, ...)
AS (
    SELECT początkowe_wartości
    FROM tabela
    WHERE warunek
    UNION ALL
    SELECT kroki_rekurencji
    FROM nazwa_cte
    WHERE warunek
)
SELECT * FROM nazwa_cte;

```
<br>

<h2>

***Podsumowując, podstawowe operacje obejmują podstawową manipulację danymi, tworzenie tabel i indeksów, a także podstawowe zapytania. Zaawansowane operacje obejmują bardziej zaawansowane funkcje, takie jak tworzenie funkcji, procedur składowanych i triggerów, a także bardziej zaawansowane techniki, takie jak indeksy na wielu kolumnach, indeksy pełnotekstowe i rekurencyjne zapytania.***
</h2>
