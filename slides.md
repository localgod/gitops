---
# try also 'default' to start simple
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://cover.sli.dev
# some information about your slides (markdown enabled)
title: Welcome to Slidev
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# apply UnoCSS classes to the current slide
class: text-center
# https://sli.dev/features/drawing
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations.html#slide-transitions
transition: slide-left
# enable MDC Syntax: https://sli.dev/features/mdc
mdc: true
---

# Welcome to Slidev

Presentation slides for developers

<div @click="$slidev.nav.next" class="mt-12 py-1" hover:bg="white op-10">
  Press Space for next page <carbon:arrow-right />
</div>

<div class="abs-br m-6 text-xl">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="slidev-icon-btn">
    <carbon:edit />
  </button>
  <a href="https://github.com/slidevjs/slidev" target="_blank" class="slidev-icon-btn">
    <carbon:logo-github />
  </a>
</div>

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---
src: ./pages/01-what-is-slidev.md
---

---
src: ./pages/02-navigation.md
---

---
src: ./pages/03-table-of-contents.md
---

---
src: ./pages/04-code.md
---

---
src: ./pages/05-shiki-magic-move.md
---

---
src: ./pages/06-components.md
---

---
src: ./pages/07-themes.md
---

---
src: ./pages/08-clicks-animations.md
---

---
src: ./pages/09-motions.md
---

---
src: ./pages/10-latex.md
---

---
src: ./pages/11-diagrams.md
---

---
src: ./pages/12-draggable-elements.md
---

---
src: ./pages/imported-slides.md
hide: false
---

---
src: ./pages/13-monaco-editor.md
---

---
src: ./pages/14-learn-more.md
---
