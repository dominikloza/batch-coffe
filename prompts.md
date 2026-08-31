# Batch No. 9 — Prompty AI dla docelowych mediów

Ten dokument zawiera gotowe prompty do wygenerowania finalnych zdjęć (Midjourney) i wideo (Runway),
które mają zastąpić tymczasowe placeholdery Unsplash w pliku `index.html`. Każdy prompt uwzględnia
estetykę marki: **Terakota (#E2725B)**, **Kość słoniowa (#FAF9F6)**, **głęboki brąz espresso
(#2B1700)** oraz naturalne, ciepłe światło.

---

## 1. Sekcja HERO — zdjęcie centralne pod nagłówkiem

**Miejsce w kodzie:** `#hero`, `<img>` wewnątrz `div.aspect-[3/4].rounded-t-[3rem]`
**Proporcje:** pionowe 3:4, zaokrąglone górne rogi
**Rola:** centralny "hero shot" — odpowiednik honey-bear bottle z oryginału, tu: torebka/ziarna kawy.

### Midjourney — desktop i mobile (pionowy, 3:4)
```
Top-down macro shot of freshly roasted specialty coffee beans filling the frame edge to edge,
rich glossy dark brown tones with warm amber highlights, single soft directional light from the
top left, shallow depth of field on the front beans, ultra realistic texture, editorial product
photography, shot on Hasselblad 90mm macro lens, warm terracotta and espresso color grading,
photorealistic, natural film grain --ar 3:4 --style raw --v 6
```

### Runway (Gen-3) — subtelna pętla wideo (opcjonalna, w tle hero)
```
Extreme close-up macro of roasted coffee beans, camera performs an almost imperceptible slow
push-in, warm directional light casting soft moving highlights across the glossy bean surface,
tiny dust particles drifting, warm espresso and amber tones, calm and premium mood, seamless
loop, 4s duration, very low motion intensity, photorealistic film look
```

---

## 2. Sekcja "PROŚLEDŹ DROGĘ SWOJEJ KAWY" — zdjęcie pełnoekranowe (prawa kolumna)

**Miejsce w kodzie:** sekcja `#kawa`, prawa kolumna `div.aspect-[4/3]` (mobile) → pełna wysokość (desktop)
**Proporcje:** mobile `4:3`, desktop pełna wysokość kolumny (ok. `3:4` do `4:5`)
**Rola:** pokazanie procesu parzenia / rzemiosła — metoda przelewowa (pour-over).

### Midjourney — desktop (pionowy, 4:5)
```
Barista's hands pouring hot water in a slow spiral over a pour-over coffee dripper with a paper
filter, glass Chemex-style carafe underneath, freshly ground coffee bed blooming with crema,
warm terracotta apron sleeve visible at the frame edge, soft natural window light from the side,
blurred warm cafe interior in the background, rich espresso brown and terracotta tones, shallow
depth of field, editorial coffee photography, photorealistic, 50mm lens --ar 4:5 --style raw --v 6
```

### Midjourney — mobile (poziomy, 4:3)
```
Close-up of a pour-over coffee brewing setup on a wooden counter, gentle steam rising, warm
golden hour light from the side, softly blurred cafe interior in terracotta and ivory tones,
minimal composition, photorealistic editorial still life --ar 4:3 --style raw --v 6
```

---

## 3. Sekcja "PALARNIA NA ŻYWO" — pełnoekranowe zdjęcie ze scroll-zoomem

**Miejsce w kodzie:** `#palarnia`, `<img id="zoom-img">`
**Proporcje:** pełna szerokość, wysokość `60vh` (mobile) / `85vh` (desktop)
**Rola:** immersyjny, "żywy" kadr z palarni/kawiarni — w kodzie ma już nałożony efekt powiększania
sterowany scrollem (JS), więc obraz źródłowy powinien mieć zapas kadru (nie kadrować zbyt ciasno).

### Midjourney — szerokie ujęcie sceny (16:9)
```
Wide cinematic shot inside a warm specialty coffee roastery kitchen, barista pouring hot water
over a pour-over dripper in the foreground, blurred roasting equipment and warm pendant lighting
in the background, steam gently rising, terracotta and ivory color palette, golden hour ambiance,
generous negative space around the subject for a scroll-triggered zoom crop, photorealistic,
editorial documentary style --ar 16:9 --style raw --v 6
```

### Runway (Gen-3) — pętla wideo tła (alternatywa dla statycznego zoomu)
```
Cinematic medium shot inside a warm coffee roastery, barista slowly pouring hot water over a
pour-over dripper, steam rising softly, warm golden pendant lighting, camera holds a slow,
continuous slight push-in, shallow depth of field with soft bokeh in the background, calm and
meditative pacing, terracotta and warm brown tones, seamless loop, 6s duration, medium motion
intensity, photorealistic film look
```

---

## 4. Sekcja "PRAWDZIWA, UCZCIWA KAWA" — mała okrągła fotografia

**Miejsce w kodzie:** sekcja CTA na tle `bg-rust`, `div.w-24.h-24.rounded-3xl`
**Proporcje:** kwadrat 1:1, mocno zaokrąglone rogi
**Rola:** mały, ozdobny akcent nad nagłówkiem — odpowiednik zdjęcia pszczoły na słoneczniku z oryginału.

### Midjourney (kwadrat, 1:1)
```
Extreme close-up macro of ripe red coffee cherries on the branch, soft natural daylight, shallow
depth of field with blurred green leaves in the background, vivid but natural color, dew drops
visible on the cherry skin, warm and organic mood, photorealistic macro photography
--ar 1:1 --style raw --v 6
```

---

## 5. Karty karuzeli "Nasze Najlepsze Mieszanki" (opcjonalne zdjęcia zamiast ikon)

**Miejsce w kodzie:** `#produkty`, `div.carousel-card` — obecnie kolorowe płytki z ikoną ziarna;
opcjonalnie do zastąpienia realnymi zdjęciami produktowymi.
**Proporcje:** kwadrat 1:1.

### Midjourney — packshot produktowy (kwadrat, 1:1)
```
Minimalist product photography of a matte kraft coffee bag standing upright, small round window
showing roasted beans inside, soft studio lighting, warm terracotta and ivory backdrop, subtle
shadow beneath the bag, centered composition, clean commercial packshot style, photorealistic
--ar 1:1 --style raw --v 6
```

---

## 6. Wskazówki ogólne dla generacji

- **Spójność świateł:** wszystkie grafiki powinny używać ciepłego, kierunkowego światła naturalnego
  (godzina złota / miękkie światło z okna), unikać zimnych, niebieskawych tonów.
- **Paleta kolorów do promptów pomocniczych (jeśli model wspiera hex/color reference):**
  `#E2725B` (terakota), `#FAF9F6` (kość słoniowa), `#2B1700` (espresso brąz), `#8B4530` (rdza).
- **Format plików:** eksportuj z Midjourney w rozdzielczości min. 2000px szerokości, kompresuj do
  WebP przed wdrożeniem (`object-cover` w CSS obsłuży przycinanie do kontenera).
- **Runway — długość i rozmiar:** dla sekcji "Palarnia na Żywo" i akcentów w tle wystarczą 4–6
  sekundowe, bezszwowe pętle (loop), eksport w 1080p, format MP4 (H.264) + WebM na mobile.
- **Dostępność:** dla finalnych wersji wideo dodaj `muted`, `playsinline`, `loop` oraz zachowaj
  statyczny obraz `poster` (klatka z Midjourney) jako fallback dla wolniejszych łączy mobilnych —
  przyciski play/pause i wycisz w sekcji "Palarnia na Żywo" są już przygotowane w markupie.
