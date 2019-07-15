***************
Termometras
***************
.. py:module:: microbit

Termometras „micro:bit” kompiuteriuke yra integruotas viename iš lustų. Lustai įšyla įjungus kompiuteriuką, todėl kambario temperatūra matuojama nevisiškai tiksliai. Lusta,s matuojantis temperatūrą, gali būti surastas galinėje kairėje „micro:bit” kompiuteriuko pusėje:

.. image:: thermometer.jpg
   :scale: 80 %


Paprastos funkcijos
===================
Termometras turi vieną paprastą funkciją - gauti temperatūros rodmenis sveikojo skaičiaus pavidalu Celsijaus formate::

   from microbit import *
   
   while True:
      temp = temperature()
      display.scroll(str(temp) + 'C')
      sleep(500)

Sukompiliuokite, paleiskite programą ir pažiūrėkite kas bus.

Pamatysite, kad temperatūra, kurią matuoja termometras, dažniausiai bus aukštesnė negu tikra kambario temperatūra, nes termometras yra šildomas tiek kambario, tiek elektronikos.
Jeigu žinote, kad temperatūra yra 27°C ir „micro:bit” nuolat rodo 3 laipsniais aukštesnę temperatūrą, galite tai pakoreguoti. Norėdami tai padaryti tiksliai, turite sužinoti tikrąją temperatūrą nenaudojant „micro:bit”. Galite sugalvoti kaip tai padaryti?

Idėjos projektams su termometru
=================================
* Pabandykite sukalibruoti termometrą. Ar jis vis dar rodo tikslią temperatūrą kai perkeliate į šiltesnę ar šaltesnę vietą?
* Padarykite taip, kad LED lemputės pakeistų šabloną pasikeitus temperatūrai.
* Patikrinkite kaip pasikeičia kambario temperatūra atidarius langą - kaip manote ką tai pasako apie šildymo energijos švaistymą?
