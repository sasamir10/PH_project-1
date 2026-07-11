Generate a pure HTML + CSS (no JavaScript) implementation of an FAQ section
for a conference landing page called "DevConf 2026". This section goes
between the existing "Secure Your Spot" pricing section and the footer.

=== SCOPE ===

- Desktop-only layout. Do NOT include any media queries or responsive
  breakpoints — assume a fixed desktop viewport.
- Keep the code simple and beginner-friendly. Do NOT use vendor prefixes
  or browser-specific properties (no -webkit-, no -moz-, etc).
- Do NOT define CSS custom properties/variables at the top. Just write
  the color values directly wherever they're used in the CSS rules.

=== DESIGN (match the existing page style) ===

- Background: white (#ffffff)
- Primary text (headings): near-black (#111827)
- Secondary/muted text (answers, subheadings): gray (#6b7280)
- Accent blue (used for icons/hover if needed): #2563eb
- Card border: light gray (#e5e7eb), 1px solid
- Card style: white background, 1px light gray border, 12px border-radius,
  20px padding, no box-shadow
- Section heading: bold, ~40px, black, centered
- Section subheading: ~16px, gray, centered, placed directly below the
  heading
- Font: system sans-serif stack (e.g. -apple-system, "Segoe UI", Roboto,
  sans-serif)
- Section vertical padding: 80px top and bottom
- Content max-width: ~800px, centered on the page

=== CONTENT & STRUCTURE ===

- Section heading: "Frequently Asked Questions"
- Subheading: "Everything you need to know before you register"
- Build the accordion using native <details> and <summary> tags only —
  no JavaScript, no checkbox/label hacks
- Layout: single column list, each FAQ item is its own <details> element
  styled as a bordered card
- Space each FAQ card 12px apart vertically
- <summary> styling:
  - Remove the default browser marker using: 
    details summary { list-style: none; }
  - Add a custom "+" character on the right side using a <span> inside 
    the <summary> (not ::after, keep it simple and directly in the HTML)
  - When the <details> element has the "open" attribute, change that 
    span's content/rotation using the CSS attribute selector: 
    details[open] span { ... }
  - Font-weight: bold, font-size: 18px, color: #111827, cursor: pointer
- Answer text (inside <details>, below <summary>): color #6b7280,
  font-size: 15px, line-height 1.6, margin-top: 12px

Include these 6 FAQ items with realistic, conference-appropriate answers:

1. What's included in my ticket?
2. Is there a refund or cancellation policy?
3. Do you offer group or team discounts?
4. Is DevConf 2026 in-person only, or is there a virtual option?
5. Will sessions be recorded?
6. What's your Code of Conduct?

=== OUTPUT REQUIREMENTS ===

- Provide complete, valid HTML markup using semantic tags (<section>,
    <details>, <summary>)
- Provide plain CSS in a single <style> block (no separate file needed)
- No external dependencies, no icon fonts, no JS
- Add a comment at the top of the HTML marking "SECTION: FAQ" so I can
  easily locate and insert it into my existing landing page
