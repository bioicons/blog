+++
author = "simonduerr"
title = "A short primer on licensing for illustrations"
date = "2023-09-08"
description = "Illuminating the license jungle"
tags = [
    "licensing",
]
weight = 0
+++

<small>

>Adapted from the Turing Way under CC BY 4.0. This document is licensed under CC BY 4.0 and was authored by Simon Dürr @simonduerr 

</small>

## TLDR
The best format to share illustrations is SVG. To facilitate reuse of your illustrations you can share them under CC BY 4.0 or CC0 license before you sign a Journal Copyright Transfer agreement for example on Zenodo. 


## Prerequisites

No previous knowledge is needed, but it is important to understand how licensing can affect your project.

## Goals

<small>

> This chapter was written using American English, in which the word license is a noun and a verb. With British English, however, licence is a noun (as in, to issue a licence), while license is a verb (as in, they licensed the event).
> 

</small>

As with anything else in society, some of what you can and cannot do when sharing illustrations is determined by the law. Most of the constraints in this particular domain stem from intellectual property laws: laws that make abstract things like illustrations or other creative works resemble physical objects by allowing them to be owned.

This chapter aims to give a brief summary of relevant intellectual property laws, explain free and open source licensing, and explain how combining illustrations from different sources works from a legal perspective. It also gives some rules we have worked out to deal with common situations.

## Motivation

Without a license, all rights are with the creator of an illustration, and that means nobody else can use, copy, distribute, or modify the work without consent. A license gives this consent. If you do not have a license for your illustration, it is effectively unusable by the whole research community. When you sign a journal copyright transfer agreement, the journal sometimes is the new owner of your work and can forbid you to use it (In practice they often allow some fair use like in your thesis or in presentations but can forbid e.g commercial reuse in a book). It is important to think about copyright before you publish your work because if you publish your illustrations under open license you will be always able to use it even if you sign over the copyright to a publisher for the publication. 


>Good legal advice is timely, specific, and given by an expert; this chapter is none of these.
>It was written by an engineer, not by a lawyer, and it is a heavily simplified overview of a very complex field.
>The intent is to give you an overview of the basics so that you will know when to check whether something you want to do has potential legal ramifications.
>Do not make any important decisions based solely on the contents of this chapter.


## Legal aspects

### Terms

Licenses for illustration vary based on different criteria, such as:

 * Attribution to original owner 

* Permission to redistribute or modify original

 * Inclusion of the same license with derivatives or redistributions

As a result, accessibility to your illustration is affected by the license (and format) you choose to distribute your illustration.

### Creative Commons Licenses

Creative Commons which is often abbreviated as CC provides a number of licenses that can be used with a wide variety of creations that might otherwise fall under copyright restrictions, including scientific illustrations, music, art, books and photographs.

