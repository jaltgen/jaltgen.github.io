---
  title: Broadcast Safe Colors Ebook
  author: Jannik Altgen
  date: 02. October 2018
---



Workflow Basics
BROADCAST SAFE COLORS
1. DEFINITIONEN
A. Farbr�ume
i. Sind Definitionsr�ume, welche die Definition und Adressierung spezifischer Farben innerhalb eines fixen Systems erm�glichen.
ii. RGB, YUV, CMYK oder HSL, Pantone, CIE LAB, CIE XYZ sind Farbmodelle, welche die mathematische Repr�sentation von Farbr�umen definieren. Folgend wird nur RGB und YUV betrachtet.
iii. RGB: Farbr�ume wie sRGB, Rec.709, AdobeRGB oder DCI-P3 werden h�ufig in den drei Komponenten Farben Rot, Gr�n und Blau angegeben. Auf einer 8bit Skala von 0-255 k�nnen R, G und B jeweils Werte von 0-255 annehmen.
iv. YUV: Farben werden �ber eine Luminanz-Komponente (Y) sowie zwei Farbdifferenzkomponenten (U,V) dargestellt. U entspricht der +/- Gr�n Achse und V der +/- Rot Achse. Doppeldeutigkeit des Begriffs YUV: technisch beschreibt YUV einen analogen Farbraum, der Begriff wird aber heute synonym f�r den digitalen Y?CbCr Farbraum verwendet. Analog zu YUV enspricht Cb = U sowie Cr = V. Bei einer 8bit Skala von 0-255 kann Y? Werte von 16-235 annehmen, sowie Cb und Cr 16-240.

B. Skalen
i. In 8bit je Kanal gibt es Werte von 0-255 (0 = Schwarz, 255 = Wei�)
ii. In 10bit je Kanal 0-1023 (0 = Schwarz, 1023 = Wei�)
iii. IRE (Institute of Radio Engineers): eine 0-100 Prozent Skala mit Bezug zur Legal Range
iv. mV (Milli-Volt): analoges Ma� der Signalamplitude, welches den digitalen Werten entspricht, 0-700mV +/- Toleranzen (s. Limits / Standards)

2. FULL RANGE UND LEGAL RANGE (VIDEO RANGE)
A. Aus dem analogen Signalumfang wurden fr�her bestimmte Bereiche f�r Steuerinformationen (Sync, Teletext, etc.) ben�tigt. In diese Signalbereiche darf auch heute digital keine Bildinformation gespeichert werden, da die TV-Sendetechnik diese Standards beibehalten hat, um r�ckw�rtskompatibel zu bleiben. Daraus ergibt sich ein Bereich im digitalen Signal, der f�r TV-Ausstrahlung nicht �ber- oder unterschritten werden darf, dieser hei�t ?Legal Range? oder ?Video Range?. Trotzdem kann dieser Bereich f�r z.B. Farbkorrektur genutzt werden (gr��eres Farbspektrum). Wenn der Full Range f�r Bildinformationen genutzt wird, muss der gesamte Full-Range Bereich in den Legal Bereich gestaucht werden. Sonst werden diese Bildinformationen in der Sendekette abgeschnitten, und es entstehen Bildfehler (verf�lschte Farben, Gamut Abweichungen, Banding etc.). Zum Beispiel: digitale Tools in RGB k�nnen Chromakan�le bis 131 IRE unterst�tzen, dort k�nnen folglich Chrominanz-�berschreitungen entstehen, die f�r die Ausstrahlung wieder in den Legal Range gestaucht werden m�ssen.
B. 8bit Legal Range: 16-235 f�r die Luma-Komponente (Y?) und 16-240 f�r die CbCr-Komponenten.
C. 10bit Legal Range:  Luma: 64-940, CbCr 64-960.
D. IRE-Skala: bezieht sich nur auf den Legal Bereich.
E. mV: 0mV entspricht O IRE bzw. dem Legal Range Schwarzwert, 700mV entspricht 100 IRE bzw. dem Legal Range Wei�wert. Der Farbdifferenzkanal Cb darf von 350 bis 0mV reichen (Waveform invertiert / Phaseninversion der Farbdifferenzkan�le). Cr und Pr reichen von 350mV bis 700mV
Skala
Luma (Y?)
Chroma (Cb, Cr)
8bit
16-235
16-240
10bit
64-940
64-960
IRE
0-100
0-102
mV
0-700
0-702


