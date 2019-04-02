************
Kompasas
************
.. py:module:: microbit.compass

Magnetometras matuoja magnetinio lauko stiprumą kiekvienoje iš trijų ašių.
Jis gali būti naudojamas elektroninio kompaso sukūrimui arba magnetinių laukų
tyrinėjimui kurie yra generuojami nuolatinio magneto arba elektros laidininku
tekanti srovė.

.. image:: compass.jpg
   :scale: 80 %

Magnetinio lauko galios atvaizdavimas nėra lengvas. Magnetometro
tvarkyklė grąžina neapdorotas vertes. Kiek vienas magnetometras yra
skirtingas ir reikės jį kalibruoti, kad būtų atsižvelgta į neapdorotus
skaičius ir magnetinio lauko iškraipymus, kuriuos veikia kietieji ir
minkštieji geležies trikdžiai, kompensacijos.

Prieš pradedant ką nors daryti, reikia sukalibruoti savo „micro:bit“ kompiuteriuką,
bet atsimink:

.. warning::

    Kompaso kalibracija sustabdys tavo programą iki kol šis veiksmas bus atliktas.
    Kalibracija vyksta žaidimo pavidalu kuriuo reikia nupiešti apskritimą LED
    ekrane sukiojant savo įrenginį.


Paprastos Funkcijos
===================
Sąsaja su magnetometru atrodo labai panašiai kaip ir sąsaja su akselerometru, iškyrus tai, kad naudojame tik dvi ašis
x ir y krypčiai nustatyti. Prisimink, prieš pradedant naudoti kompasą turėtum jį sukalibruoti, kitu atvėju rodmenys gali būti neteisingi::

    from microbit import *

    compass.calibrate()

    while True:
        x = compass.get_x() 
        y = compass.get_y() 
	print("x reading: ", x, ", y reading: ", y)
	sleep(500)

Ši dalis patikrina magnetinį lauką diem matmenimis (lygtai taip pat kaip ir tikras kompasas) ir pateikia vertes, kas atrodo pakankamai paprasta. Pabandyk išsiaiškinti, kur šiame magnetometre yra ašis x. Norint sužinoti krypti reikia ją apskaičiuoti :math:`tan^{-1} (y/x)`, „python“ programavimo kalboje tai yra parašoma taip::

    import math
    from microbit import *

    compass.calibrate()

    while True:
        x = compass.get_x() 
        y = compass.get_y() 
    	angle = math.atan2(y,x) *180/math.pi
	print("x", x, " y", y)
	print("Direction: ", angle)
	sleep(500)

180/π yra todėl, kad grįžtamasis kampas yra radianais, o ne laipsniais. Lamei, „micro:bit“ turi funkciją kuri apskaičiuoja poziciją automatiškai::

   compass.heading()

Ši funkcija pateikia kompaso kryptį kaip sveikąjį skaičių nuo 0 iki 360, nurodant kampą laipsniais pagal laikrodžio rodyklę ir šiaurė yra 0. Bet prieš naudojant ``compass.heading`` funkciją privalai įrenginį sukalibruoti.

Projekto idėjos su kompasu
===================================
* Paversk „micro:bit“ į kompasą kuris uždegtų LED lemputę arčiausiai ten, kur yra šiaurė.
* Sukalibruok savo magnetometrą. Išsiaiškint ar kalibracija išlieka panaši po tam tikro laiko ir ar ji būna tokia pati patalpoje, lauke ar ten, kur yra daug metalo (pvz. lifte).
