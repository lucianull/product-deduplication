Product Deduplication Using Vector Embeddings

Overview
This project aims to consolidate duplicate product entries extracted from various sources into a single enriched record. By leveraging vector embeddings and similarity search, the system efficiently identifies and merges duplicate products based on their textual attributes.

Approach
The deduplication process involves several key steps:
1. Data Cleaning:
    - Preprocessing the dataset to ensure text attributes are structured and consistent.

2. Generating Embeddings:
    - Using a Sentence Transformer (all-mpnet-base-v2) to convert product descriptions into 768-dimensional embeddings.

3. Storing Embeddings in a Vector Database:
    - Using ChromaDB for efficient nearest-neighbor searches.

4. Identifying and Consolidating Duplicates:
    - Performing similarity searches to find the top 10 nearest neighbors for each product.
    - Applying a cosine distance threshold of 0.15 to determine duplicates.
    - Merging duplicates into a single entry and marking them as processed.
5. Saving the Processed Data:
    - The final dataset, with unique and enriched product entries, is saved as products_output_0_15.csv.
