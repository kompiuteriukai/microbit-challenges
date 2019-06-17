Duomenų tipai
=============

„Micro:bit” programose naudositee įvairių tipų vertes, pavyzdžiui: galitee gauti pagreičio reikšmes iš akselerometro. Kita vertus, galbūt norite suskaičiuoti kiek mygtukų paspaudžia vartotojas arba parodyti vartotojui pranešimą, nurodantį kambario temperatūrą. Norėdami visą tai padaryti, turite sugebėti apibūdinti visus duomenis, kurios norite naudoti. Python ir dauguma kitų programavimo kalbų atpažįsta kelis duomenų tipus, įskaitant:

* Sveikuosius skaičius - tai yra sveikieji skaičiai.
* Realiuosius skaičius - tai yra skaičiai su kableliu ir liekana po kablelio.
* Eilutes - juose gali būti simbolių, kurios norime traktuoti kaip tekstą, pavyzdžiui: raidžių, skaičių ir simbolių derinys.  
* Loginius kintamuosius bool - tai yra loginės sistemos dalis, kuri turi dvi reikšmes, teigiamą ir neigiamą.

Paprastoje programoje galėtumete juos visus panaudoti. Čia pateikiami duomenų tipai, kuriuos galėtumėte naudoti programoje, kurioje saugoma informacija apie mėgstamus „micro:bit” žaidimus:

.. figure:: dataTypes.png

   Paveiksliukas iš: <http://www.bbc.co.uk/education/guides/zwmbgk7/revision/3>

Kintamieji
----------

Galite įsivaizduoti kintamajį kaip dėžutę, kurioje kompiuteris gali laikyti reikšmę. Reikšmė toje dėžutėje gali kisti. Visi kintamieji yra sudaryti iš trijų dalių: pavadinimo, tipo ir reikšmės. Žemiau pavaizduoti trijų tipų kintamieji::

.. figure:: variable.jpg
   :scale: 60 %

   Paveiksliukas iš: <https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/Variables>

Kintamasis ``name`` turi eilutę ``Bob``, kintamasis ``winner`` turi eilutę ``True`` ir kintamasis ``score`` turi eilutę ``35``.

Python programavimo kalboje mes privalome duoti pavadinimus kintamiesiems. Kai tai padarome, galime pradėti juos naudoti, paskirti ir manipuliuoti jų reikšmėmis::

	from microbit import *

	myCount = 0

	while True:
    	   if button_a.was_pressed(): 
		myCount = myCount + 1
	   sleep(2000)
	   print("Number of presses: " + str(count))

Čia panaudojome kintamąjį ``myCount`` tam, kad suskaičiuotume kiek kartų buvo paspaustas mygtukas ``A``. Ar galite pasakyti ką dar šis programos fragmentas daro?

Operacijos
----------

Skaičiai
^^^^^^^^
Skaitmenines reikšmes galite naudoti su pagrindiniais aritmetiniais operatoriais: `` +, -, *, / `` tokiu pat būdu, kaip ir su skaičiuokle.
Pažvelkite į aritmetinių operatorių pavyzdį. Įsivaizduokite, kad norite konvertuoti temperatūrą, kurią „micro:bit” pateikia Celsijaus formatu, į Farenheitą. Galite naudoti tokį kodą::

	celsiusTemp = temperature()
	fahrenheitTemp = celsiusTemp * 9 / 5 + 32  

Likusiam skaičiui apskaičiuoti naudojamas specialus operatorius „%”, vadinamas „mod”. Pavyzdžiui: norite sužinoti, ar numeris yra lyginis, ar nelyginis. Galite pabandyti jį padalinti iš 2, jei jis yra lyginis, tada nebus jokio likučio::

	theNumber = 3
	if theNumber % 2 == 1:
	   print("The number is odd")
	else:
	   print("The number is even")

Jei likutis lygus 1, ši programa išspausdins pranešimą „The number is odd“, kitu atveju programa spausdins pranešimą „The number is even“. Galite parašyti šią programą ir kitu būdu. Tai rodo, kad žmonės galvoja apie problemas skirtingais būdais, o dvi programos nėra tokios pačios. 

Eilutės
^^^^^^^
Svarbiausias dalykas apie eilutes, į kurį reikia atreikti dėmesį, yra tai, kad galite jas sujungti arba susieti naudojantis simboliu „+”. Kodas::

	name = "Hayley"

	message = "Well done " + name + ". You are a winner!"

Sujungs elementus dešinėje pusėje `` = `` ir įterps rezultatą į kintamąjį, vadinamą ``message``.

Negalite sujungti skaičių su eilutėmis; norint tai padaryti, pirmiausia turite konvertuoti skaičių į eilutę pasinaudojant funkcija ``str()``::

	x = temperature
	if temperature < 6:
	   display.scroll("Cold" + str(temperature))


Palyginimai
-----------

.. figure:: booleanLogic.jpg 
   :scale: 60 %

   Paveiksliukas iš: <http://www.bbc.co.uk/education/guides/zy9thyc/revision>

