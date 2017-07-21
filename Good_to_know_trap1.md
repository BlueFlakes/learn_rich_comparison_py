# Rich Comparison

Pułapki:
  * Próba porównania ze sobą dwóch obiektów różnych klas, może zaistnieć sytuacja w której druga klasa nie będzie posiadała
    atrybutów pierwszej klasy

## Example
```
class Codecooler:

    def __init__(self, name, surname, intelligence):
        self.name = name
        self.surname = surname
        self.intelligence = intelligence

    def __eq__(self, other):
        return self.intelligence == other.intelligence


class OfficeManager:

    def __init__(self, name, surname):
        self.name = name
        self.surname = surname

def main():
    kamil = Codecooler('Kamil', 'Konior', 1003210)
    sauron = OfficeManager('Sauron', 'zSosnowca')

    if kamil == sauron:
        print('hell no!')


if __name__ == "__main__":
    main()
```
Komentarz: 
  * Porównanie metodą magiczną __eq__ następuje za pomocą atrybutu intelligence. W przedstawionym przypadku klasa OfficeManager
    nie posiada atrybutu inteliigence dlatego ważne jest wiedzieć że może nam się sypnąć(AttributeError) program jeśli 
    nie sprawdzimy czy oba obiekty są tej samej klasy lub przynajmniej obaj posiadają te atrybuty.

## Solution Example
```
class Codecooler:

    def __init__(self, name, surname, intelligence):
        self.name = name
        self.surname = surname
        self.intelligence = intelligence

>   def __eq__(self, other):
>       comparison_score = False
>
>       if isinstance(other, Codecooler):
>           comparison_score = (self.intelligence == other.intelligence)
>
>       return comparison_score


class OfficeManager:

    def __init__(self, name, surname):
        self.name = name
        self.surname = surname

def main():
    kamil = Codecooler('Kamil', 'Konior', 1003210)
    sauron = OfficeManager('Typowy ent', 'zSosnowca')

    if kamil == sauron:
        print('hell no!')

    print('returned comparison_score ==', kamil == sauron, end=2*'\n')


if __name__ == "__main__":
    main()
```
Komentarz:
  Za pomocą metody isinstance sprawdzamy czy dostarczony obiekt jest obiektem klasy oczekiwanej.
