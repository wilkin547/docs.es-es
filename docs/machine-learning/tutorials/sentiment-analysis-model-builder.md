---
title: 'Tutorial: Análisis de sentimiento: clasificación binaria'
description: En este tutorial se muestra cómo crear una aplicación Razor Pages que clasifica los sentimientos de los comentarios del sitio web y toma las medidas oportunas. El clasificador binario de sentimientos usa el Generador de modelos en Visual Studio.
ms.date: 09/26/2019
author: luisquintanilla
ms.author: luquinta
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 0878a9318e7c60be29eeac9fb4efd47e408ab660
ms.sourcegitcommit: 8b8dd14dde727026fd0b6ead1ec1df2e9d747a48
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "71332582"
---
# <a name="tutorial-analyze-sentiment-of-website-comments-in-a-web-application-using-mlnet-model-builder"></a><span data-ttu-id="5fe09-104">Tutorial: Análisis del sentimiento de los comentarios del sitio web en una aplicación web con el Generador de modelos de ML.NET</span><span class="sxs-lookup"><span data-stu-id="5fe09-104">Tutorial: Analyze sentiment of website comments in a web application using ML.NET Model Builder</span></span>

<span data-ttu-id="5fe09-105">Aprenda a analizar el sentimiento de los comentarios en tiempo real dentro de una aplicación web.</span><span class="sxs-lookup"><span data-stu-id="5fe09-105">Learn how to analyze sentiment from comments in real-time inside a web application.</span></span>

<span data-ttu-id="5fe09-106">En este tutorial se muestra cómo crear una aplicación Razor Pages de ASP.NET Core que clasifica los sentimientos de los comentarios del sitio web en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="5fe09-106">This tutorial shows you how to create an ASP.NET Core Razor Pages application that classifies sentiment from website comments in real-time.</span></span>

<span data-ttu-id="5fe09-107">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="5fe09-107">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="5fe09-108">Crear una aplicación Razor Pages de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="5fe09-108">Create an ASP.NET Core Razor Pages application</span></span>
> - <span data-ttu-id="5fe09-109">Preparar y entender los datos</span><span class="sxs-lookup"><span data-stu-id="5fe09-109">Prepare and understand the data</span></span>
> - <span data-ttu-id="5fe09-110">Elección de un escenario</span><span class="sxs-lookup"><span data-stu-id="5fe09-110">Choose a scenario</span></span>
> - <span data-ttu-id="5fe09-111">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="5fe09-111">Load the data</span></span>
> - <span data-ttu-id="5fe09-112">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="5fe09-112">Train the model</span></span>
> - <span data-ttu-id="5fe09-113">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="5fe09-113">Evaluate the model</span></span>
> - <span data-ttu-id="5fe09-114">Usar el modelo para las predicciones</span><span class="sxs-lookup"><span data-stu-id="5fe09-114">Use the model for predictions</span></span>

> [!NOTE]
> <span data-ttu-id="5fe09-115">De momento, el Generador de modelos se encuentra en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="5fe09-115">Model Builder is currently in Preview.</span></span>

<span data-ttu-id="5fe09-116">Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples).</span><span class="sxs-lookup"><span data-stu-id="5fe09-116">You can find the source code for this tutorial at the [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples) repository.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="5fe09-117">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="5fe09-117">Pre-requisites</span></span>

<span data-ttu-id="5fe09-118">Para obtener una lista de los requisitos previos e instrucciones de instalación, visite la [Guía de instalación del Generador de modelos](../how-to-guides/install-model-builder.md).</span><span class="sxs-lookup"><span data-stu-id="5fe09-118">For a list of pre-requisites and installation instructions, visit the [Model Builder installation guide](../how-to-guides/install-model-builder.md).</span></span>

## <a name="create-a-razor-pages-application"></a><span data-ttu-id="5fe09-119">Creación de una aplicación Razor Pages</span><span class="sxs-lookup"><span data-stu-id="5fe09-119">Create a Razor Pages application</span></span>

1. <span data-ttu-id="5fe09-120">Cree una **aplicación Razor Pages de ASP.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="5fe09-120">Create a **ASP.NET Core Razor Pages Application**.</span></span>

    1. <span data-ttu-id="5fe09-121">Abra Visual Studio y seleccione **Archivo > Nuevo > Proyecto** en la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="5fe09-121">Open Visual Studio and select **File > New > Project** from the menu bar.</span></span>
    1. <span data-ttu-id="5fe09-122">En el cuadro de diálogo Nuevo proyecto, seleccione el nodo **Visual C#** seguido del nodo **Web**.</span><span class="sxs-lookup"><span data-stu-id="5fe09-122">In the New Project dialog, select the **Visual C#** node followed by the **Web** node.</span></span>
    1. <span data-ttu-id="5fe09-123">Seleccione la plantilla de proyecto **Aplicación web de ASP.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="5fe09-123">Then select the **ASP.NET Core Web Application** project template.</span></span>
    1. <span data-ttu-id="5fe09-124">En el cuadro de texto **Nombre**, escriba "SentimentRazor".</span><span class="sxs-lookup"><span data-stu-id="5fe09-124">In the **Name** text box, type "SentimentRazor".</span></span>
    1. <span data-ttu-id="5fe09-125">La casilla **Create a directory for solution** (Crear un directorio para la solución) debe estar activada de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5fe09-125">The **Create a directory for solution** checkbox should be checked by default.</span></span> <span data-ttu-id="5fe09-126">Si no es así, actívela.</span><span class="sxs-lookup"><span data-stu-id="5fe09-126">If that's not the case, check it.</span></span>
    1. <span data-ttu-id="5fe09-127">Seleccione el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5fe09-127">Select the **OK** button.</span></span>
    1. <span data-ttu-id="5fe09-128">Elija **Aplicación web** en la ventana que muestra los distintos tipos de proyectos de ASP.NET Core y, luego, haga clic en el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5fe09-128">Choose **Web Application** in the window that displays the different types of ASP.NET Core Projects, and then select the **OK** button.</span></span>

