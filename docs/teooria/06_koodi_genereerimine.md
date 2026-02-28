---
tags:
  - Kood
  - Tööriistad
  - AI
  - LLM
---

# 6. AI-abilised koodi genereerimisel

!!! abstract "Eesmärgid"
    - Oskan selgitada, kuidas AI koodiabilised töötavad ja mida nad tegelikult teevad
    - Mõistan Copiloti, Claude Code'i ja vestlusrobotite erinevusi koodigenereerimisel
    - Tean, kuidas AI-genereeritud koodi kriitiliselt hinnata ja testida
    - Oskan kasutada AI-d efektiivselt erinevates arendusetappides
    - Mõistan AI koodigenereerimise piiranguid ja riske

## AI ei kirjuta koodi — ta genereerib seda

Oluline eristus: AI koodiabiline ei ole programmeerija. Ta ei *mõista* koodi — ta genereerib teksti, mis näeb välja nagu kood ja statistiliselt tõenäoliselt ka töötab. Mõnikord on tulemus suurepärane. Mõnikord on see elegantne, aga valesti töötav jama.

See tähendab, et AI on *abiline*, mitte *asendus*. Sa pead mõistma, mida kood teeb, et hinnata, kas AI väljund on korrektne. IT-spetsialist, kes kasutab AI-d ilma koodi mõistmata, on nagu keegi, kes laseb Google Translate'il lepingu tõlkida ja kirjutab kohe alla — tulemus võib olla katastroofiline.

!!! warning "Kuldreegel"
    Ära kunagi kasuta AI-genereeritud koodi, mida sa ei mõista. Kui sa ei oska selgitada, mida iga rida teeb, siis kontrolli, testi ja uuri enne kasutamist.

## Kuidas koodiabilised töötavad

### Copilot — autocomplete stereoididel

GitHub Copilot töötab otse sinu koodiredaktoris. Ta loeb sinu praegust faili, avatud faile, kommentaare ja funktsiooninimesid ning pakub reaalajas jätku. Kirjutad kommentaari `# funktsioon, mis kontrollib ketta täituvust` ja Copilot genereerib terve funktsiooni.

Copilot on kiire igapäevastes ülesannetes: boilerplate'i genereerimine, tuttavate mustrite lõpetamine, testide kirjutamine. Ta on nõrgem keerukates, mitme faili vahelistes ülesannetes.

### Claude Code — agentlik lähenemine

Claude Code on käsureaatööriist, mis suudab navigeerida kogu koodibaasis. Sa kirjeldad ülesannet loomulikul keeles ja tööriist: loeb vajalikud failid, teeb muudatused, käivitab teste ja itereerib. See on agentlik lähenemine — tööriist teeb mitu sammu iseseisvalt, mitte ainult ühe rea autocompletejätku.

Claude Code on tugevam keerukates ülesannetes: refaktoreerimine, mitme faili samaaegne muutmine, bugide leidmine suures koodibaasis.

### Vestlusrobot kui koodipartner

ChatGPT, Claude ja Gemini vestlusliidesed sobivad koodi genereerimiseks siis, kui ülesanne on iseseisev — "kirjuta funktsioon, mis parsib CSV-faili" või "selgita mulle, mida see regex teeb." Nad ei näe sinu koodibaasi konteksti (välja arvatud, kui kopeerid selle sisse).

| Tööriist | Tugevus | Nõrkus | Parim kasutuskoht |
|---|---|---|---|
| Copilot | Kiire, reaalajas, IDE-s | Ei näe suurt pilti | Igapäevane koodikirjutamine |
| Claude Code | Koodibaasi navigeerimine, agentlik | Vajab CLI kogemust | Keerukad, mitmeastmelised ülesanded |
| Vestlusrobot | Selgitused, iseseisvad ülesanded | Ei näe koodibaasi | Õppimine, kiired küsimused |

*Tabel 6.1. Koodiabiliste võrdlus*

## AI arendusprotsessi erinevates etappides

AI pole kasulik ainult koodi kirjutamisel. Siin on ülevaade, kuidas AI aitab kogu arendusprotsessi jooksul:

**Planeerimine.** "Mul on vaja skripti, mis monitoorib 50 serverit. Milline arhitektuur oleks mõistlik? Mis keeles kirjutada?" AI aitab alternatiive kaaluda ja trade-off'e analüüsida.

**Kirjutamine.** Boilerplate, funktsioonid, klassid, konfiguratsioonifailid. AI genereerib algversiooni, mida sa siis kohandad ja täiendad.

**Testimine.** "Kirjuta unit testid sellele funktsioonile, katavalt nii normaal- kui äärejuhtumid." AI on testide genereerimisel üllatavalt hea — ta mõtleb äärejuhtumitele, millele sa ise ei pruugi mõelda.

**Dokumenteerimine.** "Kirjuta docstring'id kõigile funktsioonidele selles failis." Igav, aga vajalik töö, mille AI teeb sekunditega.

**Refaktoreerimine.** "Muuda see funktsioon puhtamaks, kasuta tüübiannotatsioone ja jaga see väiksemateks funktsioonideks." AI näitab alternatiivset lähenemist, mida sa ise ei pruukinud kaaluda.

**Veaotsing.** Kleebi veateade ja kontekst — AI aitab tuvastada probleemi ja pakub lahenduse. Eriti kasulik krüptiliste vigade puhul.

## AI-genereeritud koodi hindamine

Enne AI-genereeritud koodi kasutamist kontrolli alati:

