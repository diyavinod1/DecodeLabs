# NexCore Systems — Cyberpunk-Corporate Brand Assets

> A complete AI-generated visual identity system using advanced image generation prompting techniques.

---

## Brand Overview

**Brand Name**: NexCore Systems  
**Aesthetic**: Cyberpunk-Corporate — the tension between cold corporate efficiency and neon-lit digital rebellion  
**Core Palette**:

| Token | Hex | Usage |
|---|---|---|
| Background | `#020D14` | All surfaces |
| Cyan Primary | `#00FFE1` | Logo, icons, borders, UI |
| Magenta Accent | `#FF0077` | Alerts, emphasis, data |
| Text Primary | `#E0F4FF` | Headlines, body |
| Text Muted | `#4A8FA0` | Labels, metadata |

**Typography**:
- Display: `Exo 2` — weight 300 / 900
- UI / Mono: `Share Tech Mono`
- Brand suffix: `SYSTEMS // 2047`

---

## Asset 01 — Logo Concept

**Format**: SVG vector, 16:9 master  
**Concept**: Hexagonal geometric frame with dual lockup — icon badge (left) + wordmark (right). Circuit connector details extend from hex vertices.

### Midjourney Prompt
```
minimal corporate logo for "NexCore Systems", hexagonal geometric frame, 
glowing cyan neon lines, dark navy background, cyberpunk aesthetic, 
circuit board connector details, dual typography lockup, flat vector 
--style raw --v 6 --ar 16:9
```

### Negative Prompt
```
--no gradients, lens flare, photorealism, organic shapes, serif fonts, 
rounded corners, drop shadows, warm colors
```

### Advanced Parameters
| Parameter | Value | Reason |
|---|---|---|
| `--style raw` | Raw | Prevents AI over-stylizing |
| `--v 6` | Version 6 | Best for flat vector fidelity |
| `--ar 16:9` | 16:9 | Website hero ratio |

---

## Asset 02 — Hero Image

**Format**: SVG / PNG, 1920×1080  
**Concept**: Futuristic city skyline at night rendered in flat geometry. Buildings with glowing window lights in brand cyan and magenta. Brand wordmark anchored by a horizon scanline.

### DALL-E 3 Prompt
```
cyberpunk corporate hero banner, futuristic city skyline silhouette at 
night, buildings with glowing cyan and magenta window lights, bold company 
wordmark "NEXCORE" centered, holographic horizon line, flat vector style, 
deep navy black background, ultra-sharp
```

### Negative Prompt
```
no people, no cars, no clouds, no photorealistic textures, no warm colors, 
no gradients, no lens blur, no bokeh, no organic shapes
```

### Advanced Parameters
| Parameter | Value | Reason |
|---|---|---|
| Aspect Ratio | `16:9` | Website banner standard |
| Lighting Style | `Top-down neon ambient` | No natural sunlight |
| Style | `Flat vector illustration` | Brand consistency |

---

## Asset 03 — Icon Set

**Format**: SVG, 6 glyphs at 90×90px each  
**Concept**: Geometric glyph system on a micro-grid. Cyan icons for primary navigation; magenta for alerts and data emphasis.

| Icon | Name | Color | Purpose |
|---|---|---|---|
| Nested squares + dot | `CORE_SYS` | Cyan | Core system |
| Triangle + circle | `DELTA_OPS` | Cyan | Operations |
| Document + rows | `DATA_LINK` | Magenta | Data & files |
| Concentric circles | `NET_GRID` | Cyan | Network |
| Nested hexagon | `HEX_CORE` | Cyan | Core module |
| Crosshair + nodes | `SIGNAL_X` | Magenta | Signal / alerts |

### Stable Diffusion Prompt
```
Futuristic cyberpunk icon set for AI startup dashboard,
sleek minimal icons, glowing cyan and purple color palette, consistent
vector design system, AI, analytics, cloud computing, automation,
cybersecurity icons, dark background, modern UI design
```

### Negative Prompt
```
no 3D, no shadows, no rounded blobs, no emoji style, no colorful fills, 
no gradients, no inconsistent weights, no outlines with fill, no photorealism
```

---

## Asset 04 — Brand Pattern

**Format**: SVG tileable, 80×80px repeat unit  
**Concept**: Circuit board grid pattern with node points and connecting traces. Scanline overlays at key intervals. Designed as a repeatable CSS/SVG background texture.

