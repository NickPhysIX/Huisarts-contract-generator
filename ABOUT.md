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
- expliciet laten controleren dat KvK, Wtza-melding en LRZa-vermelding niet door elkaar worden gehaald;
- een bruikbaar `.docx`-contract genereren;
- geen gegevens naar een server sturen.

De tool werkt in principe voor iedere huisarts die met de LHV-modellen voor incidentele waarneming of duurwaarneming werkt.

## Wie heeft dit gebouwd?

Ontwikkeld door **Niels Braakman** als persoonlijk project.

- Geen affiliatie met de LHV, de Belastingdienst, IGJ, CIBG of enige andere organisatie
- Niet-commercieel, gratis te gebruiken, open source

## Hoe is het gebouwd?

Dit project is een experiment in **multi-AI samenwerking**. Het bouwproces bestond uit meerdere iteraties waarbij verschillende LLM-modellen zijn gebruikt voor het bouwen van de tool en feedback geven op het resultaat.

- **Claude (Anthropic)** — architectuur, formulierlogica, juridische structuur, iteratieve bugfixes, mobiele UX, iOS Share Sheet integratie, PWA-setup, en de uitbreiding naar duurwaarneming inclusief wegwijzer en type-inzet-flow.
- **ChatGPT (OpenAI)** — meerdere rondes van red-teaming en juridische review, concrete punchlists voor verbeteringen, de native `.docx`-export-engine (OOXML-generatie zonder externe libraries), finetuning van de v5.1/v5.1.1 wijzigingen, documentatie/positionering voor de v5.2 Wtza/LRZa-aanscherping, de geschillencommissie-check (v5.2.2) en de v5.2.4 GitHub-polish (`rel="noopener noreferrer"`-hardening).
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

4. **Pre-downloadchecklist**  
   De gebruiker moet expliciet bevestigen dat de belangrijkste randvoorwaarden zijn gecontroleerd vóór het contract wordt gedownload.

5. **Wtza/LRZa-controlepunt**  
   Versie 5.2 voegt een expliciete checklistregel toe voor Wtza-melding en controle van de LRZa-vermelding, naast KvK-inschrijving.

6. **Geschillencommissie-controlepunt**  
   Versie 5.2.2 voegt een aparte checklistregel toe voor aansluiting bij een erkende geschillencommissie, met SKGE en DOKh als gebruikelijke voorbeelden voor huisartsen.

7. **Client-side `.docx`-export**  
   Het contract wordt lokaal in de browser gegenereerd als Word-document, zonder externe libraries.

8. **Bewuste hergebruik-bevestiging**  
   Bij hergebruik van de tool wordt het eerder gekozen contracttype niet automatisch toegepast: de gebruiker bevestigt expliciet of de wegwijzer opnieuw moet worden doorlopen.

## Wat doet de tool wél?

- Genereert een contracttekst die inhoudelijk overeenkomt met de LHV-modelovereenkomsten voor incidentele waarneming en duurwaarneming.
- Neemt de door de Belastingdienst gemarkeerde bepalingen **ongewijzigd** over, inclusief gele markering in de output.
- Bevat de officiële verwijzing naar de Belastingdienst-kenmerknummers.
- Valideert de duur (waarschuwing bij `>7 dagen` voor incidenteel, blokkade bij `>30 dagen`) om oneigenlijk gebruik van het incidentele model te voorkomen.
- Splitst ANW-only afspraken expliciet af naar het aparte LHV-contracttype.
- Verplicht een pre-download checklist waarin de gebruiker bevestigt dat de feitelijke situatie past bij het gekozen model.
- Laat bij grijze routes tussen duurwaarneming en praktijkmedewerking bewust doorgaan toe, maar alleen met duidelijke waarschuwing dat de keuze voor rekening van partijen blijft.
- Maakt expliciet onderscheid tussen KvK-inschrijving, Wtza-melding en LRZa-controle.
- Bevat een apart controlepunt voor aansluiting bij een geschillencommissie.
- Draait volledig client-side: ingevulde contractgegevens worden niet naar een server verstuurd.

## Wat doet de tool niet?

