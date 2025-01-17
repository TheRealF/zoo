
 # TOC
[TOC]



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



