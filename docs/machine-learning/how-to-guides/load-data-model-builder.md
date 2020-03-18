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
# <a name="load-training-data-into-model-builder"></a><span data-ttu-id="d1ba3-103">Carga de datos de entrenamiento en el Generador de modelos</span><span class="sxs-lookup"><span data-stu-id="d1ba3-103">Load training data into Model Builder</span></span>

<span data-ttu-id="d1ba3-104">Obtenga información sobre cómo cargar los conjuntos de datos de entrenamiento desde un archivo o una base de datos de SQL Server para su uso en uno de los escenarios del Generador de modelos para ML.NET.</span><span class="sxs-lookup"><span data-stu-id="d1ba3-104">Learn how to load your training datasets from a file or a SQL Server database for use in one of the Model Builder scenarios for ML.NET.</span></span> <span data-ttu-id="d1ba3-105">Los escenarios del generador de modelos pueden usar bases de datos de SQL Server, archivos de imagen y formatos de archivo CSV o TSV como datos de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="d1ba3-105">Model Builder scenarios can use SQL Server databases, image files, and CSV or TSV file formats as training data.</span></span>

## <a name="training-dataset-limitations-in-model-builder"></a><span data-ttu-id="d1ba3-106">Limitaciones de los conjuntos de datos de entrenamiento en el Generador de modelos</span><span class="sxs-lookup"><span data-stu-id="d1ba3-106">Training dataset limitations in Model Builder</span></span>

<span data-ttu-id="d1ba3-107">El Generador de modelos limita la cantidad y el tipo de datos que puede usar para los modelos de entrenamiento:</span><span class="sxs-lookup"><span data-stu-id="d1ba3-107">Model Builder limits the amount and type of data you can use for training models:</span></span>

- <span data-ttu-id="d1ba3-108">Datos de SQL Server: 100.000 filas</span><span class="sxs-lookup"><span data-stu-id="d1ba3-108">SQL Server data: 100,000 rows</span></span>
- <span data-ttu-id="d1ba3-109">Archivos CSV y TSV: sin límite de tamaño</span><span class="sxs-lookup"><span data-stu-id="d1ba3-109">CSV and TSV files: No size limit</span></span>
- <span data-ttu-id="d1ba3-110">Imágenes: solo PNG y JPG.</span><span class="sxs-lookup"><span data-stu-id="d1ba3-110">Images: PNG and JPG only.</span></span>

## <a name="model-builder-scenarios"></a><span data-ttu-id="d1ba3-111">Escenarios del Generador de modelos</span><span class="sxs-lookup"><span data-stu-id="d1ba3-111">Model Builder scenarios</span></span>

<span data-ttu-id="d1ba3-112">El Generador de modelos ayuda a crear modelos para los siguientes escenarios de aprendizaje automático:</span><span class="sxs-lookup"><span data-stu-id="d1ba3-112">Model Builder helps you create models for the following machine learning scenarios:</span></span>

- <span data-ttu-id="d1ba3-113">Análisis de opinión (clasificación binaria): los datos textuales se clasifican en dos categorías.</span><span class="sxs-lookup"><span data-stu-id="d1ba3-113">Sentiment analysis (binary classification): Classify textual data into two categories.</span></span>
- <span data-ttu-id="d1ba3-114">Clasificación de incidencias (clasificación multiclase): los datos textuales se clasifican en tres o más categorías.</span><span class="sxs-lookup"><span data-stu-id="d1ba3-114">Issue classification (multiclass classification): Classify textual data into 3 or more categories.</span></span>
- <span data-ttu-id="d1ba3-115">Predicción de precios (regresión): se predice un valor numérico.</span><span class="sxs-lookup"><span data-stu-id="d1ba3-115">Price prediction (regression): Predict a numeric value.</span></span>
- <span data-ttu-id="d1ba3-116">Clasificación de imágenes (aprendizaje profundo): categorización de imágenes en función de características.</span><span class="sxs-lookup"><span data-stu-id="d1ba3-116">Image classification (deep learning): Categorize images based on characteristics.</span></span>
- <span data-ttu-id="d1ba3-117">Escenario personalizado: cree escenarios personalizados a partir de los datos mediante la regresión, la clasificación y otras tareas.</span><span class="sxs-lookup"><span data-stu-id="d1ba3-117">Custom scenario: Build custom scenarios from your data using regression, classification, and other tasks.</span></span>

<span data-ttu-id="d1ba3-118">En este artículo se describen los escenarios de clasificación y regresión con datos textuales o numéricos, y escenarios de clasificación de imágenes.</span><span class="sxs-lookup"><span data-stu-id="d1ba3-118">This article covers classification and regression scenarios with textual or numerical data, and image classification scenarios.</span></span>

## <a name="load-text-or-numeric-data-from-a-file"></a><span data-ttu-id="d1ba3-119">Carga de texto o datos numéricos desde un archivo</span><span class="sxs-lookup"><span data-stu-id="d1ba3-119">Load text or numeric data from a file</span></span>