## <a name="prepare-and-understand-the-data"></a><span data-ttu-id="5fe09-129">Preparar y entender los datos</span><span class="sxs-lookup"><span data-stu-id="5fe09-129">Prepare and understand the data</span></span>

<span data-ttu-id="5fe09-130">Descargue el [conjunto de datos detox de Wikipedia](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/wikipedia-detox-250-line-data.tsv).</span><span class="sxs-lookup"><span data-stu-id="5fe09-130">Download [Wikipedia detox dataset](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/wikipedia-detox-250-line-data.tsv).</span></span> <span data-ttu-id="5fe09-131">Cuando se abra la página web, haga clic con el botón derecho en la página, seleccione **Guardar como** y guarde el archivo en cualquier parte del equipo.</span><span class="sxs-lookup"><span data-stu-id="5fe09-131">When the webpage opens, right-click on the page, select **Save As** and save the file anywhere on your computer.</span></span>

<span data-ttu-id="5fe09-132">Cada fila del conjunto de datos *wikipedia-detox-250-line-data.tsv* presenta una opinión distinta que un usuario deja en Wikipedia.</span><span class="sxs-lookup"><span data-stu-id="5fe09-132">Each row in the *wikipedia-detox-250-line-data.tsv* dataset represents a different review left by a user on Wikipedia.</span></span> <span data-ttu-id="5fe09-133">La primera columna representa el sentimiento del texto (0 indica no tóxico, 1 indica tóxico) y la segunda columna representa el comentario que deja el usuario.</span><span class="sxs-lookup"><span data-stu-id="5fe09-133">The first column represents the sentiment of the text (0 is non-toxic, 1 is toxic), and the second column represents the comment left by the user.</span></span> <span data-ttu-id="5fe09-134">Las columnas están separadas por tabulaciones.</span><span class="sxs-lookup"><span data-stu-id="5fe09-134">The columns are separated by tabs.</span></span> <span data-ttu-id="5fe09-135">Los datos tienen un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="5fe09-135">The data looks like the following:</span></span>

| <span data-ttu-id="5fe09-136">Opinión</span><span class="sxs-lookup"><span data-stu-id="5fe09-136">Sentiment</span></span> | <span data-ttu-id="5fe09-137">SentimentText</span><span class="sxs-lookup"><span data-stu-id="5fe09-137">SentimentText</span></span> |
| :---: | :---: |
<span data-ttu-id="5fe09-138">1</span><span class="sxs-lookup"><span data-stu-id="5fe09-138">1</span></span> | <span data-ttu-id="5fe09-139">==RUDE== Dude, you are rude upload that carl picture back, or else. (Oye, vuelve a subir esa foto de Carl o te las verás conmigo).</span><span class="sxs-lookup"><span data-stu-id="5fe09-139">==RUDE== Dude, you are rude upload that carl picture back, or else.</span></span>
<span data-ttu-id="5fe09-140">1</span><span class="sxs-lookup"><span data-stu-id="5fe09-140">1</span></span> | <span data-ttu-id="5fe09-141">== OK!</span><span class="sxs-lookup"><span data-stu-id="5fe09-141">== OK!</span></span> <span data-ttu-id="5fe09-142">==  IM GOING TO VANDALIZE WILD ONES WIKI THEN!!! (BUENO, ENTONCES VOY A VANDALIZAR ALGUNAS WIKI).</span><span class="sxs-lookup"><span data-stu-id="5fe09-142">==  IM GOING TO VANDALIZE WILD ONES WIKI THEN!!!</span></span>
<span data-ttu-id="5fe09-143">0</span><span class="sxs-lookup"><span data-stu-id="5fe09-143">0</span></span> | <span data-ttu-id="5fe09-144">I hope this helps. (Espero que esto ayude).</span><span class="sxs-lookup"><span data-stu-id="5fe09-144">I hope this helps.</span></span>

## <a name="choose-a-scenario"></a><span data-ttu-id="5fe09-145">Elección de un escenario</span><span class="sxs-lookup"><span data-stu-id="5fe09-145">Choose a scenario</span></span>

![Asistente para el generador de modelos en Visual Studio](./media/sentiment-analysis-model-builder/model-builder-screen.png)

