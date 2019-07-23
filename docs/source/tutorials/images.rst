***********
LED Ekranas
***********

Tai yra greita apžvalga parodanti ką galite padaryti su LED ekranu. Idėja yra ta, kad galite naudoti šią informaciją eksperimentams ir sukurti kažką naujo. „Micro:bit“ turi 25 šviesos diodus. Jų išdėstymą galite matyti paveiksliuke žemiau. Diodai sunumeruoti nuo (0,0) viršutinio kairiojo kampo iki (4,4) apatinio dešniojo kampo. Gali naudoti diodus kaip labai mažą ekraną kuris rodytų simbolį, simbolių eilutę arba mažą paveikliuką (panašiai kaip čia rodoma šypsenėlė). Galite valdyti ir diodų ryškumą. Pažiūrėkite kaip juos naudoti.

.. image:: happy.png
   :scale: 40 %


Paprastos funkcijos
===================

Rodyti teksto eilutę arba paveiksliuką
--------------------------------------

Galite lengvai atvaizduoti simbolius LED ekrane štai taip::

    from microbit import *

    display.show("Hello")

Simboliai, kuriuos rodysite, turi būti parašyti tarp kabučių " " arba ' '.

„Micro:bit“ turi daug paveiksliukų, kuriuos galite naudoti.
Pavyzdžiui, jeigu norite, kad įrenginys nusišypsotų, rašote::

    from microbit import *

    display.show(Image.HAPPY)

Čia pateikiama keletas kitų galimų atvaizdų:

    * ``Image.HEART``, ``Image.HEART_SMALL`` 
    * ``Image.HAPPY``, ``Image.SMILE``, ``Image.SAD``, ``Image.CONFUSED``, ``Image.ANGRY``, ``Image.ASLEEP``, ``Image.SURPRISED``, ``Image.SILLY``, ``Image.FABULOUS``, ``Image.MEH``, ``Image.YES``, ``Image.NO``
    * ``Image.ARROW_N``, ``Image.ARROW_NE``, ``Image.ARROW_E``, ``Image.ARROW_SE``, ``Image.ARROW_S``, ``Image.ARROW_SW``, ``Image.ARROW_W``, ``Image.ARROW_NW``
    * ``Image.MUSIC_CROTCHET``, ``Image.MUSIC_QUAVER``, ``Image.MUSIC_QUAVERS``
    * ``Image.XMAS``, ``Image.PACMAN``, ``Image.TARGET``, ``Image.ROLLERSKATE``, ``Image.STICKFIGURE``, ``Image.GHOST``, ``Image.SWORD``, ``Image.UMBRELLA``
    * ``Image.RABBIT``, ``Image.COW``, ``Image.DUCK``, ``Image.HOUSE``, ``Image.TORTOISE``, ``Image.BUTTERFLY``, ``Image.GIRAFFE``, ``Image.SNAKE``


Judanti teksto eilutė 
-----------------------------
Kad teksto eilutė vientisai judėtų ekrane, naudokite::

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

Tai nustato diodą stulpelyje ``0`` ir eilutėje ``4`` į ryškumą ``9``. Ryškumo reikšmė gali būti bet kuris sveikas skaičius nuo 0 iki 9, kai 0 išjungia diodą, o 9 nustato jį ryškiausiu. Galite naudoti ``for loop`` ciklus norėdami įjungti visus diodus iš eilės::

    from microbit import *

    display.clear()
    for x in range(0, 5):
    	for y in range(0, 5):
    	    display.set_pixel(x,y,9)  

``For loop`` leidžia atkartoti ciklą tam tikrą kiekį kartų, naudojant skaitiklį. Išorinis ciklas::

	for x in range(0,5)

įvykdys veiksmą penkis kartus, kiekvieną kartą nuosekliai pakeičiant ``x`` diapazone nuo ``0`` iki ``4``. Ciklas sustos prieš pasiekdamas paskutinę reikšmę diapazone.

Vidinis ciklas::

	for y in range(0,5):

atkartos veiksmą penkis kartus, kiekvieną kartąnuosekliai pakeičiant ``y`` diapazone nuo ``0`` iki ``4``. Ciklas sustos prieš pasiekdamas paskutinę reikšmę diapazone.