<span data-ttu-id="d1ba3-120">Puede cargar texto o datos numéricos desde un archivo al Generador de modelos.</span><span class="sxs-lookup"><span data-stu-id="d1ba3-120">You can load text or numeric data from a file into Model Builder.</span></span> <span data-ttu-id="d1ba3-121">Acepta formatos de archivo delimitados por comas (CSV) o delimitado por tabulaciones(TSV).</span><span class="sxs-lookup"><span data-stu-id="d1ba3-121">It accepts comma-delimited (CSV) or tab-delimited (TSV) file formats.</span></span>

1. <span data-ttu-id="d1ba3-122">En el paso de datos del Generador de modelos, seleccione **Archivo** en la lista desplegable de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="d1ba3-122">In the data step of Model Builder, select **File** from the data source dropdown.</span></span>
2. <span data-ttu-id="d1ba3-123">Seleccione el botón situado junto al cuadro de texto **Seleccionar un archivo** y use el Explorador de archivos para examinar y seleccionar el archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="d1ba3-123">Select the button next to the **Select a file** text box, and use File Explorer to browse and select the data file.</span></span>
3. <span data-ttu-id="d1ba3-124">Elija una categoría en el menú desplegable **Column to Predict (Label)** (Columna para la predicción [etiqueta]).</span><span class="sxs-lookup"><span data-stu-id="d1ba3-124">Choose a category in the **Column to Predict (Label)** dropdown.</span></span>
4. <span data-ttu-id="d1ba3-125">En la lista desplegable **Input Columns (Features)** (Columnas de entrada (características)), confirme que las columnas de datos que quiere incluir están activadas.</span><span class="sxs-lookup"><span data-stu-id="d1ba3-125">From the **Input Columns (Features)** dropdown, confirm the data columns you want to include are checked.</span></span>

<span data-ttu-id="d1ba3-126">Ha terminado de configurar el archivo de origen de datos para el Generador de modelos.</span><span class="sxs-lookup"><span data-stu-id="d1ba3-126">You're done setting up your data source file for Model Builder.</span></span> <span data-ttu-id="d1ba3-127">Seleccione el vínculo **Entrenar** para ir al paso siguiente en el Generador de modelos.</span><span class="sxs-lookup"><span data-stu-id="d1ba3-127">Select the **Train** link to move to the next step in Model Builder.</span></span>

## <a name="load-data-from-a-sql-server-database"></a><span data-ttu-id="d1ba3-128">Carga de datos desde una base de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="d1ba3-128">Load data from a SQL Server database</span></span>

<span data-ttu-id="d1ba3-129">El Generador de modelos admite la carga de datos desde bases de datos de SQL Server locales y remotas.</span><span class="sxs-lookup"><span data-stu-id="d1ba3-129">Model Builder supports loading data from local and remote SQL Server databases.</span></span>

<span data-ttu-id="d1ba3-130">Para cargar datos desde una base de datos de SQL Server al Generador de módulos:</span><span class="sxs-lookup"><span data-stu-id="d1ba3-130">To load data from a SQL Server database into Module Builder:</span></span>

1. <span data-ttu-id="d1ba3-131">En el paso de datos del Generador de modelos, seleccione **SQL Server** en la lista desplegable de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="d1ba3-131">In the data step of Model Builder, select **SQL Server** from the data source dropdown.</span></span>
1. <span data-ttu-id="d1ba3-132">Seleccione el botón situado junto al cuadro de texto **Conectarse a la base de datos SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="d1ba3-132">Select the button next to the **Connect to SQL Server database** text box.</span></span>
    1. <span data-ttu-id="d1ba3-133">En el cuadro de diálogo **Elegir datos**, seleccione **Archivo de base de datos de Microsoft SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="d1ba3-133">In the **Choose Data** dialog, select **Microsoft SQL Server Database File**.</span></span>
    1. <span data-ttu-id="d1ba3-134">Desactive la casilla **Usar siempre esta selección** y seleccione **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="d1ba3-134">Uncheck the **Always use this selection** checkbox and select **Continue**</span></span>
    1. <span data-ttu-id="d1ba3-135">En el cuadro de diálogo **Propiedades de conexión**, seleccione **Examinar** y después el archivo .MDF descargado.</span><span class="sxs-lookup"><span data-stu-id="d1ba3-135">In the **Connection Properties** dialog, select **Browse** and select the downloaded .MDF file.</span></span>
    1. <span data-ttu-id="d1ba3-136">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d1ba3-136">Select **OK**</span></span>
