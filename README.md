# PID-Regler für Siemens SCL Tia-Portal

## Probleme:
Ich hatte immer viel mit Regeltechnik am Tia Portal zu tun und war einfach nie zufrieden mit den Siemens Bausteine. Ich brauche PI-Regler für Drucksteuerung und PID für Temperaturreglungen. Hier ein paar Punkte die mich störten:
- Unterschiedliche Bausteine unter verschidenen CPUs (z.B.: 300 zu 1200)
- Nicht simulierbar
- Nicht einsehbar und notfalls änderbar
- Viel zu kompliziert mit hoher Einarbeitung
- Keine Portierbarkeit nach Codesys
- Zu hohe Integration in TIA
- Viel basteln und testen bis endlich etwas funktionierte
- Zyklische OBs und Globale DB waren zwingend nötig 
- Viele tausens Seiten Handbücher

## Arbeit:
Nach längerem Suchen habe ich keine Alternative gefunden. Aber in OSCAT eine Inspiration, da es eigentlich ziemlich simpel ist, habe ich die Funktionen neu geschrieben. Jetzt habe ich alles schon länger im produktiven Einsatz und wollte mal schauen was Ihr dazu meint. 
Meine Intention war nicht jeden glücklich zu machen, sondern etwas zurück zugeben. Ich habe dank offener Libs (OSCAT) viel gelernt und es währe nicht richtig, wenn ich jetzt für immer auf meinen Sourcen sitzen bleibe. 

## Portierung:
Anmerkung zum Portieren auf Step-7, Codesys oder ähnlich:

    #VergangeneZeit := LREAL_TO_REAL(RUNTIME(#StaticZyklusZeit_Aux));
    
Diese Zeile liefert die Zeit zwischen zwei Aufrufe in Sekunden zurück. Die Auflösung ist bis zur Nanosekunde genau. Bei Step-7 würde ich die Zeit als Parameter übergeben, bei Codesys kann eventuell TIME_TCK verwendet werden. 
Bei verwendung mit Tia-Portal auf 300 Steuerung, einfach diese Zeile löschen:

    { S7_Optimized_Access := 'TRUE' }

Auf 300er kann eventuell mit "SFC64"(TIMETICK) gearbeitet werden. 

## Offene Arbeiten
- Anleitung schreiben
- Musterprojekte erstellen
- Alles auf Englisch umstellen
- Fehlerbeseitigung
- Portieren auf verschiedene Steuerungen

## License:
This project is released under the WTFPL LICENSE.
<a href="http://www.wtfpl.net/"><img src="http://www.wtfpl.net/wp-content/uploads/2012/12/wtfpl-badge-4.png"
       width="80" height="15" alt="WTFPL" /></a>
