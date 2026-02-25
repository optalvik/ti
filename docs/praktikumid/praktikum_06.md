---
tags:
  - Praktikum
---

# Praktikum 6: Koodi genereerimine ChatGPT abil

Selles praktikumis kasutad ChatGPT-d koodi genereerimiseks, analüüsimiseks ja vigade parandamiseks. Sa ei pea olema programmeerija — eesmärk on mõista, kuidas AI aitab IT-spetsialistil skripte luua ja hallata.

!!! info "Vajalik konto"
    - **ChatGPT:** kooli konto (OpenAI Edu litsents) või tasuta konto aadressil [chat.openai.com](https://chat.openai.com)

---

## Osa 1: Esimene skript

### Samm 1: Lihtne Bashi skript

Esita ChatGPT-le:

```text
Kirjuta Bashi skript, mis kontrollib, kas veebileht on kättesaadav. 
Skript võtab argumendina URL-i, teeb curl päringu ja 
ütleb kas sait vastab (HTTP 200) või mitte.
Kommenteeri iga rida eesti keeles.
```

### Samm 2: Analüüsi vastust

Enne koodi käivitamist loe see läbi ja vasta:

| Küsimus | Sinu vastus |
|---|---|
| Kas saad igast reast aru? | |
| Kas kommentaarid on arusaadavad? | |
| Kas skript käsitleb vigu (nt kui URL puudub)? | |
| Kas sa julged seda käivitada? | |

### Samm 3: Testi skripti

Kopeeri skript tekstifaili, salvesta nimega `check_site.sh` ja käivita:

```bash
chmod +x check_site.sh
./check_site.sh https://www.google.com
./check_site.sh https://seda-saiti-pole-olemas.ee
```

!!! warning "Turvarisk"
    **Ära kunagi käivita koodi, millest sa aru ei saa.** Kui AI genereerib midagi, mida sa ei mõista, küsi AI-lt: "Selgita, mida see rida teeb" — või küsi õpetajalt.

---

## Osa 2: Koodi analüüs ja parandamine

### Ülesanne 1: Vigane kood

Kopeeri see vigane Python skript ChatGPT-sse ja palu tal vead leida:

```python
import os

def check_disk_space(path)
    total, used, free = shutil.disk_usage(path
    print(f"Vaba ruum: {free / (1024 * 3)} GB")
    if free < 1000000000
        print("HOIATUS: vähe ruumi!")
    
check_disk_space("/")
```

Esita ChatGPT-le:

```text
Selles Python skriptis on mitu viga. Leia kõik vead, 
selgita igaüht ja anna parandatud versioon.
```

Kontrolli: kas ChatGPT leidis kõik vead? Mitu viga sa ise leidsid?

| Viga | Kas ChatGPT leidis? | Kas sina leidsid? |
|---|---|---|
| | | |
| | | |
| | | |

### Ülesanne 2: Koodi selgitamine

Kopeeri ChatGPT-sse:

```bash
#!/bin/bash
for ip in $(seq 1 254); do
    ping -c 1 -W 1 192.168.1.$ip > /dev/null 2>&1 && echo "192.168.1.$ip on aktiivne"
done
```

Küsi:

```text
Selgita seda skripti rida-realt. 
Mis on selle eesmärk ja kas seda on turvaline käivitada?
```

Hinda vastust: kas selgitus on täpne? Kas turvahinnang on mõistlik?

---

## Osa 3: Automatiseerimisskriptid

### Ülesanne 3: Logide analüüs

```text
Kirjuta Bashi skript, mis loeb /var/log/syslog faili ja 
leiab viimase 24 tunni jooksul kõik read, kus esineb 
sõna "error" või "failed". Sorteeri tulemused ja 
näita mitu korda iga unikaalne veateade esines.
Kommenteeri eesti keeles.
```

Loe genereeritud skripti ja vasta:

- Kas see kasutab õigeid käske (`grep`, `sort`, `uniq`)?
- Kas kuupäevafilter on korrektne?
- Mida peaks muutma, et see töötaks sinu süsteemis?

### Ülesanne 4: Kasutajate haldus

```text
Kirjuta Bashi skript, mis loeb CSV-failist kasutajanimesid 
(üks nimi rea kohta) ja loob iga nime jaoks Linuxi kasutajakonto. 
Lisa turvakontroll: enne loomist kontrolli, kas kasutaja juba eksisteerib.
Kommenteeri iga samm.
```

!!! danger "Ära käivita tootmisserveris!"
    See skript on õppimiseks. Päris kasutajahaldust tee alati vastavalt ettevõtte poliitikale ja **testi enne** testkeskkonnas.

---

## Osa 4: Iteratiivne arendamine

### Ülesanne 5: Skripti täiustamine

Võta Osa 1 veebilehe kontrollimise skript ja täiusta seda samm-sammult:

**Samm 1:** küsi ChatGPT-lt:

```text
Lisa eelmisele skriptile funktsioon, mis kontrollib mitu 
veebilehte korraga (loeb URL-id failist).
```

**Samm 2:**

```text
Lisa nüüd logifaili kirjutamine — iga kontroll salvestatakse 
faili koos kuupäeva ja tulemusega.
```

**Samm 3:**

```text
Lisa e-posti teavitus, kui mõni sait ei vasta.
```

Pane tähele: iga samm ehitab eelmisele peale. See on **iteratiivne arendamine** — sama lähenemine, mida kasutavad päris arendajad.

---

## Osa 5: Piiride testimine

### Ülesanne 6: Kus AI eksib?

Proovi järgmisi päringuid ja hinda, kui hästi ChatGPT hakkama saab:

**Lihtne (peaks töötama):**

```text
Kirjuta Bashi üherealine, mis leiab kõik .log failid, 
mis on suuremad kui 100MB.
```

**Keskmine (võib vajada parandamist):**

```text
Kirjuta PowerShelli skript, mis inventeerib kõik Active Directory 
kasutajad, kelle parool aegub järgmise 7 päeva jooksul.
```

**Keeruline (tõenäoliselt vajab parandamist):**

```text
Kirjuta Ansible playbook, mis seadistab Nginx reverse proxy 
kahe backend serveriga ja Let's Encrypt sertifikaadiga.
```

Täida tabel:

| Päring | Kas kood töötab otse? | Mitu parandust vajab? | Mis tüüpi vead? |
|---|---|---|---|
| Lihtne | | | |
| Keskmine | | | |
| Keeruline | | | |

!!! tip "Reegel"
    Mida keerulisem ülesanne, seda tõenäolisem, et AI-genereeritud kood vajab käsitsi parandamist. Lihtsa skripti puhul töötab sageli otse; keerulise infrastruktuuri puhul on see pigem **alguspunkt**, mitte valmis lahendus.

---

## Osa 6: Dokumenteerimine

### Ülesanne 7: Koodi dokumenteerimine

Võta üks oma varasematest skriptidest (ilma kommentaarideta) ja palu ChatGPT-l dokumenteerida:

```text
Lisa sellele skriptile:
1. Päise kommentaar (autor, kuupäev, eesmärk)
2. Iga funktsiooni kirjeldus
3. README.md fail kasutamisjuhendiga
```

Hinda: kas genereeritud dokumentatsioon on piisav, et keegi teine saaks skripti kasutada?

---

## Kokkuvõte

Selles praktikumis sa:

- Genereerisid AI abil töötava Bashi skripti ja testisid seda
- Lasid AI-l vigast koodi analüüsida ja parandada
- Lõid automatiseerimisskripte IT-halduse jaoks
- Kogesid iteratiivset arendamist — skripti samm-sammulist täiustamist
- Testisid AI piire eri keerukusastmega ülesannetega
- Kasutasid AI-d koodi dokumenteerimiseks
