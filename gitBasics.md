## mostra i branch che ho in locale per la repository corrente ##
	
	git branch

## mostra i branch remoti della repository corrente ##
	
	git branch -r

## mostra tutti i branch della repository ##
	
	git branch -a

## crea branch

	git branch {nome-branch}

	nota: il branch viene creato dal branch nel quale ti trovi (per capire il branch nel quale ti trovi e' semplice: quando usi il comando 'git branch' la console, di solito, ti evidenzia sia con colore diverso che con un asterisco all'inizio il branch nel quale sei)

## crea branch e rendilo il branch corrente

	git checkout -b {nome-branch}
	
## cambiare branch

	git checkout {nome-branch}
	
## aggiornare la repository
	
	git fetch
	
	nota: questa funzione viene fatta in automatico quando fai 'git pull', pero' puo' capitare che non ti serva di aggiornare il branch, ma di vedere se qualcuno ha aggiunto o rimosso dei branch sulla repository remota
	
## aggiornare il branch

	git pull origin {nome-branch}
	
## aggiornare la repository remota

	git push origin (nome-branch}
	
	nota: se si pusha un branch nuovo, potrebbe non pushare e chiedere di settare l'upstream. Basta semplicemente fare copia ed incolla di quello che viene proposto dalla console 
	(dovrebbe essere una cosa tipo: git push --set-upstream origin {nome-branch}
	
## vedere lo stato dei file nella repository locale

	git status
	
	nota: mostra in rosso i file che non sono nell'area di staging ed in verde quelli che ci sono
	
## aggiungere file all'area di staging

	git add {nome-file-da-aggiungere} ## un file alla volta
	git add .						  ## tutti i file
	
## commit dei file in staging

	git commit -m "messaggio del commit"
	
	nota: con l'opzione -m si puo' scrivere il messaggio del commit direttamente da console, se si omette viene aperto l'editor di default e lo fa inserire.
	questo comando esegue il commit solo dei file nell'area di staging
	
## clonare una repository

	git clone {indirizzo-repository} ## esempio: git clone https://github.com/cocoarou/gitBasics
	
	nota: importa la repository nella directory nella quale ci si trova. Se, per esempio, ci troviamo in C:\Users\{user-corrente}\Desktop\{cartella} ed eseguiamo il comando, viene clonata qui
	
## merge di un branch
	
	git checkout {branch-da-aggiornare}
	git merge {nome-branch-con-modifiche-da-portare}
	
## aggiungere directory vuota alla repository
	
	creare un file .gitkeep oppure un file README.md (che contiene una descrizione della cartella) in tutte le cartelle interessate
	

## inizializzare una cartella in repository locale git

	navigare nella cartella desiderata ed eseguire il comando: git init
	
	nota: ora nella cartella dovrebbe essere presente una directory nascosta .git


	