# Batch No. 9 — Prompty AI dla docelowych mediów

Ten dokument zawiera gotowe prompty do wygenerowania finalnych zdjęć (Midjourney) i wideo (Runway),
które mają zastąpić tymczasowe placeholdery Unsplash w pliku `index.html`. Każdy prompt uwzględnia
estetykę marki: **Terakota (#E2725B)**, **Kość słoniowa (#FAF9F6)**, **głęboki brąz espresso (#2B1700)**
oraz naturalne, ciepłe światło.

---

## 1. Sekcja HERO — zdjęcie główne

**Miejsce w kodzie:** `#hero`, kontener `div.relative.aspect-[4/5]...`
**Proporcje:** mobile `4:5` (pionowe) → `sm` `5:4` (poziome) → `lg` `4:5` (pionowe, duży format)
**Rola:** pierwsze wrażenie, emocjonalny "hook" — bliskość, ciepło, rzemiosło.

### Midjourney — desktop (pionowy, 4:5)
```
Overhead shot of three hands clinking specialty coffee cups together in a warm celebration
toast, latte art visible in two cups, one glass of cold brew, rustic wooden table,
terracotta and ivory ceramic cups, soft directional morning sunlight from a side window,
shallow depth of field, warm amber and burnt orange color grading, artisanal coffee roastery
atmosphere, editorial food photography, shot on Hasselblad, 90mm macro lens, ultra
realistic, natural film grain --ar 4:5 --style raw --v 6
```

### Midjourney — mobile (poziomy crop, 5:4)
```
Close-up overhead flat lay of specialty coffee cups being raised together in a toast,
latte art detail, warm terracotta ceramic mugs on light oak wood table, soft natural
window light, cozy specialty coffee shop mood, warm minimal color palette of terracotta,
ivory and espresso brown, shallow focus, editorial product photography style,
photorealistic --ar 5:4 --style raw --v 6
```

### Runway (Gen-3) — pętla wideo w tle hero
```
Slow motion cinematic close-up of steam gently rising from a terracotta ceramic coffee cup
on a wooden table, soft morning sunlight streaming from the left creating warm highlights,
subtle dust particles floating in the light beam, shallow depth of field, camera performs
a very slow, almost imperceptible push-in, warm ivory and terracotta color palette, cozy
artisanal coffee roastery ambience, natural and calm, seamless loop, 4s duration,
low motion intensity, photorealistic film look
```

---

## 2. Sekcja WYRÓŻNIONY PRODUKT — "Etiopia Yirgacheffe"

**Miejsce w kodzie:** `#produkt`, kontener `div.relative.aspect-[4/3]...`
**Proporcje:** mobile `4:3` → `sm` `16:10` → `lg` `4:5` (pionowy, duży)
**Rola:** pokazanie procesu parzenia / rzemiosła — metoda przelewowa (pour-over).

### Midjourney — desktop (pionowy, 4:5)
```
Barista's hands pouring hot water in slow spiral motion over a pour-over coffee dripper
with a paper filter, glass Chemex-style carafe underneath, freshly ground specialty coffee
bed visible, blooming crema, warm terracotta apron sleeve visible at frame edge, soft
natural side lighting from a cafe window, blurred warm background with roasting equipment,
rich espresso brown and terracotta tones, shallow depth of field, editorial coffee
photography, photorealistic, shot on 50mm lens --ar 4:5 --style raw --v 6
```

### Midjourney — mobile (poziomy crop, 16:10)
```
Wide close-up of a pour-over coffee brewing setup, glass carafe and dripper on a wooden
counter, gentle steam rising, warm golden hour light from the side, soft blurred cafe
interior in the background with terracotta and ivory tones, minimal composition with
generous negative space on the right side for text overlay, photorealistic editorial
still life --ar 16:10 --style raw --v 6
```

### Runway (Gen-3) — pętla wideo procesu parzenia
```
Cinematic macro shot of hot water being poured in a slow circular motion over ground
coffee in a pour-over filter, visible bloom and bubbling crema, warm steam rising, soft
natural light from a window, camera holds a static, slightly low angle, shallow focus
with soft bokeh background in terracotta and warm brown tones, calm and meditative pacing,
seamless loop, 5s duration, medium motion intensity, photorealistic film look
```

---

## 3. Karty "Cechy / Zalety" (opcjonalne tło sekcji)

**Miejsce w kodzie:** `#proces` / `#cechy`, tło sekcji za siatką kart (obecnie ikony SVG, bez zdjęcia)
**Proporcje:** szerokie tło `21:9`, użyte jako bardzo subtelna, przyciemniona warstwa pod kartami (opcjonalnie).

### Midjourney — szerokie tło sekcji
```
Top-down flat lay of raw specialty coffee beans scattered across a warm terracotta linen
surface, soft natural diffused light, minimal negative space, muted warm color palette of
terracotta, ivory and espresso brown, very subtle shadows, clean minimal texture background
for web design overlay, photorealistic, editorial still life --ar 21:9 --style raw --v 6
```

---

## 4. Wskazówki ogólne dla generacji

- **Spójność świateł:** wszystkie grafiki powinny używać ciepłego, kierunkowego światła naturalnego
  (godzina złota / miękkie światło z okna), unikać zimnych, niebieskawych tonów.
- **Paleta kolorów do promptów pomocniczych (jeśli model wspiera hex/color reference):**
  `#E2725B` (terakota), `#FAF9F6` (kość słoniowa), `#2B1700` (espresso brąz).
- **Format plików:** eksportuj z Midjourney w rozdzielczości min. 2000px szerokości, kompresuj do
  WebP przed wdrożeniem (`object-cover` w CSS obsłuży przycinanie do kontenera).
- **Runway — długość i rozmiar:** dla tła hero i sekcji produktu wystarczą 4–5 sekundowe, bezszwowe
  pętle (loop), eksport w 1080p, format MP4 (H.264) + WebM dla lepszej kompresji na mobile.
- **Dostępność:** dla finalnych wersji wideo dodaj `muted`, `playsinline`, `loop` oraz zachowaj
  statyczny obraz `poster` (klatka z Midjourney) jako fallback dla wolniejszych łączy mobilnych.
