---
tags:
  - Praktikum
---

# Praktikum 1: Loo oma AI-abiline

Selles praktikumis lood endale AI-abilise, kes aitab sind konkreetse IT-ülesandega. Sa ei võrdle lihtsalt kahte tööriista — sa **ehitad** midagi, mida saad päriselt kasutada.

!!! abstract "Eesmärgid"
    Selle praktikumi lõpuks:

    - Oskad AI-ga vestlust alustada ja suunata
    - Tead, kuidas kontekst ja juhised mõjutavad vastust
    - Oled loonud isikliku AI-abilise, mida saad edaspidi kasutada

!!! info "Vajalik konto"
    - **ChatGPT:** [chat.openai.com](https://chat.openai.com) (kooli konto või tasuta)
    - **Claude:** [claude.ai](https://claude.ai) (tasuta konto)

    Vali üks neist — kasutad seda kogu praktikumi jooksul.

---

## Osa 1: Vali oma abilise roll

Sinu ülesanne on luua AI-abiline, kes aitab sind ühe konkreetse asjaga. Vali üks järgmistest rollidest (või paku ise):

| Roll | Mida ta teeb |
|---|---|
| **IT tugiisik** | Aitab diagnoosida ja lahendada levinud IT-probleeme |
| **Õpiabi** | Selgitab IT-mõisteid, koostab kordamisküsimusi, kontrollib su teadmisi |
| **Skriptikirjutaja** | Aitab kirjutada ja selgitada Bashi/Pythoni skripte |
| **Küberturbespetsialist** | Analüüsib turvariske ja soovitab kaitsemeetmeid |

Kirjuta oma valik üles. Seda rolli hakkad nüüd ehitama.

---

## Osa 2: Esimene katse

### Samm 1: Lihtne algus

Kirjuta AI-le lihtne küsimus, mis on seotud sinu valitud rolliga. Näiteks:

- IT tugiisik: *"Kasutaja ütleb, et printer ei prindi. Mida teha?"*
- Õpiabi: *"Selgita mulle, mis on DNS."*
- Skriptikirjutaja: *"Kirjuta skript, mis kontrollib kettaruumi."*

### Samm 2: Hinda vastust

Loe vastus läbi ja mõtle:

- Kas vastus on sinu tasemele sobiv? (Liiga lihtne? Liiga keeruline?)
- Kas see on piisavalt konkreetne?
- Kas formaat on mugav? (Liiga pikk? Liiga lühike?)

Pane oma tähelepanekud kirja — neid läheb järgmises osas vaja.

---

## Osa 3: Ehita abiline üles

Nüüd hakkad oma abilist **täiustama**. Kopeeri järgmine mall ja täida oma rolliga:

```text
ROLL: Sa oled [sinu valitud roll].

STIIL: [Kuidas ta peaks vastama? Näiteks: "Selgita lihtsalt,
kasuta igapäevaseid näiteid" või "Ole konkreetne ja tehniline"]

FORMAAT: [Kuidas vastus peaks välja nägema? Näiteks:
"Nummerdatud sammud, iga samm max 2 lauset" või
"Esmalt lühike selgitus, siis näide"]

PIIRANGUD: [Mida ta EI tohiks teha? Näiteks:
"Ära kasuta ingliskeelseid termineid ilma selgituseta" või
"Ära anna vastust, mis on pikem kui 200 sõna"]
```

### Näide: IT tugiisik

```text
ROLL: Sa oled kogenud IT-tugiisik, kes aitab algajat kolleegi.

STIIL: Selgita lihtsalt, kasuta samm-sammulisi juhiseid.
Kui on mitu võimalikku põhjust, alusta kõige levinumast.

FORMAAT: Esmalt lühike diagnoos (1-2 lauset), seejärel
nummerdatud sammud lahenduseks. Maksimaalselt 8 sammu.

PIIRANGUD: Ära eelda, et kasutaja on tehniline.
Ära soovita midagi, mis võib andmeid kaotada, ilma hoiatamata.
```

Saada oma mall AI-le ja esita seejärel sama küsimus, mille esitasid Osa 2-s. Kas vastus on nüüd parem?

---

## Osa 4: Testi ja paranda

### Samm 1: Kolm testküsimust

Esita oma abilisele kolm erinevat küsimust, mis sobivad tema rolliga. Testi eri raskusastmeid:

1. **Lihtne küsimus** — midagi, mida sa juba tead (kontrollid, kas abiline vastab õigesti)
2. **Keskmine küsimus** — midagi, mille kohta tahad rohkem teada
3. **Keeruline küsimus** — midagi, mis nõuab põhjalikumat analüüsi

### Samm 2: Hinda tulemusi

Täida tabel:

| Küsimus | Kas vastus on õige? | Kas formaat sobib? | Mida muuta? |
|---|---|---|---|
| Lihtne: | | | |
| Keskmine: | | | |
| Keeruline: | | | |

### Samm 3: Paranda malli

Muuda oma malli vastavalt tulemustele. Näiteks:

- Kui vastused olid liiga pikad → lisa piirang sõnade arvule
- Kui vastused olid liiga üldised → lisa kontekst (nt "meie koolis on Windows arvutid")
- Kui formaat ei sobinud → muuda formaadijuhist

Testi uuesti. **Korda seda protsessi**, kuni oled tulemusega rahul.

!!! tip "Iteratsioon on normaalne"
    Harva saab esimene versioon täiuslik. Päris prompt engineering ongi katsetamine: muuda üht asja korraga, testi, vaata tulemust. Täpselt nagu koodi debuggimine.

---

## Osa 5: Dokumenteeri oma abiline

Koosta oma abilise kohta lühike **dokumentatsioon**. See on sinu praktikumi lõpptulemus.

Täida järgmine mall oma dokumendifaili:

```
═══════════════════════════════════════
MINU AI-ABILINE
═══════════════════════════════════════

Nimi: [anna oma abilisele nimi]
Roll: [mida ta teeb]
Tööriist: [ChatGPT / Claude]

PROMPT (kopeeri siia oma lõplik mall):
---
[sinu prompt siia]
---

NÄIDISVESTLUS:
Küsimus: [üks hea näide]
Vastus: [AI vastus sellele]

MIS TÖÖTAB HÄSTI:
- [punkt 1]
- [punkt 2]

MIDA TULEKS VEEL PARANDADA:
- [punkt 1]

MITU ITERATSIOONI LÄKSIN LÄBI: [arv]
═══════════════════════════════════════
```

!!! warning "3K kontroll"
    Enne lõpetamist tee kiire kontroll: sa **kasutasid** AI-d (K1) — nüüd **kahtlusta** (K2): kas abilise vastused on alati õiged? Testi ühe küsimusega, mille vastust sa kindlalt tead, ja **kontrolli** (K3), kas AI vastas õigesti.

---

## Kokkuvõte

Selles praktikumis sa:

- Lõid isikliku AI-abilise konkreetse IT-ülesande jaoks
- Õppisid, kuidas roll, stiil, formaat ja piirangud mõjutavad AI vastust
- Kogesid iteratiivset protsessi: loo → testi → paranda → korda
- Dokumenteerisid oma tulemuse nii, et saad seda edaspidi kasutada

!!! success "Boonusülesanne"
    Vaheta klassikaaslasega abilised — saada talle oma prompt ja proovi tema oma. Kas sinu abiline töötab ka kellegi teise jaoks? Mida peaks muutma?
