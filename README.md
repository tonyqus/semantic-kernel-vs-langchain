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

## Top Contributors 
(based on Github contribution chart, ordered by additions instead of commits)

Semantic Kernel:  [Github contributor insights](https://github.com/microsoft/semantic-kernel/graphs/contributors)

[Devis Lucato](https://github.com/dluc) - Principle Architect@MSFT

[Lee Miller](https://github.com/lemillermicrosoft) - Senior Software Engineer@MSFT

[Adrian Bonar](https://github.com/adrianwyatt) - Principle Software Engineer@MSFT

[Mark Wallace](https://github.com/markwallace-microsoft) - Principle Software Engineer@MSFT

[Shawn Callegari](https://github.com/shawncal) - Principle Software Engineer Lead@MSFT

[Roger Barreto](https://github.com/RogerBarreto) - Senior Software Engineer@MSFT

[Dmytro Struk](https://github.com/dmytrostruk) - Senior Software Engineer@MSFT

[Abby Harrison](https://github.com/awharrison-28) - Senior Software Engineer@MSFT

LangChain: [Github contributor insights](https://github.com/langchain-ai/langchain/graphs/contributors)

[Bagatur Askaryan](https://github.com/baskaryan) - Founding Software Engineer@LangChain

[Harrison Chase](https://github.com/hwchase17) - Cofounder/CEO@LangChain

[Erick Friis](https://github.com/efriis) - Founding Software Engineer@LangChain

[Jacob Lee](https://github.com/jacoblee93) - Founding Software Engineer@LangChain | Langchain.js maintainer

[Davis Chase](https://github.com/dev2049) - langchain.js maintainer

[Sergerdn](https://github.com/sergerdn)

[Nuno Campos](https://github.com/nfcampos) - Founding Software Engineer@LangChain

[Lance Martin](https://github.com/rlancemartin) - Software Engineer@LangChain

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
| Vector stores: Store and search over embedded data                                              | Over 50 vector stores  - [List](https://python.langchain.com/docs/integrations/vectorstores)                                                                                                                                                                                                                                                                                                                          | About 10 vector stores - [List](https://learn.microsoft.com/en-us/semantic-kernel/memories/vector-db)            |
| Retrievers: Query your data                                                                     | Simple semantic search, Contextual compression, Time-weighted vector store retriever, Parent Document Retriever, Self Query Retriever, Ensemble Retriever, and more.                                                                                                                                                                             | Simple semantic search             |

## Automatically orchestrate AI

| Type                   | LangChain's Agents | Semantic Kernel's Planner |
| ---------------------- | ------------------ | ------------------------- |
| Conversational         | ✅                 | ❌                        |
| Plan and execute       | ✅                 | ✅ (Handlebars Planner)    |
| ReAct                  | ✅                 | ✅ (Stepwise Planner)      |
| Tree of Thoughts (ToT) | ✅                 | ❌                        |

## Supported Vector Stores
| Vector Database        | LangChain | Semantic Kernel |
| ---------------------- | ------------------ | ------------------------- |
|MongoDB|✅|✅|
|Chroma|✅|✅|
|Pinecone|✅|✅|
|DuckDB|❌|✅|
|Redis|✅|✅|
|Sqlite|❌|✅|
|PGVector|✅|✅|
|Milvus|✅|✅|
|Kusto (Azure Data Explorer)|❌|✅|
|Qdrant|✅|✅|
|Weaviate|✅|✅|
|Azure AI Search|✅|✅|
|Cloudflare Vectorize|✅|❌|
|SAP HANA Cloud Vector Engine|✅|❌|
|Supabase|✅|❌|
|Neo4j Vector Index|✅|❌|
|Cassandra|✅|❌|
|Couchbase|✅|❌|
|LanceDB|✅|❌|
|RocketSet|✅|❌|
|Voy|✅|❌|
|Zep|✅|❌|





