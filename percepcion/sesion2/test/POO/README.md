## POO en python


* **Curso**: https://docs.microsoft.com/en-us/learn/modules/python-object-oriented-programming/
* **Codigo**: El codigo del curso esta en https://github.com/MicrosoftDocs/mslearn-python-oo


## Descripción del problema

"Piedra, papel, tijeras" es un juego con dos participantes. El juego consta de rondas. En cada ronda, un participante elige un símbolo entre piedra, papel o tijeras, y el otro participante hace lo mismo. Después, para determinar el ganador de la ronda, se comparan los símbolos elegidos. Las reglas del juego determinan que la piedra gana a las tijeras, las tijeras ganan al papel (lo cortan) y el papel gana a la piedra (la envuelve). Al ganador de la ronda se le concede un punto. El juego continúa durante tantas rondas como los participantes acuerden. El ganador es el participante con más puntos.


## Modelado del problema

1. Resaltar las palabras clave importantes puede aplicarles negrita o cursiva.

   "Piedra, papel, tijeras" es un **juego** con dos **participantes**. El juego consta de **rondas**. En cada ronda, un participante elige un **símbolo** entre **piedra**, **papel** o **tijeras**, y el otro participante hace lo mismo. Después, para determinar el **ganador** de la ronda, se **comparan** los símbolos elegidos. Las **reglas** del juego determinan que la piedra gana a las tijeras, las tijeras ganan al papel (lo cortan) y el papel gana a la piedra (la envuelve). Al ganador de la ronda se le concede un **punto**. El juego continúa durante tantas rondas como los participantes acuerden. El ganador es el participante con más puntos.

2. Crear una tabla con las columnas ```Phase```, ```Actor```, ```Behavior``` y ```Data```. Organice las palabras resaltadas en las posiciones que crea que deben ocupar.

|Fase |	Actor |	Comportamiento | data|
|---|---|---|---|
|Entrada |	Participante |	Elige el símbolo | Símbolo guardado como *opción* en Participant(choice) |
|Processing	| GameRound | Compara las opciones con las reglas del juego   |  *Resultado* inspeccionado |
|Processing	|GameRound	|Se conceden puntos según el valor del resultado |Se agregan puntos al objeto Participant(point) ganador|
|Processing	| Juego	| Se comprueba la respuesta para continuar |	Si la respuesta es true, se continúa; de lo contrario, se sale |
| Output |Juego	| Nueva ronda del juego o crédito final del juego||

## Creación de clases y estado

```python
class Participant:
    def __init__(self):
        self.points = 0
        self.choice = ""

class GameRound:

class Game:
    def __init__(self):
        self.endGame = False
        self.participant = Participant()
        self.secondParticipant = Participant()
```

## Implementación del comportamiento

|Fase |	Actor |	Comportamiento | data|
|---|---|---|---|
|Entrada |	Participante |	Elige el símbolo | Símbolo guardado como *opción* en Participant(choice) |
|Processing	| GameRound | Compara las opciones con las reglas del juego   |  *Resultado* inspeccionado |
|Processing	|GameRound	|Se conceden puntos según el valor del resultado |Se agregan puntos al objeto Participant(point) ganador|
|Processing	| Juego	| Se comprueba la respuesta para continuar |	Si la respuesta es true, se continúa; de lo contrario, se sale |
| Output |Juego	| Nueva ronda del juego o crédito final del juego||

Esta vez se centrará en la columna **Comportamiento** y la rellenará con métodos que se agregarán a las clases. Además, agregará código a esos métodos para que funcionen de la manera prevista.


