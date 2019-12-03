# BLAST
## Installazione
BLAST è disponibile al link   
ftp://ftp.ncbi.nlm.nih.gov/blast/executables/blast+/LATEST/  
si può scaricare direttamente dal browser oppure tramite **ftp**.

### Linux
Sono disponibili i pacchetti installabili in archivi rpm, oltre al codice sorgente da compilare.  
Per compilare il sorgente (scelta consigliata) bisogna scaricare il file che contiente *src* nel nome, decomprimerlo `tar -zxvf ncbi-blast-xxx-src.tar.gz`, spostarsi nella cartella del codice sorgente `cd ncbi-blast-xxx-src.tar.gz/c++` e procedere con l'installazione: `./configure && make && sudo make install`. 

### Windows
Per sistemi Windows il file da scaricare è quello che finisce per *win64.exe*.  
Dopo aver scaricato il file bisogna eseguirlo e consentire l'installazione.  
A installazione terminata dovrebbe essere possibile eseguire i comandi del pacchetto di BLAST dal prompt dei comandi.
 
### Mac
Dopo aver scaricato l'installatore ed aver installato il pacchetto BLAST si possono trovare tutti i comandi blast disponibili nel terminale. 

### Anaconda (cross-platform, richiede conoscenza minima di anaconda)
entrare nell'ambiente anaconda in cui installare blast ed eseguire  
`conda install -c bioconda blast`  
oppure, se si è installato mamba  
`mamba install -c bioconda blast`  

## Uso
### Termini
Da qui in poi userò sempre gli stessi termini per definire i vari elementi usati nei comandi:  
+ **query**:
+ **database**:
+ **sorgente**:
### Creazione del database
È necessario convertire la lista di sequenze su cui fare la ricerca in un 
