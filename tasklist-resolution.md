# 🐞 Risoluzione Bug “Scatta foto con microcamera”

## Descrizione del problema

Premendo il pulsante “scatta foto con microcamera” l’app andava in errore:

* non veniva aperta la microcamera
* non veniva eseguita alcuna azione

## 📥 Requisiti

* **Node.js**: scarica da [https://nodejs.org/en/download](https://nodejs.org/en/download)
* **Privilegi amministrativi** su Windows (per i comandi WMI)


## 1. Verifica installazioni
	node -v  # Check if Node.js is installed  
	npm -v   # Check npm version

## 2. Esegui “tasklist”
	tasklist   # List running processes on Windows

Se il comando restituisce l’elenco dei processi, il bug risulta risolto

## 3. Ripara WMI (solo Windows)
⚠️ Usa questi comandi con attenzione e in un prompt come Administrator
	cd \Windows\System32\wbem           # Enter WMI folder  
	net stop winmgmt                    # Stop the WMI service  
	rename Repository Repository.old    # Backup the repository  
	net start winmgmt                   # Restart the WMI service

Riprova:
tasklist

Se funziona, hai completato la riparazione.
