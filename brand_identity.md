# TUSSLE.AI — Complete Brand & Build Specification
> Give this entire file to Claude Code. It contains everything needed to build the full landing page from scratch.

---

## 1. PRODUCT OVERVIEW

**Name:** Tussle.AI
**Tagline:** Weaponized Sales Intelligence
**One-liner:** Tussle listens to your sales calls in real time, calculating margins and anchoring prices while you speak. Never leave money on the table again.
**Target user:** B2B sales reps, SDRs, Account Executives, Founders doing sales, Sales Managers
**Product type:** Pre-launch waitlist landing page (no pricing page needed)
**Domain:** tussle.ai

---

## 2. BRAND IDENTITY

### Voice & Tone
- Aggressive, confident, zero fluff
- Talks like a closer, not a corporate SaaS tool
- Think: F1 pit crew meets Wall Street trading floor
- NOT friendly/bubbly — this is a weapon, not a toy
- Reference brands: Linear.app, Vercel, Loom (dark mode)

### Design Aesthetic
- Name: "The Kinetic Monolith"
- Dark, machined, precise
- Elements feel carved out of obsidian
- Glassmorphism cards with subtle orange glow borders
- NO rounded corners (max border-radius: 8px)
- NO stock photos of people
- NO generic SaaS gradients
- Subtle dot grid background texture

---

## 3. COLOR PALETTE

```
--orange:        #FF3B00   /* Primary accent — aggressive red-orange */
--orange-dim:    #CC2F00   /* Darker orange for gradients */
--orange-glow:   rgba(255, 59, 0, 0.25)
--bg:            #080808   /* Main background */
--surface:       #111111   /* Card backgrounds */
--surface-high:  #1a1a1a   /* Elevated surfaces */
--surface-highest:#222222  /* Highest elevation */
--border:        rgba(255,255,255,0.06)
--border-orange: rgba(255, 59, 0, 0.2)
--text:          #E5E2E1   /* Primary text */
--text-dim:      #888888   /* Secondary text */
--text-muted:    #555555   /* Tertiary text */
```

### Background Texture
```css
background-color: #080808;
background-image: radial-gradient(rgba(255,59,0,0.03) 1px, transparent 1px);
background-size: 32px 32px;
```

---

## 4. TYPOGRAPHY

### Font Stack
```
Headlines:  'Oxanium' — weights 700, 800, 900 (Google Fonts)
Body:       'Inter'   — weights 400, 500, 600 (Google Fonts)
Labels:     'Roboto Condensed' — weights 600, 700 (Google Fonts)
```

### Type Scale
```
Hero H1:      clamp(48px, 7vw, 88px) | Oxanium 900 | uppercase | letter-spacing: -0.03em
Section H2:   clamp(28px, 4vw, 56px) | Oxanium 900 | uppercase | letter-spacing: -0.02em
Card H3:      20–24px | Oxanium 800 | uppercase
Body large:   18px | Inter 400 | line-height: 1.65
Body normal:  15–16px | Inter 400 | line-height: 1.65
Labels:       9–12px | Roboto Condensed 700 | UPPERCASE | letter-spacing: 0.15–0.3em
```

---

## 5. COMPONENT LIBRARY

### Primary Button (.btn-primary)
```css
background: #FF3B00;
color: #fff;
font-family: 'Roboto Condensed';
font-weight: 700;
letter-spacing: 0.12em;
text-transform: uppercase;
padding: 14px 32px;
border-radius: 4px;
box-shadow: 0 0 20px rgba(255,59,0,0.35);
transition: transform 0.15s, box-shadow 0.15s;

hover: transform: translateY(-2px); box-shadow: 0 0 32px rgba(255,59,0,0.5);
active: transform: scale(0.97);
```

### Ghost Button (.btn-ghost)
```css
background: transparent;
color: rgba(255,255,255,0.7);
border: 1px solid rgba(255,255,255,0.15);
/* same font/padding as primary */
hover: border-color: rgba(255,59,0,0.4); color: #fff;
```

### Glass Card (.glass-card)
```css
background: rgba(26,26,26,0.6);
backdrop-filter: blur(12px);
border: 1px solid rgba(255,255,255,0.06);
border-top-color: rgba(255,59,0,0.1);
border-radius: 8px;
transition: border-color 0.3s, box-shadow 0.3s;

hover: border-color: rgba(255,59,0,0.25); box-shadow: 0 0 24px rgba(255,59,0,0.08);
```

### Section Divider
```css
height: 1px;
background: linear-gradient(90deg, transparent 0%, #FF3B00 50%, transparent 100%);
opacity: 0.18;
```

### Mockup Window (.mockup-window)
```css
background: #0a0a0a;
border: 1px solid rgba(255,255,255,0.07);
border-radius: 10px;
overflow: hidden;
```
Title bar: `background: rgba(255,255,255,0.04)` with 3 colored dots (red/yellow/green) + label text

