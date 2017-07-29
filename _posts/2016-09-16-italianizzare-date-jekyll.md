---
layout: post
title: Italianizzare le date in Jekyll
description: Jekyll utilizza di default le date inglesi. Scopriamo come cambiarle in modo da mostrare date italiane.
thumbnail: /assets/calendario.jpg
img: /assets/calendario.jpg
image:
  path: /assets/calendario.jpg
  twitter: /assets/calendario.jpg
  facebook: //assets/calendario.jpg
  height: 300
  width: 300
---

Una modifiche obbligate che noi italiani dobbiamo fare per il nostro blog jekyll è quella di cambiare il formato delle date dei post. Infatti Jekyll utilizza di default i mesi in lingua inglese.
Ad esempio, la pagina che mostra gli ultimi post utilizza abbreviazioni dei mesi inglesi, tipo **Jan** o **Sep**, numero del giorno e anno. Noi italiani siamo invece abituati a numero del giorno, mese ed anno.
<img src="{{ site.url }}/assets/date-inglesi-brevi.png" alt="immagine esempio del sito"/>
Diamo un'occhiata al codice che genera le date visualizzate nell'immagine sopra.
{% gist Cyborg101/15f4e4c4fff1a7abca0d3234ef35f794 basic-date.html%}
Se volessimo una data italiana, vorremmo inanzitutto il giorno, selezionabile con l'opzione **%-d**, poi il nome del mese, che selezioneremo con uno **switch statement**, ed infine l'anno, **%Y**.
Ecco il codice completo.
{% gist Cyborg101/15f4e4c4fff1a7abca0d3234ef35f794 gistfile1.liquid%}
In breve, utilizziamo la variabile **m** per ottenere il numero del mese, e a seconda di quest'ultimo selezioniamo l'abbreviazione italiana del mese.
Ecco come cambiano le date
<img src="{{ site.url }}/assets/date-italiane-brevi.png" alt="immagine esempio del sito"/>
La stessa tecnica si può utilizzare se si vogliono i nomi dei mesi interi, o i nomi dei giorni.
