****************
Muzika
****************
Tai yra trumpas gidas, skirtas parodyti ką galima padaryti su „micro:bit“ muzika. Galite naudoti šią informaciją eksmperimentams ir kuriant kažką naujo. „Micro:bit“ gali groti paprastas melodijas, jeigu prijungsi garsiakalbį.

Jeigu naudojate garsiakalbį, galite jį prijungti prie „micro:bit“ naudodami krokodilinius segtukus štai taip:

.. figure:: connect_speaker.jpg
   :scale: 150 %

   Paveiksliukas iš: <https://www.kitronik.co.uk/blog/microbit-alarm-kitronik-university/>

.. warning:: Negalite valdyti garso lygio apimties iš „micro:bit“. Būkite labai atsargus, jeigu naudosite ausines. Garsiakalbis yra geresnis pasirinkimas darbui su garsu.

Vis dėlto, jeigu naudosite ausines, galite jas prijungti krokodiliniais segtukais prie „micro:bit“ taip:

.. image:: connect_headphones.jpg
   :scale: 70 %

Paprastos funkcijos
===================

Groti melodiją
--------------
Ikelkite muziką į „micro:bit“::

	from microbit import *
	import music

	music.play(music.NYAN)

.. note:: Privalai importuoti modulį ``music`` norėdamas groti ar kontroliuoti garsą.

„Micro:bit“ turi daug integruotų melodijų. Štai keletas iš jų: 

 *  ``music.DADADADUM``
 *  ``music.ENTERTAINER``
 *  ``music.PRELUDE``
 *  ``music.ODE``
 *  ``music.NYAN``
 * ``music.RINGTONE``
 
 
Sukurkite savo melodiją
--------------------
Galite sukurti savo melodiją naudodamiesi Žemiau pateikiama kodo iškarpa, rodančia kaip groti garsą. Numeris einantis po natos yra oktava, o oktava gali būti bet koks skaičius nuo 1 iki 8. Skaičius po dvitaškio nusako kaip ilgai nata bus grojama::

	from microbit import *
	import music

	# Play a 'C'
	music.play('C')

	# Play a 'C' for 4 beats long
	music.play('C:4')

	# Play a 'C' in octave number 3 for 4 beats long
 	music.play('C3:4')

Groti eilę natų vieną po kitos yra paprasta: sudėkite natas, kurias norite groti, į sąrašą::

	from microbit import *
	import music

	# Tune: Frere Jacques
	tune = ["C4:4", "D4:4", "E4:4", "C4:4", "C4:4", "D4:4", "E4:4", "C4:4",
        	"E4:4", "F4:4", "G4:8", "E4:4", "F4:4", "G4:8"]
	music.play(tune)
	

Išplėstinės funkcijos
=====================
Taip pat galite nustatyti natos dažnį ``frequency``. Pažiūrėkite į šį pavyzdį, kuriame sukuriamos policijos sirenas. Dažnis ar nata kontroliuojama ``for`` ciklu::

	while True:
		for freq in range(880, 1760, 16):
		        music.pitch(freq, 6)
		for freq in range(1760, 880, -16):
			music.pitch(freq, 6)

Ar galite atspėti ką šis kodas daro? Kiekvieną kartą cikle apskaičiuojamas naujas dažnis pridedant (arba atimant) 16.

Idėjos projektams su muzika 
==============================
* Sukurkite savo melodiją.
* Sukurkite muzikinį instrumentą. Pakeiskite melodijos skambesį pasunaudodami akselerometro gautais duomenimis. 
