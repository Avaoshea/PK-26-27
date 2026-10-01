# Programowanie komputerów w języku C++: przykłady z laboratoriów

To repozytorium zawiera **przykłady kodu prezentowane i omawiane podczas zajęć laboratoryjnych** z programowania w języku C++.

Repozytorium ma przede wszystkim ułatwić dostęp do przykładów z zajęć oraz umożliwić ich samodzielne uruchamianie i modyfikowanie.

> **Uwaga:** zadania przeznaczone do samodzielnego wykonania i oddania znajdują się na platformie **UPEL**.  
> To repozytorium nie zastępuje materiałów ani zadań publikowanych na UPEL-u.

## Struktura repozytorium

Materiały są podzielone według kolejnych laboratoriów:

    cpp-lab/
    ├── README.md
    ├── lab01/
    │   ├── README.md
    │   ├── lab01_zad01.cpp
    │   ├── lab01_zad02.cpp
    │   └── lab01_zad03.cpp
    ├── lab02/
    │   ├── README.md
    │   ├── lab02_zad01.cpp
    │   └── lab02_zad02.cpp
    ├── lab03/
    │   └── ...
    └── .devcontainer/

W każdym katalogu `labXX` mogą znajdować się:

- przykładowe programy omawiane podczas zajęć,
- dodatkowe informacje w pliku `README.md`,
- krótkie przykłady pokazujące wybrane elementy języka C++.

---

## GitHub Codespaces

Podczas zajęć będziemy korzystać z **GitHub Codespaces**.

Codespaces udostępnia środowisko programistyczne działające w przeglądarce. Zawiera edytor Visual Studio Code oraz terminal, w którym możemy kompilować i uruchamiać programy.

---

## Pliki źródłowe C++

Programy piszemy w języku **C++**.

Pliki zawierające kod źródłowy C++ muszą mieć rozszerzenie:

    .cpp

Przykładowe poprawne nazwy plików:

    program.cpp
    lab01_zad01.cpp
    petla.cpp
    tablice.cpp

---

## Uruchamianie programu: przycisk Run ▶

Najwygodniejszym sposobem uruchamiania programów podczas laboratoriów jest użycie przycisku **Run ▶** znajdującego się w edytorze Visual Studio Code.

Do obsługi programów C++ potrzebne jest rozszerzenie:

**C/C++: Microsoft**

Jeżeli rozszerzenie nie jest zainstalowane:

1. wybierz zakładkę **Extensions** po lewej stronie okna Visual Studio Code,
2. wyszukaj `C++`,
3. znajdź rozszerzenie **C/C++** firmy Microsoft,
4. wybierz **Install**.

Po otwarciu pliku `.cpp` w prawym górnym rogu edytora powinien pojawić się przycisk:

    ▶

Po jego wybraniu, przy pierwszym uruchomieniu programu, może pojawić się okno z wyborem konfiguracji debugowania.

Wybierz:

    C/C++: g++ Kompiluj i debuguj aktywny plik

Ta opcja wykorzystuje kompilator `g++` dostępny w GitHub Codespaces.

Nie wybieraj opcji:

    (gdb) Launch

Jeżeli pojawi się również opcja z `g++-13`, można jej użyć, ale na zajęciach będziemy korzystać z podstawowej opcji:

    C/C++: g++ Kompiluj i debuguj aktywny plik

Po wybraniu tej konfiguracji program zostanie skompilowany i uruchomiony.

Przy kolejnych uruchomieniach Visual Studio Code zwykle zapamięta wybraną konfigurację.

---

## Podstawowe komendy terminala

Mimo że większość programów można wygodnie uruchamiać przyciskiem **Run ▶**, warto znać kilka podstawowych poleceń terminala.

### `pwd`

Wyświetla katalog, w którym aktualnie się znajdujemy.

    pwd

### `ls`

Wyświetla zawartość aktualnego katalogu.

    ls

Przykładowo:

    README.md  lab01  lab02  lab03

### `cd`

Pozwala przejść do innego katalogu.

Aby wejść do katalogu `lab01`:

    cd lab01

Aby wrócić o jeden poziom wyżej:

    cd ..

### `clear`

Czyści zawartość terminala:

    clear

---

## Kompilowanie programu w terminalu

Program można również skompilować ręcznie w terminalu.

W Codespaces będziemy korzystać z kompilatora `g++`.

Jeżeli w katalogu znajduje się plik:

    lab01_zad01.cpp

możemy go skompilować poleceniem:

    g++ lab01_zad01.cpp -o lab01_zad01

Opcja:

    -o lab01_zad01

określa nazwę utworzonego programu.

Po poprawnej kompilacji uruchamiamy go poleceniem:

    ./lab01_zad01

Czyli cały proces wygląda następująco:

    g++ lab01_zad01.cpp -o lab01_zad01
    ./lab01_zad01

Jeżeli zmienimy kod programu, należy go ponownie skompilować przed uruchomieniem nowej wersji.

---

## Przykład pracy z plikiem

Załóżmy, że chcemy uruchomić program:

    lab01/lab01_zad01.cpp

Możemy po prostu:

1. otworzyć katalog `lab01`,
2. otworzyć plik `lab01_zad01.cpp`,
3. nacisnąć **Run ▶**,
4. przy pierwszym uruchomieniu wybrać konfigurację:

    C/C++: g++ Kompiluj i debuguj aktywny plik

Alternatywnie możemy zrobić to z poziomu terminala:

    cd lab01
    g++ lab01_zad01.cpp -o lab01_zad01
    ./lab01_zad01

---

## Materiały do poszczególnych laboratoriów

Każdy katalog `labXX` może zawierać własny plik `README.md` z dodatkowymi informacjami dotyczącymi danego laboratorium.

Przed rozpoczęciem pracy warto więc sprawdzić plik:

    labXX/README.md

Szczegółowe zadania do wykonania oraz materiały wymagane do zaliczenia laboratoriów znajdują się na **UPEL-u**.