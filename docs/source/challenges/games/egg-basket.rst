******************
Žaidimas "Sugauk kiaušinius"
******************

.. tabularcolumns:: |L|l|

+--------------------------------+----------------------+
| **Galimi taškai**		 | **Naudoja**	        |
+================================+======================+
| 10			 	 | LED ekraną, mygtukus |
+--------------------------------+----------------------+
	
Aprašymas
===========

Šiame iššūkyje sukursite žaidimą "Sugauk kiaušinius". Įsivaizduokite šokoladinius kiaušinius krentančius iš dangaus. Žaidėjas turi juos sugauti ir neleisti nukristi ant žemės. Žaidėjas gali judėti į kairę arba dešinę pusę naudojant "A" ir "B" mygtukus ant „micro:bit“. Jeigu kiaušinis nukrenta ant žemės žaidimas pasibaigia. 

Paprastas žaidimas
==================
Rinkite taškus už šiuos etapus: 

.. tabularcolumns:: |p{14cm}|R|

+---------------------------------------------------------+------------+
| **Užduotys**                                            | **Taškai** |
+=========================================================+============+
| Rodyti sveikinimo pranešimą.                            |      1     |
+---------------------------------------------------------+------------+
| Sukurkite žaidimo kilpą, kuri kartojasi kas sekundę.	  |      1     |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Sukurkite žaidėjo tašką stulpelyje 0, eilutė 3.         |      1     |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Pastumkite žaidėjo tašką į dešinę, jeigu yra paspaustas |            |
| mygtukas "B", ir kairę, jeigu paspaustas mygtukas "A".  |      1     |
| Užuomina: saugokite žaidėjo poziciją sąraše 	          |            |
| "player = [0,0]".	                		  |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Sukurkite krentančio kiaušinio tašką. Kiaušinis pradės  |      1     |
| kristi nuo ekrano viršaus po 1 pikselį kaskart          |            |
| pasikartojus žaidimo kilpai. Užuoina: saugok kiaušinio  |            |
| poziciją sąraše "egg = [0,0]".                  	  |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Sukurkite krentančio kiaušinio tašką atsitiktiniame     |      1     |
| stulpelyje ekrane. Užuomina: naudokite 	          |            |
| "random.randint(0,4)".                                  |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Kiekvieną kartą pasikartojus kilpai, patikrinkite ar    |      2     |
| žaidėjas susidūrė su kiaušiniu. Jeigu susidūrimas įvyko,|            |
| vadinasi žaidėjas sugavo kiaušinį ir žaidimas           |            |
| pasibaigia. Pasveikinkite žaidėją parodydami 		  |            |
| paveiksliuką arba pranešimą.                            |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Jeigu kiaušinis pasiekia ekrano apačią ir nesusiduria su|            |
| žaidėju, perkelkite kiaušinį į atsitiktinį stulpelį     |      1     |
| ekrano viršuje.					  |            |
|                                                         |            |
+---------------------------------------------------------+------------+
	
	 
Papildomi taškai
================

.. tabularcolumns:: |p{14cm}|R|

+---------------------------------------------------------+------------+
| **Užduotys**                                            | **Taškai** |
+=========================================================+============+
|                                                         |            |
| Leiskite žaidėjui gaudyti kiaušinius iki kol jis numeta |      1     |
| vieną. Žaidimui pasibaigus parodykite galutinį rezultatą|            |
|                                                         |            |
+---------------------------------------------------------+------------+

 
