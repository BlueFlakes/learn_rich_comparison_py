## Rich Comparison

  * Jeśli nie zaimplementujemy metody porównania obiektów i spróbujemy ją wykonać to wyskoczy na nas TypeError.
  ### Example
  ```
  class Codecooler:

    def __init__(self, name, surname, intelligence):
        self.name = name
        self.surname = surname
        self.intelligence = intelligence

    def __eq__(self, other):
        comparison_score = (self.intelligence == other.intelligence)


def main():
    kamil = Codecooler('Kamil', 'Konior', 1003210)
    gandalf = Codecooler('Typowy ent', 'zSosnowca', 121)

    if kamil > gandalf:
        print('Wysoki jak mount everest')


if __name__ == "__main__":
    main()
    ```
Komentarz:
   * Jeszcze nie zdefiniowaliśmy metody "greater than", więc próba dokonania tego cudu bez implementacji 
     metody __gt__ wyskoczy na nas z TypeError :D
     Po prostu trzeba dorobić resztę metod ^^
