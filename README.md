# Innføring i webutvikling

Denne innføringen vil gi deg raskt innblikk i HTML, CSS og JavaScript, som er de mest brukte språkene for å utvikle nettsider.

Vi kommer ikke til å gå i dybden her, men du kan få en smakebit på om nettutvikling er noe for deg. I notatene ligger det en link til en spilleliste jeg har laget for dere som synes nettutvikling virker interessant, som vil gjøre dere rustet til å lage hva dere vil.

Kort oppsumert er HTML det som lar oss strukturere en nettside - for eksempel fortelle nettleseren at vi vil ha en knapp, CSS lar oss utforme strukturen, sånn at knappen kan se fancy ut, og JavaScript gjør det mulig å lage funksjonalitet som ikke er bygd inn i HTML allerede, som at man eksempelvis får knappen til å endre variabler som påvirker noe annet på nettsiden.

Ikke bekymre deg dersom ting går litt fort fram og du ikke skjønner alt, siden webutvikling krever mye trening for å få det inn i fingrene, og spillelisten vil fylle inn mye som utelates her.

I praksis er det sjeldent at man bruker HTML, CSS og JavaScript direkte på den måten vi kommer til å gjøre nå, og man bruker som regel et rammeverk som fikser HTML, CSS og JavaScript for deg. Derfor vil slutten av videoen vise hvordan man ville implementert det vi har laget i rammeverket React, som er det vi oftest bruker på Eik.

