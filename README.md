# CeneoScrapper


## Kod produktu do testów
84514582


## Algorytm pobierania opinii o produkcie z serwisu Ceneo.pl


1. Wysłanie żądania dostępu do strony internetowej z opiniami o produkcie
1. Zakładając powodzenie połączenia pobieramy dane html ze strony
1. Segregacja tylko danych o opiniach na podstawie znaczników html
1. Rozdzielenie danych na pojedyncze elementy (obiekty/słowniki)
1. Wyświetlenie przygotowanych informacji na stronie
1. Przejście do kolejnej strony opinii jeśli istnieje
1. Zapisanie danych do bazy danych


## Struktura opinii w serwisie Ceneo.pl
|składowa|zmienna|selektor|
|----------|----------|----------|
|opinia|review|.js-product__review|
|id opinii|review_id|.review_id[data-entry-id]|
|autor|author|.user-post__author-name|
|rekomendacja|recommend|span.user-post_author-recomendation > em|
|l. gwiazdek|stars|.user-post__score-count|
|treść|content|.user-post__text|
|liczba zalet|pros|.review-feature__item--positive|
|liczba wad|cons|.review-feature__item--negative|
|ile os. uznało za przydatną|useful|button.vote-yes > span|
|ile os. uznało za nieprzydatną|unuseful|button.vote-no > span|
|data wystawienia opinii|post_date|.user-post__published > time:nth-of-type(1)['datetime']|
|data zakupu produktu|purchase_date|.user-post__published > time:nth-of-type(2)['datetime']|