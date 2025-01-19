# UCI_PySpark
# Proyecto ETL con PySpark

## **Descripción del proyecto**
El objetivo de este proyecto es desarrollar un pipeline ETL (Extract, Transform, Load) utilizando PySpark para procesar y analizar datos transaccionales de un comercio minorista en línea. Este pipeline demostrará la capacidad de manejar grandes volúmenes de datos, garantizar su calidad, y extraer información valiosa para la toma de decisiones empresariales.

---

## **Objetivos del proyecto**

1. **Automatizar el flujo de datos**: Diseñar y construir un pipeline ETL eficiente que:
   - Extraiga datos desde fuentes en bruto en formatos CSV, JSON o Parquet.
   - Transforme los datos para su limpieza, enriquecimiento y agregación.
   - Cargue los datos transformados en un formato optimizado (Parquet) listo para consultas y análisis.

2. **Garantizar calidad y consistencia de datos**:
   - Detectar y eliminar valores nulos o duplicados.
   - Corregir inconsistencias en los datos.
   - Enriquecer los datos generando columnas adicionales como categorías o fechas derivadas.

3. **Proporcionar insights clave**:
   - Análisis de ventas totales por país, producto y periodo.
   - Identificar los productos más vendidos y su impacto en los ingresos.
   - Analizar el comportamiento de compra de los clientes por regiones.

4. **Optimizar almacenamiento y rendimiento**:
   - Usar formatos de almacenamiento como Parquet para mejorar el rendimiento en consultas y reducir el espacio requerido.
   - Implementar particionamiento basado en columnas como fechas o regiones para escalar el pipeline.

5. **Escalabilidad y portabilidad**:
   - Diseñar un pipeline capaz de manejar grandes volúmenes de datos.
   - Garantizar que el pipeline sea fácilmente desplegable en entornos locales o en la nube (AWS S3, EMR).

---

## **Estructura del proyecto**

```
etl_project/
├── data/          # Datos de entrada (ejemplos y datasets brutos)
├── scripts/       # Scripts principales de PySpark para ETL
├── docs/          # Documentación adicional del proyecto
├── notebooks/     # Exploraciones y prototipos en Jupyter Notebook
├── output/        # Datos procesados y optimizados
└── README.md      # Descripción general del proyecto
```

---

## **Dataset utilizado**

**Nombre**: Online Retail Dataset (UCI)  
**Descripción**: Datos de transacciones de un comercio minorista en línea del Reino Unido entre 2010 y 2011.  

**Columnas clave**:
- `InvoiceNo`: Número de factura.
- `StockCode`: Código del producto.
- `Description`: Descripción del producto.
- `Quantity`: Cantidad comprada.
- `InvoiceDate`: Fecha de la factura.
- `UnitPrice`: Precio unitario.
- `CustomerID`: ID del cliente.
- `Country`: País del cliente.

**Fuente**: [Online Retail Dataset - UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Online+Retail)

---

## **Pasos del Pipeline ETL**

1. **Extract (Extracción)**:
   - Leer los datos desde archivos en formato CSV.
   - Manejar grandes volúmenes de datos simulando la extracción desde un sistema de almacenamiento (por ejemplo, AWS S3).

2. **Transform (Transformación)**:
   - **Limpieza de datos**:
     - Filtrar valores nulos, duplicados y datos incorrectos.
     - Asegurar que las columnas numéricas tengan valores positivos.
   - **Enriquecimiento de datos**:
     - Crear columnas derivadas como el mes y el año a partir de la fecha de la factura.
     - Categorización de productos por su contribución al ingreso total.
   - **Agregación**:
     - Calcular ventas totales por país, producto y periodo de tiempo.

3. **Load (Carga)**:
   - Guardar los datos procesados en formato Parquet optimizado.
   - Implementar particionamiento basado en columnas clave como `Country` y `Year` para consultas eficientes.

---

## **Resultados esperados**

1. **Datos transformados**:
   - Un dataset limpio y optimizado, almacenado en formato Parquet.
   - Datos organizados y particionados para consultas y análisis eficientes.

2. **Visualizaciones**:
   - Gráficos que muestren:
     - Ventas totales por país y mes.
     - Productos más vendidos y su impacto en los ingresos.
     - Comparativas de ingresos entre diferentes periodos.

3. **Documentación completa**:
   - README detallado con instrucciones sobre cómo reproducir el pipeline.
   - Notebooks que exploren el dataset y muestren insights clave.

---

## **Tecnologías utilizadas**
- **Lenguajes**: Python (PySpark)
- **Almacenamiento**: CSV, Parquet
- **Procesamiento**: Apache Spark
- **Visualización**: Power BI o Tableau
- **Cloud (opcional)**: AWS S3, AWS EMR

---

## **Instrucciones para ejecutar**
1. **Requisitos previos**:
   - Instalar PySpark: `pip install pyspark`
   - Descargar el dataset y colocarlo en la carpeta `data/`.

2. **Ejecutar el script ETL**:
   - Ejecutar: `spark-submit scripts/etl_pipeline.py`

3. **Visualizar resultados**:
   - Abrir los datos procesados desde la carpeta `output/` y cargar en la herramienta de visualización.

---

## **Contribuciones**
Si deseas contribuir a este proyecto, puedes crear un Pull Request o abrir un Issue con tus sugerencias.

---

**Autor**: Jose Manuel Ruz  
**GitHub**: jxseruzm

