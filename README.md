# IPS-PS4
Mit diesem Modul ist es möglich, ein PS4-System über IP-Symcon zu steuern.
Das Modul befindet sich noch in einer Beta Phase.


## Funktionen 
* Wecken der PS4 aus dem Ruhemodus
* PS4 in den Ruhemodus versetzen
* PS4 Spiele / Apps starten
 

## Installation
Dieses Modul besteht aus zwei Modueln (PS4 und PS4 Dummy).
Die eigentlichen Funktionen sind in dem PS4 Modul vorhanden.
Das PS4-Dummy Modul wird benötigt, um die Playstation mit IP-Symcon zu verknüpfen.

### Einrichtung in IP-Symcon
Einbinden des Git Repository in IP-Symcon wie gewohnt vornehmen, dazu folgende URL verwenden:
https://github.com/Schnittcher/IPS-PS4.git

### Einrichtung der Instanzen

#### PS4-Dummy
Der PS4-Dummy wird unter Splitter Instanzen angelegt.
Beim Anlegen des PS4-Dummy Moduls wird gleichzeitig ein Multicast Socket mit angelegt.
Dort sind folgende Einstellungen zu tätigen:


Feld | Inhalt
------------ | -------------
Sende-Host | 239.255.255.250
Sende-Port | 987
Empf.-Host | Alle
Empf.-Port | 987
Multicast | 239.255.255.250

Alle 3 Haken setzen (Aktiviere Broadcast, Aktiviere Reuse Address und Aktiviere Loopback)

#### PS4
Die PS4 Instanz wird im Objektbaum erzeugt.

Feld | Erklärung
------------ | -------------
IP-Adresse der PS4 | Hier die IP-Adresse der PS4 eintragen
User-Credentials | Hier die User-Credentials der PS4 eintragen - siehe Registrierung von IPS an der PS4
Gameliste | Hier können die Spiele / Apps eingetragen werden, welche über IPS gestartet werden sollen


Innerhalb der Testumgebung wird die PS4, registriert, weiteres ist hier zu finden: Registrierung von IPS an der PS4
 
### Registrierung von IPS an der PS4
Es wird die App PS4 Second Screen auf einem Smartphone oder Tavlet benötigt.
Diese App auf dem Gerät öffnen und nach neuen Geräten im Netzwerk suchen.
Nun sollte eine PS4 mit dem Namen IP-Symcon gefunden (das ist das PS4-Dummy Modul) werden.
Diesen Eintrag auswählen und die App wird versuchen sich mit IP-Symcon zu verbinden.
Unterhalb der PS4-Dummy Instanz gibt es eine Variable **Credentials**.
Diese sollte nun eine längere Zeichenfolge enthalten, diese Zeichenfolge kopieren und im Konfigurationsformular des PS4 Moduls unter User-Credentials eintragen.
  
Um die Registrierung der PS4 abzuschließen, muss auf dem PS4 System unter Einstellungen -> Einstellungen der Verbindung über die mobile App ->
Gerät hinzufügen, das IP-Symcon Modul autorisiert werden, es wird dort ein 8 stelliger Pincode angezeigt.
Diesen Pincode nun in dem Konfigurationsformular der PS4 Instanz in dem Feld Pincode eingeben und den Button Register anklicken.

Nun sollte die PS4 mit IP-Symcon verknüpft sein.