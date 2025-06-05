# GraphTalk Madrid 2025 Demo
## 🧠 GraphRAG sobre Catálogo de Productos con Neo4j y LangChain

Este notebook implementa una demo de **GraphRAG (Retrieval-Augmented Generation sobre grafos)** utilizando una base de productos en Neo4j. La finalidad es enriquecer respuestas generadas por un LLM a partir de descripciones de productos almacenadas como nodos en un grafo.

## ¿Qué hace el código?

1. **Carga configuraciones** desde variables de entorno: credenciales de Neo4j y clave de OpenAI.

2. **Inicializa un vectorstore** (`Neo4jVector`) a partir de un grafo existente en Neo4j:
   - Genera embeddings para los nodos `Product`, usa las propiedades `name` y `description`.

3. **Realiza búsquedas por similitud semántica**:
   - Dado un texto libre, recupera los productos más similares según sus descripciones.

4. **Genera respuestas enriquecidas**:
   - Crea prompts dinámicos incluyendo los resultados relevantes.
   - Utiliza un LLM de OpenAI para construir una respuesta natural y contextualizada.

## Tecnologías utilizadas

- **LangChain**: Framework para integrar LLMs con fuentes externas.
- **Neo4jVector**: Vectorstore especializado para trabajar con grafos en Neo4j.
- **OpenAIEmbeddings**: Modelo de embeddings semánticos.
- **Neo4j**: Base de datos de grafos que almacena productos con embeddings.

---