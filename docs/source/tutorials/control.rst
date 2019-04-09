********************
Kontrolės struktūros
********************
Kartais norime kontroliuoti kas vyksta programoje, nori pakartoti kokį nors veiksmą daugybę kartų?
Programinės kilpos tau padės. Galbūt nori, kad kas nors įvyktų tik tuomet kai įvyko tam tikras įvykis? Pažvelk į
sąlygas, jos tau padės. Žinoma, bet kurioje programoje naudosi visus šiuos dalykus tam, kad „micro:bit” darytų
viską ką nori ir štai čia prasideda visas įdomumas.

.. image:: control_structures_icons.jpg
   :align: left

Jau matei kaip rašyti instrukcijas ar pareiškimus iš eilės ir generuoti duomenis juos įvedant ar pateikiant. Likusioje
šio skyriaus dalyje apžvelgsime programines kilpas, pasirinkimus ir funkcijas.

Programinės kilpos
==================
Yra dviejų tipų kilpos: ``for`` šios kilpos leidžia skaičiuoti kiek kartų veiksmas buvo atliktas ir ``while`` kilpos leidžia
atlikti veiksmą iki kol nurodyta sąlyga daugiau nebevyksta.

„For” kilpos
------------
Kartais norime atlikti veiksmą tam tikrą skaičių kartų. Pavyzdžiui: uždegti LED lemputes abiejose ekrano pusėse taip sukuriant
trasą. Galime naudoti ``for`` kilpas kurios atliktų skaičiavimą taip::

	from microbit import *

	for i in range (5):
	   display.set_pixel(0,i,9) 	# set the pixel in column 0, row i to 9 
	   display.set_pixel(4,i,9)	# set the pixel in column 4, row i to 9 

Dar vienas pavyzdys. Galime naudoti ``for loop`` taip, kad uždegtų LED lemputes vienoje pusėje ir paskui kitoje::

    from microbit import *

    display.clear()
    for x in range(0, 5):
        for y in range(0, 5):
            display.set_pixel(x,y,9)  

``For loop`` leidžia atlikti kilpą norimą kiekį kartų kuris buvo nustatytas. Išorinė kilpa::

        for x in range(0,5):

įvykdys veiksmą penkis kartus pakeičiant ``x`` iš eilės einančiomis vertėmis nuo ``0`` iki ``4`` kiek vieną kartą. Kilpa sustos pasiekus 5, paskutinę vertę diapozone.

Vidinė kilpa::

        for y in range(0,5):

įvykdys veiksmą penkis kartus pakeičiant ``y`` iš eilės einančiomis vertėmis nuo ``0`` iki ``4`` kiek vieną kartą. Vėlgi, kilpa sustos pasiekus 5, paskutinę vertę diapozone.

