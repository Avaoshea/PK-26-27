# Laboratorium 01: podstawy programu w C++

Na pierwszym laboratorium poznamy podstawową budowę programu w języku C++ oraz nauczymy się korzystać ze zmiennych, prostych działań arytmetycznych, danych tekstowych oraz wejścia i wyjścia.

Część osób może mieć podczas tych zajęć pierwszy kontakt z programowaniem. Najważniejsze jest więc zrozumienie podstawowej struktury programu oraz tego, w jakiej kolejności wykonywane są instrukcje.

---

## 1. Podstawowa struktura programu

Najprostszy program w C++ może wyglądać tak:

```cpp
#include <iostream>

using namespace std;

int main() {

    cout << "Pierwszy program w C++" << endl;

    return 0;
}
```

Każdy element ma tutaj konkretne znaczenie.

---

## 2. Program jest czytany od góry do dołu

Kod programu jest analizowany przez kompilator od góry do dołu.

Dlatego elementy potrzebne później powinny zostać wcześniej:

- dołączone,
- zadeklarowane,
- albo zdefiniowane.

Przykładowy porządek programu:

```cpp
#include <iostream>

using namespace std;

int main() {

    // deklaracje zmiennych

    // wczytywanie danych

    // obliczenia

    // wyświetlanie wyników

    return 0;
}
```

Na pierwszych zajęciach będziemy trzymać się właśnie takiego układu.

---

## 3. `#include`

Na początku programu znajdują się dyrektywy `#include`.

Przykład:

```cpp
#include <iostream>
```

Biblioteka `<iostream>` umożliwia korzystanie między innymi z:

```cpp
cout
cin
endl
```

Jeżeli chcemy używać tekstów typu `string`, możemy również dołączyć:

```cpp
#include <string>
```

Do formatowania liczb rzeczywistych będziemy używać:

```cpp
#include <iomanip>
```

Przykładowy początek programu może więc wyglądać tak:

```cpp
#include <iostream>
#include <string>
#include <iomanip>

using namespace std;
```

Nie każdy program musi korzystać ze wszystkich bibliotek. Dołączamy te, których potrzebujemy.

---

## 4. Funkcja `main()`

Każdy program musi mieć miejsce, od którego rozpoczyna się jego wykonywanie.

W C++ jest nim funkcja:

```cpp
int main()
```

Przykład:

```cpp
int main() {

    cout << "Start programu" << endl;

    return 0;
}
```

Instrukcje znajdujące się pomiędzy:

```cpp
{
}
```

należą do funkcji `main()`.

Instrukcja:

```cpp
return 0;
```

oznacza poprawne zakończenie programu.

Na pierwszych zajęciach cały kod programu będziemy umieszczać wewnątrz `main()`.

---

## 5. `using namespace std`

Elementy takie jak:

```cpp
cout
cin
string
endl
```

należą do przestrzeni nazw `std`.

Bez:

```cpp
using namespace std;
```

należałoby pisać na przykład:

```cpp
std::cout << "Test" << std::endl;
```

Po dodaniu:

```cpp
using namespace std;
```

możemy pisać krócej:

```cpp
cout << "Test" << endl;
```

Na początku zajęć będziemy korzystać z:

```cpp
using namespace std;
```

ponieważ upraszcza zapis.

---

## 6. Instrukcje i średnik

Większość instrukcji w C++ kończymy średnikiem:

```cpp
;
```

Przykład:

```cpp
int x = 10;
cout << x << endl;
return 0;
```

Brak średnika jest jednym z najczęstszych błędów na początku nauki programowania.

---

## 7. Zmienne

Zmienna to miejsce w pamięci programu, w którym przechowujemy określoną wartość.

Przykład:

```cpp
int liczbaPunktow = 20;
```

W tym przypadku:

- `int` oznacza typ zmiennej,
- `liczbaPunktow` jest nazwą zmiennej,
- `20` jest jej wartością.

Zmiennej można od razu nadać wartość:

```cpp
int poziom = 3;
```

Można ją również najpierw zadeklarować:

```cpp
int poziom;
```

a wartość przypisać później:

```cpp
poziom = 3;
```

