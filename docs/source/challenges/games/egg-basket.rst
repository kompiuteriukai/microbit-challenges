******************
Sugauk kiaušinius
******************

.. tabularcolumns:: |L|l|

+--------------------------------+----------------------+
| **Galimi taškai**		 | **Naudoja**	        |
+================================+======================+
| 10			 	 | LED ekraną, mygtukus |
+--------------------------------+----------------------+
	
Aprašymas
===========

Šiame iššūkyje patikrinsite žaidėjo gabumus sugauti kiaušinius į krepšelį. Įsivaizduok šokoladinius kiaušinius krentančius iš dangaus. Žaidėjas turi juos sugauti ir neleisti nukristi ant žemės. Žaidėjas gali judėti į kairę arba dešinę pusę naudojant ``A`` ir ``B`` mygtukus ant „micro:bit“. Jeigu kiaušinis nukrenta ant žemės žaidimas pasibaigia. 

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
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Sukurk žaidėjo tašką stulpelyje 0, eilutė 3.            |      1     |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Pastumk žaidėjo tašką į dešinę jeigu mytukas            |            |
| ``B`` yra paspaustas ir kairę jeigu paspaustas          |      1     |
| mygtukas ``A``. Užuomena: saugok žaidėjo poziciją       |            |
| sąraše ``player = [0,0]``.                 		  |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Sukurk kiaušinio tašką. Kiaušinis pradės kristi nuo     |      1     |
| ekrano viršaus po 1 pikselį kas kart pasikartojus       |            |
| žaidimo kilpai. Užuomena: saugok kiaušinio poziciją     |            |
| sąraše ``egg = [0,0]``.                                 |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Sukurk kiaušinio tašką atsitiktiniame stulpelyje        |      1     |
| ekrane. Užuomena: naudok ``random.randint(0,4)``.       |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Kiek vieną kartą pasikartojus kilpai, patikrink ar      |      2     |
| žaidėjas susidūrė su kiaušiniu. Jeigu susidūrimas įvyko |            |
| vadinasi žaidėjas sugavo kiaušinį ir žaidimas           |            |
| pasibaigia. Pasveikink žaidėją parodydamas paveiksliuką |            |
| arba pranešimą.                                         |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Jeigu kiaušinis pasiekia ekrano apačią ir nesusiduria su|            |
| žaidėju perkelk kiaušinį į atsitiktinį stulpelį ekrano  |            |
| viršuje.						  |      1     |
|                                                         |            |
+---------------------------------------------------------+------------+
	
	 
Papildomi taškai
================

.. tabularcolumns:: |p{14cm}|R|

+---------------------------------------------------------+------------+
| **Užduotys**                                            | **Taškai** |
+=========================================================+============+
|                                                         |            |
| Leisk žaidėjui gaudyti kiaušinius iki kol jis numeta    |      1     |
| vieną. Žaidimui pasibaigus parodyk galutinį rezultatą.  |            |
|                                                         |            |
+---------------------------------------------------------+------------+

 