Dažnai programuojant mes norime palyginti vieną vertę su kita, patestuoti. Šiuos testus arba palyginimus naudojame atrankoje arba cikluose. Štai keletas anglų kalba parašytų palyginimų pavyzdžių::

	score is greater than 100
	name equals "Harry"
 	x acceleration is not equal to 0

Python programavimo kalba turi palyginimo operatorių rinkinį, kuris leidžia mums lengvai atlikti palyginimus:

.. tabularcolumns:: |L|l|

+--------------------------------+----------------------------------------+
| **Palyginimų operatoriai**     | **Reikšmė**                            |
+================================+========================================+
| ==                             | Lygu                                   |
+--------------------------------+----------------------------------------+
| <, <=                          | Mažiau, mažiau arba lygu               |
+--------------------------------+----------------------------------------+
| >, >=                          | Daugiau, daugiau arba lygu            |
+--------------------------------+----------------------------------------+
| !=                             | Nelygu                                 |
+--------------------------------+----------------------------------------+

Perrašius palyginimus viršuje į Python programavimo kalbą, tai atrodytų taip::

	score > 100
	name ==  "Harry"
 	acceleration  != 0


Palyginimų naudojimas
^^^^^^^^^^^^^^^^^^^^^

Palyginimo rezultatas yra teigiamas arba neigiamas. ``True`` ir ``False`` yra specialios vertės, žinomos kaip ** loginio kintamojo bool vertės **. Galite jas naudoti, kad nustatytumėte, ką atliks jūsų programos. Galbūt jau naudojote tai kituose pavyzdžiuose. Šiame pavyzdyje „micro:bit” rodys rodyklę, nukreiptą į x ašies pasvirimo taško kryptį::

	from microbit import *
	
	while True:
	
	    x_acceleration = accelerometer.get_x()
	
	    if x_acceleration > 100:
	         display.show(Image.ARROW_E)
	
	    if  x_acceleration < 100:
	         display.show(Image.ARROW_W) 

Sąrašai
-------

.. figure:: lists.jpg 
 
   Paveiksliukas iš: <http://www.bbc.co.uk/education/guides/zy9thyc/revision>

Sąrašai yra naudingi saugant kelias vertes kartu. Tarkime, jūs norite išsaugoti žaidėjo balus. Galite naudoti aukščiau pavaizduotą sąrašą. Sąrašas turi vieną langelį kiekvienai vertei. Langeliai, arba dėžutės, yra žinomos kaip „elementai”.

Pažiūrėkite kaip sudaryti sąrašus Python programavimo kalboje. Norėdami sukurti sąrašą Python, turite sugalvoti sąrašo pavadinimą ir kas jame bus:: 

	from microbit import *

	highScores = [25, 20, 10, 15, 30]       # Create a list and store some values in it.
	print(highScores[0])			# Print 25
	print(highScores[3])			# Print 15

Sąrašo elemento vertės nustatymas yra paprastas, tereikia prisiminti, kad Python skaičiuoja elementus pradedant nuo „0”. Mūsų sąrašo ``highScores``, kuris yra viršuje, ``highScores[0]`` yra 25 ir ``highScores[3]`` yra 15.

Nenuostabu, kad „Python” turi funkcijų, padedančių apdoroti sąrašus. Žemiau pateiktas kodas patikrina kiekvieną masyvo (array) elementą atskirai, kad galėtumėte juos apibendrinti ir apskaičiuoti vidutinį aukštą rezultatą::

	print("Average High Score: ") 		

	total = 0
	for score in highScores: 		# For each element ...
		total = total + score

	average = total / len(highScores)  # Use the len() function here to find the length of the array 
	print(average)  

Pridėti į sąrašą
^^^^^^^^^^^^^^^^
Tais atvejais, kai nėra žinoma, kokio dydžio turi būti masyvas arba kokios bus sąraše esančios vertės, galite užpildyti sąrašą su temperatūros rodmenimis arba pagreičio matuoklio reikšmėmis. Šis kodas parodo kaip tai padaryti::

	from microbit import *

	recordedTemperature = [] 		# Create an empty list
	for i in range(100):			# Add 100 temperature values
		recordedTemperature.append(temperature())
		sleep(1000)			 

``For`` ciklas įvykdomas 100 kartų ir ``i`` turės reikšmes nuo 0 iki 99. Tai pamatuos temperatūrą kas sekundę šimtą kartų ir įkels gautas vertes į sąrašo galą.

Ištrinti iš sąrašo
^^^^^^^^^^^^^^^^^^
Yra du būdai skirti elementų ištrynimui iš sąrašo::

	highScores.delete(24)

Tai ištrins pirmąjį elementą, kurio vertė yra 24.
Norint ištrinti elementą tam tikroje vietoje, kai žinoma tiksli jo vietą::
 
	highScores.pop(3)

Tai ištrins arba išstums elementą esantį tam tikroje sąrašo vietoje. Prisiminkite tai::

	highScores.pop() 
	
ištrins paskutinį elementą sąraše.
