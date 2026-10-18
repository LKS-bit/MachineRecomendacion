# MachineRecomendacion
# Sistema de Recomendación de Películas basado en Reglas de Asociación
**Taller 2 · Aprendizaje No Supervisado (Certamen 2)**

**Dashboard:**
**Presentación (Canva):** [Pegar link aquí]

---

## 1. Descripción del Problema y Caso de Uso
Las plataformas de streaming enfrentan el problema de **sobrecarga de opciones (fatiga de decisión)**: los usuarios abandonan la sesión si no encuentran rápidamente qué ver. 
Este proyecto transforma el historial de calificaciones de **MovieLens 1M** en un motor de recomendación auditable y explicable basado en **Reglas de Asociación (Apriori / FP-Growth)**, capaz de sugerir películas explicando el motivo exacto (*"Porque te gustó X, te recomendamos Y"*) y manejando usuarios nuevos mediante un esquema híbrido con respaldo de popularidad (*arranque en frío*).

## 2. Fuente de los Datos
**Dataset:** [MovieLens 1M Dataset (GroupLens Research)](https://grouplens.org/datasets/movielens/1m/)
**Licencia:** Uso abierto para fines académicos y de investigación (GroupLens / University of Minnesota).
**Definición de Transacción:** El conjunto de películas que un usuario (`userId`) evaluó positivamente (**calificación $\ge 4$ estrellas** en escala de 1 a 5). Se filtran transacciones con al menos 2 ítems.
**Definición de Item:** Película única identificada por su título y año de estreno (ej. `Matrix, The (1999)`).

## 3. Estructura del Repositorio
```text
certamen2-grupo-X/
├── README.md                   ← Documentación del proyecto y links
├── requirements.txt            ← Dependencias para reproducción y despliegue
├── app.py                      ← Aplicación interactiva en Streamlit
├── data/                       ← Datos precalculados exportados desde el Notebook
│   ├── resumen.json            ← KPIs globales (transacciones, ítems, densidad)
│   ├── reglas.csv              ← Reglas filtradas (Fisher + Holm y sin redundantes)
│   ├── populares.csv           ← Top películas por soporte (respaldo arranque en frío)
│   └── hitrate.csv             ← Resultados de evaluación offline (Leave-One-Out)
└── Certamen2_Grupo_X.ipynb     ← Notebook completo con el flujo de minería y evaluación
