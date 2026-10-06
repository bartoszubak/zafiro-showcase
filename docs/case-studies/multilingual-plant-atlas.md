# Multilingual plant publishing

[Back to the showcase](../../README.md) · [Browse Plant Atlas](https://playzafiro.com/garden-planner/plant-atlas/en/)

Plant Atlas is a searchable horticultural catalog in English, Polish, German, French and Spanish. Its publishing model connects botanical identity, localized information and the pages readers can actually visit.

## Context

A plant profile combines mature dimensions, growing conditions, care, garden use and imagery. Adding languages introduces more than translated paragraphs: a name in search, a page title and a language-switch destination must still refer to the same plant.

At the same time, a new profile can have finished text while its imagery or another language version is still being prepared. The existence of content alone does not make it ready for publication.

## Decision: organize around a shared plant identity

Plant Atlas keeps a common identity for the plant while giving each language its own presentation. Localized names and explanatory text can develop without turning every translation into a separate botanical record.

The catalog supports discovery by common or botanical name. Search labels, profile pages and language navigation all need to agree on which plant is being presented.

**Trade-off:** shared identity reduces ambiguity across languages, but localized names, search terms and descriptions still require deliberate editorial work. Supporting five languages does not imply that translations create or review themselves.

## Decision: publish available language versions deliberately

Public visibility depends on both the plant and the requested language version being published. Missing translations are not silently replaced with English profiles. Public route generation and language destinations follow the content that is available.

For example, writing a French description does not by itself make that profile public. Its language version must also cross the publication boundary. Conversely, a missing version should not be advertised as a working destination just because other languages exist.

This applies to discoverability as well as navigation. Localized titles, page descriptions and alternate-language relationships are part of publishing quality. They are not evidence of search-engine indexing or ranking.

## Decision: distinguish authored content from a release

The publishing workflow assesses content structure, locale readiness and media readiness before preparing public output. Preview and public content serve different purposes: preparation can include unfinished work while the public catalog follows publication status.

**Trade-off:** reviewing readiness and producing static output adds a release step. It gives unfinished content a place to develop without automatically presenting it as a complete profile. A source inventory, a prepared release and the deployed catalog therefore describe different things.

## Decision: remain independent of the 3D editors

Plant Atlas uses TypeScript, React and Next.js to produce static public pages. Botanical content and discovery belong to Atlas; the surrounding website presents the resulting output through a separate boundary.

A useful plant profile does not require a matching 3D model. The Atlas can stand on its own, and its placement on the Zafiro website does not establish a finished plant-to-model integration.

## Result

Readers get a searchable catalog with language-specific plant information. The implementation ties public availability to content readiness and retains a clear boundary between the content product and the 3D applications.

The useful engineering outcome is that identity, localization and publication can be discussed together without conflating prepared content with deployed content. The full dataset, authoring contracts and operational release procedures remain outside this showcase.
