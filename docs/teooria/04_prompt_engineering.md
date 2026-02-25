---
tags:
  - Prompt
---

# 4. Promptimise tehnikad

!!! abstract "Eesmärgid"
    - Oskan selgitada, mis on prompt ja miks selle kvaliteet mõjutab vastuse kvaliteeti
    - Tean peamisi promptimistehnikaid: zero-shot, few-shot, chain-of-thought, role prompting
    - Oskan koostada struktureeritud prompte konkreetsete ülesannete jaoks
    - Mõistan süsteemiprompti ja kasutajapromptia erinevust
    - Oskan optimeerida prompte parema väljundi saamiseks

## Miks prompt on oluline?

LLM on nagu väga võimekas, aga sõnasõnaline praktikant. Ta teeb täpselt seda, mida sa palud — aga kui sa palud halvasti, on tulemus halb. Sama mudel, mis annab ühe promptiga geniaalse vastuse, võib teise promptiga anda kasutut jama. Vahe pole mudelis, vaid küsimuses.

**Prompt** on sisend, mille sa LLM-ile annad — küsimus, juhis, kontekst või nende kombinatsioon. **Prompt engineering** on oskus kirjutada prompte nii, et mudel annaks parima võimaliku vastuse.

See pole lihtsalt "küsimuse küsimine." See on struktureeritud suhtlus, kus sa annad mudelile konteksti, defineerid rolli, näitad formaadi ja seead piirangud. Mõtle sellest kui tööülesande kirjutamisest — mida selgem ülesanne, seda parem tulemus.

??? question "🤔 Mõtle kaasa"
    Kui sa annad kellelegi ülesande — näiteks palud sõbral osta poest süüa —, kas läheb paremini, kui ütled "osta midagi" või "osta 500g kanafilee, 1 kg riisi ja kurki"? Miks?

    ??? tip "Vihje"
        Sama loogika kehtib AI puhul. Mida täpsem juhis, seda parem tulemus.

    ✅ **Vastus:** Täpsem juhis annab parema tulemuse, sest kuulaja (või AI) ei pea arvama, mida sa tegelikult tahad. "Osta midagi" jätab liiga palju tõlgendamisruumi. AI puhul on täpselt sama — "kirjuta kood" vs "kirjuta Python funktsioon, mis võtab CSV-faili sisendiks ja tagastab sorteeritud listi" annab drastiliselt erineva tulemuse.

## Zero-shot prompting

Kõige lihtsam tehnika — annad mudelile ülesande ilma ühegi näiteta.

```text
Klassifitseeri see e-kiri: rämps või tavaline.

E-kiri: "Tere! Saadan teile manuses lepingu projekti. Palun vaadake üle."
```

Mudel saab hakkama, sest ta on treenimise käigus näinud piisavalt näiteid klassifitseerimisülesannetest. Zero-shot töötab hästi lihtsate ja üheselt mõistetavate ülesannete puhul.

## Few-shot prompting

Annad mudelile mõned näited enne tegelikku ülesannet. See on üllatavalt võimas — mõni näide suunab mudeli palju täpsemini kui pikk juhis.

```text
Klassifitseeri e-kiri: rämps või tavaline.

E-kiri: "KIIRE! Võida 10000€! Kliki SIIN!"
Kategooria: rämps

E-kiri: "Homme kell 10 on meeskonna koosolek ruumis 305."
Kategooria: tavaline

E-kiri: "Congratulations!!! You've been selected for a FREE iPhone!!!"
Kategooria: rämps

E-kiri: "Palun edasta see aruanne Martinile enne reedest."
Kategooria:
```

Mudel näeb mustrit ja vastab "tavaline." Few-shot on eriti kasulik, kui ülesanne on ebatavaline või kui tahad kindlat väljundiformaati.[^few_shot]

!!! tip "Mitu näidet on piisav?"
    Tavaliselt piisab 2–5 näitest. Rohkem näiteid aitab, kui ülesanne on keerukas või ambivalentne. Aga iga näide kulutab kontekstiakent — seega tasakaal on oluline.

## Chain-of-thought prompting

Mõned ülesanded nõuavad loogikat, mitte ainult mustrite tuvastamist. Sel juhul palud mudelil *samm-sammult mõelda*, mitte kohe vastust anda.

