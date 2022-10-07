# INTRODUCTION TO NODE.JS - The Util Module

In app.js abbiamo richiesto un oggetto contenente sentieri escursionistici a lunga distanza negli Stati Uniti. L'oggetto è nel file trail.js.

Sotto c'è una funzione di callback, getTrailDistance, pronta per essere convertita usando util.promisify().

Inizia richiedendo il modulo util nella parte superiore di app.js e salvandolo in una variabile util.

Successivamente, sotto la chiamata della funzione di callback nella parte inferiore del file, utilizzando const, dichiarare una variabile, getTrailDistancePromise e assegnarle util.promisify(getTrailDistance).

Quindi, chiama la nuova funzione promessa, getTrailDistancePromise, con 'North Country' (o qualsiasi proprietà trail dall'oggetto trail in trails.js) come unico argomento. Risolvi la promessa con un metodo .then() e rifiuta la promessa con un metodo .catch().

Infine, all'interno di then(), accedi alla console:

`The ${nickname} is ${mi} miles long!`

dove nickname è il soprannome e mi è la distanza del sentiero passato. All'interno di catch(), passa una funzione che registra eventuali errori.
