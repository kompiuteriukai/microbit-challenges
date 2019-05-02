**************
Morzės abėcėlė
**************

.. tabularcolumns:: |L|l|

+--------------------------------+------------------------+
| **Galimi taškai**		 | **Naudoja**	          |
+================================+========================+
| 10			 	 | LED ekraną, garsekalbį |
+--------------------------------+------------------------+
	
Aprašymas
===========

Morzės abėcėlę 1836m. sukūrė grupė žmonių įskaitant amerikiečių menininką Samuel F. B. Morse. Naudojant Morzės abėcėlę, pranešimai pateikiami kaip elektrinių impulsų serija, kuri gali keliauti per laidus į elektromagneto sistemą gavėjo pusėje. Simboliai naudojami kiek vienai raidei yra pateikti žemiau.

.. figure:: morse.png
   :scale: 60 %

Šaltinis: raspberrypi.org

Žinoma, nesi apribotas tik elektriniais impulsais, gali perduoti Morzės abėcėlės pranešimą naudojant šviesą ar garsą. Morzės abėcėlės pranešimas perduodamas elektros laidais yra žinomas kaip telegramas, pranešimas išverčiamas į Morzės abėcėlę operatoriaus ir siunčiamas su tefegrafo raktu, panašiu kaip šiame paveiksliuke.

.. figure:: J38TelegraphKey.jpg 
   :scale: 60 %

Telegrafo raktas, šaltinis:  „Wikipedia“ 

Pranešimą gavėjo pusėje operatorius išverčia į normalų tekstą.

Tavo tikslas paversti „micro:bit“ į įrenginį, kuris gali šifruoti pranešimus naudojant Morzės abėcėlę. Konvertuojamą pranešimą vadinsime *paprastu tekstu*. Programoje reikės saugoti abėcėlę kartu su Morzės abėcėle. Tam padaryti gali naudoti „python“ *žodyną*. Žemiau pateikiama dalis žodyno Morzės abėcėlei::

    morse_code = { 'A':'.-', 'B':'-...', 'C':'---.', 'D':'-..', 'E':'.', 'F':'..-.', 'G':'..-.', 'H':'--.', ...  }

Anglų kalboje tai reiškia: simbolis 'A' turėtų būti pakeistas eilute '.-'; simbolis 'B' turėtų būti pakeistas eilute '-...' ir taip toliau. Gali atspausdinti žodyną naudojant::

    print(morse_code)

Išbandyk ir eksperimentuok naudodamas „REPL“.

                                                                     
Paprasta užduotis
=================
Rink taškus už šiuos etapus:

.. tabularcolumns:: |p{14cm}|R|

+---------------------------------------------------------+------------+
| **Užduotys** 		                                  | **Taškai** |
+=========================================================+============+
| Rodyti sveikinimo pranešimą.                            | 	 1     |
+---------------------------------------------------------+------------+
|                                                         |            |
| Sukurk žodyną, sudarytą iš abėcėlės raidžių atitinkamai |      2     |
| sutanpančiu su Morzės abėcėle. Atspausdink žodyną       |            |
| naudodamas „REPL“.                                      |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Šioje savo programos versijoje turėtum saugoti   	  |      1     |
| pranešimą, kurį nori šifruoti šitaip: 	   	  |            |
| ``message = 'KEEP THIS A SECRET'``.                     |            |
|                                                         |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Dabar parodyk pranešimą po vieną raidę vienu metu	  |      1     |
| naudojantis ``for`` kilpa. Užuomena: tam, kad gauti kiek|            |
| vieną simbolį iš žinutės naudok ``for c in message:``.  |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Panaudok sukurtą žodyną kiek vieno simbolio išvertimui  |     3      |
| pranešime į atitinkamą šifruotą simbolį.     	          |            |
| Užuomena: ``morse_code['A']`` pateiks Morzės abėcėlės   |            |
| simbolį atitinkantį raidei 'A' tavo žodyne.	  	  |            |
| 			               	   	          |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Atvaizduok Morzės abėcėlę „micro:bit“ ir atspausdink    |      1     |
| šifruotą tekstą „REPL“ naudojant ``print()`` funkciją.  |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Prijunk garsiakalbį prie „micro:bit“ ir paleisk seriją  |            |
| garsų reprezentuojančių pranešimą.       		  |     1      |
|                                                         |            |
|                                                         |            |
+---------------------------------------------------------+------------+
