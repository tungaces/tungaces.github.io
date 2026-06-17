# tungaces.github.io
# Event Schedule Timeline

A responsive event schedule webpage inspired by the provided design. The page displays a three-day agenda (Friday, Saturday, Sunday) in a calendar-style timeline layout.

## Features

- Responsive schedule layout
- Time grid from 16:30 to 05:00
- Three-day column view
- Orange event cards matching the design
- Hover effects for event cards
- Mobile-friendly layout
- GitHub Pages compatible
- **Every orange event box is a clickable link**

## Demo

After deployment, users can click anywhere inside an orange event box to open the corresponding event page.

## Project Structure

```text
.
├── index.html
├── css
│   └── style.css
├── js
│   └── script.js
├── assets
│   └── images
└── README.md
```

## Technology Stack

- HTML5
- CSS3
- Vanilla JavaScript

No frameworks required.

---

## Event Data Structure

Store events in JavaScript:

```javascript
const events = [
  {
    title: "Friday party",
    day: "friday",
    start: "20:00",
    end: "04:00",
    location: "BIP - Rue Royale 2 - 1000 Brussels",
    url: "https://example.com/friday-party",
    details: [
      "21:00 – Talk The heritage of women in Jazz",
      "22:00 – Live band Roaring Cats",
      "22:45 – Show Time"
    ]
  }
];
```

---

## Clickable Event Cards

Each orange box must be wrapped inside an anchor tag.

Example:

```html
<a
  href="https://example.com/friday-party"
  class="event-card"
  target="_blank"
  rel="noopener noreferrer"
>
  <div class="event-content">
    <h3>Friday party</h3>
    <p>Where we meet: BIP - Rue Royale 2 - 1000 Brussels</p>
  </div>
</a>
```

Or generated dynamically:

```javascript
card.innerHTML = `
  <a href="${event.url}" class="event-link">
    <div class="event-card-content">
      ...
    </div>
  </a>
`;
```

---

## CSS Requirements

### Event Card

```css
.event-link {
  text-decoration: none;
  color: inherit;
  display: block;
  height: 100%;
}

.event-card {
  background: #f2a900;
  border-radius: 16px;
  cursor: pointer;
  transition: transform 0.2s ease,
              box-shadow 0.2s ease;
}

.event-card:hover {
  transform: translateY(-3px);
  box-shadow: 0 8px 20px rgba(0,0,0,0.15);
}
```

### Grid Layout

```css
.schedule-grid {
  display: grid;
  grid-template-columns: 80px repeat(3, 1fr);
}
```

---

## Accessibility

Every clickable event card should contain:

```html
<a
  href="..."
  aria-label="Open Friday Party details"
>
```

This improves keyboard navigation and screen-reader support.

---

## Mobile Layout

For screens below 768px:

```css
@media (max-width: 768px) {
  .schedule-grid {
    display: block;
  }

  .day-column {
    margin-bottom: 2rem;
  }
}
```

---

## Local Development

Clone the repository:

```bash
git clone https://github.com/yourusername/event-schedule.git
```

Open:

```bash
index.html
```

or use:

```bash
python -m http.server 8000
```

Visit:

```text
http://localhost:8000
```

---

## Deploy to GitHub Pages

1. Push repository to GitHub.
2. Open:

   Settings → Pages

3. Configure:

```text
Source: Deploy from a branch
Branch: main
Folder: / (root)
```

4. Save.

GitHub Pages will publish automatically.

The site will be available at:

```text
https://yourusername.github.io/event-schedule/
```

---

## Functional Requirement

✅ Every orange event box is a clickable hyperlink.

The following cards should each have their own URL:

- Friday Party
- Harvest Moon Ball Prelims (ULB)
- Saturday Party
- Halles That Swing
- Blues After Party

Clicking anywhere inside a card must open its corresponding page.
