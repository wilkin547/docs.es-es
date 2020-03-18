---
title: Carga de datos de entrenamiento para el Generador de modelos
description: Obtenga información sobre cómo cargar datos de entrenamiento desde una base de datos de SQL Server o un archivo para su uso en uno de los escenarios del Generador de modelos para ML.NET.
ms.date: 10/29/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to, mlnet-tooling
ms.openlocfilehash: 23de2d06090f4c1eaa2c79178ba4c346698d45e1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "78849164"
---
# <a name="load-training-data-into-model-builder"></a>Carga de datos de entrenamiento en el Generador de modelos

Obtenga información sobre cómo cargar los conjuntos de datos de entrenamiento desde un archivo o una base de datos de SQL Server para su uso en uno de los escenarios del Generador de modelos para ML.NET. Los escenarios del generador de modelos pueden usar bases de datos de SQL Server, archivos de imagen y formatos de archivo CSV o TSV como datos de entrenamiento.

## <a name="training-dataset-limitations-in-model-builder"></a>Limitaciones de los conjuntos de datos de entrenamiento en el Generador de modelos

El Generador de modelos limita la cantidad y el tipo de datos que puede usar para los modelos de entrenamiento:

- Datos de SQL Server: 100.000 filas
- Archivos CSV y TSV: sin límite de tamaño
- Imágenes: solo PNG y JPG.

## <a name="model-builder-scenarios"></a>Escenarios del Generador de modelos

El Generador de modelos ayuda a crear modelos para los siguientes escenarios de aprendizaje automático:

- Análisis de opinión (clasificación binaria): los datos textuales se clasifican en dos categorías.
- Clasificación de incidencias (clasificación multiclase): los datos textuales se clasifican en tres o más categorías.
- Predicción de precios (regresión): se predice un valor numérico.
- Clasificación de imágenes (aprendizaje profundo): categorización de imágenes en función de características.
- Escenario personalizado: cree escenarios personalizados a partir de los datos mediante la regresión, la clasificación y otras tareas.

En este artículo se describen los escenarios de clasificación y regresión con datos textuales o numéricos, y escenarios de clasificación de imágenes.

## <a name="load-text-or-numeric-data-from-a-file"></a>Carga de texto o datos numéricos desde un archivo

Puede cargar texto o datos numéricos desde un archivo al Generador de modelos. Acepta formatos de archivo delimitados por comas (CSV) o delimitado por tabulaciones(TSV).

1. En el paso de datos del Generador de modelos, seleccione **Archivo** en la lista desplegable de origen de datos.
2. Seleccione el botón situado junto al cuadro de texto **Seleccionar un archivo** y use el Explorador de archivos para examinar y seleccionar el archivo de datos.
3. Elija una categoría en el menú desplegable **Column to Predict (Label)** (Columna para la predicción [etiqueta]).
4. En la lista desplegable **Input Columns (Features)** (Columnas de entrada (características)), confirme que las columnas de datos que quiere incluir están activadas.

Ha terminado de configurar el archivo de origen de datos para el Generador de modelos. Seleccione el vínculo **Entrenar** para ir al paso siguiente en el Generador de modelos.

## <a name="load-data-from-a-sql-server-database"></a>Carga de datos desde una base de datos de SQL Server

El Generador de modelos admite la carga de datos desde bases de datos de SQL Server locales y remotas.

Para cargar datos desde una base de datos de SQL Server al Generador de módulos:

1. En el paso de datos del Generador de modelos, seleccione **SQL Server** en la lista desplegable de origen de datos.
1. Seleccione el botón situado junto al cuadro de texto **Conectarse a la base de datos SQL Server**.
    1. En el cuadro de diálogo **Elegir datos**, seleccione **Archivo de base de datos de Microsoft SQL Server**.
    1. Desactive la casilla **Usar siempre esta selección** y seleccione **Continuar**.
    1. En el cuadro de diálogo **Propiedades de conexión**, seleccione **Examinar** y después el archivo .MDF descargado.
    1. Seleccione **Aceptar**.
1. Elija el nombre del conjunto de datos en la lista desplegable **Table Name** (Nombre de la tabla).
1. En la lista desplegable **Column to Predict (Label)** (Columna para la predicción [etiqueta]), elija la categoría de datos en la que quiere crear una predicción.
1. En la lista desplegable **Input Columns (Features)** (Columnas de entrada (características)), confirme que las columnas que quiere incluir están activadas.

Ha terminado de configurar el archivo de origen de datos para el Generador de modelos. Seleccione el vínculo **Entrenar** para ir al paso siguiente en el Generador de modelos.

## <a name="set-up-image-data-files"></a>Configuración de archivos de datos de imagen

El Generador de modelos espera que los datos de imagen sean archivos JPG o PNG organizados en carpetas que se corresponden con las categorías de la clasificación.

Para cargar imágenes al Generador de modelos, proporcione la ruta de acceso a un único directorio de nivel superior:

- Este directorio de nivel superior contiene una subcarpeta para cada una de las categorías que se van a predecir.
- Cada subcarpeta contiene los archivos de imagen que pertenecen a su categoría.

En la estructura de carpetas que se muestra a continuación, el directorio de nivel superior es *flower_photos*. Hay cinco subdirectorios que se corresponden con las categorías que quiere predecir: daisy, dandelion, roses, sunflowers y tulips. Cada uno de estos subdirectorios contiene imágenes que pertenecen a su categoría correspondiente.

```text
\---flower_photos
    +---daisy
    |       100080576_f52e8ee070_n.jpg
    |       102841525_bd6628ae3c.jpg
    |       105806915_a9c13e2106_n.jpg
    |
    +---dandelion
    |       10443973_aeb97513fc_m.jpg
    |       10683189_bd6e371b97.jpg
    |       10919961_0af657c4e8.jpg
    |
    +---roses
    |       102501987_3cdb8e5394_n.jpg
    |       110472418_87b6a3aa98_m.jpg
    |       118974357_0faa23cce9_n.jpg
    |
    +---sunflowers
    |       127192624_afa3d9cb84.jpg
    |       145303599_2627e23815_n.jpg
    |       147804446_ef9244c8ce_m.jpg
    |
    \---tulips
            100930342_92e8746431_n.jpg
            107693873_86021ac4ea_n.jpg
            10791227_7168491604.jpg
```

## <a name="next-steps"></a>Pasos siguientes

Siga estos tutoriales para crear aplicaciones de aprendizaje automático con el Generador de modelos:

- [Predicción de precios mediante regresión](../tutorials/predict-prices-with-model-builder.md)
- [Análisis de sentimiento en una aplicación web mediante la clasificación binaria](../tutorials/sentiment-analysis-model-builder.md )

Si va a entrenar un modelo mediante código, [aprenda a cargar datos mediante la API de ML.NET](load-data-ml-net.md).
