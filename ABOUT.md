# Over deze tool

## Wat is dit?

Een browser-gebaseerde contractgenerator voor de **LHV-modelovereenkomst Incidentele Waarneming huisarts** (Belastingdienst beoordeling nr. 905-2021-82676-2-0, d.d. 30 september 2021).

De tool vult de variabele velden van de modelovereenkomst in op basis van een eenvoudig formulier en genereert vervolgens een echte `.docx` die direct geprint of gemaild kan worden.

## Waarom?

Dit project is ontstaan uit een praktische vraag tijdens de opstart van de huisartsenpraktijk van mijn vrouw: bij elke incidentele waarneming moest opnieuw een contract worden opgesteld op basis van het LHV-model, met handmatig kopiëren, plakken en invullen. Dat kan efficiënter, mits het juridisch correct blijft.

De tool is dus primair gebouwd voor **één praktijk**, maar werkt voor iedere huisarts die met het LHV-model voor incidentele waarneming werkt.

## Wie?

Ontwikkeld door **Niels Braakman** als persoonlijk project in de vrije tijd.

- Geen affiliatie met het Haaglanden Medisch Centrum (mijn werkgever) of enige andere organisatie
- Geen affiliatie met de LHV of de Belastingdienst
- Niet-commercieel, gratis te gebruiken, open source

## Hoe is het gebouwd?

Dit is voor mij ook een experiment in **multi-AI samenwerking**. Het bouwproces:

- **Claude (Anthropic)** — initiële architectuur, formulierlogica, juridische structuur, iteratieve bugfixes, mobiele UX, iOS Share Sheet integratie, PWA-setup
- **ChatGPT (OpenAI)** — meerdere rondes van red-teaming en juridische review, concrete punchlists voor verbeteringen, en de native `.docx` export-engine (OOXML-generatie zonder externe libraries)
- **Gemini (Google)** — privacy-review en UX-suggesties
- **Grok (xAI)** — aanvullende UX-feedback

Elke AI heeft op basis van de vorige iteratie kritiek geleverd. De resulterende tool is iteratief verbeterd tot een stabiele versie. De eindregie (welke suggesties wel/niet doorvoeren, juridische afweging, deployment) lag bij mij.

## Wat doet de tool wél?

- Genereert een contracttekst die inhoudelijk overeenkomt met de LHV-modelovereenkomst
- Neemt de door de Belastingdienst gemarkeerde bepalingen **ongewijzigd** over, inclusief gele markering in de output
- Bevat de officiële verwijzing naar het Belastingdienst-kenmerknummer
- Valideert de duur (waarschuwing bij >7 dagen, blokkade bij >30 dagen) om misbruik voor duurwaarneming te voorkomen
- Splitst ANW-diensten expliciet af naar het aparte LHV-contracttype
- Verplicht een pre-download checklist waarin de gebruiker bevestigt dat de feitelijke situatie past bij incidentele waarneming
- Draait volledig client-side (in de browser): ingevulde contractgegevens worden niet naar een server verstuurd

## Wat doet de tool **niet**?

- **Geen juridisch advies.** De tool genereert een contracttekst, maar beoordeelt niet of de feitelijke arbeidsrelatie kwalificeert als overeenkomst van opdracht (DBA-proof). Bij twijfel: raadpleeg een jurist of fiscaal adviseur.
- **Geen garantie op Belastingdienst-conformiteit.** De tekst is afgeleid van de beoordeelde modelovereenkomst, maar de uiteindelijke kwalificatie door de Belastingdienst hangt af van feitelijke uitvoering, niet alleen van de contracttekst.
- **Geen onderhoudscontract.** Dit is een persoonlijk project zonder garanties. Bij wijzigingen in wet- of regelgeving (bijvoorbeeld de DBA-handhaving) kan de tool verouderen.

## Verschil met het origineel

De gegenereerde contracttekst komt inhoudelijk overeen met het LHV-model, met een paar bewuste afwijkingen:

1. **ANW-diensten zijn verwijderd** uit de generator. Voor ANW-afspraken verwijst de tool door naar de aparte LHV-contractgenerator voor ANW-diensten.
2. **Artikel 5 is consistent hernummerd** (5.1 t/m 5.10). Het origineel bevat een nummeringsfout (dubbel 5.5, springende nummers naar 5.9). De *inhoud* van elke bepaling is ongewijzigd overgenomen.
3. **De Belastingdienst-verklaring staat prominent bovenaan** als apart blok, in plaats van verspreid over de overwegingen. Dit is een versterking, geen wijziging.

## Aansprakelijkheid

Gebruik op eigen risico. Er wordt geen aansprakelijkheid aanvaard voor gevolgen van het gebruik van de gegenereerde contracten, onjuiste classificatie van de arbeidsrelatie, of wijzigingen in wet- en regelgeving na de laatste update.

De disclaimer in de tool zelf en de checklist-bevestigingen door de gebruiker zijn integraal onderdeel van het gebruik.

## Licentie

Open source. Vrij te gebruiken, kopiëren, aan te passen en te verbeteren — graag zelfs. Pull requests welkom.

## Contact

Voor vragen, bugs of verbetersuggesties: open een issue op GitHub.
