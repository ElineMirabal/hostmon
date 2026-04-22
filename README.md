# Astro Starter Kit: Minimal

```sh
npm create astro@latest -- --template minimal
```

> 🧑‍🚀 **Seasoned astronaut?** Delete this file. Have fun!

## 🚀 Project Structure

Inside of your Astro project, you'll see the following folders and files:

```text
/
├── public/
├── src/
│   └── pages/
│       └── index.astro
└── package.json
```

Astro looks for `.astro` or `.md` files in the `src/pages/` directory. Each page is exposed as a route based on its file name.

There's nothing special about `src/components/`, but that's where we like to put any Astro/React/Vue/Svelte/Preact components.

Any static assets, like images, can be placed in the `public/` directory.

## 🧞 Commands

All commands are run from the root of the project, from a terminal:

| Command                   | Action                                           |
| :------------------------ | :----------------------------------------------- |
| `npm install`             | Installs dependencies                            |
| `npm run dev`             | Starts local dev server at `localhost:4321`      |
| `npm run build`           | Build your production site to `./dist/`          |
| `npm run preview`         | Preview your build locally, before deploying     |
| `npm run astro ...`       | Run CLI commands like `astro add`, `astro check` |
| `npm run astro -- --help` | Get help using the Astro CLI                     |

## 👀 Want to learn more?

Feel free to check [our documentation](https://docs.astro.build) or jump into our [Discord server](https://astro.build/chat).

##

Teknisk dokumentation – [HoestMoen]

OM PROJEKTET
Dette projekt er udarbejdet i Tema 9, hvor indholdet til websitet er bestående af HTML, CSS og JavaScripts (I Astro).
Indholdet til selve Programoversigt og Singleview bliver hentet fra egen API.

Sitet består af flere sider, hvor brugeren kan:
Forside med introduktion til Hoest Mon med hero, musikprogramteaser, lidt om Hoest Moen og genveje til de andre sites.
Andet indhold på sites er bestående af et musik- og aktivitetsprogram , billetter og et arkiv for tidligere musikprogram. Andre tilføjelser er en frivillig-signup formular med Pop-over og et udvidet programoversigt i Pop-over.

//
LISTE MED INDHOLD
Klikke sig videre til en detaljeside
Udfylde en formular
Links
GitHub repository: [indsæt link]
GitHub Pages: [indsæt link]
Figma: [indsæt link]
Trello: [indsæt link]
Projektstruktur
Projektet er opdelt i HTML, CSS og JavaScript-filer.
//

├── public/
│ ├── billeder
│ └── resten
│ └── kunstnere
├── src/
│ ├── Components/
│ └── Header.astro
│ └── Cta.astro
│ └── KunstnerTeaserCard.astro
│ └── GenvejCards.astro
│ └── ProgramoversigtKunstnere.astro
│ └── ProgramoversigtAktiviteter.astro
│ └── Billetter.astro
│ └── ForrigelineupCards.astro
│ └── SingleviewKunster.astro
│ └── FrivilligForms.astro
│ └── ProgramoversigtForms.astro
│ └── Footer.astro
│
│ ├── layouts/
│ └── Layout.astro
│
│ ├── pages/
│ └── index.astro
│ └── kunstneroversigt.astro
│ └── singleview.astro
│
│ └── styles/
│ └── #global.css
│
├── js/
│ ├── astro.config.mjs
│
└── README.md

FILBESKRIVELSER
index.astro – forsiden der viser hero, kunstnerteaser, lidt om host mon og genvej til frivillig og forrigelineup
kunstneroversigt.astro - viser en liste med data fra API'et, billetkøb og forrigelineup
singleview.astro - viser detaljer om en valgt kunstner
Layout.astro - er skellettet til Layoutet
global.css – styrer designet grundlæggende
JavaScriptfil – styrer det dynamiske indhold på de forskellige sider (javascriptet indgår i de pages det har relevans for)
components - herunder er alle komponenterne, som vi benytter i de forskellige .astro pages.

HVORDAN KODEN FUNGERER
Under kunstneroversigt.astro henter vha. json data fra vores egen API og viser en liste med musikkunstnerne.
På singleview.astro hentes og vises der yderligere information om dem.

FLOW
Siden loader
JavaScript kører
Data hentes fra API
Brugeren kan klikke på en kunstner i kunstnereoversigt.astro.
Singleview bruges til detaljesiden. Den læser et id fra URL'en og henter derefter den rigtige kunstner fra egen API'et.

Det gør det muligt at genbruge den samme astro-side til flere single views. I stedet for at lave én side per kunstner, bruger vi ét id i URL'en til at vise det rigtige indhold.

Javascriptet i astro-siden(frivilligForms.astro) styrer formularen og validering af inputfelter.
Denne fil bruges til at sikre, at brugeren udfylder formularen korrekt. Det gør formularen mere brugervenlig og mindsker fejl.

NAVNGIVNING
Vi har navngivet vores filer, variabler og funktioner så tydeligt som muligt.

Eksempel:
// Henter kunstnere fra egen API
const data = await fetch(url, {
headers: {
"Content-Type": "application/json",
"apikey": apiKey,
"Authorization": `Bearer ${apiKey}`
}
}).then(res => res.json());

Data og JSON-struktur:
Vi henter data fra et API i JSON-format.

Felter vi bruger:
id – bruges til at sende brugeren videre til detaljesiden
img - billede af kunstner
navn – kunstnernavn
tid – hvilket tidspunkt der spilles
dag – hvilken dag der spilles
beskrivelse – uddybet beskrivelse om kunstneren
link - til youtube
link - til spotify

HTML-validering under frivillig popover(Modal):
required – feltet skal udfyldes
type="email" – validerer email-format
type="number" – accepterer kun tal
Det sikrer, at brugeren ikke kan sende formularen, hvis felterne ikke er udfyldt korrekt.

Git og branches
Vi har brugt GitHub til at samarbejde om projektet.
Vi har arbejdet med branches, så vi ikke sad og ændrede i det samme på samme tid.
Vi navngav branchene med feature først og navnet på den, der lavede branchen til sidst.

Eksempler på branches:
hero-yasmin
header-signe
footer-signe
kunstnercardforside-eline

Workflow:
Lave en branch med feature-navn og eget navn til sidst
Kode en feature
Committe ændringer
Pushe til GitHub
Merge til main når det virkede (ét gruppemedlem ad gangen)
Det gør det nemmere at holde styr på, hvem der laver/lavede hvad.

Bæredygtighed:
Vi har forsøgt at tænke bæredygtighed ind i projektet ved at holde løsningen forholdsvis enkel.

Tiltag:
Bruge få og lette filer
Undgå tunge frameworks
Genbruge kode
Optimere billeder og indhold
Et lettere website kræver færre ressourcer at loade og bruge.

Udfordringer
At opstille Astro og sætte os ind i de forskellige (og nye) kodningsstrategier.
En af vores udfordringer var at oprette og indsætte data fra vores egen API - altså vist korrekt på siderne og hvilken del af URL’en der er til detaljesiden.

Løsninger:
Console.logge data undervejs
Teste fetch-kald separat
Bruge URLSearchParams
Dele opgaverne mere tydeligt i gruppen
Mulige forbedringer
Hvis vi skulle arbejde videre med projektet, kunne vi forbedre det ved at tilføje:

Søgefunktion
Flere filtre
Bedre error handling
Loading state
Mere avanceret formular
Bedre responsivt design

Gruppe nr. 4
Gruppemedlemmer
Yasmin
Eline
Signe

##
