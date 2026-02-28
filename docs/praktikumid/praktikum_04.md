---
tags:
  - Praktikum
---

# Praktikum 4: Loo oma õppematerjal

Selles praktikumis kasutad Google'i NotebookLM-i, et luua **päris õppematerjal**, mida saad ise (ja su klassikaaslased) kasutada. Sa laadid üles allikad, genereerid kokkuvõtteid, lood küsimusi ja teed audiokokkuvõtte.

!!! abstract "Eesmärgid"
    Selle praktikumi lõpuks:

    - Oskad NotebookLM-i kasutada allikapõhiseks tööks
    - Oled loonud kompaktse õppematerjali ühe IT-teema kohta
    - Tead, mille poolest erineb allikapõhine AI tavalisest vestlusrobotist

!!! info "Vajalik konto"
    - **NotebookLM:** Google'i konto aadressil [notebooklm.google.com](https://notebooklm.google.com)

---

## Osa 1: Vali teema ja kogu allikad

### Samm 1: Vali IT-teema

Vali üks teema, mille kohta tahad õppematerjali luua. Hea valik on teema, mida sul on vaja ka päriselt õppida.

Näiteid:

- Võrguprotokollid (TCP/IP, DNS, DHCP)
- Küberturvalisus (tulemüürid, krüpteerimine, autentimine)
- Pilveteenused (IaaS, PaaS, SaaS)
- Operatsioonisüsteemid (Linux vs Windows haldus)
- Virtualiseerimine ja konteinerid

**Minu teema:** _______________

### Samm 2: Kogu allikad

Leia 2-4 allikat oma teema kohta. Kasuta erinevaid tüüpe:

| Allikatüüp | Kust leida | Näide |
|---|---|---|
| Kursuse materjal | Selle kursuse teooriapeatükid | PDF-ina salvestatud peatükk |
| Ametlik dokumentatsioon | Cisco, Microsoft, Linux.org | Ametlik juhend |
| Wikipedia / õpik | Wikipedia, IT-raamatud | Hea üldine ülevaade |
| Tehniline artikkel | Medium, Dev.to, Ars Technica | Praktiline selgitus |

!!! tip "Allikate kvaliteet loeb"
    NotebookLM vastab **ainult** sinu allikate põhjal. Kui laadid üles kehvad allikad, saad kehva tulemuse. Vali sisukaid ja usaldusväärseid allikaid.

### Samm 3: Loo notebook

