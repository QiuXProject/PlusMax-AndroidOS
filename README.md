PlusMax
Darmowy system na bazie Androida 17, który instaluje się jednym kliknięciem na Windowsie — z własną animacją startu, launcherem i fioletowym motywem.

Bez Linuksa. Bez kompilowania. Bez Android Studio. Bez płacenia.

text

Pobierz paczkę  →  kliknij START-PLUSMAX.bat  →  wybierz 1  →  gotowe
Co to jest — uczciwie
PlusMax to obraz systemu Android 17 od Google uruchamiany w emulatorze, na który instalator nakłada branding:

animację rozruchową i wyłączania,
launcher PlusMax Home (zegar, siatka aplikacji, tapeta),
tapetę i ciemny, fioletowy motyw Default Purple+,
aplikację QiuX Cloud.
To nie jest system napisany od zera i nie jest powiązany z Google. Dokładnie tak samo robi się LineageOS, /e/OS czy GrapheneOS: bierzesz otwarte źródła Androida i dokładasz swoją markę w warstwie systemowej.

Nowego jądra ani nowego stosu aplikacji nie pisze nikt poza Google — i nie jest to potrzebne, żeby mieć własny system.

Co dostajesz
🤖 Android 17	obraz Google, API 37, x86_64 — działa na kartach NVIDIA przez DirectX 11
⚡ Animacja startu	znak plus i napis PlusMax, plus animacja wyłączania
📱 Launcher	PlusMax Home jako domyślny ekran główny, ustawiany automatycznie
🎨 Motyw	ciemny fiolet, #9B4DFF / #0A0713
☁️ QiuX Cloud	Twoje konto TeraBox w jednej aplikacji
Wymagania
System	Windows 10 lub 11, 64-bit
RAM	16 GB zalecane (na 8 GB będzie bardzo wolno)
Dysk	ok. 25 GB wolnego na C:
Procesor	włączona wirtualizacja VT-x w BIOS
Internet	tylko do pierwszego pobrania obrazu
Instalator sam to sprawdzi i przerwie, zamiast zaśmiecać dysk.

Jak uruchomić
Kliknij 
START-PLUSMAX.bat
 i wybierz jedną z dwóch opcji:

[1] ZAINSTALUJ I URUCHOM
Robi wszystko samo: pobiera obraz Androida (2,2 GB, ze wznawianiem), sprawdza sumę SHA-1, rozpakowuje, tworzy wirtualny telefon i uruchamia system z brandingiem.

Pierwsze uruchomienie: 20–40 minut.

[2] UZYJ TEGO, CO JUZ MAM
Sprawdza dysk i bierze to, co już jest — zero pobierania:

obrazy zainstalowane przez Android Studio,
pliki ZIP w folderze Pobrane i na Pulpicie,
poprzednie instalacje PlusMax.
Gotowy obraz z innego SDK jest kopiowany, a nie pobierany od nowa. Jeśli nic nie ma — mówi o tym wprost i kończy.

Jeśli pobieranie się przerwie
Uruchom 
START-PLUSMAX.bat
 jeszcze raz i wybierz 1. Pobieranie dokończy od miejsca przerwania — 20 prób, bez zaczynania od zera. Pobrany plik zostaje w folderze paczki, więc nie przepada.

Co jest w paczce
Wszystko leży w jednym folderze — żadnych podfolderów.

Plik	Do czego

START-PLUSMAX.bat
jedyny plik, który klikasz (dwie opcje)
plusmax-system.ps1	instalator — możesz otworzyć w Notatniku i przeczytać
PlusMaxHome-1.2.0.apk	launcher (podpisany, gotowy)
QiuXCloud-2.0.0.apk	chmura (podpisana, gotowa)
bootanimation.zip	animacja startu
shutdownanimation.zip	animacja wyłączania
PlusMax-NAPRAW-AVD.bat	naprawa, gdy emulator nie widzi telefonu
repair-avd.ps1	to samo co wyżej, bez bat-ki
index.html	strona PlusMax (działa offline)

