první sekce od nultého byte začíná znaky 93 FF 89 44 (prefix) informace o turnaji\
pevná velikost 0x68 (104) bytes\
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
| **7**      | ???             |            |                  |      |      |      |      |      |      |
| **8**      | ???             |            |                  |      |      |      |      |      |      |
| **9**      | ???             |            |                  |      |      |      |      |      |      |
| **10**     | ???             |            |                  |      |      |      |      |      |      |
| **11**     | ???             |            |                  |      |      |      |      |      |      |
| **12**     | ???             |            | FileName         | jméno souboru    |      |      |      |      |      |
| **13**     | ???             |            |                  |      |      |      |      |      |      |
| **14**     | věková skupina  |            |                  | Categories     |      |      |      |      |      |
| **15**     | časová kontrola |            | Tempo            |      |      |      |      |      |      |
| **16**     | ???             |            |                  |      |      |      |      |      |      |
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

**Sekce 2** - začíná prefixem 95 FF 89 44\
velkost asi pevná 16FB (5 883 DEC)\
obsahuje data o turnaji,

**Sekce 3** - začíná prefixem A3 FF 89 44\
udaje o terminech\
první 2byte velikost field - čas např. 04 00 39 00 3A 00 35 00 -> 9:15\
další fields asi pevné umístění velikost 1A4B - 1AB5 6A (106 DEC)\
počáteční byte = 0\
byte 1E 1F 20 (30, 31, 32 DEC) datum termínu, kola např. 15.12.2024 3F DB 34, 15.12.2024 3E DB 34, 17.12.2024 40 DB 34\

