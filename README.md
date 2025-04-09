# CeneoScrapper


## Kod produktu do testów
84514582


## Algorytm pobierania opinii o produkcie z serwisu Ceneo.pl


1. Wysłanie żądania dostępu do strony internetowej z opiniami o produkcie
1. Jeżeli operacja zakończy się powodzeniem pobieramy dane html ze strony
1. Dla każdej opinii wyodrębnienie danych i przypisanie ich do struktury danych
1. Rozdzielenie danych na pojedyncze elementy (obiekty/słowniki)
1. Wyświetlenie przygotowanych informacji na stronie
1. Jeżeli istnieje kolejna strona z opiniami, przejście do niej i powtórzenie kroków 1-4
1. Zapisanie wyników do bazy danych


## Struktura opinii w serwisie Ceneo.pl
|składowa|zmienna|selektor|
|----------|----------|----------|
|opinia|review|div.js_product-review:not(.user-post--highlight)|
|id opinii|review_id|.review_id[data-entry-id]|
|autor|author|span.user-post__author-name|
|rekomendacja|recommend|span.user-post__author-recomendation > em|
|l. gwiazdek|stars|span.user-post__score-count|
|treść|content|span.user-post__text|
|liczba zalet|pros|div.review-feature__item--positive|
|liczba wad|cons|div.review-feature__item--negative|
|ile os. uznało za przydatną|useful|button.vote-yes > span|
|ile os. uznało za nieprzydatną|unuseful|button.vote-no > span|
|data wystawienia opinii|post_date|span.user-post__published > time:nth-of-type(1)['datetime']|
|data zakupu produktu|purchase_date|span.user-post__published > time:nth-of-type(2)['datetime']|