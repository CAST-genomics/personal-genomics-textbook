# 2.2 Next-generation sequencing

SNP arrays are convenient to perform relatively cheap genotyping of a large number of samples. However, they are limited in that they can only assess a set of pre-determined polymorphic sites. Further, due to historical biases these chips tend to contain SNPs that are most polymorphic in European samples but might be less relevant to individuals with other ancestries.

An alternative is to actually *sequence* someone's genome. That is, we can read the code of the entire genome, and not just a subset. While multiple sequencing technologies exist, the major current technology are from Illumina's next-generation sequencing (NGS) machines.

Sequencing technologies are limited in our ability to read very long stretches of DNA at once. We cannot just take an entire chromosome and read it start to finish. Instead, we sequence short fragments, which we refer to as *reads*. NGS technology typically outputs billions of short reads of 150bp or so. Newer long-read technologies (see below) are capable of generating much longer sequences, but with some tradeoffs in error rates.

We just briefly outline the NGS workflow here. See CSE185 or past offerings of this course for more details.

![NGS workflow](NGS.png)
Source: [Illumina](https://www.illumina.com/content/dam/illumina-marketing/documents/products/illumina_sequencing_introduction.pdf)

1. Genomic DNA is isolated from a sample, e.g. from a blood sample or from human cell lines. Note, this results in DNA from many (millions) cells, so we are starting with many many copies of a person's genome.
2. The DNA is fragmented into small fragments of several hundred base pairs. This is because NGS technology cannot sequence very large pieces of DNA in one go.
3. Special adapter sequences are added to these fragments to enable them to be read by the sequencer.
4. Sequences are loaded onto the sequencing machine. They attach to a *flowcell*, where each original fragment is copied many times to increase the amount of DNA available for sequencing. 
5. The sequencer then uses a process of *sequencing by synthesis* to determine the sequence of each DNA fragment. Briefly, the sequencer is loaded with many nucleotides. Each base (A, C, G, or T), is fluorescently labeled with a different color. One base is added to each fragment at a time. After each base is added, the sequencer takes a picture of the flowcell. The color of the fluorescent label indicates which base was added.

For a more detailed view of Illumina NGS technology, take a look at this video: https://www.youtube.com/watch?v=fCd6B5HRaZ8.

This process generates billions of short reads. The reads are highly accurate, with error rates typically less than 1%. These reads can then be used to perform genotyping of SNPs and other complex variants. A typical workflow includes: (1) aligning the short reads to a reference genome sequence and (2) analysis of the bases aligned to each position to identify variable sites.

While we will mostly focus on SNPS in this course, NGS data can be used to genotyping much more complex types of genetic variation, including repeats, copy number variants, and large insertions and deletions.
