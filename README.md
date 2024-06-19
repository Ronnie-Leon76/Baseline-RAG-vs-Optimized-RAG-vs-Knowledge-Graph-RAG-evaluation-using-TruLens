### Comparing baseline RAG vs optimized RAG that uses hybrid search vs knowledge graph based RAG

- This repository contains a series of Jupyter notebooks that compare the performance of three different Retrieval Augmented Generation (RAG) systems: baseline RAG, optimized RAG using hybrid search with contextual compression, and knowledge graph-based RAG. The evaluation of these systems is performed using TruLens, which assesses three key metrics: context relevance, answer relevance, and groundedness.

- Context relevance is the proportion of the retrieved contexts that are relevant to the question. 

- Answer relevance is the proportion of the retrieved answers that are relevant to the question. 

- Groundedness is the proportion of the retrieved answers that are grounded in the retrieved contexts.


### Notebooks

- `BaselineRAG.ipynb` - This notebook contains the code to run a baseline RAG system and evaluate the performance using the three metrics: context relevance, answer relevance, and groundedness provided by TruLens.

- `Knowledge_Graph_Based_RAG.ipynb` - This notebook contains the code to run a knowledge graph based RAG system and evaluate the performance using the three metrics: context relevance, answer relevance, and groundedness provided by TruLens.

- `OptimizedRAG.ipynb` - This notebook contains the code to run an optimized RAG system that uses hybrid search and evaluate the performance using the three metrics: context relevance, answer relevance, and groundedness provided by TruLens.

### Setup
#### 1. Setup Neo4j Database in a Docker Container

- Start neo4j running in a docker container. You can do this by running the following command in the terminal:

```bash
sudo docker run     -p 7474:7474 -p 7687:7687     --name neo4j-apoc     -e NEO4J_apoc_export_file_enabled=true     -e NEO4J_apoc_import_file_enabled=true     -e NEO4J_apoc_import_file_use__neo4j__config=true     -e NEO4J_PLUGINS=\[\"apoc\"\]     neo4j:5.19.0
```

- This command will start a Neo4j instance with APOC (Awesome Procedures on Cypher) plugins enabled, allowing for enhanced data processing capabilities within Neo4j.

#### 2. Install Dependencies

- Install the required dependencies by running the following command in the terminal:

```bash
pip install -r requirements.txt
```

#### 3. Setup your environment variables i.e. OPENAI_API_KEY, NEO4J_URI, NEO4J_USER, NEO4J_PASSWORD

- Set the environment variables `OPENAI_API_KEY`, `NEO4J_URI`, `NEO4J_USER`, and `NEO4J_PASSWORD` to the appropriate values in your .env file.


#### 4. Run the Notebooks

- Run the notebooks `BaselineRAG.ipynb`, `Knowledge_Graph_Based_RAG.ipynb`, and `OptimizedRAG.ipynb` to compare the performance of the three different RAG systems.

### Summary

- This repository provides the tools and instructions necessary to compare different RAG implementations. By following the provided notebooks and setup instructions, you can evaluate and understand the performance differences across baseline, optimized, and knowledge graph-based RAG systems.