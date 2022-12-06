# Systemy operacyjne - lab nr 9

## Skrypty cz.2 i działania arytmetyczne

Programy mają liczyć proste działania arytmetyczne. Jako wynik, można wyświetlić wartość liczbową na standardowe wyjście.

1. Proszę stworzyć skrypt dla interpretera `bash` wykonujący działania arytmetyczne na 2 liczbach, przyjmujący jako arugmenty te dwie liczby oddzielone białymi znakami, poprzedzone nazwą opcji:
    - `-a` -- dodawanie (`a`ddition),
    - `-s` -- odejmowanie (`s`ubstraction),
    - `-m` -- mnożenie (`m`ultiplication),
    - `-d` -- dzielenie (`d`ivision).
Dopuszczamy, że program przyjmie więcej niż 2 liczby, ale nadwyżkę zignoruje.

1. Proszę dodać do programu opcję `-f`, oznaczającą silnię (`f`actorial). Program w tej opcji ma obliczyć silnię liczby, jaka została podana do skryptu jako parametr nr 2. Można założyć, że użytkownik nie będzie zbyt nieprzewidywalny i jako dane wejściowe poda liczbę naturalną. Można założyć, że `!0=1`.

1. Proszę dołożyć obsługę błędów, sprawdzającą liczbę parametrów podanych przez użytkownika w zależności od podanej opcji:

	- jeżeli użytkownik poda `-f` jako parametr nr 1, program ma sprawdzić, czy podana liczba parametrów nie jest mniejsza od 2,
	- jeżeli użytkownik poda jako parametr nr 1 opcje z 1-go punktu zadania, program ma sprawdzić, czy podana liczba parametrów nie jest mniejsza od 3,

	- jeżeli któryś z warunków się spełni, program ma nie wykonywać działań arytmetycznych, zakończyć działanie, wyświetlić komunikat np. "niepoprawna liczba parametrów" i zwrócić `exit_status` większy od zera.

1. Jeśli użytkownik poda parametry w jakikolwiek inny sposób niż było wskazane wcześniej, program ma zwrócić krótki komunikat informujący o poprawnym sposobie użytkowanai skryptu. 

1. Proszę stworzyć program, który będzie wykonywał powyższe działania oraz dopuszczał tryb interaktywny za pomocą opcji `-i`, w którym użytkownik może podawać parametry opisujące tryb wykonywania działań oraz argumenty liczbowe do momentu podania słowa klucz `STOP`. Ostatecznie program powinien:
    - działać tak jak program poprzedni, w przypadku podaniu opcji `-a, -s, -d, -m`, `-f` łącznie z przekazywaniem komunikatów i kodów `exit status`,
    - pozwalać na zastosowanie dodatkowej opcji `-i`, w której ww. działania będą wykonywane na podstawie danych wejściowych użytkownika. Praca w trybie interaktywnym powinna wyglądać tak:	
    1. Po wywołaniu skryptu z opcją `-i`, np. `.\skrypt.sh -i`, program przechodzi do trybu interaktywnego.
    1. Program wyświetla komunikat, jakie działania użytkownik może podjąć i jak ma podać dane wejściowe.
    1. Program pobiera dane wejściowe.
    1. Jeżeli dane wejściowe to nie `STOP`, program wykonuje działania tak, jakby podać mu te dane z wiersza poleceń (np. `\skrypt.sh -a 1 2`), wyświetla wynik i wraca do punktu nr **ii**.
    1. Jeżeli dane wejściwowe to `STOP`, to program kończy działanie.
    - Obsługa błędów w trybie interaktywnym powinna działać jak wcześniej, program ma wyświetlić komunikat adekwatny do danej sytuacji (zła liczba parametrów lub info o użytkowaniu) i czekać na dalsze dane wejściowe. Idealnie by było, jakby końćowy exit status skryptu w trybie interaktywnym był równy kodowi błędu ostatnio wykonanej operacji arytmetycznej (domyślnie 0, chyba że wyłapiemy jakiś błąd). 
**Wskazówka:** Można zrobić nowy skrypt, który wywołuje skrypt wcześniej napisany. Można spróbować zwrócić `exit status` ostatnio wykonanej operacji przez program, korzystając z pomocniczej zmiennej, przechowującej wartość parametru `?` tuż po uruchomieniu skryptu wykonującego działania arytmetyczne.

Rozwiązaniem powinien być skrypt lub skrypt i wszystkie inne potrzebne pliki spakowane do archiwum `.tar`. Proszę przesłać [na tą samą stronę, co wcześniej](https://alioth.uwb.edu.pl/cgi-bin/so-lab/rejestr)
