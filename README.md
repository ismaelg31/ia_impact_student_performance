# 📊 AI Impact on Student Performance (EDA + Análisis)

Este proyecto analiza un dataset de **8,000 estudiantes** para explorar si el **uso de herramientas de IA** y la **intensidad de uso** se relacionan con el **rendimiento académico** (puntaje final y aprobación).

> Nota: El análisis es **correlacional** (observacional). No se infiere causalidad.

---

## 🎯 Objetivo
Responder dos preguntas principales:

1. **IA vs desempeño:** ¿Los estudiantes que usan IA tienen mejores resultados que los que no la usan?
2. **Intensidad de uso:** Entre quienes usan IA, ¿más tiempo/prompts se asocia con cambios en el rendimiento?

---

## 📦 Dataset
- Filas: **8,000**
- Columnas: **26**
- Variables clave:
  - Rendimiento: `final_score`, `passed`, `assignment_scores_avg`, `last_exam_score`, `concept_understanding_score`
  - IA: `uses_ai`, `ai_usage_time_minutes`, `ai_prompts_per_week`, `ai_dependency_score`, `ai_generated_content_percentage`, `ai_tools_used`
  - Hábitos: `study_hours_per_day`, `sleep_hours`, `attendance_percentage`, `social_media_hours`

### Valores faltantes
Se detectaron nulos en:
- `ai_tools_used` (1,362)
- `ai_usage_purpose` (1,346)

Estos se tratan de forma explícita (ej. “No AI” / “No especificado”) para que el análisis no pierda filas y sea reproducible.

---

## 🧪 Metodología (resumen)
1. **Carga del dataset**
2. **Revisión rápida de estructura y calidad**
3. **Limpieza mínima y preparación**
   - manejo de nulos en variables de IA
   - creación de etiquetas de lectura (`uses_ai_label`, `passed_label`)
4. **EDA (Exploratory Data Analysis)**
   - distribuciones (histogramas)
   - comparaciones por grupos (boxplots / barras)
   - correlaciones (heatmap)
5. **Análisis por preguntas**
   - comparación AI vs No AI
   - cuartiles de intensidad (minutos y prompts)
6. **Exportación de outputs** en CSV para reportes/dashboards

---

## ✅ Resultados (alto nivel)
- **AI vs No AI:** diferencias muy pequeñas en `final_score` y `pass_rate` (en este dataset no se observa un impacto relevante solo por usar IA).
- **Intensidad:** no se observa un patrón claro de “más IA = mejor rendimiento” usando cuartiles por tiempo/prompts.
- Variables académicas tradicionales (por ejemplo `concept_understanding_score`) muestran relación más fuerte con `final_score` que las variables de IA.
