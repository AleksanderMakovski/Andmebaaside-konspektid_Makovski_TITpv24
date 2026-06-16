## Andmebaasi võtmed (Keys)


## 1. Primary Key

Definitsioon:

PRIMARY KEY piirang identifitseerib iga kirje andmebaasi tabelis unikaalselt.

Milleks kasutatakse?

Kasutatakse iga rea unikaalseks tuvastamiseks.

Erinevus teistest võtmetest:

Ei tohi sisaldada NULL väärtusi ja peab olema unikaalne.

<img width="660" height="112" alt="{9CEC0621-D2AA-42D7-9AF2-A49D96FD66C2}" src="https://github.com/user-attachments/assets/b1be2b7b-4171-4a40-b959-c9a1a5ab706b" />

<img width="404" height="318" alt="{2B4304DF-265E-4AA3-9A9A-96849AA7F07D}" src="https://github.com/user-attachments/assets/6cf4c8f6-3901-4633-affb-6c6793165174" />

## 2. Foreign Key

Definitsioon:

The FOREIGN KEY piirang loob kahe tabeli vahele lingi ja takistab toiminguid, mis nendevahelise lingi hävitavad.

Milleks kasutatakse?

Seoste loomiseks tabelite vahel.

Erinevus teistest võtmetest:

Viitab teise tabeli andmetele.
<img width="822" height="253" alt="{F4FBFF0D-66EB-493E-9272-83A7D869E397}" src="https://github.com/user-attachments/assets/f82e680d-7e39-40fd-bcab-677680dcb626" />

<img width="727" height="214" alt="{18E4877C-7A8C-4687-9621-C0FA3EF96E99}" src="https://github.com/user-attachments/assets/a566367e-aae4-47e9-aa15-4943a115e607" />

## 3. Unique Key

Definitsioon:

UNIQUE piirang tagab, et kõik veeru väärtused on unikaalsed.

Milleks kasutatakse?

Duplikaatide vältimiseks.

Erinevus teistest võtmetest:

Võib sisaldada NULL väärtust.
<img width="794" height="228" alt="{E1E6292E-D2D9-4321-9140-36F82DBB7310}" src="https://github.com/user-attachments/assets/4975c8b5-88f4-46bf-bb28-ed86544f8716" />

<img width="381" height="232" alt="{46CF8620-0B50-430C-8261-9526FE17A4CF}" src="https://github.com/user-attachments/assets/d163117b-517a-4cf2-8df9-91afa6823c55" />

## 4. Simple Key

Definitsioon:

Simple Key koosneb ühest atribuudist.

Milleks kasutatakse?

Kirjete unikaalseks identifitseerimiseks ühe välja abil.

Erinevus teistest võtmetest:

Sisaldab ainult ühte veergu.
<img width="908" height="251" alt="{CB4926BE-4A7F-4667-958B-F96B5F156CF3}" src="https://github.com/user-attachments/assets/d11fd194-b1c0-46d1-935e-df8915bc8be7" />

<img width="359" height="230" alt="{36FF7ADB-8EBF-4A1B-B4D7-BCF782FE5BAC}" src="https://github.com/user-attachments/assets/d3d2d810-0b86-4a5c-abf1-9d25ca1fc211" />

## 5. Composite Key

Definitsioon:

Composite Key on primary key, mis on moodustatud kahest või enamast veerust, mis koos identifitseerivad unikaalselt iga tabeli kirjet.

Milleks kasutatakse?

Kui üks väli üksi ei ole unikaalne.

Erinevus teistest võtmetest:

Koosneb mitmest veerust.
<img width="877" height="293" alt="{8E35BD9E-2C99-4E3E-AA27-BB106FE13116}" src="https://github.com/user-attachments/assets/570c7b56-7d6b-457b-b050-bcd18ffbfefd" />

<img width="342" height="260" alt="{5CC7D449-647C-4A9E-B04F-FABF364DA1BA}" src="https://github.com/user-attachments/assets/5418b10b-c01c-4a50-a66c-acf4538c57b1" />