**Ilma chain-of-thought'ita:**

```text
Serveris on 32 GB RAM-i. Operatsioonisüsteem kasutab 4 GB.
Andmebaas vajab 12 GB. Veebiserver vajab 8 GB.
Monitooringu agent vajab 2 GB. Kas mälu piisab?
```

Mudel võib vastata "Jah" ilma arvutamata.

**Chain-of-thought'iga:**

```text
Serveris on 32 GB RAM-i. Operatsioonisüsteem kasutab 4 GB.
Andmebaas vajab 12 GB. Veebiserver vajab 8 GB.
Monitooringu agent vajab 2 GB. Kas mälu piisab?

Mõtle samm-sammult: loetle iga komponendi vajadus,
arvuta kokku ja võrdle saadaolevaga.
```

Nüüd mudel teeb: 4 + 12 + 8 + 2 = 26 GB. Saadaval 32 GB. Vaba 6 GB. Jah, piisab, aga varu on napilt.[^cot]

!!! warning "Millal chain-of-thought ei aita"
    Lihtsa faktiküsimuse puhul ("Mis on Eesti pealinn?") ei anna samm-sammuline mõtlemine midagi juurde — see teeb vastuse ainult pikemaks. Kasuta seda tehnikat siis, kui ülesanne nõuab loogikat, arvutamist või mitme teguri kaalumist.

## Role prompting

Annad mudelile rolli, mis suunab vastuse stiili, sügavust ja fookust.

```text
Sa oled kogenud Linux-süsteemiadministraator 15-aastase kogemusega.
Selgita mulle, kuidas seadistada fail2ban SSH kaitseks.
Kirjuta nii, nagu selgitaksid kolleegile, kes tunneb Linuxi,
aga pole fail2ban-i varem kasutanud.
```

See on palju tõhusam kui lihtsalt "Kuidas seadistada fail2ban?" — sest rolli määramine annab mudelile konteksti, millist sügavust ja stiili oodata.

## Struktureeritud prompt

Keerukate ülesannete puhul on kasulik prompt üles ehitada selge struktuuriga:

```text
# Ülesanne
Kirjuta Ansible playbook, mis seadistab Nginx reverse proxy.

# Kontekst
- Ubuntu 24.04 server
- Taga on 3 veebiserverit portidel 8080, 8081, 8082
- SSL sertifikaat on juba olemas: /etc/ssl/certs/domain.crt
- Logid peavad minema /var/log/nginx/ alla

# Nõuded
- Kasuta Ansible parimaid praktikaid (handlers, variables)
- Lisa kommentaarid iga sektsiooni juurde
- Testi, et konfiguratsioon on süntaktiliselt korrektne

# Formaat
Väljund: üks YAML-fail koos selgitavate kommentaaridega
```

Mida selgem struktuur, seda parem tulemus. Märka, kuidas ülesanne, kontekst, nõuded ja formaat on eraldatud — see aitab mudelil aru saada, mida temalt oodatakse.

## Süsteemiprompt vs kasutajaprompt

API kaudu suheldes on kaks erinevat prompti tüüpi:

**Süsteemiprompt** (*system prompt*) — määrab mudeli käitumise kogu vestluse jooksul. Näiteks: "Sa oled IT-tugiisik, kes vastab alati eesti keeles ja kasutab tehnilisi termineid."

**Kasutajaprompt** (*user prompt*) — konkreetne küsimus või ülesanne, mille kasutaja esitab.

```text
Süsteem: Sa oled kogenud võrguinsener. Vasta alati eesti keeles.
         Kui küsitakse midagi, mis pole võrkudega seotud, ütle viisakalt,
         et see pole sinu valdkond.

Kasutaja: Miks mu ping-vastus on 200ms serverisse, mis on samas linnas?
```

Süsteemiprompt on nagu tööleping — see kehtib kogu vestluse jooksul. Kasutajaprompt on nagu konkreetne tööülesanne.

