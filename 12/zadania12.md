
# Systemy operacyjne - lab nr 12

## Zlecanie zadań do systemów kolejkowych cz. II

1. Na zajęciach trzeba będzie stworzyć w plikach `cronjob1` oraz `cronjob2` zadania (skrypty powłoki) do zlecenia do kolejki dla demona (`daemon`) `cron`, a potem opisać w pliku `README` sposób uruchomienia tych zadań poprzez `cron` o określonych porach.

1. Skrypt `cronjob1` ma zapisać całą zawartość folderu **'/Users/student/LOGIN'** do archiwum `/tmp/LOGIN-DATA.tar`, gdzie:

	- `LOGIN` zastąpiony ma być loginem na serwer alioth,

	- `DATA` ma być zastąpione dzisiejszą datą (np. wynikiem komendy `date`)

1. Skrypt `cronjob2` ma zapisać do pliku `/Users/student/LOGIN/prog_size` średnią wielkość plików z folderu **`/Users/student/`**, które mają poziom uprawnień pozwalający na **conajmniej uruchamianie jako skrypt wykonywalny (executable), w dowolnej grupie uprawnień (uprawnienia ownera, grupy, lub innych)**. Można wykorzystać komendę `find` i opcję `-perm`, w połączeniu z `-exec` i `stat` (jak na poprzednich zajęciach), i potem policzyć średnią. Jeśli uda się policzyć w formacie liczb rzeczywistych oraz wszystko inne będzie działać OK - będą 4 punkty, inaczej 3.
 

1. Proszę napisać w pliku `README` oczekiwaną zawartość pliku typu `crontab`, który pozwoli na uruchomienie skryptów o określonych porach:

- `cronjob1` - o 11:15 w każdą środę,

- `cronjob2` - co pół godziny w trzecim dniu pierwszego miesiąca każdego kwartału.

Jako rozwiązanie trzeba przesłać archiwum `cronjobs.tar` zawierające pliki `cronjob1`, `cronjob2` oraz `README` [na tą samą stronę, co wcześniej](https://alioth.uwb.edu.pl/cgi-bin/so-lab/rejestr)
