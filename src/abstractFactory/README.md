# Abstract factory pattern #
The abstract factory pattern is a way to specify how several factories are defined by their API.
Basically it allows to create hierarchies of objects linked by the same interfaces.

## UML ##
                          +-----------"I"-------------+                                                                   +----"I"----+
                          |        Restaurant         |                                                                   |  SideDish |
                          +---------------------------+                                                                   +-----------+
                          | +cookMainDish(): MainDish |-----------------------+------------------------------------------>| +eat()    |
                          | +cookSideDish(): SideDish |                       |                                           +-----^-----+
                          +------------^--------------+                       |                                                /_\
                                      /_\                                     |                                                 :
                                       :                                      |       +----"I"----+                             :
                                       :                                      |       |  MainDish |                   +.........+.........+
                                       :                                      |       +-----------+                   :                   :
                     +.................+.................+                    +------>| +eat()    |               +---+-----+       +-----+-----+
                     :                                   :                            +-----^-----+               | Lettuce |       | FrenchFry |
                     :                                   :                                 /_\                    +---------+       +-----------+
        +------------+-------------+      +--------------+-------------+                    :                     | +eat()  |       | +eat()    |
        |         Pizzeria         |      |          FastFood          |                    :                     +---------+       +------+----+
        +--------------------------+      +----------------------------+            +.......+.......+                  ^                   ^
        | +cookMainDish(): Pizza   |      | +cookMainDish(): Burger    |            :               :                  |                   |
        | +cookSideDish(): Lettuce |      | +cookSideDish(): FrenchFry |        +---+----+     +----+---+              |                   |
        +------------+-------------+      +--------------+-------------+        | Pizza  |     | Burger |              |                   |
                     |                                   |                      +--------+     +--------+              |                   |
                     |                                   |                      | +eat() |     | +eat() |              |                   |
                     |                                   |                      +---+----+     +----+---+              |                   |
                     |                                   |                          ^               ^                  |                   |
                     |                                   |                          |               |                  |                   |
                     |                                   |                          |               |                  |                   |
                     |                                   |                          |               |                  |                   |
                     +--------------------------------------------------------------+----------------------------------+                   |
                                                         |                                          |                                      |
                                                         +------------------------------------------+--------------------------------------+
