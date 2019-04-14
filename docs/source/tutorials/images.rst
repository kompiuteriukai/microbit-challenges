***********
LED Ekranas
***********

Tai yra greita apžvalga parodanti ką galite padaryti su LED ekranu. Idėja yra ta, kad galite naudoti šią informaciją eksperimentuoti ir sukurti kažką sau. Pabandyk, pasinagrinėk, pažiūrėk kas gaunasi ir ką galėtum sukurti. „Micro:bit“ turi 25 šviesos diodus išdėstytus kaip pateikta paveiksliuke žemiau. Diodai sunumeruoti nuo (0,0) viršutinio kairiojo kampo iki (4,4) apatinio dešniojo kampo. Gali naudoti diodus kaip labai mažą ekraną kuris rodytų simbolį, simbolių eilutę arba mažą paveikliuką panašiai kaip šypsenėlė rodoma čia. Galime valdyti ir diodų ryškumą. Pažiūrėkime kaip juos naudoti.

.. image:: happy.png
   :scale: 40 %


Paprastos funkcijos
===================

Rodyti teksto eilutę arba paveiksliuką
--------------------------------------

Galite lengvai atvaizduoti simbolius LED ekrane štai taip::

    from microbit import *

    display.show("Hello")

Simboliai kuriuos rodysite turi būti parašyti tarp kabučių " " arba ' '.

„Micro:bit“ turi daug paveiksliukų kuriuos galite naudoti.
Pavyzdžiui, jeigu norite, kad įrenginys nusišypsotų, rašote::

    from microbit import *

    display.show(Image.HAPPY)

Čia pateikiama keletas kitų atvaizdų kuriuos galite naudoti:

    * ``Image.HEART``, ``Image.HEART_SMALL`` 
    * ``Image.HAPPY``, ``Image.SMILE``, ``Image.SAD``, ``Image.CONFUSED``, ``Image.ANGRY``, ``Image.ASLEEP``, ``Image.SURPRISED``, ``Image.SILLY``, ``Image.FABULOUS``, ``Image.MEH``, ``Image.YES``, ``Image.NO``
    * ``Image.ARROW_N``, ``Image.ARROW_NE``, ``Image.ARROW_E``, ``Image.ARROW_SE``, ``Image.ARROW_S``, ``Image.ARROW_SW``, ``Image.ARROW_W``, ``Image.ARROW_NW``
    * ``Image.MUSIC_CROTCHET``, ``Image.MUSIC_QUAVER``, ``Image.MUSIC_QUAVERS``
    * ``Image.XMAS``, ``Image.PACMAN``, ``Image.TARGET``, ``Image.ROLLERSKATE``, ``Image.STICKFIGURE``, ``Image.GHOST``, ``Image.SWORD``, ``Image.UMBRELLA``
    * ``Image.RABBIT``, ``Image.COW``, ``Image.DUCK``, ``Image.HOUSE``, ``Image.TORTOISE``, ``Image.BUTTERFLY``, ``Image.GIRAFFE``, ``Image.SNAKE``


Išeilės einanti teksto eilutė 
-----------------------------
Tam, kad teksto eilutė vientisai judėtų ekrane, naudokite::

    from microbit import *

    display.scroll("Hello!")


Išvalyti ekraną
-----------------
Jeigu norite išvalyti LED ekraną, galite tai padaryti taip::

    from microbit import *

    display.clear()


Išplėstinės funkcijos
=====================

Pikselio nustatymas
-------------------
Galite nustatyti pikselį LED ekrane naudodami ``set_pixel`` metodą::

    from microbit import *

    display.set_pixel(0,4,9)

Tai nustato diodą stulpelyje ``0`` ir eilutėje ``4`` į ryškumą ``9``. Ryškumo reikšmė gali būti bet kuris sveikas skaičius nuo 0 iki 9, kai 0 išjungia diodą, o 9 nustato jį ryškiausiu. Galite naudoti ``for loop`` norėdami įjungti visus diodus išeilės::

    from microbit import *

    display.clear()
    for x in range(0, 5):
    	for y in range(0, 5):
    	    display.set_pixel(x,y,9)  

``For loop`` leidžia atlikti kilpą tam tikrą kiekį kartų, naudojant skaitiklį. Išorinė kilpa::

	for x in range(0,5)

įvykdys kilpą penkis kartus nuosekliai pakeičiant ``x`` diapazone nuo ``0`` iki ``4`` kiek vieną kartą. Kilpa sustos prieš jai pasiekiant paskutinę reikšmę diapazone.

Vidinė kilpa::

	for y in range(0,5):

įvykdys kilpą penkis kartus nuosekliai pakeičiant ``y`` diapazone nuo ``0`` iki ``4`` kiek vieną kartą. Kilpa sustos prieš jai pasiekiant paskutinę reikšmę diapazone.

