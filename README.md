# 🧠 Taller 1 - IA Generativa (EcoMarket)

Autores: 

- Farid Sandoval 
- Ivan Morán
- Josué Cobaleda

Este repositorio contiene el desarrollo del **Taller Práctico #1** de la asignatura de Inteligencia Artificial Generativa, enfocado en el diseño de una solución basada en **LLMs y arquitectura RAG (Retrieval-Augmented Generation)** para mejorar el servicio al cliente de una empresa de e-commerce ficticia llamada **EcoMarket**.

---

## 🎯 Objetivo del proyecto

Diseñar y proponer una solución basada en IA generativa que permita:

- Reducir los tiempos de respuesta en atención al cliente  
- Automatizar consultas repetitivas (≈80%)  
- Mejorar la experiencia del usuario  
- Mantener precisión mediante integración con datos reales  

---

## 🧩 Estructura del repositorio
Taller1-IAGenerativa/
│
├── README.md
├── fase1.md # Selección y justificación del modelo
├── fase2.md # Análisis de riesgos éticos (modelo Huang)
├── fase3.md # Ingeniería de prompts y prototipo
│
├── data/
│ ├── pedidos.json # Base de datos simulada de pedidos
│ └── politica_devoluciones.txt # Políticas de devolución
│
├── prompts/
│ ├── prompt_pedido.txt
│ └── prompt_devolucion.txt
│
├── Model-ollama-langchain.ipynb.

---

## 🏗️ Arquitectura de la solución

La solución propuesta sigue un enfoque híbrido basado en RAG.


### Componentes clave:

- **LLM (LLaMA 3 vía Ollama)**: generación de respuestas
- **RAG**: recuperación de información relevante
- **Embeddings**: búsqueda semántica en datos
- **Datos estructurados**: pedidos y políticas
- **Prompt engineering**: control del comportamiento del modelo

---

## ⚙️ Tecnologías utilizadas

- Python 3
- Ollama (LLM local)
- Sentence Transformers (embeddings)
- NumPy (similitud vectorial)
- JSON / TXT (fuentes de datos)
- Prompt Engineering

---

## 🚀 Cómo ejecutar el proyecto

### Requisitos previos

- **Python 3.10+** (con venv activo como kernel del notebook)
- **Ollama** instalado ([descargar desde ollama.com](https://ollama.com))
- Ejecutar desde **la raíz del proyecto** (donde están `data/` y `prompts/`)

### Pasos

#### 1. Clonar el repositorio:

```bash
git clone https://github.com/josue-cobaleda/Taller1-IAgenerativa.git
cd Taller1-IAgenerativa

2. Crear y activar un entorno virtual:

python -m venv venv
source venv/Scripts/activate  # Windows: venv\Scripts\activate

3. Instalar dependencias:
Opción A (recomendado): 

pip install -r requirements.txt

Opción B (alternativa):

pip install langchain>=0.3,<0.4 \
  langchain-community>=0.3,<0.4 \
  langchain-ollama>=0.2,<0.3 \
  langchain-huggingface>=0.1,<0.2 \
  ollama faiss-cpu sentence-transformers gradio

4. Instalar y ejecutar Ollama:
Descargar instalador desde https://ollama.com/download/windows (Windows) o https://ollama.com (macOS/Linux)
Tras instalar, Ollama corre automáticamente como servicio en http://localhost:11434
Si no está activo, abre una terminal y ejecuta: ollama serve
Verifica: ollama --version

5. Abrir el notebook:
En VS Code (con kernel del venv activo):

Abre Model-ollama-langchain.ipynb
Selecciona kernel: Python 3.10+ (venv)
Run All para ejecutar de arriba a abajo
En Jupyter Lab/Notebook:

jupyter lab Model-ollama-langchain.ipynb

6. El notebook descargará automáticamente:
Modelo LLaMA 3.2:3b (~2 GB) la primera vez
Embeddings multilingües (~1.3 GB) la primera vez
En corridas posteriores se cargan desde caché
Probar el asistente
Ejecuta las celdas de "Preguntas de prueba" (sección 7)

"¿Cuál es el estado de mi pedido 1003?"
→ Responde con estado "Retrasado" y fecha de entrega

"¿Puedo devolver un producto de higiene personal?"
→ Responde según política de devoluciones (no reembolsable)
El chatbot Gradio abre en http://localhost:7860 tras ejecutar la última sección.

---

## 🧠 Enfoque de Prompt Engineering

Se aplicaron técnicas avanzadas de prompting:

Role Prompting
Context Injection (RAG)
Instruction Prompting
Output Formatting
Constraint Prompting
Conditional Logic Prompting
Tone Control

Esto permitió:

Reducir alucinaciones
Mejorar precisión
Controlar estructura de respuestas
Alinear la IA con necesidades empresariales

---

## ⚖️ Consideraciones éticas

Se realizó un análisis basado en el modelo de Huang, considerando:

Seguridad (alucinaciones, prompt injection)
Privacidad de datos
Sesgo algorítmico
Transparencia
Impacto laboral
Sostenibilidad

Se proponen mecanismos de mitigación como:

RAG con fuentes controladas
Escalamiento a humanos
Minimización de datos
Auditoría de respuestas

---

## 💡 Resultados clave

La solución permite:

Automatizar consultas frecuentes
Mejorar tiempos de respuesta (de horas a segundos)
Reducir carga operativa
Mantener precisión mediante datos reales
Escalar sin aumentar proporcionalmente el equipo


