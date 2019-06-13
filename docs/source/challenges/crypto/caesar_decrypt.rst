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

Šis iššūkis yra apie pranešimų, kurie buvo užkoduoti naudojant „Caesar“ šifrą, iššifravimą. Jeigu nebandėte šifruoti pranešimų su „Caesar“ šifru, vertėtų tai pabandyti prieš tęsiant šią pamoką.

Naudojant „Caesar“ šifrą galite šifruoti ir iššifruoti visas pranešimo raides pastumiant abėcėlės raides tam tikrą kiekį kartų. Žemiau pateikta figūra parodo kaip šifruoti pranešimą perkėlus 3 raides:

.. figure:: shift.png

Jūsų tikslas - paversti „micro:bit“ į įrenginį, kuris galėtų **iššifruoti** užkoduotus pranešimus naudojant „Caesar“ šifrą. Visus užkoduotus pranešimus vadiname *šifruotu tekstu* ir iššifruotus pranešimus *atviru tekstu*.

Yra triukas, kurį galite naudoti norint iššifruoti ar pastumti žinutę. Jis remiasi tuo, kad „micro:bit“ mato abėcėlės raides kaip specialiuosius skaičius žinomus kaip *„ascii“ vertės*. Galite išversti raidę į atitinkamą „ascii“ skaičių ir atvirkščiai, naudojant „python“ funkcijas ``ord()`` ir ``chr()``.

Pavyzdys: Tarkime, turite šifruotą pranešimą, kuris buvo pastumtas per 4 vietas. Pabandykite naudoti šį kodą, kuris pavers kiek vieną simbolį į skaičių ir atims 4:

	ascii_char = ord(encrypted_char) - 4      	               

Anglų kalboje tai reiškia: išversti ``encrypted_char`` į ASCII skaičių naudojant ``ord()`` funkciją ir atimti 4 (t. y. skaičius simbolių, kuriuos norime pastumti).

Yra dar vienas dalykas, kurį turite padaryti. Pažvelgus į paveiksliuką viršuje, pamatysite, kad turite grįšti atgal nuo A į Z. Norėdami tai padaryti, turi pridėti 26 (raidžių skaičius abėcėlėje) jeigu peržengėme raidę 'A'::

        ascii_char = ord(plaintext_char) - 4                       
	if ascii_char > ord('Z') 
		ascii_char = ascii_char + 26
	encrypted_char = chr(ascii_char) 

Išbandykite ir eksperimentuokite naudodamas „REPL“.

                                                                     
Paprastas iššūkis
=================
Rinkite taškus už šiuos etapus:

.. tabularcolumns:: |p{14cm}|R|

+---------------------------------------------------------+------------+
| **Užduotys** 		                                  | **Taškai** |
+=========================================================+============+
| Rodyti sveikinimo pranešimą.                            | 	 1     |
+---------------------------------------------------------+------------+
|                                                         |            |
| Jums nereikės kompiuterio šitam etapui!                 |      2     |
| Naudodami šifravimo ratą (paprašykite mokytojo)         |            |
| užšifruokite pranešimą, kuris sudarytas iš 10 raidžių.  |            |
| **Svarbu:** prisiminti per kiek vietų buvo perkeltas    |            |
| pranešimas.                                             |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Savo programoje turėtumėte saugoti šifruotą pranešimą   |      1     |
| teksto eilutėje panašioje į šią:	 		  |            |
| ``encrypted_message = 'QKKV OZ G YKIXKZ'``.             |            |
|                                                         |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Dabar parodykite pranešime po vieną raidę vienu metu	  |      1     |
| naudojantis"for" kilpa. Užuomina: tam, kad gautumėte    |            |
| kiekvieną simbolį iš žinutės naudokite                  |            |
| ``for c in encrypted_message:``.                        |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Naudokite "ord()" funkciją tam, kad išverstumėte        |     1      |
|kiekvieną simbolį į ASCII skaičių ir atimkite skaičių    |            |
|simbolių, kuriuos norite pastumti.                       |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Įsitikinkite, kad abėcėlė prasideda nuo pradžių.        |     1      |
| Užuomina: patikrinkite ar ASCII vertė yra mažesnė	  |            |
| nei 'A'.                                                |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Naudokite "chr()", kad išverstumėte kiekvieną ASCII 	  |      2     |
| numerį atgal į paprastą tekstą. Užuomina:               |            |
|nešifruokite tarpų.		                  	  |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Pavaizduokite paprastą tekstą „micro:bit“ ir            |            |
|atspausdinkite jį „REPL“ naudojant ``print()`` funkciją. |            |            
|                                                         |            |
+---------------------------------------------------------+------------+
