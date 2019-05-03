***************************
„Caesar“ Šifras - II dalis
***************************

.. tabularcolumns:: |L|l|

+--------------------------------+----------------------+
| **Galimi taškai**		 | **Naudoja**	        |
+================================+======================+
| 10			 	 | LED ekraną           |
+--------------------------------+----------------------+
	
Aprašymas
===========

šis iššūkis yra apie pranešimų iššifravimą, kurie buvo užkoduoti naudojant „Caesar“ šifrą. Jeigu nebandei šifruoti pranešimų su „Caesar“ šifru, vertėtų tai pabandyti prieš tęsiant.

Naudojant „Caesar“ šifrą gali šifruoti ir iššifruoti visas pranešimo raides pastumiant abėcėlės raides tam tikrą kiekį kartų. Žemiau pateikta figūra parodo kaip šifruoti pranešimą perkėlus 3 raides:

.. figure:: shift.png

Tavo tikslas yra paversti „micro:bit“ į įrenginį, kuris galėtų **iššifruoti** pranešimus užkoduotus naudojant „Caesar“ šifrą. Visus užkoduotus pranešimus vadiname *šifruotu tekstu* ir iššifruotus pranešimus *atviru tekstu*.

Yra triukas, kurį gali naudoti norint iššifruoti ar pastumti žinutę. Triukas remiasi tuo, kad „micro:bit“ mato abėcėlės raides kaip specialiuosius skaičius žinomus kaip *„ascii“ vertės*. Gali išversti raidę į atitinkamą „ascii“ skaičių ir atvirkščiai naudojant „python“ funkcijas ``ord()`` ir ``chr()``.

Pavyzdys: Tarkime, turi šifruotą pranešimą, kuris buvo pastumtas per 4 vietas. Pabandyk naudoti šį kodą, kuris pavers kiek vieną simbolį į skaičių ir atims 4::

	ascii_char = ord(encrypted_char) - 4      	               

Anglų kalboje tai reiškia: išversti ``encrypted_char`` į „ascii“ skaičių naudojant ``ord()`` funkciją ir atimti 4, skaičius vietų per kiek nori pastumti.

Palukėk, yra dar vienas dalykas, kurį turi padaryti. Pažvelgus į paveiksliuką viršuje, pamatysi, kad turi grįšti atgal nuo A į Z. Norėdamas tai padaryti, turi pridėti 26 (raidžių skaičius abėcėlėje) jeigu peržengėme raidę 'A'::

        ascii_char = ord(plaintext_char) - 4                       
	if ascii_char > ord('Z') 
		ascii_char = ascii_char + 26
	encrypted_char = chr(ascii_char) 

Išbandyk ir eksperimentuok naudodamas „REPL“.

                                                                     
Paprastas iššūkis
=================
Rink taškus už šiuos etapus:

.. tabularcolumns:: |p{14cm}|R|

+---------------------------------------------------------+------------+
| **Užduotys** 		                                  | **Taškai** |
+=========================================================+============+
| Rodyti sveikinimo pranešimą.                            | 	 1     |
+---------------------------------------------------------+------------+
|                                                         |            |
| Tau nereikės kompiuterio šitam etapui!                  |      2     |
| Naudok šifravimo ratą (paprašyk mokytojo) užšifruoti    |            | 
| pranešimą, kuris sudarytas iš 10 raidžių.		  |            |
| **Svarbu:** prisiminti per kiek vietų buvo perkeltas    |            |
| pranešimas.                                             |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Savo programoje turėtum saugoti šifruotą pranešimą      |      1     |
| teksto eilutėje panašioje kaip ši:	 		  |            |
| ``encrypted_message = 'QKKV OZ G YKIXKZ'``.             |            |
|                                                         |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Dabar parodyk pranešimą po vieną raidę vienu metu	  |      1     |
| naudojantis ``for`` kilpa. Užuomena: tam, kad gauti kiek|            |
| vieną simbolį iš žinutės naudok 			  |            |
| ``for c in encrypted_message:``.                        |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Naudok ``ord()`` funkciją tam, kad išversti kiek vieną  |     1      |
| simbolį į „ascii“ skaičių ir atimk skaičių per kiek     |            |
| vietų šifruotas tekstas buvo pastumtas.                 |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Įsitikint, kad abėcėlė prasideda nuo pradžių.           |     1      |
| Užuomena: patikrink ar „ascii“ vertė yra mažiau	  |            |
| negu 'A'.                                               |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Naudok ``chr()`` tam, kad išversti kiekvieną „ascii“ 	  |      2     |
| numerį atgal į paprastą tekstą. Užuomena: nešifruok 	  |            |
| tarpų.		                  	          |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Atvaizduok paprastą tekstą „micro:bit“ ir atspausdink   |      1     |
| paprastą tekstą „REPL“ naudojant ``print()`` funkciją.  |            |
|                                                         |            |
+---------------------------------------------------------+------------+
