# Siemens-SCL
Siemens SCL Tia Portal Tia-Portal Source Code wie in OSCAT 

Ich hatte immer viel mit Regeltechnik am Tia Portal zu tun und war einfach nie zufrieden mit den Siemens Bausteine. Ich brauche PI-Regler für Drucksteuerung und PID für Temperaturreglungen. Hier ein paar Punkte die mich störten:

    Unterschiedliche Bausteine unter verschidenen CPUs (z.B.: 300 zu 1200)
    Nicht simulierbar
    Nicht einsehbar und notfalls änderbar
    Viel zu kompliziert mit hoher einarbeitung
    Keine Portierbarkeit nach Codesys
    Zu hohe Integration in TIA
    Viel basteln und testen bis endlich etwas funktionierte
    Zyklische OBs und Globale DB waren zwingend nötig 
    Viele tausens Seiten Handbücher

Nach längerem Suchen habe ich keine Alternative gefunden. Aber in OSCAT eine Inspiration, da es eigentlich ziemlich simpel ist, habe ich die Funktionen neu geschrieben. Jetzt habe ich alles schon länger im produktiven Einsatz und wollte mal schauen was Ihr dazu meint. 
Meine Intention war nicht jeden glücklich zu machen, sondern etwas zurück zugeben. Ich habe dank offener Libs (OSCAT) viel gelernt und es währe nicht richtig, wenn ich jetzt für immer auf meinen Sourcen sitzen bleibe. Jeder darf mit meinem Regler machen was er will, oder auch nicht. Fall jemand Fehler findet oder es irgend wie noch besser hin bekommt, nur zu. 

