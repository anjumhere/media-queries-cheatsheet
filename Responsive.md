# Media Queries Cheatsheet

Font sizes, breakpoints & real-world dimensions from sites like YouTube, Airbnb & Twitter

---

## Syntax — Old vs New

```css
/* Old way — still works */
@media only screen and (max-width: 768px) {
}

/* Modern way — cleaner, use this */
@media (width <= 768px) {
}
@media (width >= 768px) {
}
@media (400px <= width <= 800px) {
}
```

---

## Breakpoints

| Device                   | Width       |
| ------------------------ | ----------- |
| Small Mobile (iPhone SE) | 320px       |
| Mobile                   | 375 – 480px |
| Large Mobile             | 480 – 600px |
| Tablet                   | 768px       |
| Small Laptop             | 1024px      |
| Laptop                   | 1280px      |
| Large Desktop            | 1440px+     |

```css
/* 3 you use 90% of the time */
@media (max-width: 480px) {
} /* mobile */
@media (max-width: 768px) {
} /* tablet */
@media (max-width: 1024px) {
} /* laptop */
```

---

## Font Sizes

| Element    | Desktop | Tablet  | Mobile    |
| ---------- | ------- | ------- | --------- |
| H1 Hero    | 48–64px | 36–40px | 28–32px   |
| H2 Section | 32–40px | 26–32px | 22–26px   |
| H3 Card    | 22–28px | 20–24px | 18–20px   |
| Paragraph  | 16–18px | 15–16px | 14–15px   |
| Caption    | 13–14px | 13–14px | 12–13px   |
| Button     | 15–16px | 14–15px | 14px      |
| Nav links  | 15–16px | 14px    | hamburger |

---

## Padding & Spacing

| Screen  | Container Padding | Gap         |
| ------- | ----------------- | ----------- |
| Desktop | 40px – 80px       | 24px – 32px |
| Tablet  | 24px – 40px       | 16px – 24px |
| Mobile  | 16px – 20px       | 12px – 16px |

---

## Container Max-Widths

| Website        | Max Width     |
| -------------- | ------------- |
| Twitter (feed) | 600px         |
| Most blogs     | 680 – 800px   |
| Landing pages  | 1100 – 1200px |
| YouTube        | 1280px        |
| Airbnb         | 1760px        |

---

## Real Website Font References

| Site        | Element       | Size               | Note                                        |
| ----------- | ------------- | ------------------ | ------------------------------------------- |
| YouTube     | H1            | 24px → 20px mobile | Body stays 14px across all screens          |
| Twitter / X | Tweets        | 15px everywhere    | Only layout changes, font barely moves      |
| Airbnb      | Hero H1       | 58px → 32px mobile | Card titles stay 16px                       |
| Amazon      | Product title | 17 – 21px          | Almost nothing changes on font, only layout |

---

## Most Common Layout Pattern

```css
/* Desktop: 3 cols → Tablet: 2 cols → Mobile: 1 col */
.card {
  width: 30%;
}

@media (max-width: 768px) {
  .card {
    width: 48%;
  }
}

@media (max-width: 480px) {
  .card {
    width: 100%;
  }
}
```

---

## Golden Rules

1. Font size **never goes below 14px** — too hard to read on mobile
2. **Paragraph text barely changes** — 16px desktop, 15px mobile at most
3. **Only headings shrink a lot** — H1 can go from 64px down to 28px
4. **Padding shrinks more than font** — mobile feels tight because of reduced padding, not smaller text
5. **Line height** — always 1.5 to 1.7 for paragraphs on all screens
6. **Touch targets** — buttons minimum 44px height on mobile so fingers can tap easily
7. **Let content decide breakpoints** — resize your browser until something looks broken, then add a breakpoint there

---

## Common Mistake

```css
/* WRONG — missing space before ( */
@media only screen and(max-width: 600px) {
}

/* CORRECT */
@media (max-width: 600px) {
}
```