<span data-ttu-id="5fe09-147">Para entrenar el modelo, deberá seleccionarlo en la lista de escenarios de aprendizaje automático disponibles proporcionada por el Generador de modelos.</span><span class="sxs-lookup"><span data-stu-id="5fe09-147">To train your model, you need to select from the list of available machine learning scenarios provided by Model Builder.</span></span>

1. <span data-ttu-id="5fe09-148">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto *SentimentRazor* y seleccione **Agregar** > **Machine Learning**.</span><span class="sxs-lookup"><span data-stu-id="5fe09-148">In **Solution Explorer**, right-click the *SentimentRazor* project, and select **Add** > **Machine Learning**.</span></span>
1. <span data-ttu-id="5fe09-149">En este ejemplo, el escenario es el análisis de sentimiento.</span><span class="sxs-lookup"><span data-stu-id="5fe09-149">For this sample, the scenario is sentiment analysis.</span></span> <span data-ttu-id="5fe09-150">En el paso *Escenario* de la herramienta Generador de modelos, seleccione el escenario **Análisis de sentimiento**.</span><span class="sxs-lookup"><span data-stu-id="5fe09-150">In the *scenario* step of the Model Builder tool, select the **Sentiment Analysis** scenario.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="5fe09-151">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="5fe09-151">Load the data</span></span>

<span data-ttu-id="5fe09-152">El Generador de modelos acepta datos de dos orígenes, una base de datos de SQL Server o un archivo local en formato `csv` o `tsv`.</span><span class="sxs-lookup"><span data-stu-id="5fe09-152">Model Builder accepts data from two sources, a SQL Server database or a local file in `csv` or `tsv` format.</span></span>

1. <span data-ttu-id="5fe09-153">En el paso de datos de la herramienta Generador de modelos, seleccione **Archivo** en la lista desplegable origen de datos.</span><span class="sxs-lookup"><span data-stu-id="5fe09-153">In the data step of the Model Builder tool, select **File** from the data source dropdown.</span></span>
1. <span data-ttu-id="5fe09-154">Seleccione el botón junto al cuadro de texto **Seleccionar un archivo** y use el Explorador de archivos para examinar y seleccionar el archivo *wikipedia-detox-250-line-data.tsv*.</span><span class="sxs-lookup"><span data-stu-id="5fe09-154">Select the button next to the **Select a file** text box and use File Explorer to browse and select the *wikipedia-detox-250-line-data.tsv* file.</span></span>
1. <span data-ttu-id="5fe09-155">Elija **Sentimiento** en el menú desplegable **Column to Predict (Label)** (Columna para la predicción [etiqueta]).</span><span class="sxs-lookup"><span data-stu-id="5fe09-155">Choose **Sentiment** in the **Column to Predict (Label)** dropdown.</span></span>
1. <span data-ttu-id="5fe09-156">Deje los valores predeterminados del menú desplegable **Input Columns (Features)** (Columnas de entrada [características]).</span><span class="sxs-lookup"><span data-stu-id="5fe09-156">Leave the default values for the **Input Columns (Features)** dropdown.</span></span>
1. <span data-ttu-id="5fe09-157">Seleccione el vínculo **Entrenar** para ir al paso siguiente en la herramienta Generador de modelos.</span><span class="sxs-lookup"><span data-stu-id="5fe09-157">Select the **Train** link to move to the next step in the Model Builder tool.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="5fe09-158">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="5fe09-158">Train the model</span></span>

<span data-ttu-id="5fe09-159">La tarea de aprendizaje automático que se usa para entrenar el modelo de predicción de precio en este tutorial es la clasificación binaria.</span><span class="sxs-lookup"><span data-stu-id="5fe09-159">The machine learning task used to train the price prediction model in this tutorial is binary classification.</span></span> <span data-ttu-id="5fe09-160">Durante el proceso de entrenamiento de modelos, el Generador de modelos entrena modelos independientes con diferentes opciones y algoritmos de clasificación binaria para encontrar el modelo con mejor rendimiento para el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="5fe09-160">During the model training process, Model Builder trains separate models using different binary classification algorithms and settings to find the best performing model for your dataset.</span></span>

<span data-ttu-id="5fe09-161">El tiempo necesario para el entrenamiento del modelo es proporcional a la cantidad de datos.</span><span class="sxs-lookup"><span data-stu-id="5fe09-161">The time required for the model to train is proportionate to the amount of data.</span></span> <span data-ttu-id="5fe09-162">El generador de modelos selecciona automáticamente un valor predeterminado para **Tiempo de entrenamiento (segundos)** en función del tamaño del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="5fe09-162">Model Builder automatically selects a default value for **Time to train (seconds)** based on the size of your data source.</span></span>

