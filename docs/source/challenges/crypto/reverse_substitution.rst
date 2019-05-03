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

Tavo tikslas paversti „micro:bit“ į įrenginį galintį iššifruoti pakaitinio kodo pranešimus. Pranešimą, kuris buvo užšifruotas vadiname *šifruotu tekstu*, o iššifruotą pranešimą *paprastu tekstu*. Programoje reikės saugoti abėcėlę su pakaitiniu kodu. Tam įgyvendinti gali naudoti „python“ *žodyną*. Pakaitinio kodo „python“ žodynas atrodo šitaip::

        cipher_key = { 'A':'V', 'B':'J', 'C':'Z', 'D':'B', 'E':'G', 'F':'N', 'G':'F', 'H':'E', 'I':'P', 'J':'L', 'K':'I','L':'T','M':'M','N':'X','O':'D','P':'W','Q':'K','R':'Q','S':'U','T':'C','U':'R','V':'Y','W':'A','X':'H','Y':'S','Z':'O'}

Anglų kalboje tai reiškia: simbolis 'A' turėtų būti pakeistas su simboliu 'V'; simbolis 'B' turėtų būti pakeistas su simboliu 'J' ir taip toliau. Gali atspausdinti žodyną naudojant ``print(cipher_key)``.

Išbandyk ir eksperimentuok naudodamas „REPL“.
                                                                     
Paprasta užduotis
=================

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
| pranešimą, kurį nori iššifruoti, eilutėje šitaip:	  |            |
| ``encrypted_message = 'IGGW PC V UGZQGC'``.             |            |
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
| Panaudok sukurtą žodyną kiek vieno simbolio pranešime   |     4      |
| vertimui į atitinkamą paprasto teksto simbolį.          |            |
| Užuomena: ``for key, value in cipher_key.items():``     |            |
| keliaus per žodyną, raidė po raidės pateikiant ``key``  |            |
| ir ``value`` poras. Taigi pirma grąžinta reikšmė bus    |            |
| ``key`` raidės ``A`` ir ``value`` raidės ``V``. Turėsi  |	       |
| išieškoti visą žodyną iki kol rasi širuoto teskto       |            |
| reikšmės simbolį.					  |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Atvaizduok iššifruotą tekstą „micro:bit“ ir atspausdink |      1     |
| iššifruotą tekstą „REPL“ naudojant ``print()`` funkciją.|            |
| 							  |            |
|                                                         |            |
+---------------------------------------------------------+------------+
