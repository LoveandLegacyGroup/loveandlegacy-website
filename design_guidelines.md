{
  "brand": {
    "name": "Love & Legacy Executive Transportation LLC",
    "location": "Atlanta, Georgia",
    "tagline": "Discretion. Reliability. Presence.",
    "attributes": [
      "cinematic",
      "elite",
      "discreet",
      "powerful",
      "emotionally luxurious",
      "hospitality-grade",
      "private-aviation influenced"
    ]
  },
  "non_negotiables": {
    "palette_locked": true,
    "typography_locked": true,
    "motion_rules": {
      "no_bouncy_elastic": true,
      "hero_parallax_only": true,
      "content_animation": "fade-up on scroll",
      "performance_priority": "no jank on mobile"
    },
    "imagery_rules": {
      "no_generic_limo_imagery": true,
      "no_bright_corporate_visuals": true,
      "no_cartoon_icons": true,
      "no_colors_outside_locked_set": true,
      "treatment": "20–40% dark overlay, slightly desaturated, dramatic lighting"
    },
    "ornamentation": {
      "gold_rules_between_sections": "1px",
      "ornamental_gold_dividers": "featured sections only",
      "watermark_crest": {
        "opacity": 0.15,
        "placement": "behind Brand Promise section"
      }
    },
    "testing": {
      "data_testid_required": "All interactive and key informational elements MUST include data-testid (kebab-case, role-based)."
    }
  },
  "design_tokens": {
    "colors": {
      "ink": "#0B0B0B",
      "gold": "#D4AF37",
      "purple": "#4B1E78",
      "ivory": "#F6F1E6",
      "champagne": "#C8B98A",
      "white": "#FFFFFF",
      "usage": {
        "dominant_background": "ink",
        "primary_text_on_dark": "white (body) + ivory (secondary)",
        "primary_cta": "gold",
        "section_accent": "purple",
        "captions_links": "champagne",
        "light_sections": "ivory background with ink text"
      }
    },
    "css_custom_properties": {
      "instructions": "Implement these in /app/frontend/src/index.css :root and .dark overrides. Keep Tailwind + shadcn tokens aligned. Do NOT introduce new hues.",
      "tokens": {
        "--ll-ink": "#0B0B0B",
        "--ll-gold": "#D4AF37",
        "--ll-purple": "#4B1E78",
        "--ll-ivory": "#F6F1E6",
        "--ll-champagne": "#C8B98A",
        "--ll-white": "#FFFFFF",
        "--ll-ink-2": "#111112",
        "--ll-ink-3": "#161618",
        "--ll-border-gold": "rgba(212, 175, 55, 0.35)",
        "--ll-border-ink": "rgba(246, 241, 230, 0.12)",
        "--ll-overlay-hero": "rgba(11, 11, 11, 0.85)",
        "--ll-overlay-image": "rgba(11, 11, 11, 0.28)",
        "--ll-overlay-image-strong": "rgba(11, 11, 11, 0.40)",
        "--ll-focus-ring": "rgba(212, 175, 55, 0.55)",
        "--ll-shadow-soft": "0 18px 60px rgba(0,0,0,0.55)",
        "--ll-shadow-gold": "0 18px 60px rgba(212,175,55,0.10)",
        "--ll-radius-sm": "10px",
        "--ll-radius-md": "14px",
        "--ll-radius-lg": "18px",
        "--ll-container": "1120px",
        "--ll-container-wide": "1240px"
      },
      "shadcn_mapping": {
        "--background": "var(--ll-ink)",
        "--foreground": "0 0% 98% (use white/ivory text)",
        "--card": "var(--ll-ink-2)",
        "--border": "use --ll-border-ink",
        "--ring": "use --ll-focus-ring",
        "--radius": "0.875rem (≈14px)"
      }
    },
    "typography": {
      "fonts": {
        "headlines": "Cormorant Garamond (preferred) OR Playfair Display",
        "body": "Inter (preferred) OR Montserrat"
      },
      "font_loading": {
        "instructions": "Use Google Fonts in index.html or @import in index.css. Ensure font-display: swap.",
        "google_fonts": [
          "https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@400;500;600;700&family=Inter:wght@300;400;500;600&display=swap"
        ]
      },
      "scale": {
        "display_h1": "text-4xl sm:text-5xl lg:text-6xl (serif, tracking-[0.02em], leading-[1.05])",
        "h2": "text-2xl sm:text-3xl lg:text-4xl (serif, leading-[1.15])",
        "h3": "text-xl sm:text-2xl (serif)",
        "body": "text-sm sm:text-base (sans, leading-7)",
        "caption": "text-xs sm:text-sm (sans, text-champagne/70)",
        "overline": "text-[11px] tracking-[0.22em] uppercase (sans, gold/champagne)"
      },
      "type_rules": {
        "headline_emphasis": "Use gold only for 1–3 words max per hero/section headline (e.g., span with text-gold).",
        "max_line_length": "Keep body copy to ~60–72 characters per line on desktop (use max-w-prose / max-w-[65ch]).",
        "serif_usage": "Only for headlines, section titles, pull quotes. Avoid serif in form labels and nav."
      }
    },
    "spacing_system": {
      "section_padding": {
        "mobile": "py-16",
        "tablet": "md:py-24",
        "desktop": "lg:py-28"
      },
      "container": {
        "default": "mx-auto max-w-[1120px] px-5 sm:px-6 lg:px-8",
        "wide": "mx-auto max-w-[1240px] px-5 sm:px-6 lg:px-8"
      },
      "vertical_rhythm": {
        "between_blocks": "gap-10 md:gap-14",
        "between_headline_and_body": "mt-4",
        "between_body_and_cta": "mt-8",
        "between_sections": "gold 1px rule + 24px breathing space"
      }
    },
    "grid": {
      "services": "grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-5 md:gap-6",
      "atlanta_identity": "grid grid-cols-2 lg:grid-cols-4 gap-3 md:gap-4",
      "footer": "grid grid-cols-1 md:grid-cols-3 gap-10"
    },
    "borders_and_dividers": {
      "gold_rule": "h-px bg-[rgba(212,175,55,0.55)]",
      "ornamental_divider": "Use a centered gold rule with small diamond: before/after pseudo elements (no gradients).",
      "section_separator_component": "shadcn Separator + custom className"
    },
    "texture": {
      "noise": {
        "instructions": "Add a subtle CSS noise overlay (opacity 0.06–0.10) on dark sections only. Must not reduce readability.",
        "css_scaffold": ".ll-noise::before{content:'';position:absolute;inset:0;background-image:url('data:image/svg+xml;utf8,<svg xmlns=\"http://www.w3.org/2000/svg\" width=\"160\" height=\"160\"><filter id=\"n\"><feTurbulence type=\"fractalNoise\" baseFrequency=\"0.8\" numOctaves=\"3\" stitchTiles=\"stitch\"/></filter><rect width=\"160\" height=\"160\" filter=\"url(%23n)\" opacity=\"0.35\"/></svg>');mix-blend-mode:overlay;opacity:.08;pointer-events:none;}"
      }
    }
  },
  "components": {
    "component_path": {
      "shadcn_primary": [
        "/app/frontend/src/components/ui/button.jsx",
        "/app/frontend/src/components/ui/navigation-menu.jsx",
        "/app/frontend/src/components/ui/sheet.jsx",
        "/app/frontend/src/components/ui/separator.jsx",
        "/app/frontend/src/components/ui/card.jsx",
        "/app/frontend/src/components/ui/carousel.jsx",
        "/app/frontend/src/components/ui/form.jsx",
        "/app/frontend/src/components/ui/input.jsx",
        "/app/frontend/src/components/ui/textarea.jsx",
        "/app/frontend/src/components/ui/select.jsx",
        "/app/frontend/src/components/ui/checkbox.jsx",
        "/app/frontend/src/components/ui/radio-group.jsx",
        "/app/frontend/src/components/ui/tooltip.jsx",
        "/app/frontend/src/components/ui/sonner.jsx"
      ],
      "notes": "Project uses .js (not .tsx). Create new components as .jsx and follow named exports for components, default exports for pages."
    },
    "nav": {
      "pattern": "Transparent over hero → solid ink on scroll with gold bottom rule",
      "layout": {
        "desktop": "Left: wordmark + crest mark; Center: primary links; Right: Reserve CTA + phone",
        "mobile": "Top bar with wordmark + hamburger; Sheet drawer for nav; sticky bottom CTA bar"
      },
      "scroll_behavior": {
        "threshold": 24,
        "states": {
          "top": "bg-transparent text-white",
          "scrolled": "bg-[rgba(11,11,11,0.92)] backdrop-blur-md shadow-[0_18px_60px_rgba(0,0,0,0.55)] border-b border-[rgba(212,175,55,0.22)]"
        }
      },
      "data_testids": {
        "nav": "site-header",
        "reserve_button": "nav-reserve-button",
        "call_button": "nav-call-button",
        "mobile_menu_button": "nav-mobile-menu-button",
        "mobile_drawer": "nav-mobile-drawer"
      }
    },
    "buttons": {
      "shape": "Luxury / Elegant: tall, slim, radius 10–12px",
      "variants": {
        "primary_gold": {
          "use": "Primary CTAs: Reserve, Submit booking",
          "tailwind": "bg-[#D4AF37] text-[#0B0B0B] hover:bg-[#C8B98A] focus-visible:ring-2 focus-visible:ring-[rgba(212,175,55,0.55)]",
          "motion": "hover: translateY(-1px) + subtle sheen; active: scale(0.98)"
        },
        "secondary_purple": {
          "use": "Secondary CTAs: View Fleet, Explore Services",
          "tailwind": "bg-[#4B1E78] text-[#F6F1E6] hover:bg-[#3F1766] border border-[rgba(212,175,55,0.22)]",
          "motion": "hover: translateY(-1px)"
        },
        "ghost_gold": {
          "use": "Tertiary: Learn more links",
          "tailwind": "bg-transparent text-[#D4AF37] border border-[rgba(212,175,55,0.35)] hover:bg-[rgba(212,175,55,0.08)]",
          "motion": "hover: underline offset + icon nudge"
        }
      },
      "micro_interactions": {
        "sheen": "On hover, animate a pseudo-element linear gradient sweep across button (opacity 0.18). Duration 420ms, ease-out.",
        "no_universal_transition": "Only transition-colors, background-color, box-shadow, opacity. Avoid transition-all."
      },
      "data_testids": {
        "primary": "primary-cta-button",
        "secondary": "secondary-cta-button",
        "ghost": "ghost-cta-button"
      }
    },
    "service_tile": {
      "spec": {
        "background": "Deep Black",
        "top_border": "Gold 3px",
        "text": "Ivory",
        "hover": "Purple bg shift + translateY(-4px)",
        "radius": "14px",
        "padding": "p-6 md:p-7",
        "min_height": "min-h-[220px]"
      },
      "tailwind": "relative rounded-[14px] bg-[#0B0B0B] border border-[rgba(246,241,230,0.10)] pt-6 p-6 md:p-7 shadow-[0_18px_60px_rgba(0,0,0,0.55)] before:absolute before:inset-x-0 before:top-0 before:h-[3px] before:bg-[#D4AF37] hover:bg-[#4B1E78] hover:-translate-y-1 transition-[background-color,box-shadow] duration-300",
      "content": {
        "overline": "SERVICE",
        "title": "Serif h3",
        "bullets": "3 trust signals max",
        "cta": "Ghost gold button"
      },
      "data_testids": {
        "tile": "service-tile",
        "tile_cta": "service-tile-cta"
      }
    },
    "review_card_and_carousel": {
      "carousel": {
        "component": "shadcn Carousel",
        "auto_scroll": "Implement requestAnimationFrame or interval with pause on hover/focus; respect prefers-reduced-motion.",
        "timing": "advance every 5200ms; transition 520ms ease-in-out"
      },
      "card": {
        "bg": "ink-2",
        "border": "gold 1px at 20% opacity",
        "stars": "gold",
        "quote": "serif italic optional",
        "tailwind": "rounded-[14px] bg-[#111112] border border-[rgba(212,175,55,0.22)] p-6 md:p-7"
      },
      "data_testids": {
        "carousel": "reviews-carousel",
        "card": "review-card"
      }
    },
    "forms": {
      "booking_form": {
        "fields": 11,
        "conditional": "Flight number appears only when transfer type = Airport",
        "layout": "Two-column on md+, single column on mobile",
        "input_style": {
          "bg": "ink-3",
          "text": "white",
          "placeholder": "champagne/50",
          "border": "ivory/12",
          "focus": "gold ring + border gold/35",
          "radius": "12px",
          "height": "h-12"
        },
        "tailwind_input": "h-12 rounded-[12px] bg-[#161618] text-white placeholder:text-[rgba(200,185,138,0.55)] border border-[rgba(246,241,230,0.12)] focus-visible:ring-2 focus-visible:ring-[rgba(212,175,55,0.55)] focus-visible:border-[rgba(212,175,55,0.35)]",
        "labels": "text-xs tracking-[0.18em] uppercase text-[rgba(200,185,138,0.85)]",
        "helper_text": "text-xs text-[rgba(246,241,230,0.65)]",
        "error": "Use shadcn FormMessage; color stays within palette: gold for emphasis, ivory for text."
      },
      "data_testids": {
        "form": "booking-form",
        "submit": "booking-form-submit-button",
        "flight_number": "booking-form-flight-number-input"
      }
    },
    "iconography": {
      "style": "Purple circle with gold icon (64x64px). No cartoonish icons.",
      "implementation": {
        "container": "h-16 w-16 rounded-full bg-[#4B1E78] border border-[rgba(212,175,55,0.35)] flex items-center justify-center",
        "icon": "lucide-react icon size-7 text-[#D4AF37]"
      },
      "data_testids": {
        "pillar_icon": "pillar-icon"
      }
    },
    "mobile_sticky_cta_bar": {
      "spec": {
        "visibility": "Only < md",
        "height": "h-16",
        "bg": "ink with blur",
        "buttons": "CALL NOW (ghost gold) + RESERVE YOUR EXPERIENCE (primary gold)",
        "safe_area": "pb-[env(safe-area-inset-bottom)]"
      },
      "tailwind": "fixed bottom-0 inset-x-0 z-50 md:hidden bg-[rgba(11,11,11,0.92)] backdrop-blur-md border-t border-[rgba(212,175,55,0.22)]",
      "data_testids": {
        "bar": "mobile-sticky-cta-bar",
        "call": "mobile-sticky-call-button",
        "reserve": "mobile-sticky-reserve-button"
      }
    }
  },
  "homepage_blueprint": {
    "global": {
      "max_width": "1120px",
      "gold_rule_between_major_sections": true,
      "section_intro_pattern": "Overline (gold/champagne) → Serif H2 → Body copy (ivory) → CTA",
      "scroll_reveal": {
        "library": "framer-motion",
        "variant": "fadeUp",
        "timing": {
          "duration": 0.65,
          "ease": "[0.22, 1, 0.36, 1]",
          "stagger_children": 0.08,
          "viewport_once": true,
          "viewport_amount": 0.22
        }
      }
    },
    "sections": [
      {
        "id": "hero",
        "height": "min-h-[100svh]",
        "bg": "full-bleed image + 85% black overlay",
        "parallax": "background only; translateY 0 → -36px across scroll",
        "layout": "Left-aligned content block, max-w-[640px], bottom-third alignment",
        "content": {
          "overline": "ATLANTA • EXECUTIVE TRANSPORTATION",
          "headline": "Discretion. Reliability. Presence.",
          "subcopy": "Private aviation-level service for executives, VIPs, and productions.",
          "ctas": ["Reserve Your Experience", "View Fleet"],
          "trust_row": "3 micro badges: Licensed • Insured • 24/7 Concierge"
        },
        "spacing": "px-5 sm:px-6 lg:px-8 pb-16 md:pb-20",
        "data_testids": {
          "section": "home-hero-section",
          "primary_cta": "home-hero-reserve-button",
          "secondary_cta": "home-hero-view-fleet-button"
        }
      },
      {
        "id": "three-pillars",
        "bg": "ink",
        "anatomy": "3 cards with purple icon circles + gold icons; thin gold rule above",
        "grid": "grid-cols-1 md:grid-cols-3 gap-6",
        "card": "bg ink-2, border ivory/10, hover border gold/30",
        "data_testids": {"section": "home-pillars-section"}
      },
      {
        "id": "services-grid",
        "bg": "purple section background",
        "anatomy": "6 service tiles; each tile has gold 3px top border; hover purple shift + translateY -4px",
        "grid": "grid-cols-1 sm:grid-cols-2 lg:grid-cols-3",
        "divider": "ornamental gold divider at top of section",
        "data_testids": {"section": "home-services-section"}
      },
      {
        "id": "fleet-feature",
        "bg": "ink",
        "anatomy": "Tahoe black-on-black showcase: left image (aspect 16/10), right specs + CTA",
        "image_treatment": "overlay 28–35%",
        "data_testids": {"section": "home-fleet-feature-section"}
      },
      {
        "id": "reviews-carousel",
        "bg": "purple",
        "anatomy": "Carousel with gold stars; auto-scroll; pause on hover/focus",
        "data_testids": {"section": "home-reviews-section"}
      },
      {
        "id": "brand-promise",
        "bg": "ink",
        "anatomy": "Centered promise copy + crest watermark behind at 15% opacity; gold rule top/bottom",
        "data_testids": {"section": "home-brand-promise-section"}
      },
      {
        "id": "atlanta-identity",
        "bg": "ink",
        "anatomy": "4-image grid (2x2 mobile, 4 across desktop) with captions in champagne",
        "data_testids": {"section": "home-atlanta-identity-section"}
      },
      {
        "id": "instagram-strip",
        "bg": "ivory",
        "anatomy": "Horizontal strip of 6 images; gold follow buttons; ink text",
        "data_testids": {"section": "home-instagram-section"}
      },
      {
        "id": "final-cta-banner",
        "bg": "ink",
        "anatomy": "Short headline + 2 CTAs; gold ornamental divider; optional skyline image overlay",
        "data_testids": {"section": "home-final-cta-section"}
      },
      {
        "id": "footer",
        "bg": "ink",
        "anatomy": "3-column: Brand, Services, Contact; champagne links; gold rule top",
        "data_testids": {"section": "site-footer"}
      }
    ]
  },
  "page_templates": {
    "service_subpages": {
      "route_pattern": "/services/[slug]",
      "hero": "Shorter hero (min-h-[70svh]) with same overlay treatment; breadcrumb; primary CTA Reserve",
      "trust_signals": "Bullet list with gold check icons; 6 items max",
      "sections": [
        "What this service includes (3 cards)",
        "Ideal for (2-column list)",
        "Process (3 steps)",
        "CTA band (gold rule + Reserve)"
      ],
      "data_testids": {"hero": "service-hero-section"}
    },
    "services_hub": {
      "hero": "Editorial intro + services grid",
      "filters": "Optional tabs (shadcn Tabs) for categories; keep minimal",
      "data_testids": {"section": "services-hub"}
    },
    "fleet": {
      "layout": "Bento grid of vehicles; each card has image + specs + Reserve",
      "feature": "Tahoe spotlight module reused",
      "data_testids": {"section": "fleet-page"}
    },
    "experience": {
      "layout": "Hospitality narrative: 5 blocks with alternating image/text; gold rules between",
      "data_testids": {"section": "experience-page"}
    },
    "reviews": {
      "layout": "Hero + rating summary + full list; carousel reused at top",
      "data_testids": {"section": "reviews-page"}
    },
    "book": {
      "layout": "Hero-lite + booking form + reassurance panel (discretion/privacy)",
      "form": "shadcn Form + Input/Select/Textarea",
      "data_testids": {"section": "book-page"}
    },
    "contact": {
      "layout": "Two-column: contact form + direct lines (phone/email) + hours",
      "data_testids": {"section": "contact-page"}
    },
    "corporate_inquiry": {
      "layout": "Form-first page with corporate fields + SLA expectations",
      "data_testids": {"section": "corporate-inquiry-page"}
    },
    "thank_you": {
      "layout": "Minimal confirmation + next steps + call button",
      "data_testids": {"section": "thank-you-page"}
    },
    "privacy_terms": {
      "layout": "Ivory background reading page; ink text; gold rules; max-w-[75ch]",
      "data_testids": {"section": "legal-page"}
    }
  },
  "imagery": {
    "overlay": {
      "hero": "rgba(11,11,11,0.85)",
      "standard": "rgba(11,11,11,0.28)",
      "strong": "rgba(11,11,11,0.40)",
      "desaturation": "filter: saturate(0.85) contrast(1.05)"
    },
    "ratios": {
      "hero": "21:9 or 16:9",
      "fleet_feature": "16:10",
      "service_tiles": "no image inside tile (icon only) to avoid generic visuals",
      "atlanta_grid": "1:1",
      "instagram_strip": "1:1"
    },
    "image_urls": [
      {
        "category": "hero",
        "description": "Cinematic black vehicle at night; apply 85% overlay + parallax",
        "url": "https://images.unsplash.com/photo-1697908833194-e29be25dea12?crop=entropy&cs=srgb&fm=jpg&ixlib=rb-4.1.0&q=85"
      },
      {
        "category": "fleet_feature",
        "description": "Black-on-black vehicle detail shot; apply 28–35% overlay",
        "url": "https://images.unsplash.com/photo-1518466088889-82466d82e1ba?crop=entropy&cs=srgb&fm=jpg&ixlib=rb-4.1.0&q=85"
      },
      {
        "category": "private_aviation_accent",
        "description": "Private jet cabin mood shot for Experience page blocks",
        "url": "https://images.unsplash.com/photo-1564370086346-46159b3d01fd?crop=entropy&cs=srgb&fm=jpg&ixlib=rb-4.1.0&q=85"
      },
      {
        "category": "atlanta_identity",
        "description": "Atlanta skyline / night identity grid",
        "url": "https://images.pexels.com/photos/12181718/pexels-photo-12181718.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=650&w=940"
      }
    ]
  },
  "motion": {
    "principles": [
      "Smooth, intentional, restrained",
      "No bounce/elastic",
      "Hero parallax only",
      "Fade-up on scroll for content blocks"
    ],
    "framer_scaffold_js": {
      "fadeUp": "export const fadeUp = { hidden: { opacity: 0, y: 18 }, show: { opacity: 1, y: 0, transition: { duration: 0.65, ease: [0.22, 1, 0.36, 1] } } };",
      "stagger": "export const stagger = { show: { transition: { staggerChildren: 0.08 } } };"
    },
    "hover_states": {
      "service_tile": "translateY(-4px) + background shift to purple",
      "buttons": "translateY(-1px) + sheen",
      "links": "underline offset + gold"
    },
    "reduced_motion": "Respect prefers-reduced-motion: disable parallax and auto-scroll carousel."
  },
  "accessibility": {
    "contrast": "White/ivory on ink must meet WCAG AA; gold used for accents only (avoid long gold paragraphs).",
    "focus": "Visible gold ring on all interactive elements.",
    "keyboard": "Nav drawer, carousel controls, form fields fully keyboard accessible.",
    "alt_text": "All images require descriptive alt text; avoid keyword stuffing."
  },
  "seo": {
    "landmarks": "Use header/main/footer landmarks; section headings in order.",
    "meta": "Unique title/description per route; OpenGraph images use hero treatment."
  },
  "instructions_to_main_agent": [
    "Replace default CRA App.css centering patterns; do not use .App { text-align:center }.",
    "Update /app/frontend/src/index.css tokens to match locked palette; set default background to ink and text to white/ivory.",
    "Implement Nav with scroll state (transparent→solid) and mobile Sheet drawer; add data-testid attributes.",
    "Build Home page with 10 sections exactly as blueprint; insert 1px gold rules between major sections.",
    "Services tiles must follow: ink bg + gold 3px top border + ivory text; hover purple + translateY(-4px).",
    "Booking form uses shadcn Form/Input/Select/Textarea; conditional flight number field; luxury dark inputs.",
    "Add mobile sticky bottom CTA bar with CALL NOW + RESERVE YOUR EXPERIENCE.",
    "Use Framer Motion fade-up variants; no bounce; parallax only on hero background.",
    "Add crest watermark SVG (gold at 15% opacity) behind Brand Promise section."
  ]
}