1. <span data-ttu-id="5fe09-163">Aunque el Generador de modelos establezca el valor de **Tiempo de entrenamiento (segundos)** en 10 segundos, debe aumentarlo a 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="5fe09-163">Although Model Builder sets the value of **Time to train (seconds)** to 10 seconds, increase it to 30 seconds.</span></span> <span data-ttu-id="5fe09-164">El entrenamiento durante un período de tiempo más prolongado permite que el Generador de modelos explore un mayor número de algoritmos y combinación de parámetros en la búsqueda del mejor modelo.</span><span class="sxs-lookup"><span data-stu-id="5fe09-164">Training for a longer period of time allows Model Builder to explore a larger number of algorithms and combination of parameters in search of the best model.</span></span>
1. <span data-ttu-id="5fe09-165">Seleccione **Iniciar entrenamiento**.</span><span class="sxs-lookup"><span data-stu-id="5fe09-165">Select **Start Training**.</span></span>

    <span data-ttu-id="5fe09-166">Durante el proceso de entrenamiento, los datos de progreso se muestran en la sección `Progress` del paso de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="5fe09-166">Throughout the training process, progress data is displayed in the `Progress` section of the train step.</span></span>

    - <span data-ttu-id="5fe09-167">En Estado se muestra el grado de finalización del proceso de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="5fe09-167">Status displays the completion status of the training process.</span></span>
    - <span data-ttu-id="5fe09-168">En Mejor precisión se muestra la precisión del modelo con mejor rendimiento que ha encontrado el Generador de modelos hasta el momento.</span><span class="sxs-lookup"><span data-stu-id="5fe09-168">Best accuracy displays the accuracy of the best performing model found by Model Builder so far.</span></span> <span data-ttu-id="5fe09-169">Una mayor precisión significa que el modelo realiza una predicción más correcta de los datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="5fe09-169">Higher accuracy means the model predicted more correctly on test data.</span></span>
    - <span data-ttu-id="5fe09-170">En Mejor algoritmo se muestra el nombre del algoritmo con mejor rendimiento que ha encontrado el Generador de modelos hasta el momento.</span><span class="sxs-lookup"><span data-stu-id="5fe09-170">Best algorithm displays the name of the best performing algorithm performed found by Model Builder so far.</span></span>
    - <span data-ttu-id="5fe09-171">En Último algoritmo se muestra el nombre del algoritmo que ha usado más recientemente el Generador de modelos para entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="5fe09-171">Last algorithm displays the name of the algorithm most recently used by Model Builder to train the model.</span></span>

1. <span data-ttu-id="5fe09-172">Una vez que se complete el entrenamiento, seleccione el vínculo de **evaluación** para ir al paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="5fe09-172">Once training is complete, select the **evaluate** link to move to the next step.</span></span>

## <a name="evaluate-the-model"></a><span data-ttu-id="5fe09-173">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="5fe09-173">Evaluate the model</span></span>

<span data-ttu-id="5fe09-174">El resultado del paso de entrenamiento será un modelo que tenga el mejor rendimiento.</span><span class="sxs-lookup"><span data-stu-id="5fe09-174">The result of the training step will be one model which had the best performance.</span></span> <span data-ttu-id="5fe09-175">En el paso de evaluación de la herramienta Generador de modelos, la sección de salida contendrá el algoritmo usado por el modelo con el mejor rendimiento en la entrada **Mejor modelo** junto con las métricas en **Modelo de mayor calidad (RSquared)** .</span><span class="sxs-lookup"><span data-stu-id="5fe09-175">In the evaluate step of the Model Builder tool, the output section, will contain the algorithm used by the best performing model in the **Best Model** entry along with metrics in **Best Model Quality (RSquared)**.</span></span> <span data-ttu-id="5fe09-176">Además de una tabla resumen que contiene los cinco mejores modelos y sus métricas.</span><span class="sxs-lookup"><span data-stu-id="5fe09-176">Additionally, a summary table containing top five models and their metrics.</span></span>

<span data-ttu-id="5fe09-177">Si no está satisfecho con las métricas de precisión, una forma sencilla de intentar mejorar la precisión del modelo es aumentar la cantidad de tiempo para entrenar el modelo o usar más datos.</span><span class="sxs-lookup"><span data-stu-id="5fe09-177">If you're not satisfied with your accuracy metrics, some easy ways to try and improve model accuracy are to increase the amount of time to train the model or use more data.</span></span> <span data-ttu-id="5fe09-178">En caso contrario, seleccione el vínculo de **código** para ir al paso final de la herramienta Generador de modelos.</span><span class="sxs-lookup"><span data-stu-id="5fe09-178">Otherwise, select the **code** link to move to the final step in the Model Builder tool.</span></span>

## <a name="add-the-code-to-make-predictions"></a><span data-ttu-id="5fe09-179">Incorporación del código para hacer predicciones</span><span class="sxs-lookup"><span data-stu-id="5fe09-179">Add the code to make predictions</span></span>

<span data-ttu-id="5fe09-180">Se crearán dos proyectos como resultado del proceso de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="5fe09-180">Two projects will be created as a result of the training process.</span></span>

### <a name="reference-the-trained-model"></a><span data-ttu-id="5fe09-181">Referencia al modelo entrenado</span><span class="sxs-lookup"><span data-stu-id="5fe09-181">Reference the trained model</span></span>

