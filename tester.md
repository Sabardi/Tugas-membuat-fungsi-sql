CREATE FUNCTION kategori_harga (harga DOUBLE)
    RETURNS VARCHAR(20)
    BEGIN
        DECLARE kategori VARCHAR(20);
        select harga_jual from produk 
            IF harga > 0 AND harga <= 500000  THEN
            SET kategori = 'murah';
        ELSEIF harga > 500000 AND harga <= 3000000 THEN
            SET kategori = 'sedang';
        ELSEIF  harga > 3000000 AND harga <= 10000000 THEN
            SET kategori = 'mahal';
        ELSE
            SET kategori = 'sangat mahal';
        END IF;
        RETURN kategori;
    END$$

    SELECT kategori_harga.harga_jual AS kategori, kategori_harga.harga_beli AS harga
FROM produk AS kategori_harga;