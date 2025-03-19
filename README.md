## 1. Praktilise töö sooritamise käik

**Eesmärk:** 
Koodis tuleb rakendada kokkupõrke tuvastamist Pygame'i abil, kus mängija objekt liigub ekraanil ja puutub kokku vaenlastega. Kokkupõrke korral eemaldatakse vaenlane ning punktisumma suureneb.

**Lühikirjeldus:** 
Rakendus loob ekraanile mängija objekti ja juhuslikult genereeritud vaenlased. Mängija liigub etteantud suunas ja peegeldub ekraani äärest tagasi. Kui mängija puudutab vaenlast, eemaldatakse see nimekirjast ning lisatakse punkt.


**Töötasin:** 
Töötasin üksi.

**Kas oled abi saanud kaasõppijalt või abi andnud kaasõppijale?** 
Hetkel pole abi vajanud ega andnud.

## 2. Esinenud probleemid ja nende lahenduskäik

**Probleem 1: Pygame ei leidnud pilte (`FileNotFoundError`)
- **Lahendus:** Kontrollisin, kas `img/knight.png` ja `img/enemy.png` on õiges kataloogis.
- **Kasutasin prompti:** "Pygame image load FileNotFoundError solution"

**Probleem 2: Kokkupõrke tuvastamise probleemid**
- **Lahendus:** Algne kood kirjutas mängija objekti üle igal kaadril uue `pygame.Rect` objektiga, mistõttu kokkupõrke tuvastamine ei töötanud. Lahendus oli kasutada `player.topleft = (posX, posY)`.
- **Kasutasin prompti:** "pygame colliderect not working fix"

**Probleem 3: Ekraanile tekkis artefakte**
- **Lahendus:** Kood joonistas mängija enne ekraani puhastamist, mistõttu eemaldatud vaenlaste kujutised jäid ekraanile. Lahendasin selle, muutes `screen.fill(lBlue)` enne uute objektide joonistamist.

## 3. Testimine

**Testimismeetod:**
- Testisin manuaalselt, jälgides mängija liikumist ja kokkupõrkeid vaenlastega.
- Kontrollisin, kas vaenlased kaovad kokkupõrkel ja kas punktisumma suureneb.
- Testisin, kas mäng lõppeb 20 punkti saavutamisel.

**Tulemus:**
- Kood töötab ootuspäraselt.
- Vaenlased eemaldatakse korralikult.
- Mängija liikumine on sujuv.
- Kokkupõrke tuvastamine toimib.

## 4. Eneseanalüüs

### 4.1. Kuidas sul läks?
Töö käigus tekkisid väikesed vead (failiteede probleem ja kokkupõrke tuvastamise loogika), kuid need õnnestus lahendada. 

### 4.2. Kas avastasid uusi Python'i tehnikaid või lähenemisi?
- Sain parema arusaama Pygame'i `colliderect()` kasutamisest.
- Mõistsin, et Pygame'is on oluline objekti atribuutide ajakohastamine selle asemel, et luua uus objekt igal kaadril.

### 4.3. Enesehinnang
Hindan oma tööd **4**
- Ülesanne on korrektselt täidetud.
- Esines väikeseid vigu, kuid need suudeti lahendada.
- Parandada võiks veel optimeerimist (nt vaenlaste eemaldamise loogikat).

### 4.4. Mida teeksid järgmisel korral teisiti?
- Kasutaksin `pygame.sprite.Group()` vaenlaste haldamiseks, mis teeks eemaldamise efektiivsemaks.
- Lisaksin vaenlaste liikumise, et muuta mäng dünaamilisemaks.
- Loeksin rohkem Pygame'i dokumentatsiooni, et vältida tüüpilisi vigu.

---
