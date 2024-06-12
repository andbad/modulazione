Il sistema di modulazione è composto da un'automazione che richiama due script.
Si avvia quando viene collegata l'auto e in caso sia giorno, avvia lo script "solare", ovvero la modulazione vera e propria.
Se invece è notte, verifica se la produzione fotovoltaica prevista è sufficiente, in quel caso ricarica comunque prelevando da rete fino a raggiungere una percentuale di SOC minima, poi attende.
Se invece il giorno dopo la produzion prevista è insufficiente (farà brutto), ricarica fino alla percentuale di SOC massima impostata

L'automazione si interrompe al raggiungimento del SOC massimo impostato o quando l'auto viene scollegata.

Lo script "normale" verifica se vengono rispettati alcuni parametri (tensione di rete e differenza fra le fasi, visto che ho trifase) e che vi sia abbastanza potenza prelevabile da rete, in quel caso aumenta la potenza di mezzo Ampere.
Se anche uno dei parametri non viene rispettato (per esempio stiamo prelevando troppo da rete o la tensione è troppo bassa), riduce l'assorbimento di mezzo Ampere.
Se si raggiunge la corrente minima di ricarica di 6A, la ricarica viene sospesa in attesa che i parametri rientrino nei limiti, poi ricomincia a caricare.

Lo script "solare" fa le stesse cose ma prende in considerazione non la potenza massima del contatore ma la produzione del fotovoltaico, in modo da restare il più vicino possibile allo zero immissione.
Anche in questo caso controlla i parametri di tensione e sfasamento, oltre che lo stato dell'inverter.
