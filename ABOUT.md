# Over deze tool

**Contractgenerator Waarneming Huisarts** is een praktische browsertool voor het opstellen van een `.docx`-overeenkomst voor waarneming door een huisarts.

De tool ondersteunt twee LHV-/Belastingdienst-modelovereenkomsten:

- **incidentele waarneming huisarts** — Belastingdienst nr. `905-2021-82676-2-0`;
- **duurwaarneming huisarts** — Belastingdienst nr. `905-2021-82676-1-0`.

De tool is bedoeld als invulhulp en beslisondersteunende wegwijzer, niet als juridisch of fiscaal oordeel. De wegwijzer adviseert en waarschuwt, maar neemt de uiteindelijke keuze voor het contracttype niet over.

## Waarom deze tool bestaat

Dit project is ontstaan uit een praktische vraag: bij elke waarneming moet opnieuw een contract worden opgesteld op basis van het LHV-model, met handmatig kopiëren, plakken en invullen. Dat kon efficiënter, mits de inhoud juridisch herkenbaar en controleerbaar bleef.

De officiële modelovereenkomsten zijn nuttig, maar in de praktijk wil je snel en zorgvuldig kunnen bepalen welk model waarschijnlijk past, welke gegevens nodig zijn en waar de grenzen zitten.

Deze tool probeert die praktische laag toe te voegen:

- eerst nadenken over het type inzet;
- daarna pas invullen;
- waarschuwingen tonen bij risicovolle situaties, zonder elke grijze route automatisch op slot te zetten;
- een bruikbaar `.docx`-contract genereren;
- geen gegevens naar een server sturen.

De tool werkt in principe voor iedere huisarts die met de LHV-modellen voor incidentele waarneming of duurwaarneming werkt.

## Wie heeft dit gebouwd?

Ontwikkeld door **Niels Braakman** als persoonlijk project.

- Geen affiliatie met de LHV, de Belastingdienst of enige andere organisatie
- Niet-commercieel, gratis te gebruiken, open source

## Hoe is het gebouwd?

Dit project is een experiment in **multi-AI samenwerking**. Het bouwproces bestond uit meerdere iteraties waarbij verschillende LLM-modellen zijn gebruikt voor het bouwen van de tool en feedback geven op het resultaat.

- **Claude (Anthropic)** — architectuur, formulierlogica, juridische structuur, iteratieve bugfixes, mobiele UX, iOS Share Sheet integratie, PWA-setup, en de uitbreiding naar duurwaarneming inclusief wegwijzer en type-inzet-flow. Vanaf v5.2 ook de Wtza-/LRZa-aanscherping in de pre-download checklist.
- **ChatGPT (OpenAI)** — meerdere rondes van red-teaming en juridische review, concrete punchlists voor verbeteringen, de native `.docx`-export-engine (OOXML-generatie zonder externe libraries), en finetuning van de v5.1/v5.1.1 wijzigingen (toonzetting wegwijzer, type inzet, bevestigingsdialoog bij hergebruik, en eigen-verantwoordelijkheid bij grijze routes).
- **Gemini (Google)** — privacy-review en UX-suggesties.

De resulterende tool is stap voor stap verbeterd tot een stabiele versie. De eindregie — welke suggesties wel of niet zijn doorgevoerd, de inhoudelijke afwegingen en deployment — lag bij mij.

## Wat de tool toevoegt

De tool voegt bovenop de modelovereenkomsten een gebruikslaag toe:

1. **Wegwijzer vooraf**  
   De gebruiker beantwoordt eerst enkele vragen over duur, type inzet, vaste einddatum, verlenging en of de waarnemer vervangt of naast de praktijkhouder werkt.

2. **Onderscheid tussen inzetpatronen**  
   De tool maakt onderscheid tussen:
   - korte aaneengesloten waarneming;
   - losse vooraf bepaalde dagen;
   - structurele of terugkerende inzet.