1. <span data-ttu-id="5fe09-182">En el paso de *código* de la herramienta Generador de modelos, seleccione **Agregar proyectos** para agregar los proyectos generados automáticamente a la solución.</span><span class="sxs-lookup"><span data-stu-id="5fe09-182">In the *code* step of the Model Builder tool, select **Add Projects** to add the autogenerated projects to the solution.</span></span>

    <span data-ttu-id="5fe09-183">Los proyectos siguientes deben aparecer en el **Explorador de soluciones**:</span><span class="sxs-lookup"><span data-stu-id="5fe09-183">The following projects should appear in the **Solution Explorer**:</span></span>

    - <span data-ttu-id="5fe09-184">*SentimentRazorML.ConsoleApp*: una aplicación de consola de .NET Core que contiene el entrenamiento del modelo y el código de predicción.</span><span class="sxs-lookup"><span data-stu-id="5fe09-184">*SentimentRazorML.ConsoleApp*: A .NET Core Console application that contains the model training and prediction code.</span></span>
    - <span data-ttu-id="5fe09-185">*SentimentRazorML.Model*: Una biblioteca de clases .NET Standard que contienen los modelos de datos que definen el esquema de entrada y salida de los datos del modelo, así como la versión guardada del modelo con mejor rendimiento durante el entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="5fe09-185">*SentimentRazorML.Model*: A .NET Standard class library containing the data models that define the schema of input and output model data as well as the saved version of the best performing model during training.</span></span>

    <span data-ttu-id="5fe09-186">En este tutorial, solo se usa el proyecto *SentimentRazorML.Model*, porque las predicciones se realizarán en la aplicación web *SentimentRazor* en lugar de hacerlo en la consola.</span><span class="sxs-lookup"><span data-stu-id="5fe09-186">For this tutorial, only the *SentimentRazorML.Model* project is used because predictions will be made in the *SentimentRazor* web application rather than in the console.</span></span> <span data-ttu-id="5fe09-187">Aunque *SentimentRazorML.ConsoleApp* no se usará para la puntuación, se puede usar para volver a entrenar el modelo con datos nuevos más adelante.</span><span class="sxs-lookup"><span data-stu-id="5fe09-187">Although the *SentimentRazorML.ConsoleApp* won't be used for scoring, it can be used to retrain the model using new data at a later time.</span></span> <span data-ttu-id="5fe09-188">No obstante, el reentrenamiento queda fuera del ámbito de este tutorial.</span><span class="sxs-lookup"><span data-stu-id="5fe09-188">Retraining is outside the scope of this tutorial though.</span></span>

### <a name="configure-the-predictionengine-pool"></a><span data-ttu-id="5fe09-189">Configuración del grupo PredictionEngine</span><span class="sxs-lookup"><span data-stu-id="5fe09-189">Configure the PredictionEngine pool</span></span>