- **Geen juridisch advies.** De tool genereert een contracttekst, maar beoordeelt niet of de feitelijke arbeidsrelatie kwalificeert als overeenkomst van opdracht (DBA-proof).
- **Geen fiscaal advies.** De tool geeft geen oordeel over loonheffingen, ondernemerschap of fiscale kwalificatie.
- **Geen garantie op Belastingdienst-conformiteit.** De uiteindelijke kwalificatie hangt af van feitelijke uitvoering, niet alleen van de contracttekst.
- **Geen Wtza- of LRZa-check namens de gebruiker.** De tool verwijst en herinnert, maar controleert geen registratie of melding automatisch.
- **Geen controle op aansluiting bij een geschillencommissie namens de gebruiker.** De tool verwijst en herinnert, maar verifieert geen aansluiting automatisch.
- **Geen vervanging van de officiële LHV-contractgenerator.** Voor praktijkmedewerking en ANW-only afspraken verwijst de tool naar de LHV-route.
- **Geen onderhoudscontract.** Dit is een persoonlijk project zonder garanties. Bij wijzigingen in wet- en regelgeving kan de tool verouderen. De huidige modelovereenkomsten zijn geldig tot en met 31 december 2029.

## Incidentele waarneming, duurwaarneming en praktijkmedewerking

De kern van de tool is dat niet elke tijdelijke inzet hetzelfde is.

Een korte inzet van één of enkele dagen kan passen bij incidentele waarneming. Een beperkt aantal vooraf vastgestelde losse dagen kan ook incidenteel blijven, ook als de eerste en laatste datum verder uit elkaar liggen.

Een aaneengesloten periode van meerdere weken of maanden wijst eerder richting duurwaarneming, mits er een duidelijk tijdelijk karakter en een afgebakend einde is.

Werkt de zzp-huisarts niet in plaats van de praktijkhouder, maar naast de praktijkhouder om capaciteit aan te vullen, dan is praktijkmedewerking waarschijnlijk passender. Daarvoor verwijst de tool naar de officiële LHV-route. In twijfelgevallen blokkeert de tool de gebruiker niet volledig: de gebruiker kan, na bewuste eigen afweging, alsnog doorgaan met duurwaarneming. Dat is nadrukkelijk geen juridische of fiscale bevestiging dat duurwaarneming passend is.

## ANW-diensten

Voor avond-, nacht- en weekenddiensten bestaat een aparte LHV-route. Deze tool behandelt ANW-diensten alleen beperkt binnen de context van duurwaarneming, voor zover dat past bij het gekozen model. Voor ANW-only afspraken moet de officiële LHV-contractgenerator worden gebruikt.

## Wtza, LRZa en KvK

Versie 5.2 voegt een expliciete Wtza/LRZa-laag toe aan de toelichting en pre-downloadchecklist.

De tool maakt daarbij bewust onderscheid tussen drie dingen:

1. **KvK-inschrijving**  
   De waarnemer verklaart dat hij/zij staat ingeschreven in het handelsregister.

2. **LRZa/Zorgaanbiedersportaal**  
   Een KvK-inschrijving met passende zorg-SBI-code kan ertoe leiden dat een onderneming zichtbaar wordt in het LRZa/Zorgaanbiedersportaal. Dat is nuttig om te controleren, maar het is niet hetzelfde als een Wtza-melding.

3. **Wtza-melding**  
   De Wtza-melding is een aparte handeling die de waarnemer zelf moet doen. De tool kan dit niet controleren en geeft geen bevestiging dat aan Wtza-verplichtingen is voldaan.

De pre-downloadchecklist bevat daarom bij zowel incidentele waarneming als duurwaarneming een aparte bevestiging dat de gebruiker zich heeft gemeld bij de IGJ in het kader van de Wtza en de LRZa-vermelding heeft gecontroleerd. Dit is een bewust controlepunt, geen automatische verificatie.

## Geschillencommissie

Versie 5.2.2 voegt ook een expliciet controlepunt toe voor aansluiting bij een erkende geschillencommissie. Dit past naast de Wtza/LRZa-laag als praktische vooraf-check: het is geen DBA-beoordeling, maar wel een afzonderlijk compliance-risico.