### CTA Box (.cta-box)
```css
background: #0f0f0f;
border: 2px solid #FF3B00;
border-radius: 12px;
box-shadow: 0 0 60px rgba(255,59,0,0.15), inset 0 0 40px rgba(255,59,0,0.03);
/* top gradient line */
::before { top gradient bar using orange }
```

### Form Input (.form-input)
```css
background: #111111;
border: 1px solid rgba(255,255,255,0.12);
color: #fff;
padding: 14px 20px;
border-radius: 4px;
focus: border-color: #FF3B00; box-shadow: 0 0 0 2px rgba(255,59,0,0.15);
placeholder: color #555
```

### Testimonial Card
```css
background: #111111;
border: 1px solid rgba(255,59,0,0.12);
border-radius: 8px;
hover: border-color: rgba(255,59,0,0.3); box-shadow: 0 0 20px rgba(255,59,0,0.1); transform: translateY(-2px);
```

---

## 6. ANIMATIONS

### Scroll Reveal (apply to all sections)
```css
.reveal {
  opacity: 0;
  transform: translateY(28px);
  transition: opacity 0.6s ease, transform 0.6s ease;
}
.reveal.visible { opacity: 1; transform: translateY(0); }
/* delay variants: reveal-delay-1 (0.1s), reveal-delay-2 (0.2s), reveal-delay-3 (0.3s) */
```
Use IntersectionObserver with threshold 0.12 to trigger `.visible` class.

### Live Pulse Badge
```css
@keyframes live-pulse {
  0%   { box-shadow: 0 0 0 0 rgba(255,59,0,0.6); }
  70%  { box-shadow: 0 0 0 6px rgba(255,59,0,0); }
  100% { box-shadow: 0 0 0 0 rgba(255,59,0,0); }
}
```

### Progress Bar
Animate width from 0% → 84.7% on page load with 1.2s ease transition (delayed 800ms)

### Who-For Cards: Icons start grayscale, go full color + scale(1.15) on hover

---

## 7. PAGE STRUCTURE (section by section)

---

### SECTION 1: NAV (sticky, z-index 100)
```
[TUSSLE 🥊 .AI]          [How It Works] [Features] [Who It's For]          [Join Waitlist btn]
```
- Sticky top, backdrop-blur, subtle bottom border
- NO "Pricing" link — this is a pre-launch page
- Mobile: hamburger menu (3 links inside)
- Join Waitlist scrolls to CTA section

---

### SECTION 2: HERO
**Layout:** 2-column grid (text left, product card right)

**Left column:**
- Tag: `⚡ WEAPONIZED SALES INTELLIGENCE` (orange, tiny label font)
- H1: `YOUR NEXT DEAL DESERVES A CLOSER.` ("DESERVES" in orange)
- Subtext: "Tussle listens to your sales calls in real time, calculating margins and anchoring prices while you speak. Never leave money on the table again."
- Buttons: [GET EARLY ACCESS] [SEE IT IN ACTION ↓]
- Waitlist counter: 3 avatar circles + "+1.2k" chip + "1,247 closers already on the waitlist"
- Progress bar: "847 / 1,000 beta spots claimed" animated to 84.7%

**Right column — Product mockup card:**
- Dark window with traffic light dots + "TUSSLE_OVERLAY_v1.04" label + pulsing "LIVE" badge
- 3 stat boxes: Floor ($7,200) | Target ($9,500 in orange) | Margin (34%)
- Orange suggestion box: `"Say: 'We can do $8,400 if you commit by Friday — that's our best number and it works for both sides.'"`
- Subtle orange glow around entire card

---

### SECTION 3: PAIN (dark bg #0a0a0a)
**Label:** `SOUND FAMILIAR?`
**3 glass cards:**
1. 😰 **You froze...** — "The prospect asked for a discount and you didn't have the math ready. The silence was deafening."
2. 💸 **You went lower...** — "Panic set in. You slashed the price by 20% before they even finished their sentence. Margin: Destroyed."
3. 🤦 **You said the wrong thing...** — "The wrong value prop at the wrong time. You missed the cues that they were ready to sign."

---

### SECTION 4: HOW IT WORKS (id="how-it-works")
**H2:** `SIMPLE. FAST. LETHAL.` ("LETHAL." in orange)
**3 steps with connecting orange line between them:**

1. **SET YOUR LIMITS** (tune icon, dark square)
   "Input your floor price, target, margin % and non-negotiables in 30 seconds before the call starts."

2. **TUSSLE LISTENS** (graphic_eq icon, dark square)
   "Our AI analyzes sentiment, detects objections and pricing cues from both sides in real-time."

3. **YOU SAY THE RIGHT THING** (bolt icon, ORANGE square with glow)
   "A card appears on your screen with exactly what to say. Calm. Precise. Devastating."

---

### SECTION 5: PRODUCT MOCKUP DEEP DIVE (dark bg)
**H2:** `Watch It FIGHT FOR YOU` ("FIGHT FOR YOU" in orange)
**Subtext:** "Real output from a live negotiation. Buyer pushes back. Tussle responds in under 2 seconds."

**3-column layout:**

