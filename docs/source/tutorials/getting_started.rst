****************************
„Micro:bit“ - Įvadas 
****************************

„BBC micro:bit“ yra mažas kompiuteriukas su kuriuo galima kurti įvairiausius projektus nuo robotų iki muzikinių instrumentų - galimybės beribės.
Pasižiūrėkite į funkcijas, kurias galite naudoti savo projektuose.

 * 25 raudonos LED lemputės galinčios nušviesti žinutes.
 * Du programuojami mygtukai (A ir B) su kuriais galima pranešti „micro:bit“ kada pradėti ar užbaigti veiksmus.
 * Termometras temperatūrai matuoti.
 * Šviesos jutiklis matuojantis pokyčius šviesoje.
 * Akselerometras judesiams aptikti.
 * Magnetometras, kuris nusako kuria kryptimi judate.
 * Radijo ir „Bluetooth“ mažos energijos jungtis sąveikavimui su kitais įrenginiais.

.. image:: microbit-front-back.jpg
   :scale: 60%
   :align: center

Dabar sukursite savo pirmąją „micro:bit“ programą. Vėliau pateiksime keletą įdėjų, kuriomis galėsite pasinaudoti.

Pirmoji Programa
===================
„Micro:bit“ programavimas susideda iš 4 žingsnių. Galite nusiteikti pakartotį šį procesą daugybę kartų kol pavyks sukurti veikiančią programą.

.. image:: microbit_lifecycle.jpg
   :scale: 60%
   :align: center


Programinio kodo maketavimas
----------------------------

Pirmiausiai parašysite programą, kuri parodys žinutę "Hello UCL!" ir drugelio atvaizdą. Šiuo atveju tai nepareikalaus daug, tačiau padės suprasti kaip galėtų atrodyti planas:

.. image:: microbit_plan.jpg
   :scale: 70%
   :align: center

Kodo rašymas
--------------
Naudosime specialią teksto redagavimo programą savo kodo rašymui, kuri atrodys panašiai kaip žemiau esančiame paveiksliuke:

.. image:: getting_started.jpg
   :scale: 60%
   :align: center

Apžvelkime viską paeiliui::

	while True: 

Tai vadinama while ciklu. Veiksmas bus vykdomas kol ciklo sąlyga bus lygi rezultatui (true). While ciklas šiek tiek panašus į vaizdo klipą, kuris vis kartojasi iš naujo. ``True`` ir ``False`` turi specialią prasmę Phyton programavimo kalboje. ``True`` visada yra tiesa. Likusi programos dalis yra paprasta::

	from microbit import *

	while True:
    	    display.show('Hello UCL!')
            display.show(Image.BUTTERFLY)
	    print('Hi There!!!')    
    	    sleep(2000)

Ši sąlyga LED ekrane parodys užrašą ``Hello UCL`` ir iškart po jo - paveikslėlį.
Teiginys ``print('Hi There!!')``, atspausdins žinutę „REPL“ sąsajoje. Paspauskite mygtuką „REPL“ įrankių juostoje, jis atidarys „REPL“ langą:

.. image:: mu_repl_button.jpg
   :scale: 60%
   :align: center

„REPL“ langas yra skirtas „micro:bit“ žinučių atvaizdavimui ir komandų siuntimui tiesiai į „micro:bit“. Kol kas naudokite „REPL“ langą tik žinučių ir klaidų rodymui.

Kodėl mes prašome „micro:bit“ užmigti ``2000`` laikotarpiui? Ši vertė yra išreikšta milisekundėmis, „micro:bit“ užmigs tik 2 sekundėms. Tai suteiks pakankamai laiko pamatyti paveiksliuką prieš pradedant kartoti visą programą iš naujo.

Kodo įkėlimas
----------------
Paskutinis pasitikrinimas. Ar „micro:bit“ prijungtas prie kompiuterio? Taip? Tuomet spauskite „flash“ mygtuką:

.. image:: mu_flash.jpg
   :scale: 60%
   :align: center

Turėtumėte matyti žinutę ir paveiksliuką „micro:bit“ ekrane, o žinutė "Hello There!!" bus atspausdinta „REPL“ sąsajoje.

.. image:: mu_first_program_repl.jpg
   :scale: 60%
   :align: center


Atlikite pakeitimą 
---------------
Pakeiskite tekstą, kuris yra rodomas ekrane, ir padarykite taip, kad jis keliautų per LED ekraną. Galite tai padaryti pakeisdami žodį ``show`` į ``scroll``. Nepamirškite išsaugoti savo programos ir nusiųskite ``flash`` naują kodą į „micro:bit“.

.. image:: high_five.png
   :scale: 60%
   :align: center

Ką tik parašėte savo pirmąją progamą! Skaitykite toliau, nes su „micro:bit“ galite padaryti dar daugiau.
