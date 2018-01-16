# ls-dropdown-province-comuni

Domanda LimeSurvey tipo array duale per la selezione combinata di province e comuni italiani. Codice Javascript incorporato in una domanda tipo array dual scale con due dropdown combinate (Province e Comuni da classificazione ISTAT al giugno 2017). Il codice può essere usato anche per qualsiasi altra classificazione gerarchica a due livelli.

I due file lsq sono le domande in formato xml che possono essere importate direttamente in una survey. Contengono il codice javascript e le opzioni di risposta Province-Comuni da Istat (giugno 2017):
- limesurvey_question_prov_com_ver266.lsq per la versione limesurvey 2.6.6 LTS e comprende le versioni fino alla 2.06
- limesurvey_question_prov_com_ver274.lsq per la versione limesurvey 2.74 LTS e comprende le versioni dalla 2.50

Le opzioni di risposta combinate e associate di Province e Comuni si trovano nei due file csv:
- ls_province_30_06_2017.csv con i due campi:
	- codice a 5 caratteri, con i primi due che rappresentano la sigle provincia e gli ultimi 3 il codice ISTAT di provincia
	- denominazione ISTAT della provincia
- ls_comuni_30_06_2017.csv
	- codice a 5 caratteri, con i primi due che rappresentano la sigle provincia e gli ultimi 3 il codice ISTAT di comune
	- denominazione ISTAT del comune

Per realizzare ex-novo la domanda limesurvey, occorre eseguire in limesurvey i seguenti passi:
1) Creare una domanda di tipo Array con doppia scala e in impostazioni avanzate della domanda, mettere a si l'opzione "Usare presentazione con elenchi a discesa (dropdown)"
2) Aggiungere una sottodomanda "fittizia", che costituirà l'unico elemento dell'array a doppia scala
3) Aggiungere le opzioni di risposta della doppia scala. Queste possono essere copiate e incollate con l'aggiunta veloce di limesurvey, prendendole dai due file csv relativi alle Province e Comuni ISTAT al giugno 2017:
- ls_province_30_06_2017.csv con i due campi:
	- codice a 5 caratteri, con i primi due che rappresentano la sigle provincia e gli ultimi 3 il codice ISTAT di provincia
	- denominazione ISTAT della provincia
- ls_comuni_30_06_2017.csv
	- codice a 5 caratteri, con i primi due che rappresentano la sigle provincia e gli ultimi 3 il codice ISTAT di comune
	- denominazione ISTAT del comune
L'associazione tra provincia selezionata e comuni ad essa relativi avviene nello script tramite i primi due caratteri del codice risposta (la sigla provincia)	
4) Nel testo della domanda di tipo array, definire la modifica "Codice Sorgente", quindi incollare il testo e lo script preso interamente dal file script_domanda_dual_prov_com_all_version.txt

Per usare la domanda e lo script per altre classificazioni gerarchiche è sufficende definire le due liste di opzioni di risposta usando per entrambe un codice risposta di 5 caratteri e usando i primi due per l'associazioni dinamica tra le due dropdown.
