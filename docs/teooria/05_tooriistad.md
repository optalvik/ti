---
tags:
  - Tööriistad
  - LLM
  - AI
  - Prompt
---

# 5. AI tööriistad

!!! abstract "Eesmärgid"
    - Tean peamisi AI tööriistade kategooriaid: vestlusrobotid, koodiabilised, õppimistööriistad, lokaalsed mudelid
    - Oskan võrrelda ChatGPT, Claude, Gemini, NotebookLM ja Copiloti tugevusi ja nõrkusi
    - Mõistan pilvepõhiste ja lokaalsete mudelite erinevust (privaatsus, kiirus, maksumus)
    - Oskan valida ülesandele sobiva tööriista
    - Tean, kuidas AI tööriistu IT-töös praktiliselt kasutada

## Tööriistade maastik 2026

AI tööriistu on palju ja neid tuleb pidevalt juurde. Selle asemel, et iga tööriista detaile pähe tuupida, on targem mõista *kategooriaid* — siis oskad iga uue tööriista õigesse kasti panna ja hinnata, kas see sinu vajadusi täidab.

### Üldised vestlusrobotid

Need on "räägi masinaga" tööriistad, kus sa kirjutad küsimuse ja saad vastuse. Kõige tuntumad:

**ChatGPT** (OpenAI) — esimene laialt levinud LLM-teenus. Kasutab GPT-mudelisarja. Tugev üldiste tekstiülesannete, koodi genereerimise ja analüüsi poolest. Tasuta versioon saadaval, tasuline Pro-pakett lisavõimalustega.

**Claude** (Anthropic) — tuntud pikkade dokumentide analüüsi, nüansirohke arutluse ja koodikirjutamise poolest. Pakub suurt kontekstiakent. Tasuta versioon saadaval, tasuline Pro-pakett.

**Gemini** (Google) — integreeritud Google'i ökosüsteemiga (Gmail, Docs, Search). Tugev multimodaalsete ülesannete poolest (tekst + pilt + video).

Kõik kolm suudavad enamiku igapäevaseid ülesandeid — kirjutada teksti, vastata küsimustele, analüüsida dokumente, genereerida koodi. Erinevused on nüanssides: üks on parem pikas analüüsis, teine kiiremas koodigenereerimises, kolmas Google'i teenustega integreerumises.

### Koodiabilised

Need on AI tööriistad, mis on spetsiaalselt loodud arendajate jaoks:

**GitHub Copilot** — töötab otse koodiredaktoris (VS Code, JetBrains). Pakub reaalajas koodisoovitusi, kui sa kirjutad. Mõtle sellest kui autocomplete'ist, mis mõistab konteksti. Haridusasutustele ja õpilastele tasuta.

**Claude Code** (Anthropic) — käsureaatööriist, mis suudab navigeerida koodibaasis, lugeda faile, kirjutada koodi ja käivitada käsklusi. Agentlik lähenemine — sa kirjeldad ülesannet ja tööriist teeb mitu sammu iseseisvalt.

**Cursor, Windsurf** — AI-põhised koodiredaktorid, mis integreerivad LLM-i otse arenduskeskkonda.

### Õppimis- ja uurimistööriistad

**Google NotebookLM** — AI-põhine uurimisassistent, mis analüüsib *sinu üles laaditud* dokumente. Laadid üles PDF-id, artiklid, märkmed või veebilehed ja NotebookLM vastab küsimustele ainult nende allikate põhjal — ta ei hallutsineri juurde, sest piirdub sinu materjaliga. Eriti kasulik: aine kordamine, tehnilise dokumentatsiooni kokkuvõtmine, allikatepõhine uurimine. Unikaalne funktsioon: genereerib üles laaditud materjalidest **podcast-stiilis audiokokkuvõtte**, kus kaks AI häält arutavad teemat loomulikul viisil.

!!! tip "Miks NotebookLM on õppijale eriti kasulik"
    Tavaline vestlusrobot vastab oma treenimisandmete põhjal ja võib hallutsineerida. NotebookLM piirdub ainult sinu üles laaditud allikatega — iga vastus viitab konkreetsele kohale konkreetses dokumendis. See on nagu isiklik tuutor, kes on lugenud täpselt samu materjale kui sina.

### Lokaalsed mudelid

**Ollama** — tööriist, mis võimaldab LLM-e käitada otse oma arvutis. Andmed ei lahku sinu masinast — see on kriitiline, kui töötad tundlike andmetega. Mudelid on väiksemad kui pilveteenuste omad (7B–70B parameetrit vs 100B+ pilves), aga privaatsus on tagatud.