**Left panel (Deal Setup):**
- Deal Target slider bar ($5k → $12.5k)
- Competitive Angle: ROI FOCUSED (selected, orange) / FEATURE SUPERIORITY
- Floor Protection: 🛡 $7,800 HARD FLOOR

**Center panel (Live Interface mockup window):**
- Title: "Tussle Real-Time Interface" + "● LIVE ANALYZING" (pulsing orange)
- Prospect quote box: `"We really like the tech, but the price is a bit high."` → labeled RESISTANCE
- 2 signal boxes: "Budget Constraints" detected | "74% CLOSE RATE" (green)
- Rebuttal box (orange left border): `"Focus on the cost of delay. Remind them of the $200k monthly leak they mentioned earlier."`

**Right panel (Live Insight):**
- Lightbulb icon in orange box
- Label: LIVE INSIGHT
- Insight: `"Buyer mentioned budget pressure → anchor on ROI, not price."`
- Script box: `"Let's talk about what this costs you to delay..."`

---

### SECTION 6: WHO IT'S FOR (id="for-who")
**H2:** `Built For CLOSERS.` ("CLOSERS." in orange)
**4 cards in a row:**
1. 💼 **ACCOUNT EXECUTIVES** — "Crush quotas with real-time margin protection on every call."
2. 📞 **SDRs** — "Handle objections like a 10-year veteran on day one."
3. 🚀 **FOUNDERS** — "Close early adopters without bleeding precious runway."
4. 👑 **SALES MANAGERS** — "Clone your best performers across the entire floor."

Icons: grayscale by default, animate to color + scale up on hover

---

### SECTION 7: TESTIMONIALS
**Counter header:** 3 avatars + "+1.2k" chip + `1,200+ REPS ALREADY ON THE WAITLIST`

**3 testimonial cards:**

Card 1:
> ★★★★★
> "I closed a $12k expansion call using the ROI anchor Tussle suggested mid-call. It's like having a VP of Sales in your ear."
> **Marcus T. — Enterprise AE**

Card 2:
> ★★★★★
> "No more post-call regret about discounting too deep. Tussle keeps me disciplined when the pressure is on."
> **Priya S. — Founder**

Card 3:
> ★★★★★
> "The real-time margin calculation is a game changer. I never have to look away from the camera to use a spreadsheet."
> **Derek L. — Senior SDR**

Use DiceBear avatars:
- Marcus: `https://api.dicebear.com/7.x/avataaars/svg?seed=Marcus&backgroundColor=b6e3f4`
- Priya: `https://api.dicebear.com/7.x/avataaars/svg?seed=Priya&backgroundColor=ffdfbf`
- Derek: `https://api.dicebear.com/7.x/avataaars/svg?seed=Derek&backgroundColor=c0aede`

---

### SECTION 8: CTA / WAITLIST (id="cta-section")
**CTA Box** (orange border, glow, centered, max-width 720px):

**H2:** `DON'T WALK INTO ANOTHER DEAL NAKED.` ("NAKED." in orange)
**Subtext:** "The beta is nearly full. Secure your spot and start closing with lethal precision."

**Form:** `[email input field] [GET EARLY ACCESS btn]`
**Fine print:** "🔥 SPOTS ARE LIMITED FOR BETA · NO SPAM · NO CREDIT CARD"

**On submit → show success state:**
- Orange checkmark circle
- H3: "You're In The Fight. 🥊"
- Text: "We'll hit you up when your spot is ready. Get ready to close like a weapon."

---

### SECTION 9: FOOTER (bg #0a0a0a)
```
TUSSLE.AI                    [Privacy Policy] [Terms of Service] [Contact]
© 2026 Tussle. Built For Closers.
```

---

## 8. RESPONSIVE BREAKPOINTS

```
Desktop:  > 900px  — full multi-column layouts
Tablet:   ≤ 900px  — all grids collapse to single column
                   — hamburger menu replaces nav links
                   — step connector line hidden
Mobile:   ≤ 480px  — Who-For grid becomes 1 column
                   — hero text smaller
                   — CTA form stacks vertically
```

---

## 9. TECH STACK

Single HTML file (no framework needed):
- **CSS:** Pure CSS + CSS variables (no Tailwind required, but Tailwind CDN is fine)
- **Fonts:** Google Fonts CDN (Oxanium, Inter, Roboto Condensed)
- **Icons:** Google Material Symbols CDN
- **Avatars:** DiceBear API (no login needed)
- **JS:** Vanilla JS only — IntersectionObserver for scroll reveal, form submit handler
- **No backend needed** for MVP — form just shows success state client-side

---

## 10. PROMPT FOR CLAUDE CODE

> "Build a complete single-file HTML landing page for Tussle.AI using the brand spec in this file.
> Use pure HTML, CSS variables, and vanilla JS only.
> No frameworks. Single file output.
> Make it pixel-perfect on desktop (1440px wide) and fully responsive on mobile.
> All sections, copy, colors, fonts, components and animations are specified above — follow them exactly.
> The waitlist form should show a success state on submit (no backend needed).
> Output one complete tussle.html file."
