# Design System Strategy: Galactic Intelligence

## 1. Overview & Creative North Star
**Creative North Star: "The Obsidian Command Center"**

This design system is engineered to move away from the "flat" web and into the "spatial" future. We are not building a simple chat tool; we are building a high-tech terminal for interstellar communication. The aesthetic rejects the "boxed-in" nature of traditional apps in favor of **Atmospheric Depth**. 

By utilizing intentional asymmetry—such as right-aligned message metadata and oversized, technical display headers—we create a layout that feels like a mission control dashboard. We break the grid through "overflowing" glows and overlapping glass modules, ensuring the UI feels alive, reactive, and premium.

---

## 2. Colors & Atmospheric Tones
The palette is rooted in the deep void of space (`background: #0e1320`), punctuated by high-energy plasma accents.

### The "No-Line" Rule
**Strict Mandate:** Never use 1px solid borders to separate chat threads, sidebars, or headers. 
*   **The Alternative:** Define boundaries through "Surface Stepping." Use `surface_container_low` for the sidebar and `surface` for the main chat area. Let the shift in hex value do the work.
*   **The Glow Boundary:** If a separation is needed, use a subtle 40px wide linear gradient shadow that bleeds from the edge of one container into the next.

### Surface Hierarchy & Nesting
Treat the UI as a physical stack of semi-transparent materials:
*   **Level 0 (The Void):** `surface_dim` (#0e1320) - The base canvas.
*   **Level 1 (Sub-Panels):** `surface_container_low` (#161b29) - For list backgrounds and inactive states.
*   **Level 2 (Active Modules):** `surface_container_high` (#252a38) - For active chat bubbles or focused inputs.

### The "Glass & Gradient" Rule
For elevated floating elements (Modals, Hover Tooltips), use the **Glass Card** spec: `rgba(255,255,255,0.04)` background with a `24px` backdrop-blur. 
*   **Signature Textures:** Main Action Buttons must use the `primary` to `primary_container` gradient (#1A3A8F to #00B4D8). 
*   **The Atithi Signature:** Use the `tertiary` to `primary_container` gradient (#6D28D9 to #00B4D8) exclusively for VIP users and special system notifications to create instant visual hierarchy.

---

## 3. Typography: The Technical Editorial
We mix heavy-duty geometric sans with utilitarian mono fonts to simulate a futuristic flight computer.

*   **Display & Headlines (Space Grotesk):** Set with tight letter-spacing (-0.02em). This is your "Brand Voice." Use `display-lg` for welcome screens and `headline-sm` for channel names.
*   **Titles & Body (Inter):** The "Workhorse." Use `body-md` for chat messages. Its neutrality balances the high-octane headings.
*   **System Identifiers (JetBrains Mono):** Use for `@usernames`, `timestamps`, and `ID_NUMBERS`. This font conveys "data" and "precision."

---

## 4. Elevation & Depth: Tonal Layering
In this system, light doesn't come from "above"—it comes from the "interface itself."

*   **The Layering Principle:** Instead of standard shadows, use **inner glows**. A message bubble should have a subtle top-left inner highlight to suggest it is a physical glass plate.
*   **Ambient Shadows:** For floating elements, use `0 0 16px rgba(0,180,216,0.3)`. This isn't a shadow; it's a **Photonic Glow**. It should look like the element is emitting light onto the surface below it.
*   **The "Ghost Border" Fallback:** If a container requires a border for accessibility, use `outline_variant` at **15% opacity**. This creates a "barely-there" structural guide without breaking the immersion.

---

## 5. Components: The Command Modules

### Buttons (The Launch Initiators)
*   **Primary:** Gradient fill (#1A3A8F to #00B4D8) | 12px radius | White Text | Glow Shadow.
*   **Secondary:** Glass background | `outline_variant` (20% opacity) | 12px radius.
*   **Special (Atithi):** Violet-Cyan gradient | 12px radius | High-intensity violet glow.

### Input Fields (The Data Terminals)
*   **Style:** Glass background (`rgba(255,255,255,0.04)`) | 12px radius.
*   **State:** On focus, the border-glow transitions from `outline` to `primary`.

### Chat Bubbles & Lists
*   **Rule:** Forbid divider lines.
*   **Structure:** Use `spacing.4` (1rem) of vertical space to separate messages. 
*   **Atithi Frames:** Avatars for Special users must be contained in a **Hexagon Frame** rather than a circle. Use a CSS mask-image to achieve the sharp, high-tech geometric look.

### Interactive Components
*   **Chips:** 12px radius. Use `surface_container_highest` for inactive and `primary` with 10% opacity for active states.
*   **Tooltips:** Absolute Glassmorphism. `24px` blur is mandatory.

---

## 6. Do's and Don'ts

### Do:
*   **Use Asymmetry:** Place timestamps or read receipts in non-traditional spots (e.g., vertically aligned to the left of a message) to enhance the "tech-manual" feel.
*   **Embrace the Glow:** Use the functional colors (Success/Error) as neon glows rather than flat fills.
*   **Leverage Mono:** Use JetBrains Mono for all numerical data to give it a "live-feed" aesthetic.

### Don't:
*   **No Pure Black:** Never use `#000000`. Use `background` (#080D1A) to maintain the "deep space" blue tint.
*   **No Sharp 90° Corners:** Everything must feel engineered. Use the `lg` (16px) or `md` (12px) scales to keep the "aerodynamic" feel.
*   **No Solid Dividers:** If you feel the urge to use a `<hr>` tag, use a 12px gap of `surface_container_lowest` instead.

---

## 7. Technical Tokens Reference

| Property | Token/Value |
| :--- | :--- |
| **Corner Radius** | Card: 16px (xl) \| Input/Btn: 12px (md) |
| **Spacing Unit** | 4px (Base) \| Common: 16px, 24px, 32px |
| **Primary Glow** | `0 0 16px rgba(0,180,216,0.3)` |
| **Glass Blur** | `24px` |
| **Heading Font** | Space Grotesk (700 weight) |
| **Data Font** | JetBrains Mono |