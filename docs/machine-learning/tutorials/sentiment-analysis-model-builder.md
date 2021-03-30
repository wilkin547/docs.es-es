---
title: 'Tutorial: Análisis de sentimiento: clasificación binaria'
description: En este tutorial se muestra cómo crear una aplicación Razor Pages que clasifica los sentimientos de los comentarios del sitio web y toma las medidas oportunas. El clasificador binario de sentimientos usa el Generador de modelos en Visual Studio.
ms.date: 11/21/2019
author: luisquintanilla
ms.author: luquinta
ms.topic: tutorial
ms.custom: mvc,mlnet-tooling
ms.openlocfilehash: cb4f18ad9da2e57ee09598183a1226b20a1d7aec
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104874620"
---
# <a name="tutorial-analyze-sentiment-of-website-comments-in-a-web-application-using-mlnet-model-builder"></a><span data-ttu-id="bda72-104">Tutorial: Análisis del sentimiento de los comentarios del sitio web en una aplicación web con el Generador de modelos de ML.NET</span><span class="sxs-lookup"><span data-stu-id="bda72-104">Tutorial: Analyze sentiment of website comments in a web application using ML.NET Model Builder</span></span>

<span data-ttu-id="bda72-105">Aprenda a analizar la opinión de los comentarios en tiempo real dentro de una aplicación web.</span><span class="sxs-lookup"><span data-stu-id="bda72-105">Learn how to analyze sentiment from comments in real time inside a web application.</span></span>

<span data-ttu-id="bda72-106">En este tutorial se muestra cómo crear una aplicación Razor Pages de ASP.NET Core que clasifica las opiniones de los comentarios del sitio web en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="bda72-106">This tutorial shows you how to create an ASP.NET Core Razor Pages application that classifies sentiment from website comments in real time.</span></span>

<span data-ttu-id="bda72-107">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="bda72-107">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="bda72-108">Crear una aplicación Razor Pages de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="bda72-108">Create an ASP.NET Core Razor Pages application</span></span>
> - <span data-ttu-id="bda72-109">Preparar y entender los datos</span><span class="sxs-lookup"><span data-stu-id="bda72-109">Prepare and understand the data</span></span>
> - <span data-ttu-id="bda72-110">Elección de un escenario</span><span class="sxs-lookup"><span data-stu-id="bda72-110">Choose a scenario</span></span>
> - <span data-ttu-id="bda72-111">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="bda72-111">Load the data</span></span>
> - <span data-ttu-id="bda72-112">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="bda72-112">Train the model</span></span>
> - <span data-ttu-id="bda72-113">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="bda72-113">Evaluate the model</span></span>
> - <span data-ttu-id="bda72-114">Usar el modelo para las predicciones</span><span class="sxs-lookup"><span data-stu-id="bda72-114">Use the model for predictions</span></span>

> [!NOTE]
> <span data-ttu-id="bda72-115">De momento, el Generador de modelos se encuentra en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="bda72-115">Model Builder is currently in Preview.</span></span>

<span data-ttu-id="bda72-116">Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples).</span><span class="sxs-lookup"><span data-stu-id="bda72-116">You can find the source code for this tutorial at the [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples) repository.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="bda72-117">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="bda72-117">Pre-requisites</span></span>

<span data-ttu-id="bda72-118">Para obtener una lista de los requisitos previos e instrucciones de instalación, visite la [Guía de instalación del Generador de modelos](../how-to-guides/install-model-builder.md).</span><span class="sxs-lookup"><span data-stu-id="bda72-118">For a list of pre-requisites and installation instructions, visit the [Model Builder installation guide](../how-to-guides/install-model-builder.md).</span></span>

## <a name="create-a-razor-pages-application"></a><span data-ttu-id="bda72-119">Creación de una aplicación Razor Pages</span><span class="sxs-lookup"><span data-stu-id="bda72-119">Create a Razor Pages application</span></span>

1. <span data-ttu-id="bda72-120">Cree una **aplicación Razor Pages de ASP.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="bda72-120">Create a **ASP.NET Core Razor Pages Application**.</span></span>

    1. <span data-ttu-id="bda72-121">Abra Visual Studio y seleccione **Archivo > Nuevo > Proyecto** en la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="bda72-121">Open Visual Studio and select **File > New > Project** from the menu bar.</span></span>
    1. <span data-ttu-id="bda72-122">En el cuadro de diálogo Nuevo proyecto, seleccione el nodo **Visual C#** seguido del nodo **Web**.</span><span class="sxs-lookup"><span data-stu-id="bda72-122">In the New Project dialog, select the **Visual C#** node followed by the **Web** node.</span></span>
    1. <span data-ttu-id="bda72-123">Seleccione la plantilla de proyecto **Aplicación web de ASP.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="bda72-123">Then select the **ASP.NET Core Web Application** project template.</span></span>
    1. <span data-ttu-id="bda72-124">En el cuadro de texto **Nombre**, escriba "SentimentRazor".</span><span class="sxs-lookup"><span data-stu-id="bda72-124">In the **Name** text box, type "SentimentRazor".</span></span>
    1. <span data-ttu-id="bda72-125">Asegúrese de que **Colocar la solución y el proyecto en el mismo directorio** está **desactivado** (VS 2019) o que **Crear directorio para la solución** está **activado** (VS 2017).</span><span class="sxs-lookup"><span data-stu-id="bda72-125">Make sure **Place solution and project in the same directory** is **unchecked** (VS 2019), or **Create directory for solution** is **checked** (VS 2017).</span></span>
    1. <span data-ttu-id="bda72-126">Seleccione el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bda72-126">Select the **OK** button.</span></span>
    1. <span data-ttu-id="bda72-127">Elija **Aplicación web** en la ventana que muestra los distintos tipos de proyectos de ASP.NET Core y, luego, haga clic en el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bda72-127">Choose **Web Application** in the window that displays the different types of ASP.NET Core Projects, and then select the **OK** button.</span></span>

