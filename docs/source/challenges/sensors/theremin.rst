**********
Tereminas
**********

.. tabularcolumns:: |L|l|

+--------------------------------+----------------------------+
| **Galimi taškai**		 | **Naudoja**	              |
+================================+============================+
| 10			 	 | Akcelerometrą, garsiakalbį |
+--------------------------------+----------------------------+
	
Aprašymas
===========
Šiame projekte naudosite akcelerometrą tam, kad galėtumėte kontroliuoti tono dažnį. 

Tereminas yra keistas ir nuostabus elektroninis instrumentas, kuriam nereikia jokio fizinio kontakto. Pasiklausykite šio instrumento istorijos: `<http://www.bbc.co.uk/programmes/b0076nqv>`_. Tereminas buvo išrastas 1920 metais Rusijos elektronikos inžinierius Léon'o Theremin'o. Instrumentu grojama judinant rankas prie dviejų antenų - pirma valdo skleidžiamą garsą, o antra toną. Tiems, kurie domisi muzika, verta žinoti, kad tereminas ikvėpė Robert'ą Moog'ą išrasti sintezatorių. Taigi, nors pats instrumentas buvo mažai naudojamas, jis turėjo galingą efektą muzikos istorijoje.

.. figure::  leon_theremin.jpg

   Paveiksliukas: Leon Theremin, šaltinis: Wikipedia


Apžvelkite sąrašus
----------------------------

Kaip dalį šios užduoties, turėsite rinkti ir saugoti kai kurias akcelometro vertes iš sąrašo ir apskaičiuoti jų vidurkį. Sąrašas yra duomenų struktūra, naudojama beveik visose programavimo kalbose. Šiuo atveju tai yra sunumeruota akcelerometro verčių kolekcija. Tai yra tarsi dėžių rinkinys, į kurį mes galime įdėti vertes - kiekviena dėžė turi skaičių, pradedant nuo 0 ir einant aukštyn. Tarkim, kad mums reikia išlaikyti paskutines 30 akcelerometro reikšmių, tada mes sukuriame sąrašą ir pridėsime akcelerometro reikšmę kiekvieną kartą, kai šis ciklas pasikartos::
        
        while True:

            x_acceleration = accelerometer.get_x()

            # Add to the list of readings
            readings.append(x_acceleration)
        
            # If readings contains more than 30 values then pop the first value from the beginning
            if len(readings) > 30:
                readings.pop(0)
            sleep(1)

Kaip matote, jeigu sąrašas turės daugiau nei 30 įrašų, šis kodas tiesiog ištrins pirmąjį įrašą::

        readings.pop(0)

                                                                     
Paprasta užduotis
==================
Rinkite taškus už šiuos etapus: 

.. tabularcolumns:: |p{14cm}|R|

+---------------------------------------------------------+------------+
| **Užduotys** 		                                  | **Taškai** |
+=========================================================+============+
|                                                         |            |
| Naudokite akcelerometro vertes x ašyje. Parašykite 	  | 	 1     |
| programos kodą, kuris atspausdintų akcelerometro vertes |            |
| x ašyje.		                                  |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Užrašykite ant popieriaus x ašies duomenis iš 	  |      1     |
| akcelerometro kai pakreipiate kompiuteriuką į kairę, į  |            |
| dešinę ir kai jis laikomas tolygiai, veidu į viršų.     |            |
| Turi sužinoti minimalų ir maksimalų vertės diapozoną.   |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Sudėkite 30 akcelerometro įrašų į sąrašą. Pažiūrėkite į |     2      |
| užrašus viršuje, ten rasite daugiau informacijos. 	  |            |
| Atspausdink sąrašą „REPL“.			          |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Pabandykite sukurti garsą. Prijunkite garsiakalbį prie  |      1     |
| „micro:bit“ naudojant krokodilinius segtukus. 	  |            |
| Įkelkite muzikos biblioteką ``import music`` ir 	  |            |
| pagrokite garsus naudojant 			          |            |
| ``music.pitch(frequency, time)``, kur dažnis yra tarp 50|            |
| ir 4000 Hz, o laikas pateikiamas milisekundėmis.	  |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Išverskite akcelerometro vertes į garso dažnį.          |      1     |
| Ar galite sugalvoti būdą kaip tai padaryti?		  |            |
| Eksperimentuokite su programa, atspausdinkite vertes 	  |            |
| „REPL“.                                                 |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Pagrokite dažnį, kuris atitinka akcelerometro vertę.	  |     1      |
|                                                         |            |
+---------------------------------------------------------+------------+
| Pamatysite, kad garsas kinta, nes akcelerometro vertės  |            |
| kinta labai greitai. Vienas iš būdų kaip tai išspręsti, |            |
| tai suskaičiuoti vertės vidurkį ir groti atitinkamą     |            |
| dažnį.						  |            |
|                                                         |     2      |
| Apskaičiuokite akcelerometro vertės vidurkį ir jį	  |            |
| atspausdinkite. Užuomina: yra dvi „python“ funkcijos    |            | 
| galinčios padėti: ``sum(readings) / len(readings)``.    |            | 
| ``sum`` sudeda visus sąrašo elementus, o ``len``        |	       | 
| grąžina sąrašo ilgį, kad turėtume visų akcelerometro    |            |
| rodmenų sumą, padalytą iš rodmenų skaičiaus.	 	  |            |
| 			                                  |            |  
+---------------------------------------------------------+------------+
