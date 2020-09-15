# Bevezetés
Jelen dokumentációban az adatkommunikációban előforduló adatok megléte és sikeres betöltésén alapúl. Adatok esetén előfordulhat, hogy nem létezik vagy nem tárolt, így a valós futás közben a válaszban NULL érték jelenik meg. Továbbá hiba esetén pl.: HTTP4xx vagy HTTP5xx válasz hiba kódok esetén az adott kérés NEM e dokumentumban írt válasz „response” adattal tér vissza!

Kommunikáció során a böngésző szabványos JSON formátumban kommunikál. Így ezen okból kifolyólag a leírásban a szabványos megközelítést alkalmazzuk.

## JSON
JSON (JavaScript Object Notation) kis méretű és szöveg alapú szabvány, amit a RFC4627  ír le. A JSON szerkezetére vonatkozóan a szóközök, új sor (enter) vagy tabulátor nincs rá hatással.

### JSON alaptípusai:
A JSON struktúrális szerkezete [itt](https://github.com/Project-echef/provisions/blob/master/img/json.svg) tekinthető meg.

- **null**. Olyan adat (vagy üres érték), ami nem képvisel típust vagy értéket, továbbá minden adattípust helyettesíthet.
- **Szám**. A dokumentációban úgy hivatkozunk rá, mint: <number>
- **Karakterlánc**. A dokumentációban úgy hivatkozunk rá, mint: <string>
- **Logikai**. A logikai érték az igaz (true) vagy hamis (false) értékeket reprezentálja. A dokumentációban úgy hivatkozunk rá, mint: <boolean>
- **Lista/Tömb/Halmaz**. Ez egy „[” jellel kezdődő és egy „]” záródó blokk, aminek tartalma bármely JSON típus lehetséges. Az adatokat vessző választja el. Amennyiben azonos szerkezetű adatok jelennek meg, úgy csak az első előfordulást emeljük ki, majd „…”-al jelezzük, hogy ebből több azonos, más-más adatot tartalmazó elem fordulhat elő.

Logikai 2 elemű tömb:
```
[
      <boolean>,
      ...,
]
```

Két szintű két vegyes típusú lista:
```
[
      [    
           <number>,
           <string>
      ],
      [    
           <boolean>,
           <string>
      ]
]
```
 
- Objektum. Az elejét egy nyitó kapcsos zárójel jelenti, míg a végét egy bezáró kapcsos jel. Egy legalább nulla darab számú kulcs-érték párú objektum „{}”, úgy nevezett üres objektum. Más esetben kulcs-érték párból álló elemek sokaságát képzik. Ennek számosságára nincs korlát. Kulcs érték mindig idézőjelek közötti szöveges név, de az értéke bármely JSON típus lehetséges. Az adatokat vessző választja el. Kulcsok értékei angol betűkből és „camel case” szerűek. Szóközöket a következő szó nagy kezdőbetűje reprezentál és speciális karaktert nem tartalmaz. Példa: „ezEgyKulcs”.
Egy minta adat:
```
{
     „vezeteknev”: <string>,
     „kor”: <number>,
     „telefonszam”: [
           {
                „tipus”: <string>
                „szam”: <string>
           },
           …
     ],
}
```