De tool noemt SKGE en DOKh als gebruikelijke voorbeelden voor huisartsen:

- SKGE — https://www.skge.nl/zorgverleners/dienstverlening/
- DOKh — https://dokh.nl/klachten-geschillen/

Ook hier geldt: de tool controleert dit niet automatisch. De gebruiker blijft zelf verantwoordelijk voor de daadwerkelijke aansluiting en actuele toepasselijkheid.

## Aanvullende vooraf-check: Waarneem-Risicoscan

Deze contractgenerator helpt bij het maken van een passende modelovereenkomst. De feitelijke uitvoering van de opdracht blijft minstens zo belangrijk.

Voor een bredere, oriënterende vooraf-check op DBA-/schijnzelfstandigheidsrisico is er een aparte, niet-officiële werkversie beschikbaar:

https://nickphysix.github.io/Huisarts-zzp-risicoscan/

De Waarneem-Risicoscan geeft geen juridisch of fiscaal advies, geen vrijwaring en is niet verbonden aan de officiële LHV-Vergewistool.

## Verschillen met het origineel

De gegenereerde contracttekst komt inhoudelijk overeen met de LHV-modelovereenkomsten, met een paar bewuste afwijkingen of technische keuzes:

1. **De Belastingdienst-verklaring staat prominent bovenaan** als apart blok, in plaats van verspreid over de overwegingen.
2. **Artikel 5 is consistent hernummerd** in de incidentele variant. Het origineel bevat een nummeringsfout; de inhoud van de bepalingen is niet aangepast.
3. **ANW-only afspraken** maken geen onderdeel uit van deze generator. Voor ANW-only contracten verwijst de tool door naar de LHV-route. Binnen duurwaarneming kunnen ANW-diensten wel beperkt worden opgenomen.
4. **Praktijkmedewerking** wordt niet als contracttype gegenereerd — de tool verwijst naar de LHV-contractgenerator wanneer de wegwijzer aangeeft dat dit waarschijnlijk het passende model is. In grijze routes kan de gebruiker toch doorgaan met duurwaarneming op eigen verantwoordelijkheid.
5. **Wtza/LRZa** zijn toegevoegd als praktische controlepunten in toelichting en checklist. De contracttekst zelf wordt daardoor niet omgevormd tot een Wtza- of registratiebeoordeling.
6. **Geschillencommissie-aansluiting** is toegevoegd als apart praktisch controlepunt in de pre-downloadchecklist. De contracttekst zelf wordt daardoor niet omgevormd tot een klachten- of geschillenreglement.
7. **De export is een echte `.docx`** in plaats van een HTML-als-`.doc` workaround. De OOXML-structuur wordt client-side opgebouwd zonder externe libraries.
8. **Bestandsnamen zijn gestandaardiseerd** zodat incidentele waarneming en duurwaarneming hetzelfde patroon gebruiken, inclusief `YYYYMM` op basis van de startdatum wanneer beschikbaar.

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

Een bewuste ontwerpkeuze sinds v5.1.1 is dat de tool bij twijfel tussen duurwaarneming en praktijkmedewerking niet automatisch alles blokkeert.

De tool doet dan drie dingen:

1. duidelijk waarschuwen dat praktijkmedewerking of de officiële LHV-route waarschijnlijk passender is;
2. de LHV-route als primaire keuze aanbieden;
3. toch een secundaire route openlaten om met duurwaarneming door te gaan, als de gebruiker daar na eigen afweging voor kiest.

Dit past bij het karakter van de tool: ondersteunen, structureren en waarschuwen, maar niet namens partijen beslissen. De tool blijft géén praktijkmedewerking-overeenkomst genereren.

Er is één bewuste uitzondering op deze advieslaag-aanpak. Wanneer de gebruiker in de wegwijzer kiest voor **lang of doorlopend** (stap 1) of voor een **structureel of terugkerend rooster** (stap 2), biedt de tool géén secundaire route naar duurwaarneming aan. Deze antwoorden bevestigen feitelijk dat het geen tijdelijke waarneming is. Een grijze-routeknop zou hier de boodschap ondergraven. De gebruiker kan wel de wegwijzer opnieuw beginnen wanneer een antwoord onbedoeld is gegeven.