Pasidaryk paveiksliukus pats
----------------------------
Žinoma, nori susikurti savo paveiksliukus ir atvaizduoti juos „micro:bit“ ekrane, ar ne taip?

Tai paprasta. Kiek vienam diodui gali būti suteikta viena iš dešimties reikšmių. Jeigu pikselis nustatytas į ``0`` (nulį) tai jis yra išjungtas. Jo ryškumas yra nulinis. Tačiau, jeigu nustatome ``9`` tuomet tai ryškiausias lygis. Reikšmės nuo ``1`` iki ``8`` reprezentuoja ryškumo lygius tarp išjungta (``0``) ir ryškiausia (``9``).

Apsišarvavę visa šita informacija, galime sukurti naujus paveiksliukus::

    from microbit import *

    boat = Image("05050:"
                 "05050:"
                 "05050:"
                 "99999:"
                 "09990")

    display.show(boat)

Beje, neprivalai rašyti šito per kelias eilutes. Jeigu manai, kad gali sekti kiek vieną eilutę, gali rašyti vientisai:: 

    boat = Image("05050:05050:05050:99999:09990")

(Kai paleisite programą, įrenginys rodys senovinį burlaivį „Blue Peter“ kurio stiebai yra reguliuojami laivo korpuse.)

Ar išsiaiškinai kaip piešti paveiksliuką? Ar pastebėjai, kad kiek viena fizinė ekrano eilutė atvaizduota skaičių eile pasibaigiančia ``:`` ir įterpta tarp ``"`` dvigubų kabučių? Kiek vienas skaičius nusako ryškumą. Yra penkios eilutės su penkiais skaičiais tad įmanoma individualiai nustatyti kiek vieno pikselio ryškumą kiek vienoje fizinio ekrano eilutėje.

Animacija
---------
Statiniai vaizdai yra įdomūs, bet dar smagiau yra priversti juos judėti. Tai irgi neįtikėtinai lengva padaryti su „micro:bit“, tiesiog naudokite vaizdų sąrašą!

Laimei mes jau turime keletą integruotų sąrašų su paveiksliukais. Jie vadinasi ``Image.ALL_CLOCKS`` ir ``Image.ALL_ARROWS``::

    from microbit import *

    display.show(Image.ALL_CLOCKS, loop=True, delay=100)

Mes nurodome „micro:bit“ naudoti ``Image.ALL_CLOCKS`` ir jis supranta, kad jam reikia atvaizduoti kiek vieną paveiksliuką sąraše, vieną po kito. Dar mes nurodome „micro:bit“ laikyti visą tai kilpoje (tam, kad animaciją tęstūsi amžinai) pasakydami ``loop=True``. Be to mes taip pat pasakome, kad tarpas tarp kiek vieno vaizdo turėtų būti tik 100 milisekundžių (viena dešimtoji sekundės) naudodami argumentą ``delay=100``.

Dabar pažiūrėkime kaip susikurti savo animaciją. Pirmiausia reikia sukurti sąrašą.
Štai valčių sąrašas::

    all_boats = [boat1, boat2, boat3, boat4, boat5, boat6]

„Python“ programavimo kalboje, sąraše gali laikyti be ką, net ir paveiksliukus. Mano pavyzdyje aš padarysiu taip, kad valtis paskestų ekrano apačioje. Norėdamas tai įgyvendinti sukursiu 6 paveiksliukus ir sudėsiu juos į sąrašą pavadinimu ``all_boats``::

    from microbit import *

    boat1 = Image("05050:"
                  "05050:"
                  "05050:"
                  "99999:"
                  "09990")

    boat2 = Image("00000:"
                  "05050:"
                  "05050:"
                  "05050:"
                  "99999")

    boat3 = Image("00000:"
                  "00000:"
                  "05050:"
                  "05050:"
                  "05050")

    boat4 = Image("00000:"
                  "00000:"
                  "00000:"
                  "05050:"
                  "05050")

    boat5 = Image("00000:"
                  "00000:"
                  "00000:"
                  "00000:"
                  "05050")

    boat6 = Image("00000:"
                  "00000:"
                  "00000:"
                  "00000:"
                  "00000")

    all_boats = [boat1, boat2, boat3, boat4, boat5, boat6]
    display.show(all_boats, delay=200)

Galiausiai galime nurodyti „micro:bit“ animuoti paveiksliukų sąrašą naudojant ``display.show``.

Projektai su LED ekranu
==========================
* Išbandyk keletą jau sukurtų paveiksliukų ir pažiūrėk kaip jie atrodo.
* Sukurk animaciją iš ``Image.ALL_ARROWS`` sąrašo. Kaip išvegti amžinos kilpos (užuomena: priešingai negu ``True`` yra ``False``). Gali pakeisti animacijos greitį?
* Sukurk savo paveiksliuką. Pabandyk padaryti taip, kad jis išlėto išnyktų ir vėl atsirastų.
* Sukurk taškiuką LED ekrane. Priversk jį šokinėti paspaudus mygtuką.
