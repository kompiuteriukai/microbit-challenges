********************
Kontrolinės struktūros
********************
Kartais norime kontroliuoti kas vyksta programoje. Norite pakartoti kokį nors veiksmą daugybę kartų?
Tam skirtos programinės kilpos. Galbūt norite, kad kas nors įvyktų tik tuomet, kai įvyko tam tikras įvykis? Pažvelkite į
sąlygas, kurios jums padės. Žinoma, bet kurioje programoje naudosite visus šiuos dalykus tam, kad „micro:bit” darytų
viską, ką norite. Štai čia prasideda visas įdomumas.

.. image:: control_structures_icons.jpg
   :align: left

Jau matėte kaip iš eilės rašyti instrukcijas ar pareiškimus bei generuoti duomenis juos įvedant ar pateikiant. Likusioje
šio skyriaus dalyje apžvelgsime programines kilpas, pasirinkimus ir funkcijas.

Programinės kilpos
==================
Yra dviejų tipų kilpos: ``for`` kilpos, leidžiančios skaičiuoti kiek kartų veiksmas buvo atliktas, ir ``while`` kilpos, leidžiančios atlikti veiksmą iki kol nurodyta sąlyga daugiau nebevyksta.

„For” kilpos
------------
Kartais norime atlikti veiksmą tam tikrą kiekį kartų. Pavyzdžiui: uždegti LED lemputes abiejose ekrano pusėse taip sukuriant
trasą. Galime naudoti ``for`` kilpas kurios atliktų skaičiavimą taip::

	from microbit import *

	for i in range (5):
	   display.set_pixel(0,i,9) 	# set the pixel in column 0, row i to 9 
	   display.set_pixel(4,i,9)	# set the pixel in column 4, row i to 9 

Galime naudoti ``for loop`` taip, kad pirmiau uždegtų LED lemputes vienoje pusėje, o vėliau kitoje::

    from microbit import *

    display.clear()
    for x in range(0, 5):
        for y in range(0, 5):
            display.set_pixel(x,y,9)  

``For loop`` leidžia atlikti kilpą norimą nustatytą kiekį kartų. Išorinė kilpa::

        for x in range(0,5):

įvykdys veiksmą penkis kartus, kiekvieną kartą pakeičiant ``x`` iš eilės einančiomis vertėmis nuo ``0`` iki ``4``. Kilpa sustos pasiekusi 5, paskutinę vertę diapozone.

Vidinė kilpa::

        for y in range(0,5):

įvykdys veiksmą penkis kartus, kiekvieną kartą pakeičiant ``y`` iš eilės einančiomis vertėmis nuo ``0`` iki ``4``. Vėlgi, kilpa sustos pasiekus 5, paskutinę vertę diapozone.

