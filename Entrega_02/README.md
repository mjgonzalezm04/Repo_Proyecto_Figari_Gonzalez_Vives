# README — Documentación completa (Entrega_02)

## 1. Resumen ejecutivo
Se construyó una **base de datos limpia** a partir de **Google Trends** para Chile (últimos 5 años) con los términos **Pistacho**, **Nueces** y **Chocolate dubai**. La base final:
- Está **limpia** (sin NA, sin duplicados, con fechas en ISO).
- Es **comprensible** (columnas claras, formato ancho apto para Excel).
- Es **replicable** (script y notebook incluidos).
- **Sigue las observaciones docentes**: escalas **relativas** 0–100, comparabilidad asegurada al consultar los tres términos **en la misma búsqueda/categoría/tipo**.

## 2. Fuentes utilizadas y justificación
- **Google Trends** (explorer.google.com/trends), búsqueda web, Chile, últimos 5 años, todas las categorías.
  - Justificación: temporalidad y comparabilidad **relativa** entre términos cuando se consultan **juntos**.
- (Opcional) **Fuentes absolutas** (ventas, importaciones, precios): para complementar magnitud (no incluidas en esta entrega).

## 3. Proceso de limpieza (paso a paso)
1. **Diseño de consulta** (Google Trends):
   - Región: **Chile (CL)**.
   - Periodo: **últimos 5 años**.
   - Tipo de búsqueda: **web**.
   - Categoría: **todas** (ID=0).
   - Términos: **Pistacho**, **Nueces**, **Chocolate dubai** (en la **misma consulta**).
2. **Descarga CSV crudo** (botón descargar en Trends) → guardar como `datos_originales/google_trends_raw.csv`.
3. **Ejecución del script/notebook**:
   - Carga el CSV crudo.
   - Detecta y salta líneas de **metadatos** hasta la fila de encabezados (Week/Fecha).
   - Renombra la columna temporal a `date` (ISO).
   - Localiza columnas de los tres términos aunque vengan con sufijos (ej.: "Pistacho: (Chile)").
   - Convierte a numérico, **rellena vacíos con 0** (para que no queden NA).
   - Reordena a formato **ancho** (una columna por término).
   - Guarda en `base_limpia_trends.csv`.
4. **Control de calidad**:
   - Valores 0–100 dentro de rango.
   - Sin duplicados por fecha.
   - `Chocolate dubai` muestra 0 hasta 2024 (término emergente).
5. **Documentación**:
   - **Ficha técnica** con variables y definiciones.
   - **README** (este archivo) con proceso, decisiones, preguntas y reproducibilidad.

## 4. Herramientas
- Python 3 + **pandas**
- Jupyter/Google Colab
- VS Code + Git + GitHub

## 5. Preguntas que se pueden responder
1. ¿Cuándo ocurre el **pico** de interés del término **Chocolate dubai**?
2. ¿Cómo evoluciona **Pistacho** respecto de **Nueces** a nivel **anual**?
3. ¿Qué término muestra mayor **estacionalidad** al comparar sus medias mensuales/anuales?

## 6. Consideraciones críticas (feedback docente)
- **Relativo, no absoluto:** el 100 es el **pico** del periodo por término **en esta misma gráfica/consulta**.
- Comparar **siempre** en la **misma consulta** (misma categoría y tipo de búsqueda).  
- Si Trends marca “**no comparable**”, homologa tipo/categoría y reintenta.  
- Examina **interés por región** y **términos relacionados** para orientar hipótesis sobre consumo.

## 7. Reproducibilidad (cómo correrlo)
**Opción A (VS Code local):**
1) Coloca `google_trends_raw.csv` en `datos_originales/`  
2) Abre `script/cleaning_and_eda.ipynb` y ejecuta las celdas  
3) Revisa `base_limpia_trends.csv` en la carpeta del proyecto

**Opción B (Google Colab):**
1) Sube `google_trends_raw.csv` y el notebook a Colab  
2) Ajusta rutas si es necesario  
3) Ejecuta y descarga el CSV limpio

## 8. Licencias y ética
- Respeta Términos de uso de Google.
- Credita las fuentes con enlaces y fechas.
- No interpretes el índice 0–100 como cantidad de personas.

*Última actualización:* 2025-09-26