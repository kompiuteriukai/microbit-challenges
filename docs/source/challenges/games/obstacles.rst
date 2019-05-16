*********
Kliūtys
*********

.. tabularcolumns:: |L|l|

+--------------------------------+----------------------+
| **Galimi taškai**		 | **Naudoja**	        |
+================================+======================+
| 10			 	 | LED ekraną, mygtukus |
+--------------------------------+----------------------+
	
Aprašymas
===========

Šiame iššūkyje žaidėjas važiuoja gatve arba lenktynių trasoje. Kelyje yra kliūtys ir žaidėjas turi jų išvengti naudodamas ``A`` ir ``B`` mygtukus. Jeigu žaidėjas atsitrenkia į kliūtį žaidimas pasibaigia.

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
| Sukurk žaidėjo tašką bet kuriame stulpelyje apatinėje   |            |
| eilutėje. Rodyk tašką maksimaliu ryškumu.               |            |
+---------------------------------------------------------+------------+
| Pastumk žaidėjo tašką vienu pikseliu aukštyn kas kart   |      1     |
| kilpai pasikartojus. Jeigu žaidėjo taškas eilutėje 0,   |            |
| perkelk žaidėjo tašką atgal į eilutę 4.                 |            |
| Užuomena: saugok žaidėjo poziciją sąraše:               |            |
| ``player = [0,0]``.                   		  |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Pastumk žaidėjo tašką į dešinę jeigu paspaustas mygtukas|     1      |
| ``B`` ir į kairę jeigu paspaustas ``A``.		  |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Sukurk kliūties tašką bet kuriame stulpelyje ekrano     |      2     |
| viršuje. Rodyk tašką minimaliu ryškumu.                 |            |
| Kliūties taškas turėtų pajudėti vienu pikseliu žemyn    |            |
| žaidimo kilpai pasikarotjus. Užuomena: saugok kliūties  |            |
| poziciją sąraše ``obstacle = [0,0]``.                   |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Padėk sukurtą kliūties tašką į atsitiktinį stuleplį.    |      1     |
| Užuomena: naudok ``random.randint(0,4)``.               |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Kas kart kilpai pasikartojus patikrink ar žaidėjas      |      2     |
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
| Pradžioje žaidimo duok žaidėjui 3 gyvybes. Atimk gyvybę |      1     |
| kiek vieną kartą įvykus susidūrimuis. Pabaik žaidimą    |            |
| kai žaidėjas nebeturi gyvybių.		          |            |
|                                                         |            |
+---------------------------------------------------------+------------+

 