---

## 8. Podstawowe typy danych

### `int`

Typ całkowity.

Przykłady:

```cpp
int liczba = 10;
int rok = 2026;
int liczbaPunktow = 24;
```

Przechowuje liczby bez części ułamkowej.

---

### `float`

Typ zmiennoprzecinkowy.

Przykłady:

```cpp
float temperatura = 21.5;
float masa = 12.75;
```

Służy do przechowywania liczb rzeczywistych.

---

### `double`

Również służy do przechowywania liczb rzeczywistych, ale pozwala przechowywać je z większą precyzją niż `float`.

```cpp
double pomiar = 3.14159265;
```

---

### `char`

Przechowuje pojedynczy znak.

```cpp
char symbol = 'A';
```

Wartość typu `char` zapisujemy w pojedynczych apostrofach:

```cpp
'A'
```

---

### `bool`

Przechowuje jedną z dwóch wartości:

```cpp
true
false
```

Przykład:

```cpp
bool czyAktywny = true;
```

---

### `string`

Typ `string` służy do przechowywania tekstu.

Przykład:

```cpp
string kolor = "zielony";
```

Tekst zapisujemy w cudzysłowie:

```cpp
"zielony"
```

Aby korzystać z typu `string`, możemy dołączyć bibliotekę:

```cpp
#include <string>
```

Przykład:

```cpp
#include <iostream>
#include <string>

using namespace std;

int main() {

    string miasto;

    cout << "Podaj miasto: ";
    cin >> miasto;

    cout << "Wybrano: " << miasto << endl;

    return 0;
}
```

`cin >> miasto` wczytuje pojedyncze słowo.

Na pierwszym laboratorium jest to wystarczające, ponieważ będziemy pracować z prostymi danymi tekstowymi.

---

## 9. Nazwy zmiennych

Nazwy zmiennych powinny informować, co dana wartość oznacza.

Lepiej:

```cpp
float temperatura;
```

niż:

```cpp
float x;
```

Nazwa zmiennej:

- nie może zaczynać się od cyfry,
- nie może zawierać spacji,
- nie może być słowem kluczowym języka C++.

Poprawne przykłady:

```cpp
wiek
temperatura
liczbaPunktow
liczba_studentow
promien
```

---

## 10. Wyświetlanie danych: `cout`

Do wyświetlania informacji używamy:

```cpp
cout
```

Przykład:

```cpp
cout << "Program uruchomiony" << endl;
```

Możemy również wyświetlać wartości zmiennych:

```cpp
int x = 10;

cout << x << endl;
```

Tekst można łączyć ze zmiennymi:

```cpp
cout << "Wartosc x = " << x << endl;
```

Operator:

```cpp
<<
```

przekazuje dane do strumienia wyjściowego.

Możemy przekazać kilka elementów jeden po drugim:

```cpp
cout << "x = " << x << endl;
```

---

## 11. `endl`

Instrukcja:

```cpp
endl
```

powoduje przejście do nowej linii.

Przykład:

```cpp
cout << "Pierwsza linia" << endl;
cout << "Druga linia" << endl;
```

Wynik:

```text
Pierwsza linia
Druga linia
```

---

## 12. Wprowadzanie danych: `cin`

Do pobierania danych od użytkownika używamy:

```cpp
cin
```

Przykład:

```cpp
int numer;

cout << "Podaj numer: ";
cin >> numer;
```

Operator:

```cpp
>>
```

pobiera dane wpisane przez użytkownika i zapisuje je do zmiennej.

Możemy wczytywać różne typy danych:

```cpp
int liczba;
float temperatura;
string kolor;

cin >> liczba;
cin >> temperatura;
cin >> kolor;
```

Możemy również wczytać kilka wartości:

```cpp
cin >> a >> b;
```

Na początku wygodniej jednak zapisywać każdą operację osobno, ponieważ kod jest wtedy bardziej czytelny.

---

## 13. Wczytywanie i wyświetlanie danych

Typowy fragment programu może wyglądać tak:

```cpp
int numer;

cout << "Podaj numer: ";
cin >> numer;

cout << "Wprowadzono: " << numer << endl;
```

