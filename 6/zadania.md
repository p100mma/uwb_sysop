
# Systemy operacyjne- lab nr 6
## Wyrażenia regularne i ekspansje powłoki

1. Jeżeli komputer był włączony, proszę się wylogować i zalogować ponownie.

1. Proszę pobrać plik `error_log` [z tego adresu](http://alioth.uwb.edu.pl/so/data/error_log) i umieścić w folderze `/Users/Student/<login>/grep_assignment/`. Wszystkie zadania proszę zrobić w tym folderze.

1. Za pomocą narzędzia `grep`, proszę zapisać w pliku `error_lines`: linie w pliku `error_log`, które zaczynają się od `E`. 

1. Za pomocą narzędzia `grep`, proszę zapisać w pliku `info_lines`: linie w pliku `error_log`, które zaczynają się od `I`. 

1. (to najlepiej zrobić na koniec) Proszę za pomocą połączenia narzędzia `grep` oraz innego, wybranego narzędzia powłoki:

    - odnaleźć pliki w folderze /usr/bin, do których użytkownik ma uprawnienia odczytu, zapisu jak i uruchamiania, a wszyscy inni ("inni" jak i grupa posiadająca uprawnienia do pliku) mają uprawnienia: odczytu, uruchamiania, ale nie zapisu,

    - listę tych plików **z dołączonymi numerami linii** proszę zapisać w pliku `bin_ur-x_list.txt`. *Najważniejsze będzie uzyskanie porządanego wyniku określonego w poprzednim zdaniu polecenia. Można wykorzystać *`ls -l`*,* `cat` *z odpowiednią opcją, operator przekierowania pipeline* `|` *, ale można to zrobić na inne sposoby.*

1. Proszę spakować do archiwum `my_archive.tar` wszystkie pliki z `/usr/bin`, **których nazwy** spełniają następujące kryteria:

    - zaczynają się od 3-ciej litery loginu użytkownika, **LUB**,

    - druga litera w nazwie to druga litera loginu użytkownika.

1. Jako rozwiązanie należy przesłać plik `grep.txt`, [na tą samą stronę, co wcześniej](https://alioth.uwb.edu.pl/cgi-bin/so-lab/rejestr):

    - plik ma zawierać wszystkie polecenia potrzebne do rozwiązania zadania (można użyć komendy `history -a grep.txt`, która do pliku `grep.txt` dopisze historię od momentu zalogowania, lub go utworzy, jeśli on nie istnieje)

