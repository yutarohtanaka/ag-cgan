# CG-GAN (Conditional Genomic - Generative Adversarial Network)

Term Project for Machine Learning for Functional Genomics (COMS W4762, Professor David Knowles, Spring 2022) @ Columbia University. 
Developer : Yutaro Tanaka (yutaro.tanaka [at] columbia.edu)

Aim : Develop a cGAN model that can produce artificial high-quality genomic data for specific populations that are underrepresented in genomic studies, such as African and Hispanic populations. This work has the potential to be of significant impact in that it could eventually be used to produce or supplement training data for highly specific population (eg. Hispanic with heart condition, Asian with type II diabetes) from a very small sample population, and better understanding these populations.

Inspired by : Yelmen, B., Decelle, A., Ongaro, L., Marnetto, D., Tallec, C., Montinaro, F., … Jay, F. (2021). Creating artificial human genomes using generative neural networks. PLOS Genetics, 17(2), e1009303. doi:10.1371/journal.pgen.1009303

# Descriptions for JupyterNotebooks
0. data_preparation.ipynb
Takes raw VCF data and formats it into machine processable variant and variant info data. Also obtains population tags.
Input : 1000 Genomes raw data (Chromosome X)
Output : variant_info_formatted.csv, vcf_formatted.csv
1. prepare_dataset.ipynb
Take in formatted data and merge with labels to prepare test dataset.
Input : variant_info_formatted.csv, vcf_formatted.csv
Output : test_dataset.csv
2. baseline_model.ipynb
Runs CTGAN (baseline model) on the test dataset.
Input : test_dataset.csv
Output : baseline_artificial_data.csv
3. build_own_cgan.ipynb (OUTDATED)
OUTDATED ver of CG-GAN
Input : test_dataset.csv
Output : artificial_genome_data.csv
3-1. build_own_cgan_v2.ipynb
current ver of CG-GAN using wasserstein loss
Input : test_dataset.csv
Output : artificial_genome_data.csv
3-2. postprocessing_artificial_data.ipynb
Processing the CG-GAN output aritificial data.
Input : artificial_genome_data.csv
Output : processed_artificial_genome_data.csv
4. evaluation of synthesized data
Evaluated the synthesized data using different metrics.
Input : processed_artificial_genome_data.csv, vcf_formatted.csv, baseline_artificial_data.csv