## Aansprakelijkheid

**Gebruik op eigen risico.** Er wordt geen aansprakelijkheid aanvaard voor gevolgen van het gebruik van de gegenereerde contracten, onjuiste classificatie van de arbeidsrelatie, onjuiste invoer door de gebruiker, onjuiste of ontbrekende Wtza-melding/LRZa-controle, ontbrekende of onjuiste aansluiting bij een geschillencommissie, of wijzigingen in wet- en regelgeving na de laatste update.

De uiteindelijke verantwoordelijkheid voor controle, passend gebruik en ondertekening blijft bij de gebruiker.

## Bronnen

De tool verwijst naar en is inhoudelijk geïnspireerd door:

- de LHV-contractgenerator;
- de Belastingdienst-modelovereenkomst incidentele waarneming huisarts (nr. 905-2021-82676-2-0);
- de Belastingdienst-modelovereenkomst duurwaarneming huisarts (nr. 905-2021-82676-1-0);
- algemene Belastingdienstinformatie over modelovereenkomsten;
- LHV-informatie over zzp-wetgeving en Wtza;
- het Zorgaanbiedersportaal/LRZa;
- Toetredingzorgaanbieders.nl voor de Wtza-melding;
- SKGE en DOKh als voorbeelden van geschilleninstanties voor huisartsen.

Gebruikers moeten altijd de actuele officiële bronnen raadplegen voordat zij op de tekst vertrouwen.

## Versie

**v5.2.4**

GitHub-polish ten opzichte van v5.2.3:

- alle externe links met `target="_blank"` in de app zijn voorzien van `rel="noopener noreferrer"` als security- en privacy-best-practice (voorkomt `window.opener`-toegang en referer-leak naar derde partijen);
- versie-aanduiding bijgewerkt in title, header, footer en code-commentaar;
- "GitHub-polish" toegevoegd aan de header-version-label;
- geen functionele wijzigingen in de tool zelf.

**v5.2.3**

Documentatie- en consistentiefix ten opzichte van v5.2.2:

- nummering van de sectie "Wat de tool toevoegt" rechtgetrokken (dubbele 6.);
- "Advieslaag, geen poortwachter" uitgebreid met de bewuste uitzondering voor de wegwijzer-antwoorden "lang of doorlopend" en "structureel of terugkerend rooster";
- geen functionele wijzigingen in de tool zelf.

**v5.2.2**

Checklist-update ten opzichte van v5.2.1:

- extra pre-downloadchecklistregel voor aansluiting bij een erkende geschillencommissie;
- SKGE en DOKh toegevoegd als gebruikelijke voorbeelden voor huisartsen;
- README/ABOUT en zichtbare versie-aanduiding bijgewerkt.

**v5.2.1**

Hotfix ten opzichte van v5.2:

- lege optionele tijden bij duurwaarneming worden niet meer als `[tijden]` of `([tijden])` in preview of contracttekst weergegeven;
- het duurwaarnemingveld voor tijden is verduidelijkt als optioneel veld voor tijden of spreekuurblokken;
- bestandsnamen zijn geharmoniseerd naar `overeenkomst_incidentele_waarneming_YYYYMM_opdrachtgever_opdrachtnemer.docx` en `overeenkomst_duurwaarneming_YYYYMM_opdrachtgever_opdrachtnemer.docx`;
- `YYYYMM` wordt afgeleid uit de startdatum van de overeenkomst wanneer beschikbaar, met de huidige maand als fallback.

**v5.2**

- Wtza-melding, LRZa-vermelding en KvK-inschrijving zijn expliciet uit elkaar getrokken in toelichting en pre-downloadchecklist.
- De bescheiden verwijzing naar de aparte Waarneem-Risicoscan is toegevoegd.

## Licentie

Open source. Vrij te gebruiken, kopiëren, aan te passen en te verbeteren.

## Contact

Voor vragen, bugs of verbetersuggesties: open een issue op GitHub.