Najpierw:

1. deklarujemy zmienną,
2. wyświetlamy komunikat,
3. pobieramy wartość,
4. wykorzystujemy ją w dalszej części programu.

---

## 14. Zasięg zmiennej: scope

Zmienne mają określony zasięg działania.

Najprościej mówiąc: zmienna istnieje wewnątrz bloku `{ }`, w którym została zadeklarowana.

Przykład:

```cpp
int main() {

    int x = 10;

    cout << x << endl;

    return 0;
}
```

Zmienna `x` jest dostępna wewnątrz funkcji `main()`.

Jeżeli utworzymy dodatkowy blok:

```cpp
int main() {

    {
        int x = 10;
        cout << x << endl;
    }

    return 0;
}
```

po wyjściu z tego bloku zmienna `x` przestaje być dostępna.

Na pierwszych zajęciach większość zmiennych będziemy deklarować bezpośrednio wewnątrz `main()`.

---

## 15. Kolejność wykonywania instrukcji

Program jest wykonywany instrukcja po instrukcji, od góry do dołu.

Przykład:

```cpp
int x = 10;

cout << x << endl;

x = 20;

cout << x << endl;
```

Wynik:

```text
10
20
```

Najpierw `x` ma wartość `10`.

Następnie wykonuje się pierwsze `cout`.

Później przypisujemy:

```cpp
x = 20;
```

i dopiero wtedy wykonywane jest kolejne `cout`.

Kolejność instrukcji ma więc znaczenie.

---

## 16. Podstawowe działania arytmetyczne

W C++ możemy korzystać z podstawowych operatorów matematycznych:

```text
+    dodawanie
-    odejmowanie
*    mnożenie
/    dzielenie
```

Przykład:

```cpp
int x = 12;
int y = 4;

int wynik1 = x + y;
int wynik2 = x - y;
int wynik3 = x * y;
int wynik4 = x / y;
```

Możemy również wykonywać obliczenia bez tworzenia dodatkowej zmiennej:

```cpp
cout << x + y << endl;
```

W bardziej rozbudowanych programach często czytelniejsze jest jednak zapisanie wyniku do osobnej zmiennej.

---

## 17. Kolejność wykonywania działań matematycznych

C++ stosuje standardową kolejność wykonywania działań matematycznych.

Najpierw wykonywane są między innymi:

```text
*
/
```

a później:

```text
+
-
```

Jeżeli chcemy jednoznacznie określić kolejność działań, używamy nawiasów:

```cpp
wynik = (a + b) * c;
```

W zadaniach matematycznych warto stosować nawiasy również wtedy, gdy poprawiają czytelność zapisu.

---

## 18. Stałe

Jeżeli dana wartość nie powinna zmieniać się podczas działania programu, możemy zadeklarować ją jako stałą.

Przykład:

```cpp
const float WSPOLCZYNNIK = 1.25;
```

Słowo:

```cpp
const
```

oznacza, że wartości tej zmiennej nie będziemy później zmieniać.

Stałe często zapisuje się wielkimi literami, aby łatwo odróżnić je od zwykłych zmiennych.

---

## 19. Wyświetlanie liczb z określoną liczbą miejsc po przecinku

Do formatowania liczb rzeczywistych używamy biblioteki:

```cpp
#include <iomanip>
```

Przydatne są:

```cpp
fixed
setprecision()
```

Przykład:

```cpp
#include <iostream>
#include <iomanip>

using namespace std;

int main() {

    float x = 7.42891;

    cout << fixed << setprecision(2);
    cout << x << endl;

    return 0;
}
```

Wynik:

```text
7.43
```

Instrukcja:

```cpp
cout << fixed << setprecision(2);
```

oznacza, że kolejne liczby rzeczywiste wypisywane przez `cout` będą wyświetlane z dokładnością do dwóch miejsc po przecinku.

---

## 20. Zmiana liczby miejsc po przecinku

Liczbę miejsc po przecinku można łatwo zmieniać.

Jedno miejsce:

```cpp
cout << fixed << setprecision(1);
```

Przykładowy wynik:

```text
7.4
```

Dwa miejsca:

