*****************
Akcelerometras
*****************
„Micro:bit” akcelerometras matuoja gravitacijos jėgą. Akcelerometras gali matuoti gravitacijos jėgą nuo +2G iki -2G.

.. image:: accelerometer.jpg
   :scale: 80 %

„Micro:bit” matuoja judėjimą trimis ašimis:

* X - pakreipimas iš kairės į dešinę.
* Y - pakreipimas į priekį ir atgal.
* Z - kėlimas į viršų ir į apačią.

.. image:: microbitAxes.jpg

Paprastos funkcijos
===================
Kiekvienos ašies matavimas yra teigiamas arba neigiamas skaičius nurodomas mili-G formatu. Kai rodoma reikšmė yra 0, vadinasi įrenginys yra tolygus toje ašyje. 1024 mili-G yra akceleracija dėl gravitacijos.

Vienu metu galite pasiekti visus tris akcelarijos parametrus ir juos laikyi sąraše arba tiesiog pasiekti kiekvieną parametrą atskirai. Pasiteiraukite savo mokytojo apie sąrašus, bet kol kas naudokite šį kodą: 

	from microbit import *

	while True:
	    x = accelerometer.get_x()
	    y = accelerometer.get_y()
	    z = accelerometer.get_z()
	    print("x, y, z:", x, y, z)
	    sleep(500)

Visa tai įkelkite ir atidarykite serijinį monitorių. Laikykite „micro:bit” tolygiai, LED lemputėmis į viršų. Turėtumėte matyti, kad X ir Y gravitacijos jėga yra netoli nulio ir Z gravitacijos jėga yra netoli -1024. Tai pasako, kad gravitacija traukia „micro:bit” žemyn. Apverskite „micro:bit”, kad LED lemputės žiūrėtų į apačią. Z reikšmė turėtų būti teigiama +1024 mili-G. Jeigu papurtysite „micro:bit” pakankamai stipriai, pamatysite, kad pagreitis pakyla iki +2048 mili-G. Tai yra todėl, kad akcelerometras gali maksimaliai matuoti iki +2048 mili-G: tikras skaičius gali būti ir didesnis.

Jeigu kada nors susimąstėte, kaip mobilusis telefonas žino, kur yra ekrano viršus ir parodo paveiksliuką taisyklinga kryptimi ekrane, tai yra todėl, kad jis, kaip ir programa viršuje, naudoja akcelerometrą. Žaidimų valdymo pulteliai irgi turi akcelerometrus, tam, kad padėtų vairuoti ir judėti žaidime.
	
Gestai
--------

Labai įdomus šalutinis poveikis turint akcelerometrą yra judesių aptikimas. Jeigu pajudinsite „micro:bit” tam tikra kryptimi (kaip gestą), jis gali tai aptikti.

„Micro:bit” gali atpažinti šiuos gestus: ``up`` (į viršų), ``down`` (į apačią), ``left`` (į kairę), ``right`` (į dešnę), ``face up`` (veidu į viršų), ``face down`` (veidu žemyn), ``freefall`` (laisvas kritimas), ``3g``, ``6g``, ``8g``, ``shake`` (purtymas). Judesiai visada pateikti kaip teksto eilutė. Dauguma pavadinimų turėtų būti savaime suprantami, ``3g``, ``6g`` ir ``8g`` aptinkami kai įrenginys susiduria su šiais G-jėgos lygiais (pvz: kai astronautai yra paleidžiami į kosmosą).

Tam, kad gautumėte esamą judesį, naudokite ``accelerometer.current_gesture`` metodą. Jo rezultas bus vienas iš gestų pateiktų viršuje. Pavyzdžiui, ši programa privers įrenginį nusišypsoti tik tuo atvėju, kai jis bus veidu į viršų::

    from microbit import *

    while True:
        gesture = accelerometer.current_gesture()
        if gesture == "face up":
            display.show(Image.HAPPY)
        else:
            display.show(Image.ANGRY)

Dar kartą primenu, jeigu norite, kad įrenginys reaguotų į besikeičiančias sąlygas, turime naudoti ``while`` kilpą. Kilpos viduje esamasis gestas yra nuskaitomas ir įdedamas į ``gesture``. Sąlyga ``if`` patikrina jeigu gestas yra lygus ``"face up"`` (Python programavimo kalboje ``==`` patikrina ligybę, viengubas ženklas ``=`` yra naudojamas priskyrimui - taip pat kaip mes priskiriame gestą nuskaitytam objektui ``gesture``). Jeigu gestas yra lygus ``"face up"``, tuomet ekranas rodys linksmą šypsenėlę. Kitu atvėju įrenginys bus nuliūdęs.

Išplėstinės funkcijos
=====================
Akcelerometras neturi jokių išplėstinių funkcijų. Bet verta pasižiūrėti kaip galime panaudoti 3D akceleraciją, kad aptiktume skirtingus judesius tokius kaip papurtymą. Akceleracija yra žinoma kaip vektorinis kiekis (pasiklauskite matematikos mokytojo) - magnitudė (dydis, ilgis) ir kryptis. Norėdami gauti bendrą magnitudę, nepriklausomai nuo orientacijos, turime atlikti keletą matematinių veiksmų. Jeigu turėtume tik X ir Y ašis (pvz. 2D akceleraciją), situacija būtų tokia:

.. image:: microbitOverallAcceleration.jpg
   :scale: 60 %
   :align: left

Galime apskaičiuoti magnitudės (ilgį) gautą iš Pitagoro teoremos:

.. math::

   acceleration = \sqrt{x^2 + y^2}

Tačiau mes turime 3D akcelerometrą ir toks pats principas taikomas kai turime X, Z ir Y ašis. Taigi bendra magnitudė gauta iš akceleracijos vektoriaus yra:

.. math::

   acceleration = \sqrt{x^2 + y^2 + z^2}

Žemiau pateikiamas kodas apskaičiuojantis bendrą akceleraciją::

	from microbit import *
	import math

	while True:
	    x = accelerometer.get_x()
	    y = accelerometer.get_y()
	    z = accelerometer.get_z() 
	    acceleration = math.sqrt(x**2 + y**2 + z**2)
	    print("acceleration", acceleration)
	    sleep(500)

Jeigu nejudinsite akcelerometro (padėkite jį ant stalo), jis turėtų rodyti gravitacijos jėgą  ~1G, nepriklausomai kokioje orientacijoje šiuo metu yra „micro:bit”, ir ji keisis judinant įrenginį. Tiesą, vertė kis netgi jeigu jo ir nejudinsite, nes akcelerometras nėra tobulas matavimo įrenginys. Norint tai išspręsti, turime naudoti kalibracijos procesą, kad gautume tikslų rezultatą.

Idėjos projektams su akcelerometru
=========================================
* Naudojant „micro:bit” muzikos biblioteką, grokite natą priklausomai nuo gauto akcelerometro rodmens. Užuomina: nustatykite natos aukštį pasitelkiant akcelerometro rodmenis.
* Parodykite raidę 'L' arba 'R' priklausomai nuo to ar „micro:bit” pakreiptas į kairę ar į dešnę.
* Padarykite, kad LED lemputės užsidegtų kai gravitacinės jėgos magnitudė yra aukštesnė negu 1024 mili-G.
* Pajudinus „micro:bit” užsidegtų LED lemputės.
* Sukurkte kauliuką: naudokite Phyton atsitiktinę funkciją. Įveskite ``import random`` savo programos viršuje ir naudokite ``random.randrange(start, stop)``. Tai sugeneruos atsitiktinį numerį tarp ``start`` ir ``stop`` - 1.
