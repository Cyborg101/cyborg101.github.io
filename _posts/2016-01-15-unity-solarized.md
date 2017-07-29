---
layout: post
title: Unity Solarized (Facciamo bello il nostro desktop)
description: Ecco come dare un tocco in più ad Ubuntu Unity. In questo post spiego come installare le icone numix, cambiare lo schema di colori al terminale e alla shell Unity.
---

Ecco come appare il mio Ubuntu Desktop:


<img src="{{ site.url }}/assets/solarizednumix.png" alt="My Unity Solarized Desktop" style="width: 500px;"/>

Non male, vero?

Ecco i passi che ho seguito per personalizzarlo:


Prima di tutto, aggiungi la ppa del Numix project.

{% highlight bash %}
sudo add-apt-repository ppa:numix/ppa
{% endhighlight %}

In seguito, installa le icone ed il tema

{% highlight bash %}
sudo apt-get install numix-gtk-theme numix-icon-theme-circle
{% endhighlight %}

Con il seguente comando, scarichi invece i vari wallpaper messi a disposizione gratuitamente

{% highlight bash %}
sudo apt-get install numix-wallpaper-*
{% endhighlight %}

In seguito, scarica la unity-tweak tool, che ti consentirà di configurare a puntino la shell di Canonical

{% highlight bash %}
sudo apt-get install unity-tweak-tool
{% endhighlight %}

Successivamente ti sarà sufficiente aprire la unity-tweak-tool (apparirà tra le applicazioni), andare sulla voce temi e cambiare il tema di default con quello numix. Sempre dalla unity tweak tool puoi selezionare le icone numix (io uso le icone numix circle).

Bene, ora il nostro Ubuntu ha un aspetto molto gradevole, ma possiamo fare di meglio.

Conosci lo schema di colori Solarized? E’ uno degli schemi più utilizzati in tutti gli editor, e francamente c’è un motivo. Quel che è meglio, è che qualcuno si è già sbattuto per rendere il numix theme “solarized”, e quindi possiamo farlo anche noi. Per farlo, scarica il file zip da questa pagina.

Una volta scaricato il file, spostati nella cartella documenti e decomprimilo.

{% highlight bash %}
unzip numix_solarized_by_bitterologist-d6wm3nc.zip
{% endhighlight %}

Muoviti nella cartella creata e sposta i temi in /usr/share/themes

{% highlight bash %}
cd Solarized theme/ mv Numix Solarized Light/   /usr/share/themes/

mv Numix Solarized/    /usr/share/themes/
{% endhighlight %}

Ora spostati nella cartella temi,  e rendi eseguibile il file accent_colors.sh che ti consentirà di scegliere quale colore verrà usato come evidenziatore.

{% highlight bash %}
sudo chmod +x accent_colors.sh sh accent_colors.sh
{% endhighlight %}

Seleziona il tuo colore preferito ed il gioco è fatto!
Ti basterà selezionare Numix Solarized con la Unity Tweak Tool e il tuo ubuntu sarà bellissimo! Anche i fan Apple sbaveranno di fronte a cotanta spietatissima beltà!
