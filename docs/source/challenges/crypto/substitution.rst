*******************
Pakaitinis šifras
*******************

.. tabularcolumns:: |L|l|

+--------------------------------+----------------------+
| **Galimi taškai**	         | **Naudoja**	        |
+================================+======================+
| 10			 	 | LED ekraną           |
+--------------------------------+----------------------+
	
Aprašymas
===========

Pakaitinis kodas yra apgaulingai paprastas. Pranešimai yra šifruojami naudojant iš anksto sukurtą raktą. Raktas sukuriamas kaitaliojant abėcėlę:

.. figure:: substitution.png

Jūsų tikslas paversti „micro:bit“ į įrenginį galintį šifruoti pranešimus naudojant pakaitinį kodą. Pranešimą, kurį norime užšifruoti vadiname *paprastu tekstu*, o šifruotą pranešimą - *šifruotu tekstu*. Programoje reikės saugoti abėcėlę su pakaitiniu kodu. Tam įgyvendinti gali naudoti Python *žodyną*. Pakaitinio kodo Phyton žodynas atrodo šitaip::

	cipher_key = { 'A':'V', 'B':'J', 'C':'Z', 'D':'B', 'E':'G', 'F':'N', 'G':'F', 'H':'E', 'I':'P', 'J':'L', 'K':'I','L':'T','M':'M','N':'X','O':'D','P':'W','Q':'K','R':'Q','S':'U','T':'C','U':'R','V':'Y','W':'A','X':'H','Y':'S','Z':'O'}

Anglų kalboje tai reiškia: simbolis 'A' turėtų būti pakeistas su simboliu 'V'; simbolis 'B' turėtų būti pakeistas su simboliu 'J' ir taip toliau. Galite atspausdinti žodyną naudojant ``print(cipher_key)``.

Išbandykite ir eksperimentuokite naudodamiesi „REPL“. 

                                                                     
Paprasta užduotis
==================

Rinkite taškus už šiuos etapus: 

.. tabularcolumns:: |p{14cm}|R|

+---------------------------------------------------------+------------+
| **Užduotys** 		                                  | **Taškai** |
+=========================================================+============+
| Rodyti sveikinimo pranešimą.                            | 	 1     |
+---------------------------------------------------------+------------+
|                                                         |            |
| Sukurkite žodyną su abėcėle ir atitinkamu šifruotu      |      2     |
| tekstu. Atspausdinkite žodyną naudojant „REPL“. 	  |            |
| 			                                  |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Šioje savo programos versijoje turėtumėte saugoti 	  |      1     |
| pranešimą, kurį norite užšifruoti, eilutėje šitaip:	  |            |
| ``message = 'KEEP THIS A SECRET'``.                     |            |
|                                                         |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Parodykite pranešimą po vieną raidę vienu metu	  |      1     |
| naudojantis ``for`` kilpa. Užuomina: tam, kad gauti     |            |
| kiekvieną simbolį iš žinutės naudok 			  |            |
| "for c in message:". 					  |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Panaudokite sukurtą žodyną kiekvieno simbolio           |     4      |
| vertimui į atitinkamą paprasto teksto simbolį.          |            |
| Užuomina: ``cipher_key['A']`` pateiks šifruotą simbolį  |            |
| atitinkantį raidę 'A' Jūsų žodyne.    	          |            |
| 				                          |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Atvaizduokite šifruotą tekstą „micro:bit“ ir jį         |      1     |
| atspausdinkite „REPL“ naudojant ``print()`` funkciją.   |            |
| 							  |            |
|                                                         |            |
+---------------------------------------------------------+------------+