Paveiksliukų kūrmas
----------------------------
Turbūt norėsite sukurti ir atvaizduoti savo paveikslėlius „micro:bit“ ekrane.

Tai padaryti paprasta. Kiekvienam diodui gali būti suteikta viena iš dešimties reikšmių. Jeigu pikselis nustatytas ``0`` (nulis ), diodas yra išjungtas. Jeigu nustatytas pikselis lygus ``9`` (devyni), tuomet diodas švues ryškiausiai. Reikšmės nuo ``1`` iki ``8`` reprezentuoja ryškumo lygius tarp išjungta (``0``) ir ryškiausia (``9``).

Naudodamiesi šia informacija galime sukurti naujus paveiksliukus::

    from microbit import *

    boat = Image("05050:"
                 "05050:"
                 "05050:"
                 "99999:"
                 "09990")

    display.show(boat)

Neprivalote to rašyti per kelias eilutes. Ši sąlyga gali būti pateikta ir vienoje eilutėje:: 

    boat = Image("05050:05050:05050:99999:09990")

(Kai paleisite programą, įrenginys rodys senovinį burlaivį „Blue Peter“, kurio stiebai yra reguliuojami laivo korpuse.)

Ar pastebėjote, kad kiekviena fizinė ekrano eilutė atvaizduota skaičių eile pasibaigiančia ``:`` ir įterpta tarp ``"`` dvigubų kabučių? Kiekvienas skaičius nusako ryškumą. Yra penkios eilutės su penkiais skaičiais tad įmanoma individualiai nustatyti kiekvieno pikselio ryškumą kiekvienoje fizinio ekrano eilutėje.

Animacija
---------
Statiniai vaizdai yra įdomūs, bet dar smagiau yra priversti juos judėti. Tai irgi neįtikėtinai lengva padaryti su „micro:bit“, tiesiog naudokite vaizdų sąrašą!

Jau yra keletas integruotų sąrašų su paveiksliukais. Jie vadinasi ``Image.ALL_CLOCKS`` ir ``Image.ALL_ARROWS``::

    from microbit import *

    display.show(Image.ALL_CLOCKS, loop=True, delay=100)

Kai nurodome „micro:bit“ naudoti ``Image.ALL_CLOCKS``, kompiuteriukas atvaizduoja kiekvieną paveiksliuką sąraše, vieną po kito. ``loop=True`` reiškia, jog paveikslėliai bus atkartojami nuolatos ir be perstojo. Argumentas ``delay=100`` nurodo, kad laiko tarpas tarp kiekvieno paveikslėlio lygus 100 milisekundžių (viena dešimtoji sekundės).

Dabar pažiūrėkite kaip sukurti savo animaciją. Pirmiausia reikia sukurti paveikslėlių sąrašą. Pateiktame pavyzdyje sukurti šeši skirtingi valties paveikslėliai.

Štai valčių sąrašas::

    all_boats = [boat1, boat2, boat3, boat4, boat5, boat6]

Phyton programavimo kalboje sąraše galite laikyti be ką, net ir paveiksliukus. Šiame pavyzdyje, pamatysite kaip valtis paskęs paskutiniame paveiklėlyje. Tam įgyvedinti reikės šešių paveikslėlių pateiktų viename sąraše pavadinimu ``all_boats``::

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

Galiausiai galite nurodyti „micro:bit“ animuoti paveiksliukų sąrašą naudojant ``display.show``.

Projektai su LED ekranu
==========================
* Išbandykite keletą jau sukurtų paveiksliukų ir pažiūrėkite kaip jie atrodo.
* Sukurkite animaciją iš ``Image.ALL_ARROWS`` sąrašo. Kaip išvegti amžino ciklo (užuomina: ``True`` priešingybė yra ``False``)? Kaip pakeisti animacijos greitį?
* Sukurkite savo paveiksliuką. Pabandykite padaryti taip, kad jis iš lėto išnyktų ir vėl atsirastų.
* Sukurkite taškiuką LED ekrane. Priverskite jį šokinėti paspaudus mygtuką.
