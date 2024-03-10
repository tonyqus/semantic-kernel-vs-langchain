# Semantic Kernel vs LangChain

The repo tries to compare Semantic Kernel and LangChain to show the difference and similarity between them.

| LangChain | Semantic Kernel                                | Note                                                       |
| --------- | ---------------------------------------------- | ---------------------------------------------------------- |
| Chains    | Kernel                                         | Construct sequences of calls                               |
| Agents    | Planner                                        | Auto create chains to address novel needs for a user       |
| Tools     | Plugins (semantic functions + native function) | Custom components that can be reused across different apps |
| Memory    | Memory                                         | Store context and embeddings in memory or other storage    |

## Initial Release Date
LangChain: Oct, 2022

Semantic Kernel: Mar, 2023 

## Some Numbers
Semantic Kernel: <img alt="Github Stars" src="https://img.shields.io/github/stars/microsoft/semantic-kernel?logo=github&style=flat-square&labelColor=343b41"/> [![Pip Downloads](https://static.pepy.tech/badge/semantic-kernel)](https://pepy.tech/project/semantic-kernel) [![NuGet](https://img.shields.io/nuget/dt/Microsoft.SemanticKernel?label=Nuget-downloads)](https://www.nuget.org/packages/Microsoft.SemanticKernel) <img src="https://img.shields.io/github/contributors/microsoft/semantic-kernel?logo=github&label=contributors" alt="GitHub contributors"/>

LangChain: <img alt="Github Stars" src="https://img.shields.io/github/stars/langchain-ai/langchain?logo=github&style=flat-square&labelColor=343b41"/> [![pip-downloads](https://static.pepy.tech/badge/langchain)](https://pepy.tech/project/langchain) ![npm](https://img.shields.io/npm/dt/langchain?label=npm-downloads) <img src="https://img.shields.io/github/contributors/langchain-ai/langchain?logo=github&label=contributors" alt="GitHub contributors"/>

## Major Contributors 
(based on Github contribution chart)

Semantic Kernel:

[Devis Lucato](https://www.linkedin.com/in/devislucato/) - Principle Architect@MSFT

[Lee Miller](https://www.linkedin.com/in/lee-miller-838b5621/) - Senior Software Engineer@MSFT

[Adrian Bonar](https://www.linkedin.com/in/adrian-bonar/) - Principle Software Engineer@MSFT

[Mark Wallace](https://www.linkedin.com/in/markewallace/) - Principle Software Engineer@MSFT

[Shawn Callegari](https://www.linkedin.com/in/shawncallegari/) - Principle Software Engineer Lead@MSFT

LangChain: 

[Harrison Chase](https://www.linkedin.com/in/harrison-chase-961287118/) - Cofounder/CEO | ex-Robust Intelligence staff

[Bagatur Askaryan](https://www.linkedin.com/in/bagatur-askaryan/) - Founding Software Engineer | ex-Robust Intelligence staff

[Erick Friis](https://www.linkedin.com/in/efriis/) - Founding Software Engineer 

[Jacob Lee](https://www.linkedin.com/in/jacoblee93/) - Founding Software Engineer | Langchain.js maintainer

[Davis Chase](https://github.com/dev2049) - langchain.js maintainer

[Nuno Campos](https://www.linkedin.com/in/nuno-f-campos/) - Founding Software Engineer

[Eugene Yurtsev](https://www.linkedin.com/in/eugene-yurtsev-797a3b1b/) 


## Supported languages

| Language   | LangChain | Semantic Kernel |
| ---------- | --------- | --------------- |
| Python     | ✅        | ✅              |
| JavaScript | ✅        | ❌              |
| C#         | ❌        | ✅              |
| Java       | ✅        | ✅              |

## Data connection (Retrieval)

Many LLM applications require user-specific data that is not part of the model's training set. The primary way of accomplishing this is through Retrieval Augmented Generation (RAG). In this process, external data is *retrieved* and then passed to the LLM when doing the *generation* step.

![Data connection](./images/data_connection.jpg)

| Building block                                                                                  | LangChain                                                                                                                                                                                                                                                                                                                                        | Semantic Kernel                    |
| ----------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------- |
| Document loaders: Load documents from many different sources                                    | Over 100 document loaders: [File Loaders](https://js.langchain.com/docs/modules/data_connection/document_loaders/integrations/file_loaders/) (CSV, Docx, EPUB, JSON, PDF, Markdown...) and [Web Loaders](https://js.langchain.com/docs/modules/data_connection/document_loaders/integrations/web_loaders/) (Azure Storage, S3, GitHub, Figma...) | Web pages, PDF, Images, Word, PowerPoint, Excel, Markdown, Text, JSON (via Kernel Memory)                               |
| Document transformers: Split documents, drop redundant documents, and more                      | Multiple Split methods                                                                                                                                                                                                                                                                                                                           | ❌                                 |
| Text embedding models: Take unstructured text and turn it into a list of floating point numbers | Over 25 different embedding providers: OpenAI, Azure OpenAI, Hugging Face, Cohere, Google PaLM, Google Vertex AI, TensorFlow...                                                                                                                                                                                                                  | OpenAI, Azure OpenAI, Hugging Face |
| Vector stores: Store and search over embedded data                                              | Over 50 vector stores                                                                                                                                                                                                                                                                                                                            | About 10 vector stores             |
| Retrievers: Query your data                                                                     | Simple semantic search, Contextual compression, Time-weighted vector store retriever, Parent Document Retriever, Self Query Retriever, Ensemble Retriever, and more.                                                                                                                                                                             | Simple semantic search             |


## Automatically orchestrate AI

| Type                   | LangChain's Agents | Semantic Kernel's Planner |
| ---------------------- | ------------------ | ------------------------- |
| Conversational         | ✅                 | ❌                        |
| Plan and execute       | ✅                 | ✅ (SequentialPlanner)    |
| ReAct                  | ✅                 | ✅ (StepwisePlanner)      |
| Tree of Thoughts (ToT) | ✅                 | ❌                        |