## 6. Compound Key

Definitsioon:

Compound Key on Composite Key tüüp, mis koosneb mitmest väljast.

Milleks kasutatakse?

Unikaalse identifikaatori loomiseks mitme välja abil.

Erinevus teistest võtmetest:

Koosneb vähemalt kahest väljast.
<img width="918" height="295" alt="{F073B1A2-8763-40E1-AA9A-38FCB32EAEED}" src="https://github.com/user-attachments/assets/c8448134-2c92-4e6b-b530-ff6888f13131" />

<img width="320" height="219" alt="{C749D8E9-19D6-48EA-96E0-F371367D56D2}" src="https://github.com/user-attachments/assets/861b6ca7-740b-46ad-93ca-6c2f09621814" />

## 7. Superkey

Definitsioon:

Superkey on tabelis ühe või mitme atribuudi rühm, mis suudab iga tabeli rida unikaalselt identifitseerida. See tagab, et kahel real ei ole nende atribuutide väärtuste kombinatsiooni.

Milleks kasutatakse?

Kirjete unikaalseks määramiseks.

Erinevus teistest võtmetest:

Võib sisaldada liigseid atribuute.
<img width="879" height="304" alt="{AA2CEFC6-3869-4E21-9F05-12FBEE5CF365}" src="https://github.com/user-attachments/assets/0409c5cc-22ff-46be-802b-2c5c02434041" />

<img width="337" height="244" alt="{B32DBA29-6E9A-4DCE-A82C-6D2DE2DEDFA5}" src="https://github.com/user-attachments/assets/7ed0e6ca-0d30-42ff-a922-fd794a37e0eb" />

## 8. Candidate Key

Definitsioon:

Candidate Key on minimaalne atribuutide kogum, mis identifitseerib unikaalselt iga tabelis olevat tuple'i. Teisisõnu, tabelis ei tohiks olla kahte rida, mille veergudel, mis on kandidaadivõtme osa, võivad olla samad väärtused.

Milleks kasutatakse?

Primary Key valimiseks.

Erinevus teistest võtmetest:

Ei sisalda liigseid atribuute.
<img width="691" height="143" alt="{4C381EA8-4AF0-4725-B0C6-630412E62942}" src="https://github.com/user-attachments/assets/4c6b98ac-1b85-486c-a4fd-5905b697bab7" />

<img width="341" height="244" alt="{1C3B2EE0-29F7-4F2A-BE8F-34915EDFF0A3}" src="https://github.com/user-attachments/assets/26f25a3d-b9ad-42b5-8486-6d482183a001" />

## 9. Alternate Key
Definitsioon

Alternate Key on kandidaatvõti, mida ei valita primaarvõtmeks, kuid mis suudab siiski tabeli kirjet unikaalselt tuvastada.

Milleks kasutatakse

Täiendava unikaalsuse tagamiseks.

Erinevus teistest võtmetest

On kandidaatvõti, kuid mitte Primary Key.
<img width="875" height="298" alt="{C6B93B08-915A-4000-9297-82768417FB04}" src="https://github.com/user-attachments/assets/801a5024-4a6c-4056-8538-42752ffde1f2" />

<img width="358" height="247" alt="{C7399F35-74C7-468D-ACD6-AA53AD6BF861}" src="https://github.com/user-attachments/assets/a298af9a-88dc-4d21-8ce8-518e33445e90" />

#KASUTATUD LINGID

https://www.w3schools.com/sql/sql_primarykey.asp

https://www.w3schools.com/sql/sql_unique.asp#gsc.tab=0&gsc.q=simple%20key

https://www.geeksforgeeks.org/sql/composite-key-in-sql/

https://dba.stackexchange.com/questions/3134/in-sql-is-it-composite-or-compound-keys

https://www.geeksforgeeks.org/dbms/super-key-in-dbms/

https://www.geeksforgeeks.org/dbms/candidate-key-in-dbms/

https://www.geeksforgeeks.org/sql/sql-alternate-key/