„While” kilpos
--------------
Vienas iš labiausiai paplitusių dalykų kada naudojame kilpą ``while`` tai kai norime, kad kažkas vyktų amžinai iki kol 
„micro:bit” yra išjuntas arba perkrautas. Galbūt suprogramavai „micro:bit” su savo mėgstamiausiu žaidimu arba galbūt jis
renka temperatūros duomenis klasės kampe. Žemiau pateikiamas pavyzdys programos kuri kartosis amžinai::

	from microbit import *
	
	while True:
	    display.scroll("Hello UCL)

Ši programa pakartotinai rodys žinutę ``Hello UCL``. Tikriausiai turėsi bent vieną ``while True:`` kilpą savo programoje
tam, kad „micro:bit” pastoviai veiktų.

Bet kas, jeigu nori imtis veiksmų tik tada, kai vyksta veiksmas? Galbūt nori parodyti atvaizdą jeigu temperatūra kurią matuoja „micro:bit” nukrenta žemiau tam tikros vertės, tada tau reikės patikrinti temperatūrą taip::

	from microbit import *
	
	while temperature() < 18:
	    display.scroll(Image.SAD)
	    sleep(1000)

	display.clear()

Pasirinkimas
============
Pasirinkimai, pasirinkimai, pasirinkimai. Kartais norime pradėti veiksmą, jei įvyko kažkas konkretaus. Tam galime naudoti ``if`` ir ``else`` pareiškimus.
Šiame pavyzdyje rodysime mirksinčią širdutę jeigu mygtukas ``A`` yra paspaustas ir linksmą veiduką jeigu mygtukas ``B`` yra paspaustas. Jeigu joks mygtukas nėra paspaustas rodysime vaiduoklį::

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

Atkreiptike dėmesį į tai kaip sutrumpinamas ``else if`` pavirsta ``elif``, neprivalai to daryti jeigu nenori, tai tik sutaupo laiko rašant.

Funkcijos 
=========
Programavimo metu naudojamos funkcijos ir metodai „supakuojami“ į naudingus kodo fragmentus ir galime juos naudoti, kai tik norime. Tikriausiai jau naudojai funkcijas ir metodus dar prieš mums pradedant apie tai kalbėti. Šioje pamokoje mes nebeaptarinėsime metodų, bet paaiškinsime, kaip naudoti ir parašyti savo funkcijas.

Funkcijų naudojimas
-------------------
Funkcijos yra puikus dalykas, nes galime jas naudoti daugiau nei tik vienoje programoje. Taipogi galime naudoti ir kitų žmonių parašytas funkcijas. „Python” programavimo kalboje naudingos funkcijos gali būti sugrupuotos į modulius (žinoma neprivalai to daryti), „random” modulis yra geras pavyzdys. Tam, kad galėtume naudoti funkciją iš „random” modulio visų pirma turime jį įkelti į programą. Kai tai padarėme galime naudoti bet kurią funkciją iš to modulio. Pateikiame du pavyzdžius su funkcijomis iš „random” modulio, kurias tikriausiai norėtum panaudoti.

Atsitiktinis skaičius intervale
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Daugeliu atvėju norėsime sugeneruoti atsitiktinį sveiką skaičių iš tam tikro intervalo. ``Random.randint()`` funkcija leis mums tai padaryti::

	from microbit import *
	import random
	
	display.show(str(random.randint(1, 6)))

Programoje, pateiktoje aukščiau, atsitiktinis skaičius bus sugeneruotas tarp 1 ir 5, viršutinė riba, šiuo atveju 6 nebus įtraukta.
    
Atsitiktinis pasirinkimas
^^^^^^^^^^^^^^^^^^^^^^^^^
Šiame programos fragmente funkcija ``random.choice`` patikrins kiek elemtų yra vardų sąraše, sugeneruos atsitiktinį sveikąjį skaičių intervale nuo 0 iki vardų sumos sąraše skaičiaus ir pateiks atsitiktinį vardą iš sąrašo susijusiu su tuo skaičiu::

	from microbit import *
	import random
	
	names = ["Mary", "Yolanda", "Damien", "Alia", "Kushal", "Mei Xiu", "Zoltan" ]
	
	display.scroll(random.choice(names))


Parašyk savo funkciją
---------------------
Savų funkcijų rašymas gali padėti susiorganizuoti savo programos kodą, padaryti ji švarų ir gražų. Štai paprastos funkcijos, kuri spausdina pranešimą, pavyzdys::


	def showGreeting():
		print("Hello Friend!")

Norėdami panaudoti šią funkciją galime ją iškviesti taip::

	showGreeting()

Tai nėra labai įdomi funkcija? Naudodami „parametrus” ir „grąžinamas vertes” galime sukurti sudėtingesnias funkcijas. Jei galvotume apie funkciją kaip apie juodają dėžę, tai įvedus reikšmes vienoje pusėje gautume jas kitoje. Tarkime, mes norime parašyti nedidelę programą, kuri pasveikintų draugus žinute kurioje būtų jų vardai ir amžius. Programa atrodytų štai taip::

	from microbit import *

	def printBirthday(name, age):
	    return "Happy Birthday " + name + ", you are " + str(age) + " years old"   


 	display.scroll(printBirthday("Tabitha", 8))
 	display.scroll(printBirthday("Henry", 9))
 	display.scroll(printBirthday("Maria", 11))
		
Funkcija ``printBirthday`` sukuria gimtadienio sveikinimą ir paverčia tai į eilutę. Panaudojome „python” funkciją ``str()`` tam, kad paverstume ``age``, kuris yra skaičius, į eilutę. Neprivalai naudoti kitų funkcijų ar grąžinti reikšmes savo funkcijose, nebent to nori.