1. <span data-ttu-id="d1ba3-137">Elija el nombre del conjunto de datos en la lista desplegable **Table Name** (Nombre de la tabla).</span><span class="sxs-lookup"><span data-stu-id="d1ba3-137">Choose the dataset name from the **Table Name** dropdown.</span></span>
1. <span data-ttu-id="d1ba3-138">En la lista desplegable **Column to Predict (Label)** (Columna para la predicción [etiqueta]), elija la categoría de datos en la que quiere crear una predicción.</span><span class="sxs-lookup"><span data-stu-id="d1ba3-138">From the **Column to Predict (Label)** dropdown, choose the data category on which you want to make a prediction.</span></span>
1. <span data-ttu-id="d1ba3-139">En la lista desplegable **Input Columns (Features)** (Columnas de entrada (características)), confirme que las columnas que quiere incluir están activadas.</span><span class="sxs-lookup"><span data-stu-id="d1ba3-139">From the **Input Columns (Features)** dropdown, confirm the columns you want to include are checked.</span></span>

<span data-ttu-id="d1ba3-140">Ha terminado de configurar el archivo de origen de datos para el Generador de modelos.</span><span class="sxs-lookup"><span data-stu-id="d1ba3-140">You're done setting up your data source file for Model Builder.</span></span> <span data-ttu-id="d1ba3-141">Seleccione el vínculo **Entrenar** para ir al paso siguiente en el Generador de modelos.</span><span class="sxs-lookup"><span data-stu-id="d1ba3-141">Select the **Train** link to move to the next step in Model Builder.</span></span>

## <a name="set-up-image-data-files"></a><span data-ttu-id="d1ba3-142">Configuración de archivos de datos de imagen</span><span class="sxs-lookup"><span data-stu-id="d1ba3-142">Set up image data files</span></span>

<span data-ttu-id="d1ba3-143">El Generador de modelos espera que los datos de imagen sean archivos JPG o PNG organizados en carpetas que se corresponden con las categorías de la clasificación.</span><span class="sxs-lookup"><span data-stu-id="d1ba3-143">Model Builder expects image data to be JPG or PNG files organized in folders that correspond to the categories of the classification.</span></span>

<span data-ttu-id="d1ba3-144">Para cargar imágenes al Generador de modelos, proporcione la ruta de acceso a un único directorio de nivel superior:</span><span class="sxs-lookup"><span data-stu-id="d1ba3-144">To load images into Model Builder, provide the path to a single top-level directory:</span></span>

- <span data-ttu-id="d1ba3-145">Este directorio de nivel superior contiene una subcarpeta para cada una de las categorías que se van a predecir.</span><span class="sxs-lookup"><span data-stu-id="d1ba3-145">This top-level directory contains one subfolder for each of the categories to predict.</span></span>
- <span data-ttu-id="d1ba3-146">Cada subcarpeta contiene los archivos de imagen que pertenecen a su categoría.</span><span class="sxs-lookup"><span data-stu-id="d1ba3-146">Each subfolder contains the image files belonging to its category.</span></span>

<span data-ttu-id="d1ba3-147">En la estructura de carpetas que se muestra a continuación, el directorio de nivel superior es *flower_photos*.</span><span class="sxs-lookup"><span data-stu-id="d1ba3-147">In the folder structure illustrated below, the top-level directory is *flower_photos*.</span></span> <span data-ttu-id="d1ba3-148">Hay cinco subdirectorios que se corresponden con las categorías que quiere predecir: daisy, dandelion, roses, sunflowers y tulips.</span><span class="sxs-lookup"><span data-stu-id="d1ba3-148">There are five subdirectories corresponding to the categories you want to predict: daisy, dandelion, roses, sunflowers, and tulips.</span></span> <span data-ttu-id="d1ba3-149">Cada uno de estos subdirectorios contiene imágenes que pertenecen a su categoría correspondiente.</span><span class="sxs-lookup"><span data-stu-id="d1ba3-149">Each of these subdirectories contains images belonging to its respective category.</span></span>

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

## <a name="next-steps"></a><span data-ttu-id="d1ba3-150">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="d1ba3-150">Next steps</span></span>

<span data-ttu-id="d1ba3-151">Siga estos tutoriales para crear aplicaciones de aprendizaje automático con el Generador de modelos:</span><span class="sxs-lookup"><span data-stu-id="d1ba3-151">Follow these tutorials to build machine learning apps with Model Builder:</span></span>

- [<span data-ttu-id="d1ba3-152">Predicción de precios mediante regresión</span><span class="sxs-lookup"><span data-stu-id="d1ba3-152">Predict prices using regression</span></span>](../tutorials/predict-prices-with-model-builder.md)
- [<span data-ttu-id="d1ba3-153">Análisis de sentimiento en una aplicación web mediante la clasificación binaria</span><span class="sxs-lookup"><span data-stu-id="d1ba3-153">Analyze sentiment in a web application using binary classification</span></span>](../tutorials/sentiment-analysis-model-builder.md )

<span data-ttu-id="d1ba3-154">Si va a entrenar un modelo mediante código, [aprenda a cargar datos mediante la API de ML.NET](load-data-ml-net.md).</span><span class="sxs-lookup"><span data-stu-id="d1ba3-154">If you're training a model using code, [learn how to load data using the ML.NET API](load-data-ml-net.md).</span></span>
