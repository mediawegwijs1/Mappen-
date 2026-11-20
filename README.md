# 🗂️ Mappenstudio

**Mappenstudio** is een interactieve oefenomgeving waarin leerlingen (en andere beginnende computergebruikers) op een veilige manier leren werken met **mappen, bestanden, downloaden en _Opslaan als…_**.

Alles gebeurt in de browser met een *gesimuleerd* bestandssysteem: er worden geen echte bestanden gedownload of opgeslagen op de computer. Zo kun je vrij oefenen zonder iets kapot te maken.

---

## 📑 Inhoud

- [Doel van het project](#-doel-van-het-project)
- [Functies](#-functies)
- [Snel aan de slag](#-snel-aan-de-slag)
- [Gebruik stap voor stap](#-gebruik-stap-voor-stap)
- [Projectstructuur](#-projectstructuur)
- [Technische werking](#-technische-werking)
- [Aanpassen](#-aanpassen)
- [Browserondersteuning](#-browserondersteuning)
- [Bekende beperkingen](#-bekende-beperkingen)
- [Ideeën voor uitbreiding](#-ideeën-voor-uitbreiding)

---

## 🎯 Doel van het project

Veel kinderen en volwassenen weten niet goed waar een gedownload bestand terechtkomt of hoe je het netjes in de juiste map zet. Mappenstudio laat dit proces stap voor stap oefenen:

1. **Een mappenstructuur bedenken en maken** (bijv. `School/Rekenen`, `Foto’s/Vakantie`).
2. **Bestanden downloaden**; deze komen altijd eerst in de map **Downloads** terecht.
3. **Bestanden opruimen met _Opslaan als…_**: een duidelijke naam geven en in de juiste map plaatsen.

Het is geschikt voor gebruik in de klas, bij mediawijsheidslessen of als zelfstandige oefening.

---

## ✨ Functies

### Stap 1: Mappenstructuur bouwen
- 📁 **Hoofdmappen toevoegen** met de knop **+ Hoofdmap**.
- ＋ **Submappen en bestanden aanmaken** in elke map via het plus-menu.
- ✏️ **Hernoemen** via de potlood-knop of door te **dubbelklikken** op een naam (Enter = bevestigen, Esc = annuleren).
- 🗑️ **Verwijderen** van mappen en bestanden (met bevestiging).
- ▼/▶︎ **Mappen openen en sluiten**, of in één keer met **Alles openen** / **Alles sluiten**.
- 🔄 **Reset structuur** zet alles terug naar een lege computer met alleen *Downloads*.
- 💾 **Auto-opslag**: elke wijziging wordt direct bewaard in de browser (`localStorage`), zodat je werk blijft staan na het verversen van de pagina.

### De beschermde map *Downloads*
- Wordt **blauw gemarkeerd** met een badge.
- Kan **niet hernoemd of verwijderd** worden.
- Wordt automatisch opnieuw aangemaakt als hij ontbreekt.
- Is de plek waar alle nieuwe downloads terechtkomen, net als op een echte computer.

### Stap 2: Downloadcentrum
Een lijst met voorbeeldbestanden die je kunt “downloaden”:

| Bestand | Type |
|---|---|
| `Rekensommen-jan.pdf` | PDF-document |
| `Toets-taal-maart.docx` | Word-document |
| `Klasfoto.png` | Afbeelding |
| `Vakantie2023-strand.jpg` | Foto |
| `Kat_Miep.png` | Afbeelding |
| `muziek-liedje.mp3` | Audio |
| `leeg-document.txt` | Tekstbestand |

- Vink één of meer bestanden aan (of gebruik **Selecteer alles** / **Niets**).
- Klik **⬇️ Download geselecteerde**; de bestanden verschijnen in *Downloads*.
- Download je hetzelfde bestand twee keer, dan krijgt het automatisch een nieuwe naam, zoals Windows en macOS dat ook doen: `Klasfoto (1).png`, `Klasfoto (2).png`, …

### *Opslaan als…*-venster
Een nagebootst *Opslaan als*-dialoogvenster:
- **Doelmap kiezen** uit een lijst met alle mappen (standaard geselecteerd: *Downloads*).
- **Bestandsnaam aanpassen**, inclusief extensie.
- **Huidig pad** wordt live getoond, bijv. `/School/Rekenen`.
- **Controle van de bestandsnaam**:
  - de naam mag niet leeg zijn;
  - er moet een extensie zijn (bijv. `.pdf`, `.docx`, `.png`);
  - de tekens `\ / : * ? " < > |` zijn niet toegestaan.
- **Conflictcontrole**: bestaat er al een bestand met dezelfde naam in de doelmap, dan wordt gevraagd of je het wilt **overschrijven**.
- **Meerdere bestanden tegelijk**: selecteer bestanden met de vinkjes en klik **💾 Opslaan als… (selectie)**. Het venster loopt ze één voor één door (teller `1/3 bestanden`).
- Het bestand wordt **verplaatst** naar de gekozen map (niet gekopieerd).

---

## 🚀 Snel aan de slag

Er is **geen installatie, server of internetverbinding** nodig.

### Optie 1: direct openen
1. Download of clone deze repository:
   ```bash
   git clone https://github.com/mediawegwijs1/Mappen-.git
   ```
2. Dubbelklik op **`mappenstructuur.html`**; het bestand opent in je standaardbrowser.

### Optie 2: via een lokale webserver (optioneel)
```bash
cd Mappen-
python3 -m http.server 8000
```
Open daarna <http://localhost:8000/mappenstructuur.html>.

### Optie 3: online publiceren met GitHub Pages
1. Ga naar **Settings → Pages** van de repository.
2. Kies bij *Source* de branch `main` en de map `/ (root)`.
3. De app is daarna bereikbaar op
   `https://mediawegwijs1.github.io/Mappen-/mappenstructuur.html`.

> 💡 Tip: hernoem `mappenstructuur.html` naar `index.html` als je wilt dat de app direct opent op de hoofd-URL.

---

## 🧭 Gebruik stap voor stap

Een voorbeeldles:

1. **Maak een structuur**
   Klik op **+ Hoofdmap** en maak bijv. `School`. Klik op **＋** naast `School` → **📁 Map aanmaken** → `Rekenen`, `Taal`.
2. **Download bestanden**
   Scroll naar *Download en verdeel je bestanden*, vink `Rekensommen-jan.pdf` en `Toets-taal-maart.docx` aan en klik **⬇️ Download geselecteerde**.
3. **Bekijk Downloads**
   Open de blauwe map *Downloads*: daar staan de nieuwe bestanden.
4. **Opslaan als…**
   Klik bij `Rekensommen-jan.pdf` op **💾 Opslaan als…**, kies `/School/Rekenen`, geef eventueel een betere naam (bijv. `Rekenen-week3.pdf`) en klik **Opslaan**.
5. **Herhaal** voor de andere bestanden, of selecteer er meerdere tegelijk.
6. **Controleer**: is *Downloads* nu leeg en staat alles in de juiste map? 🎉

**Opdrachtideeën voor docenten**
- “Zorg dat alle foto’s in `Foto’s/Huisdieren` of `Foto’s/Vakantie` staan.”
- “Geef elk bestand een naam met vak + datum.”
- “Wat gebeurt er als je een bestand opslaat met een naam die al bestaat?”
- “Probeer een bestand op te slaan zonder extensie. Welke melding krijg je, en waarom?”

---

## 📁 Projectstructuur

```
Mappen-/
├── mappenstructuur.html   # De complete app (HTML + CSS + JavaScript in één bestand)
├── Mappenstructuur.txt    # Python-script dat dezelfde HTML wegschrijft naar een bestand
└── README.md              # Deze documentatie
```

### `mappenstructuur.html`
De volledige, zelfstandige applicatie. Geen externe bibliotheken, frameworks of build-stap.

### `Mappenstructuur.txt`
Een Python-snippet waarin de HTML als string (`html = r"""…"""`) staat en die deze wegschrijft naar
`/mnt/data/mappenstudio_opslaan_v2.html`. De HTML-inhoud is identiek aan `mappenstructuur.html`.
Wil je het script gebruiken, hernoem het dan naar `.py` en pas het pad aan:

```python
path = "mappenstudio.html"
```

```bash
python3 Mappenstructuur.py
```

> Let op: wijzigingen aan de app moet je in beide bestanden doorvoeren, of je kiest er één als bron.

---

## ⚙️ Technische werking

### Datamodel
Het bestandssysteem is een boomstructuur van JavaScript-objecten:

```js
{
  id: 'root', type: 'folder', name: 'Mijn computer', open: true,
  children: [
    { id: 'a1b2c3d', type: 'folder', name: 'Downloads', open: true, children: [] },
    { id: 'e4f5g6h', type: 'folder', name: 'School',    open: true, children: [
        { id: 'i7j8k9l', type: 'file', name: 'Rekenen-week3.pdf' }
    ]},
    { id: 'm0n1o2p', type: 'folder', name: 'Foto’s',    open: false, children: [] }
  ]
}
```

| Veld | Betekenis |
|---|---|
| `id` | Willekeurige unieke sleutel (7 tekens) |
| `type` | `'folder'` of `'file'` |
| `name` | Weergavenaam (bij bestanden inclusief extensie) |
| `open` | Of een map uitgeklapt is (alleen mappen) |
| `children` | Inhoud van de map (alleen mappen) |

### Opslag
- De hele boom wordt als JSON opgeslagen in `localStorage` onder de sleutel **`mappenstudio.v1`**.
- Bij het laden van de pagina wordt deze teruggelezen; ontbreekt hij, dan start de app met `Downloads`, `School` en `Foto’s`.
- Gegevens blijven **lokaal in de browser** en worden nergens naartoe verstuurd.

**Handmatig alles wissen** (bijv. in de browserconsole):
```js
localStorage.removeItem('mappenstudio.v1');
```

### Belangrijkste functies in de code

| Functie | Wat doet het |
|---|---|
| `render()` / `renderFolder()` / `renderFile()` | Tekent de boomstructuur opnieuw |
| `ensureDownloads()` | Zorgt dat de map *Downloads* altijd bestaat |
| `findById()` / `parentOf()` / `removeById()` | Zoeken, ouder vinden en verwijderen in de boom |
| `pathTo()` | Bouwt het pad, bijv. `/School/Rekenen` |
| `uniqueNameIn()` | Maakt unieke namen zoals `bestand (1).pdf` |
| `startRename()` | Inline hernoemen met Enter/Esc |
| `openSaveAs()` / `performSave()` | Het *Opslaan als…*-venster en de verplaatslogica |
| `validateFilename()` | Controleert lege naam, extensie en ongeldige tekens |
| `save()` / `load()` | Opslaan en laden via `localStorage` |

---

## 🛠️ Aanpassen

### Andere voorbeeldbestanden
Pas de lijst `DOWNLOAD_CATALOG` aan in `mappenstructuur.html`:

```js
const DOWNLOAD_CATALOG = [
  {name:'Rekensommen-jan.pdf'},
  {name:'Spreekbeurt-dieren.pptx'},   // nieuw
  // …
];
```

### Andere startmappen
Pas de standaard-`state` bovenaan het script aan (de map `Downloads` moet blijven bestaan):

```js
let state = load() || {
  id: 'root', type: TYPE.FOLDER, name: 'Mijn computer', open: true, children: [
    { id: uid(), type: TYPE.FOLDER, name: DOWNLOADS_NAME, open:true, children: [] },
    { id: uid(), type: TYPE.FOLDER, name: 'Documenten', open:true, children: [] },
  ]
};
```

> Bestaande gebruikers zien deze wijziging pas na **Reset structuur** of na het wissen van `localStorage`.

### Kleuren en stijl
Alle kleuren staan als CSS-variabelen in `:root`:

```css
--brand:#2563eb;   /* hoofdkleur knoppen */
--accent:#7c3aed;  /* stapnummers */
--bad:#ef4444;     /* foutmeldingen */
```

---

## 🌐 Browserondersteuning

Werkt in alle moderne browsers: **Chrome, Edge, Firefox en Safari** (desktop en tablet).
Er wordt gebruikgemaakt van `localStorage`, `Element.animate()` en moderne JavaScript (ES2020, zoals optional chaining `?.`).
Op smalle schermen (< 960 px) wordt het *Opslaan als*-venster onder elkaar weergegeven.

---

## ⚠️ Bekende beperkingen

- Het is een **simulatie**: er worden geen echte bestanden gedownload, aangemaakt of opgeslagen.
- Bestanden hebben geen inhoud en kunnen niet geopend worden.
- Bestanden en mappen kunnen niet met slepen (drag & drop) verplaatst worden; verplaatsen gaat via *Opslaan als…*.
- Bij het aanmaken van mappen/bestanden via het ＋-menu wordt de naam nog niet gecontroleerd op dubbele namen of ongeldige tekens.
- Gegevens zijn per browser en per apparaat; in een privévenster gaan ze verloren na het sluiten.
- De interface is alleen in het **Nederlands** beschikbaar.

---

## 💡 Ideeën voor uitbreiding

- Drag & drop om bestanden en mappen te verplaatsen.
- Bestandspictogrammen per type (🖼️ afbeelding, 🎵 audio, 📝 document).
- Opdrachtenmodus met automatische controle (“Staat alles in de juiste map?”).
- Exporteren/importeren van een mappenstructuur als JSON.
- Prullenbak met herstelfunctie.
- Toetsenbordbediening en verbeterde toegankelijkheid (ARIA).
- Meertaligheid (bijv. Engels).

---

## 🤝 Bijdragen

Suggesties en verbeteringen zijn welkom!

1. Fork de repository.
2. Maak een branch: `git checkout -b mijn-verbetering`.
3. Commit je wijzigingen en open een Pull Request.

---

Gemaakt met ❤️ voor digitale geletterdheid en mediawijsheid.
