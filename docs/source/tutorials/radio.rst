********
Radijas
********
„Micro:bit“ turi radijo lustą, kuris gali siūsti arba gauti žinutes.

.. image:: radio.jpg
   :scale: 80 %


Paprastos Funkcjijos
====================

Pasiruošimas 
-------------
Prieš pradedant naudotis radiju prisimink, kad reikia importuoti ``import`` radijo biblioteką ir jį įjungti. Kai radijas įjungtas jis girdės žinutes iš netoliese esančių kitų „micro:bit“::

	from microbit import *
	import radio		

	radio.on()			# Switch the radio on.

Kanalo numerio pasirinkimas
^^^^^^^^^^^^^^^^^^^^^^^^^^^
Jeigu nori dalintis žinutėmis su grupe įrenginių tuomet kiekvienas „micro:bit“ grupėje turi būti sukonfiguruotas nautoti tą patį kanalo numerį. Kanalo numeris turi būti skaičius tarp ``0`` ir ``100``. Gali tai padaryti taip::

	radio.config(channel=19)	# Set the channel number to 19 

Svarbu tai padaryti, jei esi kambaryje su kitais žmonėmis, ir naudoji savo „micro:bit“, nes kitaip „micro:bit“ išgirs visus netoliese esančius pranešimus ir tai nėra tai, ko nori.

Galios lygio nustatymas
^^^^^^^^^^^^^^^^^^^^^^^
Galiausiai, turi nustatyti radijo galios lygį, pagal nutylėjimą, „micro:bit“ naudoja galios lygį 0, o tai reiškia, kad žinutės keliaus labai netoli. Galios reikšmė gali būti tarp ``0`` ir ``7``::

	radio.config(power=7)	# Set the power level to 7 

Žinučių siūntimas ir gavimas
-------------------------------
Dabar esi pasiruošęs siūsti ir gauti žinutes. Gali siūsti tekstinę eilutę kuri yra neilgesnė kaip 250 simbolių. Žemiau pateikiamas pavyzdys::

	my_message = "Be nice to yu turkeys dis christmas, Cos' turkeys just wanna hav fun, Turkeys are cool, turkeys are wicked, An every turkey has a Mum."

	radio.send(my_message)

Žinutės gavimo procesas yra panašus, naudok::

    message_received = radio.receive()

Sudėti viską kartu
-------------------
Tavo „micro:bit“ yra protingas, jis gali siūsti ir gauti žinutes greitai. Tiesiog nurodyk „micro:bit“ pastoviai jų klausyti arba jas siūsti štai taip::

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

Jeigu spausdinsi ateinančias žinutes, kartais pamatysi užrašą ``None``. Tai yra todėl, kad „micro:bit“ klausosi žinučių bet jos dar neatėjo. Mes galime ignoruoti šiuos įvykius tikrinant ar ateinančios ``incoming`` žinutės yra lygu ``None``.

Idėjos projektams su radiju
=================================
* Siūsti žinutę kiek vieną kartą kai mygtukas ``A`` yra paspaustas.
* Tau reikės poros „micro:bit“. Suprogramuok vieną „micro:bit“ gauti žinutes ir jas atspausdinti naudojant ``print()`` metodą. Palik šį „micro:bit“ prijungtą prie kompiuterio su „USB“ laidu. Suprogramuok kitą „micro:bit“ siūsti akselerometro arba temperatūros rodmenis žinutėje kiek vieną sekundę. Atjunk šį „micro:bit“ ir naudok bateriją jam įjungti. Sveikinu! Sukūriai duomenų gavėją ir siuntėją!
