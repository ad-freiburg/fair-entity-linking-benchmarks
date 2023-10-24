# Fair Entity Linking Benchmarks

This repository contains the entity linking benchmarks Wiki-Fair and News-Fair introduced in the EMNLP 2023 paper
["A Fair and In-Depth Evaluation of Existing End-to-End Entity Linking Systems"](https://arxiv.org/abs/2305.14937).

The benchmarks aim at providing a basis for a fairer comparison between different entity linkers. This is achieved,
e.g., by including non-named entities in the ground truth, providing alternative mentions in cases where it is
 unclear what the best ground truth annotation is and using optional mentions for entities such as datetimes and
 quantities.

The annotation guidelines that were used to annotate the benchmarks can be found at
https://github.com/ad-freiburg/entity-linking-annotation-guidelines

## Description
Wiki-Fair contains 80 random Wikipedia articles from a Wikipedia dump from 2020. News-Fair contains 40 random news
 articles from a news crawl. In each article, 3 consecutive paragraphs were manually annotated. The remainder of each
 article is left unannotated (to cover a large variety of topics with an acceptable amount of manual annotation work)
 but kept in the benchmark to provide context for entity linkers.

Unlike most entity linking benchmarks, the benchmark contains not only named entities, but also non-named entities.
 Which kinds of entities were annotated was determined by a
 [type whitelist](https://github.com/ad-freiburg/elevant/blob/master/small-data-files/whitelist_types.tsv).
 To ensure a fair comparison of different linkers, the benchmark includes alternative ground truth mentions in cases
 where it is unclear what the best ground truth annotation is. The benchmark also contains optional mentions, e.g.,
 for datetimes and quantities. Coreferences are annotated, too, but there also exists a version without coreferences.
 A comprehensive list of annotation guidelines can be found in
 [this repository](https://github.com/ad-freiburg/entity-linking-annotation-guidelines).

## Usage
The benchmarks are best used within the [ELEVANT](https://github.com/ad-freiburg/elevant) entity linking evaluation tool
 since ELEVANT automatically handles special features of these benchmarks such as alternative mentions, optional
 mentions or the evaluation of only the annotated part of the articles. The Wiki-Fair and News-Fair benchmarks are
 included per default in ELEVANT such that linking results on these benchmarks can be evaluated with ease. Please
 refer to the ELEVANT GitHub repository for simple instructions on how to work with ELEVANT.
