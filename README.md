# 📊 ConnectaTel - Análisis de Clientes y Comportamiento de Uso

## Descripción del proyecto

Este proyecto realiza un análisis exploratorio y de calidad de datos para ConnectaTel, una empresa de telecomunicaciones en Latinoamérica.

El objetivo principal es comprender el comportamiento de los clientes mediante el análisis de sus planes contratados, características demográficas y patrones de uso de servicios de telefonía y mensajería. A partir de este análisis se busca identificar oportunidades para mejorar la retención de clientes, detectar anomalías en los datos y generar información útil para la toma de decisiones del negocio.

---

## Objetivos del análisis

- Explorar y comprender la estructura de los datasets.
- Identificar problemas de calidad de datos.
- Detectar valores faltantes, sentinels y registros inconsistentes.
- Limpiar y preparar los datos para análisis posteriores.
- Analizar el comportamiento de uso de los clientes.
- Construir métricas agregadas por usuario.
- Generar estadísticas descriptivas sobre consumo y características demográficas.
- Visualizar distribuciones y detectar posibles patrones de comportamiento.

---

## Datasets utilizados

El proyecto utiliza tres conjuntos de datos:

### 1. `plans.csv`
Información de los planes disponibles.

Variables principales:
- Nombre del plan
- Mensajes incluidos
- Minutos incluidos
- GB incluidos
- Pago mensual
- Costos por excedentes

### 2. `users_latam.csv`
Información de los clientes.

Variables principales:
- ID de usuario
- Nombre y apellido
- Edad
- Ciudad
- Fecha de registro
- Plan contratado
- Fecha de cancelación (churn)

### 3. `usage.csv`
Historial de uso de los servicios.

Variables principales:
- ID de evento
- ID de usuario
- Tipo de evento (`call` o `text`)
- Fecha
- Duración de llamadas
- Longitud de mensajes

Todos los datos corresponden a registros disponibles hasta el año 2024.
---

## Etapas del análisis

### 1. Carga y exploración inicial

- Importación de librerías (`pandas`, `numpy`, `matplotlib`, `seaborn`).
- Carga de los datasets.
- Revisión de dimensiones, columnas y tipos de datos.
- Exploración preliminar mediante `.head()` e `.info()`.

### 2. Evaluación de calidad de datos

- Identificación de valores nulos.
- Cálculo de proporciones de datos faltantes.
- Detección de sentinels y valores inválidos.
- Revisión de estadísticas descriptivas.
- Exploración de variables categóricas y numéricas.

### 3. Limpieza de datos

Se realizaron las siguientes correcciones:

- Reemplazo del sentinel `-999` en la variable edad por la mediana.
- Conversión de `"?"` a valores nulos en la variable ciudad.
- Conversión de columnas de fecha al formato datetime.
- Identificación y eliminación lógica de fechas fuera del rango esperado.
- Validación del comportamiento de los valores faltantes en variables de uso.

### 4. Construcción de métricas por usuario

Se generaron indicadores agregados por cliente:

- Cantidad total de mensajes enviados.
- Cantidad total de llamadas realizadas.
- Total de minutos consumidos en llamadas.

Posteriormente estas métricas fueron integradas con la información de clientes.

### 5. Estadística descriptiva

Se analizaron:

- Edad de los usuarios.
- Cantidad de mensajes.
- Cantidad de llamadas.
- Minutos consumidos.
- Distribución de usuarios por tipo de plan.

### 6. Visualización de datos

Se construyeron gráficos para:

- Distribución de edades.
- Distribución de mensajes.
- Distribución de llamadas.
- Distribución de minutos consumidos.
- Comparaciones entre planes Básico y Premium.

Estas visualizaciones permiten identificar patrones de comportamiento y posibles valores atípicos.

---

## Tecnologías utilizadas

- Python 3
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook / Google Colab

---

## Cómo ejecutar el proyecto

### Opción 1: Google Colab

1. Descarga el notebook y los archivos CSV.
2. Abre Google Colab.
3. Selecciona **Archivo → Subir notebook**.
4. Carga el archivo `.ipynb`.
5. Sube los datasets al entorno de Colab.
6. Ajusta las rutas de los archivos si es necesario.
7. Ejecuta las celdas en orden.

### Opción 2: Jupyter Notebook

1. Clona este repositorio:

```bash
git clone https://github.com/tu-usuario/connectatel-analysis.git
```

2. Instala las dependencias:

```bash
pip install pandas numpy matplotlib seaborn
```

3. Inicia Jupyter:

```bash
jupyter notebook
```

4. Abre el notebook y ejecuta todas las celdas.

---

## Guía de reproducción

Para reproducir completamente el análisis:

1. Descargar o clonar el repositorio.
2. Colocar los archivos:
   - `plans.csv`
   - `users_latam.csv`
   - `usage.csv`

   dentro de la carpeta de datos correspondiente.

3. Ejecutar el notebook desde la primera celda.
4. Verificar que las rutas de los archivos coincidan con la estructura local.
5. Ejecutar las secciones en el siguiente orden:

   - Carga de datos
   - Exploración inicial
   - Calidad de datos
   - Limpieza
   - Agregaciones por usuario
   - Estadística descriptiva
   - Visualizaciones

6. Revisar los resultados e insights documentados en cada sección.

---

## Resultados principales

- Se identificaron valores sentinels e inconsistencias en variables demográficas.
- Se detectaron registros con fechas fuera del rango esperado.
- Se comprobó que algunos valores nulos dependen del tipo de evento registrado y forman parte del comportamiento esperado de los datos.
- Se construyeron métricas agregadas que permiten analizar el consumo de los usuarios de manera individual.
- Se generó una base limpia y estructurada para análisis avanzados de segmentación, churn y comportamiento de clientes.

---

## Autor

Andrea Saldivar

Proyecto académico de análisis exploratorio y limpieza de datos para ConnectaTel.
