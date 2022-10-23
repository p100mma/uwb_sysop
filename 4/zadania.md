
# Systemy operacyjne- lab nr 4

## Konsolowe programy użytkowe i przekierowania strumieni danych

 1. W  `/Users/Student/<login>/` **utworzyć podkartotekę `redir` i w niej wykonać kolejne kroki zadania** z użyciem podanych konsolowych programów użytkowych.
 
 1. `echo`: Utworzyć plik `user` zawierający linię w formacie `USER: <login>` a następnie dopisać do pliku kolejną linię w formacie `GROUP: <numer grupy laboratoryjnej>`.

 1. `less`: Odnaleźć w pliku `/etc/passwd` linię zawierającą opis administratora `root`, po czym przekopiować ją z terminala i dopisać poleceniem     `echo` jako kolejną linię pliku `user`.

 1. `cat`: Połączyć zawartość plików `/etc/passwd` oraz `/etc/group` w jeden plik o nazwie `system`, po czym utworzyć jego kopię zawierającą numery linii na początku (opcja `-n`) w pliku pod nazwą `system_numbers`.

 1. `head, tail`: Zapisać dwie pierwsze linie pliku `system` do nowego pliku `system2`, a następnie dopisać dwie ostatnie linie pliku `system` do `system2`.

 1. `sort, uniq, wc`: Uporządkowaną alfabetycznie listę wszystkich linii występujących w obydwu plikach `system` (**NIE `system_numbers`**) oraz `system2` zapisać w pliku `lines.sorted`, a ich ilość (bez powtórzeń) w pliku `lines.nr` (drugie podzadanie można rozwiązać, korzystając z polecenia `sort` z odpowiednią opcją w połączeniu z `wc` lub łącząc 3 wymienione polecenia. Co prawda liczbę linii bez powtórzeń można wydedukować bez używania pliku `lines.sorted`, ale chodzi tutaj o przetestowanie umiejętności usuwania duplikatów z posortowanej listy ).

 1. `curl, wc`(z odpowiednią opcją) : za pomocą polecenia `curl`, ściągnąć zawartość tego samego linku, co na zajęciach nr 2 (z podanego poniżej     adresu) i **nie zapisując jej na dysku** -- policzyć ile znaków wchodzi w skład tej zawartości. Wynik -- czyli liczbę znaków -- zapisać proszę pod nazwą `thing_nchar.txt`.

    -  `https://raw.githubusercontent.com/p100mma/uwb_sysop/main/II/thing`

 1. Wszystkie kolejne polecenia niezbędne do wykonania całego zadania należy umieścić w pliku tekstowym o nazwie `pipeline.txt`:

     - komenda `history -a pipeline.txt` zapisze CAŁĄ historię od momentu rozpoczęcia sesji (stąd prosiłem o wylogowanie)

     - powyższa komenda ma ułatwić Państwu zadanie, aby nie pisać "z palca" wszystkich poleceń jeszcze raz. Zalecam kontrolnie sprawdzić, czy plik zawiera wszystko, co potrzeba.

     - Komentarze proszę ewentualnie dodawać poprzedzone symbolem `#`

 Plik `pipeline.txt` proszę przesłać [na tą stronę, co wcześniej](https://alioth.uwb.edu.pl/so-lab/)
