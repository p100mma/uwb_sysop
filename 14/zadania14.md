
# Systemy operacyjne - lab nr 14

## Tworzenie interaktywnego instalatora

1. Na pocżatku, należy przygotować kod źródłowy w języku C jednego z programów poniżej, rozszerzających podstawowe narzędzie powłoki `seq` (do wyboru):
	- program `deg_seq`, rozszerzający funkcjonalność programu `seq` na przypadek definiowania sekwencji stopni (jak w mierzeniu kątów, od 0 do 360 stopni). 		- Przykładowo, zwykły program `seq` dla wywołania `seq 90 60 540`, zwróci liczby `90 150 210 270 330 390 450 510`, program `deg_seq` ma zwrócić `90 150 210 270 330 30 90 150`. 
		- Tutaj powinna być możliwość podania jednego, dwóch lub trzech argumentów, jak w normalnym programie `seq`. Dla uproszczenia - program ma wydrukować każdą liczbę od nowej linijki, bez wyboru separatora.
	- program `range`, przyjmujący (dla uproszczenia) zawsze 3 parametry: `START`, `STOP`, `N`. Pierwsze dwa z nich to liczby rzeczywiste (może być `float`, dla uprosczenia, większe równe zero), `N` to dodatnia liczba całkowita. Program `range` ma wydrukować listę `N` liczb równomiernie rozłożonych pomiędzy `START` i `STOP`. Pierwsza drukowana liczba zawsze powinna być liczbą `START`, ostatnia zawsze liczbą `STOP`, środkowe liczby listy mają być oddalone o `(STOP - START)/N`. Można założyć, że `STOP > START`. Można wydrukować z precyzją np. do 6 miejsc po przecinku. **Uwaga:** z powodów błędów numerycznych, ostatnia liczba powstająca w wyniku intuicyjnego algorytmu iteracyjnego dodawania różnicy `(STOP - START)/N` może przewyższyć wartość `STOP`.
 
1. Stworzyć skrypt-instalator `my_installer`, 	który będzie korzystał z programu `dialog`, aby przeprowadzić instalację, to jest:
	- przestawi treść typu `README` jako okno informacyjne (`textbox`),
	- po zatwierdzeniu kontynuacji przez użytkownika -- pobierze od użytkownika dane: ścieżkę do miejsca, gdzie program ma być zainstalowany,
	- przeprowadzi w miarę kompletną instalację wybranego programu z punktu 1-go, w określonej wcześniej lokalizacji:
		- trzeba dokonać kompilacji kodu źródłowego za pomocą kompilatora np. `gcc`,
		- umieścić skompilowany plik wykonywalny we wskazanej lokalizacji,
		- dodać ścieżkę do folderu zawierającego ww. plik wykonywalny do zmiennej środowiskowej `PATH` (umownie: nie zmieniamy tak jak należy treści pliku `.bashrc` lub `zshrc`)
		- ustalić dla pliku wykonywalnego TYLKO następujące uprawnienia: odczytu i zapisu, TYLKO dla właściciela (usera instalującego) oraz grupy użytkownika instalującego program (czyli po prostu dla pola uprawnień group). wszystkie inne uprawnienia mają być wyzerowane. 


Jako rozwiązanie trzeba przesłać skompresowane archiwum `zaj14.tar.gz` zawierające pliki: `my_installer`, `README` oraz skompilowany program;  [na tą samą stronę, co wcześniej](https://alioth.uwb.edu.pl/cgi-bin/so-lab/rejestr).
