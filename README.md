# CRISPR-Cas9 Computational Design for Allele-Specific Silencing in Huntington's Disease

## 🔬 Project Overview
This project focuses on the bioinformatic design and optimization of single-guide RNAs (sgRNAs) targeting the human Huntingtin ($HTT$) gene. The goal is to isolate high-efficiency target sites within the early coding region of the transcript to disrupt the expression of the neurotoxic mutant huntingtin protein responsible for Huntington's Disease.

---

## 🧬 Target Architecture & Methodology
- **Reference Transcript:** Human $HTT$ mRNA reference sequence (**NCBI RefSeq: NM_002111**) spanning 13,498 base pairs (bp).
- **Target Coordinate:** The pathogenic trinucleotide repeat region (**CAG repeat expansion**) is located at the 5' end of the transcript, beginning at **coding nucleotide coordinate 52** within **Exon 1**.
- **Structural Overlap:** Bioinformatic mapping confirms that the 5' boundary of the **Coding Sequence (HTT CDS)** for huntingtin isoform 2 aligns precisely with **Exon 1**, ensuring that targeted edits will directly disrupt the translated reading frame.

### Visual Map of the HTT Transcript Locus:
![HTT Gene Linear Map](https://github.com/rimshatalib/CRISPR-Huntingtons-Project/blob/main/linear_map.png?raw=true)

---

## 🛠️ CRISPR Parameters & Computational Design
The guide RNA library was generated using cloud-based molecular biology software against the human genome assembly template (**GRCh38 / Homo sapiens**).

- **Nuclease Platform:** SpCas9
- **Protospacer Adjacent Motif (PAM):** 5'-NGG-3'
- **Spacer Length:** 20 nucleotides
- **Scanning Window:** Nucleotides 50 to 100 (encompassing the pathogenic CAG initiation boundary)

---

## 📊 Leading sgRNA Candidate Results

The algorithmic scan evaluated candidates based on thermodynamic efficiency (On-Target Score) and genomic safety/specificity (Off-Target Score). 

| Lead Candidate Address | Strand | Spacer Sequence (5' -> 3') | PAM | On-Target Score | Off-Target Score |
| :--- | :---: | :--- | :---: | :---: | :---: |
| **Cut Position 69** | (-) | `CAGCACCGGGGCAATGAATG` | GGG | **60.0** | **70.9** |

### Selection Rationale:
The sgRNA targeting **Cut Position 69** was selected as the lead therapeutic candidate. It demonstrates an optimal balance between cellular cleavage efficiency (**On-Target: 60.0**) and genome-wide safety (**Off-Target: 70.9**). This high specificity minimizes the risk of off-target double-strand breaks across other polymorphic areas of the human genome while precisely targeting the upstream exon 1 boundary.

---

## 🚀 Future Horizons & Wet-Lab Translation
1. **Plasmid Construction:** Clone the selected spacer sequence into a dual-expression vector (e.g., pX459) containing both the sgRNA scaffold and human-codon-optimized Cas9.
2. **In Vitro Validation:** Transfect patient-derived Huntington's Disease fibroblast or induced pluripotent stem cell (iPSC) lines.
3. **Cleavage Assay:** Assess genomic editing efficiency at the target locus using a T7 Endonuclease I (T7E1) assay or Next-Generation Sequencing (NGS).
