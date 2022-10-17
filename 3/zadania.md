
# Systemy operacyjne- lab nr 3
## Systemy plików

1. Jeżeli komputer był włączony, proszę się wylogować i zalogować ponownie.

1. W kartotece domowej (`/Users/Student/<login>/`) utworzyć podkartotekę linki, w niej stworzyć dwie kopie pliku `/etc/passwd` o nazwach `kopia1` i `kopia2` oraz dwa dowiązania do tych kopii: statyczne (twarde) do pierwszej z nich o nazwie hard oraz symboliczne (miękkie) do drugiej o nazwie soft (komenda `ln`)

1. Ustalić prawo dostępu do pliku będącego pierwszą kopią (w sposób symboliczny) tak, aby dostęp do odczytu, zapisu i uruchamiania miał jedynie jego właściciel, członkowie grupy nie mieli żadnych uprawnień, natomiast pozostali użytkownicy systemu mogli go jedynie odczytywać (komenda `chmod`)

1. Ustalić prawo dostępu do pliku będącego drugą kopią (w sposób numeryczny) tak, aby wszyscy użytkownicy systemu mieli dostęp jedynie do odczytu, a poza tym nikt nie miał żadnych innych uprawnień (też `chmod`, ale z wykorzystaniem kodów w bazie 8-kowej)

1. Na poziomie kartoteki domowej utworzyć dowiązanie do kartoteki linki pod nazwą `<login>-lnk` (odpowiedni rodzaj łącza).

1. Wszystkie kolejne polecenia niezbędne do wykonania całego zadania należy umieścić w pliku tekstowym o nazwie `links.txt`:

    - komenda w `history -a links.txt` zapisze CAŁĄ historię od momentu rozpoczęcia sesji (stąd prosiłem o wylogowanie)

    - komentarze proszę ewentualnie dodawać poprzedzone symbolem `#` 

Zadania przesłać proszę przesłać [na tą stronę, co wcześniej](https://alioth.uwb.edu.pl/so-lab/)
