---
tags:
  - Praktikum
  - Masinõpe
---

# Praktikum 5: Masinõpe brauseris — Teachable Machine

Selles praktikumis treenid oma esimese masinõppe mudeli. Teachable Machine on Google'i tasuta tööriist, mis laseb visuaalselt näha, kuidas mudel õpib — ilma ühegi koodirea kirjutamiseta.

!!! abstract "Eesmärgid"
    Selle praktikumi lõpuks:

    - Oled treeninud oma pildituvastuse mudeli
    - Tead, kuidas treeningandmed mõjutavad mudeli kvaliteeti
    - Mõistad, mis on ülesobitus (overfitting) ja andmete kallutatus (bias)

!!! info "Vajalik"
    - **Teachable Machine:** [teachablemachine.withgoogle.com](https://teachablemachine.withgoogle.com)
    - Veebikaamera (sülearvuti kaamera sobib)

---

## Osa 1: Treeni oma esimene mudel

### Samm 1: Ava Teachable Machine

Mine [teachablemachine.withgoogle.com](https://teachablemachine.withgoogle.com) ja vali **Image Project** → **Standard image model**.

### Samm 2: Loo klassid

Näed ekraanil kahte klassi. Nimeta need ümber:

- **Class 1:** "Pöial üles"
- **Class 2:** "Pöial alla"

Lisa kolmas klass (**Add a class**):

- **Class 3:** "Tühi" (taust ilma käeta)

### Samm 3: Kogu treeningandmeid

Iga klassi juures vajuta **Webcam** ja hoia nuppu all:

| Klass | Mida näidata | Pilte vähemalt |
|---|---|---|
| Pöial üles | Pöial üles, liiguta kätt eri nurkadesse | 50 |
| Pöial alla | Pöial alla, eri nurgad ja kaugused | 50 |
| Tühi | Ainult taust, ilma käeta | 30 |

!!! tip "Miks mitu nurka?"
    Mida rohkem variatsioone treeningandmetes, seda paremini mudel üldistab. Kui treenid ainult ühest nurgast, ei tunne mudel teist nurka ära.

### Samm 4: Treeni

Vajuta **Train Model**. Treenimine võtab 10-30 sekundit.

### Samm 5: Testi

Paremal on **Preview** aken. Näita kaamerale erinevaid liigutusi ja jälgi:

- Kas mudel tunneb õigesti ära?
- Milline on **usaldusskoor** (confidence) iga klassi juures?
- Millal mudel eksib?

---

## Osa 2: Paranda mudelit

### Ülesanne 1: Leia vead

Proovi leida olukordi, kus mudel eksib. Testi:

- Teine käsi (vasak vs parem)
- Teine kaugus kaamerast
- Teine taustavalgus
- Klassikaaslase käsi

Täida tabel:

| Mida näitasin | Mida mudel arvas | Usaldusskoor | Miks eksis? |
|---|---|---|---|
| | | | |
| | | | |
| | | | |

### Ülesanne 2: Lisa andmeid ja treeni uuesti

Lisa treeningandmeid nendele klassidele, kus mudel eksib. Treeni uuesti.

- Kas täpsus paranes?
- Kas mõni teine klass muutus halvemaks?

See on masinõppe põhitsükkel: **treeni → testi → paranda → korda**.

### Ülesanne 3: Lisa neljas klass

Lisa uus klass, näiteks "Rusikas" või "Avatud peopesa". Kogu andmed ja treeni uuesti.

- Kas mudel suudab nelja klassi eristada?
- Milline klass segab kõige rohkem?

---

## Osa 3: Katseta andmete mõju

### Ülesanne 4: Vähe vs palju andmeid

Loo **uus** Image Project. Tee sama katse, aga seekord:

- Üks klass: **10 pilti**
- Teine klass: **100 pilti**

Treeni ja testi:

| Klass | Treeningpilte | Täpsus (hinnanguline) |
|---|---|---|
| Vähe andmeid (10) | 10 | |
| Palju andmeid (100) | 100 | |

Mida see näitab andmete hulga mõju kohta?

### Ülesanne 5: Tausta mõju

Treeni mudel ühes kohas (nt klassiruumis). Seejärel testi seda **teises kohas** (koridoris, kodus, väljas).

- Kas täpsus muutub?
- Mida see tähendab?

!!! warning "Oluline avastus"
    Kui mudeli täpsus langeb uues kohas, tähendab see, et mudel õppis ära **tausta**, mitte sinu käeliigutuse. See on päris masinõppes väga levinud probleem.

---

## Osa 4: Seosta teooriaga

### Ülesanne 6: Mõtesta oma kogemust

Vasta oma katsetuste põhjal:

**Treeningandmed:**

- Miks on rohkem andmeid parem?
- Mis juhtub, kui ühe klassi andmeid on teistest palju vähem?

**Ülesobitus (overfitting):**

- Kas sinu mudel töötas ainult sinu käega hästi, aga klassikaaslase käega halvasti?
- Miks see juhtub ja kuidas seda vältida?

**Kallutatus (bias):**

- Kui treenisid mudelit ainult enda käega — kas see on kallutatuse näide?
- Too üks näide, kuidas andmete kallutatus võib päriselus probleeme tekitada (nt näotuvastus, laenuhindamine)

---

## Osa 5: Dokumenteeri oma projekt

Täida oma katse kohta projekti kokkuvõte:

| Väli | Sinu vastus |
|---|---|
| Klassid | |
| Treeningnäiteid kokku | |
| Treenimisaeg | |
| Täpsus (hinnanguline %) | |
| Suurim probleem | |
| Kuidas lahendasid | |
| Mis üllatas | |

!!! info "Päriselus"
    Teachable Machine on lihtne demo. Päris masinõppe mudelid vajavad tuhandeid-miljoneid näiteid, võimsamaid GPU-sid ja nädalaid treenimist. Aga põhimõte on täpselt sama — andmed sisse, mustrid välja.

---

## Kokkuvõte

Selles praktikumis sa:

- Treenisid oma esimese pildituvastuse mudeli
- Kogesid masinõppe iteratiivset protsessi: treeni → testi → paranda
- Nägid, kuidas andmete hulk ja kvaliteet mõjutavad tulemust
- Avastasid tausta mõju probleemi
- Seostasid praktilise kogemuse teooriaga (bias, overfitting)