```python
class Participant:
    def __init__(self, name):
        self.name = name
        self.points = 0
        self.choice = ""
    def choose(self):
        self.choice = input("{name}, select rock, paper or scissor: ".format(name= self.name))
        print("{name} selects {choice}".format(name=self.name, choice = self.choice))

class GameRound:
    def __init__(self, p1, p2):
        p1.choose()
        p2.choose()
    def compareChoices(self):
        print("implement")
    def awardPoints(self):
        print("implement")

class Game:
    def __init__(self):
        self.endGame = False
        self.participant = Participant("Spock")
        self.secondParticipant = Participant("Kirk")
    def start(self):
        game_round = GameRound(self.participant, self.secondParticipant)

    def checkEndCondition(self):
        print("implement")
    def determineWinner(self):
        print("implement")

game = Game()
game.start()
```

Ha agregado los métodos de la tabla a cada objeto. Los cambios que ha realizado se pueden expresar en una tabla para que sea más fácil ver qué comportamiento ha provocado que se agregue cada método.

|Comportamiento	|Método	|Actor|
|---|---|---|
|Elige el símbolo|	choose()|	Participante|
|Compara las opciones|	compareChoices()	|GameRound|
Concede puntos|	awardPoints()|	GameRound|
|Se comprueba la respuesta para continuar|	checkEndCondition()	|Juego|
|Crédito final del juego|	determineWinner()|	Juego|

## Invocación

```bash
python3 rock-paper-scissor.py
```

### Implementación de reglas 

## Puntuación del juego

## Adición de una consulta de continuación



|Opción|	Piedra|	Documento|	Tijeras|
|---|---|---|---|
|Piedra	|0|	-1|	1|
|Documento|	1|	0|	-1|
|Tijeras|	-1|	1|	0|

```python
class Participant:
    def __init__(self, name):
        self.name = name
        self.points = 0
        self.choice = ""
    def choose(self):
        self.choice = input("{name}, select rock, paper or scissor: ".format(name= self.name))
        print("{name} selects {choice}".format(name=self.name, choice = self.choice))
    def toNumericalChoice(self):
        switcher = {
            "rock": 0,
            "paper": 1,
            "scissor": 2
        }
        return switcher[self.choice]
    def incrementPoint(self):
        self.points += 1

class GameRound:
    def __init__(self, p1, p2):
        self.rules = [
            [0, -1, 1],
            [1, 0, -1],
            [-1, 1, 0]
        ]

        p1.choose()
        p2.choose()
        result = self.compareChoices(p1,p2)
        print("Round resulted in a {result}".format(result = self.getResultAsString(result) ))
        if result > 0:
           p1.incrementPoint()
        elif result < 0:
           p2.incrementPoint()

    def compareChoices(self):
        print("implement")
    def awardPoints(self):
        print("implement")
    def compareChoices(self, p1, p2):
        return self.rules[p1.toNumericalChoice()][p2.toNumericalChoice()]
    def getResultAsString(self, result):
        res = {
            0: "draw",
            1: "win",
            -1: "loss"
        }       
        return res[result]

class Game:
    def __init__(self):
        self.endGame = False
        self.participant = Participant("Spock")
        self.secondParticipant = Participant("Kirk")
    def start(self):
        while not self.endGame:
            GameRound(self.participant, self.secondParticipant)
            self.checkEndCondition()
    def checkEndCondition(self):
        print("implement")
    def determineWinner(self):
        print("implement")
    def determineWinner(self):
        resultString = "It's a Draw"
        if self.participant.points > self.secondParticipant.points:
            resultString = "Winner is {name}".format(name=self.participant.name)
        elif self.participant.points < self.secondParticipant.points:
            resultString = "Winner is {name}".format(name=self.secondParticipant.name)
        print(resultString)
    def checkEndCondition(self):
        answer = input("Continue game y/n: ")
        if answer == 'y':
            GameRound(self.participant, self.secondParticipant)
            self.checkEndCondition()
        else:
            print("Game ended, {p1name} has {p1points}, and {p2name} has {p2points}".format(p1name = self.participant.name, p1points= self.participant.points, p2name=self.secondParticipant.name, p2points=self.secondParticipant.points))
            self.determineWinner()
            self.endGame = True

game = Game()
game.start()
```

