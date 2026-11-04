# E. coli metabolic network visualization

Interactive map of *E. coli* central metabolism with a flux distribution computed by **flux balance analysis (FBA)** on the genome-scale model **iJO1366**.

Open [`red_metabolica.html`](red_metabolica.html) in a browser. It is a single self-contained file: no installation, no server.

## The model

| | |
| --- | --- |
| Genome-scale model | iJO1366 (BiGG) |
| Reactions | 2,583 |
| Metabolites | 1,805 |
| Genes | 1,367 |
| Map | *E. coli* core metabolism, 95 reactions drawn |

## The scenario

The fluxes on the map come from solving the model as a linear program (FBA) with COBRApy under anaerobic conditions, with glucose as the only carbon source:

- Glucose uptake: 10 mmol/gDW/h
- Ethanol secretion: 20 mmol/gDW/h, and CO₂: 20 mmol/gDW/h, which is the theoretical yield of 2 mol of ethanol per mol of glucose
- Non-growth ATP maintenance: 3.15 mmol/gDW/h
- 39 reactions carry flux and are highlighted on the map, from glycolysis to pyruvate decarboxylation and alcohol dehydrogenase

It shows how a genome-scale model turns into a concrete answer, such as which pathway the cell uses and how much product it can make, and how to present that answer so a non-specialist can follow it.

## Tools

- **COBRApy:** loading the model, setting the constraints and solving the FBA linear program
- **Escher:** drawing the metabolic map and overlaying the reaction fluxes
- **Python**

## How to read the map

- Arrows are reactions and circles are metabolites.
- Colour and thickness show the flux through each reaction.
- Use the menu to zoom, search for a reaction or metabolite, and switch to full screen.

---

**Español.** Mapa interactivo del metabolismo central de *E. coli* con una distribución de flujos calculada por análisis de balance de flujos (FBA) sobre el modelo genómico iJO1366, de 2.583 reacciones, 1.805 metabolitos y 1.367 genes. El escenario es anaeróbico con glucosa como única fuente de carbono: el modelo predice fermentación a etanol con el rendimiento teórico de 2 mol de etanol por mol de glucosa. Se abre `red_metabolica.html` en el navegador, sin instalar nada.

Autor: [Juan Laiglecia](https://www.linkedin.com/in/juanlaiglecia) · [Ingeniería VR](https://www.ingenieriavr.com)
