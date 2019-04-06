Duomenų tipai
=============

„Micro:bit” programose naudosime įvairių tipų vertes, pavyzdžiui: galime gauti pagreičio reikšmes iš akselerometro. Kita vertus, galbūt norime suskaičiuoti, kiek mygtukų paspaudžia vartotojas, arba parodyti vartotojui pranešimą, nurodantį kambario temperatūrą. Norėdami visą tai padaryti, turime sugebėti apibūdinti visus duomenis, kurios norime naudoti. „Python“ ir dauguma kitų programavimo kalbų atpažįsta kelis duomenų tipus, įskaitant:

* Sveikuosius skaičius - tai yra sveikieji skaičiai.
* Realiuosius skaičius - tai yra skaičiai su kableliu ir liekana po kablelio.
* Eilutes - juose gali būti simbolių, kurios norime traktuoti kaip tekstą, pavyzdžiui: raidžių, skaičių ir simbolių derinys.  
* Būlius - tai yra loginės sistemos dalis, kuri turi dvi reikšmes, teigiamą ir neigiamą.

Paprastoje programoje galėtume juos visus panaudoti. Čia pateikiami duomenų tipai, kuriuos galėtume naudoti programoje, kurioje saugoma informacija apie mėgstamus „micro:bit” žaidimus:

.. figure:: dataTypes.png

   Paveiksliukas iš: <http://www.bbc.co.uk/education/guides/zwmbgk7/revision/3>

Kintamieji
----------

Galime įsivaizduoti kintamajį kaip dėžutę, kurioje kompiuteris gali laikyti reikšmę. Reikšmė toje dėžutėje gali pasikeisti ar kisti. Visi kintamieji yra sudaryti iš trijų dalių: pavadinimo, tipo ir reikšmės. Žemiau pavaizduoti trijų tipų kintamieji::

.. figure:: variable.jpg
   :scale: 60 %

   Paveiksliukas iš: <https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/Variables>

Kintamasis ``name`` turi eilutę ``Bob``, kintamasis ``winner`` turi eilutę ``True`` ir kintamasis ``score`` turi eilutę ``35``.

„Python” programavimo kalboje, mes privalome duoti pavadinimus kintamiesiems ir kai tai padarome, galime pradėti juos naudoti, paskirti ir manipuliuoti jų reikšmėmis::

	from microbit import *

	myCount = 0

	while True:
    	   if button_a.was_pressed(): 
		myCount = myCount + 1
	   sleep(2000)
	   print("Number of presses: " + str(count))

Čia panaudojome kintamąjį ``myCount`` tam, kad suskaičiuoti kiek kartų buvo paspaustas mygtukas ``A``. Ar gali pasakyti ką dar šis programos fragmentas daro?

Operacijos
----------

Numeriai
^^^^^^^^
Skaitmenines reikšmes galime naudoti su pagrindiniais aritmetiniais operatoriais: `` +, -, *, / `` tokiu pat būdu, kaip ir su skaičiuokle.
Pažvelkime į aritmetinių operatorių pavyzdį. Įsivaizduokite, kad norite konvertuoti temperatūrą, kurią „micro:bit” pateikia Celsijaus formatu, į Farenheitą, galite naudoti tokį kodą::

	celsiusTemp = temperature()
	fahrenheitTemp = celsiusTemp * 9 / 5 + 32  

Likusiam skaičiui apskaičiuoti naudojamas specialus operatorius „%”, vadinamas „mod”. Pavyzdžiui: galbūt norėtumėte žinoti, ar numeris yra lyginis, ar nelyginis, galite pabandyti jį padalinti iš 2, jei jis yra lyginis tada nebus jokio likučio::

	theNumber = 3
	if theNumber % 2 == 1:
	   print("The number is odd")
	else:
	   print("The number is even")

Jei likutis lygus 1, ši programa išspausdins pranešimą „The number is odd“, kitaip, programa spausdins pranešimą „The number is even“. Galite parašyti šią programą kitaip, tai rodo, kad žmonės galvoja apie problemas skirtingais būdais, o dvi programos nėra tokios pačios. 

Eilutės
^^^^^^^
Svarbiausias dalykas apie eilutes, į kurį reikia atreikti dėmesį, yra tai, kad galite jas sujungti arba susieti naudojantis simboliu „+”. Kodas::

	name = "Hayley"

	message = "Well done " + name + ". You are a winner!"

Sujungs elementus dešinėje pusėje `` = `` ir įterps rezultatą į kintamąjį, vadinamą ``message``.

Negalite sujungti skaičių su eilutėmis; norint tą padaryti pirmiausia turite konvertuoti skaičių į eilutę pasinaudojant funkcija ``str()``::

	x = temperature
	if temperature < 6:
	   display.scroll("Cold" + str(temperature))


Palyginimai
-----------

