# NODE.JS EXERCISES SOLUTIONS

## 01 - INTRODUCTION TO NODE.JS: The Process Module

Vogliamo che il programma in app.js memorizzi la quantità iniziale di memoria utilizzata (heapUsed), esegua un'operazione e quindi confronti la quantità finale di memoria utilizzata con la quantità originale. Al momento, la variabile initialMemory è assegnata a null. Modificare questa riga, in modo che a initialMemory venga invece assegnato il valore della proprietà heapUsed sull'oggetto restituito dal richiamo del metodo process.memoryUsage().

Vogliamo che l'utente del programma sia in grado di inserire la propria parola quando esegue il programma. In questo momento “word” è assegnato a null. Modificare il programma in modo che quando un utente avvia il programma con un argomento della riga di comando aggiuntivo, a word verrà assegnato quel valore. Ad esempio, l'esecuzione del programma con il comando: node app.js Codecademy comporterebbe l'assegnazione a word del valore 'Codecademy'.

```js
let initialMemory = process.memoryUsage().heapUsed;
let word = process.argv[2];

console.log(`Your word is ${word}`);

// Create a new array
let wordArray = [];

// Loop 1000 times, pushing into the array each time
for (let i = 0; i < 1000; i++) {
  wordArray.push(`${word} count: ${i}`);
}

console.log(
  `Starting memory usage: ${initialMemory}. \nCurrent memory usage: ${
    process.memoryUsage().heapUsed
  }. \nAfter using the loop to add elements to the array, the process is using ${
    process.memoryUsage().heapUsed - initialMemory
  } more bytes of memory.`
);
```

## 02 - INTRODUCTION TO NODE.JS: The OS Module

STEP

* In app.js, usando la parola chiave const, dichiara una variabile, os, che memorizza il modulo os.
* Quindi, sotto la riga che richiede nel modulo os, usa const per creare un oggetto vuoto chiamato server.
* All'interno del server, aggiungi le chiavi: type, architecture e uptime. Memorizza i rispettivi valori usando i metodi del modulo os.
* Infine, console.log() dell'oggetto server ed esegui il programma digitando node app.js nel terminale.

```js
const os = require("os");

const server = {
  type: os.type(),
  architecture: os.arch(),
  uptime: os.uptime(),
};

console.log(server);
```

## 03 - INTRODUCTION TO NODE.JS: The Util Module

In app.js abbiamo richiesto un oggetto contenente sentieri escursionistici a lunga distanza negli Stati Uniti. L'oggetto è nel file trail.js.

Sotto c'è una funzione di callback, getTrailDistance, pronta per essere convertita usando util.promisify().

Inizia richiedendo il modulo util nella parte superiore di app.js e salvandolo in una variabile util.

Successivamente, sotto la chiamata della funzione di callback nella parte inferiore del file, utilizzando const, dichiarare una variabile, getTrailDistancePromise e assegnarle util.promisify(getTrailDistance).

Quindi, chiama la nuova funzione promessa, getTrailDistancePromise, con 'North Country' (o qualsiasi proprietà trail dall'oggetto trail in trails.js) come unico argomento. Risolvi la promessa con un metodo .then() e rifiuta la promessa con un metodo .catch().

Infine, all'interno di then(), accedi alla console:

`The ${nickname} is ${mi} miles long!`

dove nickname è il soprannome e mi è la distanza del sentiero passato. All'interno di catch(), passa una funzione che registra eventuali errori.

script.js

```js
// Require in trails module from trails.js
const trails = require("./trails.js.js");
// Require util module here!
const util = require("util");

// Simulate database call to search trails module for specified trail
const getTrailDistance = (trail, callback) => {
  return setTimeout(() => {
    if (trails.hasOwnProperty(trail)) {
      const foundTrail = trails[trail];
      callback(null, foundTrail);
    } else {
      callback(new Error("Trail not found!"));
    }
  }, 1000);
};

// Callback function to send an error in the case of an error, or to handle trail data if a trail was found successfully.
function callback(error, trailData) {
  if (error) {
    console.error(error.message);
    process.exit(1);
  } else {
    const mi = trailData.miles;
    const nickname = trailData.nickname;
    console.log(`The ${nickname} is ${mi} miles long!`);
  }
}

getTrailDistance("North Country", callback);
```

trail.js

```js
module.exports = trails = {
  Appalachian: {
    nickname: "AT",
    miles: 2189.1,
    kilometers: 3253,
    region: "Appalachian Mountains",
  },
  "Continental Divide": {
    nickname: "CDT",
    miles: 3100,
    kilometers: 5000,
    region: "Rocky Mountains",
  },
  "North Country": {
    nickname: "NCT",
    miles: 4600,
    kilometers: 7400,
    region: "Northern United States",
  },
  "Pacific Crest": {
    nickname: "PCT",
    miles: 2654,
    kilometers: 4271,
    region: "West Coast",
  },
};
```
