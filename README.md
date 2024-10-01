# VisionRAG

VisionRAG is an innovative implementation of MULTI-MODALITY-RAG, leveraging the novel approach introduced in [ColPali: Efficient Document Retrieval with Vision Language Models](https://arxiv.org/abs/2407.01449).

<p align="center">
  <img src="images/colpali.jpg" alt="ColPali Architecture" width="800px">
</p>

## Overview!

ColPali offers a groundbreaking method for document retrieval using vision language models. This project aims to demonstrate how visual-based embedding can simplify and enhance RAG systems, making them more versatile and easier to implement for a wide range of document types.

### Key Features of ColPali:

- Direct embedding of document screenshots
- No need for OCR or complex preprocessing
- Handles multi-modal content (text, images, charts, tables)
- Streamlined retrieval and ranking process
- Built on ColPali 2's efficient embedding technique

## How does colpali compare to the traditional way of Multi-modality RAG

1) Dependence on OCR and Complex Preprocessing
- Challenge: Traditional document retrieval systems often rely on Optical Character Recognition (OCR) for extracting text from images, which can be error-prone and require extensive preprocessing.
- Problem: OCR may struggle with complex layouts, low-quality images, or non-standard fonts, leading to inaccurate text extraction.

2) Efficiency and Speed
- Challenge: Many systems had inefficiencies in processing and indexing documents, leading to slower retrieval times.
- Problem: High computational costs and slow indexing could limit the scalability and usability of the system.

3) Scalability
- Challenge: Scaling document retrieval systems to handle large volumes of data and complex document structures often posed significant challenges.
- Problem: Systems could become unwieldy and less effective as the dataset grew in size and complexity.

4) Interpretability
- Challenge: Understanding and visualizing what parts of a document the model is focusing on or interpreting could be difficult.
- Problem: Lack of transparency in how models made decisions made it challenging to trust and refine the system.

## How ColPali Addresses These Challenges

1) Direct Embedding of Document Screenshots
- Solution: ColPali eliminates the need for OCR by directly embedding document screenshots into the model. This simplifies the preprocessing pipeline and improves accuracy by leveraging end-to-end learning.


2) Enhanced Efficiency and Speed
- Solution: By leveraging efficient embedding techniques and optimized indexing on GPUs, ColPali improves the speed and efficiency of document retrieval.
- Benefit: Accelerates indexing and retrieval processes, making the system more scalable and responsive.

3) Scalability Improvements
- Solution: ColPali’s design is built to handle large datasets and diverse document types more effectively.
- Benefit: Allows the system to scale better with increasing data volumes and complex document structures.

4) Improved Interpretability
- Solution: ColPali includes features for generating and visualizing heatmaps and attention maps, providing insights into model focus and decision-making.
- Benefit: Enhances transparency and helps users understand how the model interacts with different parts of the document.

### How fast is the indexing? 
We tested the speed of the indexing on affordable GPUs , we pass the embeddings into GPUs 

| GPU          | Batch Size | Speed (s/iteration) |
|--------------|-------------|---------------------|
| NVIDIA A10g  | 4           | 2.67                |
| NVIDIA l4    | 4           | 3.6s                |
| NVIDIA t4    | 4           | 4.55                |

### Interpretability 
| Query                                              |  Image                                               |  Image                                                  |
|----------------------------------------------------|------------------------------------------------------------|------------------------------------------------------------|
| Scaled and Dot                                     |<p align="center"><img src="images/hm_token_1.png" width="800px"></p>|<p align="center"><img src="images/hm_token_3.png" width="800px"></p>|
| What is the model architecture and what is adaptive visual encoding?  |<p align="center"><img src="images/hm_token_map_32.png" width="800px"></p>|<p align="center"><img src="images/hm_token_41.png" width="800px"></p>|

What does this heatmap tell us ?
- The heatmap shows areas of high attention (bright spots) and low attention (darker areas) for a specific token.
-  The model seems to understand and focus on the relevant parts of the image that discuss or illustrate the adaptive visual encoding concept.
- The spread of attention indicates how precisely the model can identify the relevant areas. In this case, the attention seems to be spread across relevant diagrams and text, suggesting a good understanding.


## Resources

For more information about this innovative approach:

- [ColPali GitHub Repository](https://github.com/illuin-tech/colpali)
- [ColPali on Hugging Face](https://huggingface.co/vidore/colpali)
- [Colpali Blog](https://blog.vespa.ai/retrieval-with-vision-language-models-colpali/)



## Getting Started
1) The notebook provids  a step by step on how to use colpali to index and how to then pass the image to a Vision-Language model  to generate answers
2) The notebook also shows how to generate the heatmaps to check what the model sees


