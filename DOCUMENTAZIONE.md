
 # Progetto Zoo

# Indice

1. [File implementazione funzioni Zoo](#documentazione-del-progetto)
    - [Funzioni](#funzioni)
        - [`inserisci`](#inserisci)
        - [`serializza`](#serializza)
        - [`animale`](#animale)
        - [`elimina`](#elimina)
        - [`cambia_zona`](#cambia_zona)
        - [`zone`](#zone)
        - [`animali_zona`](#animali_zona)
        - [`zone_animali`](#zone_animali)
        - [`animali_classe`](#animali_classe)
        - [`animali_specie`](#animali_specie)
        - [`animali_ambiente`](#animali_ambiente)
        - [`animali_con_zampe_almeno`](#animali_con_zampe_almeno)
        - [`conta_sangue`](#conta_sangue)
        - [`conta_classe`](#conta_classe)
        - [`conta_specie`](#conta_specie)
        - [`conteggio`](#conteggio)
3. [Documentazione della Classe](#documentazione-della-classe)
    - [Classe `Animale`](#classe-animale)
    - [Sottoclassi di `Animale`](#sottoclassi-di-animale)
        - [Classe `Mammifero`](#classe-mammifero)
        - [Classe `Uccello`](#classe-uccello)
        - [Classe `Pesce`](#classe-pesce)
        - [Classe `Leone`](#classe-leone)
        - [Classe `Giraffa`](#classe-giraffa)
        - [Classe `Ippopotamo`](#classe-ippopotamo)
        - [Classe `Pinguino`](#classe-pinguino)
        - [Classe `Gufo`](#classe-gufo)
        - [Classe `PescePagliaccio`](#classe-pescepagliaccio)
4. [Introduzione alla GUI](#introduzione-alla-gui)
    - [Struttura del File](#struttura-del-file)
    - [Classe `ZooApp`](#classe-zooapp)
    - [Metodi della Classe `ZooApp`](#metodi-della-classe-zooapp)
        - [`__init__`](#__init__)
        - [`crea_widgets`](#crea_widgets)
        - [`aggiorna_lista_animali`](#aggiorna_lista_animali)
        - [`aggiungi_animale`](#aggiungi_animale)
        - [`modifica_zona`](#modifica_zona)
        - [`mostra_stringa_animale`](#mostra_stringa_animale)
        - [`lista_nomi_specie`](#lista_nomi_specie)
        - [`list_nomi_ambiente`](#list_nomi_ambiente)
        - [`conta_animali_classe`](#conta_animali_classe)
        - [`carica_zoo`](#carica_zoo)
        - [`salva_zoo`](#salva_zoo)
        - [`uscita_app`](#uscita_app)
5. [Introduzione al File `zoo.py`](#introduzione-al-file-zoo.py)
    - [Struttura del File](#struttura-del-file)
    - [Classe `Zoo`](#classe-zoo)
    - [Metodi della Classe `Zoo`](#metodi-della-classe-zoo)
        - [`__init__`](#__init__-1)
        - [`aggiungi_animale`](#aggiungi_animale)
        - [`__str__`](#__str__)
        - [`__eq__`](#__eq__)
        - [`inserisci`](#inserisci-1)
        - [`animale`](#animale-1)
        - [`zona`](#zona-1)
        - [`elimina`](#elimina-1)
        - [`cambia_zona`](#cambia_zona-1)
        - [`zone`](#zone-1)
        - [`animali_zona`](#animali_zona-1)
        - [`zone_animali`](#zone_animali-1)
        - [`animali_classe`](#animali_classe-1)
        - [`animali_specie`](#animali_specie-1)
        - [`animali_ambiente`](#animali_ambiente-1)
        - [`animali_con_zampe_almeno`](#animali_con_zampe_almeno-1)
        - [`conta_sangue`](#conta_sangue-1)
        - [`conta_classe`](#conta_classe-1)
        - [`conta_specie`](#conta_specie-1)
        - [`salva`](#salva)
        - [`carica`](#carica)


# Documentazione del progetto Zoo





Questo file contiene una serie di funzioni per gestire un dizionario che rappresenta uno zoo. Ogni animale nello zoo è rappresentato da una tupla contenente diverse informazioni come il nome, la classe, la specie, il numero di zampe, se ha sangue caldo o freddo, l'ambiente in cui vive, la zona in cui si trova e il verso che emette. Le funzioni permettono di inserire, eliminare, modificare e interrogare gli animali nel dizionario.

## Funzioni

### `inserisci(zoo, nome, classe, specie, numero_zampe, sangue_caldo, ambiente, zona, verso)`

**Descrizione:**
Inserisce un nuovo animale nel dizionario `zoo` evitando duplicati e verificando che i parametri abbiano il tipo corretto e siano nel range di valori ammessi.

**Parametri:**
- `zoo`: il dizionario dello zoo.
- `nome`: nome dell'animale (stringa).
- `classe`: classe dell'animale (stringa) uno fra: "Mammifero", "Uccello", "Pesce", "Rettile", "Anfibio".
- `specie`: specie dell'animale (stringa).
- `numero_zampe`: numero di zampe (intero positivo).
- `sangue_caldo`: sangue caldo (booleano).
- `ambiente`: ambiente in cui vive (lista di stringhe) almeno uno fra: "Acqua", "Terra", "Aria".
- `zona`: zona in cui si trova (stringa) composta da una lettera maiuscola seguita da un numero intero (es. "A1").
- `verso`: verso che emette (stringa).

**Ritorna:**
- `True` se l'inserimento è stato effettuato con successo.
- `False` se i parametri non hanno il tipo corretto o non sono corretti.

**Corpo della funzione:**
1. Verifica che il `nome` sia una stringa.
2. Verifica che la `classe` sia una stringa e appartenga a una lista di classi valide.
3. Verifica che la `specie` sia una stringa.
4. Verifica che `numero_zampe` sia un intero positivo.
5. Verifica che `sangue_caldo` sia un booleano.
6. Verifica che `ambiente` sia una lista di stringhe e che ogni elemento appartenga a una lista di ambienti validi.
7. Verifica che `zona` sia una stringa composta da una lettera maiuscola seguita da un numero intero.
8. Verifica che `verso` sia una stringa.
9. Verifica che l'animale non sia già presente nel dizionario.
10. Inserisce l'animale nel dizionario e restituisce `True`.

### `serializza(zoo)`

**Descrizione:**
Serializza tutti gli animali nel dizionario `zoo` creando una singola stringa. Ogni animale è rappresentato da una descrizione narrativa che include tutte le informazioni dell'animale. Le descrizioni degli animali sono separate dal carattere di nuova linea (`\n`).

**Parametri:**
- `zoo`: il dizionario da serializzare.

**Ritorna:**
- Una stringa che rappresenta il dizionario.

**Corpo della funzione:**
1. Inizializza una stringa vuota `zoo_serializzato`.
2. Itera su ogni animale nel dizionario.
3. Costruisce una descrizione narrativa per ogni animale.
4. Aggiunge la descrizione narrativa alla stringa `zoo_serializzato`.
5. Restituisce la stringa `zoo_serializzato`.

### `animale(zoo, nome)`

**Descrizione:**
Restituisce la tupla relativa all'animale con nome `nome`.

**Parametri:**
- `zoo`: il dizionario.
- `nome`: il nome dell'animale da estrarre.

**Ritorna:**
- La tupla relativa all'animale se presente.
- `None` se l'animale non è presente nel dizionario.

**Corpo della funzione:**
1. Verifica se il `nome` è presente nel dizionario.
2. Restituisce la tupla corrispondente se presente.
3. Restituisce `None` se l'animale non è presente.

### `elimina(zoo, nome)`

**Descrizione:**
Elimina l'animale con nome `nome` dal dizionario `zoo`.

**Parametri:**
- `zoo`: il dizionario.
- `nome`: il nome dell'animale da eliminare.

**Ritorna:**
- `True` se l'eliminazione è avvenuta con successo.
- `False` se l'animale non è presente nel dizionario.

**Corpo della funzione:**
1. Verifica se il `nome` è presente nel dizionario.
2. Elimina l'animale dal dizionario se presente.
3. Restituisce `True` se l'eliminazione è avvenuta con successo.
4. Restituisce `False` se l'animale non è presente.

### `cambia_zona(zoo, nome, zona)`

**Descrizione:**
Cambia la zona dell'animale con nome `nome`.

**Parametri:**
- `zoo`: il dizionario.
- `nome`: il nome dell'animale da spostare.
- `zona`: la nuova zona in cui si trova l'animale.

**Ritorna:**
- `True` se lo spostamento è avvenuto con successo.
- `False` se l'animale non è presente nel dizionario o la zona non è corretta.

**Corpo della funzione:**
1. Verifica che `zona` sia una stringa composta da una lettera maiuscola seguita da un numero intero.
2. Verifica che il `nome` sia presente nel dizionario.
3. Aggiorna la zona dell'animale nel dizionario.
4. Restituisce `True` se lo spostamento è avvenuto con successo.
5. Restituisce `False` se l'animale non è presente o la zona non è corretta.

### `zone(zoo)`

**Descrizione:**
Restituisce la lista delle zone presenti nel dizionario `zoo`.

**Parametri:**
- `zoo`: il dizionario.

**Ritorna:**
- La lista delle zone presenti nel dizionario `zoo`.

**Corpo della funzione:**
1. Inizializza un insieme vuoto `zone_lista`.
2. Itera su ogni animale nel dizionario e aggiunge la zona all'insieme.
3. Restituisce la lista delle zone ordinate alfabeticamente.

### `animali_zona(zoo, zona)`

**Descrizione:**
Restituisce la lista degli animali presenti nella zona `zona`.

**Parametri:**
- `zoo`: il dizionario.
- `zona`: la zona di interesse.

**Ritorna:**
- La lista degli animali presenti nella zona `zona`.

**Corpo della funzione:**
1. Inizializza una lista vuota `animali_in_zona`.
2. Itera su ogni animale nel dizionario e verifica se la zona corrisponde.
3. Aggiunge il nome dell'animale alla lista se la zona corrisponde.
4. Restituisce la lista degli animali presenti nella zona.

### `zone_animali(zoo)`

**Descrizione:**
Restituisce un dizionario che ha come chiavi le zone e come valori la lista degli animali presenti in quella zona.

**Parametri:**
- `zoo`: il dizionario.

**Ritorna:**
- Il dizionario con le zone e gli animali presenti in ciascuna zona.

**Corpo della funzione:**
1. Inizializza un dizionario vuoto `dict_zone`.
2. Itera su ogni animale nel dizionario.
3. Aggiunge la zona come chiave nel dizionario e l'animale alla lista dei valori corrispondente.
4. Restituisce il dizionario con le zone e gli animali presenti in ciascuna zona.

### `animali_classe(zoo, classe)`

**Descrizione:**
Restituisce la lista degli animali della classe `classe`.

**Parametri:**
- `zoo`: il dizionario.
- `classe`: la classe di interesse.

**Ritorna:**
- La lista degli animali della classe `classe`.

**Corpo della funzione:**
1. Inizializza una lista vuota `animali_in_classe`.
2. Itera su ogni animale nel dizionario e verifica se la classe corrisponde.
3. Aggiunge il nome dell'animale alla lista se la classe corrisponde.
4. Restituisce la lista degli animali della classe.

### `animali_specie(zoo, specie)`

**Descrizione:**
Restituisce la lista degli animali della specie `specie`.

**Parametri:**
- `zoo`: il dizionario.
- `specie`: la specie di interesse.

**Ritorna:**
- La lista degli animali della specie `specie`.

**Corpo della funzione:**
1. Inizializza una lista vuota `animali_in_specie`.
2. Itera su ogni animale nel dizionario e verifica se la specie corrisponde.
3. Aggiunge il nome dell'animale alla lista se la specie corrisponde.
4. Restituisce la lista degli animali della specie.

### `animali_ambiente(zoo, ambiente)`

**Descrizione:**
Restituisce la lista degli animali che vivono nell'ambiente `ambiente`.

**Parametri:**
- `zoo`: il dizionario.
- `ambiente`: l'ambiente di interesse.

**Ritorna:**
- La lista degli animali che vivono nell'ambiente `ambiente`.

**Corpo della funzione:**
1. Inizializza una lista vuota `animali_in_ambiente`.
2. Itera su ogni animale nel dizionario e verifica se l'ambiente corrisponde.
3. Aggiunge il nome dell'animale alla lista se l'ambiente corrisponde.
4. Restituisce la lista degli animali che vivono nell'ambiente.

### `animali_con_zampe_almeno(zoo, numero_zampe=2)`

**Descrizione:**
Restituisce la lista degli animali che hanno almeno `numero_zampe` zampe.

**Parametri:**
- `zoo`: il dizionario.
- `numero_zampe`: il numero minimo di zampe (default=2).

**Ritorna:**
- La lista degli animali che hanno almeno `numero_zampe` zampe.

**Corpo della funzione:**
1. Inizializza una lista vuota `animali_2_zampe`.
2. Itera su ogni animale nel dizionario e verifica se il numero di zampe è maggiore o uguale a `numero_zampe`.
3. Aggiunge il nome dell'animale alla lista se il numero di zampe è maggiore o uguale a `numero_zampe`.
4. Restituisce la lista degli animali che hanno almeno `numero_zampe` zampe.

### `conta_sangue(zoo, sangue_caldo)`

**Descrizione:**
Restituisce il numero di animali con sangue caldo o freddo.

**Parametri:**
- `zoo`: il dizionario.
- `sangue_caldo`: `True` se si vogliono contare gli animali con sangue caldo, `False` altrimenti.

**Ritorna:**
- Il numero di animali con sangue caldo o freddo.

**Corpo della funzione:**
1. Inizializza una variabile `count` a 0.
2. Itera su ogni animale nel dizionario e verifica se il sangue è caldo o freddo.
3. Incrementa `count` se il sangue corrisponde.
4. Restituisce il numero di animali con sangue caldo o freddo.

### `conta_classe(zoo, classe)`

**Descrizione:**
Restituisce il numero di animali della classe `classe`.

**Parametri:**
- `zoo`: il dizionario.
- `classe`: la classe di interesse.

**Ritorna:**
- Il numero di animali della classe `classe`.

**Corpo della funzione:**
1. Inizializza una variabile `count` a 0.
2. Itera su ogni animale nel dizionario e verifica se la classe corrisponde.
3. Incrementa `count` se la classe corrisponde.
4. Restituisce il numero di animali della classe.

### `conta_specie(zoo, specie)`

**Descrizione:**
Restituisce il numero di animali della specie `specie`.

**Parametri:**
- `zoo`: il dizionario.
- `specie`: la specie di interesse.

**Ritorna:**
- Il numero di animali della specie `specie`.

**Corpo della funzione:**
1. Inizializza una variabile `count` a 0.
2. Itera su ogni animale nel dizionario e verifica se la specie corrisponde.
3. Incrementa `count` se la specie corrisponde.
4. Restituisce il numero di animali della specie.

### `conteggio(zoo, x)`

**Descrizione:**
Restituisce il numero di animali che soddisfano il parametro `x`.

**Parametri:**
- `zoo`: il dizionario.
- `x`: il parametro di interesse.

**Ritorna:**
- Il numero di animali che soddisfano il parametro `x`.

**Corpo della funzione:**
1. Inizializza una variabile `count` a 0.
2. Itera su ogni animale nel dizionario e verifica se uno degli attributi corrisponde a `x`.
3. Incrementa `count` se uno degli attributi corrisponde.
4. Restituisce il numero di animali che soddisfano il parametro `x`.


## Documentazione della Classe `Animale` e delle Sue Sottoclassi

Questo file contiene la definizione della classe `Animale` e delle sue sottoclassi, che rappresentano diverse categorie di animali. Ogni classe ha metodi per gestire lo stato degli animali, inclusi costruttori, getter, setter, e metodi per la rappresentazione testuale e l'uguaglianza profonda.

### Classe `Animale`

**Stato:**
- `nome`: stringa non vuota
- `sangue_caldo`: booleano
- `numero_zampe`: intero non negativo
- `verso`: stringa
- `ambiente`: lista di stringhe contenente almeno uno fra "Terra", "Acqua", "Aria"

**Metodi:**
- **Costruttore (`__init__`)**: Inizializza gli attributi dello stato controllando tipi e valori, sollevando eccezioni `TypeError` e `ValueError` se necessario.
- **Getter**: Metodi per restituire gli attributi dello stato singolarmente.
  - `get_nome()`
  - `get_sangue()`
  - `get_zampe()`
  - `get_verso()`
  - `get_ambiente()`
- **Setter**: Metodi per modificare gli attributi dell'animale singolarmente, controllando tipi e valori, sollevando eccezioni `TypeError` e `ValueError` se necessario.
  - `set_nome(nome)`
  - `set_sangue(sangue_caldo)`
  - `set_numero_zampe(numero_zampe)`
  - `set_verso(verso)`
  - `set_ambiente(ambiente)`
- **`__str__`**: Restituisce una stringa rappresentante l'animale.
- **`__eq__`**: Uguaglianza profonda fra animali.

**Corpo della Classe:**
1. **Controllo dei Tipi e dei Valori**:
   - Verifica che `nome` sia una stringa non vuota.
   - Verifica che `sangue_caldo` sia un booleano.
   - Verifica che `numero_zampe` sia un intero non negativo.
   - Verifica che `verso` sia una stringa.
   - Verifica che `ambiente` sia una lista di stringhe non vuota e che ogni elemento sia uno fra "Terra", "Acqua", "Aria".

2. **Assegnamento degli Attributi**:
   - Assegna i valori controllati agli attributi dell'istanza.

3. **Metodi Getter e Setter**:
   - Implementa i metodi getter e setter per ogni attributo, controllando tipi e valori nei setter.

4. **Metodo `__str__`**:
   - Costruisce una stringa descrittiva dell'animale, gestendo casi speciali come animali senza zampe o senza verso.

5. **Metodo `__eq__`**:
   - Implementa l'uguaglianza profonda tra due istanze di `Animale`.

### Sottoclassi di `Animale`

#### Classe `Mammifero`

**Estende**: `Animale`

**Stato Aggiuntivo**:
- `settimane_gestazione`: intero positivo

**Metodi Aggiuntivi**:
- **Costruttore (`__init__`)**: Inizializza gli attributi ereditati e controlla i valori e tipi degli attributi aggiuntivi.
- **Getter e Setter**: Metodi per gli attributi aggiuntivi.
  - `get_settimane_gestazione()`
  - `set_settimane_gestazione(settimane)`
- **`__eq__`**: Uguaglianza profonda che controlla anche gli attributi aggiuntivi.
- **`__str__`**: Estende la descrizione dell'animale con le settimane di gestazione.

#### Classe `Uccello`

**Estende**: `Animale`

**Stato Aggiuntivo**:
- `volatile`: booleano

**Metodi Aggiuntivi**:
- **Costruttore (`__init__`)**: Inizializza gli attributi ereditati e controlla i valori e tipi degli attributi aggiuntivi.
- **Getter e Setter**: Metodi per gli attributi aggiuntivi.
  - `get_volatile()`
  - `set_volatile(volo)`
- **`__eq__`**: Uguaglianza profonda che controlla anche gli attributi aggiuntivi.
- **`__str__`**: Estende la descrizione dell'animale con l'informazione se sa volare o no.

#### Classe `Pesce`

**Estende**: `Animale`

**Stato Aggiuntivo**:
- `acqua`: stringa fra "Dolce" e "Salata"

**Metodi Aggiuntivi**:
- **Costruttore (`__init__`)**: Inizializza gli attributi ereditati e controlla i valori e tipi degli attributi aggiuntivi.
- **Getter e Setter**: Metodi per gli attributi aggiuntivi.
  - `get_acqua()`
  - `set_acqua(azzurra)`
- **`__eq__`**: Uguaglianza profonda che controlla anche gli attributi aggiuntivi.
- **`__str__`**: Estende la descrizione dell'animale con il tipo di acqua.

### Sottoclassi delle Specie Animali

#### Classe `Leone`

**Estende**: `Mammifero`

**Metodi Aggiuntivi**:
- **`file_str`**: Restituisce una stringa formattata per la scrittura su file.

#### Classe `Giraffa`

**Estende**: `Mammifero`

**Metodi Aggiuntivi**:
- **`file_str`**: Restituisce una stringa formattata per la scrittura su file.

#### Classe `Ippopotamo`

**Estende**: `Mammifero`

**Metodi Aggiuntivi**:
- **`file_str`**: Restituisce una stringa formattata per la scrittura su file.

#### Classe `Pinguino`

**Estende**: `Uccello`

**Metodi Aggiuntivi**:
- **`file_str`**: Restituisce una stringa formattata per la scrittura su file.

#### Classe `Gufo`

**Estende**: `Uccello`

**Metodi Aggiuntivi**:
- **`file_str`**: Restituisce una stringa formattata per la scrittura su file.

#### Classe `PescePagliaccio`

**Estende**: `Pesce`

**Metodi Aggiuntivi**:
- **`file_str`**: Restituisce una stringa formattata per la scrittura su file.

### Introduzione al File GUI

Il file GUI implementa una GUI (Graphical User Interface / Interfaccia Utente Grafica) per la gestione di uno zoo utilizzando la libreria `tkinter` in Python. Questa applicazione permette agli utenti di eseguire varie operazioni come l'inserimento di nuovi animali, la modifica della zona di un animale, la visualizzazione delle informazioni di un animale, e altre operazioni di gestione dello zoo. La GUI è progettata per essere intuitiva e fornire feedback all'utente in caso di errori o input non validi.

### Struttura del File

Il file è strutturato in una classe principale `ZooApp` che contiene tutti i metodi necessari per gestire l'interfaccia utente e le operazioni dello zoo. Ecco una panoramica delle principali sezioni del file:

1. **Importazioni**:
   - Importa le funzioni e le classi necessarie dai moduli `zoo` e `animali`.
   - Importa la libreria `tkinter` per la creazione della GUI.

2. **Classe `ZooApp`**:
   - Contiene il costruttore `__init__` per inizializzare l'applicazione.
   - Contiene il metodo `crea_widgets` per creare i widget dell'interfaccia utente.
   - Contiene vari metodi per gestire le operazioni dello zoo, come l'inserimento di animali, la modifica delle zone, la visualizzazione delle informazioni, e il salvataggio/caricamento dei dati.

3. **Metodi della Classe `ZooApp`**:
   - `aggiorna_lista_animali`: Aggiorna la lista degli animali visualizzati nella GUI.
   - `aggiungi_animale`: Aggiunge un nuovo animale allo zoo.
   - `modifica_zona`: Modifica la zona di un animale esistente.
   - `mostra_stringa_animale`: Mostra una descrizione testuale di un animale.
   - `lista_nomi_specie`: Mostra una lista di nomi di animali appartenenti a una specie specifica.
   - `list_nomi_ambiente`: Mostra una lista di nomi di animali che vivono in un determinato ambiente.
   - `conta_animali_classe`: Conta il numero di animali appartenenti a una classe specifica.
   - `carica_zoo`: Carica i dati dello zoo da un file di testo.
   - `salva_zoo`: Salva i dati dello zoo su un file di testo.
   - `uscita_app`: Chiude l'applicazione.

### Dettagli delle Funzioni

#### `__init__(self, root)`

**Descrizione:**
Inizializza l'applicazione ZooApp.

**Parametri:**
- `root`: La finestra principale dell'applicazione tkinter.

**Corpo della funzione:**
1. Imposta il titolo della finestra principale.
2. Inizializza il dizionario `zoo` per memorizzare gli animali.
3. Chiama il metodo `crea_widgets` per creare l'interfaccia utente.

#### `crea_widgets(self)`

**Descrizione:**
Crea i widget dell'interfaccia utente.

**Corpo della funzione:**
1. Crea un frame per visualizzare gli animali con una `Listbox` e una barra di scorrimento.
2. Crea un frame per i pulsanti delle operazioni.
3. Aggiunge pulsanti per le seguenti operazioni:
   - Aggiungi Animale
   - Modifica Zona
   - Mostra Animale
   - Lista per Specie
   - Lista per Ambiente
   - Numero per Classe
   - Carica Zoo
   - Salva Zoo
   - Esci
4. Chiama il metodo `aggiorna_lista_animali` per popolare la lista degli animali.

#### `aggiorna_lista_animali(self)`

**Descrizione:**
Aggiorna la `Listbox` con gli animali presenti nello zoo, divisi per zona.

**Corpo della funzione:**
1. Cancella tutti gli elementi attuali nella `Listbox`.
2. Crea un dizionario `zone_animali` per raggruppare gli animali per zona.
3. Itera su ogni animale nel dizionario `zoo` e aggiunge il nome dell'animale alla lista corrispondente alla sua zona.
4. Aggiunge gli elementi alla `Listbox` in ordine alfabetico per zona.

#### `aggiungi_animale(self)`

**Descrizione:**
Aggiunge un nuovo animale allo zoo.

**Corpo della funzione:**
1. Raccoglie informazioni sull'animale tramite dialoghi di input:
   - Nome
   - Specie
   - Numero di zampe
   - Verso
   - Ambiente
   - Sangue caldo
   - Zona
2. Verifica la validità dei dati inseriti.
3. Crea un'istanza della classe appropriata (`Leone`, `Giraffa`, `Ippopotamo`, `Pinguino`, `Gufo`, `PescePagliaccio`) e la aggiunge al dizionario `zoo`.
4. Aggiorna la lista degli animali.

#### `modifica_zona(self)`

**Descrizione:**
Modifica la zona di un animale esistente.

**Corpo della funzione:**
1. Raccoglie il nome dell'animale e la nuova zona tramite dialoghi di input.
2. Verifica la validità della nuova zona.
3. Aggiorna la zona dell'animale nel dizionario `zoo`.
4. Aggiorna la lista degli animali.

#### `mostra_stringa_animale(self)`

**Descrizione:**
Mostra una descrizione testuale di un animale dato il suo nome.

**Corpo della funzione:**
1. Raccoglie il nome dell'animale tramite un dialogo di input.
2. Verifica se l'animale esiste nel dizionario `zoo`.
3. Mostra la descrizione dell'animale in una finestra di messaggio.

#### `lista_nomi_specie(self)`

**Descrizione:**
Mostra una lista di nomi di animali appartenenti a una specie specifica.

**Corpo della funzione:**
1. Raccoglie la specie tramite un dialogo di input.
2. Verifica la validità della specie.
3. Crea una lista di nomi di animali appartenenti alla specie specificata.
4. Mostra la lista in una finestra di messaggio.

#### `list_nomi_ambiente(self)`

**Descrizione:**
Mostra una lista di nomi di animali che vivono in un determinato ambiente.

**Corpo della funzione:**
1. Raccoglie l'ambiente tramite un dialogo di input.
2. Verifica la validità dell'ambiente.
3. Crea una lista di nomi di animali che vivono nell'ambiente specificato.
4. Mostra la lista in una finestra di messaggio.

#### `conta_animali_classe(self)`

**Descrizione:**
Conta il numero di animali appartenenti a una classe specifica.

**Corpo della funzione:**
1. Raccoglie la classe tramite un dialogo di input.
2. Verifica la validità della classe.
3. Conta il numero di animali appartenenti alla classe specificata.
4. Mostra il numero in una finestra di messaggio.

#### `carica_zoo(self)`

**Descrizione:**
Carica i dati dello zoo da un file di testo.

**Corpo della funzione:**
1. Apre una finestra di dialogo per selezionare il file da caricare.
2. Legge il file e aggiunge gli animali al dizionario `zoo`.
3. Aggiorna la lista degli animali.

#### `salva_zoo(self)`

**Descrizione:**
Salva i dati dello zoo su un file di testo.

**Corpo della funzione:**
1. Apre una finestra di dialogo per selezionare il file in cui salvare i dati.
2. Scrive i dati degli animali nel file.

#### `uscita_app(self)`

**Descrizione:**
Chiude la finestra principale e termina l'applicazione.

**Corpo della funzione:**
1. Chiama il metodo `destroy` della finestra principale per chiudere l'applicazione.

### Come si utilizza una GUI in python?

Per utilizzare questa classe, si crea un'istanza di `ZooApp` passando la finestra principale di `tkinter` come argomento. Quindi, bisogna avviare il loop principale di `tkinter` per visualizzare la GUI e gestire gli eventi.

```python
if __name__ == "__main__":
    root = tk.Tk()
    app = ZooApp(root)
    root.mainloop()
```

### Introduzione al File `zoo.py`

Il file `zoo.py` implementa una classe `Zoo` che gestisce un dizionario di animali. Ogni animale è rappresentato da un oggetto della classe `Animale` o una delle sue sottoclassi, e ogni animale è associato a una zona specifica nello zoo. La classe `Zoo` fornisce vari metodi per aggiungere, modificare, eliminare e interrogare gli animali nel dizionario, nonché per salvare e caricare lo stato dello zoo da un file.

### Struttura del File

Il file è strutturato nella classe `Zoo` che contiene tutti i metodi necessari per gestire il dizionario degli animali e le operazioni dello zoo. Ecco una panoramica delle principali sezioni del file:

1. **Importazioni**:
   - Importa le classi necessarie dal modulo `animali`.

2. **Classe `Zoo`**:
   - Contiene il costruttore `__init__` per inizializzare il dizionario degli animali.
   - Contiene i metodi `__str__` e `__eq__` per rappresentare lo zoo come stringa e per l'uguaglianza profonda tra oggetti `Zoo`.
   - Contiene vari metodi per gestire le operazioni dello zoo, come l'inserimento di animali, la modifica delle zone, la visualizzazione delle informazioni, e il salvataggio/caricamento dei dati.

### Dettagli delle Funzioni

#### `__init__(self)`

**Descrizione:**
Inizializza l'oggetto `Zoo` creando un dizionario vuoto per memorizzare gli animali.

**Corpo della funzione:**
1. Inizializza il dizionario `zoo` come un dizionario vuoto.

#### `aggiungi_animale(self, nome, animale, zona)`

**Descrizione:**
Aggiunge un nuovo animale allo zoo.

**Parametri:**
- `nome`: Il nome dell'animale.
- `animale`: Un oggetto della classe `Animale` o una delle sue sottoclassi.
- `zona`: La zona in cui si trova l'animale (stringa composta da una lettera maiuscola seguita da un numero intero, es. "A1").

**Corpo della funzione:**
1. Verifica che `animale` sia un'istanza della classe `Animale`.
2. Verifica che `zona` sia una stringa nel formato corretto.
3. Aggiunge l'animale al dizionario `zoo` con il nome come chiave e una tupla (animale, zona) come valore.
4. Restituisce il dizionario `zoo` aggiornato.

#### `__str__(self)`

**Descrizione:**
Restituisce una stringa rappresentante lo zoo, utilizzando la rappresentazione stringa degli animali.

**Corpo della funzione:**
1. Inizializza una stringa vuota `descrizione`.
2. Itera su ogni animale nel dizionario `zoo` e aggiunge una descrizione dell'animale alla stringa `descrizione`.
3. Restituisce la stringa `descrizione` senza spazi finali.

#### `__eq__(self, other)`

**Descrizione:**
Implementa l'uguaglianza profonda tra due oggetti `Zoo`.

**Parametri:**
- `other`: Un altro oggetto `Zoo` da confrontare.

**Corpo della funzione:**
1. Verifica che `other` sia un'istanza della classe `Zoo`.
2. Verifica che i dizionari `zoo` di entrambi gli oggetti abbiano la stessa lunghezza.
3. Itera su ogni animale nel dizionario `zoo` e verifica che ogni animale e la sua zona corrispondano nell'altro dizionario.
4. Restituisce `True` se tutti gli animali e le zone corrispondono, altrimenti `False`.

#### `inserisci(self, animale, zona)`

**Descrizione:**
Inserisce un nuovo animale nel dizionario `zoo` evitando duplicati e verificando che i parametri abbiano il tipo corretto e siano nel range di valori ammessi.

**Parametri:**
- `animale`: Un oggetto della classe `Animale` o una delle sue sottoclassi.
- `zona`: La zona in cui si trova l'animale (stringa composta da una lettera maiuscola seguita da un numero intero, es. "A1").

**Corpo della funzione:**
1. Verifica che `animale` sia un'istanza della classe `Animale`.
2. Verifica che `zona` sia una stringa nel formato corretto.
3. Verifica che l'animale non sia già presente nel dizionario.
4. Aggiunge l'animale al dizionario `zoo`.

#### `animale(self, nome)`

**Descrizione:**
Restituisce l'oggetto animale con il nome specificato.

**Parametri:**
- `nome`: Il nome dell'animale da restituire.

**Corpo della funzione:**
1. Verifica che l'animale con il nome specificato sia presente nel dizionario.
2. Restituisce l'oggetto animale corrispondente.

#### `zona(self, nome)`

**Descrizione:**
Restituisce la zona in cui si trova l'animale con il nome specificato.

**Parametri:**
- `nome`: Il nome dell'animale di cui ottenere la zona.

**Corpo della funzione:**
1. Verifica che l'animale con il nome specificato sia presente nel dizionario.
2. Restituisce la zona corrispondente.

#### `elimina(self, nome)`

**Descrizione:**
Elimina l'animale con il nome specificato dal dizionario `zoo`.

**Parametri:**
- `nome`: Il nome dell'animale da eliminare.

**Corpo della funzione:**
1. Verifica che l'animale con il nome specificato sia presente nel dizionario.
2. Elimina l'animale dal dizionario.

#### `cambia_zona(self, nome, zona)`

**Descrizione:**
Cambia la zona dell'animale con il nome specificato.

**Parametri:**
- `nome`: Il nome dell'animale da spostare.
- `zona`: La nuova zona in cui si trova l'animale (stringa composta da una lettera maiuscola seguita da un numero intero, es. "A1").

**Corpo della funzione:**
1. Verifica che l'animale con il nome specificato sia presente nel dizionario.
2. Verifica che `zona` sia una stringa nel formato corretto.
3. Aggiorna la zona dell'animale nel dizionario.
4. Restituisce la tupla (animale, zona) aggiornata.

#### `zone(self)`

**Descrizione:**
Restituisce la lista delle zone presenti nel dizionario `zoo`.

**Corpo della funzione:**
1. Inizializza una lista vuota `lista`.
2. Itera su ogni animale nel dizionario e aggiunge la zona alla lista.
3. Restituisce la lista delle zone senza duplicati.

#### `animali_zona(self, zona)`

**Descrizione:**
Restituisce la lista dei nomi degli animali presenti nella zona specificata.

**Parametri:**
- `zona`: La zona di interesse.

**Corpo della funzione:**
1. Inizializza una lista vuota `lista`.
2. Itera su ogni animale nel dizionario e aggiunge il nome dell'animale alla lista se la zona corrisponde.
3. Restituisce la lista dei nomi degli animali nella zona specificata.

#### `zone_animali(self)`

**Descrizione:**
Restituisce un dizionario che ha come chiavi le zone e come valori la lista degli animali presenti in quella zona.

**Corpo della funzione:**
1. Inizializza un dizionario vuoto `dict_zone`.
2. Itera su ogni animale nel dizionario e aggiunge la zona come chiave nel dizionario e l'animale alla lista dei valori corrispondente.
3. Restituisce il dizionario con le zone e gli animali presenti in ciascuna zona.

#### `animali_classe(self, classe)`

**Descrizione:**
Restituisce la lista dei nomi degli animali della classe specificata.

**Parametri:**
- `classe`: La classe di interesse (es. Mammifero).

**Corpo della funzione:**
1. Inizializza una lista vuota `lista_nomi`.
2. Verifica che `classe` sia una stringa.
3. Itera su ogni animale nel dizionario e aggiunge il nome dell'animale alla lista se la classe corrisponde.
4. Verifica che la classe sia una delle classi esistenti.
5. Restituisce la lista dei nomi degli animali della classe specificata.

#### `animali_specie(self, specie)`

**Descrizione:**
Restituisce la lista dei nomi degli animali della specie specificata.

**Parametri:**
- `specie`: La specie di interesse (es. Leone).

**Corpo della funzione:**
1. Inizializza una lista vuota `lista_nomi`.
2. Verifica che `specie` sia una stringa.
3. Itera su ogni animale nel dizionario e aggiunge il nome dell'animale alla lista se la specie corrisponde.
4. Restituisce la lista dei nomi degli animali della specie specificata.

#### `animali_ambiente(self, ambiente)`

**Descrizione:**
Restituisce la lista dei nomi degli animali che vivono nell'ambiente specificato.

**Parametri:**
- `ambiente`: L'ambiente di interesse (es. Terra).

**Corpo della funzione:**
1. Inizializza una lista vuota `lista_nomi`.
2. Verifica che `ambiente` sia una stringa.
3. Itera su ogni animale nel dizionario e aggiunge il nome dell'animale alla lista se l'ambiente corrisponde.
4. Verifica che l'ambiente sia uno degli ambienti esistenti.
5. Restituisce la lista dei nomi degli animali che vivono nell'ambiente specificato.

#### `animali_con_zampe_almeno(self, numero_zampe=2)`

**Descrizione:**
Restituisce la lista dei nomi degli animali che hanno almeno `numero_zampe` zampe.

**Parametri:**
- `numero_zampe`: Il numero minimo di zampe (default=2).

**Corpo della funzione:**
1. Inizializza una lista vuota `lista_nomi`.
2. Verifica che `numero_zampe` sia un intero non negativo.
3. Itera su ogni animale nel dizionario e aggiunge il nome dell'animale alla lista se il numero di zampe è maggiore o uguale a `numero_zampe`.
4. Restituisce la lista dei nomi degli animali che hanno almeno `numero_zampe` zampe.

#### `conta_sangue(self, sangue_caldo)`

**Descrizione:**
Restituisce il numero di animali con sangue caldo o freddo.

**Parametri:**
- `sangue_caldo`: `True` se si vogliono contare gli animali con sangue caldo, `False` altrimenti.

**Corpo della funzione:**
1. Inizializza una variabile `count` a 0.
2. Verifica che `sangue_caldo` sia un booleano.
3. Itera su ogni animale nel dizionario e incrementa `count` se il sangue corrisponde.
4. Restituisce il numero di animali con sangue caldo o freddo.

#### `conta_classe(self, classe)`

**Descrizione:**
Restituisce il numero di animali della classe specificata.

**Parametri:**
- `classe`: La classe di interesse (es. Mammifero).

**Corpo della funzione:**
1. Inizializza una variabile `count` a 0.
2. Verifica che `classe` sia una stringa.
3. Itera su ogni animale nel dizionario e incrementa `count` se la classe corrisponde.
4. Verifica che la classe sia una delle classi esistenti.
5. Restituisce il numero di animali della classe specificata.

#### `conta_specie(self, specie)`

**Descrizione:**
Restituisce il numero di animali della specie specificata.

**Parametri:**
- `specie`: La specie di interesse (es. Leone).

**Corpo della funzione:**
1. Inizializza una variabile `count` a 0.
2. Verifica che `specie` sia una stringa.
3. Itera su ogni animale nel dizionario e incrementa `count` se la specie corrisponde.
4. Restituisce il numero di animali della specie specificata.

#### `salva(self, nome_file)`

**Descrizione:**
Salva lo stato dell'oggetto `Zoo` in un file di testo.

**Parametri:**
- `nome_file`: Il nome del file in cui salvare lo stato.

**Corpo della funzione:**
1. Apre il file in modalità scrittura.
2. Itera su ogni animale nel dizionario e scrive i dettagli dell'animale nel file.
3. Chiude il file.

#### `carica(self, nome_file)`

**Descrizione:**
Carica lo stato dell'oggetto `Zoo` da un file di testo, sovrascrivendo lo stato corrente se il caricamento va a buon fine.

**Parametri:**
- `nome_file`: Il nome del file da cui caricare lo stato.

**Corpo della funzione:**
1. Inizializza il dizionario `zoo` come un dizionario vuoto.
2. Apre il file in modalità lettura.
3. Itera su ogni riga del file, estrae i dettagli dell'animale e lo aggiunge al dizionario `zoo`.
4. Verifica che il file sia nel formato corretto.
5. Chiude il file.

### Esempio di Utilizzo

Per utilizzare la classe `Zoo`, si crea un'istanza della classe e si chiamano i metodi appropriati per gestire gli animali nello zoo. Ecco un esempio di come utilizzare la classe:

```python
zoo = Zoo()
leone = Leone("Simba", True, 4, "Ruggito", ["Terra"], 7)
zoo.inserisci(leone, "A1")
print(zoo)
zoo.salva("zoo_salvato.txt")
```

