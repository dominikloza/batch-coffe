# Batch No. 9 — Palarnia Kawy Specialty

Statyczna strona typu one-page dla fikcyjnej marki **Batch No. 9** — rzemieślniczej palarni kawy
specialty. Projekt zrealizowany jako w pełni responsywny (RWD, mobile-first) landing page w czystym
HTML5 + Tailwind CSS (CDN), bez zależności buildowych.

> **O wierności odwzorowania:** referencyjny link Mobbin (preview) wymaga zalogowanego konta i
> zwracał `403 Forbidden` przy bezpośrednim dostępie. Układ, sekwencję sekcji, typografię (efekt
> warstwowego "3D" na nagłówkach), ticker, karuzelę produktów, sekcję ze scroll-zoomem oraz układ
> stopki z gigantycznym logo odtworzono na podstawie klatek wyodrębnionych z udostępnionego przez
> klienta nagrania wideo podglądu strony referencyjnej (oryginalnie marka miodu "Busy Bee Honey").
> Nazwa marki, kolorystyka, teksty i wszystkie zasoby graficzne zostały w 100% zastąpione tematyką
> kawy specialty zgodnie z briefem — struktura DOM i rytm sekcji odpowiadają oryginałowi 1:1.

## Podgląd

Otwórz [`index.html`](index.html) bezpośrednio w przeglądarce — strona nie wymaga serwera ani
procesu budowania.

## Struktura strony

1. **Preloader** — ekran ładowania z licznikiem 0–100% i animowanym ziarnem kawy (odpowiednik
   "Gathering Nectar..." z oryginału).
2. **Header / Nav** — ciemne (espresso) tło, nawigacja rozdzielona na lewo/prawo, wyśrodkowane logo
   w formie plakietki/wstążki, menu mobilne (hamburger).
3. **Hero** — gigantyczny nagłówek "POZNAJ SWOJĄ KAWĘ" z efektem warstwowego cienia 3D, dwa hasła
   boczne, zdjęcie produktowe na środku.
4. **Ticker** — przewijający się poziomo pasek "WYPALANE RĘCZNIE · MAŁA PARTIA · ŚWIEŻO PALONE".
5. **Prześledź Drogę Kawy** — sekcja dwukolumnowa: plakietka z obracającym się tekstem w okręgu,
   nagłówek, CTA (lewo) + pełnowymiarowe zdjęcie (prawo).
6. **Nasze Najlepsze Mieszanki** — pozioma karuzela 5 produktów z auto-przewijaniem i kropkami
   nawigacyjnymi.
7. **Palarnia na Żywo** — pełnoekranowe zdjęcie lifestyle z efektem zoomu sterowanym scrollem oraz
   dekoracyjnymi przyciskami play/pause i wycisz (jak w oryginalnym wideo w tle).
8. **Prawdziwa, Uczciwa Kawa** — sekcja CTA na ciemnym rdzawym tle (rust) z okrągłym zdjęciem i
   nagłówkiem 3D.
9. **Prawdziwe, Uczciwe Opinie** — 4 kolorowe karty z opiniami klientów (na przemian espresso /
   jasna terakota / rust / terakota).
10. **Świeżo Wypalana Kawa Blisko Ciebie** — finalne CTA na tle terakoty z unoszącymi się ziarnami.
11. **Footer** — pełny rząd linków nawigacyjnych, gigantyczne logo "BATCH No. 9" z efektem 3D na całą
    szerokość, stopka prawna i social media.

## Stos technologiczny

- **HTML5** — jeden plik `index.html`.
- **Tailwind CSS** — przez CDN (`cdn.tailwindcss.com`), mobile-first, z niestandardową konfiguracją
  kolorów i fontów w `tailwind.config`.
- **Fonty:** [Rye](https://fonts.google.com/specimen/Rye) (pogrubione nagłówki w stylu vintage) +
  [Inter](https://fonts.google.com/specimen/Inter) (tekst), z Google Fonts.
- **Vanilla JavaScript** — preloader z licznikiem, menu mobilne, animacje fade-in przy scrollu
  (`IntersectionObserver`), ticker CSS, karuzela produktów (scroll-snap + auto-advance + kropki),
  scroll-linked zoom na sekcji "Palarnia na Żywo" — bez zewnętrznych bibliotek.
- **Ikony i logo** — własne, minimalistyczne SVG (ziarno kawy zamiast pszczoły, plakietka z nazwą
  marki zamiast oryginalnego logo).
- **Zdjęcia** — tymczasowe placeholdery z Unsplash (`object-cover`), docelowo do podmiany na
  materiały wygenerowane wg promptów z [`prompts.md`](prompts.md).

## Paleta kolorów marki

Bazowa paleta z briefu (ivory / terracotta / espresso) rozszerzona o dwa pochodne odcienie —
potrzebne do odtworzenia rytmu naprzemiennych kolorowych sekcji z oryginału (który używał żółtego
miodowego i niebieskiego) w sposób spójny z tematyką kawy:

| Rola                                   | Kolor                        | Hex       |
|-----------------------------------------|-------------------------------|-----------|
| Tło strony / sekcje jasne               | Kość słoniowa (Ivory)        | `#FAF9F6` |
| Akcent / CTA / ticker                   | Terakota                     | `#E2725B` |
| Tekst główny / ciemne sekcje (Header, Hero) | Głęboki brąz espresso     | `#2B1700` |
| Jasny wariant terakoty (zastępuje żółty) | Terakota jasna (peach)       | `#E9B29F` |
| Ciemny wariant terakoty (zastępuje czerwień) | Rdza (rust)               | `#8B4530` |

## Docelowe media (AI)

Plik [`prompts.md`](prompts.md) zawiera gotowe, angielskie prompty do **Midjourney** (zdjęcia) i
**Runway** (wideo w pętli) dla każdego miejsca ze zdjęciem placeholder na stronie, uwzględniające
proporcje desktop/mobile oraz estetykę marki (terakota, kość słoniowa, naturalne światło).

## Historia commitów

Strona była budowana i commitowana sekcja po sekcji, w dwóch etapach — pierwszy szkic ogólny, a
następnie pełna przebudowa 1:1 na podstawie klatek z wideo referencyjnego:

1. `fix: wierne odwzorowanie Header/Nav wg oryginalu Mobbin (badge logo, ciemne tlo, preloader)`
2. `fix: wierne odwzorowanie sekcji Hero (naglowek 3D, zdjecie produktu, animacja reveal)`
3. `feat: dodanie tickera WYPALANE RECZNIE i sekcji Prosledz Droge Kawy`
4. `feat: dodanie karuzeli produktow Nasze Najlepsze Mieszanki`
5. `feat: dodanie sekcji scroll-zoom Palarnia na Zywo i CTA Prawdziwa Uczciwa Kawa`
6. `feat: dodanie sekcji Prawdziwe Uczciwe Opinie i finalnego CTA Znajdz Sklep`
7. `fix: przebudowa Footer - gigantyczne logo 3D, pelna nawigacja, stopka prawna`
