**Sekce 1** vždy od nultého byte začíná znaky 93 FF 89 44 (prefix) informace o turnaji\
pevná velikost 0x68 (104) bytes\
| **Pořadí** | **Jméno (GUI)** | **adresa** | **Jméno (json)** | **decr** | **** | **** | **** | **** | **** |
|------------|-----------------|------------|------------------|------|------|------|------|------|------|
|            | databázový klíč | 29 - 32    |   |      |      |      |      |      |      |
|            |            |     |   |      |      |      |      |      |      |
|            |            |     |   |      |      |      |      |      |      |

následují string variabilné dékou jednotlivý fields vžda první 2 bytes určují velikost field, následuje honodat field\
adresa 0x006C 

| **Pořadí** | **Jméno (GUI)** | **adresa** | **Jméno (json)** | **decr** | **** | **** | **** | **** | **** |
|------------|-----------------|------------|------------------|------|------|------|------|------|------|
| **1**      | Název           |            |                  |      |      |      |      |      |      |
| **2**      | Název2          |            |                  |      |      |      |      |      |      |
| **3**      | ???             |            |                  |      |      |      |      |      |      |
| **4**      | Ředitel turnaje |            |                  |      |      |      |      |      |      |
| **5**      | Organizátor     |            |                  |      |      |      |      |      |      |
| **6**      | Místo konání    |            |                  |      |      |      |      |      |      |
| **7**      | Rozhodčí        |            |                  |      |      |      |      |      |      |
| **8**      | ???             |            |                  |      |      |      |      |      |      |
| **9**      | ???             |            |                  |      |      |      |      |      |      |
| **10**     | ???             |            |                  |      |      |      |      |      |      |
| **11**     | ???             |            |                  |      |      |      |      |      |      |
| **12**     | ???             |            | FileName         | jméno souboru    |      |      |      |      |      |
| **13**     | ???             |            |                  |      |      |      |      |      |      |
| **14**     | věková skupina  |            |                  | Categories     |      |      |      |      |      |
| **15**     | časová kontrola |            | Tempo            |      |      |      |      |      |      |
| **16**     | Turnaj/Ostatní/HTML-název souboru |            |                  |      |      |      |      |      |      |
| **17**     | ???             |            |                  |      |      |      |      |      |      |
| **18**     | ???             |            |                  |      |      |      |      |      |      |
| **19**     | ???             |            |                  |      |      |      |      |      |      |
| **20**     | ???             |            |                  |      |      |      |      |      |      |
| **21**     | Federace        |            | Federation       |      |      |      |      |      |      |
| **22**     | HLavní rozhodčí |            | ChiefReferee     |      |      |      |      |      |      |
| **23**     | ???             |            |                  |      |      |      |      |      |      |
| **24**     | ???             |            |                  |      |      |      |      |      |      |
| **25**     | ???             |            |                  |      |      |      |      |      |      |
| **26**     | ???             |            | Federation2__    |      |      |      |      |      |      |
| **28**     | Zástupce hlavního rozhodčího |            | |      |      |      |      |      |      |

**Sekce 2** - začíná prefixem 95 FF 89 44\
velkost asi pevná 16FB (5 883 DEC)\
obsahuje data o turnaji,
| **Pořadí** | **Jméno (GUI)** | **adresa** | **Jméno (json)** | **decr** | **** | **** | **** | **** | **** |
|------------|-----------------|------------|------------------|------|------|------|------|------|------|
|            |  |     |   |      |      |      |      |      |      |
|            | Klasifikace podle ratingu FIDE | 22 |  |  | bit 1 1 - ANO, 0 - NE | pokud ANO je přítupné pole FIDE Event-ID |      |      |      |
|            | Klasifikace podle ratingu national | 22 |  |  | bit 0 1 - ANO, 0 - NE |  |      |      |      |
|            |  |     |   |      |      |      |      |      |      |
|            | Třídění seznamu nasazení | 107 |  | 0 - automaticky, 1 bez automatického třídění |      |      |      |      |      |
|            |  |     |   |      |      |      |      |      |      |
|            | Povolit zadáni specielních výsledků (0:0, ½:0.... | 831 bit    |   |      |      |      |      |      |      |
|            | Zadání výsledků vyloučených hráčů/družstev (implicitně 0) | 832 bit    |   |      |      |      |      |      |      |
|            |  |     |   |      |      |      |      |      |      |
|            | Hráči mohou být vždy nasazeny ručně | 837 bit |   |      |      |      |      |      |      |
|            |  |     |   |      |      |      |      |      |      |
|            | S pomocným hodnocením družstev | 840 bit    |   |      |      |      |      |      |      |
|            |  |     |   |      |      |      |      |      |      |
|            | Sečti body v poli PtsAdd v dialogu hráče pro potřeby losování a pořadí (disabled when JaVaFo engine is used))| 864 bit    |   |      |      |      |      |      |      |
|            |  |     |   |      |      |      |      |      |      |
|            | | 878 bit |   | zvyšuje se při každém uložení (2 nebo 4 bytes)|      |      |      |      |      |
|            |  |     |   |      |      |      |      |      |      |
|            | Time Control | 1264 |   | 1 - Standard, 2 - Rapid, 3 - Blitz |      |      |      |      |      |
|            |  |     |   |      |      |      |      |      |      |
|            | FIDE Event-ID | 1272-75 |   | přistupné pouze pokud klasifikace podle FIDE |      |      |      |      |      |