.. figure:: booleanLogic.jpg 
   :scale: 60 %

   Paveiksliukas iš: <http://www.bbc.co.uk/education/guides/zy9thyc/revision>

Dažnai programuojant mes norime palyginti vieną vertę su kita, patestuoti. Šiuos testus arba palyginimus naudojame atrankoje arba kilpose. Štai keletas anglų kalba parašytų palyginimų pavyzdžių::

	score is greater than 100
	name equals "Harry"
 	x acceleration is not equal to 0

„Python” programavimo kalba turi palyginimo operatorių rinkinį, kuris leidžia mums lengvai atlikti palyginimus:

.. tabularcolumns:: |L|l|

+--------------------------------+----------------------------------------+
| **Palyginimų operatoriai**     | **Reikšmė**                            |
+================================+========================================+
| ==                             | Lygu                                   |
+--------------------------------+----------------------------------------+
| <, <=                          | Mažiau, mažiau arba lygu               |
+--------------------------------+----------------------------------------+
| >, >=                          | Daugiau, diaugiau arba lygu            |
+--------------------------------+----------------------------------------+
| !=                             | Nelygu                                 |
+--------------------------------+----------------------------------------+

Perašius palyginimus viršuje į „Python“ programavimo kalbą, tai atrodytų taip::

	score > 100
	name ==  "Harry"
 	acceleration  != 0


Naudojant palyginimus
^^^^^^^^^^^^^^^^^^^^^

Palyginimo rezultatas yra teigiamas arba neigiamas. ``True`` ir ``False`` yra specialios vertės, žinomos kaip ** būlio vertės **, ir mes galime jas naudoti, kad nustatytume, ką atliks mūsų programos. Galbūt jau naudojote tai kituose pavyzdžiuose. Šiame pavyzdyje „micro:bit” rodys rodyklę, nukreiptą į x ašies pasvirimo taško kryptį::

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

Sąrašai yra naudingi saugant kelias vertes kartu. Tarkime, mes norime išsaugoti žaidėjo balus, galėtume naudoti tokį sąrašą, koks yra pavaizduotas aukščiau. Sąrašas turi vieną langelį kiekvienai vertei. Langeliai arba dėžutės yra žinomos kaip „elementai”.

Pažiūrėkime kaip sudaryti sąrašus „Python” programavimo kalboje. Norėdami sukurti sąrašą „Python” turime sugalvoti sąrašo pavadinimą ir kas jame bus:: 

	from microbit import *

	highScores = [25, 20, 10, 15, 30]       # Create a list and store some values in it.
	print(highScores[0])			# Print 25
	print(highScores[3])			# Print 15

Sąrašo elemento vertės nustatymas yra paprastas, tereikia prisiminti, kad „Python” skaičiuoja elementus pradedant nuo „0”. Mūsų sąrašo ``highScores``, kuris yra viršuje, ``highScores[0]`` yra 25 ir ``highScores[3]`` yra 15.

Nenuostabu, kad „Python” turi tam tikrų funkcijų, padedančių mums daryti sąrašus. Toliau pateiktame kodo fragmente bus peržiūrėtas masyvas elementais, kad galėtume juos apibendrinti ir apskaičiuoti vidutinį aukštą rezultatą::

	print("Average High Score: ") 		

	total = 0
	for score in highScores: 		# For each element ...
		total = total + score

	average = total / len(highScores)  # Use the len() function here to find the length of the array 
	print(average)  

Pridėti į sąrašą
^^^^^^^^^^^^^^^^
Bus laikas, kai mes iš anksto nežinome, kokio dydžio turi būti masyvas arba kokios bus sąraše esančios vertės. Galite užpildyti sąrašą su temperatūros rodmenimis arba pagreičio matuoklio reikšmėmis. Šis kodas parodo, kaip tai padaryti::

	from microbit import *

	recordedTemperature = [] 		# Create an empty list
	for i in range(100):			# Add 100 temperature values
		recordedTemperature.append(temperature())
		sleep(1000)			 

``For`` kylpa įvykdoma 100 kartų ir ``i`` turės reikšmes nuo 0 iki 99. Tai pamatuos temperatūrą kas sekundę šimtą kartų ir įkels gautas vertes į sąrašo galą.

Ištrinti iš sąrašo
^^^^^^^^^^^^^^^^^^
Yra du būdai, kaip ištrinti elementus iš sąrašų, kurie yra naudingi, galbūt norėsite iš sąrašo ištrinti tam tikros vertės elementą::

	highScores.delete(24)

Tai ištrins pirmą elementą, kurio vertė yra 24.
Arba, galbūt norėsite ištrinti elementą tam tikroje vietoje, jei žinote tikslią jo vietą::
 
	highScores.pop(3)

Tai ištrins arba arba 'pokštels' elementą tam tikroje sąrašo vietoje. Prisimink tai::

	highScores.pop() 
	
ištrins paskutinį elementą sąraše.