3. **Model-specifieke waarschuwingen**  
   Bij signalen voor duurwaarneming, praktijkmedewerking, structurele inzet of ANW-only situaties waarschuwt de tool expliciet en wijst hij de officiële LHV-route aan waar dat passender lijkt. Bij twijfelroutes kan de gebruiker alsnog bewust doorgaan met duurwaarneming op eigen verantwoordelijkheid.

4. **Pre-downloadchecklist met expliciete Wtza-check (v5.2)**  
   De gebruiker moet expliciet bevestigen dat de belangrijkste randvoorwaarden zijn gecontroleerd vóór het contract wordt gedownload. Vanaf v5.2 zijn KvK-inschrijving en Wtza-melding (LRZa-status "gemeld") in twee aparte vinkjes opgesplitst, met directe links naar het zorgaanbiedersportaal en het meldportaal van de IGJ.

5. **Client-side `.docx`-export**  
   Het contract wordt lokaal in de browser gegenereerd als Word-document, zonder externe libraries.

6. **Bewuste hergebruik-bevestiging**  
   Bij hergebruik van de tool wordt het eerder gekozen contracttype niet automatisch toegepast: de gebruiker bevestigt expliciet of de wegwijzer opnieuw moet worden doorlopen.

## Wat doet de tool wél?

- Genereert een contracttekst die inhoudelijk overeenkomt met de LHV-modelovereenkomsten voor incidentele waarneming en duurwaarneming.
- Neemt de door de Belastingdienst gemarkeerde bepalingen **ongewijzigd** over, inclusief gele markering in de output.
- Bevat de officiële verwijzing naar de Belastingdienst-kenmerknummers.
- Valideert de duur (waarschuwing bij `>7 dagen` voor incidenteel, blokkade bij `>30 dagen`) om oneigenlijk gebruik van het incidentele model te voorkomen.
- Splitst ANW-only afspraken expliciet af naar het aparte LHV-contracttype.
- Verplicht een pre-download checklist waarin de gebruiker bevestigt dat de feitelijke situatie past bij het gekozen model.
- **Wijst er expliciet op dat KvK-inschrijving en de Wtza-melding twee verschillende stappen zijn** (vanaf v5.2), en biedt directe links naar het zorgaanbiedersportaal en het IGJ-meldportaal.
- Laat bij grijze routes tussen duurwaarneming en praktijkmedewerking bewust doorgaan toe, maar alleen met duidelijke waarschuwing dat de keuze voor rekening van partijen blijft.
- Draait volledig client-side: ingevulde contractgegevens worden niet naar een server verstuurd.

## Wat doet de tool niet?

- **Geen juridisch advies.** De tool genereert een contracttekst, maar beoordeelt niet of de feitelijke arbeidsrelatie kwalificeert als overeenkomst van opdracht (DBA-proof).
- **Geen garantie op Belastingdienst-conformiteit.** De uiteindelijke kwalificatie hangt af van feitelijke uitvoering, niet alleen van de contracttekst.
- **Geen controle of de Wtza-melding ook daadwerkelijk is gedaan.** De tool wijst de gebruiker erop en biedt links, maar de melding zelf gebeurt buiten de tool. De gebruiker is zelf verantwoordelijk voor naleving van de meldplicht.
- **Geen vervanging van de officiële LHV-contractgenerator.** Voor praktijkmedewerking en ANW-only afspraken verwijst de tool naar de LHV-route.
- **Geen onderhoudscontract.** Dit is een persoonlijk project zonder garanties. Bij wijzigingen in wet- en regelgeving kan de tool verouderen. De huidige modelovereenkomsten zijn geldig tot en met 31 december 2029.

## Incidentele waarneming, duurwaarneming en praktijkmedewerking

De kern van de tool is dat niet elke tijdelijke inzet hetzelfde is.

Een korte inzet van één of enkele dagen kan passen bij incidentele waarneming. Een beperkt aantal vooraf vastgestelde losse dagen kan ook incidenteel blijven, ook als de eerste en laatste datum verder uit elkaar liggen.

