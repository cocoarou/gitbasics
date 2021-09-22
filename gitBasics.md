# 												**GIT**

[TOC]



------

## **Git started** 

### Inizializzare una cartella in repository locale git

Navigare nella cartella desiderata ed eseguire il comando: 

```bash
git init
```

nota: ora nella cartella dovrebbe essere presente una directory nascosta .git

### Crea branch

```bash
git branch {nome-branch}
git checkout -b {nome-branch} ##CREA e rendi il branch corrente
```

Nota: il branch viene creato dal branch nel quale ti trovi (per capire il branch nel quale ti trovi è semplice: quando usi il comando 'git branch' la console, di solito, ti evidenzia sia con colore diverso che con un asterisco all inizio il branch nel quale sei)

### Mostra i branch che ho in locale per la repository corrente ###

```bash
git branch		#branch locali
git branch -r	#branch remoti 
git branch -a	#TUTTI i branch (sia locali che remoti)
```

### Cambiare branch

```bash
git checkout {nome-branch}
```

### Clonare una repository

```bash
git clone {indirizzo-repository} 
#esempio: git clone https://github.com/cocoarou/gitBasics
```

nota: importa la repository nella directory nella quale ci si trova. Se, per esempio, ci troviamo in 
*C:\Users\{user-corrente}\Desktop\{cartella}* ed eseguiamo il comando, viene clonata qui

------

## Git LOG

### Loggare i commit della repository 

```bash
git log
git log -p (or --patch) -2
# -p: PER LOGGARE ANCHE I CAMBIAMENTI DELLE VARIE VERSIONI
# -<n>: con n=2 per loggare gli ultimi 2 cambiamenti 

git log --stat
#LOG in forma abbreviata

git log --pretty=format:"%h - %an, %ar : %s"
# --pretty peremette di rappresentare il log con dati CUSTOM

git log --since=2.weeks
git log --before="2008-11-01" 
#Si possono usare anche operatori come  --since --after --until --before ed accettano diversi formati di data					
```

Lista completa dei comandi per dati custom:
https://git-scm.com/book/en/v2/Git-Basics-Viewing-the-Commit-History

> Sarebbe buono aggiungere qualche configurazione custom per la rappresentazione dei log
>
> - Capored

------

## **Git Gud - Azioni su repository**

### Visualizzare stato file

```bash
git status
```

### Aggiornare la repository

```bash
git fetch
```

Questa funzione viene fatta in automatico quando fai 'git pull', pero puo capitare che non ti serva di aggiornare il branch, ma di vedere se qualcuno ha aggiunto o rimosso dei branch sulla repository remota

### Aggiornare il branch

```bash
git pull origin {nome-branch}
```

### Aggiornare la repository remota

```bash
git push origin (nome-branch}
```

<<<<<<< HEAD
nota: se si pusha un branch nuovo, potrebbe non pushare e chiedere di settare l upstream. 
=======
Se si pusha  branch nuovo, potrebbe non pushare e chiedere di settare l upstream. 
>>>>>>> 52001561a80fe763ed8fb1178201f1ede89b155d
Basta semplicemente fare copia ed incolla di quello che viene proposto dalla console, tipo:

```bash
git push --set-upstream origin {nome-branch}
```

### Aggiungere file all'area di staging

```bash
<<<<<<< HEAD
git add {nome-file-da-aggiungere} 		##un file alla volta
git add .								##tutti i file
=======
git add {nome-file-da-aggiungere}
#un file alla volta

git add .
#tutti i file
>>>>>>> 52001561a80fe763ed8fb1178201f1ede89b155d
```

### Commit dei file in staging

```bash
git commit -m "messaggio del commit"
```

nota: con l'opzione -m si puo' scrivere il messaggio del commit direttamente da console, se si omette viene aperto l'editor di default e lo fa inserire.
questo comando esegue il commit solo dei file nell'area di staging

### Merge di un branch

```bash
git checkout {branch-da-aggiornare}
git merge {nome-branch-con-modifiche-da-portare}
```


nota: per apportare le modifiche effettuate da un branch ad un altro, bisogna posizionarsi nel branch nel quale vogliamo far convergere le modifiche (con git checkout {branch-da-aggiornare})
e richiamare il branch con le modifiche (git merge {nome-branch-con-modifiche-da-portare})

### Aggiungere directory vuota alla repository

creare un file .gitkeep oppure un file README.md (che contiene una descrizione della cartella) in tutte le cartelle interessate

