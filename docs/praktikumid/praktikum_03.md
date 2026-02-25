---
tags:
  - Praktikum
---

# Praktikum 3: AI-põhine infootsing Perplexity abil

Selles praktikumis õpid kasutama AI-otsingumootorit, mis erineb tavalistest vestlusrobotitest ühe olulise asja poolest — Perplexity näitab alati allikaid. Sa võrdled AI-otsingut tavalise Google'i otsinguga ja õpid hindama, millal kumbagi kasutada.

!!! info "Vajalik konto"
    - **Perplexity:** tasuta konto aadressil [perplexity.ai](https://www.perplexity.ai)

---

## Osa 1: Esimene AI-otsing

### Samm 1: Logi sisse

Ava brauser ja mine aadressile [perplexity.ai](https://www.perplexity.ai). Loo tasuta konto (saad kasutada Google'i kontot).

### Samm 2: Esimene päring

Kirjuta otsinguväljale:

```text
Mis on pilveteenus ja mille poolest erinevad IaaS, PaaS ja SaaS? Selgita eesti keeles lihtsate näidetega.
```

Loe vastust ja pane tähele:

- Vastuse all on **allikate loetelu** — numbrid tekstis viitavad konkreetsetele veebilehtedele
- Sa saad igale allikale klikkida ja kontrollida, kas AI tõlgendas seda õigesti
- Vastus on koondatud mitmest allikast, mitte üks pikk arvamus

### Samm 3: Võrdle Google'iga

Ava uus tab ja otsi Google'ist täpselt sama:

```text
Mis on pilveteenus ja mille poolest erinevad IaaS PaaS SaaS
```

Täida tabel:

| Aspekt | Google | Perplexity |
|---|---|---|
| Mitu tulemust pidid avama? | | |
| Kui kiiresti said vastuse? | | |
| Kas allikad on nähtavad? | | |
| Kas vastus on kokkuvõtlik? | | |

---

## Osa 2: Tehniline infootsing

### Ülesanne 1: Konkreetne tehniline küsimus

Esita Perplexity-le:

```text
Kuidas seadistada Windows arvutis automaatsed varundused 
välisele kõvakettale? Anna samm-sammult juhised.
```

Kontrolli tulemust:

- Kas juhised vastavad praegusele Windows versioonile?
- Kas allikad viitavad ametlikele lehtedele?
- Kas midagi on aegunud või vale?

### Ülesanne 2: Tõrkeotsing

```text
Tööarvuti on viimasel ajal väga aeglane. Millised on 
samm-sammult diagnoosimise võtted ja levinumad põhjused?
```

Hinda: kas Perplexity pakub struktureeritud veaotsingu plaani? Kas allikad on usaldusväärsed (ametlik dokumentatsioon, tehnikafoorumid)?

---

## Osa 3: Allikate hindamine

### Ülesanne 3: Usaldusväärsusskoor

Esita Perplexity-le mõni teema, kus info võib olla vastuoluline:

```text
Kas avalik WiFi on ohtlik? Millised on reaalsed ründeviisid ja kuidas end kaitsta?
```

Vaata vastust ja hinda iga allikat:

| Allikas | Tüüp | Usaldusväärsus (1-5) | Miks? |
|---|---|---|---|
| | Akadeemiline / uudis / foorum / blogi | | |
| | | | |
| | | | |

!!! warning "Allikate hierarhia"
    Kõik allikad pole võrdsed. Usaldusväärsuse järjekord:

    1. Ametlik dokumentatsioon (Cisco, Microsoft, RFC)
    2. Akadeemilised artiklid ja raamatud
    3. Tuntud tehnikaväljaanded (Ars Technica, The Register)
    4. Tehnikafoorumid (Stack Overflow, ServerFault)
    5. Isiklikud blogid ja YouTube

### Ülesanne 4: Faktikontroll

Vali Perplexity vastusest **kolm konkreetset fakti** ja kontrolli neid otse allikast. Kirjuta üles:

| Fakt | Allikas | Kas kattub? | Märkused |
|---|---|---|---|
| | | Jah / Ei / Osaliselt | |
| | | | |
| | | | |

---

## Osa 4: Fookuse häälestamine

### Ülesanne 5: Focus režiimid

Perplexity-l on erinevad fookusrežiimid (All, Academic, Writing, Math jne). Proovi sama küsimust eri režiimides:

Küsimus:

```text
Mis on kaheastmeline autentimine (2FA) ja kuidas see töötab?
```

Proovi režiimides **All** ja **Academic**. Võrdle:

| Aspekt | All | Academic |
|---|---|---|
| Allikate tüüp | | |
| Vastuse detailsus | | |
| Kumb sobib paremini IT-tööks? | | |

### Ülesanne 6: Jätku-küsimused

Perplexity pakub vastuse all seotud küsimusi. Vali üks ja kliki sellel. Pane tähele, kuidas AI ehitab eelmisele vastusele peale — täpselt nagu vestlus, aga allikatega.

---

## Osa 5: Praktiline ülesanne

### Ülesanne 7: IT-probleem algusest lõpuni

Kujuta ette: kolleeg helistab ja ütleb, et ta sai kahtlase e-kirja, mis palub parooli uuendada. Ta ei ole kindel, kas see on õige või petuskeem. Kasuta Perplexityt olukorra analüüsimiseks.

1. Sõnasta probleem ja esita Perplexity-le
2. Loe vastust ja kontrolli allikaid
3. Sõnasta täpsustavad küsimused (nt "kuidas tuvastada phishing e-kirja?")
4. Koosta oma dokumendifaili **veaotsingu plaan** koos allikatega

!!! tip "Hea tava"
    IT-spetsialist ei ütle kliendile "AI ütles nii". Sa kasutad AI-d info leidmiseks, aga **kontrollid** enne, kui tegutsed. Perplexity allikad teevad selle lihtsamaks kui tavaline vestlusrobot.

---

## Kokkuvõte

Selles praktikumis sa:

- Tegid esimesed päringud Perplexity AI-otsingumootoris
- Võrdlesid AI-otsingut tavalise Google'i otsinguga
- Hindasid allikate usaldusväärsust ja tüüpe
- Tegid faktikontrolli — kontrollisid, kas AI väited kattuvad allikatega
- Kasutasid eri fookusrežiime tehnilise info otsimiseks
- Lahendasid IT-tõrkeotsingu ülesande AI abil
