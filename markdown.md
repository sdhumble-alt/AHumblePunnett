# A Humble Punnett Square — Project Documentation

**Application Name:** A Humble Punnett Square  
**Author:** Steven Humble  
**Current Version:** `V1.1.0 — 2026-08-23`  
**Architecture:** Single-file standalone web application (`HTML5` / `CSS3` / `Vanilla JavaScript` / `HTML Canvas API`)  
**External Assets:** Tabler Icons Webfont (`tabler-icons.min.css`) via CDN  

> **MAINTENANCE DIRECTIVE:**  
> **Do not increment or alter the application version number (`V1.1.0`) in the code, header, or documentation unless explicitly directed to do so by the user.**

---

## 1. Overview & Purpose
**A Humble Punnett Square** is an assessment-authoring tool designed for biology teachers, educators, and students. It enables rapid generation, visual customization, and clean image exporting of standard and complex Punnett squares and their associated mathematical answer keys (genotypic and phenotypic breakdowns).

The application conforms to the design language established by **A Humble Plotter** and **A Humble Quick Plot**, featuring an independently scrollable split-pane interface, dark-navy branding, Tabler icons, neutral card groupings, and dedicated HTML5 canvas rendering pipelines.

---

## 2. Core Feature Matrix

### Cross Configurations
* **Monohybrid ($2 \times 2$):** Single-gene inheritance analysis.
* **Dihybrid ($4 \times 4$):** Two-locus independent assortment with automatic FOIL gamete generation ($A_1B_1$, $A_1B_2$, $A_2B_1$, $A_2B_2$).

### Supported Inheritance Mechanics
1. **Complete Dominance:** Uppercase dominant alleles mask lowercase recessive alleles.
2. **Incomplete Dominance (Blending):** Heterozygotes express an intermediate/blended phenotype ($C^R C^W \rightarrow$ Blend).
3. **Co-Dominance:** Both alleles are visibly co-expressed simultaneously ($I^A I^B$, roan coats, dual antigens).
4. **Sex-Linked (X-Linked Recessive & Dominant):** 
   * Configurable condition mode (X-Linked Recessive vs. X-Linked Dominant).
   * Automatically groups females into Unaffected, Carrier, or Affected based on condition mode.
   * Toggleable aggregation mode: Group results by Sex (Female vs. Male tables) or display overall population frequencies irrespective of gender.

### Centralized Gene & Phenotype Definition
* Users define the base allele symbols (e.g., $B$/$b$, $X^B$/$X^b$, $C^R$/$C^W$) and custom trait descriptions in a single **Gene & Phenotype Setup** card.
* Parents are selected via **dynamic dropdown menus** populated directly from defined alleles.

### Text Engine & Allele Notation
* **Caret (`^`) and Underscore (`_`) Parsing:** Standard text inputs render inline superscripts and subscripts directly onto the canvas (e.g., `X^B`, `X^b`, `I^A`, `I^B`, `i`, `C^R`, `A_1`).
* **Genetics-Aware Sorting Comparator:** 
  * Enforces genetic notation conventions ($X > Y$, Dominant/Uppercase $>$ Recessive/Lowercase).
  * Clinical Phenotype Sort Order: Solutions sort by clinical hierarchy (**Affected $\rightarrow$ Carrier $\rightarrow$ Unaffected**).

### Customization & Styling
* **Custom Parent Labels:** Text fields allow custom italicized labels (e.g., *Maternal*, *Paternal*, *F1 Generation*) on the top and left axes.
* **Parent Axis Colors:** Dedicated color pickers with accessible Okabe-Ito palettes for Parent 1 and Parent 2 gametes.
* **Parent Axis Separators:** Toggleable dashed divider extensions that project into header margins.
* **Trait Key / Legend Box:** Renders an allele key directly to the right of the square with a dedicated toggle to show/hide carrier states.
* **Square Fill Modes:** Toggle between Complete (Answer Key) and Blank Grid (Student Worksheet).
* **Zero-Frequency Outcomes Toggle:** Option to display theoretical outcomes with 0% occurrence ($0/4$ or $0/16$).

---

## 3. Architecture & Data Flow