3. QC FAILS DURCH UMRECHNUNGSFEHLER (RGB ZU YUV)
Grafiken mit starken Farben (besonders gelb und dunkle blau- und rott�ne) sind anf�llig f�r Chrominanz�berschreitungen.
Umrechnungen von sRGB (in diesem Format wird alles inhouse gebaut) in Y?CbCr (Sendeformat der Sendeanstalten) f�hrt zu Umrechnungsfehlern und dadurch zu zu hohen Gamut-Werten. Dies liegt an den unterschiedlichen ?Legal Limits? f�r RGB und Y?CbCr: ein ?Wei�? in RGB (255,255,255) wird zwar korrekt in Y?CbCr (255,0,0) konvertiert, 255 ist f�r Y? aber �ber dem Limit von 235 + Toleranz.
Beispiel ?Luma �berschreitung?: RGB (62, 255 ,8) f�hrt zur Y?CbCr (245, 0, 0), welches eine �berschreitung des Limits von 235 + 3% = 241 entspr�che.
Beispiel ?Chroma �berschreitung?: RGB (255, 114, 255) f�hrt zu Y?CbCr (235, 245, 245), welches eine �berschreitung des Chroma Limits (235 + 2,3% = 240) in beiden Kan�len entspricht.
Typische Fehlerquellen:
A. Importiert man eine 10-bit Full Range Y?CbCr -Datei, interpretiert Premiere diese als Legal-Range und bl�st diese dann in die Full-Range-Skala auf.
4. IM- UND EXPORT AUS VERSCHIEDENEN PROGRAMMEN
A. DaVinci Resolve
DaVinci zeigt Waveforms auf 10-bit-Skala an, von 0-1023. Exportiert man aus DaVinci heraus, hat man die M�glichkeit, Full Range oder Legal Range (genannt Video Range) zu exportieren. Bei Full Range werden die Daten 1:1 in den Export geschrieben. Bei Video Range werden die Tonwerte komprimiert und zwischen 64-940 ?gepresst?. Das hat zur Folge, dass Video Range Exporte soweit bekannt immer Broadcast Safe sind.

Premiere :
B. Premiere Pro CC 2018
Importiert man eine 10-bit Full Range Y?CbCr -Datei, interpretiert Premiere diese als Legal-Range und bl�st diese dann in die Full-Range-Skala auf.

ProRes 4444 arbeitet mit sRGB
ProRes 422HQ arbeitet mit Y?CbCr

i. Full Range Daten

ii. Legal / Video Range
1. In 8bit gilt Luma als Legal zwischen 16-235, Chroma 16-240
2. In 10bit gilt Luma als Legal von 64-940, Chroma 64-960
3. Die Bereiche �ber und unter der Legal Range beinhalten Super-Wei� bzw. Sub-Schwarz (bei Kamerafootage z.B. f�r Headroom genutzt)



C. EBU R.103
i. Toleranzen der Legal Range im Rec.709 (int. HDTV Standard)
1. Die European Broadcasting Union erlaubt Abweichungen von der o.g. Legal Range im Luma (Y?) Kanal um +3/-1% (von 64 bis 940 / 0 bis 700 mV Legal Range)
a. Beispielrechnung 10-bit: (940-64) x 1,03 + 64 = 966 im Wei� und ca. 55,24 im Schwarz
b. Beispielrechnung 8-bit: (235-16) x 1,03+ 16 = 241,57 im Wei� und ca. 13,81 im Schwarz
c. Beispielrechnung mV: 700mV x 1,03 = 721mV im Wei� bzw. 0-((700/100) x 1) = -7mV im Schwarz
2. Die EBU erlaubt Abweichungen von der o.g. Legal Range im Chroma Kanal um +2,3/-1% (von 64 bis 940 / 0 bis 700 mV) Legal Range)
a. Beispielrechnung 10-bit: (940-64) x 1,023 + 64 = 960 im Wei� und ca. 55,24 im Schwarz
b. Beispielrechnung 8-bit: (235-16) x 1,023 +16 = 240 im Wei�
c. Beispielrechnung mV: 700mV x 1,023 = 721mV im Wei� bzw. 0-((700/100) x 1) = -7mV im Schwarz


Luma
Chroma
Bittiefe
Toleranz -
Toleranz +
Toleranz -
Toleranz +
%
-1
+3
-1
+2,3
8bit
13,81
241,57
13,81
240
10bit
55,24
966
55,24
960
IRE
-1
103
-1
102,3
mV
-7
721
-7
716

d. Titel-Wei� sollte 93% IRE / 235 RGB nicht �berschreiten (TODO: bei Adobe vermutlich alles safe, aber RES / AVID?)
e. Schwarze Balken sollten 6% IRE / 16 RGB nicht unterschreiten.

4