Miks see oluline on? Kui sa analüüsid ettevõtte sisemisi dokumente, klientide andmeid või konfiguratsioone, ei pruugi olla lubatud neid pilveteenusesse saata. Lokaalne mudel lahendab selle probleemi.

## Võrdlustabel

| Omadus | ChatGPT | Claude | Gemini | NotebookLM | Copilot | Ollama |
|---|---|---|---|---|---|---|
| Tüüp | Vestlusrobot | Vestlusrobot | Vestlusrobot | Uurimisassistent | Koodiabiline | Lokaalne LLM |
| Arendaja | OpenAI | Anthropic | Google | Google | GitHub/Microsoft | Meta/kogukond |
| Tasuta versioon | Jah (piiratud) | Jah (piiratud) | Jah (piiratud) | Jah (tasuta) | Õpilastele tasuta | Täiesti tasuta |
| Privaatsus | Pilves | Pilves | Pilves | Pilves | Pilves | Lokaalne — andmed ei lahku |
| Koodi genereerimine | Hea | Väga hea | Hea | Ei | Suurepärane (IDE-s) | Sõltub mudelist |
| Pikk dokument | Hea | Väga hea (suur aken) | Hea | Suurepärane (allikapõhine) | Ei ole mõeldud selleks | Piiratud |
| Multimodaalne | Jah (pilt, heli) | Jah (pilt, dokument) | Jah (pilt, video, heli) | Jah (PDF, veeb, video) | Ei | Sõltub mudelist |
| Audio kokkuvõte | Ei | Ei | Ei | Jah (podcast) | Ei | Ei |
| API saadaval | Jah | Jah | Jah | Ei | Ei (eraldi teenus) | Jah (lokaalne) |

*Tabel 5.1. AI tööriistade võrdlus (seisuga 2026)*

!!! warning "See tabel vananeb kiiresti"
    AI tööriistade maastik muutub kuude kaupa. Tabel annab üldise pildi, aga konkreetsed funktsioonid ja hinnad tuleks alati tööriista enda dokumentatsioonist kontrollida.

## Kuidas valida õige tööriist

Tööriista valik sõltub ülesandest, mitte tööriista populaarsusest. Siin on mõned juhised:

**Üldine küsimus või tekstiülesanne** — ChatGPT, Claude või Gemini. Proovi kõiki ja vali see, mille väljund sulle rohkem meeldib. Aja jooksul tekib eelistus, aga oskus on universaalne.

**Koodi kirjutamine IDE-s** — GitHub Copilot. Ta näeb sinu koodi konteksti ja pakub soovitusi reaalajas. Claude Code on hea alternatiiv keerukamate, mitmeastmeliste ülesannete puhul.

**Tundlike andmete analüüs** — Ollama. Kui andmed ei tohi ettevõttest lahkuda, on lokaalne mudel ainus valik.

**Google'i teenustega integratsioon** — Gemini. Kui töötad igapäevaselt Gmail-i, Docs-i ja Drive'iga, on Gemini integratsioon kõige sujuvam.

**Pikk dokumendianalüüs** — Claude. Suur kontekstiaken võimaldab analüüsida mahukaid dokumente, lepinguid ja tehnilisi spetsifikatsioone ühes päringus.

**Õppimine ja uurimine** — NotebookLM. Laadi üles kursusematerjalid, RFC-dokumendid, tehnilised spetsifikatsioonid — ja küsi küsimusi, mis piirduvad ainult nende allikatega. Genereeri audiokokkuvõte, mida kuulata trenni ajal või teel kooli.

!!! tip "Universaalne oskus"
    Kõige olulisem pole mitte konkreetne tööriist, vaid promptimisoskus. Hea prompt töötab igas LLM-is. Seetõttu keskendub see kursus tehnikatele, mitte nuppude asukohale.

## Praktiline: mida IT-spetsialist tegelikult teeb

Siin on konkreetsed näited, kuidas AI tööriistade kasutamine IT-igapäevas välja näeb:

**Logide analüüs.** Kopeeri 500 rida serverilogi LLM-i ja küsi: "Leia anomaaliad ja selgita, mis võis neid põhjustada." LLM tuvastab mustrid kiiremini kui käsitsi lugemine.

**Skriptide kirjutamine.** "Kirjuta Bash-skript, mis kontrollib kõigi serverite ketaste täituvust ja saadab meili, kui mõni ketas on üle 80% täis." Sa saad toimiva algversiooni sekunditega.

**Dokumentatsiooni koostamine.** "Selle Ansible playbooki põhjal kirjuta SOP dokument, mida uus tiimiliige saaks järgida."