!!! bug "🔍 AI eksis — leia viga"
    **Olukord:** Küsid AI-lt sama küsimust kaks korda järjest:

    *"Mis on Eesti suuruselt teine linn?"*

    Esimene vastus: "Tartu (ligi 100 000 elanikku)"
    Teine vastus: "Narva (umbes 55 000 elanikku)"

    Miks AI annab erinevaid vastuseid? Kumb on õige?

    ??? tip "Analüüs"
        LLM on **tõenäosuslik** süsteem — ta ei otsi andmebaasist fakti, vaid genereerib statistiliselt tõenäolise vastuse. Iga kord valitakse tokenid osaliselt juhuslikult ("temperatuur" parameeter). Seepärast võib sama küsimus anda eri vastuseid.

        Tartu on Eesti suuruselt teine linn (~95 000 elanikku). Narva on kolmas.

        **Kasuta → Kahtlusta → Kontrolli:** Kui fakt on oluline, kontrolli alati teisest allikast. AI ei ole entsüklopeedia — ta on teksti generaator.

## Prompti optimeerimine

Mõned praktilised nõuanded, mis töötavad kõigi LLM-idega:

**Ole konkreetne, mitte üldine.** "Kirjuta parem kood" → "Refaktoreeri see funktsioon nii, et see kasutaks list comprehension'i ja lisaks tüübiannotatsioonid."

**Määra formaat.** Kui tahad JSON-i, ütle seda. Kui tahad tabelit, ütle seda. Kui tahad koodi ilma selgituseta, ütle seda.

**Määra piirangud.** "Vasta maksimaalselt 3 lausega." "Ära kasuta tehnilist žargooni." "Kasuta ainult Pythoni standardteeki."

**Kasuta eraldajaid.** Kui annad mudelile teksti ja juhise, eralda need selgelt — näiteks kolmekordsed tagasikriipsud, XML-sildid või pealkirjad.

**Anna negatiivne juhis.** Mõnikord on kasulikum öelda, mida *mitte* teha: "Ära alusta vastust sõnadega 'Muidugi!'" või "Ära genereeri koodi, kui ma ei küsi."

| Tehnika | Millal kasutada | Näide |
|---|---|---|
| Zero-shot | Lihtne, ühene ülesanne | "Tõlgi see lause inglise keelde" |
| Few-shot | Ebatavaline formaat, klassifitseerimine | Näited ette + "nüüd tee sama" |
| Chain-of-thought | Loogika, arvutamine, mitme teguri kaalumine | "Mõtle samm-sammult" |
| Role prompting | Spetsiifiline stiil ja sügavus | "Sa oled kogenud DBA..." |
| Struktureeritud | Keerukad, mitmeastmelised ülesanded | Ülesanne + kontekst + nõuded + formaat |

*Tabel 4.1. Promptimistehnikate kokkuvõte*

---

## Kriitiline mõtlemine

??? question "Stsenaarium 1: Klient tahab 'universaalset prompti'"
    Klient küsib sinult: "Kirjuta mulle üks prompt, mis töötab alati ja annab alati õige vastuse." Ta usub, et kusagil on üks maagiline lause, mis teeb AI täiuslikuks.

    Mida sa vastad?

    ??? tip "Kaalumiseks"
        Universaalset prompti ei eksisteeri, sest: (1) erinevad ülesanded vajavad erinevaid tehnikaid, (2) LLM on tõenäosuslik — sama prompt võib anda eri vastuseid, (3) mudel muutub iga uuendusega.

        Selle asemel õpeta klient mõistma *tehnikaid* (zero-shot, few-shot, chain-of-thought), et ta saaks ise iga olukorra jaoks sobiva prompti koostada.

??? question "Stsenaarium 2: Tundlikud andmed promptis"
    Kolleeg kirjutab prompti: "Analüüsi seda kliendi lepingut ja leia probleemsed klauslid" ning kopeerib terve lepingu teksti ChatGPT tasuta versiooni.

    Kas see on probleem?

    ??? tip "Kaalumiseks"
        Tasuta versioonides võidakse andmeid kasutada mudeli treenimiseks. Kliendi lepingud on konfidentsiaalsed. See võib rikkuda GDPR-i ja NDA-d.

        Alternatiivid: kasuta äriplaani, kasuta lokaalset mudelit (Ollama), või eemalda enne saatmist isiku- ja äriandmed.

---

## Kokkuvõte

