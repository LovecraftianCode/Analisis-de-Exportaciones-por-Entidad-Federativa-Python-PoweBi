# Análisis de Exportaciones por Entidad Federativa (INEGI)

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)

> **Análisis de exportaciones anuales por entidad federativa y subsector económico** - Datos oficiales del INEGI (2007-2025)

<img width="1196" height="672" alt="Dashboard PowerBi" src="https://github.com/user-attachments/assets/3e9c1d61-811c-4f15-b2e7-cce3efff0b05" />

## Tabla de Contenidos

- [Sobre este proyecto](#sobre-este-proyecto)
- [Características principales](#características-principales)
- [Estructura del dataset](#estructura-del-dataset)
- [Hallazgos clave](#hallazgos-clave)
  - [Tendencia de confidencialidad](#tendencia-de-confidencialidad)
  - [Distribución geográfica](#distribución-geográfica)
  - [Concentración sectorial](#concentración-sectorial)
- [Tecnologías utilizadas](#tecnologías-utilizadas)
- [Análisis exploratorio](#análisis-exploratorio)
- [Archivos incluidos](#archivos-incluidos)
- [Autor](#autor)

## Sobre este proyecto

Este proyecto consiste en el **análisis exploratorio de datos** de las exportaciones anuales por entidad federativa y subsector económico, utilizando datos oficiales del **INEGI** para el período 2007-2025.

El objetivo principal es:

- **Identificar patrones de exportación** por estado y sector económico
- **Analizar la disponibilidad de la información** (Disponible vs Confidencial)
- **Determinar la concentración** geográfica y sectorial de las exportaciones
- **Crear un dashboard interactivo** en Power BI para visualización

Los datos fueron procesados y consolidados utilizando **Python** y **pandas**, con visualizaciones generadas en **Matplotlib** y un dashboard interactivo en **Power BI**.

## Características principales

| Característica | Descripción |
|----------------|-------------|
| **Procesamiento de datos** | Limpieza, consolidación y transformación con pandas |
| **Análisis de confidencialidad** | Comparación Disponible vs Confidencial por año |
| **Distribución geográfica** | Exportaciones totales por entidad federativa |
| **Concentración sectorial** | Top sectores económicos con mayor exportación |
| **Visualizaciones** | Gráficas de barras, líneas y pastel con Matplotlib |
| **Dashboard interactivo** | Power BI con filtros por año, estado y sector |
| **Documentación completa** | README, diccionario de datos y análisis detallado |

## Estructura del dataset

### Columnas principales

| Columna | Descripción | Tipo |
|---------|-------------|------|
| `PROD_EST` | Nombre del proyecto estadístico | Texto |
| `COBERTURA` | Área geográfica (Estatal) | Texto |
| `ANIO` | Año de referencia | Entero |
| `CVE_ENT` | Clave de entidad federativa | Texto |
| `NOM_ENTIDAD` | Nombre de la entidad | Texto |
| `CODIGO_SCIAN` | Clave SCIAN del subsector | Texto |
| `DESCRIPCION` | Descripción del subsector económico | Texto |
| `VAL_USD` | Valor en miles de dólares (FOB) | Flotante |
| `ESTATUS_CIFRA` | Estatus de la cifra | Texto |
| `ESTATUS` | Estatus definitivo/preliminar | Texto |

### Resumen de datos

```bash
Total de registros: 16,416
Período: 2007 - 2025 (19 años)
Cobertura: 32 entidades federativas
Registros sin VAL_USD: 7,934
Registros con VAL_USD: 8,482
```

## Hallazgos clave

### Tendencia de confidencialidad

La proporción de registros confidenciales ha mostrado una tendencia decreciente:

| Indicador| Valor |
|----------|-------|
| Pico máximo de confidencialidad |	27.90% (2012) |
| Pico mínimo de confidencialidad	| 19.84% (2024) |
| Reducción total de informacion privada| 8.06 puntos porcentuales |

<img width="1102" height="552" alt="Tendencia Confidencialidad" src="https://github.com/user-attachments/assets/ef5fd0d7-1df4-425c-bc1e-08b6014e6717" />
 Los datos son cada vez más accesibles para el análisis público, lo que facilita el estudio de las exportaciones mexicanas.

### Distribución geográfica

Las exportaciones están altamente concentradas en pocos estados:

```bash
Total global de exportaciones: 7,149.48 Millones USD
Top 3 estados concentran el 34.84% de las exportaciones totales
```

#### Top 3 estados exportadores

| Posición | Estado |	Exportaciones (M USD) |	Participación |
|----------|--------|-----------------------|---------------|
| 1 | Chihuahua | 972.43 |	13.60% |
| 2 |	Coahuila de Zaragoza | 762.51 |	10.67% |
| 3 |	Baja California |	755.98 | 10.57% |

## Concentración sectorial
Top 5 sectores concentran el 72.67% de las exportaciones totales

#### Top 5 sectores exportadores

| Posición |	Sector |	Exportaciones (M USD) |	Participación |
|----------|---------|------------------------|---------------|
| 1 |	Fabricación de equipo de transporte |	2,553.36 | 35.71% |
| 2 |	Fabricación de equipo de computación, comunicación, medición y de otros equipos, componentes y accesorios electrónicos | 1,379.63 |	19.30% |
| 3 |	Extracción de petróleo y gas | 555.95 |	7.78% |
| 4 |	Fabricación de accesorios, aparatos eléctricos y equipo de generación de energía eléctrica | 421.95 |	5.90% |
| 5 |	Otras industrias manufactureras |	284.39 | 3.98% |

## Tecnologías utilizadas

| Tecnología | Uso |
|------------|-----|
| Python 3.12 |	Procesamiento y análisis de datos |
| Pandas | Manipulación y consolidación de datos |
| NumPy |	Operaciones numéricas y cálculos |
| Matplotlib | Visualizaciones y gráficas |
| Jupyter Notebook | Entorno de desarrollo interactivo |
| Power BI | Dashboard interactivo |
| Git & GitHub | Control de versiones y despliegue |

## Análisis exploratorio

### Resumen por año

```python
================================================================
RESUMEN COMPLETO POR AÑO
================================================================
 AÑO  TOTAL_FILAS  REGISTROS_CON_VALOR  REGISTROS_SIN_VALOR
2007          864                  389                  475
2008          864                  412                  452
2009          864                  420                  444
2010          864                  406                  458
2011          864                  404                  460
2012          864                  398                  466
2013          864                  419                  445
2014          864                  417                  447
2015          864                  417                  447
2016          864                  412                  452
2017          864                  430                  434
2018          864                  501                  363
2019          864                  487                  377
2020          864                  498                  366
2021          864                  505                  359
2022          864                  495                  369
2023          864                  492                  372
2024          864                  505                  359
2025          864                  475                  389
```

### Verificación de datos

```python
================================================================
COMPARACION DIRECTA
================================================================
Registros sin VAL_USD: 7934
Registros con ESTATUS_CIFRA != 'Disponible': 7934
Diferencia: 0
```

### Comparación Disponible vs Confidencial

```python
================================================================
COMPARACION: DISPONIBLE VS CONFIDENCIAL POR AÑO
================================================================
      Confidencial  Disponible  Total  %_Confidencial
ANIO                                                 
2007           134         389    523           25.62
2008           126         412    538           23.42
2009           127         420    547           23.22
2010           143         406    549           26.05
2011           148         404    552           26.81
2012           154         398    552           27.90
2013           119         419    538           22.12
2014           126         417    543           23.20
2015           128         417    545           23.49
2016           134         412    546           24.54
2017           119         430    549           21.68
2018           149         501    650           22.92
2019           155         487    642           24.14
2020           147         498    645           22.79
2021           133         505    638           20.85
2022           138         495    633           21.80
2023           142         492    634           22.40
2024           125         505    630           19.84
2025           155         475    630           24.60
```

## Archivos incluidos

| Archivo |	Descripción |
|---------|-------------|
| eef_consolidado_final.csv |	Dataset limpio y consolidado con nombres de estados y sectores |
| diccionario_datos.csv |	Descripción detallada de cada columna |
| resumen_anios.csv |	Conteo de registros por año |
| estadisticas_anios.csv |	Estadísticas de VAL_USD por año |
| exportaciones_por_estado.csv |	Exportaciones totales por entidad federativa |
| exportaciones_por_sector.csv |	Exportaciones totales por sector económico |
| comparacion_disponible_confidencial.csv |	Comparación por año de registros disponibles vs confidenciales |
| Eportaciones-por-entidad-federativa.ipynb |	Jupyter Notebook con todo el análisis |
| Exportaciones por entidad federativa.pbix |	Dashboard powerBi |

## Dependencias
```bash
pandas==2.2.0
numpy==2.0.0
matplotlib==3.8.0
jupyter==1.0.0
```

Autor
Humberto Isaac Padilla Contreras
- GitHub: <a href="https://github.com/LovecraftianCode">@LovecraftianCode<a/>
- LinkedIn: <a href="https://www.linkedin.com/in/humberto-isaac-padilla-contreras-3527aa3b7" target="_blank">Humberto Isaac Padilla Contreras </a>
