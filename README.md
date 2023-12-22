# Umbau vom IKEA Uppatvind auf USB-C

Der neue und kleine Luftfilter von IKEA für 35€ mit 95m³/h CADR. 

Günstig und funktional, aber leider mit einem Netzteil für 230V. Kann aber für ~ 10 € auf USB-C umgerüstet und somit per Powerbank genutzt werden.

Wenn du ein Lötkolben so halten kannst, dass es nicht nach Hähnchen riecht und ein Multimeter benutzen kannst, solltest du den Umbau auch bewerkstelligen können.

Umbau und Betrieb auf eigene Gefahr. Nach dem Umbau ist zwar alles Kleinspannung aber USB-C PD Netzteile können doch erhebliche Leistungen abgeben, sodass man bei Fehlern auch Magic Smoke, Schmoren oder Brand erzeugen kann.

# Anleitung

## Materialien 

* DC-BoostUp-Converter von 5V auf 24V mit min. 2A (besser 3A, lieber etwas überdimensionieren) Ausgangsstrom
* USB-C PD Trigger-Board (für z.B. 9V, ggf. optional, siehe unten zu weiteren Überlegungen zur Spannung)
* ein bisschen Kabel für zwischen Trigger-Board und BoostUp-Converter
* doppelseitiges Klebeband
* Heißkleber

Verwendeter BoostUp-Converter (no affiliate or something like that and there are better shops than Amazon): https://www.amazon.de/LAOMAO-Converter-Einstellbare-Ausgangsspannung-Netzteiladapter/dp/B0C2H6PFVH

## Werkzeug

* Schraubendreher
* Multimeter
* Seitenschneider (und ggf. Abisolierzange)
* Heißklebepistole

## Schritte

### Aufschrauben

Aus der Steckdose ziehen ;)

Vorfilter und Filter herausnehmen.

Mit einem passenden Schraubendreher die dreieckigen Schrauben herausschrauben.
Ein Schlitz-Schraubendreher mit ~ 4 mm Breite funktioniert auch, T8 könnte auch funktionieren.

Dann kann man den inneren Teil herausheben.
Hierbei vorsichtig mit dem Kabel zum Motor sein.
Das ist auf der Platine oben unter dem Knopf mit einem arretiertem Stecker befestigt.
Den abziehen, um entspannt arbeiten zu können.

### Originales Kabel entfernen

Die Zugentlastung unten vom originalen Kabel abschrauben. 

Das schwarz-weiße Kabel nah an der Außenisolierung durchschneiden und auf der Seite Richtung Platine abisolieren.

Den äußeren Teil vom Kabel herausziehen und weglegen.
Das ist genauso wie das Netzteil nun übrig.

### USB-C Trigger-Board und BoostUp einstellen

Bei einigen USB-C PD Trigger-Boards kann man die Ausgangsspannung einstellen, z.B. über Lötpäds.
Diese auf 9V Ausgangsspannung einstellen, siehe weiter unten für Überlegungen zur Spannung.

USB-C PD Netzteil anschließen, nachmessen, ob 9V herauskommen, Netzteil wieder herausziehen.

USB-C Trigger-Board mit dem Eingang vom BoostUp-Converter verbinden, so mit 5-10 cm Kabel. Polarität beachten.

USB-C Netzteil wieder rein, mit Multimeter den Ausgang vom Bootstyp-Konverter messen und mit dem Poti auf 24V Ausgangsspannung einstellen. Netzteil wieder herausziehen.

### Verkabeln

Das Kabel von der Platine an den BoostUp-Converter Ausgang anschließen. Die weiße Ader ist Plus und Schwarz ist Minus.

### Testlauf

Motorkabel wieder einschließen und alles so hinlegen, dass der Motor frei drehen kann. Dann Netzteil einstecken, anschalten und ausprobieren.

### Befestigen

Die USB-C Trigger-Boards passen meist unten in das Loch, wo vorher das Kabel rauskam. 

Mit einem doppelseitiges Klebeband, Sperrholz, doppelseitiges Klebeband Sandwich kann man das Trigger-Board da ganz gut befestigen und dann noch mit genug Heißkleber fixieren.

Den BoostUp-Converter auf diesen Buckel überm Loch mit doppelseitigem Klebeband kleben. Dabei beachten, dass der nicht über den Buckel nach Vorne überstehen darf, da dort das zweite Gehäuseteil aufliegt. 

Kabel gut verstauen.

### Zusammenbau

Wieder das Gehäuseteil mit dem Motor einsetzen. 

Dabei können sich die Kabel irgendwo dazwischen verfangen. Also gut schauen, dass alles am richtigen Platz sitzt und die Gehäuseteile plan und schlüssig ineinander liegen. 

Schrauben wieder reinschrauben, Filter wieder einsetzen und fertig :)

## Überlegungen zur Spannung

Der verwendete BoostUp-Converter hält die 24V Ausgangsspannung stabil bei Eingangsspannungen zwischen 5V und 20V.

Der Uppatvind zieht laut Anleitung maximal 19 Watt Leistung (24V, 0.8A). 

Leitungsabnahmen bei 5V Eingangsspannung am BoostUp-Converter Eingang gemessen:

* Einschalten von 0 auf Stufe 1, Spitze: 1A, 5W
* Stufe 1: 0.45A, 2.25W
* Stufe 2: 0.8A, 4W
* 2 auf 3 Spitze: 1.65A, 8.25W
* Stufe 3: 1.45A, 7.25W
* Einschalten von 0 direkt auf Stufe 3
    * Bei 5V kurzzeitig eindeutig mehr als 2A, da hat das Labornetzteil abgeregelt, die Spannung ist zusammengebrochen und Uppatvind hat das Einschalten abgebrochen.
    * Bei 9V waren es so 1A laut analoger Anzeige, also wahrscheinlich so 10 Watt oder so.

Die Spitzenströme sind von einer analogen Anzeige eines Labornetzteils abgelesen, ggf. werden kurzzeitig (kürzer als 1 sec) noch höhere Leistungen benötigt.

Man kann den Luftfilter also auch an einem leistungsfähigen 5V Netzteil/Powerbank (min. 2A) betreiben, man muss aber die Stufen nacheinander einschalten.
Somit kann auf das Trigger-Board ggf. auch verzichtet werden.
Das verwendete Trigger-Board gibt jedoch auch fröhlich 5V aus, wenn es die eingestellte Spannung aushandeln kann, stört somit auch nicht.

Als Kompromiss scheint 9V als Ausgangsspannung vom USB-C PD Trigger-Board geeignet.
Die Spannung ist ausreichend hoch, sodass die Ströme nicht zu groß werden.
Außerdem wird von vielen (Handy-)Netzteilen 9V PD unterstützt.
15V oder 20V werden meist nur von Laptop USB-C Netzteilen unterstützt. 

Außerdem kann das verwendete Trigger-Board auch Qualcomm Quick Charge triggern und auch über diese Netzteile 9V beziehen.

Andere Spannungen könnten jedoch auch eine gute Wahl darstellen.
