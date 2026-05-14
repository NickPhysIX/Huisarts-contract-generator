# Contractgenerator Waarneming Huisarts

Praktische, client-side webtool voor het maken van een `.docx`-overeenkomst voor waarneming door een huisarts, gebaseerd op de LHV-/Belastingdienst-modelovereenkomsten voor:

- **Incidentele waarneming huisarts** — Belastingdienst nr. `905-2021-82676-2-0`
- **Duurwaarneming huisarts** — Belastingdienst nr. `905-2021-82676-1-0`

De tool is bedoeld als laagdrempelige invulhulp. De tool is **geen officiële LHV-tool**, **geen Belastingdienst-tool**, en **geen juridisch of fiscaal advies**.

## Belangrijk

Modelovereenkomsten geven alleen houvast als de gekozen overeenkomst past bij de opdracht én partijen in de praktijk ook werken volgens de afspraken in de overeenkomst. Controleer daarom altijd of het gebruikte model past bij de feitelijke situatie.

Beide modelovereenkomsten zijn **geldig tot en met 31 december 2029**. De Belastingdienst beoordeelt geen nieuwe modelovereenkomsten meer; bestaande overeenkomsten kunnen tot die datum worden gebruikt. Houd er rekening mee dat deze tool na 1 januari 2030 mogelijk niet meer aansluit op een geldige modelovereenkomst.

Deze generator helpt met structureren, invullen, waarschuwen en exporteren, maar beoordeelt niet zelfstandig of sprake is van werken buiten dienstbetrekking.

De wegwijzer is daarom bewust ingericht als **advieslaag, niet als poortwachter**. Bij duidelijke signalen voor praktijkmedewerking of structurele inzet geeft de tool een stevige waarschuwing en wijst hij de officiële LHV-route als primaire keuze aan. In grijze situaties kan de waarnemer/praktijkhouder er alsnog bewust voor kiezen om door te gaan met duurwaarneming. Dat is geen goedkeuring door de tool, maar een eigen verantwoordelijkheid van de gebruiker.

## Wat doet deze tool?

De tool helpt bij:

- het kiezen tussen incidentele waarneming en duurwaarneming via een korte wegwijzer;
- het onderscheiden van:
  - korte aaneengesloten waarneming;
  - losse vooraf bepaalde dagen;
  - structurele of terugkerende inzet;
- het herkennen van situaties waarin de officiële LHV-route voor praktijkmedewerking of ANW-diensten passender lijkt;
- het invullen van opdrachtgever-, waarnemer-, datum-, tijd-, tarief- en contractgegevens;
- het tonen van model-specifieke waarschuwingen, eigen-verantwoordelijkheidsteksten en pre-downloadchecklists;
- het expliciet scheiden van **KvK-inschrijving**, **Wtza-melding** en controle van het **Landelijk Register Zorgaanbieders (LRZa)**;
- het opnemen van een extra controlepunt voor aansluiting bij een **geschillencommissie**;
- het maken van een echte `.docx`-export;
- het lokaal onthouden van optionele gegevens op het apparaat van de gebruiker.

## Wanneer gebruik je deze tool?

Deze tool is bedoeld voor situaties waarin een praktijkhouder en een waarnemend huisarts een overeenkomst van opdracht willen opstellen voor tijdelijke waarneming.

Gebruik de tool bij voorkeur als:

- de waarnemer een afwezige praktijkhouder vervangt;
- de inzet tijdelijk en afgebakend is;
- de exacte periode of losse data vooraf bekend zijn;
- partijen de overeenkomst zelf willen controleren vóór ondertekening.

## Wanneer gebruik je deze tool niet als primaire route?

Gebruik deze tool niet als primaire route voor:

- **ANW-only diensten** — gebruik daarvoor de officiële LHV-contractgenerator;
- **praktijkmedewerking** — wanneer de zzp-huisarts naast de praktijkhouder werkt om capaciteit aan te vullen;
- structurele samenwerking zonder duidelijk tijdelijk karakter;
- situaties waarin juridisch of fiscaal advies nodig is;
- situaties waarin partijen feitelijk anders gaan werken dan in de overeenkomst staat.

De tool kan bij twijfel tussen duurwaarneming en praktijkmedewerking wel een route openlaten om toch met duurwaarneming door te gaan. Dat is bedoeld voor situaties waarin de gebruiker na eigen afweging vindt dat het duurwaarnemingsmodel toch passend is. De tool genereert geen praktijkmedewerking-overeenkomst en neemt de juridische of fiscale beoordeling niet over.

## Wegwijzer

De generator start met een korte wegwijzer. Die vraagt niet alleen hoe lang de waarneming duurt, maar ook welk soort inzet het betreft.

Dat onderscheid is belangrijk:

- **Aaneengesloten periode**: bijvoorbeeld meerdere dagen achter elkaar of een verlofperiode.
- **Losse vooraf bepaalde dagen**: bijvoorbeeld drie losse vrijdagen verspreid over een kwartaal.
- **Structureel rooster**: bijvoorbeeld wekelijks terugkerende inzet zonder duidelijk tijdelijk karakter.

