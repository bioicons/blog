+++
author = "simonduerr"
title = "Scientific figures are a community resource without a community"
date = "2026-05-01"
description = "We need an infrastructure for scientific figures that works"
tags = [
    "bioicons",
    "openscience"
]
weight = 0
+++


## Current situation bottleneck

You cannot easily take a figure from a scientific paper and adapt it, extract one of its elements to reuse, or find the data behind it. Even though most figures start at some form of raw data, which is processed into an editable document (via Python, via Illustrator) the final figure is usually just a pixel image. This has barely changed since the early 2000s. 

A few attempts to change this have been undertaken but with little success. Executable-article pilots like eLife ERA shipped but never gained traction (especially in non-computational fields), and schematic figures were never in scope for these tools anyway. Meanwhile researchers keep producing figures with a mix of proprietary tools (BioRender alone claims >100,000 published figures and >4M users) and general-purpose vector software. Also figures got increasingly more complex (e.g  the number of panels per paper has grown dramatically). In the vast majority of papers the data pipeline behind the plots is not accessible (although to be fair some journals link an Excel file below). Similarly, in schematic figures (often Figure 1), none of the visual elements are linked to the entities they represent, none of the relationships ("activates", "binds", "is located in") are encoded, and none of the underlying images has their provenance indicated. The databases for this exist (e.g the great BioImage Archive) but the connection between the figure printed in the publication and the data is seldomly made.   

The pressure on this gap is now acute from a direction that did not exist few years ago: generative AI. Frontier multimodal models can now produce complex scientific figures, but they hallucinate components and silently alter data. The bottleneck to improve these models nowadays is not model capacity, it is better data to have them stick to reality better (especially when generating schematic scientific figures). However, there is no public corpus of scientific figures paired with their semantic structure, so we cannot train, fine-tune, ground, or benchmark these systems against the biological knowledge already curated in many databases such as UniProt, InterPro, or OpenTargets. 

## The market is not going to build this

It is tempting to call this a tools problem and wait for a better BioRender or another company to build it. I think this would be the wrong diagnosis. The deeper problem is that **scientific figures are a community resource that no community owns**. Most researchers are not conscious of the fact that we have lost ownership of our figures and that instead of publishing more data we also need to valorize the data in the current papers we produce to the maximum. This means connecting the narrative to the data more directly. I want to be able to click on a figure and be directly taken to the relevant source (e.g in the PDB or in the Bioimage Archive). This will also help agents to parse science better and make science more reproducible. 

I see many parallels for example with the PDB and arXiv. In 1971, a few crystallographers bootstrapped what became the Protein Data Bank because structural data was disappearing into individual labs. In 1991, Paul Ginsparg started arXiv because sending preprints via emails became laborious. In both cases the underlying object (a structure, a paper) already existed; what was missing was a shared, maintained, addressable place to put it and community consensus to do so. The same pattern repeats further up the data stack with UniProt for protein data, ChEMBL for bioactivities, the BioImage Archive for microscopy, and OpenTargets for target-disease associations: every layer of biological knowledge eventually got its commons, except the layer that ties them together visually. Figures are stuck in the pre-PDB, pre-arXiv state. What we need is a way to connect the visual narrative to the underlying data and concepts.   Currently, this is not happening because: 

- The technological solutions proposed so far were too complicated
- The market for illustration has plenty of SaaS tools that people love to use but that are expensive (e.g BioRender at $900M valuation) with a perpetual cost and platform lock-in.
- Publishers have no incentive to invest in a new infrastructure that further modularizes the research paper because that might interfere with their business model. 


## Some hypotheses about scientific figures


**H1: A small, fixed visual vocabulary covers most of life-science figure content.** The hypothesis is that across published life-science figures, the long tail of unique drawn elements is reasonably big. Concretely: a vocabulary of ~2,000–5,000 standardized icons, plus a small set of relation types, is sufficient to reconstruct the semantic content of >80% of figures in a representative journal sample. If this is true, building a complete vocabulary is a tractable, probably costs around the subscription of a single instituion to BioRender (e.g 750k $ for Max Planck Society) and the case for funding it changes accordingly. If false, we need a different strategy that accommodates genuine long-tail visual creativity.

**H2: SVG can already carry everything we need.** Most people assemble figures in some form of vector graphics editor. The standard file format - SVG - is a mature, widely supported format that natively allows arbitrary metadata: persistent identifiers, ontology links, provenance chains, relations between elements, embedded code or data, even full RDF blocks. We do not need a new file format, we need to analyse the existing tools to find out how we can keep as much metadata as possible. If SVG works we can just start to replace jpg with annotated SVGs.

