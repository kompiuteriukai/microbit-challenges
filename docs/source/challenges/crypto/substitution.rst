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

Pakaitinis kodas yra apgaulingai paprastas. Pranešimai yra šifruojami naudojant iš anksto sukurtą raktą. Raktas sukuriamas kaitaliojant abėcėlę šitaip:

.. figure:: substitution.png

Tavo tikslas paversti „micro:bit“ į įrenginį galintį šifruoti pranešimus naudojant pakaitinį kodą. Pranešimą, kurį norime užšifruoti vadiname *paprastu tekstu*, o šifruotą pranešimą *šifruotu tekstu*. Programoje reikės saugoti abėcėlę su pakaitiniu kodu. Tam įgyvendinti gali naudoti „python“ *žodyną*. Pakaitinio kodo „python“ žodynas atrodo šitaip::

	cipher_key = { 'A':'V', 'B':'J', 'C':'Z', 'D':'B', 'E':'G', 'F':'N', 'G':'F', 'H':'E', 'I':'P', 'J':'L', 'K':'I','L':'T','M':'M','N':'X','O':'D','P':'W','Q':'K','R':'Q','S':'U','T':'C','U':'R','V':'Y','W':'A','X':'H','Y':'S','Z':'O'}

Anglų kalboje tai reiškia: simbolis 'A' turėtų būti pakeistas su simboliu 'V'; simbolis 'B' turėtų būti pakeistas su simboliu 'J' ir taip toliau. Gali atspausdinti žodyną naudojant ``print(cipher_key)``.

Išbandyk ir eksperimentuok naudodamas „REPL“. 

                                                                     
Paprasta užduotis
==================

Rink taškus už šiuos etapus: 

.. tabularcolumns:: |p{14cm}|R|

+---------------------------------------------------------+------------+
| **Užduotys** 		                                  | **Taškai** |
+=========================================================+============+
| Rodyti sveikinimo pranešimą.                            | 	 1     |
+---------------------------------------------------------+------------+
|                                                         |            |
| Sukurk žodyną su abėcėle ir atitinkamu šifruotu tekstu. |      2     |
| Atspausdink žodyną naudojant „REPL“. 			  |            |
| 			                                  |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Šioje savo programos versijoje turėtum saugoti 	  |      1     |
| pranešimą, kurį nori užšifruoti, eilutėje šitaip:	  |            |
| ``message = 'KEEP THIS A SECRET'``.                     |            |
|                                                         |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Dabar parodyk pranešimą po vieną raidę vienu metu	  |      1     |
| naudojantis ``for`` kilpa. Užuomena: tam, kad gauti kiek|            |
| vieną simbolį iš žinutės naudok 			  |            |
| ``for c in message:``. 				  |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Panaudok sukurtą žodyną kiek vieno simbolio pranešime   |     4      |
| vertimui į atitinkamą paprasto teksto simbolį.          |            |
| Užuomena: ``cipher_key['A']`` pateiks šifruotą simbolį  |            |
| atitinkantį raidę 'A' tavo žodyne.    	          |            |
| 				                          |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Atvaizduok šifruotą tekstą „micro:bit“ ir atspausdink   |      1     |
| šifruotą tekstą „REPL“ naudojant ``print()`` funkciją.  |            |
| 							  |            |
|                                                         |            |
+---------------------------------------------------------+------------+
