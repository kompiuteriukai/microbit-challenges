***************************
„Caesar“ Šifras - I dalis
***************************

.. tabularcolumns:: |L|l|

+--------------------------------+----------------------+
| **Galimi taškai**		 | **Naudoja**	        |
+================================+======================+
| 10			 	 | LED ekraną, mygtukus |
+--------------------------------+----------------------+
	
Aprašymas
===========

Žmonės buvo suinteresuoti paslėpti žinutes jau nuo seno, kai tik išmoko komunikuoti užrašydami jas. Vienas lengviausių šifrų yra žinomas kaip „Caesar“ šifras, pavadintas Julijaus Cezario garbei ir buvo naudojamas Romos imperatoriaus komunikacijoms su kariais mūšyje. Naudojant „Caesar“ šifrą, šifruoji visas pranešimo raides pastumiant abėcėlės raides tam tikrą skaičių kartų. Žemiau esanti figūra parodo kaip šifruoti pranešimą perkeliant 3 raides:

.. figure:: shift.png

Tavo tikslas paversti „micro:bit“ į įrenginį galintį **šifruoti** pranešimus naudojant „Caesar“ šifrą. Galime naudoti pranešimą, kurį norime užkoduoti **paprastu tekstu** ir užkoduoti jį su *šifruotu tekstu*.

Yra triukas, kurį gali naudoti norint šifruoti ar pastumti žinutę. Triukas remiasi tuo, kad „micro:bit“ mato abėcėlės raides kaip skaičius. Gali išversti raidę į numerį ir atvirkščiai naudojant „python“ funkcijas ``ord()`` ir ``chr()``.

Tarkime, nori perkelti kiek vieną simbolį per 4 vietas. Pabandyk naudoti šį kodą, kuris pavers kiek vieną simbolį į skaičių ir pridės 4::

	ascii_char = ord(plaintext_char) + 4      	               

Anglų kalboje tai reiškia: išversti ``plaintext_char`` į skaičių naudojant ``ord()`` funkciją ir pridėti 4, skaičius vietų per kiek nori pastumti.

Palukėk, yra dar vienas dalykas, kurį turi padaryti. Pažvelgus į paveiksliuką viršuje, pamatysi, kad turi grįšti atgal nuo Z į A. Norėdamas tai padaryti, turi atimti 26 (raidžių skaičius abėcėlėje) jeigu peržengėme raidę 'Z'::

        ascii_char = ord(plaintext_char) + 4                       
	if ascii_char > ord('Z') 
		ascii_char = ascii_char - 26
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
| Turi sužinoti iš žaidėjo per kiek vietų pastumti        |      2     |
| pranešimą. Vienas iš būdų kaip tai padaryti, tai        |            |
| pastumti pranešimą tiek kartų kiek paspaustas mygtukas. |            |
| Įsiminti kiek kartų mygtukas ``A`` paspaustas.          |            |
| Žaidėjas gali paspausti mygtuką ``B`` norėdamas         |            |
| praneši, kad baigė.                                     |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Savo programoje turėtum saugoti pranešimą, kurį nori    |      1     |
| išversti į tekstinę eilutę šai taip:               	  |            |
| ``message = 'KEEP THIS A SECRET```.                     |            |
|                                                         |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Dabar parodyk pranešimą po vieną raidę vienu metu	  |      1     |
| naudojantis ``for`` kilpa. Užuomena: tam, kad gauti kiek|            |
| vieną simbolį iš žinutės naudok ``for c in message:``.  |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Naudok ``ord()`` funkciją tam, kad išversti kiek vieną  |     1      |
| simbolį į skaičių ir pridėk skaičių per kiek vietų      |            |
| norėtum jį pastumti.                                    |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Įsitikint, kad abėcėlė prasideda nuo pradžių.           |     1      |
| Užuomena: patikrink ar perkelta reikšmė yra didesnė     |            |
| negu numerinė ``Z`` reikšmė.                            |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
|                                                         |            |
| Naudok ``chr()`` tam, kad išversti kiekvieną numerį  	  |      2     |
| atgal į simbolį. Užuomena: nešifruok tarpų.		  |            |
| 				                          |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Atvaizduok šifruotą tekstą „micro:bit“ ir atspausdink   |      1     |
| šifruotą tekstą „REPL“ naudojant ``print()`` funkciją.  |            |
| 							  |            |
|                                                         |            |
+---------------------------------------------------------+------------+