Mine [notebooklm.google.com](https://notebooklm.google.com) ja loo uus notebook. Laadi üles oma allikad (PDF, veebileht, tekst).

---

## Osa 2: Genereeri õppematerjal

### Ülesanne 1: Teema kokkuvõte

Küsi NotebookLM-ilt:

```text
Koosta selle materjali põhjal kompaktne kokkuvõte, mis katab
kõik põhimõisted. Struktureeri loogiliselt: alusta põhitõdedest
ja liigu detailsemate teemade juurde. Maksimaalselt 1 lehekülg.
```

Kontrolli tulemust:

- Kas kokkuvõte katab olulised teemad?
- Kas kõik väited on allikatega toetatud? (kliki viidetel)
- Kas midagi olulist jäi välja?

**Paranda** kokkuvõtet — küsi täiendavaid küsimusi, kui midagi on puudu.

### Ülesanne 2: Põhimõistete sõnastik

```text
Loo selle materjali põhimõistete sõnastik. Iga mõiste juurde:
- Lühike definitsioon (1-2 lauset)
- Näide või analoogia igapäevaelust
Sorteeri tähestikulises järjekorras.
```

Hinda: kas definitsioonid on arusaadavad ka kellelegi, kes teemat ei tunne?

### Ülesanne 3: Harjutusküsimused

```text
Genereeri selle materjali põhjal 10 küsimust koos õigete vastustega.
Kasuta erinevaid tüüpe:
- 3 valikvastustega küsimust (4 valikut)
- 3 õige/vale väidet
- 2 lühivastusega küsimust
- 2 selgitamist nõudvat küsimust
```

Kontrolli iga küsimust:

| # | Kas põhineb allikal? | Kas vastus on õige? | Raskusaste (1-5) |
|---|---|---|---|
| 1 | | | |
| 2 | | | |
| ... | | | |

Paranda vead ja küsi vajadusel uusi küsimusi.

---

## Osa 3: Audio kokkuvõte

### Ülesanne 4: Kuulatav versioon

NotebookLM oskab genereerida audiokokkuvõtte sinu allikatest. Vajuta **Audio Overview** nuppu.

Kuula genereeritud audiot ja hinda:

| Aspekt | Hinnang (1-5) |
|---|---|
| Kas põhiteemad on kaetud? | |
| Kas selgitused on arusaadavad? | |
| Kas midagi on valesti tõlgendatud? | |
| Kas kuulaksid seda kordamiseks? | |

!!! tip "Praktiline kasutus"
    Audio kokkuvõte on hea viis materjali kordamiseks — kuula bussiga sõites, trennis või enne eksamit. Aga **kontrolli** alati, kas audio vastab allikatele.

---

## Osa 4: Testi klassikaaslase peal

### Ülesanne 5: Vastastikune testimine

Vaheta klassikaaslasega: anna talle oma harjutusküsimused (ilma vastusteta) ja proovi tema omasid.

Pärast testimist hinda:

| Küsimus | Sinu vastus |
|---|---|
| Mitu küsimust klassikaaslane õigesti vastas? | /10 |
| Millised küsimused olid liiga kerged? | |
| Millised olid liiga rasked? | |
| Kas mõni küsimus oli segaselt sõnastatud? | |

Paranda oma küsimusi vastavalt tagasisidele.

!!! info "Miks see oluline on?"
    Küsimuste testimine teiste peal näitab, kas sinu materjal on **tegelikult** arusaadav — mitte ainult sulle, vaid ka kellelegi, kes teemat alles õpib.

---

## Osa 5: Paki kokku

### Ülesanne 6: Lõplik õppepakett

Kogu kõik kokku ühte dokumenti. See on sinu praktikumi **lõpptulemus**:

```text
═══════════════════════════════════════════════════
ÕPPEPAKETT: [sinu teema]
═══════════════════════════════════════════════════

AUTOR: [sinu nimi]
KUUPÄEV: [kuupäev]
ALLIKAD: [loetelu kasutatud allikatest]

───────────────────────────────────────────────────
1. KOKKUVÕTE
[sinu parandatud kokkuvõte siia]

───────────────────────────────────────────────────
2. PÕHIMÕISTED
[sõnastik siia]

───────────────────────────────────────────────────
3. HARJUTUSKÜSIMUSED
[parandatud küsimused siia]
[vastused eraldi lehel / dokumendi lõpus]

───────────────────────────────────────────────────
4. AUDIO KOKKUVÕTE
[link või märge, et audio on genereeritud]

───────────────────────────────────────────────────
ENESEHINNANG:
- Tugevaim osa mu materjalis: [...]
- Mida tahaksin veel parandada: [...]
═══════════════════════════════════════════════════
```

!!! warning "Kvaliteedikontroll"
    Enne esitamist veendu:

    - [ ] Kõik väited põhinevad allikatel
    - [ ] Küsimuste vastused on kontrollitud
    - [ ] Klassikaaslane on küsimusi testinud
    - [ ] Audio kokkuvõte on genereeritud

---

## Kokkuvõte

Selles praktikumis sa:

- Lõid NotebookLM-is oma teema kohta allikapõhise tööruumi
- Genereerisid kokkuvõtte, sõnastiku ja harjutusküsimused
- Lõid audiokokkuvõtte kordamiseks
- Testisid materjali klassikaaslase peal ja parandasid tagasiside põhjal
- Pakid kõik kokku kasutatavaks õppepaketiks
