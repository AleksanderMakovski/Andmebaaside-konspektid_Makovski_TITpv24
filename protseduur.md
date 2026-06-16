# Andmebaaside konspektid - Aleksander Makovski

[Põhimõsted](pohimoisted.md) | [Protseduurid](protseduur.md) | [Protseduurid XAMPP](protseduurXAMPP.md) | [Trigerid](triger.md) | [HotelliRuumid](hotelliruum.md) | [Kasutajad](kasutajad.md) | [Keys Kodutöö](keys.md)



## SQL Protseduurid
- store procedure - salvestatus protseduurid - хранимые процедуры
- sama nagu funktsioonid programmerimises - mingid tegevused, mis käivitakse automaatselt protseduuri kasutamisel.
```
CREATE PROCEDURE lisaGuest
--@parameetrid
@uusNimi varchar(25),
@uusPerenimi varchar(30),
@kuupaev date
AS
BEGIN
--protseduuri sisu
    INSERT INTO guest(firstname, lastname, memberSince)
	VALUES (@uusNimi, @uusPerenimi, @kuupaev);
	SELECT * FROM guest;
END
```

<img width="215" height="433" alt="{7066B50D-7103-4E8A-8892-689AC24551A3}" src="https://github.com/user-attachments/assets/2c027d3f-b0b5-40d9-8e34-8908d6e7e6e3" />

<img width="426" height="336" alt="{DA8D853B-889B-40DD-B468-53C285B93BBD}" src="https://github.com/user-attachments/assets/34be1baa-8574-4fff-a101-fe0e8c38564f" />

```
--protseduur, mis kustutab guest id järgi
CREATE PROCEDURE kustutaGuest
@kustutaId int
AS
BEGIN
    SELECT * FROM guest;
    DELETE FROM guest WHERE guestID=@kustutaId;
	SELECT * FROM guest;
END
```

<img width="350" height="354" alt="{68523A48-4F97-4438-A024-F35B6FDBAB88}" src="https://github.com/user-attachments/assets/976c6947-ff22-49ad-bf68-1d8b30bf950b" />

```
CREATE PROCEDURE otsing1taht
@taht char(1)
AS
BEGIN
    SELECT * FROM guest WHERE firstname LIKE @taht + '%'; --% -teised sümboolid
END

--kutse
EXEC otsing1taht 'V'
```

<img width="267" height="228" alt="{A9862068-9D49-48AD-ACEA-4293C7AC5F3C}" src="https://github.com/user-attachments/assets/f3c75f4a-5ed4-4a04-8892-7591673e350c" />

```
--kutse
DECLARE @minArve MONEY, @maxArve MONEY;
EXEC minmaxArve @minArve OUTPUT, @maxArve OUTPUT;
PRINT 'Min arve = ' + CONVERT(varchar, @minArve);
PRINT 'Max arve = ' + CONVERT(varchar, @maxArve);
```

<img width="469" height="336" alt="{4EEF929D-7D61-4043-8D0D-8133D5C05A2D}" src="https://github.com/user-attachments/assets/22a5dcec-09be-440f-8e87-229f9c18491b" />

```
--Protseduur veeru lisamiseks või kustutamiseks
CREATE PROCEDURE muudatus
    @tegevus varchar(10),
    @tabelinimi varchar(25),
    @veerunimi varchar(25),
    @tyyp varchar(25) = NULL
AS
BEGIN
    DECLARE @sqltegevus varchar(max);
    SET @sqltegevus = CASE 
        WHEN @tegevus = 'add' THEN 
            CONCAT('ALTER TABLE ', @tabelinimi, ' ADD ', @veerunimi, ' ', @tyyp)
        WHEN @tegevus = 'drop' THEN 
            CONCAT('ALTER TABLE ', @tabelinimi, ' DROP COLUMN ', @veerunimi)
    END;
    PRINT @sqltegevus;
    EXEC (@sqltegevus);
END;
```

<img width="473" height="352" alt="{9A1C1B33-9E16-4128-9334-9192C26AF143}" src="https://github.com/user-attachments/assets/df37fee4-9de2-45d1-86b9-46c2cbcdd275" />
