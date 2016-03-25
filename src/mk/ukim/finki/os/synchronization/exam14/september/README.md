Tribe dinner
=====

Едно племе јаде заеднична вечера од голем казан во кој има ограничен број порции. Доколку има храна во казанот, секој член од племето сам се послужува и седнува на трпезата да јаде. Доколку казанот е празен, се повикува готвачот за да зготви нов казан со храна и сите кои не започнале да јадат **чекаат** додека готвачот не ги извести дека вечерата е готова. Притоа, трпезата има место за максимум четворица, што значи дека максимум четворица истовремено може да јадат. Доколку нема место на трпезата, членовите чекаат додека не се ослободи.


Вашата задача е да го синхронизирате претходното сценарио. 

Во почетниот код кој е даден, дефинирани се класите `TribeMember` и `Chef`, кои го симболизираат однесувањето на членовите на племето и готвачот, соодветно. Во имплементацијата, треба да ги користите следните методи од веќе дефинираната променлива `state`:

 - `state.isPotEmpty()`
    - Враќа `boolean` кој означува дали казанот е празен. 
    - Се повикува од сите членови на племето.
    - Доколку повеќе членови паралелно проверуваат, ќе добиете порака за грешка.
 - `state.fillPlate()`
    - Го симболизира земањето храна од казанот. 
    - Се повикува од сите членови на племето.
    - Доколку казанот е празен,  ќе добиете порака за грешка. 
    - Доколку повеќе членови паралелно земаат храна, ќе добиете порака за грешка.
 - `state.eat()`
    - Го симболизира јадењето на трпезата на членовите на племето. 
    - Се повикува од сите членови на племето.
    - Доколку повеќе од четворица паралелно јадат, ќе добиете порака за грешка. 
    - Доколку методот се извршува секвенцијално (само од еден член во еден момент), ќе добиете порака за грешка.
 - `state.cook()`
    - Го симболизира готвењето на храна во казанот од страна на готвачот. 
    - Се повикува само од готвачот.
    - Доколку методот се повика, а казанот не е празен, ќе добиете порака за грешка.

За решавање на задачата, преземете го проектот со клик на копчето `Starter file`, отпакувајте го и отворете го со Eclipse или Netbeans.

Претходно назначените методи служат за проверка на точноста на сценариото и не смеат да бидат променети и мораат да бидат повикани.  

Вашата задача е да го имплементирате методот `execute()` од класите `TribeMember` и `Chef`, кои се наоѓаат во датотеката `SeptemberTribeDinnerSynchronization.java`. При решавањето можете да користите семафори и монитори по ваша желба и нивната иницијализација треба да ја направите во `init()` методот.

При стартувањето на класата, сценариото ќе се повика 10 пати, со креирање на голем број инстанци од класата `TribeMember` и една инстанца од класата `Chef`. Кај сите `TribeMember` паралелно само еднаш ќе се повика нивниот `execute()` метод, додека пак `Chef.execute()` методот се повикува повеќе пати. 