MariaDB [db_post_sib6]> DELIMITER $$
MariaDB [db_post_sib6]> CREATE FUNCTION kategori_harga (harga DOUBLE)
    -> RETURNS VARCHAR(20)
    -> BEGIN
    ->     DECLARE kategori VARCHAR(20);
    ->
    ->     IF harga > 0 AND harga <= 500000  THEN
    ->         SET kategori = 'murah';
    ->     ELSEIF harga > 500000 AND harga <= 3000000 THEN
    ->         SET kategori = 'sedang';
    ->     ELSEIF  harga > 3000000 AND harga <= 10000000 THEN
    ->         SET kategori = 'mahal';
    ->     ELSE
    ->         SET kategori = 'sangat mahal';
    ->     END IF;
    ->     RETURN kategori;
    -> END$$
Query OK, 0 rows affected (0.008 sec)

MariaDB [db_post_sib6]> DELIMITER ;