## <a name="prepare-and-understand-the-data"></a><span data-ttu-id="bda72-128">Preparar y entender los datos</span><span class="sxs-lookup"><span data-stu-id="bda72-128">Prepare and understand the data</span></span>

<span data-ttu-id="bda72-129">Descargue el [conjunto de datos detox de Wikipedia](https://raw.githubusercontent.com/dotnet/machinelearning/main/test/data/wikipedia-detox-250-line-data.tsv).</span><span class="sxs-lookup"><span data-stu-id="bda72-129">Download [Wikipedia detox dataset](https://raw.githubusercontent.com/dotnet/machinelearning/main/test/data/wikipedia-detox-250-line-data.tsv).</span></span> <span data-ttu-id="bda72-130">Cuando se abra la página web, haga clic con el botón derecho en la página, seleccione **Guardar como** y guarde el archivo en cualquier parte del equipo.</span><span class="sxs-lookup"><span data-stu-id="bda72-130">When the webpage opens, right-click on the page, select **Save As** and save the file anywhere on your computer.</span></span>

<span data-ttu-id="bda72-131">Cada fila del conjunto de datos *wikipedia-detox-250-line-data.tsv* presenta una opinión distinta que un usuario deja en Wikipedia.</span><span class="sxs-lookup"><span data-stu-id="bda72-131">Each row in the *wikipedia-detox-250-line-data.tsv* dataset represents a different review left by a user on Wikipedia.</span></span> <span data-ttu-id="bda72-132">La primera columna representa el sentimiento del texto (0 indica no tóxico, 1 indica tóxico) y la segunda columna representa el comentario que deja el usuario.</span><span class="sxs-lookup"><span data-stu-id="bda72-132">The first column represents the sentiment of the text (0 is non-toxic, 1 is toxic), and the second column represents the comment left by the user.</span></span> <span data-ttu-id="bda72-133">Las columnas están separadas por tabulaciones.</span><span class="sxs-lookup"><span data-stu-id="bda72-133">The columns are separated by tabs.</span></span> <span data-ttu-id="bda72-134">Los datos tienen un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="bda72-134">The data looks like the following:</span></span>

| <span data-ttu-id="bda72-135">Opinión</span><span class="sxs-lookup"><span data-stu-id="bda72-135">Sentiment</span></span> | <span data-ttu-id="bda72-136">SentimentText</span><span class="sxs-lookup"><span data-stu-id="bda72-136">SentimentText</span></span> |
| :---: | :---: |
<span data-ttu-id="bda72-137">1</span><span class="sxs-lookup"><span data-stu-id="bda72-137">1</span></span> | <span data-ttu-id="bda72-138">==RUDE== Dude, you are rude upload that carl picture back, or else. (Oye, vuelve a subir esa foto de Carl o te las verás conmigo).</span><span class="sxs-lookup"><span data-stu-id="bda72-138">==RUDE== Dude, you are rude upload that carl picture back, or else.</span></span>
<span data-ttu-id="bda72-139">1</span><span class="sxs-lookup"><span data-stu-id="bda72-139">1</span></span> | <span data-ttu-id="bda72-140">== OK!</span><span class="sxs-lookup"><span data-stu-id="bda72-140">== OK!</span></span> <span data-ttu-id="bda72-141">==  IM GOING TO VANDALIZE WILD ONES WIKI THEN!!! (BUENO, ENTONCES VOY A VANDALIZAR ALGUNAS WIKI).</span><span class="sxs-lookup"><span data-stu-id="bda72-141">==  IM GOING TO VANDALIZE WILD ONES WIKI THEN!!!</span></span>
<span data-ttu-id="bda72-142">0</span><span class="sxs-lookup"><span data-stu-id="bda72-142">0</span></span> | <span data-ttu-id="bda72-143">I hope this helps. (Espero que esto ayude).</span><span class="sxs-lookup"><span data-stu-id="bda72-143">I hope this helps.</span></span>

## <a name="choose-a-scenario"></a><span data-ttu-id="bda72-144">Elección de un escenario</span><span class="sxs-lookup"><span data-stu-id="bda72-144">Choose a scenario</span></span>

![Asistente para el generador de modelos en Visual Studio](./media/sentiment-analysis-model-builder/model-builder-screen.png)

<span data-ttu-id="bda72-146">Para entrenar el modelo, deberá seleccionarlo en la lista de escenarios de aprendizaje automático disponibles proporcionada por el Generador de modelos.</span><span class="sxs-lookup"><span data-stu-id="bda72-146">To train your model, you need to select from the list of available machine learning scenarios provided by Model Builder.</span></span>

1. <span data-ttu-id="bda72-147">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto *SentimentRazor* y seleccione **Agregar** > **Machine Learning**.</span><span class="sxs-lookup"><span data-stu-id="bda72-147">In **Solution Explorer**, right-click the *SentimentRazor* project, and select **Add** > **Machine Learning**.</span></span>
1. <span data-ttu-id="bda72-148">En este ejemplo, el escenario es el análisis de sentimiento.</span><span class="sxs-lookup"><span data-stu-id="bda72-148">For this sample, the scenario is sentiment analysis.</span></span> <span data-ttu-id="bda72-149">En el paso *Escenario* de la herramienta Generador de modelos, seleccione el escenario **Análisis de sentimiento**.</span><span class="sxs-lookup"><span data-stu-id="bda72-149">In the *scenario* step of the Model Builder tool, select the **Sentiment Analysis** scenario.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="bda72-150">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="bda72-150">Load the data</span></span>

<span data-ttu-id="bda72-151">El Generador de modelos acepta datos de dos orígenes, una base de datos de SQL Server o un archivo local en formato `csv` o `tsv`.</span><span class="sxs-lookup"><span data-stu-id="bda72-151">Model Builder accepts data from two sources, a SQL Server database or a local file in `csv` or `tsv` format.</span></span>

1. <span data-ttu-id="bda72-152">En el paso de datos de la herramienta Generador de modelos, seleccione **Archivo** en la lista desplegable origen de datos.</span><span class="sxs-lookup"><span data-stu-id="bda72-152">In the data step of the Model Builder tool, select **File** from the data source dropdown.</span></span>
1. <span data-ttu-id="bda72-153">Seleccione el botón junto al cuadro de texto **Seleccionar un archivo** y use el Explorador de archivos para examinar y seleccionar el archivo *wikipedia-detox-250-line-data.tsv*.</span><span class="sxs-lookup"><span data-stu-id="bda72-153">Select the button next to the **Select a file** text box and use File Explorer to browse and select the *wikipedia-detox-250-line-data.tsv* file.</span></span>
1. <span data-ttu-id="bda72-154">Elija **Sentimiento** en el menú desplegable **Column to Predict (Label)** (Columna para la predicción [etiqueta]).</span><span class="sxs-lookup"><span data-stu-id="bda72-154">Choose **Sentiment** in the **Column to Predict (Label)** dropdown.</span></span>
1. <span data-ttu-id="bda72-155">Deje los valores predeterminados del menú desplegable **Input Columns (Features)** (Columnas de entrada [características]).</span><span class="sxs-lookup"><span data-stu-id="bda72-155">Leave the default values for the **Input Columns (Features)** dropdown.</span></span>
1. <span data-ttu-id="bda72-156">Seleccione el vínculo **Entrenar** para ir al paso siguiente en la herramienta Generador de modelos.</span><span class="sxs-lookup"><span data-stu-id="bda72-156">Select the **Train** link to move to the next step in the Model Builder tool.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="bda72-157">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="bda72-157">Train the model</span></span>

<span data-ttu-id="bda72-158">La tarea de aprendizaje automático que se usa para entrenar el modelo de análisis de opinión en este tutorial es la clasificación binaria.</span><span class="sxs-lookup"><span data-stu-id="bda72-158">The machine learning task used to train the sentiment analysis model in this tutorial is binary classification.</span></span> <span data-ttu-id="bda72-159">Durante el proceso de entrenamiento de modelos, el Generador de modelos entrena modelos independientes con diferentes opciones y algoritmos de clasificación binaria para encontrar el modelo con mejor rendimiento para el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="bda72-159">During the model training process, Model Builder trains separate models using different binary classification algorithms and settings to find the best performing model for your dataset.</span></span>

<span data-ttu-id="bda72-160">El tiempo necesario para el entrenamiento del modelo es proporcional a la cantidad de datos.</span><span class="sxs-lookup"><span data-stu-id="bda72-160">The time required for the model to train is proportionate to the amount of data.</span></span> <span data-ttu-id="bda72-161">El generador de modelos selecciona automáticamente un valor predeterminado para **Tiempo de entrenamiento (segundos)** en función del tamaño del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="bda72-161">Model Builder automatically selects a default value for **Time to train (seconds)** based on the size of your data source.</span></span>

1. <span data-ttu-id="bda72-162">Aunque el Generador de modelos establezca el valor de **Tiempo de entrenamiento (segundos)** en 10 segundos, debe aumentarlo a 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="bda72-162">Although Model Builder sets the value of **Time to train (seconds)** to 10 seconds, increase it to 30 seconds.</span></span> <span data-ttu-id="bda72-163">El entrenamiento durante un período de tiempo más prolongado permite que el Generador de modelos explore un mayor número de algoritmos y combinación de parámetros en la búsqueda del mejor modelo.</span><span class="sxs-lookup"><span data-stu-id="bda72-163">Training for a longer period of time allows Model Builder to explore a larger number of algorithms and combination of parameters in search of the best model.</span></span>
1. <span data-ttu-id="bda72-164">Seleccione **Iniciar entrenamiento**.</span><span class="sxs-lookup"><span data-stu-id="bda72-164">Select **Start Training**.</span></span>

    <span data-ttu-id="bda72-165">Durante el proceso de entrenamiento, los datos de progreso se muestran en la sección `Progress` del paso de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="bda72-165">Throughout the training process, progress data is displayed in the `Progress` section of the train step.</span></span>

    - <span data-ttu-id="bda72-166">En Estado se muestra el grado de finalización del proceso de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="bda72-166">Status displays the completion status of the training process.</span></span>
    - <span data-ttu-id="bda72-167">En Mejor precisión se muestra la precisión del modelo con mejor rendimiento que ha encontrado el Generador de modelos hasta el momento.</span><span class="sxs-lookup"><span data-stu-id="bda72-167">Best accuracy displays the accuracy of the best performing model found by Model Builder so far.</span></span> <span data-ttu-id="bda72-168">Una mayor precisión significa que el modelo realiza una predicción más correcta de los datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="bda72-168">Higher accuracy means the model predicted more correctly on test data.</span></span>
    - <span data-ttu-id="bda72-169">En Mejor algoritmo se muestra el nombre del algoritmo con mejor rendimiento que ha encontrado el Generador de modelos hasta el momento.</span><span class="sxs-lookup"><span data-stu-id="bda72-169">Best algorithm displays the name of the best performing algorithm performed found by Model Builder so far.</span></span>
    - <span data-ttu-id="bda72-170">En Último algoritmo se muestra el nombre del algoritmo que ha usado más recientemente el Generador de modelos para entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="bda72-170">Last algorithm displays the name of the algorithm most recently used by Model Builder to train the model.</span></span>

1. <span data-ttu-id="bda72-171">Una vez que se complete el entrenamiento, seleccione el vínculo de **evaluación** para ir al paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="bda72-171">Once training is complete, select the **evaluate** link to move to the next step.</span></span>

## <a name="evaluate-the-model"></a><span data-ttu-id="bda72-172">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="bda72-172">Evaluate the model</span></span>

<span data-ttu-id="bda72-173">El resultado del paso de entrenamiento será un modelo que tiene el mejor rendimiento.</span><span class="sxs-lookup"><span data-stu-id="bda72-173">The result of the training step will be one model that has the best performance.</span></span> <span data-ttu-id="bda72-174">En el paso de evaluación de la herramienta Generador de modelos, la sección de salida contendrá el algoritmo que usa el modelo con el mejor rendimiento en la entrada **Mejor modelo** junto con las métricas de **Modelo de mayor precisión**.</span><span class="sxs-lookup"><span data-stu-id="bda72-174">In the evaluate step of the Model Builder tool, the output section will contain the algorithm used by the best-performing model in the **Best Model** entry along with metrics in **Best Model Accuracy**.</span></span> <span data-ttu-id="bda72-175">Además, se muestra una tabla de resumen que contiene los cinco mejores modelos y sus métricas.</span><span class="sxs-lookup"><span data-stu-id="bda72-175">Additionally, a summary table containing the top five models and their metrics is shown.</span></span>

<span data-ttu-id="bda72-176">Si no está satisfecho con las métricas de precisión, una forma sencilla de intentar mejorar la precisión del modelo es aumentar la cantidad de tiempo para entrenar el modelo o usar más datos.</span><span class="sxs-lookup"><span data-stu-id="bda72-176">If you're not satisfied with your accuracy metrics, some easy ways to try to improve model accuracy are to increase the amount of time to train the model or use more data.</span></span> <span data-ttu-id="bda72-177">En caso contrario, seleccione el vínculo de **código** para ir al paso final de la herramienta Generador de modelos.</span><span class="sxs-lookup"><span data-stu-id="bda72-177">Otherwise, select the **code** link to move to the final step in the Model Builder tool.</span></span>

## <a name="add-the-code-to-make-predictions"></a><span data-ttu-id="bda72-178">Incorporación del código para hacer predicciones</span><span class="sxs-lookup"><span data-stu-id="bda72-178">Add the code to make predictions</span></span>

<span data-ttu-id="bda72-179">Se crearán dos proyectos como resultado del proceso de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="bda72-179">Two projects will be created as a result of the training process.</span></span>

### <a name="reference-the-trained-model"></a><span data-ttu-id="bda72-180">Referencia al modelo entrenado</span><span class="sxs-lookup"><span data-stu-id="bda72-180">Reference the trained model</span></span>

1. <span data-ttu-id="bda72-181">En el paso de *código* de la herramienta Generador de modelos, seleccione **Agregar proyectos** para agregar los proyectos generados automáticamente a la solución.</span><span class="sxs-lookup"><span data-stu-id="bda72-181">In the *code* step of the Model Builder tool, select **Add Projects** to add the autogenerated projects to the solution.</span></span>

    <span data-ttu-id="bda72-182">Los proyectos siguientes deben aparecer en el **Explorador de soluciones**:</span><span class="sxs-lookup"><span data-stu-id="bda72-182">The following projects should appear in the **Solution Explorer**:</span></span>

    - <span data-ttu-id="bda72-183">*SentimentRazorML.ConsoleApp*: una aplicación de consola de .NET Core que contiene el entrenamiento del modelo y el código de predicción.</span><span class="sxs-lookup"><span data-stu-id="bda72-183">*SentimentRazorML.ConsoleApp*: A .NET Core Console application that contains the model training and prediction code.</span></span>
    - <span data-ttu-id="bda72-184">*SentimentRazorML.Model*: Una biblioteca de clases .NET Standard que contienen los modelos de datos que definen el esquema de entrada y salida de los datos del modelo, así como la versión guardada del modelo con mejor rendimiento durante el entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="bda72-184">*SentimentRazorML.Model*: A .NET Standard class library containing the data models that define the schema of input and output model data as well as the saved version of the best performing model during training.</span></span>

    <span data-ttu-id="bda72-185">En este tutorial, solo se usa el proyecto *SentimentRazorML.Model*, porque las predicciones se realizarán en la aplicación web *SentimentRazor* en lugar de hacerlo en la consola.</span><span class="sxs-lookup"><span data-stu-id="bda72-185">For this tutorial, only the *SentimentRazorML.Model* project is used because predictions will be made in the *SentimentRazor* web application rather than in the console.</span></span> <span data-ttu-id="bda72-186">Aunque *SentimentRazorML.ConsoleApp* no se usará para la puntuación, se puede usar para volver a entrenar el modelo con datos nuevos más adelante.</span><span class="sxs-lookup"><span data-stu-id="bda72-186">Although the *SentimentRazorML.ConsoleApp* won't be used for scoring, it can be used to retrain the model using new data at a later time.</span></span> <span data-ttu-id="bda72-187">No obstante, el reentrenamiento queda fuera del ámbito de este tutorial.</span><span class="sxs-lookup"><span data-stu-id="bda72-187">Retraining is outside the scope of this tutorial though.</span></span>

### <a name="configure-the-predictionengine-pool"></a><span data-ttu-id="bda72-188">Configuración del grupo PredictionEngine</span><span class="sxs-lookup"><span data-stu-id="bda72-188">Configure the PredictionEngine pool</span></span>

<span data-ttu-id="bda72-189">Para realizar una sola predicción, tendrá que crear un objeto <xref:Microsoft.ML.PredictionEngine%602>.</span><span class="sxs-lookup"><span data-stu-id="bda72-189">To make a single prediction, you have to create a <xref:Microsoft.ML.PredictionEngine%602>.</span></span> <span data-ttu-id="bda72-190"><xref:Microsoft.ML.PredictionEngine%602> no es seguro para subprocesos.</span><span class="sxs-lookup"><span data-stu-id="bda72-190"><xref:Microsoft.ML.PredictionEngine%602> is not thread-safe.</span></span> <span data-ttu-id="bda72-191">Además, tiene que crear una instancia en cualquier lugar en que se necesite dentro de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="bda72-191">Additionally, you have to create an instance of it everywhere it's needed within your application.</span></span> <span data-ttu-id="bda72-192">A medida que crece la aplicación, este proceso puede volverse difícil de administrar.</span><span class="sxs-lookup"><span data-stu-id="bda72-192">As your application grows, this process can become unmanageable.</span></span> <span data-ttu-id="bda72-193">Para mejorar el rendimiento y la seguridad para subprocesos, use una combinación de inserción de dependencias y el servicio `PredictionEnginePool`, que crea un elemento <xref:Microsoft.Extensions.ObjectPool.ObjectPool%601> de objetos <xref:Microsoft.ML.PredictionEngine%602> para usarlo en toda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="bda72-193">For improved performance and thread safety, use a combination of dependency injection and the `PredictionEnginePool` service, which creates an <xref:Microsoft.Extensions.ObjectPool.ObjectPool%601> of <xref:Microsoft.ML.PredictionEngine%602> objects for use throughout your application.</span></span>

1. <span data-ttu-id="bda72-194">Instale el paquete *Microsoft.Extensions.ML* de NuGet:</span><span class="sxs-lookup"><span data-stu-id="bda72-194">Install the *Microsoft.Extensions.ML* NuGet package:</span></span>

    1. <span data-ttu-id="bda72-195">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="bda72-195">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span>
    1. <span data-ttu-id="bda72-196">Elija "nuget.org" como origen del paquete.</span><span class="sxs-lookup"><span data-stu-id="bda72-196">Choose "nuget.org" as the Package source.</span></span>
    1. <span data-ttu-id="bda72-197">Seleccione la pestaña **Examinar** y busque **Microsoft.Extensions.ML**.</span><span class="sxs-lookup"><span data-stu-id="bda72-197">Select the **Browse** tab and search for **Microsoft.Extensions.ML**.</span></span>
    1. <span data-ttu-id="bda72-198">Seleccione el paquete en la lista y haga clic en el botón **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="bda72-198">Select the package in the list, and select the **Install** button.</span></span>
    1. <span data-ttu-id="bda72-199">Haga clic en el botón **Aceptar** en el cuadro de diálogo **Vista previa de los cambios**.</span><span class="sxs-lookup"><span data-stu-id="bda72-199">Select the **OK** button on the **Preview Changes** dialog</span></span>
    1. <span data-ttu-id="bda72-200">Haga clic en el botón **Acepto** en el cuadro de diálogo **Aceptación de la licencia** si está de acuerdo con los términos de licencia de los paquetes que aparecen.</span><span class="sxs-lookup"><span data-stu-id="bda72-200">Select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="bda72-201">Abra el archivo *Startup.cs* en el proyecto *SentimentRazor*.</span><span class="sxs-lookup"><span data-stu-id="bda72-201">Open the *Startup.cs* file in the *SentimentRazor* project.</span></span>
1. <span data-ttu-id="bda72-202">Agregue las instrucciones USING siguientes para hacer referencia al paquete de NuGet *Microsoft.Extensions.ML* y al proyecto *SentimentRazorML.Model*:</span><span class="sxs-lookup"><span data-stu-id="bda72-202">Add the following using statements to reference the *Microsoft.Extensions.ML* NuGet package and *SentimentRazorML.Model* project:</span></span>

    ```csharp
    using System.IO;
    using Microsoft.Extensions.ML;
    using SentimentRazorML.Model;
    ```

1. <span data-ttu-id="bda72-203">Cree una variable global para almacenar la ubicación del archivo del modelo entrenado.</span><span class="sxs-lookup"><span data-stu-id="bda72-203">Create a global variable to store the location of the trained model file.</span></span>

    ```csharp
    private readonly string _modelPath;
    ```

1. <span data-ttu-id="bda72-204">El archivo del modelo se almacena en el directorio de compilación junto con los archivos de ensamblado de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="bda72-204">The model file is stored in the build directory alongside the assembly files of your application.</span></span> <span data-ttu-id="bda72-205">Para facilitar el acceso, cree un método auxiliar llamado `GetAbsolutePath` después del método `Configure`.</span><span class="sxs-lookup"><span data-stu-id="bda72-205">To make it easier to access, create a helper method called `GetAbsolutePath` after the `Configure` method</span></span>

    ```csharp
    public static string GetAbsolutePath(string relativePath)
    {
        FileInfo _dataRoot = new FileInfo(typeof(Program).Assembly.Location);
        string assemblyFolderPath = _dataRoot.Directory.FullName;

        string fullPath = Path.Combine(assemblyFolderPath, relativePath);
        return fullPath;
    }
    ```

1. <span data-ttu-id="bda72-206">Use el método `GetAbsolutePath` en el constructor de la clase `Startup` para establecer el `_modelPath`.</span><span class="sxs-lookup"><span data-stu-id="bda72-206">Use the `GetAbsolutePath` method in the `Startup` class constructor to set the `_modelPath`.</span></span>

    ```csharp
    _modelPath = GetAbsolutePath("MLModel.zip");
    ```

1. <span data-ttu-id="bda72-207">Configure `PredictionEnginePool` para la aplicación en el método `ConfigureServices`:</span><span class="sxs-lookup"><span data-stu-id="bda72-207">Configure the `PredictionEnginePool` for your application in the `ConfigureServices` method:</span></span>

    ```csharp
    services.AddPredictionEnginePool<ModelInput, ModelOutput>()
            .FromFile(_modelPath);
    ```

### <a name="create-sentiment-analysis-handler"></a><span data-ttu-id="bda72-208">Creación de un controlador de análisis de sentimiento</span><span class="sxs-lookup"><span data-stu-id="bda72-208">Create sentiment analysis handler</span></span>

<span data-ttu-id="bda72-209">Las predicciones se realizarán dentro de la página principal de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="bda72-209">Predictions will be made inside the main page of the application.</span></span> <span data-ttu-id="bda72-210">Por tanto, se necesita un método que tome las entradas del usuario y use `PredictionEnginePool` para devolver una predicción.</span><span class="sxs-lookup"><span data-stu-id="bda72-210">Therefore, a method that takes the user input and uses the `PredictionEnginePool` to return a prediction needs to be added.</span></span>

1. <span data-ttu-id="bda72-211">Abra el archivo *Index.cshtml.cs* ubicado en el directorio *Pages* y agregue las instrucciones USING siguientes:</span><span class="sxs-lookup"><span data-stu-id="bda72-211">Open the *Index.cshtml.cs* file located in the *Pages* directory and add the following using statements:</span></span>

    ```csharp
    using Microsoft.Extensions.ML;
    using SentimentRazorML.Model;
    ```

    <span data-ttu-id="bda72-212">Para usar el `PredictionEnginePool` configurado en la clase `Startup`, debe insertarlo en el constructor del modelo donde quiere usarlo.</span><span class="sxs-lookup"><span data-stu-id="bda72-212">In order to use the `PredictionEnginePool` configured in the `Startup` class, you have to inject it into the constructor of the model where you want to use it.</span></span>

1. <span data-ttu-id="bda72-213">Agregue una variable para hacer referencia al `PredictionEnginePool` dentro de la clase `IndexModel`.</span><span class="sxs-lookup"><span data-stu-id="bda72-213">Add a variable to reference the `PredictionEnginePool` inside the `IndexModel` class.</span></span>

    ```csharp
    private readonly PredictionEnginePool<ModelInput, ModelOutput> _predictionEnginePool;
    ```

1. <span data-ttu-id="bda72-214">Cree un constructor en la clase `IndexModel` e inserte el servicio `PredictionEnginePool` en él.</span><span class="sxs-lookup"><span data-stu-id="bda72-214">Create a constructor in the `IndexModel` class and inject the `PredictionEnginePool` service into it.</span></span>

    ```csharp
    public IndexModel(PredictionEnginePool<ModelInput, ModelOutput> predictionEnginePool)
    {
        _predictionEnginePool = predictionEnginePool;
    }
    ```

1. <span data-ttu-id="bda72-215">Cree un controlador de método que use `PredictionEnginePool` para hacer predicciones a partir de la información proporcionada por el usuario recibida desde la página web.</span><span class="sxs-lookup"><span data-stu-id="bda72-215">Create a method handler that uses the `PredictionEnginePool` to make predictions from user input received from the web page.</span></span>

    1. <span data-ttu-id="bda72-216">Debajo del método `OnGet`, cree un método nuevo denominado `OnGetAnalyzeSentiment`.</span><span class="sxs-lookup"><span data-stu-id="bda72-216">Below the `OnGet` method, create a new method called `OnGetAnalyzeSentiment`</span></span>

        ```csharp
        public IActionResult OnGetAnalyzeSentiment([FromQuery] string text)
        {

        }
        ```

    1. <span data-ttu-id="bda72-217">Dentro del método `OnGetAnalyzeSentiment`, devuelva un sentimiento *neutral* si la información ingresada por el usuario es nula o está en blanco.</span><span class="sxs-lookup"><span data-stu-id="bda72-217">Inside the `OnGetAnalyzeSentiment` method, return *Neutral* sentiment if the input from the user is blank or null.</span></span>

        ```csharp
        if (String.IsNullOrEmpty(text)) return Content("Neutral");
        ```

    1. <span data-ttu-id="bda72-218">Dada una entrada válida, cree una instancia nueva de `ModelInput`.</span><span class="sxs-lookup"><span data-stu-id="bda72-218">Given a valid input, create a new instance of `ModelInput`.</span></span>

        ```csharp
        var input = new ModelInput { SentimentText = text };
        ```

    1. <span data-ttu-id="bda72-219">Use `PredictionEnginePool` para predecir el sentimiento.</span><span class="sxs-lookup"><span data-stu-id="bda72-219">Use the `PredictionEnginePool` to predict sentiment.</span></span>

        ```csharp
        var prediction = _predictionEnginePool.Predict(input);
        ```

    1. <span data-ttu-id="bda72-220">Convierta el valor `bool` de predicción en Tóxico o No tóxico con el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="bda72-220">Convert the predicted `bool` value into toxic or not toxic with the following code.</span></span>

        ```csharp
        var sentiment = Convert.ToBoolean(prediction.Prediction) ? "Toxic" : "Not Toxic";
        ```

    1. <span data-ttu-id="bda72-221">Por último, devuelva el sentimiento a la página web.</span><span class="sxs-lookup"><span data-stu-id="bda72-221">Finally, return the sentiment back to the web page.</span></span>

        ```csharp
        return Content(sentiment);
        ```

### <a name="configure-the-web-page"></a><span data-ttu-id="bda72-222">Configuración de la página web</span><span class="sxs-lookup"><span data-stu-id="bda72-222">Configure the web page</span></span>

<span data-ttu-id="bda72-223">Los resultados que devuelve el `OnGetAnalyzeSentiment` se mostrarán de manera dinámica en la página web `Index`.</span><span class="sxs-lookup"><span data-stu-id="bda72-223">The results returned by the `OnGetAnalyzeSentiment` will be dynamically displayed on the `Index` web page.</span></span>

1. <span data-ttu-id="bda72-224">Abra el archivo *Index.cshtml* del directorio *Pages* y reemplace su contenido por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="bda72-224">Open the *Index.cshtml* file in the *Pages* directory and replace its contents with the following code:</span></span>

    [!code-cshtml [IndexPage](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml)]

1. <span data-ttu-id="bda72-225">A continuación, agregue el código de estilo CSS al final de la página *site.css* en el directorio *wwwroot\css*:</span><span class="sxs-lookup"><span data-stu-id="bda72-225">Next, add css styling code to the end of the *site.css* page in the *wwwroot\css* directory:</span></span>

    [!code-css [CssStyling](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/css/site.css#L61-L105)]

1. <span data-ttu-id="bda72-226">Después, agregue código para enviar entradas desde la página web al controlador `OnGetAnalyzeSentiment`.</span><span class="sxs-lookup"><span data-stu-id="bda72-226">After that, add code to send inputs from the web page to the `OnGetAnalyzeSentiment` handler.</span></span>

    1. <span data-ttu-id="bda72-227">En el archivo *site.js* que se encuentra en el directorio *wwwroot\js*, cree una función llamada `getSentiment` para realizar una solicitud HTTP GET con la entrada del usuario al controlador `OnGetAnalyzeSentiment`.</span><span class="sxs-lookup"><span data-stu-id="bda72-227">In the *site.js* file located in the *wwwroot\js* directory, create a function called `getSentiment` to make a GET HTTP request with the user input to the `OnGetAnalyzeSentiment` handler.</span></span>

        [!code-javascript [GetSentimentMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L5-L10)]

    1. <span data-ttu-id="bda72-228">A continuación, agregue otra función llamada `updateMarker` para actualizar dinámicamente la posición del marcador en la página web cuando se predice el sentimiento.</span><span class="sxs-lookup"><span data-stu-id="bda72-228">Below that, add another function called `updateMarker` to dynamically update the position of the marker on the web page as sentiment is predicted.</span></span>

        [!code-javascript [UpdateMarkerMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L12-L15)]

    1. <span data-ttu-id="bda72-229">Cree una función de controlador de eventos llamada `updateSentiment` para obtener la entrada del usuario, envíela a la función `OnGetAnalyzeSentiment` mediante la función `getSentiment` y actualice el marcador con la función `updateMarker`.</span><span class="sxs-lookup"><span data-stu-id="bda72-229">Create an event handler function called `updateSentiment` to get the input from the user, send it to the `OnGetAnalyzeSentiment` function using the `getSentiment` function and update the marker with the `updateMarker` function.</span></span>

        [!code-javascript [UpdateSentimentMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L17-L34)]

    1. <span data-ttu-id="bda72-230">Por último, registre el controlador de eventos y enlácelo al elemento `textarea` con el atributo `id=Message`.</span><span class="sxs-lookup"><span data-stu-id="bda72-230">Finally, register the event handler and bind it to the `textarea` element with the `id=Message` attribute.</span></span>

        [!code-javascript [UpdateSentimentEvtHandler](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L36)]

## <a name="run-the-application"></a><span data-ttu-id="bda72-231">Ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="bda72-231">Run the application</span></span>

<span data-ttu-id="bda72-232">Ahora que la aplicación está configurada, ejecútela. Se debería iniciar en el explorador.</span><span class="sxs-lookup"><span data-stu-id="bda72-232">Now that your application is set up, run the application, which should launch in your browser.</span></span>

<span data-ttu-id="bda72-233">Cuando se inicie la aplicación, escriba *¡El Generador de modelos es genial!*</span><span class="sxs-lookup"><span data-stu-id="bda72-233">When the application launches, enter *Model Builder is cool!*</span></span> <span data-ttu-id="bda72-234">en el área de texto.</span><span class="sxs-lookup"><span data-stu-id="bda72-234">into the text area.</span></span> <span data-ttu-id="bda72-235">El sentimiento de predicción que aparece debe ser *Not Toxic* (No tóxico).</span><span class="sxs-lookup"><span data-stu-id="bda72-235">The predicted sentiment displayed should be *Not Toxic*.</span></span>

![Ventana en ejecución con la ventana de sentimiento de predicción](./media/sentiment-analysis-model-builder/web-app.png)

<span data-ttu-id="bda72-237">Si tiene que hacer referencia a los proyectos generados por el Generador de modelos más adelante en otra solución, puede encontrarlos en el directorio `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools`.</span><span class="sxs-lookup"><span data-stu-id="bda72-237">If you need to reference the Model Builder generated projects at a later time inside of another solution, you can find them inside the `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools` directory.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bda72-238">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="bda72-238">Next steps</span></span>

<span data-ttu-id="bda72-239">En este tutorial ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="bda72-239">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="bda72-240">Crear una aplicación Razor Pages de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="bda72-240">Create an ASP.NET Core Razor Pages application</span></span>
> - <span data-ttu-id="bda72-241">Preparar y entender los datos</span><span class="sxs-lookup"><span data-stu-id="bda72-241">Prepare and understand the data</span></span>
> - <span data-ttu-id="bda72-242">Elección de un escenario</span><span class="sxs-lookup"><span data-stu-id="bda72-242">Choose a scenario</span></span>
> - <span data-ttu-id="bda72-243">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="bda72-243">Load the data</span></span>
> - <span data-ttu-id="bda72-244">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="bda72-244">Train the model</span></span>
> - <span data-ttu-id="bda72-245">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="bda72-245">Evaluate the model</span></span>
> - <span data-ttu-id="bda72-246">Usar el modelo para las predicciones</span><span class="sxs-lookup"><span data-stu-id="bda72-246">Use the model for predictions</span></span>

### <a name="additional-resources"></a><span data-ttu-id="bda72-247">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="bda72-247">Additional Resources</span></span>

<span data-ttu-id="bda72-248">Para más información sobre los temas mencionados en este tutorial, visite estos recursos:</span><span class="sxs-lookup"><span data-stu-id="bda72-248">To learn more about topics mentioned in this tutorial, visit the following resources:</span></span>

- [<span data-ttu-id="bda72-249">Escenarios del Generador de modelos</span><span class="sxs-lookup"><span data-stu-id="bda72-249">Model Builder Scenarios</span></span>](../automate-training-with-model-builder.md#scenario)
- [<span data-ttu-id="bda72-250">Clasificación binaria</span><span class="sxs-lookup"><span data-stu-id="bda72-250">Binary Classification</span></span>](../resources/glossary.md#binary-classification)
- [<span data-ttu-id="bda72-251">Métricas del modelo de clasificación binaria</span><span class="sxs-lookup"><span data-stu-id="bda72-251">Binary Classification Model Metrics</span></span>](../resources/metrics.md#evaluation-metrics-for-binary-classification)
