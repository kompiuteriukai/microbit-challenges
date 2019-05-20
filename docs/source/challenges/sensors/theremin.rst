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
Šiame projekte naudosi akcelerometrą tam, kad galėtum kontroliuoti tono dažnį. 

Tereminas yra keistas ir nuostabus elektroninis instrumentas kuriam nereikia jokio fizinio kontakto. Pasiklausyk programos apie juos: `<http://www.bbc.co.uk/programmes/b0076nqv>`_. Tereminas buvo išrastas 1920 metais Léon'o Theremin'o, ankstyvasis rusijos elektronikos inžinierius. Instrumentu grojama judinant rankas prie dviejų antenų - pirma valdo skleidžiamą garsą, o antra toną. Tiems, kurie domisi muzika verta žinoti, kad tereminas ikvėpė Robert'ą Moog'ą išrasti sintezatorių, taigi, nors pats instrumentas buvo mažai naudojamas, jis turėjo galingą efektą muzikos istorijoje.

.. figure::  leon_theremin.jpg

   Paveiksliukas: Leon Theremin, šaltinis: Wikipedia


Be to: apžvelkite sąrašus
----------------------------

Kaip dalį šios užduoties, turėsi rinkti ir saugoti kai kurias vertes iš akcelerometro sąraše ir apskaičiuoti vidurkį. Štai truputis informacijos kaip tai padaryti. Sąrašas yra duomenų struktūra, naudojama beveik visose programavimo kalbose. Mūsų atveju tai yra sunumeruota akcelerometro verčių kolekcija. Iš esmės tai yra dėžių rinkinys, į kurį mes galime įdėti vertes - kiekviena dėžė turi skaičių, pradedant nuo 0 ir einant aukštyn. Sakykime, kad mums reikia išlaikyti paskutines 30 akcelerometro reikšmių, tada mes sukuriame sąrašą ir pridėsime akcelerometro reikšmę kiekvieną kartą, kai einame aplink šią kilpą::
        
        while True:

            x_acceleration = accelerometer.get_x()

            # Add to the list of readings
            readings.append(x_acceleration)
        
            # If readings contains more than 30 values then pop the first value from the beginning
            if len(readings) > 30:
                readings.pop(0)
            sleep(1)

Kaip matai, jeigu rinkinys turi daugiau nei 30 įrašų, tai tiesiog ištrins pirmą įrašą, elementą numerį 0::

        readings.pop(0)

                                                                     
Paprasta užduotis
==================
Rink taškus už šiuos etapus: 

.. tabularcolumns:: |p{14cm}|R|

+---------------------------------------------------------+------------+
| **Užduotys** 		                                  | **Taškai** |
+=========================================================+============+
|                                                         |            |
| Naudok akcelerometro vertes x ašyje. Parašyk 	 	  | 	 1     |
| programos kodą, kuris atspausdintų akcelerometro vertes |            |
| x ašyje.		                                  |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Užrašyk ant popieriaus x ašies duomenis iš akcelerometro|      1     |
| kai pakreipi kompiuteriuką į kairę, kai pakreipi į      |            |
| dešinę ir kai laikomas tolygiai, veidu į viršų.         |            |
| Turi sužinoti minimalų ir maksimalų vertės diapozoną.   |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Sudėk 30 akcelerometro įrašų į sąrašą. Pažiūrėk į       |     2      |
| užrašus viršuje, ten pateikta informacija apie tai.     |            |
| Atspausdink sąrašą „REPL“.			          |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Dabar pabandyk sukurti garsą. Prijunk garsiakalbį prie  |      1     |
| „micro:bit“ naudojant krokodilinius segtukus. 	  |            |
| Įkelk muzikos biblioteką ``import music`` ir pagrok     |            |
| garsus naudojant ``music.pitch(frequency, time)``,      |            |
| kur dažnis yra tarp 50 ir 4000 Hz, o laikas pateikiamas |            |
| mili sekundėmis.		                          |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Turi išversti akcelerometro vertes į garso dažnį.       |      1     |
| Ar gali sugalvoti būdą kaip tai padaryti?		  |            |
| Eksperimentuok su programa, atspausdink vertes „REPL“.  |            |
|                                                         |            |
|                                                         |            |
+---------------------------------------------------------+------------+
|                                                         |            |
| Pagrok dažnį kuris atitinka akcelerometro vertę.	  |     1      |
|                                                         |            |
+---------------------------------------------------------+------------+
| Pamatysi, kad garsas kinta, nes akcelerometro vertės    |            |
| kinta labai greitai. Vienas iš būdų kaip tai išspręsti  |            |
| tai suskaičiuoti vertės vidurkį ir groti atitinkamą     |            |
| dažnį.						  |            |
|                                                         |     2      |
| Apskaičiuok akcelerometro vertės vidurkį ir jį	  |            |
| atspausdink. Užuomena: yra dvi „python“ funkcijos       |            | 
| galinčios padėti: ``sum(readings) / len(readings)``     |            | 
| ``sum`` sudeda visus sąrašo elementus, o ``len``        |	       | 
| grąžina sąrašo ilgį, kad turėtume visų akcelerometro    |            |
| rodmenų sumą, padalytą iš rodmenų skaičiaus.	 	  |            |
| 			                                  |            |  
+---------------------------------------------------------+------------+
