# Systemy operacyjne - lab nr 10

## Obsługa procesów

1. Napisz skrypt `minion.sh`, który przyjmuje 2 argumenty:
    - częstotliwość wysyłania komunikatów - parametr nr 1, zwany dalej `freq`
    - liczbę komunikatów do wysłania - parametr nr 2, zwany dalej `n_msg`

Skrypt powinien od momentu uruchomienia dopisywać do pliku `minion-PID` wiadomość `I am alive` oraz bieżącą datę, co `freq` sekund i łącznie `n_msg` razy, gdzie `PID` jest zastąpione numerem ID procesu wykonującego daną instancję programu.  Przykładowe przedstawienie chronologiczne dla `freq=4` oraz `n_msg=3`:

    1. Uruchomienie skryptu poprzez proces z `PID=666`

    2. stworzenie pliku `minion-666` z bieżącą datą oraz wiadomością.

    3. mijają  4 sekundy.

    4. dopisanie do `minion-666` bieżącej daty i wiadomości.

    5. mijają  4 sekundy.

    6. dopisanie do `minion-666` bieżącej daty i wiadomości.

    7. mijają  4 sekundy.

    8. dopisanie do `minion-666` bieżącej daty i wiadomości.

    9. koniec działania procesu z `PID=666`.

2. Napisz skrypt `killer.sh`, który zabije wszystkie procesy wykonujące program o nazwie `minion.sh`, ale przed tym poda ich liczbę.

1. Napisz skrypt `keeper.sh`, przyjmujący 3 parametry (od razu piszę umowną nazwę kolejnych parametrów pozycyjnych):
    - `n_children` - liczba podprocesów do uruchomienia przez `keeper.sh`,
    - `freq_sub` - częstotliwość tworzenia podprocesów ,
    - `n_msg` - dwa ostatnie parametry dla do przekazania dla podprocesów, o podobnej interpretacji jak w punkcie nr 1.

`keeper.sh` powinien co `freq_sub` sekund tworzyć podproces wykonujący program `minion.sh` z parametrem `n_msg` równym `n_msg` (wszystkie mają wysłać tyle wiadomości, ile podał użytkownik jako parametr nr 3 do `keeper.sh`) oraz parametrem `freq` równym `freq_sub*j`, gdzie `j` to numer kolejnego wykonywanego podprocesu. Program `keeper.sh` powinien tworzyć te podprocesy do momentu utworzenia `n_children` podprocesów. Następnie, program powinien zaczekać, aż wszystkie podprocesy zakończą swoją pracę i w momencie odnotowania zakończenia danego podrocesu- powinien dopisać do pliku `necro` datę odnotowania zdarzenia zakończenia danego podprocesu oraz jego numer PID, przedzielone spacją. Jak każdy podproces zakończy działanie - program ma usunąć wszystkie pliki `minion-PID`, dla każdego `PID` będącego ID podprocesu utworzonego przez `keeper`a.

Przykład ostatniego zadania, tak jak pierwszego:

    1. Program `keeper.sh` jest uruchomiony z określonymi parametrami `n_children=3, `sub_freq=3`, `n_msg=2`.

    2. `keeper.sh` tworzy podproces wykonujący `minion.sh` z parametrem `freq=3` oraz `n_msg=2`. Przydzielono mu `PID=111`.

    3. mijają 3 sekundy.
    
    4. `keeper.sh` tworzy podproces wykonujący `minion.sh` z parametrem `freq=6`  oraz `n_msg=2`. Przydzielono mu `PID=222`.
    
    5. mijają 3 sekundy.
    
    6. `keeper.sh` tworzy podproces wykonujący `minion.sh` z parametrem `freq=9` oraz `n_msg=2`. Przydzielono mu `PID=333`.
    
    7. Program `keeper.sh` czeka po kolei na wszystkie utworzone podprocesy.
    
    8. Jak podproces z `PID=111` zakończy pracę, tworzony jest plik `necro` z datą oraz numerem `111` w pierwszej linijce.
    
    9. Jak podproces z `PID=222` zakończy pracę, do pliku `necro` dopisywana jest nowa linijka z datą oraz numerem `222`.
    
    10. Jak podproces z `PID=333` zakończy pracę, do pliku `necro` dopisywana jest nowa linijka z datą oraz numerem `333`.
    
    11. Po zakończeniu działania wszystkich podprocesów, program `keeper.sh` usuwa wszystkie pliki z wiadomościami od poprocesów, czyli `minion-111`, `minion-222`, `minion-333`. 
    
    12. `keeper.sh` kończy działanie.

**Wskazówka:** Instrukcja `wait PIDofSomeProcess` pozwala na zastopowanie działania skryptu do momentu zakończenia działania podprocesu skryptu z numrem `PIDofSomeProcess`. Nie trzeba robić nieskończonych pętli i zabijać podprocesów. 

Jako rozwiązanie proszę przesłać archiwum `tar` ze skryptami `killer.sh`, `minion.sh` oraz `keeper.sh` i przesłać [na tą samą stronę, co wcześniej](https://alioth.uwb.edu.pl/cgi-bin/so-lab/rejestr).
