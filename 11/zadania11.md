
# Systemy operacyjne - lab nr 11

## Zlecanie zadań do systemów kolejkowych cz. I

1. Proszę stworzyć w pliku `atjob.task` zadanie do zlecenia do kolejki dla demona (`daemon`) `at`. Za pomocą komendy `at` powinno się dać zlecić wykonanie zadań (komend) opisanych w pliku `atjob.task` o określonej porze, według specyfikacji komendy `at`. W kolejnych punktach (2 i 4, 4 - trudniejszy) opisane jest, jakie działania powinny w ramach `atjob.task` zostać wykonane. W punkcie 3-cim, trzeba opisać, jak uruchomić skrypt `atjob.task` za pomocą `at` o określonej porze. Za 2 i 3 punkt będą 2 pierwsze punkty, a za zadanie 4 - 2 punkty ostatnie.

1. Program `atjob.task` ma za pomocą `ls -lR` wylistować informacje o wszystkich plikach zawartych w katalogu domowym (tzn `~`, co zazwyczaj będzie katalogiem `student` bądź `Student`) i umieścić te informacje w pliku `ls.log` w folderze `~/LOGIN`, **gdzie LOGIN zastępujemy nazwą loginu na alioth**, np. `~/piosto`. 

1. Proszę napisać w pliku `README` komendę `at`, która pozwoli na uruchomienie zadania o godzinie 12:15 dnia 21-12-2022 ( **Wskazówka:** możliwości specyfikacji czasu uruchomienia jest dużo, w manualu (`man at`) najbardziej jednoznaczny sposób ustalenia daty jest opisany pod opcją `-t`.) 

1. Oprócz zadań z punktu nr 2, skrypt ma zapisać dane o wszystkich plikach w ramach `~`, których rozmiar przekracza `1 MB`, w formie pliku tekstowego `bigfiles`, gdzie jedna linijka opisuje jeden z plików za pomocą formatu `nazwa:uprawnienia:nazwa_ownera:rozmiar`, gdzie każde ze słów przedzielone `:` ma zostać zastąpione przez określoną dla danego pliku wartość:
	- `nazwa` - nazwa pliku (może być ze ścieżką absolutną doklejoną z lewej strony),
	- `uprawnienia` - kod LICZBOWY uprawnień (baza ósemkowa),
	- `nazwa_ownera` - nazwa użytkownika, który jest właścicielem,
	- `rozmiar` - rozmiar pliku (najlepiej w **megabajtach**)

**Wskazówki:** 

- Komenda `find NAZWA_FOLDERU_DO_PRZESZUKANIA` domyślnie wyświetli na standardowe wyjście wszystkie pliki w folderze `NAZWA_FOLDERU_DO_PRZESZUKANIA` linijka-po-linijce.
- Dodatkowe opcje **dodane po pierwszym argumencie określającym folder** pozwalają na przefiltrowanie wyników, np. opcja `-size <operator><liczba><jednostka>` pozwala w intuicyjny sposób na wyszukanie plików, których rozmiar spełnia dane kryteria. Przykładowo, `find SomeFolder -size -2MB` ogranicza wyniki do plików, które są **mniejsze** (stąd operator to minus, `-`) niż `2MB`.
- opcja `-exec KOMENDA_BEGINNING {} KOMENDA_END \;` dodana do `find` zmieni działanie programu- na standardowe wyjście nie będzie wyświetlana ścieżka do pliku, a wynik działania komendy opisanej przez `KOMENDA_BEGINNING {} KOMENDA_END` na **każdym** odnalezionym pliku przez `find`. `{}` to symbol który ma być zastąpiony poprzez nazwę pliku- tak aby komenda miała poprawną składnię. Przykładowo, aby dla każdego pliku w folerze `~/piosto/` wykonać komendę `wc -l`, komenda `find` będzie wyglądać tak: `find ~/piosto -exec wc -l {} \;`
- do uzyskania wszystkich informacji w ostatnim punkcie zadania o danym pliku można użyć komendy `stat` w połączeniu z `find` i `-exec`. Domyślnie, `stat FILENAME` wyświetla pewne standardowe informacje o pliku `FILENAME`. Aby wyszczególnić określone informacje przydatna jest opcja `-f`, która pozwala dokładnie określić jak ma wyglądać wynik działania `stat` na podstawie łańcucha znaków określającego format (tzw `format string`). Specyfikacje dla formatu określane są podobnie, jak w funkcji `printf` w języku C, za pomocą składni używającej `%`. Przykładowo, aby wyświetlić uprawnienia w formie kodu ósemkowego, poprzedzone słowami `uprawnienia: ` należy napisać łańcuch `uprawienia: %A`. Sekcja `Formats`, a w szczególności część `fmt` w `man stat` opisuje, jak można specyfikować łańcuchy znaków. Najprostsze elementy składni dla danego formatu, pisane od lewej do prawej to: 
    - specyfikacja zawsze zaczyna się od znaku `%`,
    - następnie, opcjonalnie można podać jeden ze specyfikatorów `D,O,U,X,F,S`, określające preferowaną formę zapisu właściwej wartości specyfikwanej następnym symbolem, np. `D` lub `U` to dwa sposoby określenia, że oczekujemy liczby w bazie 10, a `S`, że oczekujemy opisu w formie łańcucha znaków.
    - ostatnia część to litery określające typ danych, jaki chcemy wyciągnąć, m. in. `u` - nazwa właściciela pliku, `z` - rozmiar w bajtach, `N` - nazwa pliku.
    - przykłady (różne sposoby wyświetlenia nazwy pliku `FILENAME` i nazwy użytkownika będącego jego właścicielem):
	- `stat -f '%SN <- filename; username->  %Su' FILENAME` 
	- `stat -f 'fname: %SN   uid: %Du' FILENAME` 
    - w powyższych przykładach, w miejsce przykładowych strzałek i słów filename, username etc. można wpisać, co się chce- istotne są specyfikacje określone przez `%`.
    - jeśli chodzi o użycie `stat` do otrzymania informacji o rozmiarze pliku- prawdopodobnie najprościej uzyskać rozmiar za pomocą tej komendy wyrażony w bajtach, a potem policzyć konwersję np. w `awk`, ostatecznie drukując wszystko według określonego formatu

Jako rozwiązania proszę przesłać `.tar` zawierający plik `README` oraz `atjob.task` proszę przesłać [na tą samą stronę, co wcześniej](https://alioth.uwb.edu.pl/cgi-bin/so-lab/rejestr)
