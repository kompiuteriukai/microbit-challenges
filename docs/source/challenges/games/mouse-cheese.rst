*******************
Kur yra sūris?
*******************

.. tabularcolumns:: |L|l|

+--------------------------------+----------------------------+
| **Galimi taškai**    		 | **Naudoja**       	      |
+================================+============================+
| 10                             | LED ekraną, akcelerometrą  |
+--------------------------------+----------------------------+

Aprašymas
===========

Šiame iššūkyje žaidėjas yra pelė ir pelė privalo suvalgyti sūri iki kol pasibaigia laikas. Žaidėjas gali judėti aplink palenkdamas „micro:bit“ į kairę arba dešinę, viršų arba apačią. Kai žaidėjas pagauna sūrį iškviesk funkciją: ``love.badaboom()`` ir pažiūrėk kas nutinka. Žaidėjas turi suvalgyti sūrį per tam tikrą laiko tarpą arba žaidimas pasibaigia.

Paprastas žaidimas
==================
Rink taškus už šiuos etapus:

.. tabularcolumns:: |p{14cm}|R|

+---------------------------------------------------------+------------+
| **Užduotys**                                            | **Taškai** |
+=========================================================+============+
| Rodyti sveikinimo pranešimą.                            |      1     |
+---------------------------------------------------------+------------+
| Sukurk žaidimo kilpą, kuri kartojasi kiek vieną sekundę.|      1     |
+---------------------------------------------------------+------------+
|                                                         |            |
| Sukurk žaidėjo tašką. Rodyk žaidėjo tašką kairėje       |      1     |
| viršutinėje ekrano pusėje. Užuomena: saugok žaidėjo     |            |
| poziciją sąraše ``player = [0,0]``.                     |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Pajudink žaidėjo tašką į dešinę jeigu „micro:bit“       |            |
| palenktas į dešinę ir kairę jeigu „micro:bit“ palenktas |      2     |
| į kairę. Užuomena: naudok reikšmes iš                   |            |  
| ``accelerometer.get_x()``                               |            |
| tam, kad nustatyti palenkimą.				  |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Pajudink žaidėjo tašką į viršų jeigu „micro:bit“ yra    |            |
| palenktas į viršų. Pajudink žemyn jeigu „micro:bit“     |      2     |
| palenktas žemyn. Užuomena: naudok                       |            |
| `accelerometer.get_y()`` tam, kad nustatyti palenkimą.  |            |
| 		                                          |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Sukurk sūrio tašką. Paskirk atsitiktinę vietą sūrio     |      1     |
| taškui. Užuomena: saugok sūrio poziciją sąraše          |            |
| ``cheese = [0,0]``.	                     |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Kai žaidėjas juda, patikrink ar žaidėjas yra toje       |      1     | 
| pačioje vietoje kaip ir sūris. Jeigu yra, vadinasi      |            |
| žaidėjas laimėjo. Iškviesk funkciją                     |            |
| ``love.badaboom()`` ir pažiūrėk kas nutiks.             |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Sukurk laikmatį, jeigu pelė nesuranda sūrio iki kol     |      1     |
| pasibaigia laikas, žaidimas pasibaigia. Užuomena:       |            |
| žaidimo pradžioje gauk žaidimo pradžios laiką naudojant |            |
| funkciją ``microbit.running_time()``.                   |            |
|                                                         |            |
+---------------------------------------------------------+------------+
	
	 
Papildomi taškai
================

.. tabularcolumns:: |p{14cm}|R|

+---------------------------------------------------------+------------+
| **Užduotys**                                            | **Taškai** |
+=========================================================+============+
|                                                         |            |
|                                                         |            |
| Pakartok žaidimą kai pelė pasiima sūrį. Sumažink laiko  |      1     |
| intervalą per kurį žaidėjas privalo surasti sūri.       |            |
|                                                         |            |
+---------------------------------------------------------+------------+

 