```cpp
cout << fixed << setprecision(2);
```

Przykładowy wynik:

```text
7.43
```

Trzy miejsca:

```cpp
cout << fixed << setprecision(3);
```

Przykładowy wynik:

```text
7.429
```

Liczba znajdująca się w:

```cpp
setprecision(...)
```

określa liczbę miejsc po przecinku, jeżeli używamy jednocześnie:

```cpp
fixed
```

---

## 21. `fixed` i `setprecision()`

Na początku będziemy najczęściej stosować:

```cpp
cout << fixed << setprecision(2);
```

Ważne jest połączenie obu elementów.

Z:

```cpp
fixed
```

wartość:

```cpp
setprecision(2)
```

oznacza dwie cyfry po przecinku.

Bez `fixed` funkcja `setprecision()` działa inaczej i określa liczbę cyfr znaczących.

Dlatego podczas pierwszych laboratoriów, jeśli zadanie wymaga określonej liczby miejsc po przecinku, korzystaj z:

```cpp
fixed << setprecision(...)
```

---

## 22. Konwersja typu

Czasami potrzebujemy przedstawić wartość zapisaną w jednym typie jako inny typ.

Przykładowo wartość:

```cpp
float x = 7.89;
```

możemy przedstawić jako `int`:

```cpp
static_cast<int>(x)
```

Przykład:

```cpp
cout << static_cast<int>(x) << endl;
```

Wynik:

```text
7
```

Część ułamkowa zostaje odrzucona.

Warto zwrócić uwagę, że:

```cpp
static_cast<int>(x)
```

nie oznacza tego samego co zmiana sposobu wyświetlania za pomocą `setprecision()`.

`setprecision()` zmienia sposób prezentowania liczby.

`static_cast<int>()` zmienia typ wartości.

Na tym etapie wystarczy zapamiętać podstawową składnię:

```cpp
static_cast<int>(wartosc)
```

Do konwersji typów wrócimy jeszcze później.

---

## 23. `int` i `float` to różne typy

Przykład:

```cpp
int a = 5;
float b = 5.0;
```

Obie wartości wyglądają podobnie, ale mają różne typy.

`int` przechowuje liczby całkowite.

`float` pozwala przechowywać część ułamkową.

Dlatego przy deklarowaniu zmiennej należy zastanowić się, jaki rodzaj danych będzie w niej przechowywany.

---

## 24. Czytelność kodu

Kod powinien być czytelny.

Zamiast:

```cpp
int main(){int x=10;cout<<x<<endl;return 0;}
```

pisz:

```cpp
int main() {

    int x = 10;

    cout << x << endl;

    return 0;
}
```

Wcięcia i puste linie nie zmieniają działania programu, ale znacznie poprawiają jego czytelność.

---

## 25. Komentarze

Komentarze pozwalają opisać kod.

Komentarz jednoliniowy rozpoczynamy od:

```cpp
//
```

Przykład:

```cpp
// deklaracja zmiennej
int x = 10;
```

Komentarz może znajdować się również po instrukcji:

```cpp
int x = 10; // liczba punktow
```

Komentarze są przeznaczone dla osoby czytającej kod.

Kompilator ich nie wykonuje.

---

## 26. Dokładny format wyjścia

W zadaniach automatycznie sprawdzanych bardzo ważny jest dokładny format wypisywanego tekstu.

Jeżeli oczekiwany wynik zawiera:

```text
Wynik: 10
```

to program powinien wypisać dokładnie taki tekst.

Znaczenie mogą mieć:

- wielkie i małe litery,
- spacje,
- dwukropki,
- wykrzykniki,
- kolejność informacji,
- przejścia do nowej linii,
- liczba miejsc po przecinku.

Przykład:

```text
Podaj numer: 5
```

nie jest tym samym co:

```text
Numer = 5
```

Automatyczny system sprawdzający może uznać drugi zapis za błędny, nawet jeżeli sam wynik obliczeń jest poprawny.

Dlatego zawsze dokładnie przeczytaj sekcję:

```text
Wyjście:
```

w treści zadania.

---

## 27. Dane wprowadzane przez użytkownika

