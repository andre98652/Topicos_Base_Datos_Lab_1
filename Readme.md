# 🎓 Sistema de Recomendación Académica EPIS-UNSA

Este proyecto es un motor de búsqueda y recomendación inteligente de
cursos universitarios desarrollado para la Escuela Profesional de
Ingeniería de Sistemas (EPIS). Utiliza una base de datos vectorial para
entender los intereses de los estudiantes y sugerir trayectorias
académicas basadas en semántica y metadatos.

## 🚀 Características

-   **Búsqueda Semántica:** Encuentra cursos por conceptos, no solo por
    palabras clave.
-   **Persistencia de Datos:** Implementado con `PersistentClient` de
    ChromaDB para que la información no se pierda entre sesiones.
-   **Filtros Inteligentes:** Recomendaciones basadas en el semestre
    actual del alumno y su perfil de habilidades.
-   **Análisis de Relaciones:** Capacidad de encontrar cursos similares
    basándose en la carga temática de sus sílabos/descripciones.

## 🛠️ Tecnologías Utilizadas

-   Python 3.x
-   **ChromaDB:** Base de datos vectorial de código abierto.
-   **Sentence-Transformers:** Modelo `all-MiniLM-L6-v2` para la
    generación de embeddings (384 dimensiones).
-   **Pandas:** Para la gestión de tablas y análisis estadístico.

## 📋 Requisitos e Instalación

Para ejecutar este sistema, necesitas instalar las dependencias
necesarias. Ejecuta el siguiente comando en tu terminal o celda de
Colab:

``` bash
pip install chromadb sentence-transformers pandas
```

## 📂 Estructura del Proyecto

-   `db_epis_unsa/`: Carpeta local donde se almacena la base de datos
    persistente (SQLite + Vectores).
-   `sistema_recomendacion.ipynb`: Notebook principal con el código del
    motor y el menú.
-   `README.md`: Documentación del sistema.

## 💻 Instrucciones de Uso

1.  **Inicialización:** Al ejecutar el código por primera vez, el
    sistema vectorizará 20 cursos de la EPIS.
2.  **Menú Interactivo:**
    -   **Opción 1:** Ingresa tus intereses (ej. "programación web") y
        tu semestre máximo para ver qué puedes llevar.
    -   **Opción 2:** Escribe el nombre de un curso (ej. "Inteligencia
        Artificial") para ver otros relacionados.
    -   **Opción 3:** Ingresa tus habilidades y filtra por el tipo de
        área (básica, especialidad, electivo).
3.  **Persistencia:** Si cierras el programa y lo vuelves a abrir, el
    sistema detectará la carpeta `db_epis_unsa` y cargará los datos
    automáticamente sin repetir la inserción.

## ⚠️ Limitaciones y Futuras Mejoras

-   **Limitación 1:** El sistema es sensible al nombre exacto del curso
    en la opción de similitud.\
    **Mejora:** Implementar lógica difusa (Fuzzy Matching).

-   **Limitación 2:** No valida el cumplimiento real de prerrequisitos
    de forma encadenada.\
    **Mejora:** Integrar un grafo de dependencias de malla curricular.

------------------------------------------------------------------------

**Autor:** \[Andre Delgado\]\
**Curso:** \[Topicos Avanzados de base de datos\]\
**Escuela:** Ingeniería de Sistemas - UNSA\
**Año:** 2026