Een kalenderperiode van drie maanden betekent dus niet automatisch duurwaarneming als het feitelijk gaat om een beperkt aantal vooraf vastgestelde losse dagen. Andersom kan een aaneengesloten periode van meerdere weken juist wél richting duurwaarneming wijzen.

Als de antwoorden eerder richting praktijkmedewerking of structurele inzet wijzen, toont de tool een waarschuwing en maakt hij de officiële LHV-route de primaire suggestie. De tool gooit de route niet automatisch op slot: de gebruiker kan, na bewuste eigen afweging, alsnog doorgaan met duurwaarneming. Die keuze blijft volledig voor rekening van partijen.

## Wtza en LRZa

Versie 5.2 maakt expliciet onderscheid tussen:

- inschrijving in het **KvK-handelsregister**;
- melding in het kader van de **Wet toetreding zorgaanbieders (Wtza)**;
- controle van de vermelding in het **Landelijk Register Zorgaanbieders (LRZa)**.

Een KvK-inschrijving met een passende zorg-SBI-code kan ertoe leiden dat een onderneming zichtbaar wordt in het LRZa/Zorgaanbiedersportaal. Dat is niet hetzelfde als de Wtza-melding. De Wtza-melding is een aparte handeling die de waarnemer zelf moet doen.

Daarom bevat de pre-downloadchecklist een aparte bevestiging voor de Wtza-melding en LRZa-controle. De tool controleert dit niet automatisch; de gebruiker blijft zelf verantwoordelijk.

Handige bronnen:

- Zorgaanbiedersportaal — controleer je LRZa-vermelding: https://zoeken.zorgaanbiedersportaal.nl
- Toetreding zorgaanbieders — Wtza-melding doen: https://www.toetredingzorgaanbieders.nl/melden
- LHV — Wet toetreding zorgaanbieders: https://www.lhv.nl/thema/praktijkzaken/wet-toetreding-zorgaanbieders-wtza/

## Geschillencommissie

De pre-downloadchecklist bevat ook een praktische bevestiging dat de waarnemer is aangesloten bij een erkende geschillencommissie voor de behandeling van klachten en geschillen. De tool controleert dit niet automatisch; de gebruiker blijft zelf verantwoordelijk.

Gebruikelijke geschilleninstanties voor huisartsen zijn onder meer:

- SKGE — dienstverlening voor zorgverleners: https://www.skge.nl/zorgverleners/dienstverlening/
- DOKh — klachten en geschillen: https://dokh.nl/klachten-geschillen/

## Aanvullende vooraf-check

Deze contractgenerator helpt bij het maken van een passende modelovereenkomst. De feitelijke uitvoering van de opdracht blijft minstens zo belangrijk.

Voor een bredere, oriënterende vooraf-check op DBA-/schijnzelfstandigheidsrisico is er een aparte, niet-officiële werkversie beschikbaar:

https://nickphysix.github.io/Huisarts-zzp-risicoscan/

De Waarneem-Risicoscan geeft geen juridisch of fiscaal advies, geen vrijwaring en is niet verbonden aan de officiële LHV-Vergewistool.

## Lokale opslag en privacy

De tool draait volledig in de browser.

- Ingevulde contractgegevens worden niet naar een server verzonden.
- Optioneel onthouden gegevens worden alleen lokaal opgeslagen via `localStorage`.
- Opgeslagen gegevens verdwijnen als de gebruiker browsergegevens wist.
- De tool bevat geen backend, accountlaag of database.

Let op: lokale opslag is apparaat- en browsergebonden. Gebruik de tool niet op een gedeeld apparaat als dat ongewenst is.

## Technische opzet

De tool is bewust eenvoudig gehouden:

- één self-contained HTML-bestand;
- vanilla HTML, CSS en JavaScript;
- geen framework;
- geen server-side verwerking;
- geen externe scripts of CDN's;
- `.docx`-export via client-side generatie;
- consistente bestandsnamen met contracttype, `YYYYMM`, opdrachtgever en opdrachtnemer;
- geschikt voor GitHub Pages.

De keuze voor één codebase is bewust. Een aparte "simpele" incidentele variant zou extra onderhoudslast geven en verhoogt het risico dat teksten, bronverwijzingen of Belastingdienstnummers uit elkaar gaan lopen.

## Officiële bronnen

Controleer altijd de meest recente officiële informatie:

