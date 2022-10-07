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
