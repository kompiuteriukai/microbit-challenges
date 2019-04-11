****************************
„Micro:bit“ - Įvadas 
****************************

„BBC micro:bit“ yra mažas kompiuteriukas su kuriuo galima kurti įvairiausius projektus nuo robotų iki muzikinių instrumentų - galimybės beribės.
Pasižiūrėkime į funkcijas, kurias gali naudoti savo kūrybos projektuose.

 * 25 raudonos LED lemputės galinčios nušviesti žinutes.
 * Du programuojami mygtukai (A ir B) su kuriais galima pranešti „micro:bit“ kada pradėti ar užbaigti veiksmus.
 * Termometrą temperatūrai matuoti.
 * Šviesos jutiklį matuojantį pokyčius šviesoje.
 * Akselerometrą judesiams aptikti.
 * Magnetometrą kuris nusako į kurią kryptį judi.
 * Radijo ir „Bluetooth“ mažos energijos jungtis sąveikavimui su kitais įrenginiais.

.. image:: microbit-front-back.jpg
   :scale: 60%
   :align: center

O dabar sukursi savo pirmąją „micro:bit“ programą ir vėliau pateiksime keletą įdėjų kuriomis gali pasinaudoti arba ne, čia jau tau spęsti.

Tavo Pirmoji Programa
===================
„Micro:bit“ programavimas susideda iš 4 žingsnių. Gali nusiteikti pakartotį šį procesą daugybę kartų kol pavyks sukurti veikiančią programą.

.. image:: microbit_lifecycle.jpg
   :scale: 60%
   :align: center


Programinio kodo maketavimas
----------------------------

Pirmiausiai parašysi programą kuri parodys žinutę "Hello UCL!" ir drugelio atvaizdą. Šiuo atveju tai nepareikalaus daug laiko skirti maketuojant programą, bet padės suprasti kaip galėtų atrodyti planas:

.. image:: microbit_plan.jpg
   :scale: 70%
   :align: center

Kodo rašymas
--------------
Naudosime specialią teksto redagavimo programą savo kodo rašymui, kuri atrodys panašiai kaip padotyta paveiksliuke:

.. image:: getting_started.jpg
   :scale: 60%
   :align: center

Apžvelkime viską paeiliui::

	while True: 

Tai reiškia daryti kažką (kas seka šį teiginį ir yra įtraukta) amžinai ir visą laiką. Tai vadinama kilpa, tai šiek tiek panašu į vaizdo klipą, kuris vis kartojasi iš naujo. ``True`` ir ``False`` turi specialią prasmę „python“ programavimo kalboje. ``True`` visada yra tiesa, kitaip tariant ``True``. Likusi programos dalis yra paprasta::

	from microbit import *

	while True:
    	    display.show('Hello UCL!')
            display.show(Image.BUTTERFLY)
	    print('Hi There!!!')    
    	    sleep(2000)

Tai parodys užrašą ``Hello UCL`` LED ekrane, kuriame bus rodoma po vieną simbolį išeilės ir po to parodys drugelį.
Teiginys ``print('Hi There!!')``, atspausdins žinutę „REPL“ sąsajoje. Paspausk mygtuką „REPL“ įrankių juostoje, jis atidarys „REPL“ langą:

.. image:: mu_repl_button.jpg
   :scale: 60%
   :align: center

„REPL“ langas parodys mums žinutę iš „micro:bit“ ir dar jis leidžia mums siūsti komandas tiesiai į „micro:bit“. Kolkas mes naudosime „REPL“ langą žinučių ir klaidų rodymui.

Gali būti įdomu kodėl mes prašome „micro:bit“ užmigti šiam ``2000`` laikotarpiui! Ši vertė yra išreikšta milisekundėmis, todėl mes paprašėme užmigti tik 2 sekundėms. Tai suteiks mums pakankamai laiko pamatyti paveiksliuką prieš pradedant kartoti visą programą iš naujo.

Kodo įkėlimas
----------------
Paskutinis pasitikrinimas. Ar „micro:bit“ prijungtas prie kompiuterio? Taip? Tuomet spausk „flash“ mygtuką:

.. image:: mu_flash.jpg
   :scale: 60%
   :align: center

Turėtum matyti žinutę ir paveiksliuką „micro:bit“ ekrane ir žinutė "Hello There!!" bus atspausdinta „REPL“ sąsajoje.

.. image:: mu_first_program_repl.jpg
   :scale: 60%
   :align: center


Atlik pakeitimą 
---------------
Pakeisk tekstą kuris yra rodomas ekrane ir padaryk taip, kad jis keliautų per LED ekraną. Gali tai padaryti pakeisdamas žodį ``show`` į ``scroll``. Nepamiršk išsaugoti savo programos ir nusiūsk ``flash`` naują kodą į „micro:bit“.

.. image:: high_five.png
   :scale: 60%
   :align: center

Tu parašiai savo pirmąją programą. Skaityk toliau ir pamatyk ką dar gali padaryti su „micro:bit“.
