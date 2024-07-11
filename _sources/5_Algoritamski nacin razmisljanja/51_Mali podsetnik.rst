Egy kis emlékeztető
===================

Karel izgatottan vár rád a labirintusában, és alig várja, hogy újra együtt játszatok és labdákat gyűjtsetek!

Mielőtt belevágnál az idei kalandba, emlékezz vissza arra, amit eddig tanultál az algoritmikus gondolkodásmódról!

.. quizq:: 

    .. mchoice:: p511
        :correct: a
        :answer_a: Igaz.
        :answer_b: Nem igaz.
        :feedback_a: A válasz helyes. Az algoritmus olyan lépések sorozata, amelyeket meghatározott sorrendben kell végrehajtani a probléma megoldásához.
        :feedback_b: A válasz nem helyes. Olvasd el újra figyelmesen, hogy mi az algoritmus! 

        Az algoritmus összeállításánál fontos a lépések sorrendje.

.. quizq::

	.. mchoice:: 512
		:answer_a: (5, 3)
		:answer_b: (1, 3)
		:answer_c: (5, 4)
		:answer_d: (4, 1)
		:correct: b
		:feedback_a: Nézd meg még egyszer a labirintust!
		:feedback_b: Bravó, a válasz helyes!
		:feedback_c: Nézd meg még egyszer a labirintust!
		:feedback_d: Ezen a mezőn Karel van, de hol van a labda?

		Melyik mezőn van a labda?
		
		.. image:: ../../_images/karel1.png
			:width: 180
			:align: right
			
 	
.. quizq:: 

    .. mchoice:: p513
        :correct: b
        :answer_a: feltételes ciklus
        :answer_b: számláló ciklus
        :answer_c: végtelen ciklus
        :feedback_a: A válasz nem helyes. A feltételes ciklusban az utasítások mindaddig végrehajtásra kerülnek, amíg a feltétel teljesül. Nem tudjuk előre, hogy hányszor.
        :feedback_b: A válasz helyes.
        :feedback_c: A válasz nem helyes. Gondolj csak bele, ha egy ciklus végtelen számú alkalommal ismétli önmagát, az egy jól megtervezett program?

        Amikor egy utasítást (vagy utasításcsoportot) többször kell végrehajtani, akkor a programban **ciklust** használunk. Ha pontosan tudjuk, hogy hányszor kell megismételni az utasítást, akkor a következő típusú ciklusról van szó:

.. quizq:: 

    .. mchoice:: p514
        :correct: c
        :answer_a: 6
        :answer_b: 3
        :answer_c: 5
        :feedback_a: Gondold át még egyszer!
        :feedback_b: Ellenőrizd le lépésről lépésre!
        :feedback_c: Szép volt, a válasz helyes!
		
        Karel labdákat gyűjt. Hányszor kell megismételni ezt az utasítássorozatot ahhoz, hogy Karel összegyűjtse az összes labdát, amely a labirintusban található?
		.. image:: ../../_images/karel2.png
			:width: 400
			:align: right

.. quizq:: 

    .. mchoice:: p515
        :correct: a
        :answer_a: Igaz vagy Hamis. 
        :answer_b: bármilyen számot.
        :answer_c: A és B betűket.
        :feedback_a: Szép volt, a válasz helyes.
        :feedback_b: A kérdés logikai műveletekre vonatkozik, gondold át újra!
        :feedback_c: A válasz nem helyes.

        Karel világában az összehasonlító műveletek a Logikai operátorok csoportjában találhatók. Ezekkel logikai kifejezéseket hozunk létre, amelyek eredményül a következő értékeket adhatják: 
		
.. quizq:: 

    .. mchoice:: p516
        :correct: c
        :answer_a: Ciklusok
        :answer_b: Elágazások
        :answer_c: Aritmetika
        :answer_d: Változók
        :feedback_a: A válasz nem helyes.
        :feedback_b: A válasz nem helyes.
        :feedback_c: Így van, a válasz helyes.
        :feedback_d: Karel használhat változókat is, de ebben az esetben ez nem kötelező.

		Amikor Karelnek ellenőriznie kell egy számítást, akkor ehhez a következő csoport blokkjait használja:
