# VisionRAG

VisionRAG is an innovative implementation of MULTI-MODALITY-RAG, leveraging the novel approach introduced in [ColPali: Efficient Document Retrieval with Vision Language Models](https://arxiv.org/abs/2407.01449).

<p align="center">
  <img src="images/colpali.jpg" alt="ColPali Architecture" width="800px">
</p>

## 🔍 Overview!

ColPali offers a groundbreaking method for document retrieval using vision language models. This project aims to demonstrate how visual-based embedding can simplify and enhance RAG systems, making them more versatile and easier to implement for a wide range of document types.

### Key Features of ColPali:

- Direct embedding of document screenshots
- No need for OCR or complex preprocessing
- Handles multi-modal content (text, images, charts, tables)
- Streamlined retrieval and ranking process
- Built on ColPali 2's efficient embedding technique

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


## 📚 Resources

For more information about this innovative approach:

- [ColPali GitHub Repository](https://github.com/illuin-tech/colpali)
- [ColPali on Hugging Face](https://huggingface.co/vidore/colpali)
- [Colpali Blog](https://blog.vespa.ai/retrieval-with-vision-language-models-colpali/)

## 🎯 Project Goals

1. Implement a multi-modal RAG system using ColPali's approach
2. Demonstrate the efficiency and versatility of this approach 

## 🚀 Getting Started


