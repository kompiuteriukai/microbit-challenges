***********
Mygtukai 
***********

.. py:module:: microbit.button

„Micro:bit“ turi du mygtukus: jie yra pažymėti ``A`` ir ``B`` raidėmis.

.. image:: microbit_button.jpg
   :scale: 50 %

Gali naudoti mygtukus įvesties duomenims iš vartotojo gauti. Galbūt norėtum pradėti arba sustabdyti savo programą
mygtuko paspaudimu arba norėtum žinoti kiek kartų mygtukas buvo paspaustas.

Paprastos funkcijos
===================

Patikrinti ar mygtukas buvo paspaustas
--------------------------------------

Kartais mes norime, kad programa palauktų kol, kas nors nutiks, pavyzdžiui: norėtume, kad „micro:bit“ palauktų iki kol
mygtukas ``A`` yra paspautas ir tada atspausdintų žinutę. Galime tai padaryti taip::

	from microbit import *

        while True:
            if button_a.is_pressed():
                display.scroll("A")

Pasiaiškinkime tai dalimis. Pirma eilutė::

	while True:

Tai yra standartinis būdas „micro:bit“ kompiuteriukui pasakyti, kad kol reikšmė yra teigiama, vykdyti programą amžinai.
Sekanti eilutę atrodo kaip normalus anglų kalbos tekstas::

        while True:
            if button_a.is_pressed():
                display.scroll("A")

Tai reiškia, jeigu mygtukas ``A`` yra paspaustas tuomet rodyti ``A`` raidę LED ekrane.

Žinoma, dažniausiai mes norime atlikti sudėtingesnius veiksmus. Yra būdas kaip patikrinti du dalykus, mes galime
naudoti ``if`` ir ``else`` štai taip::

        while True:
            if button_a.is_pressed():
                display.scroll("A")
	    else:
		display.scroll(Image.ASLEEP)

Tai reiškia, jeigu mygtukas ``A`` yra paspaustas rodyti raidę ``A`` LED ekrane, kitu atvėju, rodyti ``Image.ASLEEP``.

Skaičiuoti procesų skaičių
------------------------------
Kartais gali prireikti suskaičiuoti kiek kartų mygtukas buvo paspaustas per tam tikrą laiką. Gali tai padaryti
pasinaudojant ``get_presses()`` metodu. Štai pavyzdys::

    from microbit import *

        while True:
	    sleep(3000)
            count = button_a.get_presses()
            display.scroll(str(count))

„Micro:bit“ užmigs 3 sekundėms, po to pabus ir patikrins kiek kartų buvo paspaustas mygtukas ``A``. Paspaudimų skaičius bus išsaugotas kintamąjame kuris vadinasi ``count``. Mes negalime tiesiogiai atvaizduoti skaičiaus LED ekrane, todėl konvertuojame kintamajį ``count`` į eilutę ir tada atvaizduojame ekrane. Ar gali sugalvoti kitą būdą kaip tai padaryti? (Užuomena: patikrink ar mygtukas buvo paspaustas ir pridėk 1 prie kintamojo jeigu tai buvo padaryta).

Išplėstinės funkcijos
======================

Patikrinti abu mygtukus
-------------------------
Yra įmanoma patikrinti ir daugiau įvykių pasinaudojant ``if``, ``elif`` ir ``else``. Tarkim norėtum patikrinti kuris mygtukas buvo paspaustas ``A``, ``B`` ar abu vienu metu. Galime tai padaryti šitaip::

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

.. pastaba:: Raktažodis ``elif`` reiškia tą patį ką ir ``else if``. Gali naudoti ir pilną variantą ``else if`` jeigu nori.

Programa parašyta viršuje parodo raides pagal mygtuko paspaudimą. Jeigu abu mygtukai yra paspaudžiami vienu metu tai ekrane bus rodoma ``AB``.

Ar mygtukas buvo paspaustas?
----------------------------
Problema naudojant ``is_pressed()`` yra tai, kad jeigu nepaspausi mygtuko tam tikru tiksliu momentu, tai programa neaptiks
ar mygtukas kadanors buvo paspaustas ar ne.

Funkcija ``was_pressed()`` yra naudinga kai nori parašyti programą kuri
retkarčiais patikrina ar mygtukas buvo paspaustas ir toliau vykdo kitus nurodymus.
Kol programa vykdo kitus nurodymus gali atsitikti taip, kad vartotojas paspaudžia
mygtuką ir jį atleidžia, bet programa tuo metu nepatikrina ir to nepamato.
Sekanti funkcija pasakys ar mygtukas buvo paspaustas ir atleistas nuo
paskutinio karto kai ta funkcija buvo įvykdyta kol programa darė kažką kitą.
Tokiu atvėju niekada nepraleisi mygtuko paspaudimo::

	from microbit import *

	while True:
	    if button_a.was_pressed(): 
	        display.scroll("A")
	    else:
		display.scroll(Image.ASLEEP)
	    sleep(1000)

Paspaudus mygtuką trumpam pamatysi raidę ``A`` ir tada bus rodoma ``Image.ASLEEP``.
Jeigu paspausi mygtuką kol programa miega, tai raidė ``A`` iškart nepasirodys,
bet ji pasirodys kai funcija sekantį kartą patikrins ar mygtukas buvo paspaustas.
Tai gali pamatyti aiškiau jeigu nustatysi ilgesnį miego laiką.

Dabar pabandyk panaudoti funkciją ``button_a.isPressed()`` vietoj ``button_a.was_pressed()``.
Tokiu atvėju jeigu programa tuo metu miegojo ji niekada nesupras, kad mygtukas buvo paspaustas.
 
Keletas idėjų projektams su mygtukais
======================================
* Pakeisk kas yra rodoma paspaudus mygtuką
* Žaidimai reikalaujantys vartotojo komandų... gal gali sugalvoti vieną?
