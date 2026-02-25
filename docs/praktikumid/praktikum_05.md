---
tags:
  - Praktikum
---

# Praktikum 5: Masinõpe brauseris — Teachable Machine

Selles praktikumis treenid oma esimese masinõppe mudeli. Teachable Machine on Google'i tasuta tööriist, mis laseb visuaalselt näha, kuidas mudel õpib — ilma ühegi koodirea kirjutamiseta.

!!! info "Vajalik"
    - **Teachable Machine:** [teachablemachine.withgoogle.com](https://teachablemachine.withgoogle.com)
    - Veebikaamera (sülearvuti kaamera sobib)

---

## Osa 1: Esimene mudel — käeliigutuste tuvastamine

### Samm 1: Ava Teachable Machine

Mine [teachablemachine.withgoogle.com](https://teachablemachine.withgoogle.com) ja vali **Image Project** → **Standard image model**.

### Samm 2: Loo klassid

Näed ekraanil kahte klassi (Class 1, Class 2). Nimeta need ümber:

- **Class 1:** "Pöial üles"
- **Class 2:** "Pöial alla"

Lisa ka kolmas klass (vajuta **Add a class**):

- **Class 3:** "Tühi" (mitte midagi näidata)

### Samm 3: Kogu treeningandmeid

Iga klassi juures vajuta **Webcam** ja hoia nuppu all:

- **Pöial üles:** näita kaamerale pöialt üles, liiguta kätt veidi (eri nurgad, eri kaugused). Kogu vähemalt **50 pilti**
- **Pöial alla:** sama, aga pöial alla. Vähemalt **50 pilti**
- **Tühi:** kaamera ette mitte midagi panna. Vähemalt **30 pilti**

!!! tip "Miks mitu nurka?"
    Mida rohkem variatsiooni treeningandmetes, seda paremini mudel üldistab. Kui treenid ainult ühest nurgast, ei tunne mudel teist nurka ära. See on masinõppe põhireegel.

### Samm 4: Treeni mudel

Vajuta **Train Model**. Oota, kuni treenimine lõpeb (tavaliselt 10-30 sekundit).

### Samm 5: Testi

Treenimine valmis? Nüüd näed paremal **Preview** akent. Näita kaamerale erinevaid liigutusi ja vaata:

- Kas mudel tunneb õigesti ära?
- Milline on **usaldusskoor** (confidence) iga klassi juures?
- Kas mõni liigutus ajab mudeli segadusse?

---

## Osa 2: Mudeli täiustamine

### Ülesanne 1: Vigade analüüs

Leia olukordi, kus mudel eksib. Täida tabel:

| Olukord | Mida näitasin | Mida mudel arvas | Usaldusskoor |
|---|---|---|---|
| | | | |
| | | | |
| | | | |

### Ülesanne 2: Rohkem andmeid

Lisa treeningandmeid nendele klassidele, kus mudel eksib. Treeni uuesti ja kontrolli:

- Kas täpsus paranes?
- Kas mõni teine klass muutus halvemaks?

See on masinõppe iteratiivne protsess: treeni → testi → paranda → korda.

### Ülesanne 3: Lisa uus klass

Lisa neljas klass, näiteks "Rusikas" või "Avatud peopesa". Kogu andmed ja treeni uuesti.

Küsimused:

- Kas mudel suudab nelja klassi eristada?
- Milline klass segab kõige rohkem?
- Mida saaksid teha, et täpsust parandada?

---

## Osa 3: Andmete mõju mudeli kvaliteedile

### Ülesanne 4: Vähe andmeid vs palju andmeid

Loo uus Image Project ja tee sama katse, aga seekord kogu ühele klassile ainult **10 pilti** ja teisele **100 pilti**.

Treeni ja testi. Täida:

| Klass | Treeningpilte | Täpsus |
|---|---|---|
| Vähe andmeid (10) | | |
| Palju andmeid (100) | | |

Mida see näitab andmete hulga mõju kohta?

### Ülesanne 5: Tausta mõju

Treeni mudel ühes kohas (nt klassiruumis). Seejärel testi seda **teises kohas** (nt koridoris või kodus). Kas täpsus muutub?

See demonstreerib olulist probleemi: mudel võib õppida ära **tausta**, mitte objekti enda.

---

## Osa 4: Dokumenteerimine ja järeldused

### Ülesanne 6: Projekti kokkuvõte

Täida oma katse kohta:

| Väli | Sinu vastus |
|---|---|
| Klassid | |
| Treeningnäiteid kokku | |
| Treenimisaeg | |
| Täpsus (hinnanguline) | |
| Suurim probleem | |
| Kuidas lahendasid? | |

---

## Osa 5: Mõtestamine

### Ülesanne 7: Seosta teooriaga

Vasta oma kogemuse põhjal:

1. **Treeningandmed:** miks on rohkem andmeid parem? Mis juhtub, kui ühe klassi andmeid on teistest palju vähem?
2. **Ülesobitus (overfitting):** kas sinu mudel töötas ainult sinu käega hästi, aga klassikaaslase käega halvasti? Miks?
3. **Bias:** kui treenisid mudelit ainult enda käega, kas see on kallutatuse näide? Kuidas see päriselus probleeme tekitab?

!!! warning "Päriselus"
    Teachable Machine on lihtne demo. Päris masinõppe mudelid vajavad tuhandeid-miljoneid näiteid, kallimaid GPU-sid ja nädalaid treenimist. Aga põhimõte on sama — andmed sisse, muster välja.

---

## Kokkuvõte

Selles praktikumis sa:

- Treenisid oma esimese pildituvastuse mudeli Teachable Machine'is
- Kogesid masinõppe iteratiivset protsessi: treeni → testi → paranda
- Nägid, kuidas treeningandmete hulk ja kvaliteet mõjutavad tulemust
- Avastasid, et mudel võib õppida tausta, mitte objekti enda
- Seostasid praktilise kogemuse teooriaga (bias, overfitting, andmekvaliteet)
