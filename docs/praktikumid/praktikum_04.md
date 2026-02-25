---
tags:
  - Praktikum
---

# Praktikum 4: NotebookLM — allikate analüüs AI abil

Selles praktikumis kasutad Google'i NotebookLM-i, mis erineb tavalistest AI-dest oluliselt — sa laadid üles oma allikad ja AI vastab ainult nende põhjal. See tähendab vähem hallutsinatsioone ja kontrollitavamaid vastuseid.

!!! info "Vajalik konto"
    - **NotebookLM:** Google'i konto aadressil [notebooklm.google.com](https://notebooklm.google.com)

---

## Osa 1: Esimene notebook

### Samm 1: Loo uus notebook

Mine [notebooklm.google.com](https://notebooklm.google.com) ja logi Google'i kontoga sisse. Vajuta **New Notebook**.

### Samm 2: Lisa allikad

Laadi üles vähemalt 2 allikat. Võid kasutada:

- Mõne teooriapeatüki PDF-i sellelt kursuselt
- Cisco CCNA dokumentatsiooni lehekülgi
- Wikipedia artiklit mõne võrgutehnoloogia kohta

!!! tip "Allikate valik"
    NotebookLM töötab kõige paremini, kui allikad on **sama teema** kohta, aga **eri vaatenurgast**. Näiteks üks akadeemiline ja üks praktiline allikas.

### Samm 3: Esimene küsimus

Kui allikad on üles laetud, kirjuta vestlusaknasse:

```text
Mis on selle materjali põhiteemad? Anna lühikokkuvõte.
```

Pane tähele: vastuse juures on **viited konkreetsetele kohtadele** sinu allikates. Sa saad klikkida ja näha täpselt, kust info pärineb.

---

## Osa 2: Allikatepõhine analüüs

### Ülesanne 1: Võrdlev analüüs

Kui sul on kaks allikat, küsi:

```text
Millised on peamised erinevused nende kahe allika käsitluses? 
Kus nad on nõus ja kus lahknevad?
```

### Ülesanne 2: Mõistete selgitus

```text
Selgita selle materjali põhjal, mis on [vali teema, nt VLAN]. 
Kasuta ainult neid allikaid — ära lisa omalt poolt.
```

Kontrolli: kas NotebookLM jääb tõepoolest allikate raamidesse? Kas ta lisab midagi, mida allikates pole?

### Ülesanne 3: Küsimuste genereerimine

```text
Genereeri selle materjali põhjal 5 eksamiküsimust koos 
õigete vastustega.
```

Hinda genereeritud küsimusi:

| Küsimus | Kas põhineb allikal? | Kas vastus on korrektne? | Raskusaste (1-5) |
|---|---|---|---|
| | Jah / Ei | Jah / Ei | |
| | | | |

---

## Osa 3: Audio kokkuvõte

### Ülesanne 4: Podcast-stiilis kokkuvõte

NotebookLM oskab genereerida audio kokkuvõtte sinu allikatest. Vajuta **Audio Overview** nuppu.

Kuula genereeritud audiot ja vasta:

- Kas kokkuvõte on täpne?
- Kas midagi jäi välja, mis oleks pidanud sees olema?
- Kas midagi on valesti tõlgendatud?

!!! info "Miks see kasulik on?"
    Audio kokkuvõte on hea viis materjali kordamiseks — saad kuulata bussiga sõites või trennis. Aga **alati kontrolli** sisu täpsust, sest AI võib nüansse kaotada.

---

## Osa 4: Praktiline projekt

### Ülesanne 5: Oma õppematerjal

Loo uus notebook ja laadi üles 3-5 allikat ühe IT-teema kohta, mis sind huvitab (näiteks tulemüürid, DNS, konteinerid, pilveteenused).

Koosta NotebookLM abil:

1. **Teema kokkuvõte** — 1 lehekülg, mis katab põhimõisted
2. **5 kordamisküsimust** koos vastustega
3. **Mõistekaart** — palu NotebookLM-il loetleda peamised mõisted ja nende seosed

### Ülesanne 6: Kvaliteedi kontroll

Vaata oma loodud materjali kriitilise pilguga:

| Kriteerium | Hinnang (1-5) | Märkused |
|---|---|---|
| Kas info on faktiliselt õige? | | |
| Kas kõik väited on allikatega toetatud? | | |
| Kas küsimused on asjakohased? | | |
| Kas materjal oleks kasulik teisele õppijale? | | |

---

## Osa 5: Võrdlus ChatGPT-ga

### Ülesanne 7: Sama küsimus, erinev lähenemine

Esita sama küsimus NotebookLM-ile (oma allikate põhjal) ja ChatGPT-le (ilma allikateta):

```text
Selgita, kuidas [sinu valitud teema] töötab ja millised 
on peamised turvariskid.
```

Võrdle:

| Aspekt | NotebookLM | ChatGPT |
|---|---|---|
| Kas allikad on nähtavad? | | |
| Kas vastus on kontrollitav? | | |
| Kas esineb hallutsinatsioone? | | |
| Kumb on põhjalikum? | | |

!!! warning "Oluline erinevus"
    NotebookLM vastab **ainult** sinu allikate põhjal — kui allikates pole infot, ütleb ta seda. ChatGPT vastab alati, isegi kui ta tegelikult ei tea. See erinevus on kriitiline, kui töötad tundlike andmetega.

---

## Kokkuvõte

Selles praktikumis sa:

- Lõid oma NotebookLM notebook'i ja laadisid üles allikaid
- Kogesid, kuidas allikatepõhine AI erineb tavalisest vestlusrobotist
- Genereerisid küsimusi ja audio kokkuvõtteid oma materjalidest
- Kontrollisid AI väidete vastavust algallikatega
- Võrdlesid allikatepõhist ja vabavormilist AI-d
