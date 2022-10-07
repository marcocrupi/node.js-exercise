# INTRODUCTION TO NODE.JS - The Process Module

Vogliamo che il programma in app.js memorizzi la quantità iniziale di memoria utilizzata (heapUsed), esegua un'operazione e quindi confronti la quantità finale di memoria utilizzata con la quantità originale. Al momento, la variabile initialMemory è assegnata a null. Modificare questa riga, in modo che a initialMemory venga invece assegnato il valore della proprietà heapUsed sull'oggetto restituito dal richiamo del metodo process.memoryUsage().

Vogliamo che l'utente del programma sia in grado di inserire la propria parola quando esegue il programma. In questo momento “word” è assegnato a null. Modificare il programma in modo che quando un utente avvia il programma con un argomento della riga di comando aggiuntivo, a word verrà assegnato quel valore. Ad esempio, l'esecuzione del programma con il comando: node app.js Codecademy comporterebbe l'assegnazione a word del valore 'Codecademy'.