### Midjourney / Stable Diffusion Prompt
```
seamless tileable background pattern, cyberpunk corporate circuit board 
motif, dark navy #020D14 base, fine cyan grid lines #00FFE1 at low opacity, 
glowing node points, scanline overlay, minimal geometric repeat 
--tile --ar 1:1 --style raw
```

### Negative Prompt
```
no photorealism, no organic shapes, no warm tones, no characters, 
no gradients, no noise grain overload, no vignette, no lens distortion
```

### Usage (CSS)
```css
.nexcore-bg {
  background-color: #020D14;
  background-image: url('assets/pattern-circuit.svg');
  background-repeat: repeat;
  background-size: 80px 80px;
}
```

---

## Asset 05 — Social / UI Card

**Format**: SVG, 4:3 ratio  
**Concept**: HUD-style employee/profile card. Demonstrates Image-to-Image consistency — the same character placeholder, badge system, and data readouts can be translated across different scenes while maintaining visual identity.

### DALL-E 3 / img2img Prompt
```
Same futuristic female AI engineer from previous image,
cyberpunk corporate HUD employee card UI, same silver hair,
same black techwear outfit, same facial structure, cyberpunk corporate aesthetic,
holographic displays, cinematic neon lighting, ultra realistic
```

### Negative Prompt
```
different character, face distortion, bad anatomy, blurry
```

### Image-to-Image Translation Notes

To keep **character/object consistency** across scenes using img2img:

1. Generate your base card asset first (this file)
2. In Stable Diffusion / Midjourney, use `--cref` (character reference) or upload as img2img seed
3. Lock the character reference weight: `--cw 80` (keeps identity, allows scene changes)
4. Change only the scene descriptor: "office", "street", "datacenter", keeping all brand tokens identical
5. Use the same seed number across generations for maximum consistency

```
[base image] + "same character, NexCore HUD overlay, datacenter background, 
cyan neon ambient lighting, cyberpunk corporate" 
--cref [base_card.png] --cw 80 --style raw
```

---

## Prompting Techniques Demonstrated

| Technique | Applied In |
|---|---|
| **Negative prompts** | All 5 assets — explicitly exclude photorealism, warm tones, gradients |
| **Aspect ratio control** | Logo `16:9`, Pattern `1:1`, Card `4:3` |
| **Lighting style specification** | Hero: "top-down neon ambient, no natural sunlight" |
| **Style locking** | `--style raw` prevents AI from adding unwanted artistic flourishes |
| **Color hex anchoring** | Exact hex values in prompts (`#00FFE1`, `#FF0077`, `#020D14`) |
| **Image-to-Image translation** | Asset 05 card → scene variations with `--cref` |
| **Character consistency** | `--cw 80` weight lock for img2img character transfer |
| **Tiling flag** | `--tile` on pattern asset for seamless repeat |

---

## Repository Structure

```
nexcore-brand-assets/
│
├── README.md                        ← This file
├── brand-guide.md                   ← Color tokens, typography, usage rules
│
├── prompts/
│   ├── 01-logo-prompt.txt
│   ├── 02-hero-prompt.txt
│   ├── 03-icons-prompt.txt
│   ├── 04-pattern-prompt.txt
│   └── 05-card-prompt.txt
│
├── assets/
│   ├── 01-logo-nexcore.svg
│   ├── 02-hero-banner.svg
│   ├── 03-icon-set.svg
│   ├── 04-pattern-circuit.svg
│   └── 05-profile-card.svg
│
└── screenshots/
    └── (add generated outputs from Midjourney / DALL-E here)
```

---

## Tools Referenced

| Tool | Best For |
|---|---|
| **Midjourney v6** | Logo, Hero — best flat vector fidelity |
| **DALL-E 3** | Hero, Card — good for precise text rendering |
| **Stable Diffusion XL** | Icons, Pattern — best for tileable / batch generation |
| **Adobe Firefly** | Alternative for brand-safe commercial use |

---

## How to Use These Prompts

1. Copy any prompt from the `prompts/` folder
2. Paste into your image generation tool of choice
3. Adjust `--ar` for your target format (Instagram = `1:1`, LinkedIn banner = `4:1`)
4. Always include the negative prompt — it's what keeps the cyberpunk-corporate look clean
5. For consistency across images, use the same seed number and reference the brand hex codes in every prompt

---

*Built as a demonstration of advanced AI image generation prompting including negative prompts, aspect ratio control, lighting specification, and image-to-image character consistency.*