Prompt engineering pole lihtsalt "küsimuse küsimine" — see on struktureeritud suhtlus, kus sa annad mudelile konteksti, rolli, näiteid ja piiranguid. Zero-shot töötab lihtsate ülesannete puhul, few-shot annab mudelile suuna näidetega, chain-of-thought aitab loogika- ja arvutusülesannetes. Struktureeritud promptid eraldavad selgelt ülesande, konteksti, nõuded ja formaadi. Süsteemiprompt määrab mudeli käitumise kogu vestluse jooksul, kasutajaprompt on konkreetne ülesanne. Kõik need tehnikad töötavad kõigi LLM-idega — oskus pole tööriistaspetsiifiline.

---

## Enesekontroll

??? question "1. Mis vahe on zero-shot ja few-shot promptimisel?"
    ??? tip "Vihje"
        Üks annab ülesande ilma näideteta, teine annab mõned näited ette. Kumba kasutaksid, kui tahad kindlat formaati?

    ✅ **Vastus:** Zero-shot annab mudelile ülesande ilma näideteta — mudel peab ise aru saama, mida temalt oodatakse. Few-shot annab enne ülesannet mõned näited (tavaliselt 2–5), mis näitavad soovitud formaati ja loogikat. Few-shot on tõhusam ebatavaliste ülesannete puhul ja kui soovid kindlat väljundiformaati.

??? question "2. Millal on chain-of-thought kasulik ja millal mitte?"
    ??? tip "Vihje"
        Mõtle: kas ülesanne nõuab *loogikat* või ainult fakti meenutamist?

    ✅ **Vastus:** Chain-of-thought on kasulik, kui ülesanne nõuab loogikat, arvutamist või mitme teguri kaalumist — näiteks serveri mälu planeerimine, võrguaadressi arvutamine või keeruka otsuse tegemine. See ei ole kasulik lihtsate faktiküsimuste puhul ("Mis on DNS?"), kus samm-sammuline mõtlemine ei anna midagi juurde.

??? question "3. Kuidas aitab struktureeritud prompt paremaid tulemusi saada?"
    ??? tip "Vihje"
        Mõtle tööülesandele: kas parem on "tee midagi" või "ülesanne + kontekst + nõuded + formaat"?

    ✅ **Vastus:** Struktureeritud prompt eraldab selgelt ülesande, konteksti, nõuded ja väljundiformaadi. See aitab mudelil aru saada, mida temalt täpselt oodatakse, milline on taustsüsteem, millised piirangud kehtivad ja millises formaadis vastust soovitakse. Ilma struktuurita võib mudel teha valesid eeldusi konteksti kohta.

??? question "4. Mis vahe on süsteemipromptil ja kasutajapromptil?"
    ??? tip "Vihje"
        Üks on nagu "tööleping", teine nagu "tööülesanne". Kumb kehtib kogu vestluse jooksul?

    ✅ **Vastus:** Süsteemiprompt määrab mudeli käitumise kogu vestluse jooksul — näiteks rolli, keele, stiili ja piirangud. See on nagu "tööleping." Kasutajaprompt on konkreetne küsimus või ülesanne, mille kasutaja esitab — see on nagu "tööülesanne." Süsteemiprompt kehtib kogu vestluse jooksul, kasutajaprompt muutub iga sõnumiga.

??? question "5. Nimeta kolm viisi, kuidas prompti optimeerida."
    ??? tip "Vihje"
        Mõtle: mida sa saad lisada (formaat, piirangud) ja mida sa saad ära jätta (ebamäärasus)?

    ✅ **Vastus:** (1) Ole konkreetne — "refaktoreeri see funktsioon kasutama list comprehension'i" on parem kui "kirjuta parem kood." (2) Määra väljundiformaat — ütle, kas tahad JSON-i, tabelit, koodi või proosa teksti. (3) Anna negatiivne juhis — ütle, mida mudel *ei tohiks* teha, näiteks "ära alusta vastust sõnaga 'Muidugi'" või "ära genereeri koodi, kui ma ei küsi."

[^few_shot]: Brown, T. et al. (2020). Language Models are Few-Shot Learners. *Advances in Neural Information Processing Systems*, 33. https://arxiv.org/abs/2005.14165
[^cot]: Wei, J. et al. (2022). Chain-of-Thought Prompting Elicits Reasoning in Large Language Models. *Advances in Neural Information Processing Systems*, 35. https://arxiv.org/abs/2201.11903
