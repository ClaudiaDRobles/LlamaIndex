LlamaIndex organiza tus datos dividiéndolos en nodos. Este proceso es importante para la información de forma que pueda ser utilizada eficientemente por modelos de lenguaje avanzado.
1. División de los Datos en Nodos
	- Tus datos, sin importar su origen(archivos, bases de datos, APIs,etc.),son fragmentados en partes más pequeñas llamadas nodos.
	- Estos nodos representan unidades manejables de información, como un párrafo en un documento, una fila de una hoja de cálculos o un registro de una base de datos.
2. Indexación de los Nodos
	- Una vez divididos, los nodos se indexan, lo que significa que se organizan de manera que puedan ser rápidamente buscados y recuperados.
	- Este índice puede ser creado utilizando:
		- **Modelos de lenguaje** que entiendan y categoricen los nodos según su contenido.
		- **Sistemas de incrustaciones (embeddings)** de terceros que convierten los nodos en representaciones vectoriales para facilitar su búsqueda.
		- **Bases de datos** optimizados para almacenar y acceder a los nodos indexados.
![[Pasted image 20241212105342.png]]
En resumen LlamaIndex permite que los datos sean fácilmente procesados, consultados y utilizados, independientemente de su volumen o complejidad. 

Diferentes tipos de indexaciones
![[Pasted image 20241212150356.png]]
1. **Index Lineal**
	En este tipo de indexación, los nodos se organizan en una secuencia simple y ordenada.
	- Como Funciona:
		  - Los nodos están conectados de manera lineal, uno tras otro ( Nodo1->Nodo2-> Nodo3).
		  - Es útil para casos en los que los datos tienen una estructura ordenada, como capítulos en un libro o párrafos en un documento.
	- Ejemplo: Supongamos que tenemos un manual técnico como un PDF dividido en capítulos:
		-Nodo1: Introducción 
		-Nodo2: Configuración inicial
		-Nodo3: Solución de problemas
	 Cuando haces una consulta como: ¿Cómo configurar el sistema?, el index revisa secuencialmente los nodos y devuelve información del nodo relevante (Nodo2).
2. **Index basado en Embedding (vector Index)**	
	Este tipo de index utiliza representaciones vectoriales (embeddings) para organizar los nodos según su contenido semántico. 
	- Como funciona:
	     -Cada nodo se convierte en un vector matemático que representa su  significado.
	     -Los vectores permiten realizar búsqueda semánticas, encontrando nodos relevantes incluso si la consulta no coincide exactamente con el  texto.
	- Ejemplo: Imagina que tienes datos como artículos de investigación, tesis, y publicaciones científicas en una biblioteca digital de una universidad :
	    -Nodo1: Artículo sobre inteligencia artificial
		-Nodo2: Artículo sobre aprendizaje automático
		-Nodo3: Artículo sobre redes neuronales.
	Cuando haces una consulta como: ¿Qué es el aprendizaje profundo? el index identificará que Node2 y Node3 son relevantes porque tienen conceptos relacionados, aunque las palabras exactas no coincidan.
3. **Index Jerárquico(Hierarchical Index)**
	Este tipo de index organiza los nodos en una estructura de árbol, con nodos raíz, nodos padres y nodos hijos.
	- Como funciona:
		  - Los datos se agrupan jerárquicamente, donde los nodos raíz contienen resúmenes o categorías principales y los nodos hijos contienen detalles específicos.
		  - Es ideal para grandes volúmenes de datos con categorías claras.
	- Ejemplo: Supongamos que tienes información sobre ciudades en un sistema de portal de turismo internacional
	    -Root Node: Información sobre ciudades
		-Parent Node1: ciuades de Estados Unidos
			-Node1: Nueva York (población, clima, etc.)
			-Node2: Los Ángeles
		-Parent Node2: Ciudades de Europa
			-Node3: París
			-Node4: Berlín
	Cuando haces una consulta como: ¿Cuál es la población de Nueva York navegará desde el nodo raíz hacia el nodo correspondiente (Node1) para devolver la respuesta.
4. Index basado en tópicos (Keyword Index)
	Este index organiza los nodos en función de palabras clave o conceptos principales.
	- Como funciona:
		-Cada nodo está etiquetado con palabras clave que representan su contenido.
		-Al buscar, se identifican los nodos que coinciden con las palabras clave de la consulta.
	- Ejemplo: Tienes datos sobre política, clima y población:
			-Node1: Datos sobre la población de Nueva York (etiqueta: "población").
			-Node2: Información sobre el clima de Nueva York (etiqueta: "clima").
			-Node3: Noticias políticas recientes (etiqueta: "política").
	Si consultas **"¿Qué información hay sobre el clima en Nueva York?"**, el índice encuentra el nodo etiquetado con "clima" y devuelve Node2.

| Tipo de Índice             | Ventaja                                                        | Usos comunes                                            |
| -------------------------- | -------------------------------------------------------------- | ------------------------------------------------------- |
| **Lineal**                 | Simplicidad, ideal para datos secuenciales                     | Libros, manuales técnicos                               |
| **Vectorial (Embeddings)** | Búsqueda semántica, alta precisión para conceptos relacionados | Bases de datos heterogéneas, artículos de investigación |
| **Jerárquico**             | Organización clara de datos complejos, navegación eficiente    | Bases de datos masivas, sistemas de categorías          |
| **Basado en Tópicos**      | Rápida identificación por palabras clave                       | Sistemas de FAQ, resúmenes temáticos                    |
**Representación Gráfica** 
![[Pasted image 20241213200343.png]]












