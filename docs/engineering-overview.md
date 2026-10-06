# Shared foundation, separate products

[Back to the showcase](../README.md)

Garden planning and terrain authoring both need an interactive 3D world. They differ in what users create, how tools behave and what it means to save or share their work. Zafiro separates those product decisions from the technology that presents the scene.

## Where responsibilities belong

| Area | Responsibility |
| --- | --- |
| Shared 3D foundation | Rendering, world lifecycle, common environmental behavior and selected reusable scene capabilities. |
| Garden Planner | Garden layout, editing tools, local projects and the garden publication experience. |
| Isle Lab | Terrain authoring, environment controls and world-building interactions. |
| Plant Atlas | Botanical information, language-specific content, discovery and public content output. |

The [product map](../README.md#three-products) shows these relationships. Plant Atlas shares the ecosystem with the editors while remaining independent of their 3D runtime.

## Share capabilities with clear owners

The shared foundation provides scene presentation and lifecycle support. Product workflows decide how people use those capabilities. A rendering concern can be shared without making garden-design rules part of a terrain editor.

Reusable functionality also has different levels of responsibility. Low-level rendering, scene content and publication behavior need not become one undifferentiated engine. Keeping their purposes distinct makes it easier to identify which part should change when a product gains a new feature.

**Trade-off:** a product needs integration work to use shared capabilities. That work creates an explicit place to adapt them to its behavior and makes responsibility for a change easier to identify.

## Preserve the design beyond the rendered scene

An interactive scene contains temporary presentation state as well as the user's work. Garden Planner retains an authored project representation that can be validated, saved and reopened. A published view has a separate role from the editing session and the local saved project.

For example, changing a local garden after publication should not be confused with editing a shared live document. The public experience represents a published snapshot, while further design work belongs to the editor.

The plan overlay is another presentation of garden information. Its current role is inspection: it reads the garden state and presents a plan view. It is not a complete second authoring environment, and this showcase does not claim plan-document or PDF export.

**Trade-off:** several views and lifecycle stages need to stay consistent with the authored design. Validation and explicit state ownership make those boundaries easier to reason about, but do not remove the need to check each user journey.

[Read the garden lifecycle case study](case-studies/garden-project-lifecycle.md)

## Give content its own lifecycle

Plant Atlas has a different unit of work: a plant profile and its language versions. It can provide useful plant information without loading a 3D editor or resolving a plant into a model.

Its static output can be presented within the Zafiro website through a separate publishing boundary. Sharing a website address does not make Atlas a runtime dependency of Garden Planner, or establish a finished plant-to-model integration.

**Trade-off:** content readiness and website delivery must be coordinated. A clear boundary keeps botanical publishing decisions with the content product while leaving editor behavior with the editors. It does not imply that the surrounding release process can always skip work on the host website.

[Read the multilingual publishing case study](case-studies/multilingual-plant-atlas.md)
