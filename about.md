---
layout: page
title: "About"
group: navigation
---

{% include JB/setup %}

__kallisto__ is a program for quantifying abundances of transcripts from bulk and single-cell RNA-Seq data, or more generally of target sequences using high-throughput sequencing reads. It is based on the novel idea of _pseudoalignment_ for rapidly determining the compatibility of reads with targets, without the need
for alignment. On benchmarks with standard RNA-Seq data, __kallisto__ can
    quantify 30 million human reads in less than 3  minutes on a Mac desktop
    computer using only the read sequences and a transcriptome index that
    itself takes less than 10 minutes to build. Pseudoalignment of reads
    preserves the key information needed for quantification, and __kallisto__
    is therefore not only fast, but also as accurate as existing
    quantification tools. In fact, because the pseudoalignment procedure is
    robust to errors in the reads, in many benchmarks __kallisto__
    significantly outperforms existing tools. __kallisto__ is described in detail in:

Nicolas L Bray, Harold Pimentel, Páll Melsted and Lior Pachter, [Near-optimal probabilistic RNA-seq quantification](http://www.nature.com/nbt/journal/v34/n5/full/nbt.3519.html), Nature Biotechnology __34__, 525--527 (2016), doi:10.1038/nbt.3519

To use __kallisto__ [download the software](download.html) and visit the
[Getting started](starting.html) page for a quick tutorial. More information about kallisto, including a demonstration of its use, is available in the materials from the [first kallisto-sleuth workshop](https://pachterlab.github.io/kallisto-sleuth-workshop-2016/). Numerous [notebooks](https://github.com/BUStools/bustools-notebooks) provide walk-throughs demonstrating the use of kallisto for single-cell RNA-Seq processing.

### FAQ

- I'm having trouble with __kallisto__. Can I get help?
  - Yes. If you think you have discovered a bug that needs to be fixed please
    file a report on the GitHub page. If you have a question about installing
    or running the program please ask on the [kallisto-and-applications Google user
    group](https://groups.google.com/forum/#!forum/kallisto-and-applications).

- Where can I get announcements about new releases?
  - You can get announcements via the [kallisto-sleuth-announcements Google
    group](https://groups.google.com/forum/#!forum/kallisto-sleuth-announcements).
    This is a read-only, low traffic mailing list that only sends an email when
    a major version is released.

- __kallisto__ is fast but is it as accurate as other quantification tools?
  - Yes. The source of  __kallisto__'s speed is the novel concept of
    _pseudoalignment_ of reads. Pseudosalignment is all that is needed for
    accurate quantification, and in tests on both real and simulated data we
    find that __kallisto__ is frequently _more_ accurate than existing methods.
    The increase in accuracy over some methods is due to the robustness of
    pseudoalignment to read base errors and indels, and the ability to perform
    many rounds of the Expectation-Maximization algorithm.

- Can __kallisto__  be used for finding differentially expressed genes in
  RNA-Seq analysis?
  - No. __kallisto__ can be used to build indices for quantification, and it
    can quantify RNA-Seq samples. It is also useful for assessing the
    reliability of abundance estimates via the bootstrap samples it produces.
    But it is not a tool for performing differential analysis. However the
    companion tool __sleuth__ is designed to for that purpose, and __sleuth__
    uses the bootstrapped samples produced by __kallisto__.

- Is __kallisto__ usable with both single-end and paired-end reads?
  - Yes.

- Does __kallisto__ require reads to be of the same length?
  - No.

- Can __kallisto__ be used to quantify single-cell RNA-Seq data?
  - Yes.

- I've already mapped all my reads. Can I use those mappings with __kallisto__?
  - No. The mappings are not relevant and not needed for __kallisto__.


- Are you distributing pre-built indices?
  - Yes. Pre-built indices constructed from [Ensembl reference transcriptomes](https://uswest.ensembl.org/info/data/ftp/index.html) can be download from the [kallisto transcriptome indices](https://github.com/pachterlab/kallisto-transcriptome-indices/releases) site. Building indices with __kallisto index__ will often be faster in practice than downloading index files. For example, the __kallisto__ index for the human transcriptome takes between 5--10 minutes to build on a standard desktop or laptop. Transcriptome fasta files for model organisms can be downloaded from the [Ensembl database](https://www.ensembl.org/info/data/ftp/index.html). We recommend using cDNA fasta, specifically the *.cdna.all.fa.gz files. __kallisto__ can build indices directly from gzipped files.

- My RNA-Seq was prepared with a stranded library. Is there a special option I need to use with kallisto?
  - Yes, you can specify the strandedness.

- Is there a reason you picked the name kallisto for your program?
  - Yes.
