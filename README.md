# Batch No. 9 — Palarnia Kawy Specialty

Statyczna strona typu one-page dla fikcyjnej marki **Batch No. 9** — rzemieślniczej palarni kawy
specialty. Projekt zrealizowany jako w pełni responsywny (RWD, mobile-first) landing page w czystym
HTML5 + Tailwind CSS (CDN), bez zależności buildowych.

> **Uwaga:** referencyjny układ (link Mobbin) wymaga zalogowanego konta i zwracał błąd `403 Forbidden`
> przy próbie dostępu, więc strukturę sekcji odtworzono na podstawie typowego, nowoczesnego układu
> premium brand-site'u (Header/Nav → Hero → Wyróżniony Produkt → Cechy/Zalety → Footer), zgodnie
> z wytycznymi projektu.

## Podgląd

Otwórz [`index.html`](index.html) bezpośrednio w przeglądarce — strona nie wymaga serwera ani
procesu budowania.

## Struktura strony

1. **Header / Nav** — sticky nawigacja z logo SVG, linkami i CTA, menu mobilne (hamburger).
2. **Hero** — nagłówek, opis marki, dwa CTA, zdjęcie hero z pływającą etykietą "9 kg / batch".
3. **Wyróżniony Produkt** — karta ziarna miesiąca (Etiopia Yirgacheffe) z notami smakowymi i ceną.
4. **Cechy / Zalety** — siatka 4 kart (bezpośredni handel, małe partie, świeżość, warsztaty).
5. **Footer** — kolumny nawigacyjne, newsletter, social media, stopka prawna.

## Stos technologiczny

- **HTML5** — jeden plik `index.html`.
- **Tailwind CSS** — przez CDN (`cdn.tailwindcss.com`), mobile-first, z niestandardową konfiguracją
  kolorów i fontów w `tailwind.config`.
- **Fonty:** [Fraunces](https://fonts.google.com/specimen/Fraunces) (nagłówki) + 
  [Inter](https://fonts.google.com/specimen/Inter) (tekst), z Google Fonts.
- **Vanilla JavaScript** — menu mobilne oraz animacje fade-in przy scrollu (`IntersectionObserver`),
  bez zewnętrznych bibliotek.
- **Ikony i logo** — własne, minimalistyczne SVG.
- **Zdjęcia** — tymczasowe placeholdery z Unsplash (`object-cover`), docelowo do podmiany na
  materiały wygenerowane wg promptów z [`prompts.md`](prompts.md).

## Paleta kolorów marki

| Rola          | Kolor                          | Hex       |
|---------------|---------------------------------|-----------|
| Tło strony    | Kość słoniowa (Ivory)          | `#FAF9F6` |
| Akcent/CTA    | Terakota / rdzawy pomarańcz    | `#E2725B` |
| Tekst główny  | Głęboki brąz espresso          | `#2B1700` |

## Docelowe media (AI)

Plik [`prompts.md`](prompts.md) zawiera gotowe, angielskie prompty do **Midjourney** (zdjęcia) i
**Runway** (wideo w pętli) dla każdego miejsca ze zdjęciem placeholder na stronie, uwzględniające
proporcje desktop/mobile oraz estetykę marki (terakota, kość słoniowa, naturalne światło).

## Historia commitów

Strona była budowana i commitowana sekcja po sekcji:

1. `feat: odtworzenie i RWD sekcji Header/Nav`
2. `feat: odtworzenie i RWD sekcji Hero`
3. `feat: odtworzenie i RWD sekcji Wyróżniony Produkt`
4. `feat: odtworzenie i RWD sekcji Cechy/Zalety`
5. `feat: odtworzenie i RWD sekcji Footer wraz z animacjami scroll i menu mobilnym`
6. `docs: wygenerowanie promptów AI dla docelowych mediów`
