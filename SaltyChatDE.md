# SaltyChat

Falls Du das Problem hast, dass Du von SaltyChat nicht in den richtigen Raum des TeamSpeak-Servers verschoben wirst, nachdem Du dem Server beigetreten bist, wird häufig das Ändern des DNS-Servers empfohlen. Diese Lösung mag zwar funktionieren, sie ist aber für einige Personen ungeeignet. Und sie ist vor allem falsch, weil der Eingriff **viel zu weitgehend** ist.

Der korrekte Weg, um das Problem zu beheben, liegt darin, die Datei

``C:\Windows\System32\drivers\etc\hosts``

mit Administratorrechten zu öffnen, etwa mit dem Editor [Notepad++](https://notepad-plus-plus.org/downloads/).

Anschließend müssen folgende Zeilen eingefügt werden:

```
127.0.0.1   lh.saltmine.de
127.0.0.1   lh.v10.network
```

Die Datei sieht anschließend z. B. so aus:

![hosts](https://user-images.githubusercontent.com/40885610/141648324-871b0a01-b177-4667-8ef0-0018ef149294.png)

Wenn das erledigt wurde, muss der DNS-Cache geleert werden. Öffne die Eingabeaufforderung und gib hierzu folgenden Befehl ein:

`ipconfig /flushdns`
