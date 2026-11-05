# E. coli metabolic network visualization

**[Open the interactive map](https://juanlaigle-hub.github.io/metabolic-network-visualization/red_metabolica.html)** · [versión en español](#español)

Interactive map of *E. coli* central metabolism with flux distributions computed by **flux balance analysis (FBA)** on the genome-scale model **iJO1366**, under anaerobic conditions with glucose as the only carbon source. Two scenarios can be switched on the page:

| Scenario | Objective | Result |
| --- | --- | --- |
| **Wild type** | Maximum growth | μ = 0.24 h⁻¹ with **mixed-acid fermentation**: formate 17.3, acetate 8.2, ethanol 8.1 mmol/gDW/h (≈ 2 : 1 : 1, as measured in anaerobic cultures) |
| **Ideal ethanol strain** | Maximum ethanol | 2 ethanol + 2 CO₂ per glucose (theoretical yield) through full glycolysis and pyruvate dehydrogenase; 2 ATP per glucose left for maintenance |

## The model

| | |
| --- | --- |
| Genome-scale model | iJO1366 (BiGG) |
| Reactions | 2,583 |
| Metabolites | 1,805 |
| Genes | 1,367 |
| Map | *E. coli* core metabolism, 95 reactions drawn |

## Method

- **COBRApy**, parsimonious FBA (pFBA): among the optimal solutions, the one with the least total flux. Plain FBA returned an alternative optimum with futile cycles (oxidative pentose phosphate pathway, transhydrogenase and nucleotide loops) that are not physiological.
- No oxygen (`EX_o2_e = 0`), glucose uptake 10 mmol/gDW/h, non-growth ATP maintenance ≥ 3.15 mmol/gDW/h.
- The F6PA aldolase (*fsaA*) is blocked: the model uses it as a free shortcut around PFK and FBA, but its in-vivo activity is marginal.
- Ideal strain: ethanol is maximized and then, with it fixed, maintenance ATP, so the surplus ATP has a defined destination.
- Phenomenology checks: carbon and NADH balances close; product ratios match known anaerobic physiology.

## How to read the map

- Arrows are reactions and circles are metabolites. Colour and thickness show the flux (mmol/gDW/h); the label shows its value.
- Reactions without flux are drawn thin and grey, without a label.
- Wheel or pinch to zoom, drag to pan, hover a reaction for details; search and full screen are on the left toolbar.
- The page works offline: Escher is bundled in `vendor/` (MIT license).

## Tools

COBRApy · Escher · Python

---

## Español

Mapa interactivo del metabolismo central de *E. coli* con flujos calculados por **análisis de balance de flujos (FBA)** sobre el modelo genómico **iJO1366** (2583 reacciones, 1805 metabolitos, 1367 genes), sin oxígeno y con glucosa como única fuente de carbono. La página permite elegir entre dos escenarios:

- **Cepa salvaje, máximo crecimiento:** μ = 0,24 h⁻¹ con **fermentación ácido-mixta** (formiato 17,3; acetato 8,2; etanol 8,1 mmol/gDW/h, relación ≈ 2 : 1 : 1, como en cultivos anaeróbicos).
- **Cepa ideal, máximo etanol:** 2 etanol + 2 CO₂ por glucosa (rendimiento teórico), por glucólisis completa y piruvato deshidrogenasa; quedan 2 ATP por glucosa para mantenimiento.

Se usa FBA parsimonioso (pFBA) porque el FBA simple daba una solución con ciclos fútiles que no son fisiológicos, y se bloquea la aldolasa F6PA (*fsaA*), que el modelo usa como atajo. Se abre `red_metabolica.html` en el navegador, sin instalar nada.

Autor: [Juan Laiglecia](https://www.linkedin.com/in/juanlaiglecia) · [Ingeniería VR](https://www.ingenieriavr.com)