Een aaneengesloten periode van meerdere weken of maanden wijst eerder richting duurwaarneming, mits er een duidelijk tijdelijk karakter en een afgebakend einde is.

Werkt de zzp-huisarts niet in plaats van de praktijkhouder, maar naast de praktijkhouder om capaciteit aan te vullen, dan is praktijkmedewerking waarschijnlijk passender. Daarvoor verwijst de tool naar de officiële LHV-route. In twijfelgevallen blokkeert de tool de gebruiker niet volledig: de gebruiker kan, na bewuste eigen afweging, alsnog doorgaan met duurwaarneming. Dat is nadrukkelijk geen juridische of fiscale bevestiging dat duurwaarneming passend is.

## ANW-diensten

Voor avond-, nacht- en weekenddiensten bestaat een aparte LHV-route. Deze tool behandelt ANW-diensten alleen beperkt binnen de context van duurwaarneming, voor zover dat past bij het gekozen model. Voor ANW-only afspraken moet de officiële LHV-contractgenerator worden gebruikt.

## Wtza-meldplicht en het Landelijk Register Zorgaanbieders

Beide modelovereenkomsten bevatten een verklaring dat de waarnemer is ingeschreven in het Landelijk Register Zorgaanbieders (LRZa). Praktijkervaring leert dat hier een hardnekkig misverstand omheen leeft: dat de inschrijving automatisch ontstaat bij het aanmaken van een KvK-inschrijving.

Dat is te kort door de bocht:

