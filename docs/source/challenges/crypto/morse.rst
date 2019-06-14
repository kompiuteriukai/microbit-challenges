**************
Morzės abėcėlė
**************

.. tabularcolumns:: |L|l|

+--------------------------------+------------------------+
| **Galimi taškai**		 | **Naudoja**	          |
+================================+========================+
| 10			 	 | LED ekraną, garsiakalbį|
+--------------------------------+------------------------+
	
Aprašymas
===========

Morzės abėcėlę 1836m. sukūrė grupė žmonių įskaitant amerikiečių menininką Samuel F. B. Morse. Naudojant Morzės abėcėlę pranešimai pateikiami kaip elektrinių impulsų serija, kuri gali keliauti per laidus į elektromagneto sistemą gavėjo pusėje. Simboliai naudojami kiekvienai raidei yra pateikti žemiau.

.. figure:: morse.png
   :scale: 60 %

Šaltinis: raspberrypi.org

Žinoma, nesate apribotas tik elektriniais impulsais, galite perduoti Morzės abėcėlės pranešimą naudojant šviesą ar garsą. Morzės abėcėlės pranešimas perduodamas elektros laidais yra vadinamas telegrama. Operatorius išverčia pranešimą į Morzės abėcėlę ir siunčiamas su telegrafo raktu, panašiu į pavaizduotą šiame paveiksliuke.

.. figure:: J38TelegraphKey.jpg 
   :scale: 60 %

Telegrafo raktas, šaltinis:  „Wikipedia“ 

Pranešimą gavėjo pusėje operatorius išverčia į įprastą tekstą.

Jūsų tikslas paversti „micro:bit“ į įrenginį, kuris gali šifruoti pranešimus naudojant Morzės abėcėlę. Konvertuojamą pranešimą vadinsime *paprastu tekstu*. Programoje reikės saugoti abėcėlę kartu su Morzės abėcėle. Tam padaryti gali naudoti „python“ *žodyną*. Žemiau pateikiama dalis žodyno Morzės abėcėlei::

    morse_code = { 'A':'.-', 'B':'-...', 'C':'---.', 'D':'-..', 'E':'.', 'F':'..-.', 'G':'..-.', 'H':'--.', ...  }

Anglų kalboje tai reiškia: simbolis 'A' turėtų būti pakeistas eilute '.-'; simbolis 'B' turėtų būti pakeistas eilute '-...' ir taip toliau. Galite atspausdinti žodyną naudojant::

    print(morse_code)

Išbandykite ir eksperimentuokite naudodami „REPL“.

                                                                     
Paprasta užduotis
=================
Rinkite taškus už šiuos etapus:

.. tabularcolumns:: |p{14cm}|R|

+---------------------------------------------------------+------------+
| **Užduotys** 		                                  | **Taškai** |
+=========================================================+============+
| Rodyti sveikinimo pranešimą.                            | 	 1     |
+---------------------------------------------------------+------------+
|                                                         |            |
| Sukurkite žodyną, sudarytą iš abėcėlės raidžių, kuris   |     2      |
| atitiktų Morzės abėcėlę. Atspausdinkite žodyną          |            |
| naudodami „REPL“.                                       |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Šioje savo programos versijoje turėtumėte saugoti   	  |      1     |
| pranešimą, kurį nori šifruoti šitaip: 	   	  |            |
| ``message = 'KEEP THIS A SECRET'``.                     |            |
|                                                         |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Dabar parodykite pranešimą po vieną raidę vienu metu	  |      1     |
| naudojantis ``for`` kilpa. Užuomina: tam, kad gautumėte |            |
| kiekvieną simbolį iš žinutės naudokite                  |            |
| "for c in message:".                                    |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Panaudokite sukurtą žodyną kiekvieno simbolio           |     3      |
| išvertimui pranešime į atitinkamą šifruotą simbolį.     |            |
| Užuomina: ``morse_code['A']`` pateiks Morzės abėcėlės   |            |
| simbolį atitinkantį raidei 'A' jūsų žodyne.	  	  |            |
| 			               	   	          |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Atvaizduokite Morzės abėcėlę „micro:bit“ ir             |      1     |
| atspausdinkite šifruotą tekstą „REPL“ naudojant         |            |
| "print()" funkciją.                                     |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Prijunkite garsiakalbį prie „micro:bit“ ir paleiskite   |            |
| seriją garsų reprezentuojančių pranešimą.     	  |     1      |
|                                                         |            |
|                                                         |            |
+---------------------------------------------------------+------------+
