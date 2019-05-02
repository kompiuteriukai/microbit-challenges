****************
Muzika
****************
Tai yra trumpas gidas, skirtas papasakoti dar keliems dalykams ką galima padaryti su „micro:bit“ muzika. Idėja ta, kad gali naudoti šią informaciją eksmperimentams ir kuriant kažką sau. „Micro:bit“ gali groti paprastas melodijas, jeigu prijungsi garsekalbį.

Jeigu naudoji garsekalbį, gali jį prijungti prie „micro:bit“ naudojant krokodilinius segtukus štai taip:

.. figure:: connect_speaker.jpg
   :scale: 150 %

   Paveiksliukas iš: <https://www.kitronik.co.uk/blog/microbit-alarm-kitronik-university/>

.. warning:: Negali valdyti garso lygio apimties iš „micro:bit“. Būk labai atsargus, jei naudosi ausines. Garsiakalbis yra geresnis pasirinkimas darbui su garsu.

Jeigu naudosi ausines, gali jas prijungti krokodiliniais segtukais prie „micro:bit“ taip:

.. image:: connect_headphones.jpg
   :scale: 70 %

Paprastos funkcijos
===================

Groti melodiją
--------------
Taigi pagrokime ką nors::

	from microbit import *
	import music

	music.play(music.NYAN)

.. note:: Privalai importuoti modulį ``music`` norėdamas groti ar kontroliuoti garsą.

„Micro:bit“ turi daug integruotų melodijų. Štai keletas iš jų, išbandyk: 

 *  ``music.DADADADUM``
 *  ``music.ENTERTAINER``
 *  ``music.PRELUDE``
 *  ``music.ODE``
 *  ``music.NYAN``
 * ``music.RINGTONE``
 
 
Sukurk savo melodiją
--------------------
Gali sukurti savo melodiją, žemiau pateikiama kodo iškarpa rodanti kaip groti garsą. Numeris einantis po natos yra oktava, o oktava gali būti bet koks skaičius nuo 1 iki 8. Skaičius po dvitaškio pasako kaip ilgai nata bus grojama::

	from microbit import *
	import music

	# Play a 'C'
	music.play('C')

	# Play a 'C' for 4 beats long
	music.play('C:4')

	# Play a 'C' in octave number 3 for 4 beats long
 	music.play('C3:4')

Groti eilę natų vieną po kitos yra paprasta, sudėk natas, kurias nori groti į sąrašą::

	from microbit import *
	import music

	# Tune: Frere Jacques
	tune = ["C4:4", "D4:4", "E4:4", "C4:4", "C4:4", "D4:4", "E4:4", "C4:4",
        	"E4:4", "F4:4", "G4:8", "E4:4", "F4:4", "G4:8"]
	music.play(tune)
	

Išplėstinės funkcijos
=====================
Taip pat galite nustatyti natos dažnį ``frequency``. Pažiūrėk į šį pavyzdį, kur sukuriame policijos sirenas. Protingas pasirinkimas čia yra tai, kad dažnis ar nata kontroliuojama ``for`` kilpos::

	while True:
		for freq in range(880, 1760, 16):
		        music.pitch(freq, 6)
		for freq in range(1760, 880, -16):
			music.pitch(freq, 6)

Ar gali atspėti ką tai daro? Kiek vieną kartą kilpoje apskaičiuojamas naujas dažnis pridedant (arba atimant) 16.

Idėjos projektams su muzika 
==============================
* Sukurk savo melodiją.
* Sukurk muzikinį instrumentą. Pakeisk melodijos skambesį pasinaudojant akselerometro gautais duomenimis. 