## Adición de las opciones lagarto y Spock

La empresa está muy satisfecha con la implementación de "Piedra, papel, tijeras" mediante la programación orientada a objetos (OOP). Y por ello quieren cambiar el juego a piedra, papel, tijeras, lagarto, Spock, ya que es a lo que la juventud juega en la actualidad.

¿Pero cuáles son las reglas para lagarto y Spock?


*Las tijeras decapitan al lagarto, las tijeras cortan el papel, el papel envuelve la piedra, la piedra aplasta al lagarto, el lagarto envenena a Spock, Spock destroza las tijeras, las tijeras decapitan al lagarto, el lagarto se come el papel, el papel desaprueba a Spock, Spock volatiliza la piedra y, como siempre, la piedra aplasta a las tijeras.*

|Opción	|Piedra|	Documento|	Tijeras	|Lagarto|	Spock|
|---|---|---|---|---|---|
|Piedra	|0|	-1|	1|	1|	-1|
|Documento|	1|	0|	-1|	-1|	1|
|Tijeras|	-1|	1|	0|	1|	-1|
|Lagarto|	-1|	1|	-1|	0|	1|
|Spock|	1|	-1|	1|	-1|	0|


```python
class Participant:
    def __init__(self, name):
        self.name = name
        self.points = 0
        self.choice = ""
    def choose(self):
        self.choice = input("{name}, select rock, paper, scissor, lizard or Spock: ".format(name= self.name))
        print("{name} selects {choice}".format(name=self.name, choice = self.choice))
    def toNumericalChoice(self):
        switcher = {
             "rock": 0,
             "paper": 1,
             "scissor": 2,
             "lizard": 3,
             "spock": 4
        }
        return switcher[self.choice]
    def incrementPoint(self):
        self.points += 1

class GameRound:
    def __init__(self, p1, p2):
        self.rules = [
            [0, -1, 1, 1, -1],
            [1, 0, -1, -1, 1],
            [-1, 1, 0, 1, -1],
            [-1, 1, -1, 0, 1],
            [1, -1, 1, -1, 0]
        ]

        p1.choose()
        p2.choose()
        result = self.compareChoices(p1,p2)
        print("Round resulted in a {result}".format(result = self.getResultAsString(result) ))
        if result > 0:
           p1.incrementPoint()
        elif result < 0:
           p2.incrementPoint()

    def compareChoices(self):
        print("implement")
    def awardPoints(self):
        print("implement")
    def compareChoices(self, p1, p2):
        return self.rules[p1.toNumericalChoice()][p2.toNumericalChoice()]
    def getResultAsString(self, result):
        res = {
            0: "draw",
            1: "win",
            -1: "loss"
        }       
        return res[result]

class Game:
    def __init__(self):
        self.endGame = False
        self.participant = Participant("Spock")
        self.secondParticipant = Participant("Kirk")
    def start(self):
        while not self.endGame:
            GameRound(self.participant, self.secondParticipant)
            self.checkEndCondition()
    def checkEndCondition(self):
        print("implement")
    def determineWinner(self):
        print("implement")
    def determineWinner(self):
        resultString = "It's a Draw"
        if self.participant.points > self.secondParticipant.points:
            resultString = "Winner is {name}".format(name=self.participant.name)
        elif self.participant.points < self.secondParticipant.points:
            resultString = "Winner is {name}".format(name=self.secondParticipant.name)
        print(resultString)
    def checkEndCondition(self):
        answer = input("Continue game y/n: ")
        if answer == 'y':
            GameRound(self.participant, self.secondParticipant)
            self.checkEndCondition()
        else:
            print("Game ended, {p1name} has {p1points}, and {p2name} has {p2points}".format(p1name = self.participant.name, p1points= self.participant.points, p2name=self.secondParticipant.name, p2points=self.secondParticipant.points))
            self.determineWinner()
            self.endGame = True

game = Game()
game.start()
```