**Sekce 3** - začíná prefixem A3 FF 89 44\
udaje o terminech\
první 2byte velikost field - čas např. 04 00 39 00 3A 00 35 00 -> 9:15\
další fields asi pevné umístění velikost 1A4B - 1AB5 6A (106 DEC)\
počáteční byte = 0\
byte 1E 1F 20 (30, 31, 32 DEC) datum termínu, kola např. 15.12.2024 3F DB 34, 15.12.2024 3E DB 34, 17.12.2024 40 DB 34\

**Sekce 4** - začíná prefixem A5 FF 89 44\
jednotlivý hráči, jednotlivé záznamy hráčů (v pořadí jak byly zadány, asi...), nejprvé proměnlivé proměnné (strings), následuje pevná část

| **Pořadí** | **Jméno (GUI)** | **adresa** | **Jméno (json)** | **decr** | **** | **** | **** | **** | **** |
|------------|-----------------|------------|------------------|------|------|------|------|------|------|
| **1**      | Příjmení        |            | LastName         |      |      |      |      |      |      |
| **2**      | Jméno           |            | FirstName        |      |      |      |      |      |      |
| **3**      | Student         |            | AcdemicTitle     |      |      |      |      |      |      |
| **4**      | Zkr.jméno       |            | Abbr             |      |      |      |      |      |      |
| **5**      | Titul           |            | Title            |      |      |      |      |      |      |
| **6**      | ID č.           |            | NatId            |      |      |      |      |      |      |
| **7**      | ???             |            |                  |      |      |      |      |      |
| **8**      | ???             |            |                  |      |      |      |      |      |      |
| **9**      | ???             |            |                  |      |      |      |      |      |      |
| **10**     | Klub            |            | ClubName         |      |      |      |      |      |      |
| **11**     | Fed             |            | Federation       |      |      |      |      |      |      |
| **12**     | Typ             |            | Type             |      |      |      |      |      |      |
| **13**     | Skup            |            | Group            |      |      |      |      |      |      |
| **14**     | ???             |            |                  |      |      |      |      |      |      |
| **15**     | Email           |            | Email            |      |      |      |      |      |      |
| **16**     | OnlineUser      |            | OnlineUser       |      |      |      |      |      |      |
| **17**     | ???             |            |                  |      |      |      |      |      |      |
| **18**     | Zdroj           |            | Source           |      |      |      |      |      |      | 
**následuje pevný počet byte 134 bytes**
|            |                 | 1-30       |                  |      |      |      |      |      |      |
|            | Poh             | 31         | Sex              | sex 0-male, 1-female, 2 computer, v exportu hráčů pokud je zadáno C je stejně m |      |      |      |      |      |
|            |                 | 32         |                  |      |      |      |      |      |      |
|            | Rtg.FIDE        | 33 34      | Rating           | FIDE rating |      |      |      |      |      |
|            | Rtg.nár         | 35 36      | NatRating        | národní rating |      |      |      |      |      |
|            |                 | 37 38      |                  |      |      |      |      |      |      |
|            | Nar.            | 39 40 41   | BirthDate/BirthYear | datum narození, většinou jen rok     |      |      |      |      |      |
|            |                 | 42         |                  |      |      |      |      |      |      |
|            | Č.kl.           | 43 44      | ClubNo           | číslo oddílu |      |      |      |      |      |
|            |                 | 45 - 48    |                  |      |      |      |      |      |      |
|            | rankcorr        | 57 58      | RankCorr         | to nevím co znamená, asi max 1000 |      |      |      |      |      |
|            | Stav            | 74 75      | ???              | to nevím co znamená, obsahuje hodnotu 2x co je v GUI |      |      |      |      |      |
|            | FIDE ID         | 49 50 51 52 | FIDEId        | FIDE Id |      |      |      |      |    
|            |                 | 53- 134 |                  |      |      |      |      |      |      |

**Sekce 5** - začíná prefixem B3 FF 89 44\
nevím co znamená, převážně byte 0

**Sekce 6** - začíná prefixem B5 FF 89 44\
pouze pro DB družstev - záznamy družstev

soubor končí bytes E3 FF 89 44\