- Een KvK-inschrijving met een passende zorg-SBI-code kan ertoe leiden dat de onderneming *zichtbaar* wordt op [zoeken.zorgaanbiedersportaal.nl](https://zoeken.zorgaanbiedersportaal.nl). De status is dan echter "nog niet gemeld".
- Zichtbaarheid in het LRZa is **niet hetzelfde** als de Wtza-melding. De Wtza-melding bij de IGJ is een aparte, actieve handeling. Deze moet de waarnemer zelf doen via [toetredingzorgaanbieders.nl/melden](https://www.toetredingzorgaanbieders.nl/melden), uiterlijk drie maanden vóór de start van de zorg.

De meldplicht onder de Wet toetreding zorgaanbieders (Wtza) geldt voor alle waarnemend huisartsen die vanuit een eigen onderneming werken — zowel bij incidentele waarneming als bij duurwaarneming. Alleen huisartsen volledig in loondienst zijn uitgezonderd. Niet melden kan leiden tot een bestuurlijke boete; het IGJ-boetebeleid begint in de praktijk met een schriftelijke waarschuwing.

Vanaf **v5.2** splitst de pre-download checklist deze twee verklaringen daarom op in twee aparte vinkjes (KvK-inschrijving en Wtza-melding/LRZa-status), met directe links naar het zorgaanbiedersportaal (om de eigen vermelding te controleren) en naar het IGJ-meldportaal (om de melding alsnog te doen). De contracttekst zelf is **niet** gewijzigd: de Belastingdienst-beoordeelde bepalingen blijven ongewijzigd overgenomen.

## Verschillen met het origineel

De gegenereerde contracttekst komt inhoudelijk overeen met de LHV-modelovereenkomsten, met een paar bewuste afwijkingen of technische keuzes:

1. **De Belastingdienst-verklaring staat prominent bovenaan** als apart blok, in plaats van verspreid over de overwegingen.
2. **Artikel 5 is consistent hernummerd** in de incidentele variant. Het origineel bevat een nummeringsfout; de inhoud van de bepalingen is niet aangepast.
3. **ANW-only afspraken** maken geen onderdeel uit van deze generator. Voor ANW-only contracten verwijst de tool door naar de LHV-route. Binnen duurwaarneming kunnen ANW-diensten wel beperkt worden opgenomen.
4. **Praktijkmedewerking** wordt niet als contracttype gegenereerd — de tool verwijst naar de LHV-contractgenerator wanneer de wegwijzer aangeeft dat dit waarschijnlijk het passende model is. In grijze routes kan de gebruiker toch doorgaan met duurwaarneming op eigen verantwoordelijkheid.
5. **De export is een echte `.docx`** in plaats van een HTML-als-`.doc` workaround. De OOXML-structuur wordt client-side opgebouwd zonder externe libraries.

## Privacy

De tool is local-first ontworpen.

- Er is geen serververwerking.
- Er is geen account nodig.
- Er is geen database.
- Ingevulde contractgegevens blijven op het apparaat van de gebruiker.
- Optioneel onthouden gegevens worden opgeslagen in de browser via `localStorage`.
- Er wordt geen tracking, analytics of telemetrie ingeladen.

Gebruikers kunnen opgeslagen gegevens wissen via de tool of via de browserinstellingen.

## Onderhoudsfilosofie

De tool gebruikt bewust één gecombineerde codebase voor incidentele waarneming en duurwaarneming. Dat beperkt het risico dat meerdere varianten inhoudelijk uit elkaar gaan lopen.

Een aparte "lichte" incidentele variant klinkt aantrekkelijk, maar zou betekenen:

- twee HTML-bestanden;
- twee README/ABOUT-verhalen;
- dubbele bronverwijzingen;
- dubbele onderhoudslast;
- groter risico op verouderde Belastingdienst- of LHV-tekst.

De betere oplossing is dat de gecombineerde tool voor eenvoudige incidentele waarneming nog steeds snel en licht voelt.

## Advieslaag, geen poortwachter

Een bewuste ontwerpkeuze in v5.1.1 is dat de tool bij twijfel tussen duurwaarneming en praktijkmedewerking niet automatisch alles blokkeert.

De tool doet dan drie dingen:

1. duidelijk waarschuwen dat praktijkmedewerking of de officiële LHV-route waarschijnlijk passender is;
2. de LHV-route als primaire keuze aanbieden;
3. toch een secundaire route openlaten om met duurwaarneming door te gaan, als de gebruiker daar na eigen afweging voor kiest.

Dit past bij het karakter van de tool: ondersteunen, structureren en waarschuwen, maar niet namens partijen beslissen. De tool blijft géén praktijkmedewerking-overeenkomst genereren.

Dezelfde filosofie geldt voor de Wtza-melding in v5.2: de tool verplicht het vinkje "gemeld bij IGJ / LRZa-status gemeld" om af te ronden, maar controleert de daadwerkelijke melding niet. De gebruiker bevestigt op eigen verantwoordelijkheid en de tool maakt de stap zo eenvoudig mogelijk door de juiste links direct aan te bieden.

## Aansprakelijkheid

**Gebruik op eigen risico.** Er wordt geen aansprakelijkheid aanvaard voor gevolgen van het gebruik van de gegenereerde contracten, onjuiste classificatie van de arbeidsrelatie, onjuiste invoer door de gebruiker of wijzigingen in wet- en regelgeving na de laatste update.

De uiteindelijke verantwoordelijkheid voor controle, passend gebruik en ondertekening blijft bij de gebruiker.

## Bronnen

De tool verwijst naar en is inhoudelijk geïnspireerd door:

- de LHV-contractgenerator;
- de Belastingdienst-modelovereenkomst incidentele waarneming huisarts (nr. 905-2021-82676-2-0);
- de Belastingdienst-modelovereenkomst duurwaarneming huisarts (nr. 905-2021-82676-1-0);
- algemene Belastingdienstinformatie over modelovereenkomsten;
- LHV-informatie over de Wet toetreding zorgaanbieders (Wtza);
- het zorgaanbiedersportaal en het IGJ-meldportaal voor het Landelijk Register Zorgaanbieders (LRZa).

Gebruikers moeten altijd de actuele officiële bronnen raadplegen voordat zij op de tekst vertrouwen.

## Licentie

Open source. Vrij te gebruiken, kopiëren, aan te passen en te verbeteren.

## Contact

Voor vragen, bugs of verbetersuggesties: open een issue op GitHub.
