*******************
Žaidimas "Kur yra sūris?"
*******************

.. tabularcolumns:: |L|l|

+--------------------------------+----------------------------+
| **Galimi taškai**    		 | **Naudoja**       	      |
+================================+============================+
| 10                             | LED ekraną, akcelerometrą  |
+--------------------------------+----------------------------+

Aprašymas
===========

Šiame iššūkyje žaidėjas yra pelė ir pelė privalo suvalgyti sūrį per duotą laiko tarpą. Žaidėjas gali judėti aplink palenkdamas „micro:bit“ į kairę arba dešinę, viršų arba apačią. Kai žaidėjas pagauna sūrį, iškvieskite funkciją: ``love.badaboom()`` ir pažiūrėkite kas nutinka. Pėlė turi suvalgyti sūrį per tam tikrą laiko tarpą arba žaidimas pasibaigia.

Paprastas žaidimas
==================
Rinkite taškus už šiuos etapus:

.. tabularcolumns:: |p{14cm}|R|

+---------------------------------------------------------+------------+
| **Užduotys**                                            | **Taškai** |
+=========================================================+============+
| Rodyti sveikinimo pranešimą.                            |      1     |
+---------------------------------------------------------+------------+
| Sukurkite žaidimo kilpą, kuri pasikartoja kas sekundę.  |      1     |
+---------------------------------------------------------+------------+
|                                                         |            |
| Sukurkite žaidėjo tašką. Rodykite žaidėjo tašką         |      1     |
| kairėje viršutinėje ekrano pusėje. Užuomina: saugokite  |            |
| žaidėjo poziciją sąraše ``player = [0,0]``.             |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Pajudinkite žaidėjo tašką į dešinę, jeigu „micro:bit“   |            |
| palenktas į dešinę, ir kairę, jeigu „micro:bit“ 	  |      2     |
| palenktas į kairę. Užuomina: naudokite reikšmes iš      |            |  
| ``accelerometer.get_x()`` tam, kad nustatytumėte        |            |
| palenkimą.						  |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Pajudinkite žaidėjo tašką į viršų, jeigu „micro:bit“ yra|            |
| palenktas į viršų. Pajudink žemyn, jeigu „micro:bit“    |      2     |
| palenktas žemyn. Užuomina: naudokite                    |            |
| ``accelerometer.get_y()`` tam, kad nustatytumėte 	  |            |
| palenkimą.		                                  |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Sukurkite "sūrio" tašką. Paskirkite atsitiktinę vietą   |      1     |
| sūrio taškui. Užuomina: saugok sūrio poziciją sąraše    |            |
| ``cheese = [0,0]``.	                     		  |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Kai žaidėjas juda, patikrinkite ar žaidėjas yra toje    |      1     | 
| pačioje vietoje kaip ir sūris. Jeigu yra, vadinasi      |            |
| žaidėjas laimėjo. Iškvieskite funkciją                  |            |
| ``love.badaboom()`` ir pažiūrėkite kas nutiks.          |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Sukurk laikmatį. Jeigu pelė nesuranda sūrio per duotą   |      1     |
| laiko tarpą, žaidimas pasibaigia. Užuomina: žaidimo     |            |
| pradžioje gaukite žaidimo pradžios laiką naudojant 	  |            |
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
| Pakartokite žaidimą kai pelė pasiima sūrį. Sumažinkite  |      1     |
| laiko intervalą per kurį žaidėjas privalo surasti sūrį. |            |
|                                                         |            |
+---------------------------------------------------------+------------+

 