[Send meg en melding](https://www.facebook.com/kristian.kramas) hvis det er noe du lurer på underveis i innføringen eller mens du jobber deg gjennom spillelisten. Jeg synes det er veldig hyggelig å hjelpe dere og ingen spørsmål er dumme når det kommer til webutvikling.

## Innhold <!-- omit in toc -->

- [Innføring i webutvikling](#innføring-i-webutvikling)
  - [📄 HTML](#-html)
  - [🎨 CSS](#-css)
  - [⚙ JavaScript](#-javascript)
  - [🎉 Gratulerer!](#-gratulerer)
  - [👨‍🔬 React (Økt vanskelighetsgrad)](#-react-økt-vanskelighetsgrad)
  - [✈ Veien videre](#-veien-videre)
  - [🖋 Notater](#-notater)

## 📄 HTML

1. Gå til [CodeSandbox](https://codesandbox.io/)
2. Trykk på `Create Sandbox`
3. Velg malen som heter `static`

    Da får du opp en ferdig HTML-mal. Du kan programmere på venstre og se hvordan nettsiden blir seende ut på høyre.

    Den eneste filen vi trenger å bry oss om i dette tilfelle er `index.html`, som er hele nettsiden vår for øyeblikket. De andre filene kan du ignorere, siden de bare har med utviklermiljøet å gjøre (som er programmet du skriver i).

    I `index.html` er det mye rare greier...

    ```html
    <!DOCTYPE html>
    <html lang="en">
        <head>
            <meta charset="UTF-8" />
            <meta name="viewport" content="width=device-width, initial-scale=1.0" />
            <meta http-equiv="X-UA-Compatible" content="ie=edge" />
            <title>Static Template</title>
        </head>
        <body>
            <h1>
                This is a static template, there is no bundler or bundling involved!
            </h1>
        </body>
    </html>
    ```

    ...men det meste kan ignoreres, siden nesten alt er informasjon til nettleseren, som vi ikke trenger å tenke på nå.

    Det vi vil fokusere på er det som er inne i bodyknaggen:

     ```html
    <body>
        <h1>
            This is a static template, there is no bundler or bundling involved!
        </h1>
    </body>
    ```

    Du kan tenke på en tag som en boks man putter ting i. `<body></body>` er boksen du ser på høyre side, og det vi setter mellom åpningsknaggen `<body>` og lukkeknaggen `</body>` vil vises på nettsiden.


5. Erstatt overskriften:

    ```html
    <h1>
        This is a static template, there is no bundler or bundling involved!
    </h1>
    ```

    med

    ```html
    <button>Knapp</button>
    ```

    Og vi har laget en enkel HTML-side med én knapp.

## 🎨 CSS

For å utforme knappen bruker vi CSS. 

1. Lag en ny fil ved å trykke på `New File`-ikonet eller `File -> New File` i verktøylinja
2. Gi den navnet `styles.css`
3. Legg til `<link rel="stylesheet" href="styles.css">` i headknaggen i `index.html` for å importere stilene i HTML-filen:

     ```html
    <!DOCTYPE html>
    <html lang="en">
        <head>
            <meta charset="UTF-8" />
            <meta name="viewport" content="width=device-width, initial-scale=1.0" />
            <meta http-equiv="X-UA-Compatible" content="ie=edge" />
            <title>Static Template</title>
            <link rel="stylesheet" href="styles.css">
        </head>
        <body>
            <button>Knapp</button>
        </body>
    </html>
    ```

4. Legg til en klasse med navn `btn` i `styles.css`:

     ```css
    .btn {

    }
    ```

5. Legg til klassen i knappen i `index.html`, ved å legge til `class="btn"` i åpningsknaggen til knappen:

    ```html
    <!DOCTYPE html>
    <html lang="en">
        <head>
            <meta charset="UTF-8" />
            <meta name="viewport" content="width=device-width, initial-scale=1.0" />
            <meta http-equiv="X-UA-Compatible" content="ie=edge" />
            <title>Static Template</title>
            <link rel="stylesheet" href="styles.css" />
            <script src="btn.js"></script>
        </head>
        <body>
            <button class="btn">Knapp</button>
        </body>
    </html>
    ```

6. Legg til litt utforming i klassen:

     ```css
    .btn {
        border: none; /* Fjerner sort ramme rundt standardknapp */
        color: white; /* Endrer farge på tekst til hvit */
        padding: 15px 32px; /* Legger til mer pusterom runt teksten i knappen */
        text-align: center;  /* Plasserer teksten i midten av knappen */
        text-decoration: none; /* Fjerner at standardstil på tekst */
        font-size: 16px; /* Endrer tekststørrelse */
        background-color: #008cba; /* Endrer bakgrunnsfarge til blå */
        border-radius: 4px; /* Avrunder hjørnene */
    }
    ```

    Dette er utforming inspirert av w3schools eksempler - linken er i notatene. Prøv deg gjerne fram ved å endre på verdiene, og se hva som skjer.

    Husk å lagre (<kbd>CTRL</kbd> + <kbd>S</kbd> eller <kbd>⌘</kbd> + <kbd>S</kbd>) for å se endringene du gjør.

7. Vi kan legge til enkel scripting for stiler uten JavaScript for tilfeller som når musepekeren er over et objekt. Jeg lagde dette basert på w3schools eksempler for å gjøre knappen litt mer livlig:

     ```css
    .btn {
        border: none; /* Fjerner sort ramme rundt standardknapp */
        color: white; /* Endrer farge på tekst til hvit */
        padding: 15px 32px; /* Legger til mer pusterom runt teksten i knappen */
        text-align: center;  /* Plasserer teksten i midten av knappen */
        text-decoration: none; /* Fjerner at standardstil på tekst */
        font-size: 16px; /* Endrer tekststørrelse */
        background-color: #008cba; /* Endrer bakgrunnsfarge til blå */
        border-radius: 4px; /* Avrunder hjørnene */
        transition-duration: 0.4s; /* Animerer overganger, så de blir mykere */
    }

    .btn:hover { /* Aktiveres bare når musepeker er over knapp */
        background-color: #046788; /* Gjør farge mørkere */
    }
    ```

## ⚙ JavaScript

Vi har nå en veldig fin knapp...

...som ikke gjør noe.

For å gi den funksjonalitet bruker vi JavaScript.

1. Lag en ny fil ved å trykke på `New File`-ikonet eller `File -> New File` i verktøylinja
2. Gi den navnet `button.js`
3. Legg til `<script src="button.js"></script>` i head-knaggen i `index.html` for å importere scriptet i HTML-filen:

     ```html
    <!DOCTYPE html>
    <html lang="en">
        <head>
            <meta charset="UTF-8" />
            <meta name="viewport" content="width=device-width, initial-scale=1.0" />
            <meta http-equiv="X-UA-Compatible" content="ie=edge" />
            <title>Static Template</title>
            <link rel="stylesheet" href="styles.css">
            <script src="button.js"></script>
        </head>
        <body>
            <button class="btn">Knapp</button>
        </body>
    </html>
    ```

4. Vi lager en funksjon i `button.js` som setter inn nåtid i en gitt knagg:

    ```js
    function getDate(id) {
        document.getElementById(id).innerHTML = Date();
    }
    ```

    - `document` refererer til nettsiden
    - `getElementById` henter et dokument med ID-en vi mater den
    - `innerHTML` refererer til det som er mellom åpnings- og lukkeknaggen
    - `Date()` gir oss nåtid

    Det vil si at når funksjonen aktiveres, vil knaggen vi har valgt fylles med dagens dato, som vises på nettsiden.

5. Legg til en knagg med ID som kan vise datoen i `index.html`:

    ```html
    <!DOCTYPE html>
    <html lang="en">
        <head>
            <meta charset="UTF-8" />
            <meta name="viewport" content="width=device-width, initial-scale=1.0" />
            <meta http-equiv="X-UA-Compatible" content="ie=edge" />
            <title>Static Template</title>
            <link rel="stylesheet" href="styles.css" />
            <script src="button.js"></script>
        </head>
        <body>
            <button class="btn">
                Knapp
            </button>
            <div id="date"></div>
        </body>
    </html>
    ```

6. Vi ber knappen kjøre funksjonen `getData()` når den trykkes, ved å legge til `onclick="getDate('date')"` i åpningsknaggen:

    ```html
    <!DOCTYPE html>
    <html lang="en">
        <head>
            <meta charset="UTF-8" />
            <meta name="viewport" content="width=device-width, initial-scale=1.0" />
            <meta http-equiv="X-UA-Compatible" content="ie=edge" />
            <title>Static Template</title>
            <link rel="stylesheet" href="styles.css" />
            <script src="button.js"></script>
        </head>
        <body>
            <button class="btn" onclick="getDate('date')">
                Knapp
            </button>
            <div id="date"></div>
        </body>
    </html>
    ```

    Sørg for at ID-en til knaggen som skal vise dato og argumentet til `getDate()` er like. Jeg har valgt å bruke "date".

7. Trykk på knappen.

## 🎉 Gratulerer!

Nå har du laget en knapp med HTML, CSS og JavaScript.

Videre kan du velge om du har lyst til å:

1. Gjøre det samme i et skikkelig rammeverk (React), ved å fortsette denne innføringen
2. Hoppe rett inn i [Zero to Fullstack Hero](https://www.youtube.com/watch?v=Mj3QejzYZ70&list=PLzWjrc7MKKxyffsM7YTBnogYpBh_QUIO0) og lære deg fullstack-utvikling
3. [Sende meg en melding](https://www.facebook.com/kristian.kramas), dersom du har en idé om noe du vil lage, så hjelper jeg deg i gang
4. Gjøre noe helt annet, hvis dette ikke var helt din greie

## 👨‍🔬 React (Økt vanskelighetsgrad)

Her fokuserer jeg på å implementere det samme i React og vil ikke forklare hvordan alt fungerer, da hensikten er at du får en liten smakebit på React før du fortsetter.

1. Gå til denne [React-malen](https://codesandbox.io/s/react-bootstrap-5rui9?file=/src/App.jsx)
2. Pass på at du er i filen `App.jsx`:

    ```jsx
    import React, { useState } from "react";
    import "styles/styles.css";
    import "styles/bootstrap.scss";

    export default () => {
        return (
            <div className="text-center">
                <div className="">Hello World!</div>
            </div>
        );
    };
    ```

3. Importer en ferdiglagd knapp fra biblioteket React Bootstrap og Bytt ut `<div className="">Hello World!</div>` med `<Button>Knapp</Button>`:

    ```jsx
    import React from "react";
    import "styles/styles.css";
    import "styles/bootstrap.scss";
    import Button from "react-bootstrap"

    export default () => {
        return (
            <div className="text-center">
                <Button>Knapp</Button>
            </div>
        );
    };
    ```

4. Legg til en knagg der vi kan plassere datoen:

    - Importer `useState`, så vi kan lagre og endre dato
    - Lag en *state* for dato med `const [date, setDate] = useState();`
    - Legg til `<div>{date}</div>` under knappen

    Du vil lære mer om hva en *state* er og hvorfor vi bruker det i spillelisten.

    ```jsx
    import React, { useState } from "react";
    import "styles/styles.css";
    import "styles/bootstrap.scss";
    import Button from "react-bootstrap"

    export default () => {
        const [date, setDate] = useState();

        return (
            <div className="text-center">
                <Button>Knapp</Button>
                <div>{date}</div>
            </div>
        );
    };
    ```

5. Gjør så knappetrykk endrer dato til nåtid, ved å legge til `onClick={() => setDate(Date())` i åpningsknaggen til knappen:

    ```jsx
    import React, { useState } from "react";
    import "styles/styles.css";
    import "styles/bootstrap.scss";
    import Button from "react-bootstrap"

    export default () => {
        const [date, setDate] = useState();

        return (
            <div className="text-center">
                <Button onClick={() => setDate(Date())}>Knapp</Button>
                <div>{date}</div>
            </div>
        );
    };
    ```

6. Trykk på knappen.
7. 👏👏👏

## ✈ Veien videre

1. Se [Zero to Fullstack Hero](https://www.youtube.com/watch?v=Mj3QejzYZ70&list=PLzWjrc7MKKxyffsM7YTBnogYpBh_QUIO0) og lære deg fullstack-utvikling
2. [Sende meg en melding](https://www.facebook.com/kristian.kramas), dersom du har en idé om noe du vil lage, så hjelper jeg deg i gang

## 🖋 Notater
- [CodeSandbox](https://codesandbox.io/)
- [Ferdig prosjekt (HTML, CSS og JavaScript)](https://codesandbox.io/s/knapp-med-html-css-javascript-z6kc6)
- [React-mal](https://codesandbox.io/s/react-bootstrap-5rui9?file=/src/App.jsx)
- [Ferdig prosjekt (React)](https://codesandbox.io/s/knapp-med-react-g0w3p?file=/src/App.jsx)
- [Spilleliste: Zero to Fullstack Hero](https://www.youtube.com/watch?v=Mj3QejzYZ70&list=PLzWjrc7MKKxyffsM7YTBnogYpBh_QUIO0)
- [CSS-eksempler for knapper](https://www.w3schools.com/css/css3_buttons.asp)
