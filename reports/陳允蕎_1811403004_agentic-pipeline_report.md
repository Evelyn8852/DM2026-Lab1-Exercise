# Your report

**Paragraph 1 — Data Loading and Exploration**

I loaded the 20 Newsgroups dataset using `load_dataset_tool` (`load_dataset_1`), which contained 2,257 documents across four categories: `alt.atheism`, `comp.graphics`, `sci.med`, and `soc.religion.christian`. I inspected the documents (`inspect_2`, `inspect_3`) and checked for missing values (`missing_4`–`missing_6`) and duplicate texts (`duplicates_7`). No missing values or exact duplicate texts were found. I also examined document-length statistics (`describe_8`) to better understand the variation in document sizes.

**Paragraph 2 — Document-Term Matrix and Term Frequency**

I constructed a document-term matrix using `build_dtm_tool` (`dtm_9`) with unigram features, producing a matrix of 2,257 documents and 1,000 terms. I then analyzed term frequencies (`tf_10`) and generated a DTM heatmap (`heatmap_11`) to visualize term occurrences across selected documents. Common words such as "that" and "it" appeared frequently, suggesting that stopwords and text preprocessing could influence the resulting features.

**Paragraph 3 — Feature Selection and Correlation Analysis**

I applied variance filtering (`variance_12`, `variance_13`) to remove low-variance terms. Using a threshold of 0.15, 595 terms were retained. I also performed Pearson (`pearson_14`) and Spearman (`spearman_15`) correlation filtering for the `comp.graphics` category, retaining 661 and 741 terms, respectively. The Spearman visualization showed that terms such as "graphics", "files", and "image" were positively associated with the target category. I additionally generated a feature correlation matrix (`feature_corr_16`) to examine relationships between selected terms.

**Paragraph 4 — Frequent Pattern Mining**

I performed frequent pattern mining using `mine_patterns_tool` (`mine_patterns_17`) for the `comp.graphics` category, applying term-frequency filtering and the FP-Growth algorithm with a minimum support count of 10. The analysis generated 4,489 frequent patterns. These patterns represent terms or term combinations that frequently occur within documents belonging to the selected category, providing insight into recurring vocabulary patterns.

**Paragraph 5 — Dimensionality Reduction and Similarity Analysis**

I applied UMAP dimensionality reduction (`reduce_umap_18`) with two components, 15 neighbors, and a random seed of 42. The resulting scatter plot (`plots/陳允蕎_agentic-pipeline_plot_reduce_umap_18.png`) illustrated the distribution of documents across the four categories in a two-dimensional space. I also converted the category labels into a one-hot encoded matrix of shape (2257, 4) (`binarize_labels_19`). Finally, I calculated cosine similarity between documents 0 and 1 (`cosine_sim_20`), obtaining a score of approximately 0.1454, indicating relatively low similarity between their term-frequency vectors.