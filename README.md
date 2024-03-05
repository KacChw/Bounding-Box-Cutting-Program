# Bounding-Box-Cutting-Program
The program is used to locate, cut out and remove the background around a selected object in the image. For this purpose, it uses simple image operations using the OpenCV library.
Program służy do lokalizacji, wycięcia i usunięcia tła dookoła wskazanego obiektu na obrazie. Wykorzystuje do tego bibliotekę PIL (Python Imaging Library) oraz operacje na obrazie za pomocą biblioteki numpy.![london](https://github.com/KacChw/Bounding-Box-Cutting-Program/assets/106623070/5bef4e3f-99fe-4594-b546-7b115019c96f)

![result](https://github.com/KacChw/Bounding-Box-Cutting-Program/assets/106623070/6dfe42b2-0343-484d-992e-99d6553a6ffc)

Kroki działania programu:
Lokalizacja i wycięcie obiektu:
![najwiekszy_ed](https://github.com/KacChw/Bounding-Box-Cutting-Program/assets/106623070/dc697fc9-8bb8-4553-a059-3d89df906e5f)

Program znajduje różnicę między dwoma obrazami (oryginalnym i edytowanym).
Tworzony jest bounding box wokół największego obszaru różnic, reprezentujący obiekt na obrazie.
Wycinany jest obszar obrazu odpowiadający wykrytemu bounding box'owi.
Usunięcie tła:
![najwiekszy_ed_bez_tla](https://github.com/KacChw/Bounding-Box-Cutting-Program/assets/106623070/aaa8b629-2662-4463-8aaa-0d71374aaaae)

Usuwanie tła odbywa się poprzez segmentację obrazu na podstawie różnic między obrazami.
Na podstawie wyznaczonej maski, tło zostaje zamienione na przezroczystość, zachowując tylko obszar z obiektem.
Zapisanie obrazu bez tła:
![result](https://github.com/KacChw/Bounding-Box-Cutting-Program/assets/106623070/7a0c328b-a770-4a0f-9df6-6a6a5824ceb0)

Ostateczny obraz z wyciętym bounding box'em bez tła zostaje zapisany w formacie PNG.
Funkcje programu:
wycnanie(original_path, edited_path, min_rozm_ramki): Funkcja przeprowadzająca proces lokalizacji, wycięcia i usunięcia tła obiektu na podstawie dwóch obrazów. original_path to ścieżka do oryginalnego obrazu, edited_path to ścieżka do obrazu po edycji, min_rozm_ramki to minimalna wielkość obszaru bounding box'a, aby został uznany za obiekt.
czesc_wspolna(image_path1, image_path2, output_path): Funkcja usuwająca tło dookoła obiektu z dwóch wyciętych obrazów i zapisująca rezultat w formie obrazu PNG.
Sposób użycia:
Podaj ścieżki do oryginalnego i edytowanego obrazu oraz minimalną wielkość ramki.
Wywołaj funkcję wycnanie z odpowiednimi parametrami.
Następnie użyj funkcji czesc_wspolna, podając ścieżki do wyciętych obrazów.
Program wygeneruje obraz z wyciętym bounding box'em bez tła i zapisze go pod wskazaną ścieżką.
Uwagi:
Program może wymagać dostosowania parametrów (np. wartości progowej dla detekcji różnic), aby uzyskać optymalne wyniki dla różnych obrazów i scenariuszy.
W przypadku obrazów o dużej złożoności tła lub obiektów o podobnych kolorach do tła, wyniki detekcji mogą być mniej precyzyjne i wymagać dodatkowej obróbki.