**Kas see kompileerub/töötab?** Käivita kood. AI genereerib mõnikord süntaksivigu või kasutab teeke, mida pole installeeritud.

**Kas see teeb seda, mida paluti?** Testi erinevate sisenditega, sealhulgas äärejuhtumitega (tühi sisend, null, väga suur arv, vale formaat).

**Kas see on turvaline?** AI-genereeritud kood võib sisaldada turvaauke — SQL-süst, krüpteerimata paroolid, hardcoded credentials. *Alati* kontrolli turvaaspekte.

**Kas see on efektiivne?** AI ei optimeeri alati jõudlust. Funktsioon, mis töötab 10 kirje peal, võib 10 miljoni kirjega kokku joosta.

**Kas see on loetav?** Mõnikord genereerib AI ülemäära keerukat koodi, kui lihtne lahendus piisaks.

!!! danger "Turvarisk: sõge usaldamine"
    2024. aastal leiti uuring, kus arendajad, kes kasutasid AI koodiabilist, tootsid statistiliselt *rohkem* turvaauguga koodi kui need, kes kirjutasid käsitsi — sest AI-koodi usaldati ilma kontrollimata.[^security_study] AI on tööriist, mitte autoriteet.

## Praktilised näited IT-kontekstis

**Bash-skript:** "Kirjuta skript, mis leiab kõik failid, mis on vanemad kui 30 päeva kataloogis /var/log, logib nende nimed ja kustutab need."

**Python-automaatika:** "Kirjuta skript, mis loeb CSV-faili, kontrollib iga serveri pingi ja genereerib HTML-raporti."

**Ansible playbook:** "Kirjuta playbook, mis paigaldab ja konfigureerib Zabbix agendi Ubuntu 24.04 serveritele."

**Dockerfile:** "Genereeri Dockerfile Python Flask rakenduse jaoks, mis kasutab multi-stage build'i ja jookseb non-root kasutajana."

Kõikidel juhtudel on AI kiire algversiooni genereerimisel. Sinu ülesanne on kontekst lisada, tulemust testida ja kohandada.

---

## Kokkuvõte

AI koodiabilised genereerivad koodi statistiliste mustrite põhjal — nad ei mõista koodi nagu programmeerija. Copilot töötab IDE-s reaalajas autocompletena, Claude Code navigeerib koodibaasis agentlikult, vestlusrobotid sobivad iseseisvateks ülesanneteks ja õppimiseks. AI on kasulik kogu arendusprotsessi jooksul: planeerimisest testimise ja dokumenteerimiseni. AI-genereeritud koodi tuleb alati kriitiliselt hinnata: testida, kontrollida turvalisust ja veenduda efektiivsuses. AI on abiline, mitte asendus — sa pead mõistma, mida kood teeb.

---

## Enesekontroll

??? question "1. Miks ei tohi AI-genereeritud koodi pimesi usaldada?"
    ??? success "Vastus"
        AI genereerib koodi statistiliste mustrite põhjal — ta ei "mõista" koodi loogikat, turvalisust ega jõudlust. AI-genereeritud kood võib sisaldada süntaksivigu, turvaauke (SQL-süst, hardcoded credentials), jõudlusprobleeme või lihtsalt valesti töötada. Uuringud näitavad, et AI-abilistega töötavad arendajad toodavad rohkem turvaauguga koodi, sest nad usaldavad väljundit ilma kontrollimata.

??? question "2. Millal on Copilot parem valik kui Claude Code?"
    ??? success "Vastus"
        Copilot on parem igapäevaseks koodikirjutamiseks IDE-s — ta pakub reaalajas soovitusi, lõpetab mustrite järgi ja genereerib boilerplate'i kiiresti. Claude Code on parem keerukate, mitmeastmeliste ülesannete jaoks, kus on vaja navigeerida suures koodibaasis, muuta mitut faili korraga ja teha iseseisvaid otsuseid.

??? question "3. Kuidas saab AI aidata arendusprotsessi testimise etapis?"
    ??? success "Vastus"
        AI genereerib unit teste, katab nii normaal- kui äärejuhtumid (tühi sisend, null, väga suur arv, vale formaat), leiab puuduvaid testistsenaariume ja genereerib mock-objekte. AI on testide genereerimisel eriti hea, sest ta mõtleb äärejuhtumitele, millele arendaja ise ei pruugi mõelda.

??? question "4. Millised turvariskid on AI-genereeritud koodis?"
    ??? success "Vastus"
        Levinumad turvariskid: SQL-süst (parameetriteta päringud), krüpteerimata paroolid, hardcoded credentials, ebaturvalised vaikeseadistused, puuduv sisendvalideerimine, aegunud teekide kasutamine teadaolevate haavatavustega. AI ei mõtle turvalisusele süsteemselt — ta genereerib koodi, mis *töötab*, aga ei pruugi olla *turvaline*.

??? question "5. Nimeta viis etappi arendusprotsessis, kus AI saab aidata."
    ??? success "Vastus"
        (1) Planeerimine — arhitektuuri arutelu ja alternatiivide kaalumine. (2) Kirjutamine — boilerplate, funktsioonid, konfiguratsioonid. (3) Testimine — unit testid, äärejuhtumid. (4) Dokumenteerimine — docstring'id, README, SOP-d. (5) Refaktoreerimine — koodi puhastamine, tüübiannotatsioonid, funktsioonide jagamine.

[^security_study]: Perry, N. et al. (2023). Do Users Write More Insecure Code with AI Assistants? *ACM Conference on Computer and Communications Security*. https://arxiv.org/abs/2211.03622
