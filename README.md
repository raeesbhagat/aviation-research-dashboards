# Interactive Aviation Research Dashboards

Can collaborators investigate their own cohort questions?

This is a public documentation repository for a connected research workstream in Raee Bhagat’s portfolio. It describes methods and decisions from reviewed project materials. It does not contain the original analysis implementation, participant data, or internal research files.

[Portfolio](https://raeeb.dev/) · [Workstream in the project library](https://raeeb.dev/project-library#P06) · [Detailed case study](https://raeeb.dev/projects/dashboards)

## Research context

Built interactive research interfaces for exploring fatigue and sleep measurements by route, crew, direction, flight phase, and operation type. Larger notebooks combine source-data preparation with reactive filters, plots, participant/trip counts, and data tables. Variants address AMOC versus SSO operations, W/tag trips, time-of-day groups, long-range versus ultra-long-range flights, and flying versus relief crew. This is the clearest application-development evidence in the folder, provided it is described as a research tool and its actual deployment status is kept accurate.

## What the workflow produces

Reactive Shiny interfaces with linked Plotly charts, DT tables, and cohort summaries.

## Methods and decisions

- Reactive programming.
- interactive filters.
- data aggregation.
- cohort comparison.
- exploratory interfaces.
- interactive tables.

## Libraries and tools

`R`, `Shiny`, `shinydashboard`, `Plotly`, `DT`, `ggplot2`, `dplyr`, `tidyr`, `lubridate`, `openxlsx`, `R Markdown`.

These tools are associated with the reviewed workstream. This repository is documentation, so it does not install or execute those libraries.

## Analytical structure

**Unit of analysis:** Participants, trips, and repeated measurements, each counted at its own level.

**Inputs:** Prepared route-level research tables with crew role, operation type, flight phase, sleep, fatigue, and performance measures.

**Output:** Reactive Shiny views with Plotly figures, DT tables, and cohort summaries.

### Prepare before presenting

The Shiny notebooks transform route-level source tables into fields suitable for filtering and display. This preparation includes operational categories and measurement phases so a filter has a defined meaning.

### Reactive dependencies

Route, crew-role, flight-phase, and operation-type selections drive the research views. Shiny reactivity connects selection state to summaries, Plotly charts, and DT tables, reducing the chance that one view represents a different cohort.

### Denominator-aware summaries

A unique participant, a trip, and a measurement row are different units. Counting rows as participants would overstate cohort size whenever a person contributes repeated observations. The display needs to keep these concepts explicit.

### Exploration and interpretation

Interactive plots let collaborators examine subgroup patterns, while tables expose the records behind a view. Sample availability and sparse selections determine how much weight a visual difference deserves.

## Validation and interpretation

- **Empty selections:** A filter combination with no eligible records should show an explicit empty state instead of an old chart.

- **Consistent counts:** Reconcile chart observations and table rows against the same filtered data and separately count distinct participants and trips.

- **Missing outcomes:** Show the number with an observed endpoint; do not let a total cohort count imply complete outcome availability.

- **Filter combinations:** Inspect route × role × phase combinations and avoid comparing groups with incompatible operational definitions.

**Model or calculation:** Selected cohort → shared reactive data → counts + summaries + plots + tables

A shared filtered dataset keeps the denominator consistent across outputs. An exploratory dashboard supports inspection and does not itself establish a confirmatory comparison.

## Where the methods transfer

Interactive analytics products with consistent filter logic and clear denominators.

## Evidence and boundaries

This summary describes analytical work and its interpretation. It is not a certification, a causal claim, or evidence of a deployed production service.

The portfolio contains twenty connected workstreams. Several share datasets, preparation logic, research programs, or legacy code. Separate documentation repositories do not imply twenty independent completed studies or exclusive authorship of all underlying research.

## Privacy and reproducibility

- Original datasets, participant identifiers, internal file paths, workbooks, and unpublished source code are not included.
- Public interactive examples on the portfolio use synthetic teaching data and are labeled accordingly.
- There is no install command, runnable research pipeline, or reproducibility claim for this documentation repository.
- No institutional endorsement or ownership of shared research materials is implied.

## Author and contact

Raee Bhagat · [Portfolio](https://raeeb.dev/) · [LinkedIn](https://www.linkedin.com/in/raee-suresh-bhagat-53168890/) · [Email](mailto:raeesbhagat@gmail.com)
