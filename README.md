# Kredyt Kompas — strona pośrednika kredytowego

Kompletna strona firmowa dla pośrednika kredytowego: prezentacja oferty, kalkulator zdolności kredytowej i ścieżka kontaktu. **Statyczny HTML, CSS i vanilla JS** — bez frameworków, bez build-stepu, bez bazy danych.

▶️ **[Zobacz stronę na żywo](https://krzysiek2115op.github.io/kredyt-kompas-demo/)**

## Co zawiera

| Podstrona | Rola |
|---|---|
| `index.html` | Strona główna — oferta, proces współpracy, dowód społeczny |
| `kalkulator.html` | **Kalkulator zdolności kredytowej** liczony w przeglądarce, bez wysyłania danych na serwer |
| `kredyty-hipoteczne.html` | Podstrona ofertowa pod frazę o największym potencjale sprzedażowym |
| `o-nas.html`, `faq.html` | Budowanie zaufania — najczęstsza bariera w usługach finansowych |
| `kontakt.html` | Formularz kontaktowy |
| `polityka-prywatnosci.html` | Wymagana przy przetwarzaniu danych z formularza |
| `nasze-auta.html` | Podstrona demonstracyjna dla [wtyczki IAAI Importer](https://github.com/krzysiek2115op/iaai-importer-demo) |
| `404.html` | Własna strona błędu |

## Decyzje techniczne

**Zero zależności.** Kalkulator, nawigacja i walidacja formularza działają na czystym JavaScript. Nic do zaktualizowania, nic do zepsucia przez breaking change w bibliotece, brak kosztów utrzymania.

**Kalkulator liczy po stronie klienta.** Dane o dochodach i zobowiązaniach nie opuszczają przeglądarki — mniejszy zakres przetwarzania danych osobowych i szybsza reakcja interfejsu.

**SEO i bezpieczeństwo od razu, nie „potem".** `sitemap.xml`, `robots.txt`, nagłówki bezpieczeństwa w pliku `_headers`, własna strona 404.

**Hosting za 0 zł.** Strona stoi na GitHub Pages; w repo jest też `vercel.json`, więc przenosi się na Vercel bez zmiany kodu.

## Stack

`HTML5` `CSS3` `vanilla JavaScript` `GitHub Pages` `Vercel`

## Powiązane

Ten sam projekt przełożony na **autorski motyw WordPress** — dostępny na życzenie. Podstrona „Nasze auta" pokazuje integrację z [importerem aukcji Copart/IAAI](https://github.com/krzysiek2115op/copart-iaai-importer): scraper w Pythonie zasila bazę, wtyczka WordPress renderuje ofertę.

## Licencja

MIT — patrz [`LICENSE`](LICENSE). Treści i dane w demo są przykładowe.