**H3: Multimodal models extract semantic content from scientific figures dramatically better when given annotated SVG than when given a rasterized version of the same figure.** The hypothesis is that input format, not model scale, is the current rate-limit for AI reading of scientific figures. The experiment holds the figure content constant and varies the representation: raster PNG, flattened SVG, SVG with element-level ontology annotations, and SVG with annotations plus typed relations. The implication is that scientific publishing should evolve toward semantic figures regardless of how AI capability evolves. 

**H4: The ability to assemble schematic figures has enough drag that eventually other forms of scientific output will be annotated too.**  Scientists given an open scholarly infrastructure that provides the building blocks for their illustration needs, plus the small benefit of element-level provenance and ontology tags, will adopt it because it solves an immediate pain (cost, reusability, OA compliance). Once those tags are routinely present in figures, the marginal cost of carrying the same identifiers into adjacent outputs (slide decks, posters, lecture notes, grant figures) drops to near zero. The hypothesis is that schematic figures are a Trojan horse for broader semantic annotation of scientific work. If true, the implication is that an open figure infrastructure does not just release figures from the "shackles of the raster format", it seeds a habit to release more scientific figures in open semantic format. 

## Pilot experiments

**Pilot 1: A vocabulary census of life-science figures.** Take a stratified sample of ~2,000 figures from recent papers across cell biology, neuroscience, immunology and structural biology. For each figure, decompose into visual elements and tag each element with the closest match in a candidate vocabulary built from e.g BioIcons, NIH BioArt, and Reactome. Track coverage curves: how many figures are fully reconstructible at vocabulary sizes of 500, 1,000, 2,000, 5,000 icons? Identify the long-tail elements that resist standardization and characterize them. The output is a public dataset and a coverage curve that directly answers H1. Either the curve saturates (the project is finite) or it does not (we learn the structure of what does not standardize).

**Pilot 2: A tool survey of SVG metadata handling.** Construct a small set of reference SVG files containing a controlled set of metadata: standard SVG `<title>` and `<desc>` elements, custom `data-*` attributes, embedded RDF, Dublin Core fields, persistent identifiers in `<metadata>` blocks, and grouping structure. Round-trip these files through every commonly used scientific figure tool and pipeline: Inkscape, Illustrator, Affinity Designer, Figma, draw.io, ... . At each stage, measure exactly which metadata fields survive, which are silently stripped, and which are mangled.

**Pilot 3: A figure-format benchmark for multimodal models.** Curate ~500 scientific figures, each available in four formats: raster PNG, flat SVG, semantically annotated SVG (element-to-ontology), and annotated SVG with typed relations. Evaluate frontier multimodal models on three tasks: entity extraction, relation extraction, and figure-to-text summary fidelity (against ground-truth captions). Hold the model fixed, vary the format. Then hold the format fixed, vary the model size. The benchmark and its results answer H3 and become a reusable evaluation that tracks how the answer changes as models evolve. If the format effect dominates, the case for figures as machine-readable infrastructure is direct and quantitative. If model scale dominates, we have evidence that the bottleneck is elsewhere.

These pilots are intentionally narrow. They do not require building a platform, recruiting a community, or proving a business model. They are measurements about how scientific figures actually work today, and each produces a public artifact that the field can use to decide if a common infrastructure has benefits. We have some prior evidence from the popularity of BioRender that the answer is probably yes, but for allocating funding to it these pilots provide the necessary data. 
This effort naturally should involve a diverse flock of the existing platforms. A mockup of how such annotated figures could look like is available here. My working title for such a service is [figures.bio](https://figures.bio)

## Why now

Multimodal models are now the fastest-growing consumers of the published literature; the bottleneck has visibly shifted from human readers to AI agents that need machine-readable inputs. Also ontology infrastructure has matured. OLS4 now exposes hundreds of biomedical ontologies via an API, making cross-figure semantic annotation tractable in a way it wasn't a decade ago. 

The window to treat this as a public-goods problem, before commercial actors entrench further and before the AI-generation gold rush produces a permanent layer of unverifiable scientific imagery, is open and probably narrowing.

## What kind of entity could do this

Open licensing was designed to break the publishing industry (in the end it did not suceed yet but this is another story). The case of BioRender which operate a platform fundamentally incompatible with CC BY shows that we still have a long way to go. For scientific figures we need an infrastructure such as ORCID, the PDB or DataCite that is running governed by the community under the  [Principles of Open Scholarly Infrastructure](https://openscholarlyinfrastructure.org/) that allows people to easily illustrate their science and at the same time liberates the underlying data and relations and publishes them openly. 