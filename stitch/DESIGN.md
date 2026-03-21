# Design System Strategy: High-Performance Sales Architecture

## 1. Overview & Creative North Star: "The Kinetic Monolith"
This design system is built for the "closer." It rejects the soft, rounded playfulness of consumer SaaS in favor of a "Kinetic Monolith" aesthetic—an environment that feels like a high-performance engine room or a darkened fight gym. It is aggressive, precise, and unapologetically focused on data-driven combat.

We break the "template" look by utilizing heavy-weighted typography contrasted against microscopic labels, paired with a layout that favors intentional asymmetry. Elements don’t just sit on a grid; they are "machined" into the interface. By utilizing overlapping glass layers and high-contrast accents, we create a sense of depth that feels like a head-up display (HUD) for B2B elite.

## 2. Colors & Surface Architecture
The palette is dominated by deep blacks (`surface_container_lowest`) and the visceral energy of `primary` (#FF3B00).

### The "No-Line" Rule
Traditional 1px solid borders are strictly prohibited for sectioning. Boundaries must be defined through background color shifts. Use `surface_container_low` for the base and `surface_container_high` for inset modules. This creates a "milled" look where components appear carved out of a single block of obsidian.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers.
*   **Base Layer:** `surface` (#131313) for the main application background.
*   **Navigation/Sidebar:** `surface_container_low` (#1C1B1B) to provide a subtle structural anchor.
*   **Actionable Cards:** `surface_container_highest` (#353534) with a 40% opacity to allow for glassmorphism.

### The "Glass & Glow" Rule
To achieve the "Vercel-meets-Gym" aesthetic, floating elements (modals, dropdowns) must use Glassmorphism. 
*   **Effect:** `backdrop-blur: 20px` combined with a background of `surface_variant` at 60% opacity.
*   **Signature Glow:** Use a 1px "Ghost Border" using `primary` at 15% opacity, but only on the top and left edges to simulate a directional light source hitting a sharp edge.

### Signature Textures
Apply a subtle 2% grain/noise texture to the `background` to eliminate banding and provide a "grit" consistent with a high-end gym environment.

## 3. Typography: The Editorial Hammer
Typography isn't just for reading; it’s for impact. We use a high-contrast scale to emphasize "The Win."

*   **Display & Headlines:** `inter` (Display variant) or `Geist`. Extra Bold. Letter-spacing: `-0.05em`. These should feel heavy, like a physical weight.
*   **Body:** `inter`. Regular. Letter-spacing: `normal`. Optimized for high-speed scanning of CRM data.
*   **Labels:** `spaceGrotesk`. All-caps. This mono-spaced influence suggests technical precision and "weaponized" data.

| Level | Token | Weight | Case | Character Spacing |
| :--- | :--- | :--- | :--- | :--- |
| **Display** | `display-lg` | 800 | Sentence | -0.05em |
| **Headline** | `headline-md` | 700 | Sentence | -0.03em |
| **Label** | `label-sm` | 500 | Uppercase | +0.1em |

## 4. Elevation & Depth: Tonal Layering
We do not use shadows to represent "lightness." We use them to represent "intensity."

*   **The Layering Principle:** Place a `surface_container_lowest` (#0E0E0E) card inside a `surface_container_high` (#2A2A2A) section to create a recessed, "docked" feel.
*   **Ambient Shadows:** For floating state-change elements, use an extra-diffused shadow: `box-shadow: 0 20px 40px rgba(0,0,0,0.6)`.
*   **The Ghost Border:** For containment, use `outline_variant` (#5E3F38) at 20% opacity. It should be felt, not seen.
*   **Accent Glows:** Primary CTAs should have a `0px 0px 15px` outer glow using `primary_container` (#FF562D) at 30% opacity to simulate a neon "ON" state.

## 5. Components: The Arsenal

### Buttons (The "Striker" Series)
*   **Primary:** Background `primary` (#FFB4A2/FF3B00), Text `on_primary`. Sharp corners (`radius-sm`). No gradients, just raw color power.
*   **Secondary:** Ghost style. `outline` border at 20% opacity. On hover, background shifts to `surface_bright`.
*   **Tertiary:** Text only in `primary_fixed`, all-caps `label-md` font.

### Cards & Data Lists
*   **Constraint:** Zero divider lines.
*   **Separation:** Use a `2.5` (0.5rem) vertical gap from the spacing scale.
*   **Interaction:** On hover, a card should shift from `surface_container` to `surface_container_high` with a subtle `primary` glow on the left border (2px width).

### Input Fields
*   **Style:** Minimalist. Underline only or "milled" (inset background).
*   **Focus State:** The border glows with `primary` at 40% opacity. Helper text uses `label-sm` in `on_surface_variant`.

### Signature Component: The "Performance HUD"
A custom component for sales metrics. Large `display-sm` numbers in `primary` color, sitting on a `surface_container_lowest` background with a background grid-line texture (12px squares, `outline_variant` at 5% opacity).

## 6. Do’s and Don’ts

### Do
*   **Use Asymmetry:** Align text to the left but place "Aggressive" CTA's in unexpected, high-margin areas.
*   **Embrace Dark Space:** Let the `#080808` breathe. High performance requires focus; focus requires the absence of noise.
*   **Tighten the Bolts:** Use the smallest `roundedness` (`sm`: 0.125rem) for a "machined" feel.

### Don't
*   **No Rounded Corners:** Avoid `xl` or `full` radius unless it's a specific status pill. "Soft" is the enemy of "Aggressive."
*   **No Generic Grays:** Every neutral must have a hint of warmth or "blood" (red/brown tint) found in the `outline` tokens (#AE887F).
*   **No Standard Shadows:** Never use a default CSS drop-shadow. If it doesn't look like ambient light in a dark room, it’s wrong.