„While” kilpos
--------------
Vienas iš labiausiai paplitusių atveju kada naudojama kilpą ``while``, kai norime, kad kažkas vyktų amžinai, iki kol 
„micro:bit” bus išjungtas arba perkrautas. Galbūt suprogramavote „micro:bit” su savo mėgstamiausiu žaidimu arba galbūt jis
renka temperatūros duomenis klasės kampe. Žemiau pateikiamas pavyzdys programos, kuri kartosis amžinai::

	from microbit import *
	
	while True:
	    display.scroll("Hello UCL)

Ši programa pakartotinai rodys žinutę ``Hello UCL``. Tikriausiai turėsite bent vieną ``while True:`` kilpą savo programoje
tam, kad „micro:bit” nuolatos veiktų.

Tačiau ką daryti jei norite imtis veiksmų tik tada, kai vyksta veiksmas? Galbūt norite parodyti paveikslėlį kai temperatūra, kurią matuoja „micro:bit”, nukrenta žemiau tam tikros vertės? Tada jums reikės patikrinti temperatūrą taip::

	from microbit import *
	
	while temperature() < 18:
	    display.scroll(Image.SAD)
	    sleep(1000)

	display.clear()

Pasirinkimas
============
Pasirinkimai, pasirinkimai, pasirinkimai. Kartais norime pradėti veiksmą, jei įvyko kažkas konkretaus. Tam galime naudoti ``if`` ir ``else`` pareiškimus.
Šiame pavyzdyje rodysime mirksinčią širdutę, jeigu  yra paspaustas mygtukas ``A``, ir linksmą veiduką, jeigu yra paspaustas mygtukas ``B``. Jeigu joks mygtukas nėra paspaustas, rodysime vaiduoklį::

	from microbit import *
	import love
	
	while True:
	    if button_a.is_pressed():
		love.badaboom()
	
	    elif button_b.is_pressed():
		display.show(Image.HAPPY)
	
	    else:
		display.show(Image.GHOST)

	    sleep(100)

Atkreipkite dėmesį į tai, kaip sutrumpinamas ``else if`` pavirsta ``elif``. Jeigu nenorite, to daryti neprivalote, tačiau tai sutaupo laiko rašant.

Funkcijos 
=========
Programavimo metu naudojamos funkcijos ir metodai „supakuojami“ į naudingus kodo fragmentus. Juos galime juos naudoti, kada tik norime. Tikriausiai, jau naudojote funkcijas ir metodus dar prieš mums pradedant apie tai kalbėti. Šioje pamokoje mes nebeaptarinėsime metodų, bet paaiškinsime, kaip naudoti ir parašyti savo funkcijas.

Funkcijų naudojimas
-------------------
Funkcijos yra puikus dalykas, nes galite jas naudoti daugiau nei vienoje programoje. Taip pat galite naudoti ir kitų žmonių parašytas funkcijas. Python programavimo kalboje naudingos funkcijos gali būti sugrupuotos į modulius (žinoma, neprivalote to daryti). Modulis „random” yra geras pavyzdys. Tam, kad galėtumėte naudoti funkciją iš „random” modulio, visų pirma turite jį įkelti į programą. Kai tai padarėte, galite naudoti bet kurią funkciją iš to modulio. Pateikiami du pavyzdžiai su funkcijomis iš „random” modulio, kurias tikriausiai norėtumėte panaudoti.

Atsitiktinis skaičius intervale
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Daugeliu atvejų norėsite sugeneruoti atsitiktinį sveiką skaičių iš tam tikro intervalo. ``Random.randint()`` funkcija leis jums tai padaryti::

	from microbit import *
	import random
	
	display.show(str(random.randint(1, 6)))

Aukščiau pateiktoje programoje bus sugeneruotas atsitiktinis skaičius nuo 1 iki 5 (viršutinė riba). Šiuo atveju 6 nebus įtrauktas.
    
Atsitiktinis pasirinkimas
^^^^^^^^^^^^^^^^^^^^^^^^^
Šiame programos fragmente funkcija ``random.choice`` patikrins kiek elemtų yra vardų sąraše, sugeneruos atsitiktinį sveikąjį skaičių intervale nuo 0 iki vardų sumos sąraše skaičiaus ir pateiks atsitiktinį vardą iš sąrašo susijusiu su tuo skaičiu::

	from microbit import *
	import random
	
	names = ["Mary", "Yolanda", "Damien", "Alia", "Kushal", "Mei Xiu", "Zoltan" ]
	
	display.scroll(random.choice(names))


Parašykite savo funkciją
---------------------
Savų funkcijų rašymas gali padėti susitvarkyti savo programos kodą, padaryti ji švarų ir gražų. Štai paprastos funkcijos, kuri spausdina pranešimą, pavyzdys::


	def showGreeting():
		print("Hello Friend!")

Norėdami panaudoti šią funkciją galite ją iškviesti taip::

	showGreeting()

Tai nėra labai įdomi funkcija? Naudodami „parametrus” ir „grąžinamas vertes” galite sukurti sudėtingesnias funkcijas. Jei galvotumėte apie funkciją kaip apie juodają dėžę, tai įvedus reikšmes vienoje pusėje, gautume jas kitoje. Tarkime, jūs norite parašyti nedidelę programą, kuri pasveikintų draugus žinute, kurioje būtų jų vardai ir amžius. Programa atrodytų štai taip::

	from microbit import *

	def printBirthday(name, age):
	    return "Happy Birthday " + name + ", you are " + str(age) + " years old"   


 	display.scroll(printBirthday("Tabitha", 8))
 	display.scroll(printBirthday("Henry", 9))
 	display.scroll(printBirthday("Maria", 11))
		
Funkcija ``printBirthday`` sukuria gimtadienio sveikinimą ir paverčia tai į eilutę. Phyton funkciją ``str()`` panaudota tam, kad paverstumėte ``age``, kuris yra skaičius, į eilutę. Neprivalote naudoti kitų funkcijų ar grąžinti reikšmių savo funkcijose, jeigu to nenorite.