**Veaotsing.** "Ma saan selle veateate: [viga]. Mida see tähendab ja kuidas parandada?" Eriti kasulik, kui veateade on krüptiline ja Google'ist ei leia head vastust.

**Konfiguratsiooni genereerimine.** "Genereeri Nginx konfiguratsioon, mis teeb reverse proxy kolmele taustaserverile koos SSL-iga ja rate limiting'uga."

---

## Kokkuvõte

AI tööriistad jagunevad nelja põhikategooriasse: üldised vestlusrobotid (ChatGPT, Claude, Gemini), koodiabilised (Copilot, Claude Code), õppimis- ja uurimistööriistad (NotebookLM) ning lokaalsed mudelid (Ollama). Tööriista valik sõltub ülesandest — pilveteenused on võimsamad, lokaalsed mudelid tagavad privaatsuse. Kõige olulisem oskus on promptimine, mis on universaalne ja töötab kõigi tööriistadega. IT-spetsialisti igapäevatöös on AI kasulik logide analüüsis, skriptide kirjutamises, dokumentatsiooni koostamises, veaotsingus ja konfiguratsiooni genereerimisel.

---

## Enesekontroll

??? question "1. Mille poolest erineb lokaalne mudel (Ollama) pilveteenusest (ChatGPT, Claude)?"
    ??? success "Vastus"
        Lokaalne mudel töötab sinu enda arvutis — andmed ei lahku masinast, mis tagab privaatsuse. Pilveteenused töötavad teenusepakkuja serverites, mis tähendab, et sinu sisend liigub üle interneti. Lokaalsed mudelid on väiksemad ja vähem võimekad, aga privaatsuse seisukohalt on need ainus valik, kui andmed ei tohi ettevõttest lahkuda.

??? question "2. Millisel juhul eelistaksid Copilot'i ja millisel Claude Code'i?"
    ??? success "Vastus"
        Copilot on parem igapäevaseks koodikirjutamiseks IDE-s — ta pakub reaalajas soovitusi, kui sa kirjutad. Claude Code on parem keerukamate, mitmeastmeliste ülesannete jaoks — näiteks kogu koodibaasi refaktoreerimine, mitme faili samaaegne muutmine või agentlik töövoog, kus tööriist teeb mitu sammu iseseisvalt.

??? question "3. Mille poolest erineb NotebookLM tavalisest vestlusrobotist ja miks see õppijale kasulik on?"
    ??? success "Vastus"
        NotebookLM piirdub ainult kasutaja üles laaditud allikatega — ta ei kasuta oma treenimisandmeid ega hallutsineri juurde. Iga vastus viitab konkreetsele kohale konkreetses dokumendis. Tavaline vestlusrobot (ChatGPT, Claude, Gemini) vastab oma treenimisandmete põhjal ja võib hallutsineerida. NotebookLM on eriti kasulik õppimisel, sest ta toimib nagu isiklik tuutor, kes on lugenud täpselt samu materjale. Lisaks genereerib ta audiokokkuvõtteid, mida saab kuulata teel kooli või trenni ajal.

??? question "4. Miks on oluline proovida mitut AI tööriista, mitte keskenduda ainult ühele?"
    ??? success "Vastus"
        Eri mudelitel on erinevad tugevused — üks on parem pikas analüüsis, teine kiiremas koodigenereerimises, kolmas konkreetses valdkonnas. Samuti muutuvad tööriistad kiiresti — tänane parim valik ei pruugi olla homme parim. Kõige olulisem on universaalne promptimisoskus, mis töötab igas tööriistas.

??? question "5. Nimeta kolm konkreetset viisi, kuidas IT-spetsialist AI tööriista igapäevatöös kasutab."
    ??? success "Vastus"
        Näiteks: (1) logide analüüs — kopeeri serverilogid LLM-i ja küsi anomaaliate kohta; (2) skriptide kirjutamine — kirjelda ülesannet ja saa toimiv algversioon; (3) veaotsing — kleebi veateade ja küsi selgitust ja lahendusetappe. Lisaks: dokumentatsiooni koostamine, konfiguratsiooni genereerimine.

??? question "6. Millal on lokaalne mudel (Ollama) parem valik kui pilveteenus?"
    ??? success "Vastus"
        Kui töötad tundlike andmetega, mida ei tohi ettevõttest välja saata — näiteks klientide isikuandmed, sisemised konfiguratsioonid, ärisaladused, meditsiiniandmed. Samuti kui sul pole usaldusväärset internetiühendust või kui tahad AI-d kasutada ilma igakuise tellimuseta (Ollama on tasuta).