- LHV Contractgenerator: https://www.lhv.nl/product/lhv-contractgenerator/
- Belastingdienst modelovereenkomst incidentele waarneming huisarts: https://www.belastingdienst.nl/wps/wcm/connect/bldcontentnl/themaoverstijgend/brochures_en_publicaties/voorbeeldovereenkomst_huisarts_incidentele_waarneming_LHV
- Belastingdienst modelovereenkomst duurwaarneming huisarts: https://www.belastingdienst.nl/wps/wcm/connect/bldcontentnl/themaoverstijgend/brochures_en_publicaties/voorbeeldovereenkomst_duurwaarneming_huisarts
- LHV — Zzp-wetgeving in de huisartsenzorg: https://www.lhv.nl/thema/praktijkzaken/zzp-wetgeving-huisartsenzorg/
- LHV — Wtza: https://www.lhv.nl/thema/praktijkzaken/wet-toetreding-zorgaanbieders-wtza/
- Zorgaanbiedersportaal / LRZa: https://zoeken.zorgaanbiedersportaal.nl
- Toetreding zorgaanbieders / Wtza-melding: https://www.toetredingzorgaanbieders.nl/melden
- SKGE — dienstverlening voor zorgverleners: https://www.skge.nl/zorgverleners/dienstverlening/
- DOKh — klachten en geschillen: https://dokh.nl/klachten-geschillen/

## Disclaimer

Deze tool is een persoonlijk, niet-commercieel hulpmiddel. De tool is niet verbonden aan de LHV, de Belastingdienst, IGJ, CIBG of een andere officiële instantie.

Gebruik van deze tool is voor eigen verantwoordelijkheid. Laat het gegenereerde contract controleren wanneer de situatie afwijkt van standaard tijdelijke waarneming of wanneer er twijfel bestaat over arbeidsrelatie, fiscale kwalificatie, duur, verlenging, gezagsverhouding, praktijkmedewerking, ANW-diensten, Wtza-melding, LRZa-vermelding of aansluiting bij een geschillencommissie.

Doorgaan na een waarschuwing betekent alleen dat de gebruiker bewust verdergaat; het betekent niet dat de tool, de maker, de LHV, de Belastingdienst, IGJ of CIBG bevestigt dat het gekozen model passend is.

## Versie

**v5.2.4**

GitHub-polish ten opzichte van v5.2.3:

- alle externe links met `target="_blank"` in de app zijn voorzien van `rel="noopener noreferrer"` als security- en privacy-best-practice (voorkomt `window.opener`-toegang en referer-leak naar derde partijen);
- versie-aanduiding bijgewerkt in title, header, footer en code-commentaar;
- "GitHub-polish" toegevoegd aan de header-version-label;
- geen functionele wijzigingen in de tool zelf.

**v5.2.3**

Documentatie- en consistentiefix ten opzichte van v5.2.2:

- nummering van de sectie "Wat de tool toevoegt" in `ABOUT.md` rechtgetrokken (dubbele 6.);
- toelichting "Advieslaag, geen poortwachter" aangevuld met de bewuste uitzondering voor de wegwijzer-antwoorden "lang of doorlopend" en "structureel of terugkerend rooster";
- versie-aanduiding bijgewerkt;
- geen functionele wijzigingen in de tool zelf.

**v5.2.2**

Checklist-update ten opzichte van v5.2.1:

- voegt aan de pre-downloadchecklist voor zowel incidentele waarneming als duurwaarneming een expliciet controlepunt toe voor aansluiting bij een erkende geschillencommissie;
- noemt SKGE en DOKh als gebruikelijke geschilleninstanties voor huisartsen;
- werkt versie-aanduiding en documentatie bij.

**v5.2.1**

Hotfix ten opzichte van v5.2:

- voorkomt dat een leeg optioneel tijdenveld in duurwaarneming als `[tijden]` of `([tijden])` in de preview of het gegenereerde contract verschijnt;
- verduidelijkt het veld **Tijden / spreekuurblokken** bij duurwaarneming als optioneel;
- maakt de bestandsnamen consistenter: `overeenkomst_incidentele_waarneming_YYYYMM_opdrachtgever_opdrachtnemer.docx` en `overeenkomst_duurwaarneming_YYYYMM_opdrachtgever_opdrachtnemer.docx`;
- gebruikt voor `YYYYMM` de startdatum van de waarneming wanneer beschikbaar, met de huidige maand als fallback.

### v5.2

Belangrijkste wijzigingen ten opzichte van v5.1.1:

- Wtza-melding expliciet gescheiden van KvK-inschrijving;
- zowel incidentele waarneming als duurwaarneming vragen expliciet: “Ik heb mij gemeld bij de IGJ in het kader van de Wtza en mijn status in het Landelijk Register Zorgaanbieders (LRZa) gecontroleerd.”;
- LRZa/Zorgaanbiedersportaal toegevoegd aan toelichting en checklist;
- pre-downloadchecklist uitgebreid met Wtza/LRZa-controle;
- README/ABOUT bijgewerkt op de v5.2-positionering.

Belangrijkste wijzigingen ten opzichte van v5.0/v5.1:

- wizardtekst aangescherpt van "Aanbeveling" naar "Waarschijnlijk passend model";
- extra stap **type inzet** toegevoegd;
- onderscheid tussen aaneengesloten periode, losse vooraf bepaalde dagen en structureel rooster;
- hergebruik van eerder gekozen contracttype aangepast: geen automatische restore zonder bevestiging;
- bij grijze routes tussen duurwaarneming en praktijkmedewerking: waarschuwing en eigen-verantwoordelijkheid, maar geen automatische blokkade;
- aparte bevestiging bij incidenteel gebruik na >7 dagen-waarschuwing.
