+++
author = "simonduerr"
title = "BioGDP: Free but not suitable for academic publishing"
date = "2024-10-30"
description = "BioGDP is a free platform for creating images but its license prohibits using it in academic publications."
tags = [
    "openscience"
]
weight = 0
+++

<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

>**Disclaimer**: This post was written by an engineer, not by a lawyer. This text does not constitute legal advice.

Recently, Nucleic Acids Research published a new tool by a Chinese team of scientists for creating scientific illustrations using a web interface called: [BioGDP](https://biogdp.com)

{{< figure src="https://github.com/user-attachments/assets/7d1c8771-9aa5-4268-bdf1-88c3dd5c1987" title="Figure 1: BioGDP overview from DOI:10.1093/nar/gkae973. Image CC BY NC Jiang et al." >}}

The authors note the following in comparison to other offers:
>Compared to existing tools, GDP offers distinct advantages. Unlike BioRender's subscription-based model or PhyloPic's limited scope, GDP is dedicated to establishing an open biomedical diagramming ecosystem.

However, from the perspective of openess the platform falls short of its promises. 
The author guidelines for the NAR Database issue mention: 
> By submitting a manuscript to the NAR Database Issue the authors certify that they have every right to bring the underlying data into public domain and accept all legal and ethical responsibility for doing so.
> Authors are encouraged, but not required, to make the contents of their databases freely available as flat or relational files upon request.

BioGDP, while accessible without logging or registration does not have a means to export illustrations in open vector format. There is a PDF export option but this produces images embedded in the PDF.
This locks users into BioGDPs platform to create illustrations and precludes sharing of high quality vector illustrations. Based on using the platform it is clear that the images are vector illustrations internally and the technological restriction to not be able to download them serves to keep users using BioGDP.

The main catch that prevents using BioGDP for academic publishing is the license conditions. First, it is unclear what exactly the academic license is because full terms aren't available on the page at all. 
When exporting an image the platform tells users they can use it for academic work but not-commercially. 

{{< figure src="https://github.com/user-attachments/assets/f78f2fce-5174-45a1-87c1-c3a7ead03ca9" title="Figure 2: BioGDP license conditions when exporting on 30.10.2024" >}}

Now, this is were things get tricky and these are the same problems that BioRender has repeatedly stumbled over but this statement gets the mechanics of academic publishing wrong. 

There are two routes to publish an article: in a closed journal operating in a subscription model and in an open access journal. 

For a closed access journal, the academic authors usually sign a copyright transfer agreement with the journal which gives the journal the copyright over the whole article and the figures. The journal then exerts a commercial activity (even if the publisher is a non-profit) when they sell subscriptions to other academics who want to read the article. 
So even while BioGDP allows publishings in journals, the restriction on commercial use applies and these terms legally contradict each other. 

In the other case of open access publishing depending on the license there are also problems. The standard license for open access journals is CC BY. CC BY allows anyone to reproduce and modify a work even for commercial purposes provided attribution. 
If an author publishes an illustration created in BioGDP in an open access journal under CC BY they give anyone the right to use that work for any purpose. 
They therefore also violate the commercial use restriction in the BioGDP license conditions. 
Note that there are some "open access" journals that use more restrictive licenses such as CC BY NC. In this case, using BioGDP illustrations would be permitted. However, the Berlin Declaration on open access which is generally referred to as the standard definition of the term clearly stipulates that the right to  create derivative works is part of the definition of open access. There is no exception for restricting commercial use wherefore CC BY NC is technically not an open access license. 
Free access but no rights to reuse is generally referred to as public access. This is for example the current policy of the NIH. But most of the big open access journals (like Nature Communications, PLoS One, eLife, Scientific Reports) all use the CC BY license. 

The BioGDP authors in the past also have made threats that they will legally pursue academics who violate the restrictions. They have since changed the wording but overall the license conditions remain unchanged. 

{{< figure src="https://github.com/user-attachments/assets/108ee4df-db93-4780-bccd-ae05599b4476" title="Figure 3: BioGDP license statement on 12.9.2024" >}}

The editor of the NAR Database issue has confirmed that the reviewers inquired with the authors about this:
{{< tweet user="DanielRigden" id="1851540928248381453" >}}

While I agree that credit is due this does not explain how third parties can reuse the images in open access papers without the threat of getting sued by BioGDP. 
The CC BY license allows to make derivatives and does not contain a clause that BioGDP has to be cited. This will create a similar situation as with BioRender where illustrations are nominally published in Open Access journals and the license of the article states that reuse is allowed but actually this is not the case. BioRender has threatend to issue corrections to these papers and given the past language BioGDP might be inclined to do the same.  Dalmeet Singh from ChemistryWorld nicely summarized this here: [ChemistryWorld Thousands of published studies may contain images with incorrect copyright licences](https://www.chemistryworld.com/news/thousands-of-published-studies-may-contain-images-with-incorrect-copyright-licences/4020367.article)
It is obviously the authors right to do this since they put in the effort of creating and maintaining this website, however, in my view this should not have been published in NAR because they way how the license is written now will further pollute the life science literature with copyright violations. 




