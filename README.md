# Immersive 3D Web Design

A Claude Code skill for building award-winning immersive, 3D, and WebGL-powered web experiences — the kind made by Active Theory, Bruno Simon, and Resn. Not generic AI websites.

## Installation

### Recommended (clone directly into Claude Code skills directory)

```bash
mkdir -p ~/.claude/skills
git clone https://github.com/YOUR_USERNAME/immersive-3d-web-design.git ~/.claude/skills/immersive-3d-web-design
```

### Manual install/update

```bash
mkdir -p ~/.claude/skills/immersive-3d-web-design
cp SKILL.md ~/.claude/skills/immersive-3d-web-design/
```

## Usage

In Claude Code, invoke the skill:

```
/immersive-3d-web-design

Build me a portfolio site with a dark 3D environment and floating project cards
```

Or ask Claude directly:

```
Build an immersive landing page for my music project — WebGL, dark, particle-heavy
```

```
Create a Three.js scene with a guided fly-through camera and post-processing
```

## Overview

Synthesized from direct study of:
- **activetheory.net** — 8 screenshots analyzed frame-by-frame + community research
- **Active Theory case studies** — Rick & Morty (Adult Swim) and Pottermore: Welcome to Hogwarts (full technical writeups)
- **prometheusfuels.ai** — full content analysis
- **acustable.com** — full content analysis
- **atlab.io** — Active Theory's 20+ WebGL/WebGPU experiment hub
- **Three.js, refs.gallery, webgpu.com, Communication Arts, Awwwards**

The skill encodes design philosophy, color theory, 3D construction patterns, shader code, scroll/interaction patterns, typography rules, 5 deep case studies, a starter scaffold, tool selection guide, and an anti-patterns list.

## What's Covered

### Philosophy
- The website IS the product (not a brochure)
- Environment before interface
- Restraint creates impact
- Performance as a design constraint

### Color Theory
- The void palette (near-black, not pure black)
- The 1 accent color rule
- Iridescence and chromatic aberration
- Light as atmosphere (bloom, fresnel, fog)

### Technical Patterns

| Pattern | Details |
|---------|---------|
| **2.5D parallax** | Z-layered 2D assets with parallax, from Rick & Morty case study |
| **Spline camera** | Guided fly-through navigation, from Hogwarts case study |
| **Instance geometry** | 1 draw call for 1000 objects, with code |
| **Particle systems** | Ambient drift, cursor trails, iridescent confetti |
| **Post-processing** | Bloom, chromatic aberration, film grain, glitch — with GLSL |
| **Scroll as timeline** | GSAP ScrollTrigger driving camera position |
| **Lenis smooth scroll** | Buttery scroll synced with ScrollTrigger |
| **Custom cursor** | `mix-blend-mode: difference` cursor with follower |
| **Glitch text reveal** | Randomized character scramble that settles |

### Case Studies (5 Deep Dives)

| Site | Key Lesson |
|------|-----------|
| activetheory.net | Entry ceremony, terminal navigation, 3D portfolio cards, AI chat as UI primitive |
| Pottermore: Hogwarts | Constraint → aesthetic, spline camera, instance geometry, vertex shader animation |
| Rick & Morty (Adult Swim) | Per-section universe theming, physics on 2D, portal gun easter egg |
| Prometheus Fuels | Premium dark tech without WebGL, blurred CSS light sources |
| Acustable.com | Editorial motion-forward portfolio, no Three.js needed |

### Anti-Patterns (what NOT to do)

- White or light-gray background with colored cards
- Inter or Poppins as primary font
- Purple-to-blue gradient on white
- Particles.js connecting-dots background
- Three.js donut geometry as generic decoration
- Scroll animations that only fade-in + translate-Y

## Tool Selection

| Project type | Stack |
|-------------|-------|
| Portfolio, editorial, landing page | CSS + GSAP + Lenis |
| Product reveal, interactive story | Three.js + GSAP + postprocessing |
| Studio portfolio, installation, experimental | Raw WebGL or Three.js + custom shaders |

## Version History

- **1.0.0** — Initial release. Synthesized from 10+ sources including screenshots, case studies, and technical analysis of award-winning studios.

## License

MIT
