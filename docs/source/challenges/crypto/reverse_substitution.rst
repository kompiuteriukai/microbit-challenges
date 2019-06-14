********************************
Pakaitinio kodo iššifravimas
********************************

.. tabularcolumns:: |L|l|

+--------------------------------+----------------------+
| **Galimi taškai**		 | **Naudoja**	        |
+================================+======================+
| 10			 	 | LED ekraną           |
+--------------------------------+----------------------+
	
Aprašymas
===========

Pakaitinis kodas yra apgaulingai paprastas. Pranešimai yra šifruojami naudojant iš anksto sukurtą raktą. Raktas sukuriamas kaitaliojant abėcėlę šitaip:

.. figure:: substitution.png

Jūsų tikslas paversti „micro:bit“ į įrenginį galintį iššifruoti pakaitinio kodo pranešimus. Pranešimą, kuris buvo užšifruotas vadiname *šifruotu tekstu*, o iššifruotą pranešimą - *paprastu tekstu*. Programoje reikės saugoti abėcėlę su pakaitiniu kodu. Tam įgyvendinti galite naudoti „python“ *žodyną*. Pakaitinio kodo „python“ žodynas atrodo šitaip::

        cipher_key = { 'A':'V', 'B':'J', 'C':'Z', 'D':'B', 'E':'G', 'F':'N', 'G':'F', 'H':'E', 'I':'P', 'J':'L', 'K':'I','L':'T','M':'M','N':'X','O':'D','P':'W','Q':'K','R':'Q','S':'U','T':'C','U':'R','V':'Y','W':'A','X':'H','Y':'S','Z':'O'}

Anglų kalboje tai reiškia: simbolis 'A' turėtų būti pakeistas su simboliu 'V'; simbolis 'B' turėtų būti pakeistas su simboliu 'J' ir taip toliau. Galite atspausdinti žodyną naudojant ``print(cipher_key)``.

Išbandykite ir eksperimentuokite naudodami „REPL“.
                                                                     
Paprasta užduotis
=================

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
| pranešimą, kurį noriite iššifruoti, eilutėje šitaip:	  |            |
| ``encrypted_message = 'IGGW PC V UGZQGC'``.             |            |
|                                                         |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Parodykite pranešimą po vieną raidę vienu metu	  |      1     |
| naudojantis ``for`` kilpa. Užuomina: tam, kad gautumėte |            |
| kiekvieną simbolį iš žinutės naudokite 		  |            |
| ``for c in encrypted_message:``.                        |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Panaudokite sukurtą žodyną kiekvieno simbolio           |     4      |
| vertimui į atitinkamą paprasto teksto simbolį.          |            |
| Užuomina: "for key, value in cipher_key.items():"       |            |
| keliaus per žodyną, raidė po raidės pateikiant "key"    |            |
| ir "value" poras. Taigi pirma grąžinta reikšmė bus      |            |
| "key" raidės "A" ir "value" raidės "V".                 |	       |
| Turėsite išieškoti visą žodyną kol rasite širuoto       |            |
| teksto reikšmės simbolį.				  |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Atvaizduokite iššifruotą tekstą „micro:bit“ ir          |      1     |
| atspausdinkite iššifruotą tekstą „REPL“ naudojant       |            |
| "print()" funkciją.	              			  |            |
|                                                         |            |
+---------------------------------------------------------+------------+