<General UI UX Design Guidelines>  
    - You must **not** apply universal transition. Eg: `transition: all`. This results in breaking transforms. Always add transitions for specific interactive elements like button, input excluding transforms
    - You must **not** center align the app container, ie do not add `.App { text-align: center; }` in the css file. This disrupts the human natural reading flow of text
   - NEVER: use AI assistant Emoji characters like`🤖🧠💭💡🔮🎯📚🎭🎬🎪🎉🎊🎁🎀🎂🍰🎈🎨🎰💰💵💳🏦💎🪙💸🤑📊📈📉💹🔢🏆🥇 etc for icons. Always use **FontAwesome cdn** or **lucid-react** library already installed in the package.json

 **GRADIENT RESTRICTION RULE**
NEVER use dark/saturated gradient combos (e.g., purple/pink) on any UI element.  Prohibited gradients: blue-500 to purple 600, purple 500 to pink-500, green-500 to blue-500, red to pink etc
NEVER use dark gradients for logo, testimonial, footer etc
NEVER let gradients cover more than 20% of the viewport.
NEVER apply gradients to text-heavy content or reading areas.
NEVER use gradients on small UI elements (<100px width).
NEVER stack multiple gradient layers in the same viewport.

**ENFORCEMENT RULE:**
    • Id gradient area exceeds 20% of viewport OR affects readability, **THEN** use solid colors

**How and where to use:**
   • Section backgrounds (not content backgrounds)
   • Hero section header content. Eg: dark to light to dark color
   • Decorative overlays and accent elements only
   • Hero section with 2-3 mild color
   • Gradients creation can be done for any angle say horizontal, vertical or diagonal

- For AI chat, voice application, **do not use purple color. Use color like light green, ocean blue, peach orange etc**

</Font Guidelines>

- Every interaction needs micro-animations - hover states, transitions, parallax effects, and entrance animations. Static = dead. 
   
- Use 2-3x more spacing than feels comfortable. Cramped designs look cheap.

- Subtle grain textures, noise overlays, custom cursors, selection states, and loading animations: separates good from extraordinary.
   
- Before generating UI, infer the visual style from the problem statement (palette, contrast, mood, motion) and immediately instantiate it by setting global design tokens (primary, secondary/accent, background, foreground, ring, state colors), rather than relying on any library defaults. Don't make the background dark as a default step, always understand problem first and define colors accordingly
    Eg: - if it implies playful/energetic, choose a colorful scheme
           - if it implies monochrome/minimal, choose a black–white/neutral scheme

**Component Reuse:**
	- Prioritize using pre-existing components from src/components/ui when applicable
	- Create new components that match the style and conventions of existing components when needed
	- Examine existing components to understand the project's component patterns before creating new ones

**IMPORTANT**: Do not use HTML based component like dropdown, calendar, toast etc. You **MUST** always use `/app/frontend/src/components/ui/ ` only as a primary components as these are modern and stylish component

**Best Practices:**
	- Use Shadcn/UI as the primary component library for consistency and accessibility
	- Import path: ./components/[component-name]

**Export Conventions:**
	- Components MUST use named exports (export const ComponentName = ...)
	- Pages MUST use default exports (export default function PageName() {...})

**Toasts:**
  - Use `sonner` for toasts"
  - Sonner component are located in `/app/src/components/ui/sonner.tsx`

Use 2–4 color gradients, subtle textures/noise overlays, or CSS-based noise to avoid flat visuals.
</General UI UX Design Guidelines>
