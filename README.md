# Siemens SCL Tia Portal Tia-Portal Source Code wie in OSCAT <br/>

<b>Probleme:</b><br/>
Ich hatte immer viel mit Regeltechnik am Tia Portal zu tun und war einfach nie zufrieden mit den Siemens Bausteine. Ich brauche PI-Regler für Drucksteuerung und PID für Temperaturreglungen. Hier ein paar Punkte die mich störten:
- Unterschiedliche Bausteine unter verschidenen CPUs (z.B.: 300 zu 1200)
- Nicht simulierbar
- Nicht einsehbar und notfalls änderbar
- Viel zu kompliziert mit hoher einarbeitung
- Keine Portierbarkeit nach Codesys
- Zu hohe Integration in TIA
- Viel basteln und testen bis endlich etwas funktionierte
- Zyklische OBs und Globale DB waren zwingend nötig 
- Viele tausens Seiten Handbücher

<b>Arbeit:</b><br/>
Nach längerem Suchen habe ich keine Alternative gefunden. Aber in OSCAT eine Inspiration, da es eigentlich ziemlich simpel ist, habe ich die Funktionen neu geschrieben. Jetzt habe ich alles schon länger im produktiven Einsatz und wollte mal schauen was Ihr dazu meint. 
Meine Intention war nicht jeden glücklich zu machen, sondern etwas zurück zugeben. Ich habe dank offener Libs (OSCAT) viel gelernt und es währe nicht richtig, wenn ich jetzt für immer auf meinen Sourcen sitzen bleibe. 

<b>Portierung:</b><br/>
Anmerkung zum Portieren auf Step-7, Codesys oder änlich:
"#VergangeneZeit := LREAL_TO_REAL(RUNTIME(#StaticZyklusZeit_Aux));"
Diese Zeile liefert die Zeit zwischen zwei Aufrufe in Sekunden zurück. Die Auflösung ist bis zur Nanosekunde genau. Bei Step-7 würde ich die Zeit als Parameter übergeben, bei Codesys kann eventuel TIME_TCK verwendet werden. 
Bei verwendung mit Tia-Portal auf 300 Steuerung, einfach die Zeile "{ S7_Optimized_Access := 'TRUE' }" löschen.

<b>Offene Arbeiten:</b>
- Anleitung schreiben
- Musterprojekte erstellen
- Alles auf Englisch umstellen
- Fehlerbeseitigung
- Portieren auf verschiedene Steuerungen

<b>License:</b><br/>
This project is released under the WTFPL LICENSE.
<a href="http://www.wtfpl.net/"><img src="http://www.wtfpl.net/wp-content/uploads/2012/12/wtfpl-badge-4.png"
       width="80" height="15" alt="WTFPL" /></a>
