+++
author = "simonduerr"
title = "Mining BioRender illustrations from Open Access articles"
date = "2024-04-30"
description = "Dataset of articles that use BioRender that would allow to reuse the figures in them for any purpose"
tags = [
    "biorender",
    "openscience"
]
weight = 0
+++

## Backstory

When I launched [BioIcons](https://bioicons.com) 2 years ago, I was overwhelmed by the positive response of the community to this new free resource of scientific illustrations in vector format. Originally, the database aggregated some other databases such as Servier Medical Art with permissive license (such as CC BY) but with sometimes not ideal format (e.g Microsoft PowerPoint) and illustrations submitted by researchers. The database has steadily grown in the last two years from 700 icons at launch to now about 2538 illustrations. However, the database is still too small to compete with commercial providers such as [BioRender](https://biorender.com) or [MindTheGraph](https://mindthegraph.com). 

## Where to find more illustrations?

I first tried to convince funding agencies to invest money into BioIcons to increase the size of the database. Unfortunately, all my 6 funding applications so far have been rejected. For many of the applications the project did not fit well in the scopes of funding programmes, yet it is clear to me that a database of open scientific illustrations will save many hours of time for scientists and reduce cost drastically compared to commercial alternatives. 

To increase the size of the catalog I therefore thought to myself, why not extract new illustrations from existing Open Access articles under open license. This is totally in line with the goals of the Open Access movement to reuse existing research to the fullest extent possible. 

BioRender is a commercial service to draw biomedical illustrations and requires all created illustrations to be attributed with the phrase "Created with biorender.com". It is relatively easy to do a full text search for this term to find articles containing figures from BioRender released under an Open Access license, that could be made availabe on BioIcons. For this the article and the illustration need to be available under CC BY 4.0 license so that reuse for any purpose is possible provided that BioRender and the authors of the article are credited. This might sound like stealing BioRender's intellectual property but since scientists paid for premium licenses to use the illustrations in their work and BioRender retains the copyright over its illustrations reusing these illustrations is perfectly legal - at least theoretically. Before we talk about the actual legal problems of this approach, let's take a look at this dataset:

## Overview of the dataset

Articles were searched via the Springer or Elsevier API or extracted from the search of MDPI, ACS or Wiley webpages. Articles were retrieved if they matched the search term "biorender.com" and labeled as Open Access by the publisher. Of course, this won't yield every single article using BioRender illustrations. Some researchers might use a different wording than the one required by BioRender and this approach might also yield a few false positives if the tool is mentioned in the text.  However, the 100 samples I manually verified were all open access articles that contained BioRender illustrations published as Open Acess. 

Using the public crossref API available metadata with respect to funders, license and author affiliation was extracted where available. 

In total, the dataset contains [12059 papers](https://docs.google.com/spreadsheets/d/1cpDMmKBlNy3ZvkJlIRMIJNaEvlAJ6nf3Q0fAaoj00P8/edit?usp=sharing). Some exploration of the dataset can be found below:


### Publishers

The biggest Open Access publisher in the dataset is SpringerNature with the respective outlets Nature, BioMed Central and Springer. This is followed by Elsevier, Wiley and the American Chemical Society (ACS). 

{{< figure src="/publisher.png" title="Figure 1: Distribution of the publishers" >}}

### Journals

Not surprisingly the biggest individual journals in the dataset are the big open access titles Nature Communications with 1174 papers and Scientific Reports with 784 papers.  
In total, the articles are published in 1810 different journals.

{{< figure src="/journals.png" title="Figure 2: Top 25 journals in the dataset  " >}}


### Funding Agencies

Funding agencies make various requirements to their grantees with respect to open access requirements. The most common funder in the dataset, the US National Institutes of Health (NIH) with 770 papers and the National Science Foundation (NSF) with 217 papers require public sharing but do not yet require Open Access (which includes the right to reuse the work) [^1],[^2]. The National Natural Science Foundation of China (603 papers) and Deutsche Forschungsgemeinschaft(DFG) with 524 papers both signed the Berlin Declaration and the standard license they propose but do not require is CC BY [^2].

The Wellcome Trust (195 papers), the European Research Council (135 papers) or the Swiss National Science Foundation (Schweizerischer Nationalfonds zur Föderung der Wissenschaftlichen Forschung, 114 papers) among many others in the list explicitly require the use of CC BY license [^4],[^5],[^6].

{{< figure src="/funders.png" title="Figure 3: Top 50 funders in the dataset." >}}

### Licenses

The most common license in the dataset is CC BY 4.0, which allows full reuse of the illustrations. Some publications have additional licenses for text mining or other purposes which is labeled "Non CC license in metadata" in the dataset. For some papers no license has been deposited in the metadata ("No license in the metadata"). The papers licensed under CC BY NC ND or any of the other ND licenses cannot be used to extract individual illustrations. Still 9307 papers is a great number of papers to extract illustrations from. All licenses were retrieved from CrossRef with the DOI of the article.

{{< figure src="/licenses.png" title="Figure 4: Histogram of the licenses in the dataset of papers with BioRender illustrations." >}}



## Why we can't use the dataset

With such a big dataset and the obvious business consequences I wanted to be absolutely sure that this extraction of illustrations from Open Access papers is legally sound. 

I have therefore picked two papers as examples which according to the article license would be eligible to extract individual icons from. I asked BioRender if the license is correct and reuse is allowed and after some back and forth since they answered that the authors of both papers chose an invalid license and they will contact the publishers to issue a correction. This is even though the instution (TU Delft) that paid for this license expressely claims that illustrations can be used in Open Access papers[^7].  These two papers are exemplary and they only engaged with me in private even if I asked them publicly last fall: {{< tweet user="simonduerr" id="1714192336865869990" >}}

After determining that the two test examples I sent them were copyright violations, I sent them a further list of 9277 papers for follow-up which are similar in licensing to the two they had marked as wrong. They acknowledged my email but have never responded to any request for follow-up. 

A recent discussion on twitter has brought this problem to attention to the wider community.
{{< tweet user="baym" id="1779249560679801059" >}}

As pointed out the issue is that BioRender claims copyright over all their content even if used in illustrations that researchers create and pay for to publish.  

Even after many thousand people discussing this online the company has not directly responded to users. However, CEO Shiz Aoki which I also personally contacted about these issues this february (without response) promised to work on fixing the language that twitter users criticized about any modifications users make to BioRender content being "work made for hire". It remains open how they address the likely copyright violations reported here. 

Of course, each illustration would need to be individually checked if the illustration has been excluded from the Creative Commons license but for the cases I checked manually this wasn't the case. It also needs to be checked if authors individually got written permission from BioRender to publish the illustrations as CC BY, which I personally doubt many researchers did. BioRender confirmed me that "Created with BioRender.com" does not consitute a valid copyright credit line that would exclude the figure from the Creative Commons license. 

One of the article I sent BioRender (doi: [10.1002/adhm.202301837](https://doi.org/10.1002/adhm.202301837) has the BioRender figure licensed with the license as the article (CC BY) right next to some copyrighted figures reproduced with permission under copyright from a third party that aren't included in the license of the article (see Figure 5).

{{< figure src="/wiley_biorender_example.png" title="Figure 5 Reproduced under CC BY 4.0 Putra et al., Advanced Healthcare Materials, 2023 doi: 10.1002/adhm.202301837. Figure 1a) has invalid copyright according to BioRender. The article also contains third party images excluded from the CC BY license" >}}

So while nominally these articles would be okay to be reused, in practice they are apparently not. In my opinion, it is imperative for BioRender to be more upfront about the limitations of its Premium plan and advise it's users with better copyright guidance. After I complained last year they published a [guide on Creative Commons](https://help.biorender.com/en/articles/8601313-creative-commons-licensing-for-biorender-figures-premium-only) licensing but since many thousand papers already likely violate their copyright this is a bit late. Also this guide is never linked anywhere when exporting illustrations so researchers have to know about not being able to publish CC BY by default or have studied the terms of the academic license in quite some detail. BioRender even asks users whether the journal they are getting the license for is an Open Access journal: ![BioRender permission form](https://pbs.twimg.com/media/GLOtkjBXgAEfH8g?format=jpg&name=large) (image from [this tweet](https://twitter.com/EvolvedBiofilm/status/1779957127760490547/photo/1))

Some publishers like eLife have already made changes to their editorial workflow so that in the future researchers do not unintentionally violate copyright.



[^1]:
    https://publicaccess.nih.gov/faq.htm#814
[^2]:
    https://www.nsf.gov/pubs/2023/nsf23104/nsf23104.pdf
[^3]:
    https://www.dfg.de/formulare/12_21/12_21_de.pdf
[^4]:
    https://wellcome.org/grant-funding/guidance/open-access-guidance/creative-commons-attribution-licence-cc
[^5]:
    https://www.snf.ch/en/33WC4FGNdpfXrqPV/news/immediate-open-access-without-restrictions-changes-as-of-1-january-2023
[^6]:
    https://www.oapen.org/article/13934224-erc-oa-requirement
[^7]:
    https://www.tudelft.nl/en/library/library-for-researchers/publishing-outreach/biorender
