<div align="center">

# Kredyt Kompas

**Kompletna strona firmowa pośrednika kredytowego** — prezentacja oferty,
kalkulator zdolności kredytowej liczony w przeglądarce i ścieżka kontaktu.
Statyczny HTML, CSS i vanilla JS: bez frameworków, bez build-stepu, bez bazy danych.

[▶ Zobacz stronę na żywo](https://krzysiek2115op.github.io/kredyt-kompas-demo/) ·
[Kalkulator](https://krzysiek2115op.github.io/kredyt-kompas-demo/kalkulator.html) ·
[Licencja MIT](LICENSE)

<br>

[![Strona główna — sekcja powitalna z hasłem „Wyznaczamy kurs na Twój kredyt hipoteczny"](docs/zrzuty/01-strona-glowna.png)](https://krzysiek2115op.github.io/kredyt-kompas-demo/)

</div>

---

## Co to jest

Demo portfolio: **8 podstron** pokazujących, jak wygląda strona usługowa
zbudowana bez ani jednej zależności zewnętrznej. Treści i dane firmowe są
przykładowe — to prezentacja rzemiosła, nie działający biznes.

| Podstrona | Rola |
|---|---|
| `index.html` | Strona główna — oferta, proces współpracy, dowód społeczny |
| `kalkulator.html` | **Kalkulator zdolności kredytowej** liczony w przeglądarce |
| `kredyty-hipoteczne.html` | Podstrona ofertowa pod frazę o największym potencjale sprzedażowym |
| `o-nas.html`, `faq.html` | Budowanie zaufania — najczęstsza bariera w usługach finansowych |
| `kontakt.html` | Formularz kontaktowy |
| `polityka-prywatnosci.html` | Wymagana przy przetwarzaniu danych z formularza |
| `nasze-auta.html` | Podstrona demonstracyjna dla [wtyczki IAAI Importer](https://github.com/krzysiek2115op/iaai-importer-demo) |
| `404.html` | Własna strona błędu |

## Kalkulator

[![Kalkulator zdolności kredytowej — parametry analizy po lewej, wynik i wskaźnik DSTI po prawej](docs/zrzuty/02-kalkulator.png)](https://krzysiek2115op.github.io/kredyt-kompas-demo/kalkulator.html)

Metodyka zbliżona do bankowej: korekta dochodu według formy zatrudnienia, koszty
gospodarstwa domowego, limit DSTI 50% i bufor stresowy stopy +2,5 p.p. zgodny
z rekomendacją KNF. **Liczy po stronie klienta** — dane o dochodach i zobowiązaniach
nie opuszczają przeglądarki. Mniejszy zakres przetwarzania danych osobowych
i natychmiastowa reakcja interfejsu.

## Decyzje techniczne

**Zero zależności.** Kalkulator, nawigacja i walidacja formularza działają na czystym
JavaScripcie. Nic do zaktualizowania, nic do zepsucia przez breaking change
w bibliotece, brak kosztów utrzymania.

**Treść widoczna także bez JavaScriptu.** Animacje wejścia (`.reveal`) odsłania
`IntersectionObserver`; przy wyłączonym JS blok `<noscript>` wymusza widoczność.
Bez tego strona byłaby dla takiego odwiedzającego pusta.

**SEO i bezpieczeństwo w plikach, nie w deklaracjach.** `sitemap.xml`, `robots.txt`,
`meta description` + `canonical` + Open Graph na każdej z ośmiu podstron, własna
strona 404 z `noindex`.

> ⚠️ **Nagłówki bezpieczeństwa: gdzie działają, a gdzie nie.** `_headers`
> (Netlify, Cloudflare Pages) i `vercel.json` (Vercel) niosą CSP, `X-Frame-Options`,
> `Referrer-Policy` i `Permissions-Policy`. **GitHub Pages ignoruje oba** — nie
> pozwala ustawiać własnych nagłówków w ogóle. Wersja pod adresem `github.io`
> działa więc bez nich i jest to ograniczenie hostingu, nie przeoczenie.

**Hosting za 0 zł.** Strona stoi na GitHub Pages; `vercel.json` pozwala przenieść
ją na Vercel bez zmiany kodu — i dopiero tam nagłówki zaczynają działać.

## Strona 404

[![Strona błędu 404 — nagłówek „Ten adres nie prowadzi do żadnej strony" i trzy karty nawigacyjne](docs/zrzuty/03-strona-404.png)](https://krzysiek2115op.github.io/kredyt-kompas-demo/404.html)

## Stack

`HTML5` `CSS3` `vanilla JavaScript` `GitHub Pages` `Vercel`

## Powiązane

Ten sam projekt przełożony na **autorski motyw WordPress** — dostępny na życzenie.
Podstrona „Nasze auta" pokazuje integrację z
[importerem aukcji Copart/IAAI](https://github.com/krzysiek2115op/copart-iaai-importer):
scraper w Pythonie zasila bazę, wtyczka WordPress renderuje ofertę.

Ta sama fikcyjna marka wraca jako witryna klienta w demo
[MP Offer Automation Suite](https://github.com/krzysiek2115op/mp-offer-automation-suite).

## Uwagi

- **Formularze niczego nie wysyłają.** Mają atrybut `data-demo` i `action`
  wskazujący na placeholder `formspree.io/f/YOUR_FORM_ID`; skrypt rozpoznaje to
  i pokazuje potwierdzenie, nie wykonując żądania. Wdrożenie u klienta = wklejenie
  własnego identyfikatora formularza.
- **Zdjęcia pochodzą z Unsplasha** i są ładowane z `images.unsplash.com`
  (licencja Unsplash). Polityka CSP w `_headers` i `vercel.json` wprost na to zezwala —
  domyślne `img-src 'self'` zablokowałoby całą warstwę wizualną strony.
- Dane firmowe, opinie i numery telefonów są **przykładowe**.

## Licencja

MIT — patrz [`LICENSE`](LICENSE). Treści i dane w demo są przykładowe;
zdjęcia pozostają na licencji Unsplash.
