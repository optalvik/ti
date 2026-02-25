---
tags:
  - Praktikum
---

# Praktikum 2: Prompt engineering praktikas

Selles praktikumis õpid, kuidas küsimuse sõnastus mõjutab AI vastuse kvaliteeti. Sa proovid erinevaid tehnikaid ja näed ise, milline vahe on halval ja heal promptil.

!!! abstract "Eesmärgid"
    Selle praktikumi läbimise järel:

    - Oskad eristada head prompti halvast
    - Oskad kasutada zero-shot, few-shot ja chain-of-thought tehnikaid
    - Tead, kuidas roll ja kontekst mõjutavad vastust
    - Oskad koostada struktureeritud prompte

---

## Osa 1: Halb prompt vs hea prompt

### Ülesanne 1: Võrdle tulemusi

Esita ChatGPT-le kõigepealt halb prompt:

```text
Räägi mulle võrkudest.
```

Seejärel esita hea prompt:

```text
Selgita lihtsalt ja konkreetselt, mis vahe on LAN-il ja WAN-il. 
Too mõlemale üks igapäevaelu näide. Vasta eesti keeles, 
maksimaalselt 150 sõna.
```

Võrdle vastuseid:

| Aspekt | Halb prompt | Hea prompt |
|---|---|---|
| Kas vastus on fookuses? | | |
| Kas pikkus on sobiv? | | |
| Kas sain, mida tahtsin? | | |

!!! tip "Reegel"
    Mida täpsem küsimus, seda parem vastus. AI ei oska mõtteid lugeda — sa pead ütlema, mida tahad.

### Ülesanne 2: Ise parandamine

Siin on kolm halba prompti. Kirjuta igaühe kõrvale parem versioon ja testi mõlemat:

| Halb prompt | Sinu parem versioon |
|---|---|
| "Mis on DNS?" | |
| "Kirjuta kood." | |
| "Aita mind." | |

---

## Osa 2: Zero-shot vs few-shot

### Ülesanne 3: Zero-shot

Anna AI-le ülesanne ilma näideteta:

```text
Klassifitseeri järgmised IT-probleemid kategooriatesse 
(riistvara / tarkvara / võrk):

1. Printer ei prindi
2. Excel jookseb kokku
3. WiFi ei ühenda
4. Ekraan on must
5. VPN ei tööta
```

### Ülesanne 4: Few-shot

Nüüd anna sama ülesanne **näidetega**:

```text
Klassifitseeri IT-probleemid kategooriatesse. Siin on näited:

- "Hiir ei tööta" → Riistvara
- "Windows ei käivitu" → Tarkvara  
- "E-post ei saabu" → Võrk

Nüüd klassifitseeri:
1. Printer ei prindi
2. Excel jookseb kokku
3. WiFi ei ühenda
4. Ekraan on must
5. VPN ei tööta
```

Võrdle: kas few-shot andis täpsemaid tulemusi? Kas formaat oli ühtlasem?

---

## Osa 3: Chain-of-thought

### Ülesanne 5: Samm-sammuline mõtlemine

Esita kõigepealt tavaline küsimus:

```text
Meil on kontoris 50 arvutit. Iga arvuti vajab IP-aadressi. 
Millist alamvõrgumaski peaksime kasutama?
```

Seejärel sama küsimus chain-of-thought tehnikaga:

```text
Meil on kontoris 50 arvutit. Iga arvuti vajab IP-aadressi. 
Millist alamvõrgumaski peaksime kasutama?

Mõtle samm-sammult:
1. Mitu IP-aadressi on vaja?
2. Milline on väikseim alamvõrk, kuhu see arv mahub?
3. Milline mask sellele vastab?
```

Võrdle: kas samm-sammuline versioon andis põhjalikuma vastuse?

!!! info "Millal kasutada chain-of-thought"
    See tehnika on kasulik, kui ülesanne nõuab **loogikat või arvutamist**. Lihtsa faktilise küsimuse puhul ("Mis on DNS?") pole sellest kasu.

---

## Osa 4: Rolli andmine

### Ülesanne 6: Rolliprompt

Proovi sama küsimust erinevate rollidega:

**Ilma rollita:**

```text
Selgita, mis on tulemüür.
```

**IT-õpetaja roll:**

```text
Sa oled kogenud IT-õpetaja, kes selgitab asju lihtsalt 
ja kasutab igapäevaelu analoogiaid. 

Selgita 17-aastasele õpilasele, mis on tulemüür.
```

**Süsteemiadministraatori roll:**

```text
Sa oled kogenud süsteemiadministraator, kes annab 
konkreetseid tehnilisi juhiseid.

Selgita, mis on tulemüür ja kuidas seda Linuxis 
iptables'iga seadistada.
```

Pane tähele, kuidas roll muudab vastuse stiili, detailsust ja keerukust.

---

## Osa 5: Struktureeritud prompt

### Ülesanne 7: Ehita prompt üles

Koosta prompt neljast osast:

```text
ROLL: Sa oled IT-tugitiimi spetsialist.

KONTEKST: Meie ettevõttes on 30 töötajat. Igal hommikul 
kurdavad mõned, et internet on aeglane. Probleem kaob 
lõunaks.

ÜLESANNE: Koosta veaotsingu plaan — millised sammud peaksin 
läbi tegema, et probleemi põhjus leida?

FORMAAT: Nummerdatud sammud, iga samm max 2 lauset. 
Maksimaalselt 10 sammu.
```

Hinda tulemust:

| Kriteerium | Hinnang (1–5) |
|---|---|
| Kas sammud on loogilises järjekorras? | |
| Kas juhised on konkreetsed? | |
| Kas formaat vastab nõudele? | |
| Kas sa saaksid neid päriselt järgida? | |

---

## Osa 6: Loo oma prompt

### Ülesanne 8: Vaba katsetamine

Vali üks IT-teema, mis sind huvitab, ja koosta struktureeritud prompt, mis sisaldab rolli, konteksti, ülesannet ja formaati.

Testi oma prompti. Kui tulemus pole rahuldav, muuda üht elementi korraga ja testi uuesti. Kirjuta üles, milline muudatus andis parima tulemuse.

!!! warning "Oluline õppetund"
    Prompt engineering on **iteratiivne** protsess. Harva saab esimene prompt täiuslikku vastust. Sa pead katsetama, kohandama ja uuesti proovima — täpselt nagu koodi debuggimine.

---

## Kokkuvõte

Selles praktikumis sa:

- Kogesid vahet halva ja hea prompti vahel
- Kasutasid zero-shot ja few-shot tehnikat ning nägid erinevust
- Proovisid chain-of-thought tehnikat arvutusülesandel
- Nägid, kuidas rolli andmine muudab vastuse stiili ja sügavust
- Ehitasid üles struktureeritud prompti neljast osast
- Kogesid, et prompting on iteratiivne protsess
