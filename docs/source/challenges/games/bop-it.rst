*********
„Bop-it“
*********

.. tabularcolumns:: |L|l|

+--------------------------------+----------------------+
| **Galimi taškai**		 | **Naudoja**	        |
+================================+======================+
| 10			 	 | LED ekraną, mygtukus |
+--------------------------------+----------------------+
	
Aprašymas
===========

Šiame iššūkyje sukursite reakcijos žaidimą panašų į „bop-it“. Pirmasis „bop-it“ žaidimas, pavaizduotas žemiau, buvo išleistas 1960-aisiais ir nuo to laiko buvo daug variantų, kurie išbando Jūsų reakciją su šviesa, garsu ir veiksmais.

.. figure:: bop_it.jpg
   :scale: 60 %

Originalus „bop-it“ dizainas, šaltinis: Wikipedia

Jūsų sukurtoje žaidimo versijoje, žaidėjas turės paspausti teisingą mygtuką ``A`` arba ``B`` per mažiau nei 1 sekundę. Jeigu žaidėjas paspaudžia neteisingą mygtuką, žaidimas pasibaigia. Jeigu paspaudžia teisingą mygtuką, gauna tašką ir gali žaisti toliau.

Paprastas žaidimas
==================
Rinkite taškus už šiuos etapus:

.. tabularcolumns:: |p{14cm}|R|

+---------------------------------------------------------+------------+
| **Užduotys** 		                                  | **Taškai** |
+=========================================================+============+
| Rodyti sveikinimo pranešimą.                            | 	 1     |
+---------------------------------------------------------+------------+
| Sukurkite žaidimo kilpą, kuri pasikartoja kas sekundę.  |      1     |
| Paprašykite žaidėjo paspausti mygtuką ``A`` arba	  |            |
| mygtuką ``B``. Užuomina: naudok ``random.randint(0,1)``.|            |
+---------------------------------------------------------+------------+
| Patikrinkite ar žaidėjas paspaudė teisingą mygtuką.     |      1     |
| Jeigu žaidėjas paspaudė teisingą mygtuką, parodykite    |            |
| atintinkamą paveiksliuką ar žinutę.                     |            |
+---------------------------------------------------------+------------+
| Jeigu žaidėjas paspaudė neteisingą mygtuką,             |      2     |
| pabaikite žaidimą.                             		  |            |
+---------------------------------------------------------+------------+
| Jeigu žaidėjas paspaudė teisingą mygtuką pridėkite 1    |      1     |
| tašką prie žaidėjo rezultato.                           |            |
+---------------------------------------------------------+------------+
| Žaidimo pabaigoje parodykite žaidėjo rezultatą. 	  |      1     |
+---------------------------------------------------------+------------+
	
	 
Papildomi taškai
================

.. tabularcolumns:: |p{14cm}|R|

+-----------------------------------------------------+------------+
| **Užduotys** 		                              | **Taškai** |
+=====================================================+============+
| Jeigu žaidėjui sekasi, sutrumpinkite laiko          |	    1	   |
| intervalą kitame žaidimo etape.                     |            |
+-----------------------------------------------------+------------+

 
