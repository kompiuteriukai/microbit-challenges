************
Kompasas
************
.. py:module:: microbit.compass

Magnetometras matuoja magnetinio lauko stiprumą kiekvienoje iš trijų ašių.
Jis gali būti naudojamas elektroninio kompaso sukūrimui arba magnetinių laukų
tyrinėjimui, kurie yra generuojami nuolatinio magneto arba elektros laidininku
tekančia srove.

.. image:: compass.jpg
   :scale: 80 %

Magnetinio lauko galios atvaizdavimas nėra lengvas. Magnetometro
tvarkyklė grąžina neapdorotas vertes. Kiekvienas magnetometras yra
skirtingas ir jį reikės kalibruoti, kad būtų atsižvelgta į neapdorotus
skaičius ir magnetinio lauko iškraipymus, kuriuos veikia kietieji ir
minkštieji geležies trikdžiai, kompensacijos.

Prieš pradedant ką nors daryti, reikia sukalibruoti savo „micro:bit“ kompiuteriuką,
tačiau atsiminkite:

.. warning::

    Kompaso kalibracija sustabdys jūsų programą iki kol šis veiksmas bus atliktas.
    Kalibracija vyksta žaidimo pavidalu, kuriuo reikia nupiešti apskritimą LED
    ekrane sukiojant savo įrenginį.


Paprastos Funkcijos
===================
Sąsaja su magnetometru atrodo labai panašiai kaip ir sąsaja su akselerometru, iškyrus tai, kad naudojame tik dvi ašis
x ir y krypčiai nustatyti. Prisiminkite, kad prieš pradedant naudoti kompasą, turėtumėte jį sukalibruoti. Kitu atveju rodmenys gali būti neteisingi::

    from microbit import *

    compass.calibrate()

    while True:
        x = compass.get_x() 
        y = compass.get_y() 
	print("x reading: ", x, ", y reading: ", y)
	sleep(500)

Ši dalis patikrina magnetinį lauką dviem matmenimis (kaip ir tikras kompasas) ir pateikia vertes, kas atrodo pakankamai paprasta. Pabandykite išsiaiškinti, kur šiame magnetometre yra ašis x. Norint sužinoti kryptį, reikia ją apskaičiuoti :math:`tan^{-1} (y/x)`, Phyton programavimo kalboje tai yra parašoma taip::

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

180/π yra todėl, kad grįžtamasis kampas yra pateikiamas radianais, o ne laipsniais. Laimei, „micro:bit“ turi funkciją kuri apskaičiuoja poziciją automatiškai::

   compass.heading()

Ši funkcija pateikia kompaso kryptį, kaip sveikąjį skaičių nuo 0 iki 360, ir kampą nurodo laipsniais pagal laikrodžio rodyklę (šiaurė yra 0). Tačiau prieš naudojant ``compass.heading`` funkciją privalote įrenginį sukalibruoti.

Projekto idėjos su kompasu
===================================
* Paverskite „micro:bit“ į kompasą, kuris uždegtų LED lemputę arčiausiai ten, kur yra šiaurė.
* Sukalibruokite savo magnetometrą. Išsiaiškintite, ar kalibracija išlieka panaši po tam tikro laiko, ir ar ji būna tokia pati patalpoje, lauke ar ten, kur yra daug metalo (pvz. lifte).
