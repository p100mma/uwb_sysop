
# Systemy operacyjne- lab nr 5

## Programy do kompresji i archiwizacji

 1. Jeżeli komputer był włączony, proszę się wylogować i zalogować ponownie.

 1. W  `/Users/Student/<login>/` **utworzyć podkartotekę `files` i w niej wykonać kolejne kroki zadania**. 
 
 1. Pobrać archiwum `LOGIN.tar` z poniższego linku (lub z repozytorium z treścią zadań) i umieścić w ww. folderze `files`. **`LOGIN` należy zamienić na swój login, np. `piosto.tar`**: 

    -  `https://raw.githubusercontent.com/p100mma/uwb_sysop/main/5/LOGIN.tar`

 1. Za pomocą programu `tar`, proszę rozpakować archiwum.

 1. W `files` stworzyć proszę folder `pack` i skopiować do niego zawartość archiwum wypakowanego w poprzednim punkcie (czyli plik `LOGIN.txt`, gdzie j.w. `LOGIN` trzeba zastąpić swoim loginem). Następnie, należy odnaleźć pierwszy według porządku alfabetycznego plik w `/usr/bin`, którego nazwa rozpoczyna się od pierwszej litery zawartej w wypakowanym wcześniej pliku `LOGIN.txt`. Odnaleziony plik proszę też skopiować do folderu `/Users/Student/<login>/files/pack/`. 

 1. Proszę utworzyć kopię zapasową `pack` np. nazwaną `pack2`. Następnie, proszę utworzyć archiwum za pomocą programu `tar`, nazwane `pack.tar`, zawierające folder `pack` oraz jego zawartość. Po utworzeniu archiwum, proszę usunąć folder `pack` oraz odwtorzyć jego zawartość za pomocą stworzonego wcześniej archiwum `pack.tar`. W przypadku pomyłki, proszę podmienić kopię zapasową `pack2` na `pack` i zrobić zadanie ponownie.  
 
 1. Proszę utworzyć kopię zapasową `pack` np. nazwaną `pack2`, jeśli jej nie utworzono wcześniej. Tak samo, proszę stworzyć kopię zapasową pliku `LOGIN.txt`. Następnie, za pomocą programu `cpio`, proszę utworzyć 2 archiwa i wykonać analogiczne czynności, jak wyżej: 

	- archiwum `pack.cpio`, zawierające TYLKO folder `pack` (wraz z zawartością!)

	- archiwum `LOGIN.cpio`, zawierające TYLKO plik `LOGIN.txt`.

	- Po utworzeniu archiwów, proszę usunąć folder `pack` oraz plik `LOGIN.txt` oraz odwtorzyć je za pomocą stworzonych wcześniej archiwów `pack.cpio` oraz `LOGIN.cpio`. W przypadku pomyłki, proszę podmienić kopie zapasowe `pack` oraz `LOGIN` i zrobić zadanie ponownie.  
 
 1. Proszę skompresować archiwum `pack.tar` za pomocą `gzip`.
 

 1. Proszę stworzyć skompresowane archiwum `pack.tgz`, zawierające tą samą zawartość, co `pack.tar`, ale tylko za pomocą narzędzia `tar`. **Wskazówka:** trzeba podać odpowiednią opcję przy tworzeniu archiwum, hasło do wyszukania w manualu narzędzia `tar` to `compress`). 
 
 1. Proszę w folderze `files` utworzyć folder `symlinks`. Potem, proszę stworzyć łącze symboliczne do folderu `pack` w ramach `symlinks`, nazwane `link_pack`, tzn: łącze `/Users/Student/<login>/files/symlinks/link_pack` ma wskazywać na `/Users/Student/<login>/files/pack`. Potem, w ramach folderu `files`, proszę stworzyć archiwum `link_pack.tar`, podając jako zawartość utworzone wcześniej łącze symboliczne, ale w taki sposób, aby archiwum zawierało oryginalny folder `pack`, a nie łącze symboliczne (**Wskazówka**: trzeba podać komendzie `tar` specjalną opcję, hasło do wyszukania w manualu `tar` to `links`. Jeśli uda się stworzyć jedną komendą archiwum w folderze `files`, zawierające folder `pack` z wykorzystaniem łącza symbolicznego oraz **nie zawierające** nadrzędnego `symlinks`, do oceny końcowej za dzisiaj doliczę dodatkowy punkt). 
 
 1. Wszystkie kolejne polecenia niezbędne do wykonania całego zadania należy umieścić w pliku tekstowym o nazwie `files.txt`, umieszczonym w folderze `files` (czyli `\Users\Student\<login>\files\files.txt`:

     - komenda `history -a files.txt` wywołana w `\Users\Student\<login>\files`  zapisze CAŁĄ historię od momentu rozpoczęcia sesji (stąd prosiłem o wylogowanie)

     - powyższa komenda ma ułatwić Państwu zadanie, aby nie pisać "z palca" wszystkich poleceń jeszcze raz. Zalecam kontrolnie sprawdzić, czy plik zawiera wszystko, co potrzeba.

     - Komentarze proszę ewentualnie dodawać poprzedzone symbolem `#`

1. PRZED PRZESŁANIEM rozwiązania, proszę wykonać polecenia:

- `ls -lRsh files >> files/files.txt` z poziomu folderu `/Users/Student/<login>/`.

- `tar -tvf link_pack.tar >> files.txt` z poziomu folderu `/Users/Student/<login>/files`.

 Plik `files.txt` proszę przesłać [na tą stronę, co wcześniej](https://alioth.uwb.edu.pl/so-lab/)
