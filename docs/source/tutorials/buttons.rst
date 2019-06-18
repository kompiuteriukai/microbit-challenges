***********
Mygtukai 
***********

.. py:module:: microbit.button

„Micro:bit“ turi du mygtukus: jie yra pažymėti ``A`` ir ``B`` raidėmis.

.. image:: microbit_button.jpg
   :scale: 50 %

Galite naudoti mygtukus įvesties duomenims iš vartotojo gauti. Galbūt norėtumėte pradėti arba sustabdyti savo programą
mygtuko paspaudimu arba norėtumėte žinoti kiek kartų mygtukas buvo paspaustas.

Paprastos funkcijos
===================

Patikrinti ar mygtukas buvo paspaustas
--------------------------------------

Kartais mes norime, kad programa palauktų kol kas nors nutiks, pavyzdžiui: norėtume, kad „micro:bit“ palauktų iki kol
mygtukas ``A`` yra paspautas ir tik tada atspausdintų žinutę. Galime tai padaryti taip:

	from microbit import *

        while True:
            if button_a.is_pressed():
                display.scroll("A")

Pasiaiškinkime tai dalimis. Pirma eilutė:

	while True:

Tai yra standartinis būdas „micro:bit“ kompiuteriukui pasakyti, kad kol reikšmė yra teigiama, jis turi vykdyti programą amžinai. Sekanti eilutę atrodo kaip įprastas anglų kalbos tekstas:

        while True:
            if button_a.is_pressed():
                display.scroll("A")

Tai reiškia: jeigu mygtukas ``A`` yra paspaustas tuomet rodyti ``A`` raidę LED ekrane.

Žinoma, dažniausiai mes norime atlikti sudėtingesnius veiksmus. Tarkime, norime palyginti du įvykius. Tam galime
naudoti ``if`` ir ``else`` štai taip:

        while True:
            if button_a.is_pressed():
                display.scroll("A")
	    else:
		display.scroll(Image.ASLEEP)

Tai reiškia: jeigu yra paspaustas mygtukas ``A`` - LED ekrane rodyti raidę ``A``, kitu atveju - rodyti ``Image.ASLEEP``.

Skaičiuoti procesų skaičių
------------------------------
Kartais gali prireikti suskaičiuoti kiek kartų mygtukas buvo paspaustas per tam tikrą laiką. Galite tai padaryti
pasinaudojant ``get_presses()`` metodu. Štai pavyzdys::

    from microbit import *

        while True:
	    sleep(3000)
            count = button_a.get_presses()
            display.scroll(str(count))

„Micro:bit“ užmigs 3 sekundėms, po to pabus ir patikrins kiek kartų buvo paspaustas mygtukas ``A``. Paspaudimų skaičius bus išsaugotas kintamąjame kuris vadinasi ``count``. Mes negalime tiesiogiai atvaizduoti skaičiaus LED ekrane, todėl konvertuojame kintamajį ``count`` į eilutę ir tik tada atvaizduojame ekrane. Ar galite sugalvoti kitą būdą kaip tai padaryti? (Užuomina: patikrinkite ar mygtukas buvo paspaustas ir pridėkite 1 prie kintamojo jeigu tai buvo padaryta).

Išplėstinės funkcijos
======================

Patikrinti abu mygtukus
-------------------------
Yra įmanoma patikrinti ir daugiau įvykių pasinaudojant ``if``, ``elif`` ir ``else``. Tarkime, norėtumėte patikrinti, kuris mygtukas buvo paspaustas - ``A``, ``B`` ar abu vienu metu. Galite tai padaryti šitaip:

	from microbit import *

	while True:
	    if button_a.is_pressed() and button_b.is_pressed():
	        display.scroll("AB")
	        break
	    elif button_a.is_pressed():
	        display.scroll("A")
	    elif button_b.is_pressed():
	        display.scroll("B")
	    sleep(100)

.. pastaba:: Raktažodis ``elif`` reiškia tą patį ką ir ``else if``. Jeigu norite, galite naudoti ir pilną variantą ``else if``.

Viršuje parašyta programa parodo raides pagal mygtuko paspaudimą. Jeigu abu mygtukai yra paspaudžiami vienu metu, ekrane bus rodoma ``AB``.

Ar mygtukas buvo paspaustas?
----------------------------
Problema naudojant ``is_pressed()`` yra tai, kad nepaspaudus mygtuko tiksliu momentu, programa neaptiks ar mygtukas buvo paspaustas ar ne.

Funkcija ``was_pressed()`` yra naudinga, kai norite parašyti programą, kuri
retkarčiais patikrina ar mygtukas buvo paspaustas ir ar toliau vykdo kitus nurodymus.
Kol programa vykdo kitus nurodymus, gali atsitikti taip, kad vartotojas paspaudžia
mygtuką ir jį atleidžia, bet programa tuo metu to nepatikrina ir nepamato.
Sekanti funkcija pasakys ar mygtukas buvo paspaustas ir atleistas nuo
paskutinio karto, kai ta funkcija buvo įvykdyta, kol programa vykdė kitus nurodymus.
Tokiu atveju niekada nepraleisite mygtuko paspaudimo::

	from microbit import *

	while True:
	    if button_a.was_pressed(): 
	        display.scroll("A")
	    else:
		display.scroll(Image.ASLEEP)
	    sleep(1000)

Paspaudus mygtuką trumpam pamatysite raidę ``A`` ir tada bus rodoma ``Image.ASLEEP``.
Jeigu paspausite mygtuką kol programa miega, raidė ``A`` iškart nepasirodys. Ji pasirodys kai funcija sekantį kartą patikrins ar mygtukas buvo paspaustas.
Tai galite pamatyti aiškiau, jeigu nustatysite ilgesnį miego laiką.

Pabandykte panaudoti funkciją ``button_a.isPressed()`` vietoj funkcijos ``button_a.was_pressed()``.
Tokiu atveju, kai programa miegojo, ji niekada nesupras, kad mygtukas buvo paspaustas.
 
Keletas idėjų projektams su mygtukais
======================================
* Pakeiskite kas yra rodoma paspaudus mygtuką
* Žaidimai reikalaujantys vartotojo komandų... gal galite sugalvoti vieną?
