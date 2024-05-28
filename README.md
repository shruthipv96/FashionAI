# Fashion AI
---
> A Generative Search System which can understand a user's query and recommend the most suitable fashion items based on their preferences from a vast collection of product data.
---

## Table of Contents
* [Dataset](#dataset)
* [Steps to Run the Project](#steps-to-run-the-project)
* [System Design](#system-design)
* [Models Used](#models-used)
* [Example Results](#example-results)
* [Conclusion](#conclusion)

Detailed report of the project is available at [here](https://github.com/shruthipv96/FashionAI/blob/main/FashionAI_Doc.pdf).

## Dataset
The dataset used for this project is [Myntra Fashion Product Dataset (kaggle.com)](https://www.kaggle.com/datasets/djagatiya/myntra-fashion-product-dataset). It includes thousands of fashion products, each with detailed information such as description, price, rating, brand name, and other attributes.
The dataset is organized in 'dataset/' folder as follows:
* _Fashion Dataset v2.csv_: This CSV file contains each product in a row, with various details spread across columns.
* _Image Folder_: This folder contains two zip folders. Extract all the images and place into this image folder. Then, this folder contains sample images for each product. Each image file is named according to the corresponding product's 'p_id' value from the CSV.

## Steps to Run the Project 
To experiment with the search tool, follow these steps:
1. _Open the Jupyter Notebook_: Ensure you have the Jupyter Notebook for this project open and run all the cells for the first time after launch.
**You can skip the cell with the comment “Add documents to the collection with a tqdm progress bar.” in section 1.2 under heading “Build Chroma Store” in case you already have the chroma db downloaded.**
3. _Navigate to the Playground Section_: Scroll to the end of the notebook until you find the section titled "Playground" or jump from the Table of Contents.
4. _Interact with the Search Tool_: In this section, you can test and experiment with the search tool. You can input various user queries to see how the system retrieves and recommends fashion products based on the descriptions, prices, ratings, brand names, and other attributes from the dataset.
In this section, two cells are provided to experiment with Semantic Search and Generative Search.
 
 ![image](https://github.com/shruthipv96/FashionAI/assets/32814013/e32f0557-07ef-447b-b8aa-a745f1f7e351)

4. _Analyse Results_: Review the recommended products to understand how well the search tool matches the user query. This will help in assessing the accuracy and effectiveness of the search algorithm.
> Make sure to set the OpenAI Api key in ‘OpenAI_API_Key.txt’ file 

Feel free to experiment with different queries and explore different aspects of the dataset to fully understand the capabilities of the search system.

## System Design
![image](https://github.com/shruthipv96/FashionAI/assets/32814013/abb519f4-737d-4249-9419-a7efd3c18fb9)

## Models Used
| Topic | Model |
|:------|:------|
| Embedding | [nomic-ai/nomic-embed-text-v1.5](https://huggingface.co/nomic-ai/nomic-embed-text-v1.5) |
| Cross Encoder for reranking | ms-marco-MiniLM-L-6-v2 |
| Generative Response | gpt-3.5-turbo |

## Example Results
From Semantic search with reranking layer,
![Query3_SearchLayer](https://github.com/shruthipv96/FashionAI/assets/32814013/0e2814bf-8318-4cc4-b18a-a47c5f495a27)

From Generative search final layer,
![Query3_GenerativeSearch](https://github.com/shruthipv96/FashionAI/assets/32814013/7701b2b3-ecde-439d-9d10-e5ad91e7e7c8)

## Conclusion
Finally, with the function GenerativeSearch(), user can input a query to fetch a product from the vast database using natural language.

### Key Points
- Explored various models to implement embedding.
- Explored various ways to prepare the document for query.
- Explored different prompts to generate appropriate response for the user query.
- Implemented cache technique for faster response.
- Hands-on experience with Chroma DB.
- Explored various datasets to experiment with RAG apart from this fashion dataset.
### Areas to improve
- In this scenario, I did not come with the use of chunking a single product data. This is an area to explore for the same problem statement.
- When using OpenAI embedding function, faced an error with ‘$’ character input. But I did not choose the model anyways since I could find something else with similar performance.
- There is still a room to explore the search query. For an example, if the user queries for “red t-shirt” it always gives the same set of results.


## Contact
Created by [Shruthip Venkatesh](https://github.com/shruthipv96) - feel free to contact me!

