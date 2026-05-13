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

## Wtza-meldplicht en het LRZa

Beide modelovereenkomsten bevatten een verklaring dat de waarnemer is ingeschreven in het Landelijk Register Zorgaanbieders (LRZa). Een veelvoorkomend misverstand is dat deze inschrijving automatisch tot stand komt bij een KvK-inschrijving. Dat is te kort door de bocht:

- Een KvK-inschrijving met een passende **zorg-SBI-code** kan ertoe leiden dat de onderneming zichtbaar wordt op [zoeken.zorgaanbiedersportaal.nl](https://zoeken.zorgaanbiedersportaal.nl). De status is dan echter "nog niet gemeld".
- Zichtbaarheid in het LRZa is **niet hetzelfde** als de Wtza-melding. De Wtza-melding bij de IGJ is een aparte, actieve handeling die de waarnemer zelf moet doen via [toetredingzorgaanbieders.nl/melden](https://www.toetredingzorgaanbieders.nl/melden), uiterlijk drie maanden vóór de start van de zorg.

De pre-download checklist in v5.2 splitst deze twee verklaringen daarom in twee aparte vinkjes, en biedt directe links naar het zorgaanbiedersportaal (om de eigen vermelding te checken) en het meldportaal van de IGJ.

De meldplicht geldt voor alle waarnemend huisartsen die vanuit een eigen onderneming werken — zowel bij incidentele waarneming als bij duurwaarneming. Alleen huisartsen volledig in loondienst zijn uitgezonderd.

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
- geschikt voor GitHub Pages.

De keuze voor één codebase is bewust. Een aparte "simpele" incidentele variant zou extra onderhoudslast geven en verhoogt het risico dat teksten, bronverwijzingen of Belastingdienstnummers uit elkaar gaan lopen.

## Officiële bronnen

Controleer altijd de meest recente officiële informatie:

- LHV Contractgenerator: https://www.lhv.nl/product/lhv-contractgenerator/
- Belastingdienst modelovereenkomst incidentele waarneming huisarts: https://www.belastingdienst.nl/wps/wcm/connect/bldcontentnl/themaoverstijgend/brochures_en_publicaties/voorbeeldovereenkomst_huisarts_incidentele_waarneming_LHV
- Belastingdienst modelovereenkomst duurwaarneming huisarts: https://www.belastingdienst.nl/wps/wcm/connect/bldcontentnl/themaoverstijgend/brochures_en_publicaties/voorbeeldovereenkomst_duurwaarneming_huisarts
- LHV — Zzp-wetgeving in de huisartsenzorg: https://www.lhv.nl/thema/praktijkzaken/zzp-wetgeving-huisartsenzorg/
- LHV — Wet toetreding zorgaanbieders (Wtza): https://www.lhv.nl/thema/praktijkzaken/wet-toetreding-zorgaanbieders-wtza/
- Zorgaanbiedersportaal (LRZa): https://zoeken.zorgaanbiedersportaal.nl
- Toetredingzorgaanbieders.nl (Wtza-melding bij IGJ): https://www.toetredingzorgaanbieders.nl/melden

## Disclaimer

Deze tool is een persoonlijk, niet-commercieel hulpmiddel. De tool is niet verbonden aan de LHV, de Belastingdienst, de IGJ of een andere officiële instantie.

Gebruik van deze tool is voor eigen verantwoordelijkheid. Laat het gegenereerde contract controleren wanneer de situatie afwijkt van standaard tijdelijke waarneming of wanneer er twijfel bestaat over arbeidsrelatie, fiscale kwalificatie, duur, verlenging, gezagsverhouding, praktijkmedewerking of ANW-diensten.

Doorgaan na een waarschuwing betekent alleen dat de gebruiker bewust verdergaat; het betekent niet dat de tool, de maker, de LHV of de Belastingdienst bevestigt dat het gekozen model passend is.

## Versie

**v5.2**

Belangrijkste wijzigingen ten opzichte van v5.1.1:

- pre-download checklist splitst KvK-inschrijving en Wtza-melding/LRZa-status in twee aparte vinkjes;
- de Wtza-meldplicht (chk4) is nu ook opgenomen in de checklist voor **incidentele** waarneming (in v5.1.1 stond deze alleen bij duurwaarneming);
- directe links bij het Wtza-vinkje naar [zoeken.zorgaanbiedersportaal.nl](https://zoeken.zorgaanbiedersportaal.nl) (eigen vermelding controleren) en [toetredingzorgaanbieders.nl/melden](https://www.toetredingzorgaanbieders.nl/melden) (Wtza-melding doen);
- bronnen-modal uitgebreid met een aparte sectie "Wtza & Landelijk Register Zorgaanbieders";
- README en ABOUT bijgewerkt met een toelichting op het verschil tussen KvK-inschrijving en Wtza-melding;
- contracttekst zelf (clausules 5.7 duurwaarneming / 5.8 incidenteel) is **niet** gewijzigd; de Belastingdienst-beoordeelde bepalingen blijven ongewijzigd overgenomen.

### v5.1.1

- wizardtekst aangescherpt van "Aanbeveling" naar "Waarschijnlijk passend model";
- nieuwe wegwijzerstap voor type inzet (aaneengesloten / losse dagen / structureel);
- onderscheid tussen aaneengesloten periode en losse vooraf bepaalde dagen, inclusief gerichte waarschuwingen;
- geen automatische terugkeer naar eerder gekozen contracttype zonder bevestiging;
- README en ABOUT afgestemd op de gecombineerde incidenteel/duurwaarneming-flow;
- waarschuwingen bij twijfel tussen duurwaarneming en praktijkmedewerking zijn adviserend gemaakt: de officiële LHV-route blijft de primaire suggestie, maar bewust doorgaan met duurwaarneming kan op eigen verantwoordelijkheid.