The CC website includes a [summary page](https://creativecommons.org/about/cclicenses/) outlining all the available licenses, explained with simple visual symbols.

### Permission Levels

The permission level provided by a Creative Commons license can be understood from its name, which is a combination of two-letter “permission marks”. The only exception to this naming scheme is CC0, which will be introduced in the next section.

|Permission Mark | What do I need to do: |
| -------------- | --------------------- |
|BY  | Creator must be credited |
|SA | Derivatives or redistributions must have identical license |
|NC | Only non-commercial uses are allowed |
|ND | No derivatives are allowed |

You can combine the different permission marks to create a license that suits your needs. For example, the CC BY-ND license specifies that users must credit the creator of the illustration and cannot create any derivatives.

### Dedicating Your Work to the Public Domain with CC0

CC0 serves as a public domain dedication mechanism, where you relinquish all copyrights to your illustration. The CC0 license is better than just stating that the work is public domain since this does not exist in certain countries (at least from the point of view of the law). By choosing CC0 this means that anyone can modify, redistribute or build on your work without restrictions on anything. Further, by using CC0, you forfeit the right to attribution. Instead, you have to rely on norms such as good citation practices in academic communities to be recognized as the creator. Several organizations, such as museums, governmental bodies and scientific publishers, have chosen CC0 for access to at least part of their intellectual property. In many instances, repositories maintained by universities recommend CC0 as the default option.

## Practical aspects

If you want to make available your illustrations to other researchers for reuse there are multiple aspects to consider:

- license (covered above, you need to choose e.g a CC license to allow people to reuse your work)
- availability of raw files (e.g .svg, .ai ) or other formats that allow reusing parts of the illustration
- timing (with some publishers you only own your illustration up to the point of signing the copyright transfer agreement with the journal)

Below some practical tips for these three aspects.

### License

As stated above there are many flavors of Creative Commons licenses around. Your default licenses should be CC0 and CC BY. 

NC is hardly enforceable and in some jurisdictions (e.g Germany) use by other researchers legally is commercial use even if used only in a research context. A NC clause therefore does not serve the scientific community. ND does not allow anyone to make modifications and therefore should be avoided because it is counter to the FAIR principles of open science. SA puts strong constraints on the resharing of the illustration and should therefore be avoided if possible, too. Be aware that you can mix licenses but e.g a SA clause will impact your whole illustration even if you reuse just a single small fragment licensed under SA. Licenses such as CC SA are therefore considered as “viral”.

For the CC licenses there are multiple versions available of which the 4.0 should be used. Older licenses such as CC 2.0 do not include a grace period if you e.g fail to credit the author which allows the creator to sue you for copyright infringement. The CC 4.0 licenses include a 30-day period that allows you to fix attribution errors.

A standard attribution should include the name of the creator, the name of the illustration, a link to the license and the name of the license: An example is the following attribution: 

> Actine-filament icon by [Servier](https://smart.servier.com/) is licensed under [CC-BY 3.0 Unported](https://creativecommons.org/licenses/by/3.0/).

Be aware that you can not add any modifying terms to any of the CC licenses. For example licensing the illustration under CC BY on your website but forbidding sharing of the raw illustration on another website is against the CC BY license terms and therefore automatically voids the CC license. Same for enforcing a specific way of attributing the original author. The CC BY license stipulates that attribution should conform to the used medium and is quite general since the license is intended for many different audiences and not just scientists.

It is however possible to allow users to choose between two different licenses. 
So you could offer e.g your illustration under CC BY ND or provide full rights to paying customers. 

### Availability of raw files

In principle there are two types of formats which can be used to share illustrations:

 - pixel graphics (e.g JPG, PNG, BMP) 

- vector graphics (e.g SVG, AI)

Some format can contain multiple different types such as vector and pixel graphics within one file. PDF is a classic example of such a format. Technically, SVG and AI can also contain pixel graphics but this is not efficient and should be avoided.  

You should prefer creating and exporting scientific illustrations in the  scalable vector graphics (SVG) file format because SVG is an open format, readable by browsers and all products to edit graphics from Photoshop, Illustrator, Corel Draw, Affinity Designer, Inkscape, GIMP to Powerpoint. Propietary formats such as AI and PDF should be avoided because they can be difficult to read with e.g Inkscape.

Vector illustrations have the advantage that they have small file size, can be scaled infinitely and one can edit individual items easily. Pixel graphics should only be used for actual photographs. 

If you share illustrations that contain text you should convert the text into a path so that there are no issues in displaying the text on other machines that do not have that particular font installed. This however disables the possibility of editing the text. To convert text to path in Inkscape you select the text box you want to convert to a path and then press `Path` &rarr; `Object to Path`

### Timing

In order to make available your illustrations to the community in perpetuity the only thing you need to do is release them under a Creative Commons license before the journal copyright transfer agreement is signed. This can be done either via preprinting the work (with the text and illustrations licensed under CC) or by individually releasing the illustrations to a suitable platform.

### Dedicated illustration platforms for scientists

- Bioicons: Contribute via Pull Request or Webform
- SciDraw: Contribute via Upload

### General purpose illustration platforms

- WikiMedia Commons: Contribute via Upload

### General platforms for scientists

Your illustration will receive a DOI and will be individually citable. You could even link the doi of the illustration in the figure caption such as done by some publishers (e.g PLoS).

- Zenodo (Choose image in the upload mask)
- FigShare
- OpenScienceFramework

Example from PLoS ONE ( [https://doi.org/10.1371/journal.pone.0088458](https://doi.org/10.1371/journal.pone.0088458)) with a figure with individual DOI.
This figure does not make the SVG file of the figure available making it harder to reuse because a pixel graphics editor must be used to erase parts of the image if one wanted to only use the chicken silhoute and bone outline. This image is licensed under CC BY by Grossi et. al.  [https://doi.org/10.1371/journal.pone.0088458.g001](https://doi.org/10.1371/journal.pone.0088458.g001)

![Grossi et.al Figure](https://journals.plos.org/plosone/article/file?id=10.1371/journal.pone.0088458.g001&type=large)