W przykładach do zadań dane wpisywane przez użytkownika mogą być wyróżnione.

Program powinien wypisywać komunikaty, natomiast wartości testowe są podawane z zewnątrz i pobierane za pomocą:

```cpp
cin
```

Nie należy wpisywać przykładowych danych z treści zadania na stałe do programu.

---

## 28. Nie wpisuj danych testowych na stałe

Jeżeli zadanie mówi, że program ma wczytać wartość od użytkownika, należy użyć:

```cpp
cin
```

Nie należy robić:

```cpp
int liczba = 5;
```

jeżeli `5` jest tylko przykładową wartością przedstawioną w treści zadania.

Zamiast tego:

```cpp
int liczba;

cout << "Podaj wartosc: ";
cin >> liczba;
```

Dzięki temu program zadziała również dla innych danych testowych.

---

## 29. Najczęstsze błędy na początku

Przed uruchomieniem programu sprawdź:

- czy plik ma rozszerzenie `.cpp`,
- czy masz `#include <iostream>`,
- czy przy korzystaniu z `string` masz dostęp do typu `string`,
- czy przy używaniu `setprecision()` masz `#include <iomanip>`,
- czy instrukcje kończą się średnikiem `;`,
- czy każda zmienna została wcześniej zadeklarowana,
- czy typ zmiennej jest odpowiedni do przechowywanych danych,
- czy używasz poprawnych nawiasów `{ }`,
- czy kod znajduje się wewnątrz `main()`,
- czy zapisujesz plik przed uruchomieniem programu,
- czy nie wpisałeś przykładowych danych z zadania na stałe,
- czy tekst wypisywany przez program jest zgodny z oczekiwanym formatem.

---

## 30. Czytanie błędów kompilatora

Jeżeli program nie chce się skompilować, przeczytaj komunikat błędu.

Kompilator często podaje:

- nazwę pliku,
- numer linii,
- informację o rodzaju problemu.

Pamiętaj jednak, że miejsce wskazane przez kompilator nie zawsze jest miejscem, w którym rzeczywiście powstał błąd.

Przykład:

```cpp
int x = 10
cout << x << endl;
```

Brakuje średnika po:

```cpp
int x = 10;
```

Kompilator może jednak zgłosić problem dopiero przy następnej instrukcji:

```cpp
cout
```

Dlatego warto sprawdzić również poprzednią linię kodu.

---

## 31. Najważniejszy schemat programu

Na pierwszych zajęciach większość programów będzie miała strukturę podobną do:

```cpp
#include <iostream>

using namespace std;

int main() {

    // deklaracja zmiennych

    // pobranie danych

    // obliczenia

    // wyświetlenie wyniku

    return 0;
}
```

Jeżeli program korzysta z tekstu:

```cpp
#include <iostream>
#include <string>

using namespace std;

int main() {

    // kod programu

    return 0;
}
```

Jeżeli potrzebujemy formatować liczby rzeczywiste:

```cpp
#include <iostream>
#include <iomanip>

using namespace std;

int main() {

    // deklaracja zmiennych

    // pobranie danych

    // obliczenia

    cout << fixed << setprecision(2);

    // wyświetlenie wyniku

    return 0;
}
```

---

## 32. Schemat pracy nad zadaniem

Przed rozpoczęciem pisania kodu zastanów się:

1. Jakie dane program ma wczytać?
2. Jakiego typu powinny być zmienne?
3. Jakie obliczenia należy wykonać?
4. Jak powinien wyglądać wynik?
5. Czy wynik ma być liczbą całkowitą czy rzeczywistą?
6. Czy trzeba określić liczbę miejsc po przecinku?
7. Czy tekst wyjściowy musi mieć konkretny format?

Dopiero potem zacznij pisać program.

Typowy schemat:

```text
biblioteki
    ↓
using namespace
    ↓
main()
    ↓
deklaracja zmiennych
    ↓
wczytanie danych
    ↓
obliczenia
    ↓
wyświetlenie wyników
    ↓
return 0
```

Na początku najważniejsze jest pisanie prostych i czytelnych programów oraz rozumienie, co robi każda instrukcja.