START-TUTAJ.txt
instrukcja na spokojnie
SUMY-KONTROLNE.txt	SHA-256 każdego pliku

LICENSE.txt
licencja i zastrzeżenia

version.txt
numer wersji
Numer wersji jest też w nazwie paczki: PlusMax BETA 1.4.8 - Emulator.zip.

Chmura QiuX — jak to naprawdę działa
QiuX Cloud to nakładka: otwiera Twoje konto TeraBox w środku własnego interfejsu. Przestrzeń pochodzi z TeraBox (darmowe 1 TB przy rejestracji), nie od nas.

TeraBox nie ma publicznego API, więc nie da się „przenieść" jego miejsca do PlusMax. Możemy je tylko wygodnie pokazać.

PlusMax nie widzi Twoich plików ani hasła. Logujesz się bezpośrednio u TeraBox.

Na telefon zamiast emulatora
Podłącz telefon kablem USB, włącz Debugowanie USB i uruchom:

PowerShell

powershell -ExecutionPolicy Bypass -File plusmax-system.ps1 -PhoneOnly
Uczciwie: bez roota podmieni się launcher, tapeta i aplikacje. Animacja startu zostanie tylko na emulatorze — Android nie pozwala jej zmienić bez roota.

Gdy coś nie działa
Objaw	Co zrobić
Unknown AVD name [PlusMax]	uruchom PlusMax-NAPRAW-AVD.bat
Czarny ekran emulatora	dodaj -Gpu swiftshader_indirect do polecenia emulatora
„Obraz systemu jest niekompletny"	usuń urwany .zip, uruchom 1 ponownie
Pobieranie stoi	uruchom ponownie — wznowi od miejsca przerwania
System bardzo wolny	sprawdź, czy VT-x jest włączone w BIOS
Logi emulatora: %TEMP%\plusmax-emulator-*.log

Bezpieczeństwo
Windows SmartScreen będzie ostrzegał — plik nie ma płatnego podpisu cyfrowego (certyfikat kosztuje kilkaset złotych rocznie). To normalne dla darmowych narzędzi.

„Windows Ochronił Twój komputer" → Więcej informacji → Uruchom mimo to
Defender usunął plik → Ochrona przed wirusami → Historia ochrony → Przywróć
Skrypt nie wysyła nigdzie Twoich danych i nie instaluje nic w tle. Cały kod instalatora jest w plusmax-system.ps1 — możesz go przeczytać.

System działa w emulatorze, czyli w odizolowanej maszynie wirtualnej. Twój Windows, pliki i przeglądarka pozostają nietknięte.

Licencja
MIT — szczegóły w 

LICENSE.txt
.

W skrócie: możesz używać, zmieniać i udostępniać kod, o ile zostawisz notkę copyright.

Czego licencja nie obejmuje:

obrazu systemu Android — należy do Google, instalator go nie rozpowszechnia, tylko pobiera z serwerów Google na Twoje polecenie,
usługi TeraBox — należy do Flextech Inc.,
znaku słownego „Android" — należnego Google, używanego tu wyłącznie opisowo.
Nazwa PlusMax i logo nie są objęte licencją MIT.

Status
BETA. Numer wersji w nazwie paczki i w 
version.txt
. Lista zmian na stronie PlusMax w sekcji „Patche".

Kod źródłowy instalatora, launchera i QiuX Cloud jest w tym repozytorium:

text

apps/         launcher i QiuX Cloud (źródła + gotowe APK)
branding/     logo, ikona, tapeta, motyw
config/       nazwa marki, wersja, kolory
device/       animacje rozruchu i wyłączania
scripts/      instalator dla Windows, naprawa AVD
site/         strona produktowa (jeden plik HTML)
tools/        buildery paczki i strony
docs/         dokumentacja techniczna, w tym plan kompilacji AOSP
Pełna kompilacja AOSP (własne obrazy systemu zbudowane od zera) jest opisana w 

README-DEWELOPERSKIE.md
 — wymaga Linuksa, 32–64 GB RAM i kilku godzin. Do uruchomienia PlusMax nie jest potrzebna.
