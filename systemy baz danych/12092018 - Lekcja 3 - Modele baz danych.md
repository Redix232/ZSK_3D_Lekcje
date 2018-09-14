# Lekcja 3 - Modele baz danych

## Model danych

**Model danych** - zbiór zasad opisujących dane, powiązania pomiędzy danymi, dozwolone operacje i ograniczenia nakładane na dane i operacje.

Model danych jest próbą reprezentacji świata realnego i występujących w nim obiektów, zdarzeń oraz związków zachodzących między nimi.

Opis każdego modelu danych obejmuje zwykle 3 składowe:

- Strukturę danych (fizyczny model danych) - konstrukcje znane z języków programowania, np. klasy, tablice
- Operacje na danych (część manipulacyjna) - działania na danych, które są dozwolone
- Więzy integralności (reguły poprawności) - ograniczenia nakładane na dane, np. miesiąc to liczba całkowita z przedziału od 1 do 12, płeć to litera K lub M.

## Hierarchiczny model bazy danych

### Struktura

Dane w tym typie bazy mają strukturę hierarchiczną, a typowy diagram ma kształt odwróconego drzewa.

Istnieje jeden korzeń (tabela nadrzędna) oraz synowie (tabele podrzędne). Jeden ojciec może mieć wiele dzieci, ale każde dziecko ma jednego ojca. Każdy rekord (z wyjątkiem głównego, na szczycie) powiązany jest z jednym rekordem nadrzędnym. Model hierarchiczny opiera się na dwóch strukturach: typach rekordów i związkach nadrzędny-podrzędny.

### Integralność danych

Podstawowe warunki integralności wynikają z samej definicji struktury danych modelu. Każdy rekord (z wyjątkiem korzenia) musi być powiązany z rekordem nadrzędnym właściwego typu; a więc np. usunięcie rekordu nadrzędnego wiąże się z usunięciem wszystkich względem niego podrzędnych. Nie można wstawić rekordu bez powiązania go z rekordem nadrzędnym.

## Sieciowy model danych

**Sieciowy model danych** w ogólnym zarysie niewiele odbiega od hierarchicznego.

W miejsce związku nadrzędny-podrzędny pomiędzy rekordami wprowadza się w nim tzw. typ kolekcji.

Określenie typu kolekcji polega na podaniu typu rekordu-"właściciela" i typu rekordów-elementów kolekcji.

## Relacyjny model danych

Relacyjny model danych został opracowany przez Edgara Franka Codda w latach 70./80. XX wieku, i stał się podstawą architektury większości popularnych SZBD.

### Definicja danych

Model relacyjny oparty jest na tylko jedne podstawowej strukturze danych - relacji. Pojęcie relacji można uważać za pewną abstrakcję intuicyjnego pojęcia tabeli, zbudowanej z wierszy i kolumn, w której na przecięciu każdej kolumny z każdym wierszem występuje określona wartość.

Codd używa terminów:

- **relacja** zamiast _tabela_
- **atrybut** zamiast _kolumna_
- **krotka** zamiast _wiersz_

Relacja spełnia następujące własności:

- Każda relacja w bazie danych jest jednoznacznie określona przez swoją nazwę.
- Każda kolumna w relacji ma jednoznaczną nazwę w ramach tej relacji.
- Porządek kolumn w relacji nie jest istotny. Kolumny nazywane bywają również _atrybutami_
- Wszystkie wartości w danej kolumnie muszą być tego samego typu. Zbiór możliwych wartości elementów danej kolumny nazywany bywa też _dziedziną_.
- Kolejność wierszy nie jest istotna; w szczególności, nie ma powtarzających się wierszy. Wiersze relacji nazywa się też _krotkami_
- Każde pole (przecięcie wiersza z kolumną) musi zawierać wartość atomową z dziedziny określonej przez kolumnę. Brakowi wartości odpowiada wartość specjalna `NULL`, zgodna z każdym typem kolumny (chyba, że została jawnie wykluczona przez definicję typu kolumny).
- Każda relacja zawiera klucz główny - kolumnę (lub kolumny), której wartoci jednoznacznie identyfikują wiersz (a więc w szczególności nie powtarzają się). Wartością klucza nie może być `NULL`.
