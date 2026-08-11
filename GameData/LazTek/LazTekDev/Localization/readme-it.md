---
permalink: /readme-it.html
title: Istruzioni per la localizzazione e la traduzione
---
<!-- readme-it.md v2.1.2.0
Localization project
created: 01 Jan 2018
updated: 13 May 2022  -->

<!--da: @HebruSan (grazie) ![link](https://github.com/HebaruSan/Astrogator/tree/master/assets/lang)  -->

# Tradurre nella tua lingua
![Lingue supportate da KSP 1.3: Inglese, Spagnolo, Cinese, Russo, Giapponese](https://i.imgur.com/DbCCJWK.png)

La versione 1.3 di KSP introduce la localizzazione, che consente al testo in gioco di essere tradotto in altre lingue. Questo permette a più persone di utilizzare il gioco nella lingua che preferiscono e di allargare la community. Nonostante ciò, questo non accade automaticamente per le mod; di default, una mod appare in inglese perché è la lingua base del gioco. Per avere sia il gioco base sia le modifiche disponibili nella stessa lingua che non è l'inglese, è necessario lavoro extra da parte del modder.

Sfortunatamente parlo solo inglese e mantengo questa mod gratuitamente. Ciò significa che non posso essere io a fare le traduzioni e non posso pagare un servizio di traduzione professionale per avere traduzioni di qualità. Il meglio che posso fare da solo è usare Google Traduttore, che è di dubbio valore per le frasi brevi e idiomatiche che servono per la UI delle mod di KSP. Di conseguenza, mi affido a voi che siete esperti, gli utenti multilingue delle mod KSP, per dirmi quali sono le traduzioni migliori per la vostra lingua. Se desideri aiutare in questo lavoro, allora ti consiglio di continuare a leggere per capire come sono strutturati i file linguistici della mod e come inviare le traduzioni in modo che siano utilizzabili da altri.

Nota: Anche se ti sembrerà di modificare i file di progetto, non preoccuparti di commettere errori. GitHub manterrà separate le tue modifiche dai file principali fino a che non avrò verificato che siano pronti e corretti per essere utilizzati. Inoltre è possibile che io faccia domande o richieda modifiche prima che il tuo lavoro sia trasferito sui file principali.

## Lingue

* Supportate da Kerbal Space Program a partire da 1.12.x
  * ![English][EN] Inglese <en-us.cfg>
  * ![Brasil][BR] Brasiliano <pt-br.cfg>
  * ![中文][CN] Cinese semplificato (中文) <zh-cn.cfg>
  * ![Deutsch][DE] Tedesco (Deutsch) <de.cfg>
  * ![Español][ES] Spagnolo (Español) <es-es.cfg>
  * ![Français][FR] Francese (Français)<fr-fr.cfg>
  * ![Italiano][IT] Italiano (Italiano) <it-it.cfg>
  * ![日本語][JA] Giapponese (日本語) <ja.cfg>
* Incluse
  * ![한국어][KO] Coreano (한국어) <ko.cfg>
  * ![Español Mexicano][MX] Spagnolo Messicano (Español Mexicano) <es-mx.cfg>
  * ![Dutch][NL] Olandese <nl-nl.cfg>
  * ![Norsk][NO] Norvegese (Norsk) <no-no.cfg>
  * ![Polski][PO] Polacco (Polski) <pl.cfg>
  * ![Русский][RU] Russo (Русский) <ru.cfg>
  * ![Svenska][SW] Svedese (Svenska) <sw-sw.cfg>
  * ![国语][TW] Thailandese (国语) <zh-tw.cfg>

## Creare o modificare una traduzione

È consigliato effettuare inizialmente le tue modifiche sul tuo computer così che tu possa testarle prima di caricarle, specialmente se stai facendo una traduzione da zero.

1. Se non lo hai già fatto installa la versione corrente della xxx mod
2. Apri la tua cartella `<KSP_ROOT>/GameData/xxxMod/Localization` sul tuo disco locale
3. Cerca un file chiamato *lang*.cfg, dove *lang* è il nome di KSP in locale; per KSP 1.3, questo include:

* en-us (English)
* es-es (Spanish)
* ja (Japanese)
* ru (Russian)
* zh-cn (Chinese)

I prossimi passi sono diversi a seconda che il file sia già esistente o meno:

### Se il file esiste

Segui questi passi per migliorare una traduzione esistente:

4. Modifica il file relativo alla tua lingua nell'editor di testo che preferisci
5. Fai le modifiche che desideri vedere in gioco (vedi la [Sezione Formato File](#formato-file) sottostante per i dettagli)
6. Salva le tue modifiche
7. Ricorda di [testare le tue modifiche](#testing)!

### Se il file non esiste

Segui questi passi per iniziare la tua traduzione da zero:

4. Fai una copia di `en-us.cfg` nella cartella `Localization`
5. Rinomina il file seguendo la lista di lingue qui sopra
6. Modifica il file per la tua lingua nel tuo editor di testo preferito 
7. Cambia la terza riga da `en-us` nella frase per la tua lingua (vedi la [Sezione Lingue](#lingue) per i dettagli)
8. Traduci ogni frase dall'inglese nella tua lingua (vedi la [Sezione Formato File](#formato-file) sottostante per i dettagli)
9. Salva le tue modifiche 
10. Ricorda di [testare le tue modifiche](#testing)!

### Formato File

La parte centrale del file `cfg` contiene le frasi da tradurre. Il formato è  `parola = traduzione`, dove la parola è una frase specifica definita dalla mod. Per esempio:

    #launchSubtitle = Transfers from <<1>>\n(Launch ~<<2>>)

**NON** modificare la parte a sinistra del simbolo uguale ("=")! Queste parole devono essere le stesse in ogni file in lingua.

La parte a destra del simbolo uguale è la frase da utilizzare in gioco. La maggior parte del testo sarà mostrata così com'è, però potrebbero essere presenti alcuni elementi speciali come mostrato in [Lingoona grammar module demo](http://lingoona.com/cgi-bin/grammar#l=en&oh=1):

| Elemento| Significato                                                                                                                |
| ------- | -------------------------------------------------------------------------------------------------------------------------- |
| \n      | Interruzione di riga; cerca di preservarle basandoti sulla frase originale per essere sicuro che la frase sia compatibile  |
| <<1>>   | Il primo token sostituibile nella stringa, sarà sostituito da un numero, il nome di un pianeta, ecc., in base alla stringa  |
| <<2>>   | Secondo token, e così via                                                                                                  |
| <<A:1>> | Il primo token, ma sostituito dal giusto articolo                                                                          |

Per esempio, questa è una possibile traduzione della riga sopra in Spagnolo, fatta da Google Traduttore:

    #launchSubtitle = Transferencias desde <<1>>\n(Lanzamiento ~<<2>>)

### Testing

È importante assicurarsi che le modifiche al lavoro siano corrette. Se usi Steam:  
1. [Seleziona la lingua da usare in Steam](https://www.youtube.com/watch?v=iBwYCvQxfeI)
2. Attendi che il download del pacchetto linguistico sia completato
3. Esegui KSP
4. Utilizza la xxxMod in gioco e assicurati che i tuoi cambiamenti appaiano correttamente

Se non usi Steam, non conosco i passaggi per scegliere la lingua. Contatta SQUAD nel caso tu abbia difficoltà.

## Rendere disponibile la tua traduzione per l'utilizzo da parte di altri

Dopo aver preparato un file `cfg` per la tua lingua e confermato che funzioni correttamente, se decidi di renderlo disponibile per la ridistribuzione sotto la licenza della xxxMod, segui questi passaggi per caricarlo per essere incluso nella distribuzione della mod principale:

1. Accedi a [GitHub](https://github.com); potresti dover registrare un account se non ne possiedi già uno
2. Apri la cartella Localization per la xxxMod
3. Cerca il file che hai modificato

I restanti passaggi sono diversi a seconda che il file esista o meno:

### Se il file esiste

4. Fai click sul nome del file per visionarlo
5. Premi [l'icona della matita](https://help.github.com/assets/images/help/repository/edit-file-edit-button.png) per modificare
6. Rimpiazza il testo con il contenuto copiato del file che hai modificato localmente
7. **Importante**: Alla fine della pagina, sotto a Proponi una modifica al file, scrivi una descrizione in inglese delle modifiche effettuate e le ragioni che le giustificano. Questo mi aiuterà a confermare che le tue modifiche siano appropriate. Ricorda che non parlo la lingua del file `cfg`, quindi ho bisogno che tu mi spieghi perché le tue scelte sono le migliori!
8. Quando hai finito fai click su `Propose file change` alla fine della pagina

### Se il file non esiste

4. Fai click su [Crea nuovo file](https://help.github.com/assets/images/help/repository/create_new_file.png) per crearlo
5. Inserisci il nome del file corretto nel box sopra
6. Copia i contenuti del file modificato localmente nel grande box al centro
7. Quando hai finito premi `Propose new file` alla fine della pagina

### Revisione

Una volta terminate le modifiche, GitHub mi invierà una notifica che è stata inviata una 'pull request'. Darò un'occhiata al lavoro nel giro di un giorno o due e verificherò che le modifiche siano coerenti, in questo modo:

* Confermando che il nome del file e la terza riga del file siano coerenti con uno dei nomi supportati in locale
* Visionando in gioco ogni frase modificata
* Controllando con Google Traduttore
* Chiedendo a persone esperte
* Chiedendo aiuto al forum di KSP

Se avrò qualunque domanda riguardo ad una modifica specifica effettuata, le aggiungerò alla 'pull request', così dovrebbe arrivarti una notifica. Cerca per favore di rispondere in tempo utile. La tua 'pull request' potrà essere chiusa senza che le modifiche siano incluse, se non riceverò risposta per un lungo periodo.

Una volta che tutte le domande e i commenti saranno risolti secondo i miei standard, le tue modifiche saranno inserite nei file principali e incluse nel prossimo rilascio. Inoltre aggiungerò il tuo nome di GitHub alla sezione dei ringraziamenti ai collaboratori del file README.

[EN]: https://raw.githubusercontent.com/zer0Kerbal/zer0Kerbal/zed'K/img/EN.png "English"  
[BR]: https://raw.githubusercontent.com/zer0Kerbal/zer0Kerbal/zed'K/img/BR.png "Português Brasil"
[CN]: https://raw.githubusercontent.com/zer0Kerbal/zer0Kerbal/zed'K/img/CH.png "中文"  
[DE]: https://raw.githubusercontent.com/zer0Kerbal/zer0Kerbal/zed'K/img/DE.png "Deutsch"  
[ES]: https://raw.githubusercontent.com/zer0Kerbal/zer0Kerbal/zed'K/img/ES.png "Español"  
[FR]: https://raw.githubusercontent.com/zer0Kerbal/zer0Kerbal/zed'K/img/FR.png "Français"  
[IT]: https://raw.githubusercontent.com/zer0Kerbal/zer0Kerbal/zed'K/img/IT.png "Italiano"  
[JA]: https://raw.githubusercontent.com/zer0Kerbal/zer0Kerbal/zed'K/img/JA.png "日本語"  
[KO]: https://raw.githubusercontent.com/zer0Kerbal/zer0Kerbal/zed'K/img/KO.png "한국어"  
[MX]: https://raw.githubusercontent.com/zer0Kerbal/zer0Kerbal/zed'K/img/MX.png "Mexicano Español"  
[NL]: https://raw.githubusercontent.com/zer0Kerbal/zer0Kerbal/zed'K/img/NL.png "Dutch"  
[NO]: https://raw.githubusercontent.com/zer0Kerbal/zer0Kerbal/zed'K/img/NO.png "Norsk"
[PO]: https://raw.githubusercontent.com/zer0Kerbal/zer0Kerbal/zed'K/img/PO.png "Polski"  
[RU]: https://raw.githubusercontent.com/zer0Kerbal/zer0Kerbal/zed'K/img/RU.png "Русский"  
[SW]: https://raw.githubusercontent.com/zer0Kerbal/zer0Kerbal/zed'K/img/SW.png "Svenska"  
[TW]: https://raw.githubusercontent.com/zer0Kerbal/zer0Kerbal/zed'K/img/TW.png "国语"

<!-- CC BY-ND 4.0 by zer0Kerbal  -->