<span data-ttu-id="5fe09-190">Para hacer una sola predicción, debe crear un [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span><span class="sxs-lookup"><span data-stu-id="5fe09-190">To make a single prediction, you have to create a [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span></span> <span data-ttu-id="5fe09-191">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) no es seguro para subprocesos.</span><span class="sxs-lookup"><span data-stu-id="5fe09-191">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="5fe09-192">Además, tiene que crear una instancia de ella en cualquier lugar en que se necesite dentro de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5fe09-192">Additionally, you have to create an instance of it everywhere it is needed within your application.</span></span> <span data-ttu-id="5fe09-193">A medida que crece la aplicación, este proceso puede volverse difícil de administrar.</span><span class="sxs-lookup"><span data-stu-id="5fe09-193">As your application grows, this process can become unmanageable.</span></span> <span data-ttu-id="5fe09-194">Para mejorar el rendimiento y la seguridad para subprocesos, use una combinación de inserción de dependencias y el servicio `PredictionEnginePool`, que crea un [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) de objetos de [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) para su uso en toda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5fe09-194">For improved performance and thread safety, use a combination of dependency injection and the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span>

1. <span data-ttu-id="5fe09-195">Instale el paquete *Microsoft.Extensions.ML* de NuGet:</span><span class="sxs-lookup"><span data-stu-id="5fe09-195">Install the *Microsoft.Extensions.ML* NuGet package:</span></span>

    1. <span data-ttu-id="5fe09-196">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="5fe09-196">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span>
    1. <span data-ttu-id="5fe09-197">Elija "nuget.org" como origen del paquete.</span><span class="sxs-lookup"><span data-stu-id="5fe09-197">Choose "nuget.org" as the Package source.</span></span>
    1. <span data-ttu-id="5fe09-198">Seleccione la pestaña **Examinar** y busque **Microsoft.Extensions.ML**.</span><span class="sxs-lookup"><span data-stu-id="5fe09-198">Select the **Browse** tab and search for **Microsoft.Extensions.ML**.</span></span>
    1. <span data-ttu-id="5fe09-199">Seleccione el paquete en la lista y haga clic en el botón **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="5fe09-199">Select the package in the list, and select the **Install** button.</span></span>
    1. <span data-ttu-id="5fe09-200">Haga clic en el botón **Aceptar** en el cuadro de diálogo **Vista previa de los cambios**.</span><span class="sxs-lookup"><span data-stu-id="5fe09-200">Select the **OK** button on the **Preview Changes** dialog</span></span>
    1. <span data-ttu-id="5fe09-201">Haga clic en el botón **Acepto** en el cuadro de diálogo **Aceptación de la licencia** si está de acuerdo con los términos de licencia de los paquetes que aparecen.</span><span class="sxs-lookup"><span data-stu-id="5fe09-201">Select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="5fe09-202">Abra el archivo *Startup.cs* en el proyecto *SentimentRazor*.</span><span class="sxs-lookup"><span data-stu-id="5fe09-202">Open the *Startup.cs* file in the *SentimentRazor* project.</span></span>
1. <span data-ttu-id="5fe09-203">Agregue las instrucciones USING siguientes para hacer referencia al paquete de NuGet *Microsoft.Extensions.ML* y al proyecto *SentimentRazorML.Model*:</span><span class="sxs-lookup"><span data-stu-id="5fe09-203">Add the following using statements to reference the *Microsoft.Extensions.ML* NuGet package and *SentimentRazorML.Model* project:</span></span>

    [!code-csharp [StartupUsings](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Startup.cs#L12-L14)]

1. <span data-ttu-id="5fe09-204">Cree una variable global para almacenar la ubicación del archivo del modelo entrenado.</span><span class="sxs-lookup"><span data-stu-id="5fe09-204">Create a global variable to store the location of the trained model file.</span></span>

    [!code-csharp [ModelPath](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Startup.cs#L20)]

1. <span data-ttu-id="5fe09-205">El archivo del modelo se almacena en el directorio de compilación junto con los archivos de ensamblado de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5fe09-205">The model file is stored in the build directory alongside the assembly files of your application.</span></span> <span data-ttu-id="5fe09-206">Para facilitar el acceso, cree un método auxiliar llamado `GetAbsolutePath` después del método `Configure`.</span><span class="sxs-lookup"><span data-stu-id="5fe09-206">To make it easier to access, create a helper method called `GetAbsolutePath` after the `Configure` method</span></span>

    [!code-csharp [GetAbsolutePathMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Startup.cs#L66-L73)]

1. <span data-ttu-id="5fe09-207">Use el método `GetAbsolutePath` en el constructor de la clase `Startup` para establecer el `_modelPath`.</span><span class="sxs-lookup"><span data-stu-id="5fe09-207">Use the `GetAbsolutePath` method in the `Startup` class constructor to set the `_modelPath`.</span></span>

    [!code-csharp [InitModelPath](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Startup.cs#L25)]

1. <span data-ttu-id="5fe09-208">Configure `PredictionEnginePool` para la aplicación en el método `ConfigureServices`:</span><span class="sxs-lookup"><span data-stu-id="5fe09-208">Configure the `PredictionEnginePool` for your application in the `ConfigureServices` method:</span></span>

    [!code-csharp [InitPredEnginePool](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Startup.cs#L42)]

### <a name="create-sentiment-analysis-handler"></a><span data-ttu-id="5fe09-209">Creación de un controlador de análisis de sentimiento</span><span class="sxs-lookup"><span data-stu-id="5fe09-209">Create sentiment analysis handler</span></span>

<span data-ttu-id="5fe09-210">Las predicciones se realizarán dentro de la página principal de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5fe09-210">Predictions will be made inside the main page of the application.</span></span> <span data-ttu-id="5fe09-211">Por tanto, se necesita un método que tome las entradas del usuario y use `PredictionEnginePool` para devolver una predicción.</span><span class="sxs-lookup"><span data-stu-id="5fe09-211">Therefore, a method that takes the user input and uses the `PredictionEnginePool` to return a prediction needs to be added.</span></span>

1. <span data-ttu-id="5fe09-212">Abra el archivo *Index.cshtml.cs* ubicado en el directorio *Pages* y agregue las instrucciones USING siguientes:</span><span class="sxs-lookup"><span data-stu-id="5fe09-212">Open the *Index.cshtml.cs* file located in the *Pages* directory and add the following using statements:</span></span>

    [!code-csharp [IndexUsings](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L7-L8)]

    <span data-ttu-id="5fe09-213">Para usar el `PredictionEnginePool` configurado en la clase `Startup`, debe insertarlo en el constructor del modelo donde quiere usarlo.</span><span class="sxs-lookup"><span data-stu-id="5fe09-213">In order to use the `PredictionEnginePool` configured in the `Startup` class, you have to inject it into the constructor of the model where you want to use it.</span></span>

1. <span data-ttu-id="5fe09-214">Agregue una variable para hacer referencia al `PredictionEnginePool` dentro de la clase `IndexModel`.</span><span class="sxs-lookup"><span data-stu-id="5fe09-214">Add a variable to reference the `PredictionEnginePool` inside the `IndexModel` class.</span></span>

    [!code-csharp [PredEnginePool](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L14)]

1. <span data-ttu-id="5fe09-215">Cree un constructor en la clase `IndexModel` e inserte el servicio `PredictionEnginePool` en él.</span><span class="sxs-lookup"><span data-stu-id="5fe09-215">Create a constructor in the `IndexModel` class and inject the `PredictionEnginePool` service into it.</span></span>

    [!code-csharp [IndexConstructor](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L16-L19)]

1. <span data-ttu-id="5fe09-216">Cree un controlador de método que use `PredictionEnginePool` para hacer predicciones a partir de la información proporcionada por el usuario recibida desde la página web.</span><span class="sxs-lookup"><span data-stu-id="5fe09-216">Create a method handler that uses the `PredictionEnginePool` to make predictions from user input received from the web page.</span></span>

    1. <span data-ttu-id="5fe09-217">Debajo del método `OnGet`, cree un método nuevo denominado `OnGetAnalyzeSentiment`.</span><span class="sxs-lookup"><span data-stu-id="5fe09-217">Below the `OnGet` method, create a new method called `OnGetAnalyzeSentiment`</span></span>

        ```csharp
        public IActionResult OnGetAnalyzeSentiment([FromQuery] string text)
        {

        }
        ```

    1. <span data-ttu-id="5fe09-218">Dentro del método `OnGetAnalyzeSentiment`, devuelva un sentimiento *neutral* si la información ingresada por el usuario es nula o está en blanco.</span><span class="sxs-lookup"><span data-stu-id="5fe09-218">Inside the `OnGetAnalyzeSentiment` method, return *Neutral* sentiment if the input from the user is blank or null.</span></span>

        [!code-csharp [InitInput](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L28)]

    1. <span data-ttu-id="5fe09-219">Dada una entrada válida, cree una instancia nueva de `ModelInput`.</span><span class="sxs-lookup"><span data-stu-id="5fe09-219">Given a valid input, create a new instance of `ModelInput`.</span></span>

        [!code-csharp [InitInput](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L29)]

    1. <span data-ttu-id="5fe09-220">Use `PredictionEnginePool` para predecir el sentimiento.</span><span class="sxs-lookup"><span data-stu-id="5fe09-220">Use the `PredictionEnginePool` to predict sentiment.</span></span>

        [!code-csharp [MakePrediction](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L30)]

    1. <span data-ttu-id="5fe09-221">Convierta el valor `bool` de predicción en Tóxico o No tóxico con el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="5fe09-221">Convert the predicted `bool` value into toxic or not toxic with the following code.</span></span>

        [!code-csharp [ConvertPrediction](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L31)]

    1. <span data-ttu-id="5fe09-222">Por último, devuelva el sentimiento a la página web.</span><span class="sxs-lookup"><span data-stu-id="5fe09-222">Finally, return the sentiment back to the web page.</span></span>

        [!code-csharp [ReturnSentiment](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L32)]

### <a name="configure-the-web-page"></a><span data-ttu-id="5fe09-223">Configuración de la página web</span><span class="sxs-lookup"><span data-stu-id="5fe09-223">Configure the web page</span></span>

<span data-ttu-id="5fe09-224">Los resultados que devuelve el `OnGetAnalyzeSentiment` se mostrarán de manera dinámica en la página web `Index`.</span><span class="sxs-lookup"><span data-stu-id="5fe09-224">The results returned by the `OnGetAnalyzeSentiment` will be dynamically displayed on the `Index` web page.</span></span>

1. <span data-ttu-id="5fe09-225">Abra el archivo *Index.cshtml* del directorio *Pages* y reemplace su contenido por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="5fe09-225">Open the *Index.cshtml* file in the *Pages* directory and replace its contents with the following code:</span></span>

    [!code-cshtml [IndexPage](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml)]

1. <span data-ttu-id="5fe09-226">A continuación, agregue el código de estilo CSS al final de la página *site.css* en el directorio *wwwroot\css*:</span><span class="sxs-lookup"><span data-stu-id="5fe09-226">Next, add css styling code to the end of the *site.css* page in the *wwwroot\css* directory:</span></span>

    [!code-css [CssStyling](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/css/site.css#L61-L105)]

1. <span data-ttu-id="5fe09-227">Después, agregue código para enviar entradas desde la página web al controlador `OnGetAnalyzeSentiment`.</span><span class="sxs-lookup"><span data-stu-id="5fe09-227">After that, add code to send inputs from the web page to the `OnGetAnalyzeSentiment` handler.</span></span>

    1. <span data-ttu-id="5fe09-228">En el archivo *site.js* que se encuentra en el directorio *wwwroot\js*, cree una función llamada `getSentiment` para realizar una solicitud HTTP GET con la entrada del usuario al controlador `OnGetAnalyzeSentiment`.</span><span class="sxs-lookup"><span data-stu-id="5fe09-228">In the *site.js* file located in the *wwwroot\js* directory, create a function called `getSentiment` to make a GET HTTP request with the user input to the `OnGetAnalyzeSentiment` handler.</span></span>

        [!code-javascript [GetSentimentMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L5-L10)]

    1. <span data-ttu-id="5fe09-229">A continuación, agregue otra función llamada `updateMarker` para actualizar dinámicamente la posición del marcador en la página web cuando se predice el sentimiento.</span><span class="sxs-lookup"><span data-stu-id="5fe09-229">Below that, add another function called `updateMarker` to dynamically update the position of the marker on the web page as sentiment is predicted.</span></span>

        [!code-javascript [UpdateMarkerMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L12-L15)]

    1. <span data-ttu-id="5fe09-230">Cree una función de controlador de eventos llamada `updateSentiment` para obtener la entrada del usuario, envíela a la función `OnGetAnalyzeSentiment` mediante la función `getSentiment` y actualice el marcador con la función `updateMarker`.</span><span class="sxs-lookup"><span data-stu-id="5fe09-230">Create an event handler function called `updateSentiment` to get the input from the user, send it to the `OnGetAnalyzeSentiment` function using the `getSentiment` function and update the marker with the `updateMarker` function.</span></span>

        [!code-javascript [UpdateSentimentMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L17-L34)]

    1. <span data-ttu-id="5fe09-231">Por último, registre el controlador de eventos y enlácelo al elemento `textarea` con el atributo `id=Message`.</span><span class="sxs-lookup"><span data-stu-id="5fe09-231">Finally, register the event handler and bind it to the `textarea` element with the `id=Message` attribute.</span></span>

        [!code-javascript [UpdateSentimentEvtHandler](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L36)]

## <a name="run-the-application"></a><span data-ttu-id="5fe09-232">Ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="5fe09-232">Run the application</span></span>

<span data-ttu-id="5fe09-233">Ahora que la aplicación está configurada, ejecútela. Debería iniciarse en el explorador.</span><span class="sxs-lookup"><span data-stu-id="5fe09-233">Now that your application is set up, run the application which should launch in your browser.</span></span>

<span data-ttu-id="5fe09-234">Cuando se inicie la aplicación, escriba *¡El Generador de modelos es genial!*</span><span class="sxs-lookup"><span data-stu-id="5fe09-234">When the application launches, enter *Model Builder is cool!*</span></span> <span data-ttu-id="5fe09-235">en el área de texto.</span><span class="sxs-lookup"><span data-stu-id="5fe09-235">into the text area.</span></span> <span data-ttu-id="5fe09-236">El sentimiento de predicción que aparece debe ser *Not Toxic* (No tóxico).</span><span class="sxs-lookup"><span data-stu-id="5fe09-236">The predicted sentiment displayed should be *Not Toxic*.</span></span>

![Ventana en ejecución con la ventana de sentimiento de predicción](./media/sentiment-analysis-model-builder/web-app.png)

<span data-ttu-id="5fe09-238">Si tiene que hacer referencia a los proyectos generados por el Generador de modelos más adelante en otra solución, puede encontrarlos en el directorio `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools`.</span><span class="sxs-lookup"><span data-stu-id="5fe09-238">If you need to reference the Model Builder generated projects at a later time inside of another solution, you can find them inside the `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools` directory.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5fe09-239">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="5fe09-239">Next steps</span></span>

<span data-ttu-id="5fe09-240">En este tutorial ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="5fe09-240">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="5fe09-241">Crear una aplicación Razor Pages de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="5fe09-241">Create an ASP.NET Core Razor Pages application</span></span>
> - <span data-ttu-id="5fe09-242">Preparar y entender los datos</span><span class="sxs-lookup"><span data-stu-id="5fe09-242">Prepare and understand the data</span></span>
> - <span data-ttu-id="5fe09-243">Elección de un escenario</span><span class="sxs-lookup"><span data-stu-id="5fe09-243">Choose a scenario</span></span>
> - <span data-ttu-id="5fe09-244">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="5fe09-244">Load the data</span></span>
> - <span data-ttu-id="5fe09-245">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="5fe09-245">Train the model</span></span>
> - <span data-ttu-id="5fe09-246">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="5fe09-246">Evaluate the model</span></span>
> - <span data-ttu-id="5fe09-247">Usar el modelo para las predicciones</span><span class="sxs-lookup"><span data-stu-id="5fe09-247">Use the model for predictions</span></span>

### <a name="additional-resources"></a><span data-ttu-id="5fe09-248">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="5fe09-248">Additional Resources</span></span>

<span data-ttu-id="5fe09-249">Para más información sobre los temas mencionados en este tutorial, visite estos recursos:</span><span class="sxs-lookup"><span data-stu-id="5fe09-249">To learn more about topics mentioned in this tutorial, visit the following resources:</span></span>

- [<span data-ttu-id="5fe09-250">Escenarios del Generador de modelos</span><span class="sxs-lookup"><span data-stu-id="5fe09-250">Model Builder Scenarios</span></span>](../automate-training-with-model-builder.md#scenarios)
- [<span data-ttu-id="5fe09-251">Clasificación binaria</span><span class="sxs-lookup"><span data-stu-id="5fe09-251">Binary Classification</span></span>](../resources/glossary.md#binary-classification)
- [<span data-ttu-id="5fe09-252">Métricas del modelo de clasificación binaria</span><span class="sxs-lookup"><span data-stu-id="5fe09-252">Binary Classification Model Metrics</span></span>](../resources/metrics.md#metrics-for-binary-classification)
