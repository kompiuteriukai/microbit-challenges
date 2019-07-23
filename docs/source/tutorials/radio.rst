********
Radijas
********
„Micro:bit“ turi radijo lustą, kuris gali siųsti arba gauti žinutes.

.. image:: radio.jpg
   :scale: 80 %


Paprastos Funkcjijos
====================

Pasiruošimas 
-------------
Prieš pradedant naudotis radiju prisiminkite, kad reikia importuoti ``import`` radijo biblioteką ir radiją įjungti. Kai radijas įjungtas, jis girdės žinutes iš netoliese esančių kitų „micro:bit“::

	from microbit import *
	import radio		

	radio.on()			# Switch the radio on.

Kanalo numerio pasirinkimas
^^^^^^^^^^^^^^^^^^^^^^^^^^^
Jeigu norite dalintis žinutėmis su grupe įrenginių, tuomet kiekvienas „micro:bit“ grupėje turi būti sukonfiguruotas naudoti tą patį kanalo numerį. Kanalo numeris turi būti skaičius tarp ``0`` ir ``100``. Gali tai padaryti taip::

	radio.config(channel=19)	# Set the channel number to 19 

Kanalo numerį svarbu nustatyti jei kambaryje estae ne vienas. Kitu atveju, „micro:bit“ reaguos į visus netoliese esančius pranešimus.

Galios lygio nustatymas
^^^^^^^^^^^^^^^^^^^^^^^
Galiausiai, turite nustatyti radijo galios lygį. Pagal nutylėjimą, „micro:bit“ naudoja galios lygį 0, o tai reiškia, kad žinutės keliaus labai netoli. Galios reikšmė gali būti tarp ``0`` ir ``7``::

	radio.config(power=7)	# Set the power level to 7 

Žinučių siuntimas ir gavimas
-------------------------------
Dabar „micro:bit“ yra paruoštas siųsti ir gauti žinutes. Galite siųsti tekstinę eilutę, kuri yra neilgesnė kaip 250 simbolių. Žemiau pateikiamas pavyzdys::

	my_message = "Be nice to yu turkeys dis christmas, Cos' turkeys just wanna hav fun, Turkeys are cool, turkeys are wicked, An every turkey has a Mum."

	radio.send(my_message)

Žinutės gavimo procesas yra panašus, naudokite::

    message_received = radio.receive()

Sudėti viską kartu
-------------------
Jūsų „micro:bit“ yra išmanus, jis gali greitai siųsti ir gauti žinutes. Tiesiog nurodykite „micro:bit“ nuolatos jų klausyti arba jas siųsti štai taip::

	from microbit import * 
	import radio

	radio.on()
	radio.config(channel=19)	# Choose your own channel number
	radio.config(power=7)		# Turn the signal up to full strength 

	my_message = "Be nice to yu turkeys dis christmas, Cos' turkeys just wanna hav fun, Turkeys are cool, turkeys are wicked, An every turkey has a Mum."
	
	# Event loop.
	while True:
		radio.send(my_message) 
		incoming = radio.receive()
		if incoming is not None:
		    display.show(incoming)
		    print(incoming)
		sleep(500)

Jeigu spausdinsite ateinančias žinutes, kartais pamatysi užrašą ``None``. Tai yra todėl, kad „micro:bit“ klausosi žinučių, bet jos dar neatėjo. Galite ignoruoti šiuos įvykius tikrinant ar ateinančios ``incoming`` žinutės yra lygu ``None``.

Idėjos projektams su radiju
=================================
* Siųsti žinutę kiekvieną kartą kai mygtukas ``A`` yra paspaustas.
* Jums reikės dviejų „micro:bit“. Suprogramuokite vieną „micro:bit“ gauti žinutes ir jas atspausdinti naudojant ``print()`` metodą. Palikite šį „micro:bit“ prijungtą prie kompiuterio su „USB“ laidu. Suprogramuokite kitą „micro:bit“ siųsti akselerometro arba temperatūros rodmenis žinutėje kiekvieną sekundę. Atjunkite šį „micro:bit“ ir naudokite bateriją jam įjungti. Sveikinu! Sukūrėte duomenų gavėją ir siuntėją!
