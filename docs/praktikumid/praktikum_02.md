---
tags:
  - Praktikum
---

# Praktikum 2: IT Helpdesk simulaator

Selles praktikumis lahendad kolm reaalset IT-tugiprobleemi AI abiga. Sa ei õpi promptimist teooria kaudu — sa õpid seda **tehes**, sest iga juhtum nõuab paremat küsimist, et saada parem vastus.

!!! abstract "Eesmärgid"
    Selle praktikumi lõpuks:

    - Oskad AI-d kasutada IT-probleemide diagnoosimiseks
    - Tead, kuidas küsimuse sõnastus mõjutab vastuse kvaliteeti
    - Oled lahendanud kolm IT-juhtumit ja dokumenteerinud lahenduskäigu

!!! info "Vajalik konto"
    - **ChatGPT:** [chat.openai.com](https://chat.openai.com) või **Claude:** [claude.ai](https://claude.ai)

---

## Kuidas see töötab

Sa oled IT-tugiisik. Sulle tulevad kolm piletit (ingl *ticket*). Iga pileti puhul:

1. Loe probleemikirjeldust
2. Kasuta AI-d, et leida lahendus
3. Kui esimene vastus pole piisav — **küsi paremini**
4. Dokumenteeri lahenduskäik

!!! tip "Promptimise nipp"
    Mida rohkem konteksti annad, seda parem vastus tuleb. Ära kirjuta lihtsalt "printer ei tööta" — kirjelda, mis juhtus, millal, mis süsteem, mida juba prooviti.

---

## Juhtum 1: Parool ei tööta

### Pilet

> **Saatja:** Mari, raamatupidamine
>
> **Teema:** Ei saa sisse logida
>
> **Kirjeldus:** Tulin hommikul tööle ja mu parool ei tööta enam. Eile õhtul töötas veel. Proovsin mitu korda, nüüd ütleb "konto lukustatud". Mul on homme aruande tähtaeg, palun aidake kiiresti!

### Sinu ülesanne

**Samm 1:** Esita AI-le esimene küsimus selle probleemi kohta. Kirjuta oma küsimus üles.

**Samm 2:** Loe AI vastust. Kas said konkreetse lahenduskäigu? Kui vastus oli liiga üldine, proovi täpsemalt:

```text
Kasutaja ei saa Windows domeeni sisse logida. Parool töötas eile,
täna hommikul mitte. Konto on nüüd lukustatud (Active Directory).
Mis on kõige tõenäolisemad põhjused ja kuidas samm-sammult
lahendada? Ma olen tugitiimi liige ja mul on AD admin-ligipääs.
```

**Samm 3:** Täida lahenduskaart:

| Väli | Sinu vastus |
|---|---|
| Esimene küsimus AI-le | |
| Kas esimene vastus oli piisav? | |
| Mitu päringut läks vaja? | |
| Põhjus | |
| Lahendus (lühidalt) | |
| Mida ütled Marile? | |

---

## Juhtum 2: Võrk on aeglane

### Pilet

> **Saatja:** Tõnis, müügiosakond
>
> **Teema:** Internet on kohutavalt aeglane
>
> **Kirjeldus:** Viimased paar päeva on internet meie osakonnas mega aeglane. Lehed laadivad igavesti, videokõned katkevad. Teistes osakondades paistab OK olevat. Meil on siin 8 inimest ja kõik kasutavad WiFi-t.

### Sinu ülesanne

See on keerulisem juhtum — põhjuseid võib olla mitu. Siin pead AI-lt küsima **samm-sammulise** diagnoosimisplaani.

**Samm 1:** Sõnasta probleem AI-le nii, et ta saaks anda struktureeritud veaotsinguplaani. Vihje — lisa:

- Mis on olukord (8 inimest, WiFi, üks osakond)
- Mis on sümptomid (aeglane, videokõned katkevad)
- Mis on juba teada (teistes osakondades OK)

**Samm 2:** AI annab tõenäoliselt pika nimekirja. Vali **kolm kõige tõenäolisemat põhjust** ja küsi iga kohta täpsemalt.

**Samm 3:** Täida lahenduskaart:

| Väli | Sinu vastus |
|---|---|
| Sinu prompt (kopeeri siia) | |
| Top 3 tõenäolisemat põhjust | 1. / 2. / 3. |
| Diagnoosimise sammud | |
| Millist tööriista kasutaksid kontrollimiseks? | |
| Mida ütled Tõnisele? | |

!!! warning "Kontrolli AI vastust"
    AI võib soovitada käske või tööriistu. **Kontrolli**, kas need on päris ja kas need teevad seda, mida AI väidab. Näiteks: kui AI soovitab `iperf3`, kontrolli, mis see on, enne kui kliendile soovitad.

---

## Juhtum 3: Kahtlane e-kiri

### Pilet

> **Saatja:** Kätlin, personaliosakond
>
> **Teema:** Kas see on pettus?
>
> **Kirjeldus:** Sain just e-kirja, kus Microsoft palub mul oma parooli uuendada. Link viib lehele `microsoft-security-update.com`. E-kiri näeb päris välja — on Microsoft'i logo ja kõik. Aga midagi tundub kahtlane. Ma ei vajutanud veel midagi.
>
> **Manusena:** [screenshot e-kirjast]

### Sinu ülesanne

See juhtum nõuab turvaanalüüsi. Sa pead AI-lt küsima nii tehnilist analüüsi kui ka soovitusi kasutajale.

**Samm 1:** Kirjelda olukord AI-le ja küsi analüüsi. Lisa kõik detailid piletist.

**Samm 2:** Küsi AI-lt konkreetseid kontrollimise samme:

```text
Kuidas kontrollida, kas e-kiri on phishing? Anna mulle konkreetne
checklist, mida IT-tugiisik peaks kontrollima. Kasutaja sai kirja,
mis näeb välja nagu Microsoft'i paroolimeeldetuletus, aga
domeeninimi on microsoft-security-update.com.
```

**Samm 3:** Koosta Kätlinile vastus — mitte tehniline IT-keel, vaid selge ja rahulik juhis.

**Samm 4:** Täida lahenduskaart:

| Väli | Sinu vastus |
|---|---|
| Kas tegemist on phishinguga? | Jah / Ei / Tõenäoliselt |
| Mis andis ära? (tunnused) | |
| Kontrollimise sammud | |
| Vastus Kätlinile (sinu sõnadega) | |
| Mida peaks organisatsioon tegema? | |

---

## Kokkuvõte ja analüüs

### Mis sa promptimisest õppisid?

Vaata tagasi oma kolme juhtumi päringuid ja vasta:

1. **Kontekst:** millal andis rohkem taustinfot parema vastuse?
2. **Formaat:** millal aitas, kui palusid konkreetset formaati (sammud, checklist)?
3. **Roll:** kas AI-le rolli andmine ("sa oled IT-tugiisik") muutis vastust?
4. **Iteratsioon:** mitu korda pidid keskmiselt küsimust ümber sõnastama?

### Promptimise tehnikad, mida kasutasid

Märgi ära, milliseid tehnikaid sa (teadlikult või kogemata) kasutasid:

- [ ] **Konteksti andmine** — lisasid taustainfot (süsteem, kasutaja, olukord)
- [ ] **Rolli määramine** — ütlesid AI-le, kes ta on
- [ ] **Formaadi määramine** — palusid konkreetset väljundit (sammud, checklist)
- [ ] **Samm-sammuline mõtlemine** — palusid AI-l samm-sammult läbi mõelda
- [ ] **Näited** — andsid näiteid soovitud vastusest
- [ ] **Piirangud** — seadsid pikkuse, keele vm piiranguid

!!! success "Hästi tehtud!"
    Sa just kasutasid prompt engineering tehnikaid **päris probleemide** lahendamiseks. Need samad tehnikad töötavad igas olukorras, kus AI-ga suhtled — olgu see koodikirjutamine, uurimistöö või õppimine.

---

## Kokkuvõte

Selles praktikumis sa:

- Lahendasid kolm reaalset IT-tugiprobleemi AI abiga
- Kogesid, kuidas täpsem küsimus annab parema vastuse
- Kasutasid promptimistehnikaid loomulikult, probleeme lahendades
- Dokumenteerisid lahenduskäigu nagu päris IT-tugitiimis
- Õppisid AI vastuseid kriitiliselt hindama
