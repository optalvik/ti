---
tags:
  - Praktikum
  - AI
  - Tööriistad
---

# Praktikum 3: Tehno-detektiiv

Selles praktikumis oled sa detektiiv. Sinu ülesanne on uurida välja, kas üks levinud tehnoväide vastab tõele. Kasutad AI-otsingut, tavalist otsingut ja allikate hindamist, et jõuda **tõendatud järelduseni**.

!!! abstract "Eesmärgid"
    Selle praktikumi lõpuks:

    - Oskad kasutada AI-otsingut (Perplexity) sihipäraselt
    - Tead, kuidas hinnata allikate usaldusväärsust
    - Oled kirjutanud tõenduspõhise faktikontrolli raporti

!!! info "Vajalikud tööriistad"
    - **Perplexity:** tasuta konto aadressil [perplexity.ai](https://www.perplexity.ai)
    - **Google:** tavapärane veebiotsing

---

## Osa 1: Vali oma juhtum

Vali üks järgmistest väidetest, mida hakkad uurima (või paku ise):

| # | Väide | Valdkond |
|---|---|---|
| A | "Incognito mode teeb sind internetis nähtamatuks" | Privaatsus |
| B | "Tasuta VPN kaitseb su andmeid sama hästi kui tasuline" | Turvalisus |
| C | "Telefoni aku kestab kauem, kui sulged taustarakendused" | Riistvara |
| D | "Avalikus WiFi-s ei tohi kunagi pangalehte avada" | Võrguturve |
| E | "AI asendab programmeerijad 5 aasta pärast" | Tulevikutrendid |

!!! tip "Hea valik"
    Vali teema, mis sind päriselt huvitab — nii on uurimine põnevam. Kui tead mõnda muud tehnoväidet, mida tahad kontrollida, kasuta seda.

Kirjuta üles: **Minu uuritav väide:**  _______________

---

## Osa 2: Esmane uuring AI-ga

### Samm 1: Küsi Perplexity-lt

Ava [perplexity.ai](https://www.perplexity.ai) ja sõnasta oma väide küsimusena. Näiteks:

- Väide A: *"Kas incognito mode teeb kasutaja internetis anonüümseks? Mis on tegelikud piirangud?"*
- Väide D: *"Kas avalikus WiFi-s on pangalehe avamine ohtlik? Millised on reaalsed riskid 2025. aastal?"*

### Samm 2: Uuri allikaid

Perplexity näitab vastuse juures **allikaid**. Ava vähemalt 3 allikat ja hinda neid:

| Allikas | Tüüp | Usaldusväärsus (1-5) | Põhjendus |
|---|---|---|---|
| | Ametlik / akadeemiline / uudis / blogi | | |
| | | | |
| | | | |

!!! warning "Allikate hierarhia"
    Kõik allikad pole võrdsed:

    1. **Ametlik dokumentatsioon** (Google, Microsoft, Cisco, CERT) — kõige usaldusväärsem
    2. **Akadeemilised artiklid** — eelretsenseeritud teadusuuringud
    3. **Tuntud tehnikaväljaanded** (Ars Technica, Wired, The Register)
    4. **Tehnikafoorumid** (Stack Overflow, ServerFault) — kontrollida mitut vastust
    5. **Blogid ja YouTube** — kõige vähem usaldusväärne, vajab alati lisakontrolli

### Samm 3: Lisa küsimusi

Esimene vastus tekitab uusi küsimusi. Sõnasta vähemalt 2 täpsustavat küsimust ja esita need Perplexityle. Näiteks:

- "Mida näeb mu internetiteenuse pakkuja, kui kasutan incognito mode'i?"
- "Kas HTTPS kaitseb avalikus WiFi-s piisavalt?"

Kirjuta vastused ja allikad üles.

---

## Osa 3: Vastaspoole uuring

Hea detektiiv uurib **mõlemat poolt**. Nüüd otsi teadlikult infot, mis **ei nõustu** sinu senise leiuga.

### Samm 1: Google'i otsing

Otsi Google'ist oma väite kohta, lisades sõnu nagu "myth", "debunked", "actually" või "misconception":

```text
"incognito mode" myth debunked
```

```text
"public WiFi" banking "is it safe" 2025
```

### Samm 2: Kas leidub vastupidist infot?

| Küsimus | Sinu vastus |
|---|---|
| Kas keegi väidab vastupidist? | |
| Kas nende allikad on usaldusväärsed? | |
| Kas tõde on kusagil "vahepeal"? | |

!!! tip "Nüanss on oluline"
    Enamik tehnoväiteid pole 100% õiged ega 100% valed. Sageli on vastus: "See oleneb..." — ja just see nüanss on väärtuslik.

---

## Osa 4: Koosta raport

Nüüd koosta oma uurimistöö tulemus. See on sinu praktikumi **lõpptulemus**.

Kopeeri järgmine mall oma dokumendifaili ja täida:

```text
═══════════════════════════════════════════════════
FAKTIKONTROLLI RAPORT
═══════════════════════════════════════════════════

VÄIDE: [uuritav väide]

VERDIKT: [Tõene / Osaliselt tõene / Eksitav / Vale]

───────────────────────────────────────────────────
KOKKUVÕTE (3-5 lauset):
[Mida sa leidsid? Mis on tegelik olukord?]

───────────────────────────────────────────────────
TÕENDID POOLT:
1. [fakt + allikas]
2. [fakt + allikas]

TÕENDID VASTU:
1. [fakt + allikas]
2. [fakt + allikas]

───────────────────────────────────────────────────
NÜANSS:
[Millistel tingimustel on väide õige? Millistel vale?]

───────────────────────────────────────────────────
ALLIKAD:
1. [autor/organisatsioon, pealkiri, URL]
2.
3.
4.

───────────────────────────────────────────────────
PRAKTILINE SOOVITUS:
[Mida peaks tavaline kasutaja tegelikult tegema?]
═══════════════════════════════════════════════════
```

---

## Osa 5: Enesekontroll

Enne esitamist kontrolli oma raportit:

- [ ] Verdikt põhineb allikatel, mitte arvamusel
- [ ] Vähemalt 3 allikat on kasutatud
- [ ] Vähemalt 1 allikas on ametlik dokumentatsioon või akadeemiline
- [ ] Uurisin ka vastupidist seisukohta
- [ ] Praktiline soovitus on konkreetne ja teostatav

!!! warning "3K kontroll"
    Sa **kasutasid** AI-d info leidmiseks (K1). Nüüd **kahtlusta** (K2) — kas Perplexity tõlgendas allikaid õigesti? **Kontrolli** (K3) — ava vähemalt üks allikas otse ja veendu, et Perplexity refereeris seda täpselt.

---

## Kokkuvõte

Selles praktikumis sa:

- Uurisid välja, kas levinud tehnoväide vastab tõele
- Kasutasid AI-otsingut ja tavalist otsingut koos
- Hindasid allikate usaldusväärsust ja tüüpe
- Otsisid teadlikult ka vastupidist seisukohta
- Koostasid tõenduspõhise faktikontrolli raporti

!!! success "Boonusülesanne"
    Esitle oma raportit klassile 2-minutilise "verdiktina". Kas klassikaaslased nõustuvad? Kas keegi leidis vastupidist infot?
