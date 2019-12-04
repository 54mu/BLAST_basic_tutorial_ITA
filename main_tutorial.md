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
D'ora in poi si prosegue in una interfaccia testuale, vale a dire **prompt dei comandi** in windows oppure **terminale** in linux o mac. Il procedimento è uguale per tutti i sistemi operativi.
### Creazione del database
È necessario convertire la lista di sequenze su cui fare la ricerca in un database di blast. Per farlo il comando più semplice è  
```
makeblastdb -in inputfile.fasta -dbtype moleculetype -parse_seqids -out database_name
```
+ **inputfile.fasta** - è il file con le sequenze di riferimento (trascrittoma, proteoma, genoma etc..)
+ **moleculetype** - il tipo di molecole del database: **nucl** per nucleotidi, **prot** per proteine
+ **database_name** - il nome che si vuole dare al database

### Ricerca di sequenze in database
ci sono 5 tipi di ricerca possibili:
+ blastn : allinea sequenze nucleotidiche su un database di sequenze nucleotidiche
+ blastp : allinea sequenze amminoacidiche su un database di sequenze amminoacidiche
+ blastx : allinea sequenze nucleotidiche su un database di sequenze amminoacidiche
+ tblastn : allinea sequenze amminoacidiche su un database di sequenze nucleotidiche tradotte
+ tblastx : allinea sequenze nucleotidiche tradotte su un database di sequenze nucleotidiche tradotte

l'utilizzo base delle ricerche blast è uguale per tutti e 5 i metodi e si distingue soltanto in base al comando, in questo esempio userò blastx, ma ognuno dei 5 va bene.
```
blastx -db database_name -query query_name -evalue evalue_threshold -out output_name -outfmt format
```
