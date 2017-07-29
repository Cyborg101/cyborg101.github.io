---
layout: post
title: "Come creare una chiavetta di installazione Ubuntu"
description: "Hai bisogno di installare ubuntu sul tuo computer? Allora leggi questo articolo, che spiega come farlo attraverso una chiavetta usb."
---

Oggi vedremo come creare una chiavetta usb da cui possiamo installare Ubuntu.

Il procedimento è molto semplice. Prima di tutto scaricate la iso di Ubuntu da
[questa pagina](http://www.ubuntu-it.org/). Consiglio vivamente di scegliere la
versione 16.04 LTS.

## LINUX

1 – Aprite una finestra terminale, e convertite il file .iso in un file .img tramite hdiutil:
{% highlight bash %}
hdiutil convert -format UDRW -o /percorso/al/fileubuntu.img /percorso/al/fileubuntu.iso
{% endhighlight %}



2 - Inserite la chiavetta, e digitate il seguente comando

{% highlight bash %}
sudo fdisk -l
{% endhighlight %}

3 – Identificate il nome della chiavetta usb dove volete creare l’installer di Ubuntu(es. /dev/sdc). Smontatela con il seguente comando:

{% highlight bash %}
sudo unmount /dev/sdc
{% endhighlight %}

4 - Digitate il seguente comando per scrivere l’immagine ubuntu:

{% highlight bash %}
sudo dd if=/percorso/per/ubuntu.img of=/nome/chiavettausb bs=1M
{% endhighlight %}
A titolo di esempio, se il tuo file si trova in download e la tua chiavetta si chiama  /dev/sdc, allora il comando da digitare sarà

{% highlight bash %}
sudo dd if=~/Downloads/ubuntu.img of=/dev/sdc bs=1M
{% endhighlight %}

Bene, la vostra chiavetta è pronta!

## MACOS:

1 – Il procedimento è simile a quello in Linux. Aprite un terminale (potete cercarlo con spotlight, pigiando cmd+barra), e convertite il file .iso in un file .img tramite hdiutil:

{% highlight bash %}
hdiutil convert -format UDRW -o /percorso/al/fileubuntu.img /percorso/al/fileubuntu.iso
{% endhighlight %}

2 -  Nel caso in cui il file sia stato rinominato automaticamente in dmg, eseguite il seguente comando per rinominarlo nuovamente in .img:

{% highlight bash %}
mv /percorso/al/file.img.dmg /percorso/al/file.img
{% endhighlight %}

3 – Ora potete inserire la chiavetta usb e identificare il nome della chiavetta tramite il comando:

{% highlight bash %}
diskutil list
{% endhighlight %}

4 – Una volta identificato il nome della vostra chiavetta (ad esempio, /dev/disk2), procedere a digitare il comando

{% highlight bash %}
sudo diskutil unmountDisk /dev/disk2
{% endhighlight %}

5 – ora procedete a scrivere il file img nella chiavetta con il comando

{% highlight bash %}
sudo dd if=/percorso/per/fileubuntu.img of=/nome/chiavettausb bs=1M
{% endhighlight %}

una volta che il sistema ha finito di scrivere la iso sulla chiavetta, mac vi avvertirà che la chiavetta è stata scritta ma che non è leggibile da mac. Potrete dunque estrarla e utilizzarla per l’installazione del sistema.

## WINDOWS

Per windows le cose sono leggermente diverse. Dovrete scaricare uno dei tanti programmi di scrittura ISO. Io vi consiglio win32 disk imager. Scaricate il software da [qui](https://sourceforge.net/projects/win32diskimager/). Poi:

1 – Eseguite il programma

2 – Rinominate l’estensione della vostra iso da **.iso** a **.img** (esempio, ubuntu.iso diventa ubuntu.img).

3 – Selezionare il file img di ubuntu e la usb che si vuole utilizzare per l’installazione

4 – Cliccate su scrivi, attendete qualche minuto ed il gioco è fatto!
