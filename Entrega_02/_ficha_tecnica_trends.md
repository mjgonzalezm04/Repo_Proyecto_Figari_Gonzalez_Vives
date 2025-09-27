#Ficha técnica de la base de datos limpia

#1) Fuente de los datos
-Google Trends (explorer.google.com/trends). mediante la descarga directa de la interfaz web. Serie semanal de Interés de búsqueda (0–100)por término, para Chile, en los últimos 5 años.  
- Términos incluidos en la misma consulta: *Pistacho*, *Nueces* y *Chocolate dubai*.  

#2) Metodología de construcción de la base
- Extracción de Google Trends, que sea en Chile, en los ultimos 5 años. 
- Selección de los tres términos para asegurar comparabilidad (escala relativa común).  
- Exportación del CSV original desde Google Trends.  
- Limpieza en Python/Pandas:  
  - Conversión de fechas  
  - Reestructuración en formato largo (una fila por fecha y término).  
- Validación de que los valores en el rango 0–100 y que no haya duplicados.  

#3) Alcance de los datos
-desde el 15 de septiembre de 2019 hasta el 15 de septiembre de 2024.  
-A nivel nacional  
-Interés de búsqueda relativo semanal por término en Google.  

#4) Características de los datos
- valores de 0 a 100, donde 100 representa punto máximo de búsquedas en el periodo de 5 años en Chile  
- Los datos son relativos, no representan número absoluto de búsquedas.  
- La comparabilidad es válida porque los términos se consultaron en la misma búsqueda y categoría. 

#5) Variables incorporadas
- fecha 
- pais
- termino de busqueda
- interes (indice de 0-100) relativo


#6) Observaciones
- El término *Chocolate dubai* aparece con valores 0 hasta 2024, cuando surge como tendencia, hay un peak muy marcado.   
- Los términos *Nueces* y *Pistacho* están presentes durante todo el periodo, siendo *Nueces* el más estable y con valores más altos. 