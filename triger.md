## trigger - triger - päastik
andmebaasi objekt, mis automaatselt käivitud tabeli sündmused(INSERT, UPDATE, DELETE)
```sql
Create table linnad(
linnID int PRIMARY KEY IDENTITY (1,1),
linnanimi varchar(15) NOT NULL,
rahvaarv int);
 
-- tabel, mis täidab triger
Create table logi(
id int PRIMARY KEY IDENTITY (1,1),
kasutaja varchar(25),
aeg DATETIME,
toiming  varchar(100),
andmed TEXT -- triger automaatselt lisab mida sekretaar lisas/kustutas tabelisse linnad
)

select * from linnad;
select * from logi;

-- Jälgib andmete sisestamine tabelis linnad ja teeb vastava kirje tabelis logi
CREATE TRIGGER linnaLisamine
ON linnad --tabelinimi, mis on vaja jälgida
FOR INSERT
AS
INSERT INTO logi(kasutaja, aeg, toiming, andmed)
SELECT
SYSTEM_USER, --kasutaja
GETDATE(),  --aeg
'on tehtud INSERT käsk',  --toiming
inserted.linnanimi  --andmed
FROM inserted;

-- kontrollimiseks insert into linnad
INSERT INTO linnad(linnanimi, rahvaarv)
VALUES ('tartu', 250000);

select * from linnad;
select * from logi;

-- trigeri muutmine
ALTER TRIGGER linnaLisamine
ON linnad --tabelinimi, mis on vaja jälgida
FOR INSERT
AS
INSERT INTO logi(kasutaja, aeg, toiming, andmed)
SELECT
SYSTEM_USER, --kasutaja
GETDATE(),  --aeg
'on tehtud INSERT käsk',  --toiming
CONCAT('linn: ', inserted.linnanimi, ' rahvaarv: ', inserted.rahvaarv)  --andmed
FROM inserted;

INSERT INTO linnad(linnanimi, rahvaarv)
VALUES ('pärnu', 20000);

select * from linnad;
select * from logi;
```

<img width="583" height="578" alt="{A6C69608-7E69-4EEF-B117-3BBADAA4E80F}" src="https://github.com/user-attachments/assets/3fb702a8-96cb-48a3-9820-234851645690" />


```sql
-- delete triger
CREATE TRIGGER linnakustutamine
ON linnad --tabelinimi, mis on vaja jälgida
FOR DELETE
AS
INSERT INTO logi(kasutaja, aeg, toiming, andmed)
SELECT
SYSTEM_USER, --kasutaja
GETDATE(),  --aeg
'on tehtud DELETE käsk',  --toiming
CONCAT('linn: ', deleted.linnanimi, ' rahvaarv: ', deleted.rahvaarv)  --andmed
FROM deleted;

-- kontroll - kuastutada tabelist linnad
DELETE FROM linnad WHERE linnID=1;
select * from linnad;
select * from logi;
```

<img width="676" height="422" alt="{7B4683EC-CAE3-4E26-B424-ADAC0D465A12}" src="https://github.com/user-attachments/assets/68bfd2a5-57cb-401f-926d-1a851f69878e" />


```sql
-- update triger
CREATE TRIGGER linnauuendamine
ON linnad --tabelinimi, mis on vaja jälgida
FOR UPDATE
AS
INSERT INTO logi(kasutaja, aeg, toiming, andmed)
SELECT
SYSTEM_USER, --kasutaja
GETDATE(),  --aeg
'on tehtud UPDATE käsk',  --toiming
CONCAT('VANAD: linn: ', deleted.linnanimi, ' rahvaarv: ', deleted.rahvaarv, 
' ||| UUED: linn: ', inserted.linnanimi, ' rahvaarv: ', inserted.rahvaarv)  --andmed
FROM deleted INNER JOIN inserted
ON deleted.linnID=inserted.linnID;

-- kontrollimiseks tuleb uuendada tabeli linn
UPDATE linnad SET linnanimi='pärnu-väike', rahvaarv=50 WHERE linnID=2;

select * from linnad;
select * from logi;
```
<img width="671" height="417" alt="{9019CAFD-CAE0-440F-9FCE-71D28FC65E0B}" src="https://github.com/user-attachments/assets/078d6c17-0c2b-4564-a787-0b6ec363b9ee" />
