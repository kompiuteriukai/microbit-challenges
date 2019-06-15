*********
Žaidimas "Kliūtys"
*********

.. tabularcolumns:: |L|l|

+--------------------------------+----------------------+
| **Galimi taškai**		 | **Naudoja**	        |
+================================+======================+
| 10			 	 | LED ekraną, mygtukus |
+--------------------------------+----------------------+
	
Aprašymas
===========

Šiame iššūkyje žaidėjas važiuoja gatve arba lenktynių trasoje. Kelyje yra kliūtys ir žaidėjas turi jų išvengti naudodamas``A`` ir ``B`` mygtukus. Jeigu žaidėjas atsitrenkia į kliūtį, žaidimas pasibaigia.

Paprastas žaidimas
==================
Rinkite taškus už šiuos etapus:  

.. tabularcolumns:: |p{14cm}|R|

+---------------------------------------------------------+------------+
| **Užduotys**                                            | **Taškai** |
+=========================================================+============+
| Rodyti sveikinimo pranešimą.                            |      1     |
+---------------------------------------------------------+------------+
| Sukurkite žaidimo kilpą, kuris pasikartotų kas sekundę. |      1     |
+---------------------------------------------------------+------------+
| Sukurkite žaidėjo tašką bet kuriame stulpelyje apatinėje|            |
| eilutėje. Rodykite tašką maksimaliu ryškumu.            |            |
+---------------------------------------------------------+------------+
| Pastumkite žaidėjo tašką vienu pikseliu aukštyn kaskart |      1     |
| pasikartojus kilapi. Jeigu žaidėjo taškas eilutėje 0,   |            |
| perkelkite žaidėjo tašką atgal į eilutę 4.              |            |
| Užuomina: saugokite žaidėjo poziciją sąraše:            |            |
| ``player = [0,0]``.                   		  |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Pastumkite žaidėjo tašką į dešinę, jeigu paspaustas 	  |     1      |
| mygtukas ``B``, ir į kairę, jeigu paspaustas ``A``.	  |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Sukurkite kliūties tašką bet kuriame stulpelyje ekrano  |      2     |
| viršuje. Rodykite tašką minimaliu ryškumu.              |            |
| Kliūties taškas turėtų pajudėti vienu pikseliu žemyn    |            |
| žaidimo kilpai pasikartojus. Užuomina: saugokite 	  |            |
| kliūties poziciją sąraše ``obstacle = [0,0]``.          |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Padėkite sukurtą kliūties tašką į atsitiktinį stulpelį. |      1     |
| Užuomina: naudokite ``random.randint(0,4)``.            |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Kaskart pasikartojus kilpai, patikrinkite ar žaidėjas   |      2     |
| atsitrenkė į kliūtį. Jeigu susidūrimas įvyko, žaidimas  |            |
| baigiasi.	                                          |            |
|                                                         |            |
+---------------------------------------------------------+------------+
	
	 
Papildomi taškai
================

.. tabularcolumns:: |p{14cm}|R|

+---------------------------------------------------------+------------+
| **Užduotys**                                            | **Taškai** |
+=========================================================+============+
|                                                         |            |
| Žaidimo pradžioje duokite žaidėjui 3 gyvybes. Atimkite  |      1     |
| gyvybę kiekvieną kartą įvykus susidūrimui. Pabaikite    |            |
| žaidimą kai žaidėjas nebeturi gyvybių.		  |            |
|                                                         |            |
+---------------------------------------------------------+------------+

 
