---
# ══════════════════════════════════════════════════════════════════════════════
# HOME PAGE
#
# The home page is built from "sections" (blocks) stacked top to bottom.
# Edit the text inside each block. To reorder, move a whole block (from its
# "- block:" line down to the next one). Keep the indentation exactly as it is.
# Block reference: https://hugoblox.com/blocks/
# ══════════════════════════════════════════════════════════════════════════════
title: ''
summary: ''
date: 2026-10-01
type: landing

sections:
  # ── 1. Big banner at the top ──────────────────────────────────────────────
  - block: hero
    content:
      eyebrow: European Research Council · Ghent University
      title: FROST - Frozen in Time
      text: At the northern edge of the habitable world, the final Ice Age people of Europe watched as forests gave way and the reindeer herds returned. How did people adpt to their new environment during the Younger Dryas? FROST sets out to unravel how this abrupt climate shift and the environmental change that followed shaped the human recolonisation of Western Europe.
      primary_action:
        text: Explore the research
        url: research/
        icon: arrow-right
        style: gradient
      secondary_action:
        text: Meet the team
        url: team/
        style: ghost
    design:
      css_class: "dark"
      spacing:
        padding: ["6rem", 0, "6rem", 0]
      background:
        color: "#0f2433"
        gradient:
          type: radial
          start: "rgba(43,93,125,0.65)"
          end: "transparent"
          position: "50% -10%"
          shape: ellipse
          size: "90% 80%"
        gradient_mesh:
          enable: true
          style: orbs
          intensity: low
          animation: none
          colors: ["primary-400/20", "secondary-500/15"]
          orb_count: 2
          positions: ["top-1/4 left-1/5", "bottom-1/4 right-1/5"]
          sizes: ["w-[30rem] h-[30rem]", "w-[22rem] h-[22rem]"]

  # ── 2. Key numbers ────────────────────────────────────────────────────────
  - block: stats
    content:
      items:
        - statistic: "30"
          description: |
            study sites
        - statistic: "5"
          description: |
            countries
        - statistic: "5"
          description: |
            research strands
        - statistic: "~1,200"
          description: |
            years of cold
    design:
      layout: minimal
      numbers_gradient: true
      css_class: "bg-white dark:bg-gray-900"
      spacing:
        padding: ["3rem", 0, "2rem", 0]

  # ── 3. The question, in plain words ───────────────────────────────────────
  - block: markdown
    id: question
    content:
      title: A climate shock in a newly resettled world
      text: |-
        At the end of the Ice Age, hunter-gatherers gradually **recolonised Western Europe** after a retreat of several millennia. An abrupt climactic shift known as the **Younger Dryas** (c. 12,850 to 11,650 cal BP), plunged temperatures across the continent . Archaeological sites dropped sharply in number, raising questions about **population decline, migration and adaptation**. How people actually responded remains poorly understood.

FROST investigates how climate fluctuations within the Younger Dryas affected **human populations, mobility, subsistence and the ecosystems they relied on**. We combine palaeoclimate, palaeoecological and archaeological evidence from **30 key sites** across Western Europe, using:

- **Speleothems** isotopes, trace elements
- **Pollen and sedaDNA**
- **Sediments** granulometry, MS, LOI, micromorphology
- **Reindeer remains** 

All of it is anchored by high-resolution dating: **radiocarbon, OSL, U/Th and tephrochronology**.

The project tackles four challenges: **reconstructing regional climate variability**, **assessing ecosystem responses**, **tracking reindeer herd movements**, and **refining the timing and spatial patterns of human occupation**. Feeding these into demographic and spatiotemporal models, FROST will show how prehistoric populations adapted to environmental change, with insights that also speak to **today's climate challenges**.

What I did: [Why this matters →](about/)
    design:
      columns: '1'
      spacing:
        padding: ["2rem", 0, "3rem", 0]

  # ── 4. The five research strands (work packages) ──────────────────────────
  - block: focus-areas
    id: research
    content:
      title: Five lines of evidence
      subtitle: Each work package tackles one piece of the puzzle; the fifth brings them together.
      items:
        - name: Climate in the caves
          description: Stalagmites grow layer by layer. Their chemistry records temperature and rainfall at a resolution of decades.
          icon: hero/sun
          gradient: from-sky-700 to-slate-800
          topics: [Speleothems, Stable isotopes, U/Th dating]
          cta:
            text: Work package 1
            url: research/wp1-palaeoclimate/
        - name: Reading the landscape
          description: Cores of peat, lake mud and cave sediment reveal how vegetation, soils and water changed around the sites.
          icon: hero/globe-europe-africa
          gradient: from-slate-600 to-stone-800
          topics: [Pollen, Sedimentary DNA, Micromorphology]
          cta:
            text: Work package 2
            url: research/wp2-palaeoenvironment/
        - name: Following the reindeer
          description: Isotopes in reindeer teeth show where the animals spent each season, and so where their hunters had to be.
          icon: hero/map
          gradient: from-amber-700 to-stone-800
          topics: [Strontium, Oxygen, Carbon]
          cta:
            text: Work package 3
            url: research/wp3-reindeer/
        - name: Putting dates on people
          description: New radiocarbon dates on butchered bone, and OSL dating with invisible volcanic ash, sharpen the timeline of occupation.
          icon: hero/clock
          gradient: from-cyan-800 to-slate-900
          topics: [Radiocarbon, OSL, Cryptotephra]
          cta:
            text: Work package 4
            url: research/wp4-chronology/
        - name: Human responses
          description: Combining every strand to model population change and map where people could, and could not, live.
          icon: hero/user-group
          gradient: from-stone-600 to-slate-900
          topics: [Population modelling, Niche models, GIS]
          cta:
            text: Work package 5
            url: research/wp5-human-responses/
    design:
      layout: cards
      css_class: "bg-slate-50 dark:bg-gray-900/50"

  # ── 5. Latest news (shows the 3 newest posts from content/news/) ───────────
  - block: collection
    id: news
    content:
      title: Latest news
      subtitle: Fieldwork diaries and project updates
      count: 3
      filters:
        folders:
          - news
      order: desc
    design:
      view: article-grid
      columns: 3
      show_read_time: false

  # ── 6. Call to action ─────────────────────────────────────────────────────
  - block: cta-card
    content:
      title: Get in touch
      text: Are you a researcher, journalist, teacher or museum interested in the Younger Dryas or the FROST sites? We'd be glad to hear from you.
      button:
        text: Contact the team
        url: contact/
    design:
      card:
        css_class: 'bg-gradient-to-br from-primary-700 via-primary-800 to-slate-900 text-white shadow-xl'
        css_style: ''
---
