---
tags:
  - Praktikum
---

# Praktikum 6: Lõpuprojekt — ehita oma IT-tööriist

Selles praktikumis ehitad AI abiga **päris töötava tööriista**, mida saad IT-töös kasutada. Sa valid projekti, genereerid koodi, testid seda ja dokumenteerid tulemuse. See on kõige praktilisem praktikum — sinu tulemus on töötav skript.

!!! abstract "Eesmärgid"
    Selle praktikumi lõpuks:

    - Oled AI abiga loonud töötava IT-skripti
    - Oskad AI-genereeritud koodi lugeda, testida ja parandada
    - Tead, millal AI-kood töötab otse ja millal vajab käsitsi parandamist
    - Oled dokumenteerinud oma tööriista nii, et teine inimene saaks seda kasutada

!!! info "Vajalik konto"
    - **ChatGPT:** [chat.openai.com](https://chat.openai.com) või **Claude:** [claude.ai](https://claude.ai)

!!! warning "Oluline reegel"
    **Ära kunagi käivita koodi, millest sa aru ei saa.** Kui AI genereerib midagi, mida sa ei mõista, küsi AI-lt: "Selgita, mida see rida teeb." Või küsi õpetajalt.

---

## Osa 1: Vali projekt

Vali üks järgmistest projektidest (või paku ise):

### Valik A: Veebilehe monitor

Skript, mis kontrollib, kas veebileht on kättesaadav, ja logib tulemused faili.

- **Keel:** Bash või Python
- **Väljund:** logifail kuupäeva, URL-i ja staatusega
- **Raskus:** Algaja

### Valik B: Süsteemiinfo koguja

Skript, mis kogub arvuti kohta olulist infot (OS, RAM, ketas, IP) ja koostab raporti.

- **Keel:** Bash või Python
- **Väljund:** loetav raport tekstifailina
- **Raskus:** Algaja

### Valik C: Failikorraldaja

Skript, mis sorteerib allalaadimiste kausta failid kaustadesse tüübi järgi (.pdf → Dokumendid, .jpg → Pildid jne).

- **Keel:** Python
- **Väljund:** sorteeritud kaustastruktuur
- **Raskus:** Keskmine

### Valik D: Logide analüüsija

Skript, mis loeb logifaili ja leiab veateateid, sorteerib need sageduse järgi.

- **Keel:** Bash või Python
- **Väljund:** kokkuvõte levinumatest vigadest
- **Raskus:** Keskmine

### Valik E: Oma idee

Kui sul on oma idee IT-tööriista kohta — paku see õpetajale ja hakka tööle.

**Minu valik:** _______________

---

## Osa 2: Spetsifikatsioon

Enne koodi genereerimist kirjuta üles, **mida** su tööriist peab tegema. See on spetsifikatsioon.

Täida:

| Väli | Sinu vastus |
|---|---|
| Tööriista nimi | |
| Mida see teeb (1-2 lauset) | |
| Sisend (mida kasutaja annab) | |
| Väljund (mida kasutaja saab) | |
| Programmeerimiskeel | |
| Mis OS-is peab töötama | |

!!! tip "Miks spetsifikatsioon enne koodi?"
    Kui tead täpselt, mida tahad, saad AI-le anda parema prompti. Ja hiljem saad kontrollida, kas tulemus vastab sellele, mida soovisid.

---

## Osa 3: Genereeri kood

### Samm 1: Esimene prompt

Koosta AI-le prompt, mis sisaldab sinu spetsifikatsiooni. Näide:

```text
Kirjuta [Bashi/Pythoni] skript, mis [mida skript teeb].

Nõuded:
- [sisend]
- [väljund]
- [OS]
- Kommenteeri iga oluline rida eesti keeles
- Lisa vigade käsitlemine (nt kui fail puudub, kui URL ei vasta)
```

### Samm 2: Loe kood läbi

**Enne käivitamist** loe kogu kood läbi. Iga rea kohta mõtle:

- Kas saan aru, mida see rida teeb?
- Kas see on turvaline? (Kas kustutab midagi? Kas saadab andmeid kuhugi?)
- Kas see teeb seda, mida ma spetsifikatsioonis kirjeldasin?

Kui miski on arusaamatu, küsi AI-lt:

```text
Selgita selle skripti ridu 5-12. Mida iga rida täpselt teeb?
```

### Samm 3: Märgi üles

| Küsimus | Sinu vastus |
|---|---|
| Mitu rida koodi genereeriti? | |
| Kas said igast reast aru? | Jah / Ei (millest mitte?) |
| Kas AI lisas midagi, mida sa ei küsinud? | |
| Kas vigade käsitlemine on olemas? | |

---

## Osa 4: Testi ja paranda

### Samm 1: Esimene käivitamine

Salvesta skript failina ja käivita. Testi erinevate sisenditega:

| Test | Sisend | Oodatud tulemus | Tegelik tulemus | OK? |
|---|---|---|---|---|
| Normaalne | [tavaline sisend] | | | |
| Tühi sisend | [midagi puudub] | Veateade | | |
| Vale sisend | [vigane sisend] | Veateade | | |

### Samm 2: Paranda vead

Kui midagi ei tööta, on kaks võimalust:

**Variant A: Küsi AI-lt**

```text
Mu skript annab selle vea: [kopeeri veateade siia].
Skript on: [kopeeri skript siia].
Mis on valesti ja kuidas parandada?
```

**Variant B: Paranda ise**

Kui saad veast aru, proovi ise parandada. See on parim viis õppida.

### Samm 3: Täiusta

Kui põhifunktsioon töötab, küsi AI-lt ühe täienduse lisamist:

```text
Lisa mu skriptile [uus funktsioon]. Siin on praegune skript:
[kopeeri skript]
```

Näiteid täiendustest:

- Lisa logifaili kirjutamine (iga käivitus salvestatakse)
- Lisa värvid terminalväljundisse
- Lisa ajatempel iga rea ette
- Lisa statistika kokkuvõte lõppu

---

## Osa 5: Dokumenteeri

### Ülesanne: Tööriista dokumentatsioon

Koosta oma tööriistale dokumentatsioon. See on sinu praktikumi **lõpptulemus**.

```text
═══════════════════════════════════════════════════
TÖÖRIISTA DOKUMENTATSIOON
═══════════════════════════════════════════════════

NIMI: [tööriista nimi]
AUTOR: [sinu nimi]
KUUPÄEV: [kuupäev]
KEEL: [Bash / Python]

───────────────────────────────────────────────────
KIRJELDUS:
[Mida tööriist teeb, 2-3 lauset]

───────────────────────────────────────────────────
KASUTAMINE:
[Kuidas käivitada, näide käsurealt]

Näide:
$ [käsk]
[oodatud väljund]

───────────────────────────────────────────────────
NÕUDED:
- OS: [milline operatsioonisüsteem]
- Vajalikud programmid: [nt Python 3, curl, jne]

───────────────────────────────────────────────────
KOOD:
[kopeeri lõplik skript siia]

───────────────────────────────────────────────────
TEADAOLEVAD PIIRANGUD:
- [mida tööriist EI tee]
- [millal võib ebaõnnestuda]

───────────────────────────────────────────────────
ARENDUSPROTSESS:
- Mitu AI prompti läks vaja: [arv]
- Mitu viga tuli parandada: [arv]
- Kas AI kood töötas kohe? [Jah / Ei]
- Mis oli kõige raskem: [...]
═══════════════════════════════════════════════════
```

---

## Osa 6: Analüüs

Vasta lõpetuseks:

1. **Kas AI-genereeritud kood töötas kohe?** Kui ei, siis millised vead esinesid?
2. **Kas sa oleksid selle skripti suutnud ise kirjutada?** Kui ei, siis mis oli uus?
3. **Kas sa usaldaksid seda skripti tootmisserveris?** Miks? Miks mitte?
4. **Millal on AI koodi genereerimine kasulik ja millal ohtlik?**

!!! warning "Oluline õppetund"
    AI on hea **alguspunkt** — ta genereerib kiiresti midagi, mis töötab lihtsal juhul. Aga päris tootmiskõlblik kood vajab alati inimese kontrolli: turvalisus, veakäsitlus, äärjuhud, jõudlus. Mida keerulisem ülesanne, seda rohkem tuleb ise mõelda.

---

## Kokkuvõte

Selles praktikumis sa:

- Valisid ja spetsifitseerisid oma IT-tööriista
- Kasutasid AI-d koodi genereerimiseks ja vigade parandamiseks
- Testisid skripti erinevate sisenditega
- Täiendasid tööriista samm-sammult
- Dokumenteerisid tulemuse nii, et keegi teine saaks seda kasutada
- Analüüsisid AI-koodi genereerimise tugevusi ja nõrkusi
