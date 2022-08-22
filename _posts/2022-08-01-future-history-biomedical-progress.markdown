---
layout: post
title:  "A Future History of Biomedical Progress"
date:   2022-08-01 15:38:39 -0400
permalink: /biomedical-progress/
---


The apparent rate of biomedical progress has never been greater.

On the research front, every day more data are collected, more papers published, and more biological mechanisms revealed. 

On the clinical front, the pace is also rapid: the FDA [is approving](https://www.nature.com/articles/d41573-022-00001-9) more novel therapeutics [than ever before](https://media.nature.com/lw800/magazine-assets/d41573-022-00001-9/d41573-022-00001-9_19997144.jpg), buoyed by a record number of biologics approvals. A flurry of new therapeutic modalities—[gene therapies](https://www.nature.com/articles/s41587-022-01346-7), [cell therapies](https://www.nature.com/articles/s41408-021-00459-7), RNA vaccines, [xenogeneic organ transplants](https://www.technologyreview.com/2022/05/04/1051725/xenotransplant-patient-died-received-heart-infected-with-pig-virus/)—are slated to solve many hard-to-crack diseases over the coming decade.

It seems we are finally on the cusp of ending biomedical stagnation.

Unfortunately, this account isn’t quite correct. Though basic biological research has accelerated, this hasn’t yet translated into commensurate acceleration of medical progress. Despite a few indisputable medical advances, we are, on the whole, still living in an age of bio-<i>medical</i> stagnation.

That said, I’ll make a contrarian case for [definite optimism](https://blakemasters.tumblr.com/post/23435743973/peter-thiels-cs183-startup-class-13-notes): progress in basic biology research tools has created the potential for accelerating medical progress; however, this potential will not be realized unless we fundamentally rethink our approach to biomedical research. Doing so will require discarding the reductionist, human-legibility-centric research ethos underlying current biomedical research, which has generated the remarkable basic biology progress we have seen, in favor of a purely control-centric ethos based on machine learning. Equipped with this new research ethos, we will realize that control of biological systems obeys empirical scaling laws and is bottlenecked by biocompute. These insights point the way toward accelerating biomedical progress.


## Outline

The first half of the essay is descriptive:

Part 1 will outline the biomedical problem setting and provide a whirlwind tour of progress in experimental tools—the most notable progress in biomedical science over the past two decades.

Part 2 will touch on some of the evidence for biomedical stagnation. 

Part 3 will recast the biomedical control problem as a dynamics modeling problem. We’ll then step back and consider the spectrum of research ethoses this problem can be approached from.

The second half of the essay is more prescriptive, looking toward the future of biomedical progress and how to hasten it:

Part 4 will explain the scaling hypothesis of biomedical dynamics and why it is correct in the long-run.

Part 5 will explain why biocomputational capacity is the primary bottleneck to biomedical progress over the next few decades. We’ll then briefly review how to build better biocomputers.

Part 6 will sketch what the near- and long-term future of biomedical research might look like, and the role non-human agents will play in it.


## Niche, Purpose, and Presentation

There are many [meta-science](https://www.worksinprogress.co/issue/we-dont-know-how-to-fix-science/) articles on why [ideas are](https://www.theatlantic.com/science/archive/2018/11/diminishing-returns-science/575665/) (or [are not](https://guzey.com/economics/bloom/)) getting [harder to find](https://web.stanford.edu/~chadj/IdeaPF.pdf), new [organizational and funding models](https://www.theatlantic.com/ideas/archive/2022/01/scientific-funding-is-broken-can-silicon-valley-fix-it/621295/), [market failures](https://files.theseedsofscience.org/2022/Market_Failures_in_Science.pdf) in science, [reproducibility and data-sharing](https://www.worksinprogress.co/issue/the-speed-of-science/), [bureaucracy](https://goodscienceproject.org/category/articles/), and the [NIH](https://newscience.org/nih/). These are all intellectually stimulating, and many have spawned promising real-world experiments that will hopefully increase the rate of scientific progress.

This essay, on the other hand, is more applied macro-science than meta-science: an attempt to present a totalizing, [object-level](https://www.lesswrong.com/tag/object-level-and-meta-level) theory of an entire macro-field. It is a swinging-for-the-fences, [wild](https://mason.gmu.edu/~rhanson/wildideas.html) [idea](https://www.overcomingbias.com/2012/05/taming-the-wild-idea.html)—the sort of idea that seems to be in relatively short supply. (Consider this a call for similarly sweeping essays written about other fields.) However, because this essay takes on so much, the treatment of some topics is superficial and at points it will likely seem meandering.

All that said, hopefully you can approach this essay as an outsider to biomedicine and come away with a high-level understanding of where the field has been, where it could head, and what it will take to get there. My aim is to abstract out and synthesize the big-picture trends, while simultaneously keeping things grounded in data (but not falling into the common trap of rehashing the research literature without getting to the heart of things, which in the case of biomedicine typically results in naive, indefinite optimism).

## 1. The Biomedical Problem Setting and Tool Review

Biomedical research is intimidating. At first glance, it seems to span so many subjects and levels of analysis as to be beyond general description. Consider all the subject areas on [bioRxiv](https://www.biorxiv.org/)—how can one speak of the [effect of cell stiffness on melanoma metastasis](https://www.biorxiv.org/content/10.1101/2022.06.09.495509v2), the [evolution of sperm morphology in water fleas](https://www.biorxiv.org/content/10.1101/2020.01.31.929414v3), and [barriers to chromatin loop extrusion](https://www.biorxiv.org/content/10.1101/2022.01.07.475367v2) in the same breath? Furthermore, research is accretive and evolving, the frontier constantly advancing in all directions, so this task becomes seemingly more intractable with time.

That said, biomedical research does not defy general description. Though researchers study thousands of different phenomena (as attested to by the thousands of unique research grants awarded by the NIH every year), the scales of which range from nanometers to meters, underneath these particularities lies a unified biomedical problem setting and research approach:

The purpose of biomedicine is to control the state of biological systems toward salutary ends. Biomedical research is the process of figuring out how to do this.

Biomedical research has until now been approached predominantly from a single research ethos.<input type="checkbox" id="cb1" /><label for="cb1"><sup></sup></label><span><br><br>By “research ethos”, I do not quite mean culture. Rather, I mean the guiding values that (often subconsciously) suffuse all aspects of a research enterprise, the imperceptible cognitive scaffolding that cultural practices are built around.<br><br></span> This ethos aims to control biological systems by building mechanistic models of them that are understandable and manipulable by humans (i.e., [human-legible](https://www.ribbonfarm.com/2010/07/26/a-big-little-idea-called-legibility/)). Therefore, we will call this dominant research ethos the “mechanistic mind”.
 

The history of biomedical research so far has largely been the story of the mechanistic mind’s attempts to make biological systems more legible. Therefore, to understand biomedical research, we must understand the mechanistic mind.


### Tools of the Mechanistic Mind 

The mechanistic mind builds models of biology by observing and performing experiments on biological systems. To do this, it uses experimental tools.

Because they are the product of the mechanistic mind, these tools have evolved unidirectionally toward reductionism. That is, these tools have evolved to carve and chop biology into ever-smaller conceptual primitives that the mechanistic mind can build models over.

We’d like to understand how the mechanistic mind’s models of biology have evolved. However, delving into its particular phenomena of study—specific biological entities, processes, etc.—would quickly bog us down in details.

But we can exploit a useful heuristic: experimental tools determine the limits of our conceptual primitives, and vice versa. Therefore, we can tell the story of the mechanistic mind’s progress in understanding biology through the lens, as it were, of the experimental tools it has created to do so. By understanding the evolution of these tools, one can understand much of the history of biomedical research.

The extremely brief summary of this evolution goes:

In the second half of the 20th century, biomedical research became [molecular](https://en.wikipedia.org/wiki/Molecular_biology) (i.e., the study of nucleic acids and proteins). At the turn of the 21st century, with the (near-complete) sequencing of the human genome, molecular biology became [computational](https://en.wikipedia.org/wiki/Computational_biology). The rest is commentary.


### Scopes, Scalpels, and Simulacra

That summary leaves a lot to be desired. 

To make further sense of it, we can layer on a taxonomy of experimental tools, composed of three classes: scopes, scalpels, and simulacra.

- “Scopes” are used to read state from biological systems. 
- “Scalpels” are used to perturb biological systems. 
- “Simulacra” are physical models that act as stand-ins for biological systems we’d like to experiment on or observe but can’t. 

This experimental tool taxonomy is invariant across eras and physical scales of biomedical research, generalizing beyond any particular paradigm like [cell theory](https://en.wikipedia.org/wiki/Cell_theory) or [genomics](https://en.wikipedia.org/wiki/Genomics). These three tool classes are, in a sense, the tool archetypes of experimental biomedical research.

Therefore, to understand the evolution in experimental tools (and, consequently, the evolution of the mechanistic mind), we can simply track advances in these three tool classes. We will pick up our (non-exhaustive) review around 15 years ago, near the beginning of the modern computational biology era, when tool progress starts to appreciably accelerate. (We will tackle scopes and scalpels now and leave simulacra for later.) I hope to convey a basic understanding of how these tools are used to interrogate biological systems, the rate they’ve been advancing at, and the resulting inundation of biomedical data we’ll soon face.


### Scopes 

To reiterate, scopes are tools that read state from biological systems. But this raises an obvious question: what is biological state?

As alluded to earlier, [in the mid-20th century](https://en.wikipedia.org/wiki/History_of_molecular_biology#%22Central_Dogma%22) biological research became molecular, meaning it became the study of nucleic acids and proteins. Therefore, broadly speaking, biological state is information about the position, content, interaction, etc. of these molecules, and the larger systems they compose, within biological systems. Subfields of the biological sciences are dedicated to interrogating facets of biological state at different scales—structural biologists study the nanometer-scale folding of proteins and nucleic acids, cell biologists study the orchestrated chaos of these molecules within and between cells, developmental biologists study how these cellular processes drive the emergence of higher-order organization during development, and so on.

Regardless of the scale of analysis, advances in tools for reading biological state (i.e., scopes) occur along a few dimensions:

- feature-richness

- spatio-temporal resolution

- spatio-temporal extent

- throughput (as measured by speed or cost)

However, there are tradeoffs between these dimensions, and therefore they map out a scopes Pareto frontier. 

In the past two decades, we’ve seen incredible advances along all dimensions of this frontier. 

To illustrate these advances, we will restrict our focus to the evolution of three representative classes of scopes, each of which highlights a different tradeoff along this frontier: 

- extremely feature-rich single-cell methods

- spatially resolved methods, which have moderate-to-high feature richness and spatio-temporal resolution

- light-sheet microscopy, which has large spatio-temporal extent, high spatio-temporal resolution, and low feature-richness

By tracking the evolution of these methods over the past two decades, we’ll gain an intuition for the rate of progress in scopes and where they might head in the coming decades.

But we must first address the metatool which has driven many, but not all, of these advances in scopes: DNA sequencing.


### Sequencing as Scopes Metatool

DNA sequencing is popularly known as a tool for reading genetic sequences, like an organism’s genome. But lesser known is the fact that sequencing can be indirectly used to read many other types of biological state. You can therefore think of sequencing as a near-universal solvent or sensor of the scopes class—much progress in scopes has simply come from discovering how to cash out different aspects of biological state in the language of A’s, T’s, G’s and C’s. 

The metric of sequencing progress to track is the cost per gigabase ($/Gb): the cost of consumables for sequencing 1 billion base pairs of DNA. Bioinformaticians can fuss about the details—error rates, paired-end vs. single-read, throughput, read quality in recalcitrant regions of the genome like telomeres or repetitive stretches—but for our purposes this metric provides the single best index of progress in sequencing over the past two decades. <input type="checkbox" id="cb2" /><label for="cb2"><sup></sup></label><span><br><br>For a thorough history of sequencing, see [this review article](https://arep.med.harvard.edu/pdf/Shendure_Waterston_2017.pdf).<br><br></span>

You’ve probably seen the [famous NIH sequencing chart](https://www.genome.gov/about-genomics/fact-sheets/DNA-Sequencing-Costs-Data), which plots the cost per Mb of sequencing (1000 Mb equals 1 Gb). However, this chart is somewhat confusing—the curve clearly appears piecewise linear, with steady Moore’s-law-esque progress from 2001 to 2007, then a period of rapid cost decline from mid-2007 to around 2010, followed by a seeming reversion to the earlier rate of decline.

![](../assets/2021_Sequencing_cost_per_Mb.jpg)


For the purposes of extrapolation, the current era of sequencing progress started around 2010 (when Illumina released the first in its line of HiSeq sequencers, the HiSeq2000). When we plot sequencing prices from then onward, restricting ourselves to short-read methods, we get the following plot.<input type="checkbox" id="cb3" /><label for="cb3"><sup></sup></label><span><br><br>Plotted are the cheapest sequencing consumables prices available by year, stratified by device throughput class (which reflects the cost of the sequencing instrument). All data points are the minimum price available that year for a given read length class and throughput class, but note that some cost estimates in the 2010-2015 period were difficult to verify, and therefore multiple prices are given.<br><br></span>


![](../assets/short_read_seq_cost_decline.png)



Over the past 12 years, the price per gigabase on high-volume, short-read sequencers has declined by almost two orders of magnitude, halving roughly every 2 years—slightly _slower_ than Moore’s law.<input type="checkbox" id="cb4" /><label for="cb4"><sup></sup></label><span><br><br>Granted, if we measured over the past 15 years, starting with the [original Solexa technology](https://www.nature.com/articles/nature07517) that Illumina [acquired and commercialized](https://www.bio-itworld.com/news/2010/09/30/the-solexa-story), which [allegedly could](http://web.archive.org/web/20101007065920/https://www.bio-itworld.com/issues/2006/feb/sci-solexa/) sequence 1 Gb for $1000-$3000 in 2007 and for $400 in 2009 (per [Illumina’s marketing materials](https://www.illumina.com/documents/seminars/presentations/2009_07_preston_jeremy.pdf#page=2)), then the trend would appear basically on par with Moore’s law.<br><br></span>

The first order of magnitude cost decline came in the 2010-2015 period with Illumina’s HiSeq line, the price of sequencing plummeting from ~$100/Gb to ~$10/Gb; this was followed by 5 years of relative stagnation, for [reasons](https://www.wired.com/2016/02/gene-sequencing-goliath-wants-get-bigger-still/) unknown; and in the past 2 years, there’s been another order of magnitude drop, with multiple competitors finally surpassing Illumina and approaching $1/Gb prices. The sequencing market is [starting to really heat up](https://mobile.twitter.com/AlbertVilella/status/1540240357555937280), and that likely means the biennial doubling trend will hold; if it does, and if current prices are to be believed, then we can expect sequencing prices to hit $0.1/Gb around 2028-2029.

To make this trend more intuitive, we can explain it in terms of the cost of sequencing a human genome. 

A haploid human genome (i.e., one of the two sets of 23 chromosomes the typical human has) is [roughly 3 Gb](https://www.science.org/doi/10.1126/science.abj6987) (bases, not bytes) on average (e.g., the X chromosome is much larger than the Y chromosome, so a male’s two haploid genomes will differ in size). Therefore, sequencing this haploid genome at [30x coverage](https://en.wikipedia.org/wiki/Coverage_(genetics))—meaning each nucleotide is part of (i.e., covered by) 30 unique reads on average—which is the standard for whole genome sequencing, results in ~90 Gb of data (call it 100 Gb to make the numbers round). So, we can use this 100 Gb human genome figure as a useful unit of measurement for sequencing prices.

In 2010 to 2011, a human genome [cost somewhere](https://en.wikipedia.org/wiki/Whole_genome_sequencing#History_2) in the $5,000 to $50,000 range; by 2015, the price had fallen [to around](https://www.nature.com/articles/nature.2014.14530) $1000; and now, in 2022, it is [allegedly](https://www.science.org/content/article/100-genome-new-dna-sequencers-could-be-game-changer-biology-medicine) nearing $100 (though this was already being claimed [two years ago](https://www.genengnews.com/news/mgi-delivers-the-100-genome-at-agbt-conference/)). 

This exponential decline in price has led to a corresponding exponential increase in genome sequencing data. Since around 2014, the number of DNA bases added per release cycle to GenBank, the repository of all publically available DNA sequences, has doubled roughly every 18 months.


![](../assets/genbank_basepairs_added.png)


![](../assets/genbank_post_2014.png)


But as noted earlier, sequencing has many uses other than genome sequencing. Arguably, the revolution in reading non-genomic biological state has been the most important consequence of declining sequencing costs. 


### The Single-Cell Omics Revolution

Biological systems run off of nucleic acids and proteins, among other macromolecules. And because proteins are translated from RNA, all biological complexity ultimately traces back to the transformations of nucleic acids—epigenetic modification of DNA, transcription of DNA to RNA, splicing of RNA, etc. Sequencing-based scopes allow us to interrogate these nucleic acid-based processes. 

We can divide the study of these processes into two areas: [transcriptomics](https://en.wikipedia.org/wiki/Transcriptomics_technologies), the study of RNA transcripts, which are transcribed from DNA; and [epigenomics](https://en.wikipedia.org/wiki/Epigenomics), the study of modifications made to genetic material above the level of the DNA sequence, which can alter transcription. 

Transcriptomics and epigenomics have been studied for decades. However, the past decade was an incredibly fertile period for these subjects due to the combination of declining sequencing costs and advances in methods for preparing biological samples for sequencing-based readout. 

The defining feature of these sample preparation methods has been their biological unit of analysis: the single cell.

It’s not inaccurate to call the past decade of computational biology the [decade of single-cell methods](https://www.nature.com/articles/s41467-020-18158-5). The ability to read epigenomic and transcriptomic state at single-cell resolution has revolutionized the study of biological systems and is the source of much current biomedical optimism.


#### Applications of Single-Cell Omics

To understand how much single-cell methods have taken off, consider the following chart:

![](../assets/HCA_cell_counts.png)

This is a plot of the number of cells in each study added to the Human Cell Atlas, which aims to “create comprehensive reference maps of all human cells—the fundamental units of life—as a basis for both understanding human health and diagnosing, monitoring, and treating disease.” The number of cells per study has been increasing by an order of magnitude a little under every 3 years—and the frequency with which studies are added is increasing too.

The HCA explains their immense ambitions like so:

> Cells are the basic units of life, but we still do not know all the cells of the human body. Without maps of different cell types, their molecular characteristics and where they are located in the body, we cannot describe all their functions and understand the networks that direct their activities.<br><br>The Human Cell Atlas is an international collaborative consortium that charts the cell types in the healthy body, across time from development to adulthood, and eventually to old age. This enormous undertaking, larger even than the Human Genome Project, will transform our understanding of the 37.2 trillion cells in the human body.

The way these human cells are charted is by reading out their internal state via single-cell methods. That is, human tissues (usually post mortem, though for blood and other tissues this isn’t always the case) are dissociated into individual cells, and then these cells’ contents are assayed (i.e., profiled, or read out) along one or more dimensions of transcriptomic or epigenomic state.

Crucially, these assays rely on sequencing for readout. In the case of [single-cell RNA sequencing](https://en.wikipedia.org/wiki/RNA-Seq#Library_preparation), the RNA transcripts inside the cells are reverse transcribed into complementary DNA sequences, which are then read out by sequencers. But sequencing can be used to read out other types of single-cell state that aren’t natively expressed in RNA or DNA—chromatin conformation, chromatin accessibility, and other epigenomic modifications—which typically requires a slightly more convoluted library preparation.

The upshot is that these [omics profiles](https://en.wikipedia.org/wiki/Omics), as they are called, act as proxies for the cells’ unique functional identities. Therefore, by assaying enough cells, one can develop a “map” of single-cell function, which can be used to understand the behavior of biological systems with incredible precision. Whereas earlier bulk assays lost functionally consequential inter-cellular heterogeneity in the tissue-average multicellular soup, now this heterogeneity can be resolved in its complete, single-cell glory. These single-cell maps look like so (this one is of a very large human fetal cell atlas, which you can [explore here](https://descartes.brotmanbaty.org/bbi/human-gene-expression-during-development/)):

![](../assets/fetal_cell_atlas_viz.PNG)

And the Human Cell Atlas is the tip of the iceberg—single-cell omics methods have taken the entire computational biology field by storm. These methods have found numerous applications: comparing cells from healthy and diseased patients; tracking the differentiation of a particular cell type to determine the molecular drivers, which might go awry in disease; and comparing single-cell state under different perturbations, like drugs or genetic modifications. Open up any major biomedical journal and you’re bound to see an article with single-cell omics data.<input type="checkbox" id="cb5" /><label for="cb5"><sup></sup></label><span><br><br>Single-cell methods have become de rigueur in computational biology. Somewhat ironically, the ability to parse biological heterogeneity has driven methodological homogenization of the field. Papers are now rather formulaic, including basically the same types of data, analysis and figures—a dimensionality reduction plot of single-cell profiles (i.e., a “single-cell map”), a volcano plot showing differential gene expression between two conditions, a visualization of the inferred gene regulatory network, and a matrix of gene expression values across pseudotime for key gene regulatory nodes.<br><br>Every year or two a fancy new analysis method will come along, which is [aped by the entire field](https://mobile.twitter.com/shchurch/status/1532422321771843584): there are [more than 70 methods](https://www.nature.com/articles/s41587-019-0071-9) for inferring cellular trajectories on single-cell maps, [a dozen methods](https://www.nature.com/articles/s41576-020-00292-x) for inferring cell-cell communication from gene expression data, and a [dozen methods and counting](https://academic.oup.com/bib/article/22/3/bbaa190/5904505) for inferring gene regulatory networks. Research has to an extent become paint-by-numbers: do single-cell omics on your biological system of study, apply new single-cell analysis method X to the data, and then tell a compelling mechanistic story about the results.<br><br>(Single-cell maps have become so important to the field of computational biology that these maps are [now being made accessible](https://www.biorxiv.org/content/10.1101/2021.10.07.463279v2) to the color-blind.)<br><br></span>

But this rapid expansion of single-cell data is only made possible by continual advances in methods for isolating and assaying single cells. 


#### Single-Cell Omic Technologies 

Over the past decade or so, single-cell sample preparation methods have advanced along two axes: throughput (as measured by cost and speed) and feature-richness (as measured by how many omics profiles can be assayed at once per cell and the resolution of these assays). 

[Svensson et al.](https://arxiv.org/ftp/arxiv/papers/1704/1704.01379.pdf) explain the exponential increase in single-cell transcriptomic throughput over the past decade as the result of multiple technical breakthroughs in isolating and processing single cells at scale:

> A jump to ~100 cells was enabled by sample multiplexing, and then a jump to ~1,000 cells was achieved by large-scale studies using integrated fluidic circuits, followed by a jump to several thousands of cells with liquid-handling robotics. Further orders-of-magnitude increases bringing the number of cells assayed into the tens of thousands were enabled by random capture technologies using nanodroplets and picowell technologies. Recent studies have used in situ barcoding to inexpensively reach the next order of magnitude of hundreds of thousands of cells.


![](../assets/svensson_single_cell_methods.PNG)


That is, once a tissue has been dissociated into single cells, the challenge then becomes organizational: how do you isolate, process, and track the contents of these cells? In the case of transcriptomics, at some point the contents of the cell must undergo multiple steps of library preparation to transform RNA transcripts into DNA, and then these DNA fragments must be exposed to the sequencer for readout—all without losing track of which transcript came from which cell.

As can be seen in the graph, throughput began to really take off [around 2013](https://www.nature.com/articles/nmeth.2801). But these methods have continued to advance since the above graph was published. 

For instance, combinatorial indexing methods went from [profiling 50,000 nematode cells](https://www.science.org/doi/10.1126/science.aam8940) at once in 2017, to [profiling two million mouse cells](https://www.nature.com/articles/s41586-019-0969-x) at once in 2019, to profiling (the gene expression and chromatin accessibility of) [four million human cells](https://www.science.org/doi/10.1126/science.aba7721) at once in 2020. With these increases in scale have come corresponding decreases in price per cell—even in the past year, sci-RNA-seq3, the most recent in this line of combinatorial indexing methods, was further optimized, making it [~4x less expensive](https://arxiv.org/ftp/arxiv/papers/2110/2110.15400.pdf#page=4) than before, nearing costs of $0.003 per cell at scale.

Costs have also declined among commercial single-cell preparation methods. 10X Genomics, the leading droplet-based single-cell sample preparation company, [offers](https://www.10xgenomics.com/products/single-cell-gene-expression) single-cell RNA sequencing library preparation at a [cost of roughly](https://docs.google.com/spreadsheets/d/1IPe2ozb1Mny8sLvJaSE57RJr3oruiBoSudAVhSH-O8M/edit#gid=450807416) $0.5 per cell. But Parse Biosciences, which, like sci-RNA-seq3, uses combinatorial indexing, [recently claimed](https://www.genomeweb.com/sequencing/parse-biosciences-lowers-cost-barriers-single-cell-transcriptomics-research) its system can sequence up to a million cells at once for only $0.09 per cell. (Though one can approach these library preparation prices on a 10x chip [by craftily multiplexing and deconvoluting](https://satijalab.org/costpercell/)—that is, by labeling cells from different samples, multiple cells can be loaded into the same droplet, and the droplet readout can be demultiplexed (i.e., algorithmically disentangled) after the fact, thereby dropping the cost per cell.)

Thus, like with sequencing, there’s an [ongoing gold-rush](https://docs.google.com/spreadsheets/d/1IPe2ozb1Mny8sLvJaSE57RJr3oruiBoSudAVhSH-O8M/edit#gid=1775983611) in single-cell sample preparation methods, and commercial prices should only decline further—especially given that the costs of academic methods are already an order of magnitude lower.

The second dimension along which single-cell methods have progressed in the richness of their readout. 

In the [past few years](https://www.nature.com/articles/s41592-019-0703-5), we’ve [seen an efflorescence](https://www.youtube.com/watch?v=kqJBTiVJ-gc&t=1555s) of so-called “multi-omic” methods, which simultaneously profile multiple omics modalities in a single-cell. For instance, one could assay gene expression along with an epigenomic modality, like [chromatin accessibility](https://www.cell.com/cell/fulltext/S0092-8674(20)31253-8), and perhaps even profile cellular surface proteins [at the same time](https://www.nature.com/articles/s41587-021-00927-2). The benefit of multi-omics is that different modalities share complementary info; often this complementary information aids in mechanistically interrogating the dynamics underlying some process—e.g., one can investigate if increases in chromatin accessibility near particular genes precede upregulation of those genes.

Yet not only can we now profile more modalities simultaneously, but we can do so at higher resolution. To give a particularly incredible example, the maximum resolution of (non-single-cell) sequencing-based chromatin conformation assays went from 1 Mb [in 2009](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2858594/), to ~5 kb [in 2020](https://www.nature.com/articles/s41467-020-16598-7), to 20 _base pairs_ [in 2022](https://www.nature.com/articles/s41467-022-29696-5)—an increase in resolution of over four orders of magnitude. Since we’re nearing the limits of resolution, future advances will likely come from sparse input methods, like those that [profile single cells](https://www.nature.com/articles/s41467-021-24662-z), and increased throughput.

Thus, improvements in sequencing and single-cell sample preparation methods have revolutionized our ability to read out state from biological systems.

But as great as single-cell methods are, their core limitation is non-existent spatio-temporal resolution. That is, because these methods require destroying the sample, we get only a snapshot of cellular state, not a continuous movie—the best we can do is reconstructing pseudo-temporal trajectories after the fact based on some metric of cell similarity (which is perhaps one of [the most influential ideas](https://www.nature.com/articles/nbt.2859) in the past decade of computational biology), though [some methods](https://www.nature.com/articles/s41576-020-0223-2) are [attempting](https://www.biorxiv.org/content/10.1101/2021.03.24.436752v1) to [address](https://centuryofbio.substack.com/p/dna-ticker-tape) this temporal limitation. And because we dissociate the tissue before single-cell sample preparation, all spatial information is lost. 

However, this latter constraint is addressed by a different set of scopes: spatial profiling methods.


### Spatial Profiling Techniques

If single-cell omics methods defined the 2010’s, then spatial profiling methods might [define the early 2020’s](https://www.nature.com/articles/s41592-020-01042-x). These methods readout nucleic acids along with their spatial locations. This information is valuable for obvious reasons—cells don’t live in a vacuum, and spatial organization plays a large role in multicellular interaction. 

We’ll briefly highlight [two major categories](https://www.nature.com/articles/s41576-022-00515-3) of these methods: sequencing-based spatial transcriptomics, which resolve spatial location via sequencing, and fluorescence in situ hybridization (FISH) approaches, which resolve spatial location via microscopy.<input type="checkbox" id="cb6" /><label for="cb6"><sup></sup></label><span><br><br>For a more thorough treatment of spatial profiling techniques, see the [Museum of Spatial Transcriptomics](https://pachterlab.github.io/LP_2021/index.html).<br><br></span>


#### Sequencing-Based Spatial Transcriptomics

The premise of sequencing-based spatial transcriptomics is simple: rather than randomly dissociating a tissue before single-cell sequencing, thereby losing all spatial information, RNA transcripts can be tagged with a “barcode” based on their location, which can later be read out via sequencing alongside the transcriptome, allowing for spatial reconstruction of the locations of the transcripts.

These barcodes [are applied by](https://pachterlab.github.io/LP_2021/current-techs.html#array) placing a slice of tissue on an array covered with spots that have probes attached to them. When the tissue is [fixed](https://en.wikipedia.org/wiki/Fixation_(histology)) and permeabilized, these probes capture the transcripts in the cells above them; then, complementary DNA sequences are synthesized from these captured transcripts, with specific spatial barcodes attached depending on the location of the spot. When these DNA fragments are sequenced, the barcodes are read out with the transcripts and used to resolve their spatial positions.

One major dimension of advance of these methods is spatial resolution, as measured by the size of the spots which RNA transcripts bind to, which determines how many cells are mapped to a single spot, and therefore the resolution with which gene expression can be resolved. Over just the past 3 years, maximum resolution has jumped by almost three orders of magnitude ([image source](https://pachterlab.github.io/LP_2021/current-techs.html#array)):


![](../assets/spot_diam_ST.png)

These spatial transcriptomics methods produce [stunning images](https://spatialtranscriptomics.com/showcase/). For instance, here’s a section of the developing mouse brain as profiled by the currently highest resolution method, [Stereo-seq](https://www.biorxiv.org/content/10.1101/2021.01.17.427004v3.full.pdf#page=43):



![](../assets/stereo_seq_image.PNG)


Each dot in the middle pane represents the intensity of the measured gene at that location, but plots of this sort can be generated for all the tens of thousands of genes assayed via RNA sequencing. In the left pane, these complete gene expression profiles are used to assign each dot to its predicted average cell-type cluster, as one might do with non-spatial single-cell transcriptomics.

Yet note the resolution [in the rightmost pane](https://developingmouse.brain-map.org/gene/show/81990) of the above figure—it is even greater than that of the middle pane. This image uses in situ hybridization, the basis of the spatial profiling technique we’ll explore next.


#### smFISH

Fluorescent in situ hybridization (FISH) methods trade off feature-richness for increased spatial resolution. That is, FISH-based methods don’t assay the RNA of every single protein-coding gene like sequencing-based methods do, but in return they localize the transcripts they do assay better.

Instead of using sequencing for readout, these methods use the other near-universal solvent or sensor of the scopes class: microscopy. 

That is, whereas spatial transcriptomics resolve the location of transcripts indirectly via sequencing barcodes, FISH methods visually resolve location via microscopy. They do this by repeatedly hybridizing (i.e., binding) complementary DNA probes to targeted nucleic acids in the tissue (attached to these probes are [fluorophores](https://en.wikipedia.org/wiki/Fluorophore) which emit different colors of light); after multiple rounds of hybridization and fluorescent emission from these probes, the resulting multi-color image can be deconvolved, the “[optical barcodes](https://www.nature.com/articles/s41576-022-00515-3)” used to localize hundreds of genes at extremely high spatial resolution. 

Unlike spatial transcriptomics, which is a hypothesis-free method that doesn’t (purposefully) select for particular transcripts, in FISH the genes to probe must be selected in advance, and typically they number in the tens or hundreds, not the tens of thousands like with spatial transcriptomics (though in principle they can reach these numbers—see below). The number of genes that can be resolved per sample (i.e., multiplexed) is limited by the size and error-rates of the [fluorescent color palette](https://pachterlab.github.io/LP_2021/current-techs.html#barcoding) that is used to mark them, and the spatial resolution with which these transcripts are localized is limited by the sensor’s ability to distinguish these increasingly [crowded fluorescent signals](https://pachterlab.github.io/LP_2021/current-techs.html#crowding) (perhaps so crowded that the distance between them falls beneath the [diffraction limit](https://en.wikipedia.org/wiki/Diffraction-limited_system) of the sensor).

The general idea of FISH has been around for [over 50 years](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC223575/?page=2), but the current generation of multi-gene single-molecule FISH (smFISH) methods only began to take off around [15 years ago](https://www.nature.com/articles/nmeth.1253). Since then, there’s been a fair deal of progress in gene multiplexing and the number of cells that can be profiled at once ([images source](https://pachterlab.github.io/LP_2021/current-techs.html#smfish)):

![](../assets/smfISH_record_num_genes.png)

![](../assets/smFISH_num_cells_per_study.png)


But the best way to understand these advances is visually. For instance, we can look at  MERFISH, a technique which [has been commercialized](https://vizgen.com/technology/), part of [a growing market](https://docs.google.com/spreadsheets/d/1IPe2ozb1Mny8sLvJaSE57RJr3oruiBoSudAVhSH-O8M/edit#gid=339061555) for FISH-based spatial profiling methods. [Here’s](https://www.biorxiv.org/content/10.1101/2020.06.04.105700v1.full.pdf#page=29) what part of a coronal slice of an adult mouse brain, with more than 200 genes visualized, looks like (the scale-bar is 20 microns in the left pane and 5 microns in the right pane): 


![](../assets/MERFISH_example.PNG)


The amount of data [these methods generate](https://www.biorxiv.org/content/10.1101/2022.03.04.483068v2.full.pdf#page=14) is immense:

> As a point of reference, the raw images from a single run of MERFISH for a ~1 cm^2 tissue sample contain about 1 TB of data.

But like spatial transcriptomics, these smFISH methods have one major drawback: though they can spatially resolve extremely feature-rich signals, they lack temporal resolution—that is, they image dead, static tissues, a problem addressed by longitudinal methods like light-sheet microscopy.


### Light-Sheet Microscopy

Biological systems operate not only across space, but across time. 

Methods like [light-sheet fluorescence microscopy](https://en.wikipedia.org/wiki/Light_sheet_fluorescence_microscopy) (LSFM) trade off feature-richness in exchange for this temporal resolution, all while maintaining high spatial extent and resolution. The niche filled by LSFM [is explained](http://www.microscopist.co.uk/wp-content/uploads/2017/04/Lightsheet-review-2017.pdf) as follows:

> Fluorescence microscopy in concert with genetically encoded reporters is a powerful tool for biological imaging over space and time. Classical approaches have taken us so far and continue to be useful, but the pursuit of new biological insights often requires higher spatiotemporal resolution in ever-larger, intact samples and, crucially, with a gentle touch, such that biological processes continue unhindered. LSFM is making strides in each of these areas and is so named to reflect the mode of illumination; a sheet of light illuminates planes in the sample sequentially to deliver volumetric imaging. LSFM was developed as a response to inadequate four-dimensional (4D; x, y, z and t) microscopic imaging strategies in developmental and cell biology, which overexpose the sample and poorly temporally resolve its processes. It is LSFM’s fundamental combination of optical sectioning and parallelization that allows long-term biological studies with minimal phototoxicity and rapid acquisition.

That is, LSFM gives us the ability to longitudinally profile large 3D _living, intact specimens_ at high spatial and temporal resolution. Thus, it plays an important complementary role to moderately feature-rich spatial transcriptomic methods and extremely feature-rich single-cell methods, both of which lack temporal resolution.<input type="checkbox" id="cb7" /><label for="cb7"><sup></sup></label><span><br><br>See [this methods primer](https://www.nature.com/articles/s43586-021-00069-4) if you wish to dig into the physics and history behind LSFM.<br><br></span>

Needless to say, the technology underlying LSFM has advanced quite a lot over the past two decades. The beautiful thing about spatio-temporally resolved methods is that we can easily witness these advances with our eyes. For instance, we can compare the state of the art in imaging fly embryogenesis [in 2004](https://www.science.org/doi/abs/10.1126/science.1100035) vs. [in 2016](https://www.nature.com/articles/nbt.3708):

<iframe src="https://www.youtube.com/embed/bDkCQIm-zbE" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

<iframe src="https://www.youtube.com/embed/cn6xmBXK4Dc" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen> </iframe>

Yet in just the past year, we have seen further advances still. [A new, simplified system](https://www.nature.com/articles/s41592-022-01417-2) has improved imaging speed while maintaining sub-micron lateral and sub-two-micron axial resolution—and on large specimens, no less.

<iframe src="https://www.youtube.com/embed/uFDjHlHUqG8" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen> </iframe>

And recently an LSFM [method was developed](https://www.nature.com/articles/s41551-022-00849-7) that can image tissues at subcellular resolution _in situ_, without the need for exogenous fluorescent dyes—in effect, a kind of in vivo 3D histology. The applications of this technology, to both research and diagnostics, [are numerous](https://www.nature.com/articles/s41551-022-00897-z).<input type="checkbox" id="cb8" /><label for="cb8"><sup></sup></label><span><br><br>You might be asking how one can perform LSFM on in situ tissue if there are no fluorophores to excite. To solve this, the researchers exploit the [natural fluorescent emission](https://en.wikipedia.org/wiki/Autofluorescence) of some cellular structures, allowing for non-invasive “label-free imaging”—though this method is also compatible with traditional fluorescent dyes, as seen in the video below.<br><br></span>

Here’s the stitching together of a 3D-resolved (but not temporally resolved) slice of in situ mouse kidney:

<iframe src="https://www.youtube.com/embed/sUdJjQuGmO8" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen> </iframe>

And here’s real-time imaging of a fluorescent tracer dye perfusing mouse kidney tubules in situ:<input type="checkbox" id="cb9" /><label for="cb9"><sup></sup></label><span><br><br>Granted, both mouse kidney videos required anesthetizing the mouse and opening up its gut so its kidneys could be more directly exposed for imaging, so it's not exactly <i>noninvasive</i>.<br><br></span> 

<iframe src="https://www.youtube.com/embed/vSaZ1sKCGho" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen> </iframe>


### Scopes Redux

The scopes Pareto frontier has advanced tremendously over the past two decades, and on many dimensions at a surprisingly regular rate. This is perhaps the most exciting development in all of biomedical research.<input type="checkbox" id="cb10" /><label for="cb10"><sup></sup></label><span><br><br>If one had to bet on a particular class of methods that will come to the fore in the next decade, the most underrated bet would be temporally resolved methods like LSFM. As the fine-grain multicellular behavior of large biological systems becomes the object of study beyond developmental biology, we’ll likely see improvements in the throughput, spatio-temporal extent and resolution, and cost of these systems.<br><br></span>

However, the ability to read state from biological systems doesn’t alone much improve our understanding of them—for that, we must perturb them.


## Scalpels

Scalpels are used to experimentally perturb biological systems. The dimensions of the scalpels Pareto frontier are similar to those of the scopes Pareto frontier:

- feature precision 

- spatio-temporal precision

- spatio-temporal extent

- throughput

However, the past decade has been one dominated by advances in scopes, not scalpels. One metric of this dominance is the annual Nature method of the year, which is a good gauge for what tools are becoming popular among biological researchers. Among the past 15 winners, two are scalpels ([optogenetics](https://www.nature.com/articles/nmeth.f.321) and [genome editing](https://www.nature.com/articles/nmeth.1852)), two are related to simulacra ([iPSC](https://www.nature.com/articles/nmeth.f.294) and [organoids](https://www.nature.com/articles/nmeth.4575)), and the rest are scopes ([NGS](https://www.nature.com/articles/nmeth1153), [super-resolution fluorescence microscopy](https://www.nature.com/articles/nmeth.f.244), [targeted proteomics](https://www.nature.com/articles/nmeth.2329), [single-cell sequencing](https://www.nature.com/articles/nmeth.2801), [LSFM](https://www.nature.com/articles/nmeth.3251), [cryo-EM](https://www.nature.com/articles/nmeth.3730), [sequencing-based epitranscriptomics](https://www.nature.com/articles/nmeth.4142), [imaging of freely behaving animals](https://www.nature.com/articles/s41592-018-0292-8), [single-cell multiomics](https://www.nature.com/articles/s41592-019-0703-5), and [spatial transcriptomics](https://www.nature.com/articles/s41592-020-01042-x)) or analytical methods ([protein structure prediction](https://www.nature.com/articles/s41592-021-01380-4)).<input type="checkbox" id="cb11" /><label for="cb11"><sup></sup></label><span><br><br>It’s hard to imagine the counterfactual of wide-ranging progress in scalpels with minimal progress in scopes. This might reflect a deep truth about tool sequencing: reading state from biological systems is a prerequisite to developing the conceptual tools necessary to build the experimental tools that can perturb those systems. For instance, it would be much more difficult to edit a genome if you didn’t understand its physical structure first, which requires imaging it.<br><br></span>

Scalpels have simply experienced far narrower progress over the past decade or so than scopes. Advances occurred mostly along the feature-precision and throughput dimensions within a single suite of tools, which we will restrict our attention to (and therefore this section will be comparatively short).<input type="checkbox" id="cb12" /><label for="cb12"><sup></sup></label><span><br><br>Though the scalpels we review here are useful for interrogating biological dynamics at the level of the cell and below, truly advanced biomedical research will require modeling dynamics at the multicellular level and above. Therefore, we must develop tools for perturbing biological systems at this level, ideally in situ, with high spatial and temporal control—in effect, we must develop the scalpel counterparts to the spatially and temporally resolved scopes that have been developed over the past decades.<br><br></span>


### Genome and Epigenome Editing

The most notable advance in scalpels has been in our ability to perturb the genome and epigenome with high precision, at scale. Of course, we’re referring to the technology of [CRISPR](https://en.wikipedia.org/wiki/CRISPR), which researchers successfully appropriated from bacteria a decade ago (though [there’s some disagreement](https://www.nature.com/articles/d41586-022-00629-y) about whom the credit should go to).

When one thinks of CRISPR, they likely think about making DNA double-strand breaks (DSB) in order to knock out (i.e., inhibit the function of) whole genes. But CRISPR is a general tool for using guide RNAs to direct nucleases (enzymes which cut DNA or RNA, like the famous Cas9) to specific regions of the genome—in effect, a kind of nuclease genomic homing guidance system. By varying the nuclease one uses and the molecules attached to them, a [variety of functions](https://www.nature.com/articles/s43586-021-00093-4) other than knockouts can be performed:[ targeted editing of DNA](https://www.liugroup.us/research-overview/genome-editing/) without DSB, [inhibiting gene expression](https://en.wikipedia.org/wiki/CRISPR_interference) without DSB, [activating gene expression](https://en.wikipedia.org/wiki/CRISPR_activation), [editing epigenetic marks](https://www.nature.com/articles/s41556-020-00620-7), and [RNA editing and interference](https://www.nature.com/articles/nmeth.4681). 

CRISPR is not the first system to perform most of these functions, and it certainly isn’t perfect—transfection rates are still low and off-target effects still common—but that’s beside the point: the defining features of CRISPR are its generality and ease of use. If sequencing and microscopy are the universal sensors of the scopes tool class, then CRISPR might be the universal genomic actuator of the scalpels tool class. 

In conjunction, these scopes and scalpels have enabled interrogating the genome at unprecedented resolution and throughput. 


## Using Scopes and Scalpels to Interrogate the Genome and Beyond

By perturbing the genome and observing how the state of a biological system shifts, we can infer the mechanistic structure underlying that biological system. Advances in scopes and scalpels have made it possible to do this at massive scale.

For instance, one could use CRISPR to systematically knockout every single gene in the genome across a set of samples (perhaps with multiple knockouts per sample), a so-called [genome-wide knockout screen](https://en.wikipedia.org/wiki/Genome-wide_CRISPR-Cas9_knockout_screens). But whereas previously the readout of these screens was limited to [simple phenotypes like fitness](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4253859/) (that is, does inhibiting a particular gene produce lethality, which can be inferred by counting the guide RNAs in the surviving samples) or a predefined set of gene expression markers, due to advances in scopes [we can now](https://www.nature.com/articles/s43586-021-00093-4) read out the entire transcriptome from every sample.

Over the past five years, a [lineage of papers](https://en.wikipedia.org/wiki/Perturb-seq) has pursued this sort of (pooled) genome-wide screening with full transcriptional readout at increasing scale. In [one](https://www.cell.com/cell/fulltext/S0092-8674(16)31610-5) of the original 2016 papers, only around 100 genes were knocked out across 200,000 mouse and human cells; yet [in one](https://www.sciencedirect.com/science/article/pii/S0092867422005979) of the most recent papers, all 10,000+ protein-coding genes are inhibited across more than 2.5 million human cells, with full transcriptional readout. 

Yet the genome is composed of more than protein-coding genes, and ideally we’d like to systematically perturb non-protein-coding regions, which play an important role in the regulation of gene expression. The [usefulness of such screens](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7845138/) would be immense:

> The human genome is currently believed to harbour hundreds-of-thousands to millions of enhancers—stretches of DNA that bind transcription factors (TFs) and enhance the expression of genes encoded in cis [i.e., [on the same DNA strand](https://en.wikipedia.org/wiki/Cis-regulatory_element)]. Collectively, enhancers are thought to play a principal role in orchestrating the fantastically complex program of gene expression that underlies human development and homeostasis. Although most causal genetic variants for Mendelian disorders fall in protein-coding regions, the heritable component of common disease risk distributes largely to non-coding regions, and appears to be particularly enriched in enhancers that are specific to disease-relevant cell types. This observation has heightened interest in both annotating and understanding human enhancers. However, despite their clear importance to both basic and disease biology, there is a tremendous amount that we still do not understand about the repertoire of human enhancers, including where they reside, how they work, and what genes they mediate their effects through.

In 2019, the first such massive enhancer inhibition screen with transcriptional readout [was accomplished](https://www.cell.com/cell/fulltext/S0092-8674(18)31554-X), inhibiting nearly 6,000 enhancers across 250,000 cells, an important step to systematic interrogation of all gene regulatory regions.

But inhibition and knockout are blunt methods of perturbation. To truly understand the genome, we must systematically mutate it. Unfortunately, massively parallel methods for profiling the effects of fine-grain enhancer mutations [don’t yet](https://www.nature.com/articles/s41467-019-11526-w) read out transcriptional state at scale, instead opting to trade off readout feature richness for screening throughput via the use of  [reporter gene](https://en.wikipedia.org/wiki/Reporter_gene) assays. However, we’ll likely see fine-grain enhancer mutation screens with transcriptional readout in the coming years.

Yet advances in scopes enable us to interrogate the effects of not only genomic perturbations, but [therapeutic chemical perturbations](https://www.science.org/doi/10.1126/science.aax6234), too:

> High-throughput chemical screens typically use coarse assays such as cell survival, limiting what can be learned about mechanisms of action, off-target effects, and heterogeneous responses. Here, we introduce “sci-Plex,” which uses “nuclear hashing” to quantify global transcriptional responses to thousands of independent perturbations at single-cell resolution. As a proof of concept, we applied sci-Plex to screen three cancer cell lines exposed to 188 compounds. In total, we profiled ~650,000 single-cell transcriptomes across ~5000 independent samples in one experiment. Our results reveal substantial intercellular heterogeneity in response to specific compounds, commonalities in response to families of compounds, and insight into differential properties within families. In particular, our results with histone deacetylase inhibitors support the view that chromatin acts as an important reservoir of acetate in cancer cells.

However, though impressive, it’s an open question whether such massive chemical screens (and all the tool progress we’ve just reviewed) will translate into biomedical progress. 

## 2. The End (of Biomedical Stagnation) Is Nigh

Progress in experimental tools over the past two decades has been remarkable. It certainly feels like biomedical research has been completely revolutionized by these tools. 

This revolution is already yielding advances in basic science. To name but a few:


- Our understanding of longevity has advanced tremendously, from the relationship between [mutation rates and lifespan](https://www.nature.com/articles/s41586-022-04618-z) among mammals, to the molecular basis of cellular [senescence and rejuvenation](https://www.salk.edu/scientist/juan-carlos-izpisua-belmonte/publications/) (which [could have](https://www.nature.com/articles/d41587-022-00002-4) huge clinical implications).


- Open up any issue of Nature or Science and you’re bound to see a few amazing computational biology articles interrogating some biological mechanism with [extreme rigor](https://www.nature.com/articles/s41586-021-04210-x), likely using the newest tools.


- And how can one forget Alphafold, the [solution to a 50-year-old grand challenge in biology](https://www.deepmind.com/research/highlighted-research/alphafold/timeline-of-a-breakthrough). “It will change medicine. It will change research. It will change bioengineering. [It will change everything.](https://www.nature.com/articles/d41586-020-03348-4)” (Well, it isn’t necessarily a product of the tools revolution, but it is a major leap in basic science that contributes to the current mood of optimism.)

Biomedical optimism abounds for other reasons, too. Consider some of the recent clinical successes with novel therapeutic modalities:


- Gene therapy (i.e., genetically edited autologous stem cell transplants) [seem poised](https://www.nejm.org/doi/full/10.1056/NEJMoa2117175) [to solve](https://www.biospace.com/article/releases/vertex-and-crispr-therapeutics-present-new-data-on-more-patients-with-longer-follow-up-treated-with-exagamglogene-autotemcel-exa-cel-at-the-2022-european-hematology-association-eha-congress/?keywords=Vertex) terrible blood disorders like sickle cell disease and [familial hypercholesterolemia](https://www.science.org/content/blog-post/more-crispr-human-subjects). 


- RNA vaccines solved SARS-CoV-2, so maybe they’ll solve [other infectious diseases](https://www.nature.com/articles/d41586-021-02913-9), like [HIV](https://www.niaid.nih.gov/news-events/nih-launches-clinical-trial-three-mrna-hiv-vaccines). Perhaps [they’ll](https://molecular-cancer.biomedcentral.com/articles/10.1186/s12943-021-01335-5) even solve [pancreatic cancer](https://www.mskcc.org/news/can-mrna-vaccines-fight-pancreatic-cancer-msk-clinical-researchers-are-trying-find-out). (Or [how about](https://www.science.org/doi/abs/10.1126/science.aay5967) the immuno-oncology [double-whammy](https://www.aacr.org/about-the-aacr/newsroom/news-releases/new-car-t-cell-therapy-for-solid-tumors-was-safe-and-showed-early-efficacy/): combining CAR-T _[and](https://clinicaltrials.gov/ct2/show/NCT04503278)_ RNA vaccines to treat solid tumors.)

It certainly feels like this confluence of factors—Moore’s-law-like progress in experimental tools, the ever-increasing mountain of biological knowledge they are generating, and a bevy of new therapeutic modalities that are already delivering promising clinical results—is ushering in the biomedical golden-age. Some [say](https://marginalrevolution.com/marginalrevolution/2020/12/why-did-the-great-stagnation-end.html) that “almost certainly the great stagnation is over in the biomedical sciences.”

How much credence should we give this feeling—are claims of the end of biomedical stagnation [pure mood affiliation](https://applieddivinitystudies.com/stagnation/)?


### Premature Celebration

A good place to start would be to define what the end of biomedical stagnation might look like.

One of the necessary, but certainly not sufficient, conditions would be the normalization of what is often called personalized/precision/genomic medicine. Former NIH Director Francis Collins sketched what this world would look like:


> …The impact of genetics on medicine will be even more widespread. The pharmacogenomics approach for predicting drug responsiveness will be standard practice for quite a number of disorders and drugs. New gene-based "designer drugs" will be introduced to the market for diabetes mellitus, hypertension, mental illness, and many other conditions. Improved diagnosis and treatment of cancer will likely be the most advanced of the clinical consequences of genetics, since a vast amount of molecular information already has been collected about the genetic basis of malignancy…it is likely that every tumor will have a precise molecular fingerprint determined, cataloging the genes that have gone awry, and therapy will be individually targeted to that fingerprint.

Here’s the kicker: [that quote is from 2001](https://jamanetwork.com/journals/jama/fullarticle/193524), part of Collins’ 20-year grand forecast about how the then-recently-accomplished Human Genome Project would revolutionize the future of medicine (i.e., what was supposed to be the medicine of today). Unfortunately, his forecast didn’t fare well.

Though the 2000’s witnessed “breathtaking acceleration in genome science,” by the halfway point, things weren’t looking good. But Collins [held out hope](https://www.nature.com/articles/464674a):


> The consequences for clinical medicine, however, have thus far been modest. Some major advances have indeed been made…But it is fair to say that the Human Genome Project has not yet directly affected the health care of most individuals…<br><br>Genomics has had an exceptionally powerful enabling role in biomedical advances over the past decade. Only time will tell how deep and how far that power will take us. I am willing to bet that the best is yet to come.

Another ten years later, it seems his predictions still haven’t been borne out. 

- Precision oncology [fell short](https://www.nature.com/articles/537S63a) of the hype. [Only ~7%](https://www.annalsofoncology.org/article/S0923-7534(21)01121-2/fulltext) of US cancer patients [are predicted to](https://www.science.org/doi/10.1126/science.360.6387.365) benefit from genome-targeted therapy. And oncology drugs approved for a genomic indication [have a poor record](https://www.ejcancer.com/article/S0959-8049(21)01186-2/fulltext) in improving overall survival in clinical trials (good for colorectal cancer and melanoma; a coin-toss for breast cancer; and terrible for non-small cell lung cancer). What we call genome-targeted therapy is merely patient stratification based on a few markers, not the tailoring of therapies based on a “molecular fingerprint”.

- There are no blockbuster “gene-based designer drugs” for the chronic diseases he mentions. 

- Pharmacogenomics [is the exception](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4711261/), not the norm, in the clinic. The number of genes with pharmacogenomic interactions is [now up to around 120](https://cpicpgx.org/genes-drugs/) (though only a subset of interactions are clinically actionable). And, as shown in the precision oncology case, oftentimes the use of genetic markers has little impact on the outcomes of the majority of patients.

Thus, despite the monumental accomplishment of the Human Genome Project, and the remarkable advances in tools that followed from it, we have not yet entered the golden-age of biomedicine that Collins foretold. 

(But don’t worry: though the precision medicine revolution has been slightly delayed, we can expect it to [arrive by 2030](https://www.cell.com/cell/pdf/S0092-8674(21)00058-1.pdf).)


### Biomedical Stagnation Example: Cancer

The optimist might retort: that’s cherry-picking. Even though genomics hasn’t yet had a huge medical impact, and even though Collins’ specific predictions weren’t realized, he is directionally correct: biomedical stagnation is already ending. Forget about tools—just look at all the recent clinical successes.

Take cancer, for instance. Many indicators seem positive: [five-year survival rates](https://ourworldindata.org/cancer-death-rates-are-falling-five-year-survival-rates-are-rising) are apparently improving, and novel therapeutic modalities like immunotherapy and cell therapy are revolutionizing the field. Hype is finally catching up with reality.

Yes, there have undoubtedly been some successes in cancer therapeutics over the past few decades—Gleevec cured ([that is not an exaggeration](https://youtu.be/RjS0T_FK9rk?t=1511)) [chronic myeloid leukemia](https://seer.cancer.gov/statfacts/html/cmyl.html); and checkpoint inhibitors have improved treatment of [melanoma](https://www.nature.com/articles/s41590-022-01141-1), [NSCLC](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6879313/), and a host of other cancers.

But in terms of overall (age-standardized) mortality across all cancers, the picture is mixed.

In the below graph, we see this (note the log-10-transformed y-axis):<input type="checkbox" id="cb13" /><label for="cb13"><sup></sup></label><span><br><br>Unless otherwise noted, all the following analyses look at deaths or disability-adjusted life-years lost per 100k individuals between the ages of 55 and 89, on an age-standardized basis. Data come from [IHME](https://www.healthdata.org/)’s [Global Burden of Disease](https://vizhub.healthdata.org/gbd-results/) dataset.<br><br></span>

![](../assets/log_10_mortality_55_89.png)

Mortality from the biggest killer of the cancers, lung cancer, has fallen due to smoking cessation (the same goes for stomach cancer). The mortality rate for the second biggest killer among women, breast cancer, fell by ⅓ from 1990 to 2019—a good portion of this is attributable to improved therapeutics. Mortality from prostate cancer in men, and colorectal cancer in both sexes, have all also fallen around 30-40%, much of which is attributable to screening.<input type="checkbox" id="cb14" /><label for="cb14"><sup></sup></label><span><br><br>For many cancers, much of the mortality declines can be [chalked up to](https://academic.oup.com/jnci/article/102/9/605/894608) better screening. However, the downside of better screening is [overdiagnosis](https://academic.oup.com/jnci/article/102/9/605/894608) (the negative effects of which, false positives and unnecessary treatment, don’t show up in mortality statistics, but do show up as inflation in [incidence and survival statistics](https://www.nejm.org/doi/full/10.1056/NEJMsr1905447) and [healthcare spending](https://www.nejm.org/doi/full/10.1056/NEJMp1615069)). See inline-note 17 below.<br><br></span>

Yet mortality from pancreatic cancer hasn’t moved. Late-stage breast cancer is still a death sentence. The incidence (and mortality) of liver cancer has [actually increased](https://www.mskcc.org/news/what-s-behind-rise-liver-cancer-deaths-and-what-can-be-done-about-it) among both sexes, [due to](https://pubmed.ncbi.nlm.nih.gov/30362090/) increased obesity. And plenty of the cancers we’ve lowered the incidence of through public health measures—esophageal, lung, stomach—still have [incredibly low survival rates](https://ourworldindata.org/grapher/five-year-cancer-survival-in-usa?time=1977..2013&country=~All+races%2C+total). 


The declines in disability-adjusted life years (DALYs) lost mirror the declines in overall mortality (note again the log-scale):

![](../assets/log_10_daly_55_89.png)


And if you’re wondering if it looks any different for adults ages 55 to 59, perhaps because of an age composition effect, it does not. The declines are all roughly the same compared to the 55 to 89 group (that is, 30-40% declines for the major cancers like breast, prostate, colorectal, ovarian, etc.). 


![](../assets/log_10_mortality_55_59.png)



But one needn’t appeal to mortality or DALY rates to show things are still stagnant. Just look at how shockingly primitive our cancer care still is: we [routinely lop off](https://www.statnews.com/2017/08/29/double-mastectomy-breast-cancer/) body parts and [pump people full of](https://en.wikipedia.org/wiki/Chemotherapy) heavy metals or other cytotoxic agents (most of which were invented in the 20th century), the survival benefits of which are often [measured in months](https://jamanetwork.com/journals/jamaotolaryngology/article-abstract/1891387), not years.

The optimist might push back again: yes, the needle hasn’t moved much for the toughest cancers, but novel modalities like [CAR-T](https://www.cancer.gov/about-cancer/treatment/research/car-t-cells) are _already_ having a huge impact on hematological malignancies, and they’ll someday cure solid tumors. Clearly biomedical stagnation is in the process of ending. Give it a bit of time.

To which the skeptic replies: Yes, CAR-T has shown some great results in some specific blood cancers, and there’s a lot to be optimistic about. But let’s not get ahead of ourselves. When one [critically examines](https://docs.google.com/spreadsheets/d/1GOKZE7f1ksa6mVnML_yPzsh6Fy5qM8k6iBMPXdgXRwQ/edit#gid=0) the [methodology](https://www.youtube.com/watch?v=l5La5xqZoIk) of many CAR-T clinical trials, the survival and quality of life benefits aren’t as impressive as its proponents [would lead you to believe](https://www.youtube.com/watch?v=aUpMZjHCtB8) (as is the case with [many oncology drugs](https://en.wikipedia.org/wiki/Malignant_(book))). We’re likely at least a decade away from CAR-T meaningfully altering annual mortality of any sort of solid tumor.<input type="checkbox" id="cb15" /><label for="cb15"><sup></sup></label><span><br><br>For some patients, CAR-T is life-changing. For instance, [Kymriah](https://en.wikipedia.org/wiki/Tisagenlecleucel), the first CAR-T to be approved by FDA, [reportedly doubles or triples](https://endpts.com/novartis-may-still-be-grappling-with-kymriah-sales-but-historic-car-t-promise-still-shines-through-5-year-data/) the five-year survival rate of pediatric patients with a rare type of refractory leukemia, [compared to](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6583018/) the previous [standard of care](https://en.wikipedia.org/wiki/Clofarabine).<br><br>On the other hand, in adult refractory [diffuse B-cell lymphoma](https://lymphoma.org/aboutlymphoma/nhl/dlbcl/relapseddlbcl/), two phase-3 randomized controlled trials (the gold-standard design in clinical experiments) were recently completed, and the results were mixed: Kymriah [showed no superiority](https://www.nejm.org/doi/full/10.1056/NEJMoa2116596) in event-free survival compared to standard-care; whereas [Yescarta](https://en.wikipedia.org/wiki/Axicabtagene_ciloleucel), another CAR-T therapy, [demonstrated modest improvements](https://www.nejm.org/doi/full/10.1056/NEJMoa2116133) in overall survival after two years (61% vs. 52% in the standard-care group), winning it [FDA marketing approval](https://www.gilead.com/news-and-press/press-room/press-releases/2022/4/yescarta-receives-us-fda-approval-as-first-car-tcell-therapy-for-initial-treatment-of-relapsed-or-refractory-large-bcell-lymphoma-lbcl) as a second-line therapy. (This Yescarta approval builds off its [original 2017 approval](https://www.fda.gov/news-events/press-announcements/fda-approves-car-t-cell-therapy-treat-adults-certain-types-large-b-cell-lymphoma) for late refractory lymphoma, which in a single-arm clinical trial [showed an incredible](https://www.gilead.com/news-and-press/press-room/press-releases/2021/12/yescarta-is-first-car-t-cell-therapy-to-report-five-year-survival-data-from-pivotal-study-showing-durable-long-term-survival-in-patients-with-refract) ~40% five-year overall survival rate in treated patients. There are also [promising results](https://www.mdanderson.org/newsroom/axi-cel-proves-effective-as-first-line-treatment-for-high-risk-lymphoma.h00-159538167.html) for Yescarta as a first-line therapy.)<br><br></span> 

Thus, it seems a bit premature to say biomedical stagnation in cancer has ended, based purely off some recent promising clinical trials—especially when we’ve been repeatedly sold this story before. 

[The war](https://en.wikipedia.org/wiki/War_on_cancer) is still being fought, 50 years on.<input type="checkbox" id="cb16" /><label for="cb16"><sup></sup></label><span><br><br>Obviously we’re painting with an extremely broad brush. One can debate cancer types and subtypes, and how long it will take for new (or, in fact, [not so new](https://irp.nih.gov/catalyst/v27i3/gene-therapy-turns-30-years-old) or [incredibly old](https://www.cancerresearch.org/en-us/immunotherapy/timeline-of-progress)) therapeutic modalities like gene therapy and immunotherapy to show up in the mortality data.<br><br></span> Likewise for the other five [major chronic diseases](https://www.cdc.gov/nchs/fastats/leading-causes-of-death.htm), where the picture is often even bleaker.

![](../assets/top_6_chronic_log_10.png)

We wanted a cure for cancer. Instead we got genetic ancestry reports.

### Real Biomedical Research Has Never Been Tried

The optimist will backpedal and grant that biomedical stagnation hasn’t _yet_ ended for chronic diseases (infectious diseases and monogenic disorders are another question). But despite biomedical progress being repeatedly oversold and under-delivered on, and despite us putting ever-more resources into it, they think this time is different. Yes, Francis Collins said the same thing 20 years ago, but [forget the reference class](https://en.wikipedia.org/wiki/Reference_class_forecasting): _this time really is different_. Those were false starts; this is the real deal. The end of biomedical stagnation is imminent. 

There’s a simple reason for believing this: our tools for interrogating biological systems are on exponential improvement curves, and they are already generating unprecedented insight. Due to the accretive nature of scientific knowledge, it’s only a matter of time before we completely understand these biological systems and cure the diseases that ail them. 

To which the skeptic might say: but didn’t the optimists make that exact same argument 10 or 20 years ago? What’s changed? [Eroom’s law](https://www.nature.com/articles/nrd3681) hasn’t: all the putatively important upstream factors (combinatorial chemistry, DNA sequencing, high-throughput screening, etc.) continue to become better, faster, and cheaper, and our understanding of disease mechanisms and drug targets has only grown, yet the number of drugs approved [per R&D dollar](https://www.nature.com/articles/nrd3681) has halved every 9 years for the past six or seven decades—with this trend [only recently plateauing](https://www.nature.com/articles/d41573-020-00059-3) (not reversing) due to a [friendlier FDA](https://www.baybridgebio.com/blog/biotech-bust-to-boom.html), and drugs targeting rare diseases, finer disease subtypes, and genetically validated targets.

Likewise for returns [per publication and clinical trial](https://web.stanford.edu/~chadj/IdeaPF.pdf#page=24). (And, by the way, [more than half](https://elifesciences.org/collections/9b1e83d1/reproducibility-project-cancer-biology) of major preclinical cancer papers fail to replicate.)<input type="checkbox" id="cb17" /><label for="cb17"><sup></sup></label><span><br><br>Some have critiqued Bloom et al.’s paper on declining returns to R&D. For instance, some [quibble](https://guzey.com/economics/bloom/#in-the-medical-research-section-bloom-et-al-change-the-procedure-of-defining-what-an-idea-to-a-completely-different-one-that-contradicts-the-procedure-they-previously-claimed-to-follow) about how Bloom et al. use a linear rather than exponential life expectancy growth rate as their baseline against which they measure returns to ideas over time.<br><br>But as Bloom et al. [point out](https://guzey.com/economics/bloom/#appendix-a-response-from-nicholas-bloom-charles-i-jones-john-van-reenen-and-michael-webb): “To the extent that growth is linear rather than exponential in certain industries or cases, this only reinforces the point that exponential growth is getting harder to achieve. If linear growth in productivity requires exponential growth in research, then certainly exponential growth is getting harder to achieve. The life expectancy case in the paper clearly and explicitly makes this point.”<br><br>One can also quibble about how the marginal difficulty of adding a year of life increases with age, so therefore we should value every year added more than the previous ones. This is a better critique, but still a relatively minor one.<br><br>But one could also object that Bloom et al.’s measures of medical returns actually _overestimate_ the true return research in the case of cancer. For their measure of years of life saved for cancer they use “the age-adjusted mortality rates for people ages 50 and over computed from 5-year survival rates” (the 5-year survival rate is measured per 1000 diagnosed cases on an [age-adjusted basis](https://seer.cancer.gov/seerstat/tutorials/aarates/definition.html), not per 1000 people in the total population, as some [misapprehend](https://guzey.com/economics/bloom/#for-some-diseases-bloom-et-al-weigh-the-effectiveness-of-medical-research-by-their-incidence-meaning-that-the-more-people-get-the-disease-the-more-effective-the-researchers-become)). However, this measure will overestimate the true years of life saved if cancer is overdiagnosed, by inflating the dominator, the incidence (i.e., how many patients are diagnosed as having cancer).<br><br>This incidence inflation is precisely what happened with breast cancer starting in the 1985-1990 period (when mammography became widespread due to Nancy Reagan’s [high profile](https://www.nytimes.com/1987/10/18/us/surgeons-remove-cancerous-breast-of-nancy-reagan.html) breast cancer case—she even did a [public service announcement](https://www.youtube.com/watch?v=oGKCThkk5Ro) for the American Cancer Society). Advances in therapeutics and catching true positives through screening (i.e., identifying cancers early on that would later become metastatic) both reduced mortality, improving the 5-year survival rate; but widespread screening also led to an increased number of false positives, inflating incidence, and thus the survival rate. The screening boom created a [lasting 30% increase](https://www.nejm.org/doi/full/10.1056/NEJMsr1905447) in apparent breast cancer incidence compared to pre-boom levels, permanently inflating survival rates and exaggerating mortality improvements. (And [it turns out](https://fivethirtyeight.com/features/even-more-evidence-that-mammograms-have-been-oversold/) that screening likely didn’t avert that many lethal cancer cases; most of the mortality decline of the past 30 years [is attributable to](https://www.nejm.org/doi/full/10.1056/NEJMoa1600249) better therapeutics.)<br><br>The screening boom also probably explains the odd “hump shape” seen in the research productivity charts for breast cancer and all cancers (many other cancers experienced similar screening booms, some of which had higher true positive rates, and therefore utility, than others) around 1985 to 1995—it might have been a particularly fecund period for cancer therapeutics, but it also might have just been a period of increasing screening, and therefore overdiagnosis. When one corrects for this screening boom, the hump would likely smooth out, resulting in almost monotonically declining returns to research, as is seen with heart disease (which is measured as a crude age-adjusted mortality rate, not a survival rate, therefore avoiding the effects of any such incidence inflation).<br><br>But there’s yet a bigger reason to think Bloom et al. are overestimating returns to research: the [anti-smoking movement](https://acsjournals.onlinelibrary.wiley.com/doi/pdfdirect/10.3322/canjclin.41.3.137#page=4), certainly one the top-5 highest return medical ideas of the 20th century, [likely drives much](https://www.nber.org/system/files/working_papers/w29145/w29145.pdf#page=32) of the declines in mortality from heart disease and cancer, and perhaps some of the increases in cancer survival rates (yes, even conditional on being diagnosed with cancer), over multiple decades. If one were able to partial out its effects, the returns to medical research would look even worse.<br><br>On net, Bloom et al.’s conclusions hold in the medical domain: exponential increases in research effort are producing, at best, linear reductions in mortality.<br><br></span>

To which the optimist says: we’ve been hamstrung by regulation and only recently developed the experimental tools necessary to do _real_ biomedical research. But now that these tools have arrived, they will change the game. We might even dare to say these tools, combined with advances in software, [enable a](https://centuryofbio.substack.com/p/whats-different-using-the-model) _qualitatively different_ type of experimental biomedical research. Biomedicine will become a “data-driven discipline”:

> …exponential progress in DNA-based technologies—primarily **Sequencing** and **Synthesis** in combination with molecular tools like CRISPR—are totally changing experimental biology. In order to grapple with the new **Scale** that is possible, **Software** is essential. This transition to being a data-driven discipline has served as an additional accelerant—we can now leverage the incredible progress made in the digital revolution [emphasis not added].

Just wait—now that we have the right biological research tools, the end of biomedical stagnation is imminent.

### The Mechanistic Mind’s Translational Conceit

But the optimist is begging the question. They assume progress in biological research will naturally lead to progress in biomedical outcomes, but we’ve repeatedly seen this isn’t the case: our biological research has (apparently) advanced tremendously over the past twenty years, yet this hasn’t translated into similarly tremendous medical results, despite all predictions to the contrary.

Yet the mechanistic mind is confident this will change. This is the mechanistic mind’s translational conceit: that accumulating experimental knowledge and building ever-more reductionistic models of biology will _eventually_ lead to cures for disease. Once we carve nature at the joints (i.e., discover the ground-truth mechanistic structure of biological systems, expressible in human-legible terms), the task of translation will become easy. Through understanding nature, we will learn how to control it.

And if we look back in ten years and the mortality indicators haven’t budged much, then it simply means we’re ten years closer to a cure. This is a marathon, not a sprint. Stay the course: run more experiments, collect more data, and continue carving. The diseases will yield eventually. We must leave no nucleotide unsequenced, no protein un-spectrometered…

### At a Crossroads

The mechanistic mind does not have a concrete model of biomedical progress. Rather, they have unwavering faith that more biomedical research leads to more translational progress. Their optimism is [indeterminate](https://knowyourmeme.com/memes/profit). It is why they are repeatedly disappointed when amazing research discoveries fail to translate into cures but nonetheless maintain faith that more research is the answer—they can’t tell you when the cures will arrive, but at least they know they’re pushing in the right direction.

The mechanistic mind has certainly [done a lot for us](https://www.youtube.com/watch?v=Qc7HmhrgTuQ)—there’s no denying that. But it will not deliver on the biomedical progress it has promised in a timely fashion.

However, there’s no need for despair: this time is, in fact, different. Progress in tools has created the potential for a radically different research ethos that will end biomedical stagnation. But to understand this new research ethos, we must first understand the telos of the mechanistic mind and why it is at odds with the biomedical problem setting.

## 3. The Spectrum of Biomedical Research Ethoses

Let’s return to our original formulation of the biomedical problem setting:

> The purpose of biomedicine is to control the state of biological systems toward salutary ends.

This definition is rather broad. It doesn’t specify how we must go about learning to control biological systems. Let’s reframe the problem to make it more tractable.

### The Dynamics Reframing of Biomedicine

We can first recast this problem as a search problem: given a starting state, $$s_0$$, and a desired end state, $$s_1$$, the task is to find the intervention that moves the system from $$s_0$$ to $$s_1$$.  For instance, a patient is in a diseased state, and you must find the therapeutic intervention that moves them into a healthy state.<input type="checkbox" id="cb17.5" /><label for="cb17.5"><sup></sup></label><span><br><br>This is the simplest case. The more general, medically relevant problem is multi-step planning and control: one chooses an action to perform on the system,  one receives an updated system state, then chooses another action, etc. This is typically formulated as a [Markov Decision Process](https://en.wikipedia.org/wiki/Markov_decision_process).<br><br></span>

However, the space of interventions is large and biology is complex, so brute-force search won’t work. Therefore, we can further recast this search problem as the problem of learning an action-conditional model of biology—i.e., a [dynamics model](https://rail.eecs.berkeley.edu/deeprlcourse/static/slides/lec-11.pdf), to use the language of model-based reinforcement learning—to guide this search through intervention space. A dynamics model takes in an input state (or, in the non-Markovian case, multiple past states) and an action, and predicts the resulting state, $$ f: S \times A → S^\prime $$.

The predictive performance of the dynamics model directly determines the efficiency of the search through intervention space. That is, the better your model predicts the behavior of a biological system, the easier it will be to learn to control it.

Thus, the biomedical control problem reduces to a search problem over intervention space, which itself reduces to the problem of learning a dynamics model to guide this search.<input type="checkbox" id="cb18" /><label for="cb18"><sup></sup></label><span><br><br>This is a temporary simplification. Drug discovery and development is more like a series of iterative search and filtering tasks. Starting with a pool of candidates, one does multiple rounds of online experimentation to search therapeutics space (guided by the dynamics model); these experimental observations are then used to cull or refine the pool of candidates; and this process then repeats.<br><br></span>

Learning this dynamics model is the task of biomedical research. 

However, the mechanistic mind smuggles in a set of assumptions about what form this model must take: 

> This ethos aims to control biological systems by building mechanistic models of them that are explainable and understandable by humans (i.e., human-legible).

By interrogating this set of assumptions, we will see why the mechanistic mind is the wrong research ethos to approach the biomedical dynamics problem from. 


### Telos of The Mechanistic Mind

> ...In that Empire, the Art of Cartography attained such Perfection that the map of a single Province occupied the entirety of a City, and the map of the Empire, the entirety of a Province. In time, those Unconscionable Maps no longer satisfied, and the Cartographers Guilds struck a Map of the Empire whose size was that of the Empire, and which coincided point for point with it. The following Generations, who were not so fond of the Study of Cartography as their Forebears had been, saw that that vast Map was Useless, and not without some Pitilessness was it, that they delivered it up to the Inclemencies of Sun and Winters. In the Deserts of the West, still today, there are Tattered Ruins of that Map, inhabited by Animals and Beggars; in all the Land there is no other Relic of the Disciplines of Geography. — _Jorge Luis Borges_, [On Exactitude in Science](https://en.wikipedia.org/wiki/On_Exactitude_in_Science)

A unifying telos, invariant across phenomena of study and eras of tooling, underlies the mechanistic mind. 

This telos is building a 1-to-1 map of the biological territory—reducing a biological system to a perfectly legible molecular (or perhaps even sub-molecular) diagram of the interactions of its constituent parts. This is how the mechanistic mind intends to carve nature at the joints; it will unify through dissolution.

This isn’t hypothetical: a [simplified version](https://twitter.com/slavov_n/status/1483039647907426304) of such a map of biochemical pathways was created [over 50 years ago](https://www.roche.com/about/philanthropy/science-education/biochemical-pathways/) for the major [metabolic pathways](http://biochemical-pathways.com/#/map/1) and major [cellular and molecular processes](http://biochemical-pathways.com/#/map/2). 


![](../assets/roche_pathways.jpg)


Those two maps are quite large and complex, but they are massively simplified and pre-genomic. Our current maps are far larger and more sophisticated.

These maps take the form of ontologies. For instance, [Gene Ontology](http://geneontology.org/docs/ontology-documentation/) is “the network of biological classes describing the current best representation of the ‘universe’ of biology: the molecular functions, cellular locations, and processes gene products may carry out.” 

Concretely, GO is a massive [directed graph](https://en.wikipedia.org/wiki/Directed_graph) of biological classes (molecular functions, cellular components, and biological processes) and [relations](http://geneontology.org/docs/ontology-relations/) (“is a”, “part of”, “has part”, “regulates”) between them.<input type="checkbox" id="cb19" /><label for="cb19"><sup></sup></label><span><br><br>For instance, within the “biological processes” meta-class, one can look at an _exhaustive_ list of [all biological processes](http://ols.wordvis.com/q=GO:0044848) that are a type of “[biological phase](http://amigo.geneontology.org/amigo/term/GO:0044848)” (itself a type of biological process)—“cell cycle phase”, “estrous cycle phase”, “hair cycle phase”, “menstrual cycle phase”, “reproductive senescence”, and “single-celled organism vegetative growth phase”. These processes contain their own sub-processes, which contain molecular function and cellular components that genes and proteins can be associated with—e.g., [here are](http://amigo.geneontology.org/amigo/search/bioentity?q=*:*&fq=isa_partof_closure:%22GO:0000080%22&sfq=document_category:%22bioentity%22) all the gene products associated with the biological process “mitotic G1 phase.”<br><br></span>

But simple ontologies are just the beginning. One can build extremely complex relational logic atop them, like [qualifiers](http://geneontology.org/docs/go-annotations/) for relational annotations between genes and processes:

> A gene product is associated with a GO Molecular Function term using the qualifier ‘contributes_to’ when it is a member of a complex that is defined as an “irreducible molecular machine” - where a particular Molecular Function cannot be ascribed to an individual subunit or small set of subunits of a complex. Note that the ‘contributes_to’ qualifier is specific to Molecular Functions.

But single annotations, even with qualifiers, are simply not expressive enough to encode the complexity of biology. Luckily, there’s an [ontology of relations](https://obofoundry.org/ontology/ro.html) one can draw on to compose convoluted relations, which can be used to model larger, more complex biological systems:

> GO-Causal Activity Models (GO-CAMs) use a defined “grammar” for linking multiple standard GO annotations into larger models of biological function (such as “pathways”) in a semantically structured manner. Minimally, a GO-CAM model must connect at least two standard GO annotations ([GO-CAM example](http://noctua.geneontology.org/editor/graph/gomodel:5323da1800000002)).<br><br>The primary unit of biological modeling in GO-CAM is a molecular activity, e.g. protein kinase activity, of a specific gene product or complex. A molecular activity is an activity carried out at the molecular level by a gene product; this is specified by a term from the GO MF ontology. GO-CAM models are thus connections of GO MF annotations enriched by providing the appropriate context in which that function occurs. All connections in a GO-CAM model, e.g. between a gene product and activity, two activities, or an activity and additional contextual information, are made using clearly defined semantic relations from the[ Relations Ontology](http://www.obofoundry.org/ontology/ro.html).

For instance, here’s a [graph visualization](http://noctua.geneontology.org/editor/graph/gomodel:596ef51500000088/) of the GO-CAM for the beginning of the WNT signaling pathway: 


![](../assets/wnt_GO_CAM.PNG)


Conceivably, one could use these [causal activity models](https://pubmed.ncbi.nlm.nih.gov/31548717/) to encode all observational and experimental knowledge about biological systems, [including the immense amounts](https://pubmed.ncbi.nlm.nih.gov/31679514/) of genome-wide, single-nucleotide-resolution screening data currently being generated. The potential applications are immense:

>  The causal networks in GO-CAM models will also enable entirely new applications, such as network-based analysis of genomic data  and logical modeling of biological systems. In addition, the models may also prove useful for pathway visualization…With GO-CAM, the massive knowledge base of GO annotations collected over the past 20 years can be used as the basis not only for a genomic-biology representation of gene function but also for a more expansive systems-biology representation and its emerging applications to the interpretation of large-scale experimental data.

The benefit of this sort of model is that it is extremely legible: the ontologies and relations are crystal clear, and every annotation points to the piece of scientific evidence it is based on. It is ordered, clean, and systematic.

And, in effect, this knowledge graph is what most modern biomedical research is working toward. Even if publications aren’t literally added to an external knowledge graph, researchers use the same set of conceptual tools when designing and analyzing their experiments—relations like upregulation, sufficiency and necessity; classes like biological processes and molecular entities—the stuff of the mechanistic mind. Ontologies and causal models are merely an externalization of the collective knowledge graph implicit in publications and the heads of researchers.

And yet, what does this knowledge graph get us in terms of dynamics and control? 

Suppose we were given the ground-truth, molecule-level mechanistic map of some biological system, like a cell, in the form of a directed graph. For instance, imagine this map as a massive, high-resolution [gene regulatory network](https://en.wikipedia.org/wiki/Gene_regulatory_network) describing the inner-workings of the cell.

It’s not immediately clear how we’d use this exact map to control the cell’s behavior, let alone the behavior of larger systems (e.g., a tissue composed of multiple cells). 

One idea is to take the network and model the [molecular kinetics](https://en.wikipedia.org/wiki/Chemical_kinetics) as a system of differential equations, and use this to [simulate the cell](https://en.wikipedia.org/wiki/Cellular_model) at the molecular level. This has [already been tried](https://www.quantamagazine.org/most-complete-simulation-of-a-cell-probes-lifes-hidden-rules-20220224/) for a minimal bacterial cell:

> We present a whole-cell fully dynamical kinetic model (WCM) of JCVI-syn3A, a minimal cell with a reduced genome of 493 genes that has retained few regulatory proteins or small RNAs… Time-dependent behaviors of concentrations and reaction fluxes from stochastic-deterministic simulations over a cell cycle reveal how the cell balances demands of its metabolism, genetic information processes, and growth, and offer insight into the principles of life for this minimal cell. 

In theory, once you’ve built a spatially resolved, molecule-level simulation of the minimal cell, you then move up to a full-fledged cell, then multiple cells, and so on. Eventually you’ll arrive at a perfect simulation of any biological system, which you can do planning over.

The most significant problem you face, obviously, is computational limitations. Therefore, it seems a perfect map of the biological territory wouldn’t make for a good dynamics model.

However, intuitively, it appears that an exact map should give us the ability to predict the dynamics of the cell and, as a result, control it. Even if simulation isn’t possible, shouldn’t understanding the system at a fine-grain level _necessarily_ give us coarser-grain maps that can be used to predict and control the system’s dynamics at a higher level? 

Unfortunately, the answer is no. The issue, it turns out, is that the mechanistic mind’s demand for dynamics model legibility led the model to capture the biological system’s dynamics at the wrong level of analysis using the wrong conceptual primitives.

This is the fundamental flaw in the mechanistic mind’s translational conceit: mistaking advances in mechanistic, human-legible knowledge of smaller and smaller _parts_ of biological systems for advances in predicting the behavior of (and, consequently, controlling) the _whole_ biological systems those parts comprise.

But we needn’t resign ourselves to biomedical stagnation; there are alternative forms of dynamics models which are more suitable for control. Understanding them will require a brief foray into the history of machine learning.


### Three Stories from the History of Machine Learning

By tracing the development of machine learning methods applied to three problem domains—language generation and understanding, game-playing agents, and autonomous vehicles—we will develop an intuition for what direction biomedical dynamics models must head in to end biomedical stagnation.


#### The Bitter Lesson

To make a long story short, these three AI problem domains, and countless others, have undergone a similar evolution, what reinforcement learning pioneer Richard Sutton calls the “[bitter lesson](http://www.incompleteideas.net/IncIdeas/BitterLesson.html)” of AI research:

> The biggest lesson that can be read from 70 years of AI research is that general methods that leverage computation are ultimately the most effective, and by a large margin. The ultimate reason for this is Moore's law, or rather its generalization of continued exponentially falling cost per unit of computation. Most AI research has been conducted as if the computation available to the agent were constant (in which case leveraging human knowledge would be one of the only ways to improve performance) but, over a slightly longer time than a typical research project, massively more computation inevitably becomes available. Seeking an improvement that makes a difference in the shorter term, researchers seek to leverage their human knowledge of the domain, but the only thing that matters in the long run is the leveraging of computation. These two need not run counter to each other, but in practice they tend to. Time spent on one is time not spent on the other. There are psychological commitments to investment in one approach or the other. And the human-knowledge approach tends to complicate methods in ways that make them less suited to taking advantage of general methods leveraging computation…<br><br>The bitter lesson is based on the historical observations that 1) AI researchers have often tried to build knowledge into their agents, 2) this always helps in the short term, and is personally satisfying to the researcher, but 3) in the long run it plateaus and even inhibits further progress, and 4) breakthrough progress eventually arrives by an opposing approach based on scaling computation by search and learning. The eventual success is tinged with bitterness, and often incompletely digested, because it is success over a favored, human-centric approach.

That is, in the long run (i.e., in the data and compute limit), general machine learning methods invariably outperform their [feature-engineered](https://en.wikipedia.org/wiki/Feature_engineering) counterparts—whether those “features” are the data features, the model architecture, the loss function, or the task formulation, all of which are types of [inductive biases](https://en.wikipedia.org/wiki/Inductive_bias) that place a prior on the problem’s solution space.

General methods win out because they meet the territory on its own terms:

> The second general point to be learned from the bitter lesson is that the actual contents of minds are tremendously, irredeemably complex; we should stop trying to find simple ways to think about the contents of minds, such as simple ways to think about space, objects, multiple agents, or symmetries. All these are part of the arbitrary, intrinsically-complex, outside world. They are not what should be built in, as their complexity is endless; instead we should build in only the meta-methods that can find and capture this arbitrary complexity. Essential to these methods is that they can find good approximations, but the search for them should be by our methods, not by us. We want AI agents that can discover like we can, not which contain what we have discovered. Building in our discoveries only makes it harder to see how the discovering process can be done.

As Sutton notes, this lesson is a hard one to digest, and it’s probably not immediately apparent how it applies to biomedicine. So, let’s briefly examine three example cases of the bitter lesson that can act as useful [analogs](https://en.wikipedia.org/wiki/Analogical_models) for the biomedical problem domain. In particular, I hope to highlight cases where machine learning methods superficially take the bitter lesson to heart, only to be superseded by methods that more fully digest it. 


#### Language Understanding, Generation, and Reasoning

> Cyc has never failed to be able to fully capture a definition, equation, rule, or rule of thumb that a domain expert was able to articulate and communicate in English. — [Parisi and Hart](https://cyc.com/wp-content/uploads/2021/04/bayesnetspaper.pdf), 2020

> ML can __never__ give an explicit step-by-step explanation of its line of reasoning behind a conclusion, but Cyc __always__ can. — [Cyc white paper](https://cyc.com/wp-content/uploads/2021/04/Cyc-Technology-Overview.pdf#page=3), 2021

Here’s an abbreviated history of how AI for language progressed over the past 50 years:<input type="checkbox" id="cb20" /><label for="cb20"><sup></sup></label><span><br><br>For a good review of the major events and players in the history of modern AI, see Cade Metz’s _[Genius Makers](https://www.penguinrandomhouse.com/books/565698/genius-makers-by-cade-metz/)_. Neural networks have been around for [70 years or so](https://en.wikipedia.org/wiki/Perceptron), but only recently became the dominant approach to AI.<br><br></span>

Neural networks experienced a [brief moment of hope](https://news.cornell.edu/stories/2019/09/professors-perceptron-paved-way-ai-60-years-too-soon) in the early 60’s, but this was quickly dashed. Neural networks became unfashionable.

From then onward, the dominant approach to language-based reasoning became symbolic AI, which is modeled after “how we think we think”, to use Sutton’s phrase. This approach was realized in, for instance, the [expert systems](https://en.wikipedia.org/wiki/Expert_system) which [became popular](https://hbr.org/1988/03/putting-expert-systems-to-work) in the 70’s and 80’s—and it is still being pursued by projects like [Cyc](https://en.wikipedia.org/wiki/Cyc).

In the 90’s and 00’s, simple statistical methods like Naive Bayes and random forest began to be applied to language sub-tasks like [semantic role labeling](https://en.wikipedia.org/wiki/Semantic_role_labeling) and [word sense disambiguation](https://en.wikipedia.org/wiki/Word-sense_disambiguation); symbolic logic still dominated all complex reasoning tasks. Neural networks were outside the mainstream, but a small group of researchers [continued working on them](https://papers.nips.cc/), making [important breakthroughs](https://www.nature.com/articles/323533a0).<input type="checkbox" id="cb21" /><label for="cb21"><sup></sup></label><span><br><br>Looking at the [major AI conference proceedings](https://en.wikipedia.org/wiki/AAAI_Conference_on_Artificial_Intelligence) from this period ([1990](https://openreview.net/group?id=dblp.org/conf/AAAI/1990), [2000](https://openreview.net/group?id=dblp.org/conf/AAAI/2000), and [2010](https://openreview.net/group?id=dblp.org/conf/AAAI/2010)) is instructive. In retrospect, it’s somewhat hard to fathom that as late as 2010 researchers were studying [forest-based methods for semantic role labeling](https://www.aaai.org/ocs/index.php/AAAI/AAAI10/paper/view/1835/2143).<br><br></span>

But by the early 2010’s, neural networks started to take off, demonstrating state of the art performance on everything from [image recognition](https://en.wikipedia.org/wiki/AlexNet) to [language translation](https://papers.nips.cc/paper/2014/file/a14ac55a4f27472c5d894ec1c3c743d2-Paper.pdf) (even though in some cases [the solutions](https://en.wikipedia.org/wiki/LeNet) had been [around for more than twenty years](https://www.youtube.com/watch?v=FwFduRA_L6Q), waiting for the right hardware and data to come along). However, these neural networks still used specialized architectures, training procedures, and datasets for particular tasks.

Finally, in the past five years, Sutton’s bitter lesson has been realized: a single, general-purpose neural network architecture, fed massive amounts of messy, varied data, trained using very simple loss functions and lots of compute, has come to dominate not only all language tasks, but also domains like vision and speech—part of the “[ongoing consolidation in AI](https://twitter.com/karpathy/status/1468370605229547522)”: 

> You can feed it sequences of words. Or sequences of image patches. Or sequences of speech pieces. Or sequences of (state, action, reward) in reinforcement learning. You can throw in arbitrary other tokens into the conditioning set—an extremely simple/flexible modeling framework.

The neural network naysayers were proven wrong and the believers vindicated: in 2022, massive language models are resolving [Winograd schemas](https://en.wikipedia.org/wiki/Winograd_schema_challenge) at [near-human levels](https://arxiv.org/pdf/2204.02311.pdf#page=12) and [explaining jokes](https://arxiv.org/pdf/2204.02311.pdf#page=38)—and on many tasks [surpassing](https://arxiv.org/pdf/2204.02311.pdf#page=17) average human performance. And yet, they’re only able to do this because we do _not_ hard-code our understanding of semantic ambiguity or humor into the model, nor do we _directly_ ask the model to produce such behaviors.


#### Game-Playing Agents

The evolution of AI for game-playing agents parallels that of AI for language in many ways. To take chess as an example, we can divide it into three eras: the DeepBlue and Stockfish era, the AlphaZero era, and the MuZero era.

Both DeepBlue and Stockfish use massive brute-force [search algorithms](https://en.wikipedia.org/wiki/Alpha%E2%80%93beta_pruning) with [hand-crafted evaluation functions](https://en.wikipedia.org/wiki/Evaluation_function#Handcrafted_evaluation_functions) (i.e., the function used during search to evaluate the strength of a position) based on expert knowledge, and a host of chess-specific heuristics. Chess researchers were understandably upset when these “inelegant” methods began to defeat humans. As Sutton tells it:

> In computer chess, the methods that defeated the world champion, Kasparov, in 1997, were based on massive, deep search. At the time, this was looked upon with dismay by the majority of computer-chess researchers who had pursued methods that leveraged human understanding of the special structure of chess. When a simpler, search-based approach with special hardware and software proved vastly more effective, these human-knowledge-based chess researchers were not good losers. They said that “brute force” search may have won this time, but it was not a general strategy, and anyway it was not how people played chess. These researchers wanted methods based on human input to win and were disappointed when they did not.

Whereas [AlphaZero](https://www.gwern.net/docs/reinforcement-learning/model/alphago/2018-silver.pdf#deepmind) dispenses with all the chess-specific expert knowledge and instead uses a neural network to _learn_ a value function atop a [more general](https://philippmuens.com/minimax-and-mcts) [search algorithm](https://en.wikipedia.org/wiki/Monte_Carlo_tree_search). Furthermore, it learns this all by training purely through self-play (that is, by playing with itself—it isn’t given a bank of past chess games to train on, only the rules of the game). It is so general an architecture that it can learn to play not only chess, but also Go and Shogi.

AlphaZero not only handily beats Stockfish, but does so using less inference-time compute, making it arguably more human-like in its play than its “brute-force” predecessors:<input type="checkbox" id="cb22" /><label for="cb22"><sup></sup></label><span><br><br>Because it uses more compute at training time to learn a superior value function, reducing the amount of test-time compute needed.<br><br></span>

> AlphaZero searches just 60,000 positions per second in chess and shogi, compared with 60 million for Stockfish…AlphaZero may compensate for the lower number of evaluations by using its deep neural network to focus much more selectively on the most promising variations—arguably a more human-like approach to searching, as originally proposed by Shannon.

Finally, [MuZero](https://www.furidamu.org/blog/2020/12/22/muzero-intuition/) takes AlphaZero and makes it even more general: it learns to play any game _without_ being given the rules. Instead, MuZero bootstraps a latent dynamics model of the environment through interacting with it, and uses this learned dynamics model for planning. This latent planning allows it to learn tasks, like Atari games, which were previously not seen as the province of model-based reinforcement learning because of their high state-space dimensionality. In fact, MuZero is so general a learning method that it can be applied to non-game tasks like [video compression](https://www.deepmind.com/blog/muzeros-first-step-from-research-into-the-real-world). If you can give it a reward signal, MuZero will learn it.


#### Autonomous Vehicles

Autonomous vehicles (AV) are by far the most instructive of the analogs, because the battle is still being played out in real time and many people are mistaken about which approach will win. Additionally, the psychological barriers to arriving at the correct approach (namely, an inability to abstract) are similar to the psychological barriers end-to-end machine learning approaches in biomedicine will face. 

We can divide modern AV approaches into two basic camps: the feature-engineering camp of Waymo et al., and the end-to-end approach of Comma.ai and Wayve (and, to a lesser extent, Tesla). Both camps use “machine learning”, but their mindsets are radically different. 

The classical approach to AV—pursued by Waymo, Cruise, Zoox, et al. (all the big players in AV that you’ve likely heard of)—decomposes the task of driving into a set of human-understandable sub-problems: perception, planning, and control. By engineering human knowledge into the perception stack, this approach hopes to simplify planning and control. 

These companies use fleets of vehicles, decked out with expensive sensors, to collect massive amounts of high-resolution data, which they use to build [high-definition maps](https://blog.waymo.com/2020/09/the-waymo-driver-handbook-mapping.html) of new environments: 

> To create a map for a new location, our team starts by manually driving our sensor equipped vehicles down each street, so our custom lidar can paint a 3D picture of the new environment. This data is then processed to form a map that provides meaningful context for the Waymo Driver, such as speed limits and where lane lines and traffic signals are located. Then finally, before a map gets shared with the rest of the self-driving fleet, we test and verify it so it’s ready to be deployed.<br><br>Just like a human driver who has driven the same road hundreds of times mostly needs to focus only on the parts of the environment that change, such as other vehicles or pedestrians, the Waymo Driver knows permanent features of the road from our highly-detailed maps and then uses its onboard systems to accurately perceive the world around it, focusing more on moving objects. Of course, our streets are also evolving, so if a vehicle comes across a road closure or a construction zone that is not reflected in a map, our robust perception system can recognize that and make adjustments in real-time.

But mapping only handles the static half of the perception problem. While on the road, the AV must also perceive and interact with active agents in the environment—cars, pedestrians, small animals. To do this, the AV’s are [trained on](https://blog.waymo.com/2022/03/expanding-waymo-open-dataset-with-new-labels.html) a variety of supervised machine learning perception tasks, like detecting and localizing moving agents. However, sometimes localization and detection aren’t enough—for instance, you might need [to train](https://arxiv.org/pdf/2112.12141.pdf) the model to estimate [pedestrian poses and keypoints](https://blog.waymo.com/2022/02/utilizing-key-point-and-pose-estimation.html), in order to capture the subtle nuances that are predictive of pedestrian behavior:

> Historically, computer vision relies on rigid bounding boxes to locate and classify objects within a scene; however, one of the limiting factors in detection, tracking, and action recognition of vulnerable road users, such as pedestrians and cyclists, is the lack of precise human pose understanding. While locating and recognizing an object is essential for autonomous driving, there is a lot of context that can go unused in this process. For example, a bounding box won't inherently tell you if a pedestrian is standing or sitting, or what their actions or gestures are.<br><br>Key points are a compact and structured way to convey human pose information otherwise encoded in the pixels and lidar scans for pedestrian actions. These points help the Waymo Driver gain a deeper understanding of an individual's actions and intentions, like whether they’re planning to cross the street. For example, a person's head direction often indicates where they plan to go, whereas a person's body orientation tells you which direction they are already heading. While the Waymo Driver can recognize a human's behavior without using key points directly using camera and lidar data, pose estimation also teaches the Waymo Driver to understand different patterns, like a person propelling a wheelchair, and correlate them to a predictable future action versus a specific object, such as the wheelchair itself.

The resulting perception stack produces [orderly and beautiful](https://youtu.be/f2u2HlTgEWY) visualizations: the maps are clean, every pedestrian and car is localized, and objects have an incredible level of granularity. 

Then comes the task of planning and control: the AV is fed this human-engineered scene representation (i.e., the high-definition map with agents, stop signs, and other objects in it) and is [trained to predict and plan against](https://arxiv.org/pdf/2206.00991v1.pdf) the behavior of other agents in this feature space, all while obeying a set of hand-engineered rules written atop the machine-learned perception stack—stop at stop signs, yield to pedestrians in the crosswalk, don’t drive above the speed limit, etc.

However, this piecewise approach has one fatal flaw, claim the end-to-end camp: it relies on a brittle, human-engineered feature space. Abstractions like “cone” and “pedestrian pose” might suffice in the narrow, unevolving world of a [simulator](https://carla.org/) or a [suburb of Phoenix](https://www.wired.com/story/32-hours-chandler-arizona-self-driving-capital/), but these abstractions won’t robustly and completely capture all the dynamic complexities of real-world driving. Waymo et al. may use machine learning, but they haven’t yet learned the bitter lesson.<input type="checkbox" id="cb23" /><label for="cb23"><sup></sup></label><span><br><br>Waymo has recently published some impressive work on using transformers for [whole-scene multi-agent motion prediction](https://arxiv.org/pdf/2106.08417v3.pdf), but they’re fundamentally still doing planning in a human-engineered feature space.<br><br>And setting aside this issue, their approach is incredibly expensive to scale up because of the sensors and humans required to build and massage the high-definition maps this approach relies on. (Though see Waymo’s recent work, [Block-NeRF](https://waymo.com/research/block-nerf/), which should reduce the human effort needed to build such maps, and will have useful applications beyond AVs.)<br><br></span>

Rather, as with other complex tasks, the ultimate solution will be learned end-to-end—that is, directly from sensor input to motion planning, without intermediate human-engineered abstraction layers—thereby fully capturing the complexity of the territory. Wayve (not to be confused with Waymo) founder Alex Kendall [explicitly cites](https://arxiv.org/pdf/2108.05805.pdf) large language models and game-playing agents as precedents for this:

> We have seen good progress in similar fields by posing a complex problem as one that is able to [be] modeled end-to-end by data. Examples include natural language processing with GPT-3, and in games with MuZero and AlphaStar. In these problems, the solution to the task was sufficiently complex that hand-crafted abstraction layers and features were unable to adequately model the problem. Driving is similarly complex, hence we claim that it requires a similar solution.<br><br>The solution we pursue is a holistic learned driver, where the driving policy may be thought of as learning to estimate the motion the vehicle should conduct given some conditioning goals. This is different to simply applying increasing amounts of learning to the components of a classical architecture, where the hand-crafted interfaces limit the effectiveness of data.<br><br>The key shift is reframing the driving problem as one that may be solved by data. This means removing abstraction layers used in this architecture and bundling much of the classical architecture into a neural network…

Likewise, Comma.ai founder George Hotz is pursuing the end-to-end approach and thinks something like [MuZero will ultimately be](https://youtu.be/pGF2xK_Hntw?t=412) the solution to self-driving cars: rather than humans feature-engineering a perception space for the AV to plan over, the AV will implicitly learn to perceive the control-relevant aspects of the scene’s dynamics (captured by a latent dynamics model) simply by training to predict and imitate how humans drive (this training is [done offline](https://openreview.net/pdf?id=HKtsGW-lNbw), of course). 

Hotz paraphrased Sutton’s bitter lesson as the reason for his conviction in the end-to-end approach:<input type="checkbox" id="cb24" /><label for="cb24"><sup></sup></label><span><br><br>This comment was made in the context of criticizing Tesla’s [pseudo-end-to-end](https://youtu.be/qVusyPcqx7Q?t=123) [multitask approach](https://slideslive.com/38917690/multitask-learning-in-the-wilderness).<br><br></span>

> The tasks themselves are not being learned. This is feature-engineering. It’s slightly better feature-engineering, but it still fundamentally is feature-engineering. And if the history of AI has taught us anything, it’s that feature-engineering approaches will always be replaced and lose to end-to-end approaches.


 

And the results speak for themselves: the feature-engineering camp has for years been claiming they’d have vehicles (without safety drivers) on the road soon, yet only recently started offering such services in San Francisco (which [has already](https://www.cbsnews.com/sanfrancisco/news/dead-end-sf-street-plagued-with-confused-waymo-cars-trying-to-turn-around-every-5-minutes/) caused [some incidents](https://www.wired.com/story/cruises-robot-car-outages/)). Conversely, the end-to-end approach, which uses [simple architectures](https://blog.comma.ai/end-to-end-lateral-planning/) and lots of data, is already demonstrating impressive performance [on highways](https://www.youtube.com/results?search_query=openpilot&sp=EgQIBBAB) and in [busy urban areas](https://www.youtube.com/watch?v=h8AhWKOUSPU) (even generalizing to [completely novel cities](https://www.youtube.com/playlist?list=PL5ksjZd5b6SKB_TSdOwCTtv1tYarzPJOn)), and is slowly improving—the AVs are even starting to [implicitly understand stop signs](https://www.youtube.com/watch?v=Of--Feiwyxw&list=PLawfivpGQ-vpGgBHu4Bs7IuewbQXR4qBt&index=1), despite never being explicitly trained to do so.


### The Full Spectrum of Biomedical Research Ethoses

These three analogs all share the same lesson: there’s a direct tradeoff between human-legibility and predictive performance, and in the long-run, low-inductive-bias models fed lots of data will win out.

But it’s unclear if this lesson applies to biomedicine. Is biology so complex and contingent that its dynamics can only be captured by large machine learning models fed lots of data? Or can biomedical dynamics only be learned data-efficiently by humans reasoning over data in the language of the mechanistic mind?<input type="checkbox" id="cb25" /><label for="cb25"><sup></sup></label><span><br><br>One cut on this is how physics-like you think the future of biomedical research is: are there human-comprehensible “general laws” of biomedical dynamics left to discover, or have all the important ones already been discovered? And how lumpy is the distribution of returns to these ideas—will we get another theory on par with Darwin’s?<br><br>For instance, RNA polymerases were [discovered over 50 years ago](https://www.nature.com/articles/s41594-019-0303-1), and a tremendous amount of basic biology knowledge has followed from this discovery—had we never discovered them, our knowledge of transcriptional regulation, and therefore biomedical dynamics, would be correspondingly impoverished. Yet [when](https://en.wikipedia.org/wiki/List_of_Nobel_laureates_in_Physiology_or_Medicine) [was](https://en.wikipedia.org/wiki/List_of_Nobel_laureates_in_Chemistry) the last time we made a similarly momentous discovery in basic biology? Might biomedicine be exhausted of grand unifying theories, left only with factoids to discover? Or might these theories and laws be inexpressible in the language of human-legible models?<br><br></span>

Throwing out the scientific abstractions that have been painstakingly learned through decades of experimental research seems like a bad idea—we probably shouldn’t ignore the concept of genes and start naively using raw, unmapped sequencing reads. But, on the other hand, once we have enough data, perhaps these abstractions will hinder dynamics model performance—raw reads contain information (e.g., about transcriptional regulation) that isn’t captured by mapped gene counts. These abstractions may have been necessary to reason our way through building tools like sequencing, but now that they’ve been built, we must evolve beyond these abstractions. 

We can situate one’s views on this issue along a spectrum of research ethoses. On one pole is the mechanistic mind, on the other is the end-to-end approach, or what we might call the “totalizing machine learning” approach to biomedical research. These two poles can be contrasted as follows:


<table>
  <tr>
   <td>
   </td>
   <td><b>Mechanistic mind</b>
   </td>
   <td><b>Totalizing ML mind</b>
   </td>
  </tr>
  <tr>
   <td><b>Primary value</b>
   </td>
   <td>Human understanding
   </td>
   <td>Control
   </td>
  </tr>
  <tr>
   <td>Asks the question(s):
   </td>
   <td>How? Why?
   </td>
   <td>What do I do to control this system?
   </td>
  </tr>
  <tr>
   <td>Model primitive
   </td>
   <td>Directed graph model (transparent, legible)
   </td>
   <td>Neural network model (opaque, illegible)
   </td>
  </tr>
  <tr>
   <td>Primary dynamics model use
   </td>
   <td>Reason over
   </td>
   <td>Predict, control
   </td>
  </tr>
  <tr>
   <td>Problem setting
   </td>
   <td>Schismatic: N separate biological systems to map, at M separate scales
   </td>
   <td>Convergent: 1 general, unified biological dynamics problem
   </td>
  </tr>
  <tr>
   <td>Problem solution
   </td>
   <td>Piecewise
   </td>
   <td>End-to-end
   </td>
  </tr>
  <tr>
   <td>Epistemic mood
   </td>
   <td>Ordered, brittle
   </td>
   <td>Anarchic (anything goes), messy, robust
   </td>
  </tr>
  <tr>
   <td>Failure mode
   </td>
   <td>Mechanism fetish, human cognitive limits
   </td>
   <td>Interpolation without extrapolation, data-inefficiency
   </td>
  </tr>
</table>


I’ll argue that in the long-run, the totalizing machine learning approach is the only way to solve biomedical dynamics. We will now explain why that is, and attempt to envision what that future might look like.

## 4. The Scaling Hypothesis of Biomedical Dynamics 

> Someone interested in machine learning in 2010 _might_ have read about some interesting stuff from weirdo diehard connectionists in recognizing hand-written digits using all of 1–2 million parameters, or some modest neural tweaks to standard voice-recognition hidden Markov models⁠. In 2010, who would have predicted that over the next 10 years, deep learning would undergo a Cambrian explosion causing a mass extinction of alternative approaches throughout machine learning, that models would scale up to 175,000 million parameters, and that these enormous models would just spontaneously develop all these capabilities? — _Gwern_, [The Scaling Hypothesis](https://www.gwern.net/Scaling-hypothesis)

> Science is essentially an anarchic enterprise: theoretical anarchism is more humanitarian and more likely to encourage progress than its law-and-order alternatives. — _Paul Feyerabend_, [Against Method](https://en.wikipedia.org/wiki/Against_Method)

The [scaling hypothesis](https://www.gwern.net/Scaling-hypothesis) is the totalizing machine learning mind’s solution to biomedical dynamics.

At the highest level, the scaling hypothesis for biomedical dynamics is the claim that training a massive, generative, low-inductive-bias neural network model on large volumes of messy, multi-modality biological data (text, omics, images, etc.), using simple training strategies, will produce an arbitrarily accurate biomedical dynamics prediction function.

Just as large models trained on human language data learn to approximate the general function “talk (and, eventually, reason) like a human”, large models trained on biological data will learn to approximate the general function “biomedical dynamics”—without needing to simulate the true causal structure of the underlying biological system. Show a model enough instances of a system’s dynamics, and it will learn to predict them.

To give a simple example: if one wanted to develop a model of single-cell dynamics, they’d take a large neural network (the architecture doesn’t matter, as long as it’s general and has low inductive bias<input type="checkbox" id="cb26" /><label for="cb26"><sup></sup></label><span><br><br>Granted, given the scale of biomedical data, the architecture probably matters somewhat. Making computation local and hierarchical seems like a smart biological inductive bias.<br><br></span>) and feed it all the [scientific publications](https://pubmed.ncbi.nlm.nih.gov/) and experimental and observational [omics data](https://www.ncbi.nlm.nih.gov/geo/) they could get their hands on (how you feed these data in doesn’t matter much either—you could probably model them as text tokens, though you'd need to treat them [as a set, not a sequence](https://arxiv.org/abs/1810.00825)). These data contain information about the correlational structure of single-cell state space and the dynamics, both action-conditional and purely observational, on this state space. By masking these data and training the model to predict the masked tokens, the model will [implicitly learn the dynamics](https://www.biorxiv.org/content/10.1101/2021.11.24.469554v2.full) underlying the data. This knowledge will be stored in the weights of the model and can be accessed by querying it. This learned dynamics model can then be used for single-cell planning and control.

Then extend this approach to all forms and scales of biological data.


### Why The Scaling Hypothesis Wins Out

In the short-term, feature-engineering approaches will have the advantage in biomedical dynamics, as they did in other domains—for instance, the highest-performing single-cell dynamics model of today would likely be a smaller machine-learning model with lots of inductive biases (e.g., a graph inductive bias to mirror the graph-like structure of the gene regulatory networks generating the single-cell omics data), trained on heavily massaged data, not a massive, blank-slate neural network. But in the long-run, general, low-inductive-bias neural networks will win out over narrower, specialized dynamics models, for three reasons: dynamics incompressibility, model subsumption, and data flows.


#### Dynamics Incompressibility and Generality

The richness and complexity of biomedical dynamics exceed human cognitive capacity, and can therefore not be fully captured by human-legible models. Human-legible models must compress these dynamics, projecting them onto lower-dimensional maps written in the language of human symbols, which necessarily involves a tradeoff with dynamics prediction performance—simply put, legibility is a strong inductive bias. This tradeoff also applies to machine learning models insofar as they are legibility-laden.

Whereas large neural networks do not make this tradeoff between human understanding and predictive performance; they meet the territory on its own terms. By modeling raw data of all modalities, they can approximate any biological function without concern for notions of mechanism or the strictures of specialized, siloed problem domains. They can pick up on subtle patterns in the data, connections across scales that human-biased models are blind to. Feed them enough data, and they’ll find the predictive signal.


#### Subsumption

The mechanistic mind will continue to produce artifacts explaining biomedical dynamics—publications, figures, knowledge bases, statistics, labeled datasets, etc. Large multimodal neural networks, because they’re agnostic about what sorts of data they take in, will ingest these mechanistic models, improving dynamics modeling. This is how the neural network will initially bootstrap its understanding of biological dynamics, coasting off the modeling efforts of the mechanistic mind instead of learning a world model from scratch, and then moving beyond it.

However, the converse is not true. The mechanistic mind is incapable of subsuming the totalizing machine learning mind. A neural network’s weights can model an ontology, but not vice versa. 


#### Data Flows and Messiness-Tolerance

Large neural networks will ingest the massive amounts of public biological data coming out in the form of omics, images, etc. These data are messy, but the models are robust to this: they tolerate partially observable, noisy, variable-length, poorly-formatted data of all modalities. The model’s performance is directly indexed against these data flows, which will only become stronger over time, due to cost declines in the tools that generate them.

Whereas narrow, specialized methods that rely on cleaner, more structured data will not experience the same tailwind, for they simply cannot handle the messy data being produced. As Daphne Koller, founder of Insitro (which develops such narrow, specialized models), [says](https://future.com/koller-insitro-drug-discovery-ai-alphafold/):

> We also don’t do enough as a community to really establish a consistent set of best practices and standards for things that everybody does. That would be hugely helpful, not only in making science more reproducible but also in creating a data repository that is much more useful for machine learning.<br><br>I mean, if you have a bunch of data collected from separate experiments with a separate set of conditions, and you try to put them together and run machine learning in that, it’s just going to go crazy. It’s going to overfit on things that have nothing to do with the underlying biology because those are going to be much more predictive and stronger signals than the biology that you’re trying to interrogate. So I think we need to be doing better as a community to enable reproducible science.

Because of the nature of academia, these coordination problems won’t be solved. Therefore, Koller and others [will have to](https://www.insitro.com/about) rely on smaller datasets, often created in-house:

> [W]hile access to large, rich data sets has driven the success of machine learning, such data sets are still rare in biology where data generation remains largely artisanal. By enabling the production of massive amounts of biological data, the recent advancements in cell biology and bioengineering are finally enabling us to change this.<br><br> It is this observation that lies at the heart of insitro. Instead of relying on the limited existing “found” data, we leverage the tools of modern biology to generate high-quality, large data sets optimized for machine learning, allowing us to unleash the full potential of modern computational approaches.

However, these in-house datasets will always be dwarfed by messy public data flows. The method that wins the race to solve biomedical dynamics must be able to surf this coming data deluge.<input type="checkbox" id="cb27" /><label for="cb27"><sup></sup></label><span><br><br>One analogy is: Insitro et al. are to drug discovery as Waymo et al. are to autonomous vehicles. Just as some think autonomous vehicles will be solved by building high-definition maps of cities and modeling dynamics at the level of individual pedestrian behavior, some think biomedicine will be solved by building high-definition molecular [“maps” of diseases](https://cellarity.com/platform) and modeling dynamics at the level of individual cellular behavior. Though they are directionally correct in their use of machine learning, they [fail to](https://biotech-insider.com/cellarity-nets-123m-to-drive-cell-behavior-pipeline-toward-clinic/) abstract [sufficiently](https://www.youtube.com/watch?v=hbLiehrC2DQ&t=460s). <br><br></span>


### An Empirical Science of Biomedical Dynamics

All these arguments seem rather faith-based. Yes, given infinite data, the end-to-end approach will learn a superior biomedical dynamics model. But in practice, we don’t have infinite data.

But we can qualify and quantify our faith in the scaling hypothesis, because the performance of large neural networks obeys predictable functions of data and computation. This is the secret of the scaling hypothesis: scaling laws.

More precisely, scaling laws refer to the empirical finding that a neural network’s error on a task smoothly decreases as a power-law function of the size of that neural network and how much data you train it on (when one is not bottlenecked by the other).

These power-law trends can be visualized as straight lines on [log-log plots](https://en.wikipedia.org/wiki/Log%E2%80%93log_plot), where each increment on the x- and y-axis denotes a relative change (i.e., a percentage change), rather than an absolute change. The exponent of the power law is equivalent to the slope of the scaling trendline on this log-log plot. 

![](../assets/kaplan_2020_scaling.PNG)


Scaling laws are [relatively](https://arxiv.org/pdf/2207.10551.pdf) invariant across [model architectures](https://arxiv.org/pdf/2202.01169.pdf), tasks, data modalities, and orders of magnitude of compute (which likely [reflects deep truths](https://en.wikipedia.org/wiki/Power_law#Universality) about the nature of dynamical systems).<input type="checkbox" id="cb28" /><label for="cb28"><sup></sup></label><span><br><br>Scaling laws for dynamical systems originally [came out of](https://www.youtube.com/watch?v=NLKJdcb1E5I) physics, specifically [statistical mechanics](https://en.wikipedia.org/wiki/Statistical_mechanics), which studies the macroscopic behavior of ensembles of microscopic entities and has deep connections to information theory (via thermodynamics). Interestingly, one of the “founders” of scaling laws for neural networks, Jared Kaplan, [worked in](https://scholar.google.com/citations?hl=en&user=KNr3vb4AAAAJ&view_op=list_works&sortby=pubdate) [theoretical physics](https://www.youtube.com/watch?v=EsP7walAtpk) (including particle physics) prior to working in machine learning. As Kaplan et al. note in their paper, which set off the scaling revolution in deep learning (but which [was not the first](https://arxiv.org/pdf/1712.00409.pdf) paper to observe scaling behavior in neural networks):<br><br><i>"At this point we do not know which of our results depend on the structure of natural language data, and which are universal. It would also be exciting to find a theoretical framework from which the scaling relations can be derived: a ‘statistical mechanics’ underlying the ‘thermodynamics’ we have observed."</i><br><br>Likewise, [Geoffrey West](https://en.wikipedia.org/wiki/Geoffrey_West#Selected_publications), who did fundamental work on [allometric scaling laws in biology](http://umdberg.pbworks.com/w/file/fetch/48318752/Science-1997-West.pdf), also worked in particle physics.<br><br>Note also that RA Fisher, one of the forefathers of the Modern Synthesis, [compared](https://archive.org/details/geneticaltheoryo031631mbp/page/n59/mode/2up) his [fundamental theorem of natural selection](https://en.wikipedia.org/wiki/Fisher%27s_fundamental_theorem_of_natural_selection) to the second law of thermodynamics:<br><br><i>"It will be noticed that the fundamental theorem proved above bears some remarkable resemblances to the second law of thermodynamics. Both are properties of populations, or aggregates, true irrespective of the nature of the units which compose them; both are statistical laws; each requires the constant increase of a measurable quantity, in the one case the entropy of a physical system and in the other the fitness, measured by m, of a biological population."</i><br><br></span>

They were originally found [in language](https://arxiv.org/pdf/2001.08361.pdf). Then they were found to apply to other modalities like [images, videos, and math](https://arxiv.org/pdf/2010.14701.pdf#page=3). Then they were found to even generalize to the [performance of game-playing agents](https://arxiv.org/pdf/2104.03113.pdf) on reinforcement learning tasks. They [show up everywhere](https://www.gwern.net/notes/Scaling).

We might say that scaling laws are a quantitative framework for describing the amount of data and model size needed to approximate the dynamics of _any_ (evolved) complex system [using a neural network](https://en.wikipedia.org/wiki/Universal_approximation_theorem). 

This is the upshot of the totalizing machine learning approach to biomedicine: by treating the biomedical control problem as a dynamics modeling problem, and learning these dynamics through large neural networks, biomedical progress becomes a predictable function of how much data and computation we feed these neural networks.


### Objections to the Scaling Hypothesis

However, we face two problems if we naively try to apply the scaling hypothesis to biomedicine in this way:

1. Biomedical data acquisition has a cost. Unlike chess or Atari, you can’t simply collect near-infinite data, particularly experimental data, from your target biological system, humans. We don’t have access to a perfect simulator. In the real world, we must do much of our research in non-human model systems.

2. In biomedicine, data doesn’t miraculously fall from the heavens like manna. The keystone of biomedical research is _experimentation_—we must actively seek out data to update our models. Brute-forcing our way to a dynamics model by collecting random data would be woefully inefficient.

By investigating these two obstacles to the scaling hypothesis, and thinking more seriously about how training data is acquired, we will arrive at an empirical law of biomedical progress.

## 5. Biocompute Bottleneck

A problem besets all approaches to learning biomedical dynamics: human experimental data is hard to come by. This poses a particular problem for the scaling hypothesis. How are we supposed to learn a dynamics model of our target biological system if we can’t acquire data from it? 


### Of Mice, Men, and Model Systems

We must instead learn a dynamics model through experimentation in [model systems](https://en.wikipedia.org/wiki/Model_organism).

The difficulty of working with model systems can best be understood through analogies to the AI problem domains we reviewed earlier.

One analogy is to the autonomous vehicle domain: in biomedicine, like in autonomous vehicles, you can’t train your driving policy online (i.e., in a live vehicle on the road), so you must passively collect data of humans driving correctly and use this to train a policy offline via imitation. The only problem is that in biomedicine we aren't trying to imitate good driving, but train a policy that corrects driving from off-road (i.e., disease) back on-road (i.e., health); therefore, we don’t have many offline datasets to train on. So, we have to settle for training our policy on a different vehicle (a mouse) in a different terrain (call it “mouse-world”) that obeys different dynamics (and for many diseases a good mouse model doesn’t even exist), and then attempt to transfer this policy to humans. The benefit of mouse-world is that you can crash the cars as often as you want; the downside is that you’re learning dynamics in mouse-world, [which don’t transfer](https://www.gwern.net/Replication#animal-models) well to humans.

Yet even if we were unconstrained by ethics and regulation, and therefore able to experiment on humans, we would still be limited by speed and the difficulty of isolating the effects of our experiments. Mice and other model systems are simply quicker and easier to experiment on.

This is the defining tradeoff of model systems in biomedicine: external validity (i.e., how well the results generalize to humans) necessarily comes at the expense of experimental throughput (i.e., how many experiments one can run in a given period of time, which is determined by some combination of ethical, regulatory, and physio-temporal constraints), and vice versa. 

Thus, model systems lie along a Pareto frontier of throughput vs. external validity.

One experiment on a human undoubtedly contains more information about human biomedical dynamics than one experiment on a mouse. However, the question is _how much_ more—is a marginal human experiment equivalent to 10 marginal mouse experiments, or 1000?

By creating a framework to understand this tradeoff, we will discover that the quality of our model systems directly upper-bounds the rate of biomedical progress.


### Scaling Laws for Transfer

The scaling laws framework offers a language for answering such questions. To make data from different model systems commensurable, we must introduce the idea of [scaling laws for transfer](https://arxiv.org/pdf/2102.01293.pdf); these scaling laws quantify how effectively a neural network trained one one data distribution can “port” its knowledge (as encoded in the neural network’s weights) to a new data distribution.

For instance, [one could](https://arxiv.org/pdf/2102.01293.pdf) pre-train a neural network on English language data and “transfer” this knowledge to the domain of code by fine-tuning the model on Python. Or [one could](https://christina.kim/2021/04/11/scaling-laws-for-language-transfer-learning/) pre-train on English and then transfer to Chinese, Spanish, or German language data. Or [one could](https://arxiv.org/pdf/2010.14701.pdf#page=3) pre-train on images and transfer to text (or vice versa). 

The usefulness of this pre-training is quantified as the “effective data transferred” from source domain A to target domain B, which captures how much pre-training on data from domain A is “worth” in terms of data from domain B—in effect, a kind of data conversion ratio. It is [defined as](https://christina.kim/2021/04/11/scaling-laws-for-language-transfer-learning/) “the amount of additional fine-tuning data that a model of the same size, trained on only that fine-tuning dataset, would have needed to achieve the same loss as a pre-trained model,” and is quantified with a transfer coefficient, $$ \alpha_{T} $$, that measures the directed similarity (which, like KL divergence, isn’t symmetric) between the two data distributions. We can think of this transfer coefficient as a measure of the external validity from domain A onto domain B.<input type="checkbox" id="cb29" /><label for="cb29"><sup></sup></label><span><br><br>This is a big simplification. We’re assuming we’re in the non-compute-constrained regime, which allows us to ignore the effects of scaling model size (which has its own transfer coefficient) and focus solely on dataset size; this is a reasonable assumption for biomedicine, which is currently far more data-limited than compute-limited.<br><br></span>


![](../assets/scaling_laws_transfer.PNG)


The analogy to biomedicine is quite clear: we pretrain our dynamics model on a corpus of data written in the “mouse” language or “in vitro human cell model” language, and then we attempt to transfer this general knowledge of language dynamics by fine-tuning the model on data from the “human” language domain. The effective data transferred from these model systems is equal to how big a boost pre-training on them gives our human dynamics model, in terms of human-data equivalents. 

However, in biomedicine, we often don’t have much human data to fine-tune on. We can easily collect large pre-training datasets from non-human model systems like mice and in vitro models, but human data, especially experimental data, is comparatively scarce. This puts us in the “low-data regime”, where our total effective data, $$ D_E $$, reduces to whatever effective data we can transfer from the source domain, $$ D_T $$ (e.g., mouse or in vitro models):

> Pre-training effectively multiplies the fine-tuning dataset, $$ D_F$$ , in the low-data regime. In the low data regime the effective data from transfer is much greater than the amount of data fine-tuned on, $$ D_T \gg D_F $$. As a result, the total effective data, $$ D_E = D_F + D_T \approx D_T $$.

Therefore, we must effectively zero-shot transfer our pre-trained model to the human domain with minimal fine-tuning—meaning our total effective data _is_ whatever we can squeeze out of pre-training on non-human data. That is, the majority of our model’s dynamics knowledge must come from the non-human domain.

The human dynamics model’s loss [scales as a](https://arxiv.org/pdf/2102.01293.pdf#page=10) power-law function of the amount of non-human data we transfer to it, but where the exponent is the product of the original human-data scaling exponent, $$ \alpha_{D} $$, and the transfer coefficient exponent between the domains, $$ \alpha_{T} $$. That is, training on non-human data reduces the original human-data scaling law by a factor $$ 1/\alpha_{T} $$, which can be visualized as the slope being reduced by this factor on a log-log plot. For instance, if the mouse to human transfer coefficient is 0.5, then the reduction in loss from a 1000x increase in human data is equivalent to the reduction in loss from a ~1,000,000x (divided by some constant) increase in mouse data.<input type="checkbox" id="cb30" /><label for="cb30"><sup></sup></label><span><br><br>For instance, suppose the transfer coefficient from mice to humans is 0.66. Because we’re dealing with exponents, this means that to achieve the same loss training on mice as you would training on humans, you don’t need 1.5x (1/0.66) the data, nor do you need 1.5 more orders of magnitude of data—you actually need to multiply the orders of magnitude <i>by 1.5</i>. That is, if 1 million ($$10^6$$) human tokens produces a loss of 0.25, you’d need 1 <i>billion</i> ($$10^{6*1.5}$$) mouse tokens (divided by some constant) to reach an equivalent loss.<br><br>Some might view this as the reductio ad absurdum of the scaling hypothesis for biomedical dynamics. (Though it’s quite possible I’m misconstruing how the math of scaling laws for transfer works, in which case I hope to be corrected.)<br><br></span> 

This has a startling implication: under this model, small decreases in the transfer coefficient of a model system require exponential increases in dataset size to offset them.

Jack Scannell, one of the coiners of the term “Eroom’s law”, found something consistent with this [in his paper](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0147215) on the role of model systems in declining returns to pharmaceutical R&D. The paper presents a decision theoretic analysis of drug discovery, in which each stage of the pipeline involves culling the pool of drug candidates using some instrument, like a model system; the pipeline can be thought of as a series of increasingly fine filters that aim to let true positives (i.e., drugs that will have the desired clinical effect in humans) through, while selecting out the true negatives. Scannell finds that small changes in the validity of these instruments can have large effects on downstream success rates:

> We find that when searching for rare positives (e.g., candidates that will successfully complete clinical development), changes in the predictive validity of screening and disease models that many people working in drug discovery would regard as small and/or unknowable (i.e., an 0.1 absolute change in the correlation coefficient between model output and clinical outcomes in man) can offset large (e.g., 10-fold, even 100-fold) changes in models’ brute-force efficiency…[and] large gains in scientific knowledge. 

Therefore, in both the dynamics transfer and drug pipeline context, model external validity is critical. (Yes, Scannell’s model is extremely simple, and it’s debatable if the scaling laws for transfer model applies in the manner described—at worst, the math doesn’t apply exactly but the general point about external validity still holds.)

Add to this the fact that there’s likely an upper bound on how much dynamics knowledge can be transferred between model systems and humans—mice and humans are separated by [80 million years](https://www.genome.gov/10001345/importance-of-mouse-genome) of evolution, after all—and it seems to suggest that running thousands, or even millions, of experiments on our current model systems won’t translate into a useful human biomedical dynamics model.


### bioFLOP Benchmark

But we can put a finer point on our pessimism. I will claim that the rate of improvement in our biomedical dynamics model, and therefore the rate of biomedical progress, is directly upper-bounded by the amount of external validity-adjusted “biocomputation” capacity we have access to.

By “biocomputation”, I [do not mean](https://en.wikipedia.org/wiki/Biological_computing) genetically engineering cells to [compute X-OR gates using RNA](https://www.nature.com/articles/s41467-018-07181-2). Rather, I mean biologically native computation, the information processing any biological system does. When one runs an experiment on ($$ S \times A → S’ $$) or passively observes the dynamics of ($$ S → S’ $$) a biological system, the data one collects are a product of this system’s biocomputation. In other words, biological computation emits information.<input type="checkbox" id="cb31" /><label for="cb31"><sup></sup></label><span><br><br>The software-hardware distinction fails us in the case of biocomputation. There is no static “hardware” upon which the “software” runs; the “program” the biological system is running cannot be distinguished from its physical instantiation—the biocomputer _is_ the program. (This isn’t to say that biological programs aren’t [multiply realizable](https://en.wikipedia.org/wiki/Multiple_realizability). In theory, it’s possible to run the same function on different biological substrates, or even in silico.)<br><br></span>

All model systems are therefore a kind of “biocomputer”, and their transfer coefficients represent a mutual information measure between the biocomputation they run and human biocomputation. The higher this transfer coefficient, the more information you can port from this biocomputer to humans. By combining transfer coefficients and measures of experimental throughput, we can develop a unified metric for comparing the biocomputational capacity of different model systems.<input type="checkbox" id="cb32" /><label for="cb32"><sup></sup></label><span><br><br>This idea of transfer generalizes to all biological systems. It applies to transferring dynamics knowledge not just across different species, but across human populations (for instance, the transfer coefficient between any two humans is likely some function of their genetic distance). And it applies across different levels of biological complexity: for instance, one could train a dynamics model on in vitro single-cell behavior, and then transfer this to in vitro multi-cellular systems—the efficiency of this transfer depends on how composable vs. emergent multi-cellular behavior is with respect to single-cell behavior. It probably even applies across tissues within a single organism: the transfer coefficient between a cardiomyocyte and a kidney epithelial cell from the same person is probably high, given that they share the same genome, but it’s not equal to 1.<br><br></span>

Let’s arbitrarily define the informational value (which you can think of in terms of reduction in human dynamics model loss) of one marginal experiment on a human as 1 human-equivalent bioFLOP. This will act as our base. The informational value of one marginal experiment on any model system is worth some fraction of this human-equivalent bioFLOP, and is a function of the model system’s transfer coefficient to humans.
 

Therefore, the human-equivalent bioFLOPS (that is, the biocomputational capacity per unit time) of a model system is the product of its experimental throughput (how many experiments you can run on it per unit time) and its biocomputational power (as measured in fractions of a human-equivalent bioFLOP per experiment—i.e., how much human-relevant information a single experiment on it returns).<input type="checkbox" id="cb33" /><label for="cb33"><sup></sup></label><span><br><br>Yes, we’d need to add modifiers for the richness of the state readout (do you observe coarse-grained phenotypic information, like brightfield imaging, or incredibly fine-grained information, like the transcriptional state of every cell in the model system) and whether the bioFLOP is experimental or observational; we’d also need to expand on our definition of model system transfer coefficients (genetic similarity and biocomputational complexity seem like two separate dimensions of external validity—which is worth more as a model of human cancer: a single [xenografted mouse](https://en.wikipedia.org/wiki/Patient_derived_xenograft), or one hundred instances of a human cancer cell line grown in vitro?).<br><br></span>

With this framework in place, we can compute the total human-equivalent biocomputational capacity available, given a set of model systems, their transfer coefficients, and their experimental throughputs. This, in theory, would tell us how many experiments we’d need to run on these model systems, and how long it would take, to achieve some level of dynamics model performance on a biomedical task. 

If we were to run this calculation on our current model systems, we’d come to the sobering conclusion that our biocomputation capacity is incredibly limited compared to the complexity of the target biological systems we’re attempting to model. We’re bioFLOP bottlenecked.<input type="checkbox" id="cb34" /><label for="cb34"><sup></sup></label><span><br><br>Perhaps we can even retrospectively explain Eroom’s law as a decline in total bioFLOPS clinical researchers had access to. Before the [standardization and regulation of](https://press.princeton.edu/books/paperback/9780691141800/reputation-and-power) the clinical development process, which began to gain steam in the late 50’s, clinical researchers were given far more license in testing on humans. This undoubtedly led to [human rights abuses](https://theconversation.com/looking-back-on-the-chequered-past-of-drug-trials-14883), death, and irreproducible quackery, but it also meant researchers learned an immense amount about human physiology. Just consider the abstract of [this 1960 NEJM article](https://www.nejm.org/doi/full/10.1056/NEJM196010132631502) on tranquilizer poisoning:<br><br><i>“As new drugs are developed, their accidental over-ingestion will occur, and, although toxicity studies on laboratory animals precede general distribution of drugs, human data usually become available only after distribution. Knowledge concerning the potential toxicity of psychopharmacologic agents is accumulating as they continue to be used. The information on the acute toxicity of these drugs in human beings presented below is based on 280 cases of accidental ingestion and poisoning involving "tranquilizer" agents…"</i><br><br></span>

To make biocomputational limits more intuitive, and to understand why we must increase biocomputation to accelerate biomedical progress, let’s work our way through an analogy to game-playing agents.

#### Biocomputation Training Analogy

Suppose you’re trying to train a MuZero-like agent to do some task in the real world. To solve the task, the agent must build up a latent dynamics model of it. The catch is you’re only able to train the agent in a simulator.  

You’re given three simulator options. Each runs on a purpose-built chip, specifically designed to run that simulator.

Simulator A is extremely high-fidelity, and accurately recapitulates the core features of the real-world environment the agent will be testing in. The downside is that this simulator operates extremely slowly and the chips to run it are incredibly expensive. 

Simulator B is also high-fidelity, but the agent trains in a different environment from the one it will be testing in, which uses a different physics engine. The upside is that this simulator is relatively quick and the chips to run it are cheap and abundant.

Simulator C is a low-fidelity version of Simulator A. In principle, it operates on the same physics engine, but in practice the chip doesn’t have the computational power to fully simulate the environment, and therefore only captures limited features of it. However, the chips are incredibly cheap (though they have a piddling amount of compute power) and they are fast (for the limited amount of computation they do).

During training, the state output of the simulator is rendered on a monitor and displayed to the agent. (This rendering used to be incredibly expensive, but it’s becoming much cheaper.) The agent observes the state, and chooses an action which is then fed to the simulator. The simulator then updates its state. This constitutes one environmental interaction.  

As you probably realize, none of the simulators can train an effective agent in a reasonable amount of time. In all three cases, training is bottlenecked by high-quality compute.


### Mistaken Moore’s Law

Scopes and scalpels, the two tool classes we covered in our earlier tool progress review, are, in a sense, [peripherals](https://en.wikipedia.org/wiki/Peripheral)—the monitors and mice to our computers. Let’s return to the most famous graph in genome sequencing, in which sequencing progress is compared to Moore’s law: 

![](../assets/2021_Sequencing_cost_per_Mb.jpg)


On one level, this comparison is purely quantitative: the decline in genome sequencing cost has outpaced Moore’s law. But the graph also invites a more direct analogy: sequencing will be to the biomedical revolution as semiconductors were to the information technology revolution. 

This comparison is wrong and ironic, because despite our peripherals improving exponentially, most human-relevant biocomputation is still done on the biological equivalent of [vacuum tubes](https://en.wikipedia.org/wiki/Vacuum_tube). (No, running them [in “the cloud”](https://www.nature.com/articles/d41586-022-01618-x) won’t increase their compute capacity.) Through an ill-formed analogy, many have mistaken the biological equivalents of oscilloscopes, screen pixel density, and soldering irons as the drivers of biomedical progress. Much misplaced biomedical optimism rests on this error.

Peripherals certainly matter—it would have been hard to build better [microchips](https://en.wikipedia.org/wiki/Integrated_circuit) if we couldn’t read or perturb their state—but they alone do not drive a biomedical revolution. For that, we need advances in compute.<input type="checkbox" id="cb35" /><label for="cb35"><sup></sup></label><span><br><br>Yes, thirty years ago, the state of the art in biomedical peripherals was looking at biocomputers with the naked-eye and poking them with a stick. At that time, advances in peripherals were clearly the bottleneck. But we quickly hit diminishing returns to our ability to read and write state to biocomputers. The bottleneck now lies with the biocomputers themselves.<br><br></span>      

The only way to increase compute capacity in biomedicine is to push the biocomputer Pareto frontier along the external validity or throughput dimensions. However, the exponential returns to improved external validity far outweigh any linear returns we could achieve by increasing throughput. Therefore, to meaningfully increase biocompute, we must build model systems with higher external validity. Scopes and scalpels will drive the Moore’s law of biomedicine only insofar as they help us in this task, which is the subject of the third and final tool class: simulacra. 


### Growing Better Biocomputers

> What I cannot create, I do not understand. — _[Richard Feynman](https://digital.archives.caltech.edu/islandora/object/image%3A2545)_

Our best hope for increasing human-equivalent bioFLOPS is to build physical, ex vivo models of human physiology, which we’ll call “bio-simulacra” (or “simulacra”, for short), using [induced pluripotent stem cells](https://en.wikipedia.org/wiki/Induced_pluripotent_stem_cell). Simulacra are the subset of model systems that aren’t complete organisms, but instead act as stand-ins for them (or parts of them). The hope is that they can substitute for the human subjects we’d otherwise like to experiment on.

For instance, in vitro cell culture is an extremely simple type of simulacrum. However, it’s like the biocomputer for running Simulator C in the metaphor above: it has too little compute to accurately mirror the complexity of complete human physiology. But simulacra could become vastly more realistic, eventually approaching the scale and complexity of human tissues, or even whole organs, thereby increasing their compute power.

Simulacra have been researched for decades under many names (“microphysiological systems”, “organ-on-a-chip”, “organoids”, “in vitro models”, etc.), and [dozens of companies](https://j-organoid.org/upload/pdf/organoid-2021-1-e11.pdf) have [attempted to](https://emulatebio.com/announcing-moxi/) commercialize them.

Though there [have been great advances](https://www.nature.com/articles/s43586-022-00118-6) in the underlying technology—microfluidics, sensors, induced pluripotent stem cells—the resulting simulacra are still disappointingly physiologically dissimilar to the tissues they are meant to model. This can be seen visually: most simulacra are small—because they lack vascularization, which limits the diffusion of nutrients and oxygen—and (quite literally) disorganized.<input type="checkbox" id="cb36" /><label for="cb36"><sup></sup></label><span><br><br>If one wanted to index how simulacra have advanced over time, a good metric would be their developmental maturity, as measured by their transcriptional similarity to the in vivo counterparts they’re attempting to mimic. This metric provides a good approximation of the full physiological similarity between a simulacrum and its in vivo counterpart (which we’d otherwise have to measure on a tissue-by-tissue basis using particular visual, metabolomic, genetic, etc. markers, thereby making simulacra incommensurable in terms of their fidelity to in vivo physiology), which is a useful proxy for the simulacrum’s external validity.<br><br></span>

Much of this slow progress can be attributed to not accurately reconstructing the in vivo milieu of the imitated tissues (i.e., those we wish to build ex vivo). There are many low-hanging fruit here that are [beginning to be](https://www.nature.com/collections/cgdegjaiaj) picked: improving [nutritional composition](https://www.nature.com/articles/s41551-022-00884-4) of cell culture media, [finding sources](https://www.nature.com/articles/s42003-021-02910-8) of extracellular matrix proteins other than [cancer cells](https://en.wikipedia.org/wiki/Matrigel), adding [biomechanical](https://www.quantamagazine.org/embryo-cells-set-patterns-for-growth-by-pushing-and-pulling-20220712/) and [electrical stimulation](https://www.nature.com/articles/s41551-022-00885-3), etc.

All these advances are directionally correct but insufficient. If we hope to grow larger, more realistic simulacra with higher external validity, placing a few cell types in a [sandwich-shaped plastic chip](https://emulatebio.com/) won’t cut it. Useful simulacra amount to real human tissues; therefore, they must be grown like real human tissues. 

Luckily, nature has given us a blueprint for how to do this: [human development](https://en.wikipedia.org/wiki/Developmental_biology). The task of growing realistic simulacra therefore reduces to the task of reverse-engineering the core elements of human development, ex vivo. That is, we must learn to mimic the physiological cues a particular tissue or organ would experience during development in order to grow it. Through this, we will grow simulacra that better represent adult human physiology, thereby increasing these models’ external validity.

Our rate of progress on this task is the main determinant of the rate of biocomputational, and therefore biomedical, progress over the next many decades. To solve the broader, more difficult problem of biomedical control, we must first solve this narrower, more tractable problem of controlling development.<input type="checkbox" id="cb37" /><label for="cb37"><sup></sup></label><span><br><br>More speculatively, it’s possible that one can’t learn (in a data-efficient manner) a dynamics model of adult human physiology, particularly in states of disease, without first learning a dynamics model of the process that generated that physiology (both [ontogeny and phylogeny](https://en.wikipedia.org/wiki/Evolutionary_developmental_biology)).<br><br></span> 

Here’s the interesting thing: reverse-engineering development can be framed as a biomedical control task and therefore is amenable to the scaling laws approach. In effect, the challenge is to use physiological cues to guide multicellular systems into growing toward the desired stable “social” configurations. This is an extremely challenging representation learning and reinforcement learning problem (one might even call it a multi-agent reinforcement learning problem).<input type="checkbox" id="cb38" /><label for="cb38"><sup></sup></label><span><br><br>Much more could be said here. Discovering how to operationalize the scaling laws reframing of the developmental control problem is left as an exercise for the reader. Hint: biological entities (cells, tissues, organs, etc.) can [be thought of](https://www.sciencedirect.com/science/article/abs/pii/S1571064519300909) as [wrapped in](https://www.sciencedirect.com/science/article/pii/S0022519319304588) hierarchical [Markov blankets](https://en.wikipedia.org/wiki/Markov_blanket). This information-processing perspective is complementary to the [social agents](https://www.biorxiv.org/content/10.1101/2022.05.16.492018v1) [perspective](https://twitter.com/DJCohenEtAl/status/1548001454127845378), which is particularly appropriate for development:<br><br><i>"We find that graded Nodal signaling, in addition to its highly conserved role in mesendoderm patterning, mechanically subdivides the tissue into a small fraction of highly protrusive leader cells able to locally unjam and thus autonomously internalize, and less protrusive followers, which remain jammed and need to be pulled inwards by the leaders…we further show that this binary mechanical switch, when combined with Nodal-dependent preferential adhesion coupling leaders to followers, is critical for triggering collective and orderly mesendoderm internalization, thus preserving tissue patterning. This provides a simple, yet quantitative, theoretical framework for how a morphogen-encoded (un)jamming transition can bidirectionally couple tissue mechanics with patterning during complex three-dimensional morphogenesis."</i><br><br></span>

## 6.The Future of Biomedical Research

We have established that biomedical dynamics can be approximated through large neural networks trained on lots of data; the predictive performance of these models is a power-law function of these data; and how much these data improve predictive performance depends on the external validity of the biocomputational system they were generated by.

However, a question remains: how do we select these data? (And is power-law scaling the best we can do?)

Unlike large language models, whose training data is a passive corpus that the model does not (yet) have an active role in generating, in biomedicine we must [actively generate data](https://en.wikipedia.org/wiki/Active_learning_(machine_learning)) through observation and experimentation. This experimental loop is the defining feature of biomedical research. 

This experimental loop is directed by biomedical research agents—currently, groups of human beings. However, in the long-run, this loop will increasingly rely on, and eventually be completely directed by, AI agents. That is, in silico compute will be fully directing the use of biocompute.

Let’s first discuss experimental efficiency. Then we’ll discuss what the handoff from humans to AI agents might look like in the near-term, and what completely AI-directed biomedical research might look like in the long-term.


### Active Learning and Experimental Efficiency 

Good news: the power-law data scaling we reviewed before is the worst-case scenario, in which data is selected at random. Through data selection techniques, [we can achieve](https://arxiv.org/pdf/2206.14486.pdf) superior scaling behavior.<input type="checkbox" id="cb39" /><label for="cb39"><sup></sup></label><span><br><br>The paper linked above looks at data pruning, a different type of data selection technique than active learning, but the principle is the same.<br><br><i>"Active learning iterates between training a model and selecting new inputs to be labeled. In contrast, we focus on data pruning: one-shot selection of a data subset sufficient to train to high accuracy from scratch."</i><br><br></span>

In the case of biomedical experimentation (e.g., in the therapeutics development context), the data selection regime we find ourselves in is active learning: at every time point, we select an experiment to run and query a biocomputer oracle (i.e., physically run the experiment) to generate the data.

The quality of this experimental selection determines how efficiently biocompute capacity is translated, via the experimental loop, into dynamics modeling improvements (and, ultimately, biomedical control). That is, there are many questions one could ask the biocomputer oracle, each of which emits different information about dynamics; the task is to properly sequence this series of questions.

However, biomedical dynamics are incredibly complex, so efficient experimental selection requires planning, especially when multiple types of experiment are possible. Thus, experimental selection [amounts to](https://arxiv.org/pdf/1708.02383.pdf) a kind of reinforcement learning task. 

Currently, this reinforcement learning task is being tackled by decentralized groups of humans. In the near-future, AI agents will play a greater role in it.

### Centaur Research Agents

At first, AI agents will be unable to efficiently run the experimental loop themselves. Therefore, in the [translational](https://en.wikipedia.org/wiki/Translational_research) research context, we’ll first see “[centaurs](https://en.wikipedia.org/wiki/Advanced_chess)”—human agents augmented with AI tools.

Initially, in the centaur setup, the AI’s main role will be as a dynamics model, which the human will query as an aid to experimental planning and selection. (Up to this point in the essay, this is the only role we’ve discussed machine learning models playing.) For instance, the human could have the AI run in silico rollouts of possible experiments, in order to select the one that maximizes predicted information gain over some time horizon (as evaluated by the human). In this scenario, the human is still firmly in the driver’s seat, determining the value of and selecting experiments—the machine is in the loop, but not directing it.

However, as the AI improves, it will begin to take on more responsibility. For instance, as it develops better multimodal understanding of its internal dynamics model, the AI will help the human analyze and reason through the dynamics underlying the predicted rollouts, via natural language interaction. Humans will become more reliant on the AI’s analysis.

Eventually, because it can reason over far larger dynamics rollouts and has an encyclopedic knowledge of biomedical dynamics to draw on, the AI will develop a measure of predicted experimental information gain (in effect, a kind of experimental “value function”) superior to human evaluation. Not soon after, by training offline on the dataset of human-directed research trajectories it has collected, the AI will develop an experimental selection policy superior to that of humans.

At some point, the AI will begin autonomously running the entire experimental loop for circumscribed, short-horizon tasks. The human will still be dictating the task-space the AI agent operates in, its goals, and the tools at its disposal, but with time, the AI will be given increasing experimental freedom.

The direction this all heads in, obviously, is end-to-end control of the experimental loop by AI agents.


### Toward End-to-End Biomedical Research

The behavior of end-to-end AI agents might surprise us.

For instance, suppose the human tasks the AI with finding a drug that most effectively moves a disease simulacrum of a person with genotype G from state A (a disease state) to state B (a state of health). The AI is given a biocompute budget and an experimental repertoire to solve this task. 

There are many ways the AI could approach this problem.

For instance, the AI might find it most resource-efficient to first do high-throughput experimental screening of a set of drug candidates (which it selects through in silico rollouts) on very simple in vitro models, and then select a promising subset of these candidates for experimentation in the more complex, target disease simulacra. Then it repeats this loop.

But the agent’s experimental loop could become much more sophisticated, even nested. For instance, the agent might first do in silico rollouts to formulate a set of “hypotheses” about the control dynamics of the area of state space the disease simulacrum lives in. Then it (in silico) spatially decomposes the target simulacrum into a set of multicellular sub-populations, and restricts its focus to the sub-population which is predicted to have the largest effect on the dynamics of the entire simulacrum. It then creates in vitro models of this sub-population, and runs targeted, fine-grained perturbation experiments on them (perhaps selected based on genetic disease association signatures it picked up on in the literature). It analyzes the experimental results, and then revises its model of the simulacrum’s control dynamics, restarting this sub-loop. After it has run this sub-loop enough to sufficiently increase its confidence in its dynamics model, it tests the first set of drug candidates on actual instances of the disease simulacrum.<input type="checkbox" id="cb40" /><label for="cb40"><sup></sup></label><span><br><br>One misconception is the idea that an AI agent wouldn’t use the experimental tools of mechanistic biomedical research—genetic and epigenetic editing, transcription factor overexpression, and other perturbations. No, the agent can in principle use these, but it will learn to deploy them end-to-end, wielding them not toward the end of understanding but toward the end of control.<br><br></span>(Obviously none of this planning is explicit. It takes place in the weights of the neural networks running the policy and dynamics models.)

As the agent becomes more advanced and biomedical tasks become longer-horizon and more open-ended, these experimental loops will become increasingly foreign to us. Even if we peer inside the weights, we likely won’t be able to express the experimental policy in human-language.

This will become even truer as the agent begins to self-scaffold higher-order conceptual tools in order to complete its tasks. For instance, given an extremely long-horizon task, like solving a disease, the agent might discover the concept of “technological bottlenecks”, and begin to proactively seek out bottlenecks (like that of biocompute, and those we can’t yet foresee) and work toward alleviating them. To solve these bottlenecks, the agent will construct and execute against [technology trees](https://en.wikipedia.org/wiki/Technology_tree), another concept it might develop.

Yet to traverse these technology trees, the agent must build new experimental tools, just as humans do. This might even involve discovering and establishing completely new technologies. 

Consider the simulacra we discussed earlier; they are but one type of biocomputer, optimized for fidelity to the human tissues they’re meant to mimic. However, the AI agent might discover other forms of biocomputers that more efficiently and cheaply emit the information needed to accomplish its aims, but which look nothing like existing forms of biocomputer—perhaps they are chimeric, or blend electronics (e.g., [embedded sensors](https://www.biorxiv.org/content/10.1101/2021.04.22.440941v1.full.pdf)) with living tissue. Furthermore, the agent might develop new types of scopes and scalpels for monitoring and perturbing these new biocomputers. The agent could even discover hacks, like [overclocking](https://en.wikipedia.org/wiki/Overclocking) biocomputers (by [literally increasing](https://twitter.com/youklab/status/1536134419781648384) the [temperature](https://twitter.com/LauraDeming/status/1475575388386603013)) to accelerate its experimental loop. 

At a certain point, the agent’s physical tools, not just its internal in silico tools, might be completely inscrutable to us.


### Speculating on Future Trajectories of Biomedical Progress: Or, How to Make PASTA

As data flows continue to accelerate, the human distributed scientific hive mind will hit its cognitive limits, unable to make sense of the fire-hose of biological data. Humans will begin ceding control to AI agents, which continue improving slowly but steadily. In due time, AI agents will come to dominate all of biomedical research—first therapeutics development, and eventually basic science. This will happen much quicker [than most expect](https://www.overcomingbias.com/2021/05/theories-of-unnatural-selection.html).

The AI’s principal advantage is informational: it can spend increasingly cheap in silico compute to more efficiently use limited biocompute. And in the limit, as it ingests more data about biomedical dynamics, the AI will offload _all_ biocomputation to in silico computation, thereby alleviating the ultimate scientific and technological bottleneck: time.

However, AI agents are not yet autonomously solving long-horizon biomedical tasks or bootstrapping their own tools, let alone building a near-perfect biological simulator. We are still bottlenecked by biocompute, so there’s reason to be pessimistic about biomedical progress in the short-term. But, conditional on advances in biocompute and continued exponential progress in scopes and scalpels, the medium-term biomedical outlook is more promising. In the long-run, all bets are off. 

> The most merciful thing in the world, I think, is the inability of the human mind to correlate all its contents. We live on a placid island of ignorance in the midst of black seas of infinity, and it was not meant that we should voyage far. The sciences, each straining in its own direction, have hitherto harmed us little; but some day the piecing together of dissociated knowledge will open up such terrifying vistas of reality, and of our frightful position therein, that we shall either go mad from the revelation or flee from the light into the peace and safety of a new dark age. — _H.P. Lovecraft_, [The Call of Cthulhu](https://en.wikipedia.org/wiki/The_Call_of_Cthulhu)

