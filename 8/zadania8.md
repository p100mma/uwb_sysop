
# Systemy operacyjne- lab nr 8

## Skrypty powłoki  

1. W zadaniu trzeba będzie stworzyć skrypt dla powłoki, wydobywający określone informacje z pliku [xinetd.log](https://alioth.uwb.edu.pl/so/data/xinetd.log). Poszczególne polecenia rozbudowują jego funkcjonalności. Możemy założyć, że plik jest obecny w folderze, w którym znajduje się skrypt (zatem aby skrypt przetestować, trzeba ten plik pobrać :) ) 

1. Niech skrypt wyświetli na standardowe wyjście czasy oraz nr IP w formacie `[godz:min:sek] nrIP`, w których odnotowano połączenia FTP w okresie sierpnia 2016 (2016-08).

1. Niech skrypt pobiera od użytkownika 3 parametry w linii polecenia: kolejno rok, miesiąc i nazwę pliku. Niech skrypt realizuje zadania z punktu poprzedniego, ale dla tych 3 wartości, które określa użytkownik, tj. wyświetli informacje o czasach i nr-ach IP wg określonego wyżej formatu połączeń FTP w miesiącu i roku podanym przez użytkownika (parametry nr 1 i 2), pobranych z pliku o nazwie, którą określi użytkownik w parametrze nr 3.

1. Niech skrypt oprócz wyświetlenia ww. danych na standardowe wyjście, zapisze je w pliku `times.txt`.

1. Niech skrypt sygnalizuje błędne wykonanie za pomocą zwracanego kodu (tzn. `exit status`). W przypadku, gdy użytkownik nie poda wszystkich 3 parametrów z punktu 3, wartość zwracanego kodu ma być równa `3` i skrypt ma wyświetlić komunikat 'Invalid input parameters' (i nie wykonywać dalszych obliczeń). Jeśli plik, którego nazwa została podana jako parametr nr 3 nie istnieje, skrypt ma zwrócić kod równy `4` i wyświetlić komunikat `input file does not exist`.  **Wskazówka:** Specjalny parametr powłoki `?`, zawiera `exit status` ostatnio uruchomionej komendy.

1. Jako rozwiązanie trzeba przesłać archiwum `log.tar`, zawierające:
	- skrypt,
	- plik z danymi `xinetd.log`,
	- wygenerowany plik `times.txt` powstały w wyniku testowego uruchomienia skryptu na parametrach: rok=2016, miesiąc=8, nazwa pliku=`xinetd.log`.

Zadanie przesłać proszę [na tą stronę, co wcześniej](https://alioth.uwb.edu.pl/so-lab/). Skrypt ma korzystać z interpretera `sh`.
