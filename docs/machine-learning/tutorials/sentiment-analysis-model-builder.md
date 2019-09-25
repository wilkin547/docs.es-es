---
title: 'Tutorial: Análisis de sentimiento: clasificación binaria'
description: En este tutorial se muestra cómo crear una aplicación Razor Pages que clasifica los sentimientos de los comentarios del sitio web y toma las medidas oportunas. El clasificador binario de sentimientos usa el Generador de modelos en Visual Studio.
ms.date: 09/13/2019
author: luisquintanilla
ms.author: luquinta
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: c6184e097daf4604173db9e2a34606e68eb0fdc8
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71054277"
---
# <a name="tutorial-analyze-sentiment-of-website-comments-in-a-web-application-using-mlnet-model-builder"></a><span data-ttu-id="a294c-104">Tutorial: Análisis del sentimiento de los comentarios del sitio web en una aplicación web con el Generador de modelos de ML.NET</span><span class="sxs-lookup"><span data-stu-id="a294c-104">Tutorial: Analyze sentiment of website comments in a web application using ML.NET Model Builder</span></span>

<span data-ttu-id="a294c-105">Aprenda a analizar el sentimiento de los comentarios en tiempo real dentro de una aplicación web.</span><span class="sxs-lookup"><span data-stu-id="a294c-105">Learn how to analyze sentiment from comments in real-time inside a web application.</span></span>

<span data-ttu-id="a294c-106">En este tutorial se muestra cómo crear una aplicación Razor Pages de ASP.NET Core que clasifica los sentimientos de los comentarios del sitio web en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="a294c-106">This tutorial shows you how to create an ASP.NET Core Razor Pages application that classifies sentiment from website comments in real-time.</span></span>

<span data-ttu-id="a294c-107">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="a294c-107">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="a294c-108">Crear una aplicación Razor Pages de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a294c-108">Create an ASP.NET Core Razor Pages application</span></span>
> * <span data-ttu-id="a294c-109">Preparar y entender los datos</span><span class="sxs-lookup"><span data-stu-id="a294c-109">Prepare and understand the data</span></span>
> * <span data-ttu-id="a294c-110">Elección de un escenario</span><span class="sxs-lookup"><span data-stu-id="a294c-110">Choose a scenario</span></span>
> * <span data-ttu-id="a294c-111">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="a294c-111">Load the data</span></span>
> * <span data-ttu-id="a294c-112">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="a294c-112">Train the model</span></span>
> * <span data-ttu-id="a294c-113">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="a294c-113">Evaluate the model</span></span>
> * <span data-ttu-id="a294c-114">Usar el modelo para las predicciones</span><span class="sxs-lookup"><span data-stu-id="a294c-114">Use the model for predictions</span></span>

> [!NOTE]
> <span data-ttu-id="a294c-115">De momento, el Generador de modelos se encuentra en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="a294c-115">Model Builder is currently in Preview.</span></span>

<span data-ttu-id="a294c-116">Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples).</span><span class="sxs-lookup"><span data-stu-id="a294c-116">You can find the source code for this tutorial at the [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples) repository.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="a294c-117">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a294c-117">Pre-requisites</span></span>

<span data-ttu-id="a294c-118">Para obtener una lista de los requisitos previos e instrucciones de instalación, visite la [Guía de instalación del Generador de modelos](../how-to-guides/install-model-builder.md).</span><span class="sxs-lookup"><span data-stu-id="a294c-118">For a list of pre-requisites and installation instructions, visit the [Model Builder installation guide](../how-to-guides/install-model-builder.md).</span></span>

## <a name="create-a-razor-pages-application"></a><span data-ttu-id="a294c-119">Creación de una aplicación Razor Pages</span><span class="sxs-lookup"><span data-stu-id="a294c-119">Create a Razor Pages application</span></span>

1. <span data-ttu-id="a294c-120">Cree una **aplicación Razor Pages de ASP.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="a294c-120">Create a **ASP.NET Core Razor Pages Application**.</span></span>

    1. <span data-ttu-id="a294c-121">Abra Visual Studio y seleccione **Archivo > Nuevo > Proyecto** en la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="a294c-121">Open Visual Studio and select **File > New > Project** from the menu bar.</span></span> 
    1. <span data-ttu-id="a294c-122">En el cuadro de diálogo Nuevo proyecto, seleccione el nodo **Visual C#** seguido del nodo **Web**.</span><span class="sxs-lookup"><span data-stu-id="a294c-122">In the New Project dialog, select the **Visual C#** node followed by the **Web** node.</span></span> 
    1. <span data-ttu-id="a294c-123">Seleccione la plantilla de proyecto **Aplicación web de ASP.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="a294c-123">Then select the **ASP.NET Core Web Application** project template.</span></span> 
    1. <span data-ttu-id="a294c-124">En el cuadro de texto **Nombre**, escriba "SentimentRazor".</span><span class="sxs-lookup"><span data-stu-id="a294c-124">In the **Name** text box, type "SentimentRazor".</span></span>
    1. <span data-ttu-id="a294c-125">La casilla **Create a directory for solution** (Crear un directorio para la solución) debe estar activada de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a294c-125">The **Create a directory for solution** checkbox should be checked by default.</span></span> <span data-ttu-id="a294c-126">Si no es así, actívela.</span><span class="sxs-lookup"><span data-stu-id="a294c-126">If that's not the case, check it.</span></span> 
    1. <span data-ttu-id="a294c-127">Seleccione el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a294c-127">Select the **OK** button.</span></span>
    1. <span data-ttu-id="a294c-128">Elija **Aplicación web** en la ventana que muestra los distintos tipos de proyectos de ASP.NET Core y, luego, haga clic en el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a294c-128">Choose **Web Application** in the window that displays the different types of ASP.NET Core Projects, and then select the **OK** button.</span></span>

## <a name="prepare-and-understand-the-data"></a><span data-ttu-id="a294c-129">Preparar y entender los datos</span><span class="sxs-lookup"><span data-stu-id="a294c-129">Prepare and understand the data</span></span>

<span data-ttu-id="a294c-130">Descargue el [conjunto de datos detox de Wikipedia](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/wikipedia-detox-250-line-data.tsv).</span><span class="sxs-lookup"><span data-stu-id="a294c-130">Download [Wikipedia detox dataset](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/wikipedia-detox-250-line-data.tsv).</span></span> <span data-ttu-id="a294c-131">Cuando se abra la página web, haga clic con el botón derecho en la página, seleccione **Guardar como** y guarde el archivo en cualquier parte del equipo.</span><span class="sxs-lookup"><span data-stu-id="a294c-131">When the webpage opens, right-click on the page, select **Save As** and save the file anywhere on your computer.</span></span> 

<span data-ttu-id="a294c-132">Cada fila del conjunto de datos *wikipedia-detox-250-line-data.tsv* presenta una opinión distinta que un usuario deja en Wikipedia.</span><span class="sxs-lookup"><span data-stu-id="a294c-132">Each row in the *wikipedia-detox-250-line-data.tsv* dataset represents a different review left by a user on Wikipedia.</span></span> <span data-ttu-id="a294c-133">La primera columna representa el sentimiento del texto (0 indica no tóxico, 1 indica tóxico) y la segunda columna representa el comentario que deja el usuario.</span><span class="sxs-lookup"><span data-stu-id="a294c-133">The first column represents the sentiment of the text (0 is non-toxic, 1 is toxic), and the second column represents the comment left by the user.</span></span> <span data-ttu-id="a294c-134">Las columnas están separadas por tabulaciones.</span><span class="sxs-lookup"><span data-stu-id="a294c-134">The columns are separated by tabs.</span></span> <span data-ttu-id="a294c-135">Los datos tienen un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="a294c-135">The data looks like the following:</span></span>

| <span data-ttu-id="a294c-136">Opinión</span><span class="sxs-lookup"><span data-stu-id="a294c-136">Sentiment</span></span> | <span data-ttu-id="a294c-137">SentimentText</span><span class="sxs-lookup"><span data-stu-id="a294c-137">SentimentText</span></span> |
| :---: | :---: |
<span data-ttu-id="a294c-138">1</span><span class="sxs-lookup"><span data-stu-id="a294c-138">1</span></span> | <span data-ttu-id="a294c-139">==RUDE== Dude, you are rude upload that carl picture back, or else. (Oye, vuelve a subir esa foto de Carl o te las verás conmigo).</span><span class="sxs-lookup"><span data-stu-id="a294c-139">==RUDE== Dude, you are rude upload that carl picture back, or else.</span></span>
<span data-ttu-id="a294c-140">1</span><span class="sxs-lookup"><span data-stu-id="a294c-140">1</span></span> | <span data-ttu-id="a294c-141">== OK!</span><span class="sxs-lookup"><span data-stu-id="a294c-141">== OK!</span></span> <span data-ttu-id="a294c-142">==  IM GOING TO VANDALIZE WILD ONES WIKI THEN!!! (BUENO, ENTONCES VOY A VANDALIZAR ALGUNAS WIKI).</span><span class="sxs-lookup"><span data-stu-id="a294c-142">==  IM GOING TO VANDALIZE WILD ONES WIKI THEN!!!</span></span>
<span data-ttu-id="a294c-143">0</span><span class="sxs-lookup"><span data-stu-id="a294c-143">0</span></span> | <span data-ttu-id="a294c-144">I hope this helps. (Espero que esto ayude).</span><span class="sxs-lookup"><span data-stu-id="a294c-144">I hope this helps.</span></span>

## <a name="choose-a-scenario"></a><span data-ttu-id="a294c-145">Elección de un escenario</span><span class="sxs-lookup"><span data-stu-id="a294c-145">Choose a scenario</span></span>

![](./media/sentiment-analysis-model-builder/model-builder-screen.png)

<span data-ttu-id="a294c-146">Para entrenar el modelo, deberá seleccionarlo en la lista de escenarios de aprendizaje automático disponibles proporcionada por el Generador de modelos.</span><span class="sxs-lookup"><span data-stu-id="a294c-146">To train your model, you need to select from the list of available machine learning scenarios provided by Model Builder.</span></span> 

1. <span data-ttu-id="a294c-147">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto *SentimentRazor* y seleccione **Agregar** > **Machine Learning**.</span><span class="sxs-lookup"><span data-stu-id="a294c-147">In **Solution Explorer**, right-click the *SentimentRazor* project, and select **Add** > **Machine Learning**.</span></span>
1. <span data-ttu-id="a294c-148">En este ejemplo, el escenario es el análisis de sentimiento.</span><span class="sxs-lookup"><span data-stu-id="a294c-148">For this sample, the scenario is sentiment analysis.</span></span> <span data-ttu-id="a294c-149">En el paso *Escenario* de la herramienta Generador de modelos, seleccione el escenario **Análisis de sentimiento**.</span><span class="sxs-lookup"><span data-stu-id="a294c-149">In the *scenario* step of the Model Builder tool, select the **Sentiment Analysis** scenario.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="a294c-150">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="a294c-150">Load the data</span></span>

<span data-ttu-id="a294c-151">El Generador de modelos acepta datos de dos orígenes, una base de datos de SQL Server o un archivo local en formato `csv` o `tsv`.</span><span class="sxs-lookup"><span data-stu-id="a294c-151">Model Builder accepts data from two sources, a SQL Server database or a local file in `csv` or `tsv` format.</span></span>

1. <span data-ttu-id="a294c-152">En el paso de datos de la herramienta Generador de modelos, seleccione **Archivo** en la lista desplegable origen de datos.</span><span class="sxs-lookup"><span data-stu-id="a294c-152">In the data step of the Model Builder tool, select **File** from the data source dropdown.</span></span>
1. <span data-ttu-id="a294c-153">Seleccione el botón junto al cuadro de texto **Seleccionar un archivo** y use el Explorador de archivos para examinar y seleccionar el archivo *wikipedia-detox-250-line-data.tsv*.</span><span class="sxs-lookup"><span data-stu-id="a294c-153">Select the button next to the **Select a file** text box and use File Explorer to browse and select the *wikipedia-detox-250-line-data.tsv* file.</span></span>
1. <span data-ttu-id="a294c-154">Elija **Sentimiento** en el menú desplegable **Etiqueta o columna para la predicción**.</span><span class="sxs-lookup"><span data-stu-id="a294c-154">Choose **Sentiment** in the **Label or Column to Predict** dropdown</span></span>
1. <span data-ttu-id="a294c-155">Seleccione el vínculo **Entrenar** para ir al paso siguiente en la herramienta Generador de modelos.</span><span class="sxs-lookup"><span data-stu-id="a294c-155">Select the **Train** link to move to the next step in the Model Builder tool.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="a294c-156">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="a294c-156">Train the model</span></span>

<span data-ttu-id="a294c-157">La tarea de aprendizaje automático que se usa para entrenar el modelo de predicción de precio en este tutorial es la clasificación binaria.</span><span class="sxs-lookup"><span data-stu-id="a294c-157">The machine learning task used to train the price prediction model in this tutorial is binary classification.</span></span> <span data-ttu-id="a294c-158">Durante el proceso de entrenamiento de modelos, el Generador de modelos entrena modelos independientes con diferentes opciones y algoritmos de clasificación binaria para encontrar el modelo con mejor rendimiento para el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="a294c-158">During the model training process, Model Builder trains separate models using different binary classification algorithms and settings to find the best performing model for your dataset.</span></span>

<span data-ttu-id="a294c-159">El tiempo necesario para el entrenamiento del modelo es proporcional a la cantidad de datos.</span><span class="sxs-lookup"><span data-stu-id="a294c-159">The time required for the model to train is proportionate to the amount of data.</span></span> <span data-ttu-id="a294c-160">El generador de modelos selecciona automáticamente un valor predeterminado para **Tiempo de entrenamiento (segundos)** en función del tamaño del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="a294c-160">Model Builder automatically selects a default value for **Time to train (seconds)** based on the size of your data source.</span></span> 

1. <span data-ttu-id="a294c-161">Aunque el Generador de modelos establezca el valor de **Tiempo de entrenamiento (segundos)** en 10 segundos, debe aumentarlo a 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="a294c-161">Although Model Builder sets the value of **Time to train (seconds)** to 10 seconds, increase it to 30 seconds.</span></span> <span data-ttu-id="a294c-162">El entrenamiento durante un período de tiempo más prolongado permite que el Generador de modelos explore un mayor número de algoritmos y combinación de parámetros en la búsqueda del mejor modelo.</span><span class="sxs-lookup"><span data-stu-id="a294c-162">Training for a longer period of time allows Model Builder to explore a larger number of algorithms and combination of parameters in search of the best model.</span></span>
1. <span data-ttu-id="a294c-163">Seleccione **Iniciar entrenamiento**.</span><span class="sxs-lookup"><span data-stu-id="a294c-163">Select **Start Training**.</span></span>

    <span data-ttu-id="a294c-164">Durante el proceso de entrenamiento, los datos de progreso se muestran en la sección `Progress` del paso de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="a294c-164">Throughout the training process, progress data is displayed in the `Progress` section of the train step.</span></span>

    - <span data-ttu-id="a294c-165">En Estado se muestra el grado de finalización del proceso de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="a294c-165">Status displays the completion status of the training process.</span></span>
    - <span data-ttu-id="a294c-166">En Mejor precisión se muestra la precisión del modelo con mejor rendimiento que ha encontrado el Generador de modelos hasta el momento.</span><span class="sxs-lookup"><span data-stu-id="a294c-166">Best accuracy displays the accuracy of the best performing model found by Model Builder so far.</span></span> <span data-ttu-id="a294c-167">Una mayor precisión significa que el modelo realiza una predicción más correcta de los datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="a294c-167">Higher accuracy means the model predicted more correctly on test data.</span></span>
    - <span data-ttu-id="a294c-168">En Mejor algoritmo se muestra el nombre del algoritmo con mejor rendimiento que ha encontrado el Generador de modelos hasta el momento.</span><span class="sxs-lookup"><span data-stu-id="a294c-168">Best algorithm displays the name of the best performing algorithm performed found by Model Builder so far.</span></span>
    - <span data-ttu-id="a294c-169">En Último algoritmo se muestra el nombre del algoritmo que ha usado más recientemente el Generador de modelos para entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="a294c-169">Last algorithm displays the name of the algorithm most recently used by Model Builder to train the model.</span></span>

1. <span data-ttu-id="a294c-170">Una vez que se complete el entrenamiento, seleccione el vínculo de **evaluación** para ir al paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="a294c-170">Once training is complete, select the **evaluate** link to move to the next step.</span></span>

## <a name="evaluate-the-model"></a><span data-ttu-id="a294c-171">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="a294c-171">Evaluate the model</span></span>

<span data-ttu-id="a294c-172">El resultado del paso de entrenamiento será un modelo que tenga el mejor rendimiento.</span><span class="sxs-lookup"><span data-stu-id="a294c-172">The result of the training step will be one model which had the best performance.</span></span> <span data-ttu-id="a294c-173">En el paso de evaluación de la herramienta Generador de modelos, la sección de salida contendrá el algoritmo usado por el modelo con el mejor rendimiento en la entrada **Mejor modelo** junto con las métricas en **Modelo de mayor calidad (RSquared)** .</span><span class="sxs-lookup"><span data-stu-id="a294c-173">In the evaluate step of the Model Builder tool, the output section, will contain the algorithm used by the best performing model in the **Best Model** entry along with metrics in **Best Model Quality (RSquared)**.</span></span> <span data-ttu-id="a294c-174">Además de una tabla resumen que contiene los cinco mejores modelos y sus métricas.</span><span class="sxs-lookup"><span data-stu-id="a294c-174">Additionally, a summary table containing top five models and their metrics.</span></span>

<span data-ttu-id="a294c-175">Si no está satisfecho con las métricas de precisión, una forma sencilla de intentar mejorar la precisión del modelo es aumentar la cantidad de tiempo para entrenar el modelo o usar más datos.</span><span class="sxs-lookup"><span data-stu-id="a294c-175">If you're not satisfied with your accuracy metrics, some easy ways to try and improve model accuracy are to increase the amount of time to train the model or use more data.</span></span> <span data-ttu-id="a294c-176">En caso contrario, seleccione el vínculo de **código** para ir al paso final de la herramienta Generador de modelos.</span><span class="sxs-lookup"><span data-stu-id="a294c-176">Otherwise, select the **code** link to move to the final step in the Model Builder tool.</span></span>

## <a name="add-the-code-to-make-predictions"></a><span data-ttu-id="a294c-177">Incorporación del código para hacer predicciones</span><span class="sxs-lookup"><span data-stu-id="a294c-177">Add the code to make predictions</span></span>

<span data-ttu-id="a294c-178">Se crearán dos proyectos como resultado del proceso de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="a294c-178">Two projects will be created as a result of the training process.</span></span>

### <a name="reference-the-trained-model"></a><span data-ttu-id="a294c-179">Referencia al modelo entrenado</span><span class="sxs-lookup"><span data-stu-id="a294c-179">Reference the trained model</span></span>

1. <span data-ttu-id="a294c-180">En el paso de *código* de la herramienta Generador de modelos, seleccione **Agregar proyectos** para agregar los proyectos generados automáticamente a la solución.</span><span class="sxs-lookup"><span data-stu-id="a294c-180">In the *code* step of the Model Builder tool, select **Add Projects** to add the autogenerated projects to the solution.</span></span>

    <span data-ttu-id="a294c-181">Los proyectos siguientes deben aparecer en el **Explorador de soluciones**:</span><span class="sxs-lookup"><span data-stu-id="a294c-181">The following projects should appear in the **Solution Explorer**:</span></span>

    - <span data-ttu-id="a294c-182">*SentimentRazorML.ConsoleApp*: una aplicación de consola de .NET Core que contiene el entrenamiento del modelo y el código de predicción.</span><span class="sxs-lookup"><span data-stu-id="a294c-182">*SentimentRazorML.ConsoleApp*: A .NET Core Console application that contains the model training and prediction code.</span></span>
    - <span data-ttu-id="a294c-183">*SentimentRazorML.Model*: Una biblioteca de clases .NET Standard que contienen los modelos de datos que definen el esquema de entrada y salida de los datos del modelo, así como la versión persistente del modelo con mejor rendimiento durante el entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="a294c-183">*SentimentRazorML.Model*: A .NET Standard class library containing the data models that define the schema of input and output model data as well as the persisted version of the best performing model during training.</span></span>

    <span data-ttu-id="a294c-184">En este tutorial, solo se usa el proyecto *SentimentRazorML.Model*, porque las predicciones se realizarán en la aplicación web *SentimentRazor* en lugar de hacerlo en la consola.</span><span class="sxs-lookup"><span data-stu-id="a294c-184">For this tutorial, only the *SentimentRazorML.Model* project is used because predictions will be made in the *SentimentRazor* web application rather than in the console.</span></span> <span data-ttu-id="a294c-185">Aunque *SentimentRazorML.ConsoleApp* no se usará para la puntuación, se puede usar para volver a entrenar el modelo con datos nuevos más adelante.</span><span class="sxs-lookup"><span data-stu-id="a294c-185">Although the *SentimentRazorML.ConsoleApp* won't be used for scoring, it can be used to retrain the model using new data at a later time.</span></span> <span data-ttu-id="a294c-186">No obstante, el reentrenamiento queda fuera del ámbito de este tutorial.</span><span class="sxs-lookup"><span data-stu-id="a294c-186">Retraining is outside the scope of this tutorial though.</span></span>

1. <span data-ttu-id="a294c-187">Para usar el modelo entrenado dentro de la aplicación Razor Pages, agregue una referencia al proyecto *SentimentRazorML.Model*.</span><span class="sxs-lookup"><span data-stu-id="a294c-187">To use the trained model inside your Razor Pages application, add a reference to the *SentimentRazorML.Model* project.</span></span>

    1. <span data-ttu-id="a294c-188">Haga clic con el botón derecho en el proyecto **SentimentRazor**.</span><span class="sxs-lookup"><span data-stu-id="a294c-188">Right-click **SentimentRazor** project.</span></span> 
    1. <span data-ttu-id="a294c-189">Seleccione **Agregar > Referencia**.</span><span class="sxs-lookup"><span data-stu-id="a294c-189">Select **Add > Reference**.</span></span> 
    1. <span data-ttu-id="a294c-190">Elija el nodo **Proyectos > Solución** y, en la lista, active el proyecto **SentimentRazorML.Model**.</span><span class="sxs-lookup"><span data-stu-id="a294c-190">Choose the **Projects > Solution** node and from the list, check the **SentimentRazorML.Model** project.</span></span>
    1. <span data-ttu-id="a294c-191">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a294c-191">Select **OK**.</span></span>

### <a name="configure-the-predictionengine-pool"></a><span data-ttu-id="a294c-192">Configuración del grupo PredictionEngine</span><span class="sxs-lookup"><span data-stu-id="a294c-192">Configure the PredictionEngine pool</span></span>

<span data-ttu-id="a294c-193">Para realizar una sola predicción, use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span><span class="sxs-lookup"><span data-stu-id="a294c-193">To make a single prediction, use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span></span> <span data-ttu-id="a294c-194">Para poder usar [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) en la aplicación, debe crearlo cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="a294c-194">In order to use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) in your application, you must create it when it's needed.</span></span> <span data-ttu-id="a294c-195">En ese caso, un procedimiento recomendado que se debe considerar es la inserción de dependencias.</span><span class="sxs-lookup"><span data-stu-id="a294c-195">In that case, a best practice to consider is dependency injection.</span></span>

> [!WARNING]
> <span data-ttu-id="a294c-196">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) no es seguro para subprocesos.</span><span class="sxs-lookup"><span data-stu-id="a294c-196">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="a294c-197">Para mejorar el rendimiento y la seguridad para subprocesos, use el servicio `PredictionEnginePool`, que crea un [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) de objetos `PredictionEngine` para el uso de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a294c-197">For improved performance and thread safety, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of `PredictionEngine` objects for application use.</span></span> <span data-ttu-id="a294c-198">Lea la siguiente entrada de blog para obtener más información acerca de la [creación y el uso de grupos de objetos `PredictionEngine` en ASP.NET Core](https://devblogs.microsoft.com/cesardelatorre/how-to-optimize-and-run-ml-net-models-on-scalable-asp-net-core-webapis-or-web-apps/).</span><span class="sxs-lookup"><span data-stu-id="a294c-198">Read the following blog post to learn more about [creating and using `PredictionEngine` object pools in ASP.NET Core](https://devblogs.microsoft.com/cesardelatorre/how-to-optimize-and-run-ml-net-models-on-scalable-asp-net-core-webapis-or-web-apps/).</span></span> 

1. <span data-ttu-id="a294c-199">Instale el paquete *Microsoft.Extensions.ML* de NuGet:</span><span class="sxs-lookup"><span data-stu-id="a294c-199">Install the *Microsoft.Extensions.ML* NuGet package:</span></span>

    1. <span data-ttu-id="a294c-200">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="a294c-200">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span> 
    1. <span data-ttu-id="a294c-201">Elija "nuget.org" como origen del paquete.</span><span class="sxs-lookup"><span data-stu-id="a294c-201">Choose "nuget.org" as the Package source.</span></span> 
    1. <span data-ttu-id="a294c-202">Seleccione la pestaña **Examinar** y busque **Microsoft.Extensions.ML**.</span><span class="sxs-lookup"><span data-stu-id="a294c-202">Select the **Browse** tab and search for **Microsoft.Extensions.ML**.</span></span> 
    1. <span data-ttu-id="a294c-203">Seleccione el paquete en la lista y haga clic en el botón **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="a294c-203">Select the package in the list, and select the **Install** button.</span></span> 
    1. <span data-ttu-id="a294c-204">Haga clic en el botón **Aceptar** en el cuadro de diálogo **Vista previa de los cambios**.</span><span class="sxs-lookup"><span data-stu-id="a294c-204">Select the **OK** button on the **Preview Changes** dialog</span></span>
    1. <span data-ttu-id="a294c-205">Haga clic en el botón **Acepto** en el cuadro de diálogo **Aceptación de la licencia** si está de acuerdo con los términos de licencia de los paquetes que aparecen.</span><span class="sxs-lookup"><span data-stu-id="a294c-205">Select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span> 

1. <span data-ttu-id="a294c-206">Abra el archivo *Startup.cs* en el proyecto *SentimentRazor*.</span><span class="sxs-lookup"><span data-stu-id="a294c-206">Open the *Startup.cs* file in the *SentimentRazor* project.</span></span>
1. <span data-ttu-id="a294c-207">Agregue las instrucciones USING siguientes para hacer referencia al paquete de NuGet *Microsoft.Extensions.ML* y al proyecto *SentimentRazorML.Model*:</span><span class="sxs-lookup"><span data-stu-id="a294c-207">Add the following using statements to reference the *Microsoft.Extensions.ML* NuGet package and *SentimentRazorML.Model* project:</span></span>

    [!code-csharp [StartupUsings](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Startup.cs#L12-L14)]        

1. <span data-ttu-id="a294c-208">Cree una variable global para almacenar la ubicación del archivo del modelo entrenado.</span><span class="sxs-lookup"><span data-stu-id="a294c-208">Create a global variable to store the location of the trained model file.</span></span>

    [!code-csharp [ModelPath](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Startup.cs#L20)]

1. <span data-ttu-id="a294c-209">El archivo del modelo se almacena en el directorio de compilación junto con los archivos de ensamblado de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a294c-209">The model file is stored in the build directory alongside the assembly files of your application.</span></span> <span data-ttu-id="a294c-210">Para facilitar el acceso, cree un método auxiliar llamado `GetAbsolutePath` después del método `Configure`.</span><span class="sxs-lookup"><span data-stu-id="a294c-210">To make it easier to access, create a helper method called `GetAbsolutePath` after the `Configure` method</span></span>

    [!code-csharp [GetAbsolutePathMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Startup.cs#L66-L73)]

1. <span data-ttu-id="a294c-211">Use el método `GetAbsolutePath` en el constructor de la clase `Startup` para establecer el `_modelPath`.</span><span class="sxs-lookup"><span data-stu-id="a294c-211">Use the `GetAbsolutePath` method in the `Startup` class constructor to set the `_modelPath`.</span></span>

    [!code-csharp [InitModelPath](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Startup.cs#L25)]

1. <span data-ttu-id="a294c-212">Configure `PredictionEnginePool` para la aplicación en el método `ConfigureServices`:</span><span class="sxs-lookup"><span data-stu-id="a294c-212">Configure the `PredictionEnginePool` for your application in the `ConfigureServices` method:</span></span>

    [!code-csharp [InitPredEnginePool](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Startup.cs#L42)]

### <a name="create-sentiment-analysis-handler"></a><span data-ttu-id="a294c-213">Creación de un controlador de análisis de sentimiento</span><span class="sxs-lookup"><span data-stu-id="a294c-213">Create sentiment analysis handler</span></span>

<span data-ttu-id="a294c-214">Las predicciones se realizarán dentro de la página principal de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a294c-214">Predictions will be made inside the main page of the application.</span></span> <span data-ttu-id="a294c-215">Por tanto, se necesita un método que tome las entradas del usuario y use `PredictionEnginePool` para devolver una predicción.</span><span class="sxs-lookup"><span data-stu-id="a294c-215">Therefore, a method that takes the user input and uses the `PredictionEnginePool` to return a prediction needs to be added.</span></span>

1. <span data-ttu-id="a294c-216">Abra el archivo *Index.cshtml.cs* ubicado en el directorio *Pages* y agregue las instrucciones USING siguientes:</span><span class="sxs-lookup"><span data-stu-id="a294c-216">Open the *Index.cshtml.cs* file located in the *Pages* directory and add the following using statements:</span></span>

    [!code-csharp [IndexUsings](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L7-L8)]

    <span data-ttu-id="a294c-217">Para usar el `PredictionEnginePool` configurado en la clase `Startup`, debe insertarlo en el constructor del modelo donde quiere usarlo.</span><span class="sxs-lookup"><span data-stu-id="a294c-217">In order to use the `PredictionEnginePool` configured in the `Startup` class, you have to inject it into the constructor of the model where you want to use it.</span></span> 

1. <span data-ttu-id="a294c-218">Agregue una variable para hacer referencia al `PredictionEnginePool` dentro de la clase `IndexModel`.</span><span class="sxs-lookup"><span data-stu-id="a294c-218">Add a variable to reference the `PredictionEnginePool` inside the `IndexModel` class.</span></span>

    [!code-csharp [PredEnginePool](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L14)]

1. <span data-ttu-id="a294c-219">Cree un constructor en la clase `IndexModel` e inserte el servicio `PredictionEnginePool` en él.</span><span class="sxs-lookup"><span data-stu-id="a294c-219">Create a constructor in the `IndexModel` class and inject the `PredictionEnginePool` service into it.</span></span>

    [!code-csharp [IndexConstructor](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L16-L19)]

1. <span data-ttu-id="a294c-220">Cree un controlador de método que use `PredictionEnginePool` para hacer predicciones a partir de la información proporcionada por el usuario recibida desde la página web.</span><span class="sxs-lookup"><span data-stu-id="a294c-220">Create a method handler that uses the `PredictionEnginePool` to make predictions from user input received from the web page.</span></span>

    1. <span data-ttu-id="a294c-221">Debajo del método `OnGet`, cree un método nuevo denominado `OnGetAnalyzeSentiment`.</span><span class="sxs-lookup"><span data-stu-id="a294c-221">Below the `OnGet` method, create a new method called `OnGetAnalyzeSentiment`</span></span>

        ```csharp
        public IActionResult OnGetAnalyzeSentiment([FromQuery] string text)
        {

        }
        ```

    1. <span data-ttu-id="a294c-222">Dentro del método `OnGetAnalyzeSentiment`, devuelva un sentimiento *neutral* si la información ingresada por el usuario es nula o está en blanco.</span><span class="sxs-lookup"><span data-stu-id="a294c-222">Inside the `OnGetAnalyzeSentiment` method, return *Neutral* sentiment if the input from the user is blank or null.</span></span>

        [!code-csharp [InitInput](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L28)] 
    
    1. <span data-ttu-id="a294c-223">Dada una entrada válida, cree una instancia nueva de `ModelInput`.</span><span class="sxs-lookup"><span data-stu-id="a294c-223">Given a valid input, create a new instance of `ModelInput`.</span></span> 

        [!code-csharp [InitInput](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L29)] 

    1. <span data-ttu-id="a294c-224">Use `PredictionEnginePool` para predecir el sentimiento.</span><span class="sxs-lookup"><span data-stu-id="a294c-224">Use the `PredictionEnginePool` to predict sentiment.</span></span>

        [!code-csharp [MakePrediction](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L30)] 

    1. <span data-ttu-id="a294c-225">Convierta el valor `bool` de predicción en Tóxico o No tóxico con el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="a294c-225">Convert the predicted `bool` value into toxic or not toxic with the following code.</span></span>

        [!code-csharp [ConvertPrediction](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L31)]

    1. <span data-ttu-id="a294c-226">Por último, devuelva el sentimiento a la página web.</span><span class="sxs-lookup"><span data-stu-id="a294c-226">Finally, return the sentiment back to the web page.</span></span>

        [!code-csharp [ReturnSentiment](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L32)]

### <a name="configure-the-web-page"></a><span data-ttu-id="a294c-227">Configuración de la página web</span><span class="sxs-lookup"><span data-stu-id="a294c-227">Configure the web page</span></span>

<span data-ttu-id="a294c-228">Los resultados que devuelve el `OnGetAnalyzeSentiment` se mostrarán de manera dinámica en la página web `Index`.</span><span class="sxs-lookup"><span data-stu-id="a294c-228">The results returned by the `OnGetAnalyzeSentiment` will be dynamically displayed on the `Index` web page.</span></span>

1. <span data-ttu-id="a294c-229">Abra el archivo *Index.cshtml* del directorio *Pages* y reemplace su contenido por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="a294c-229">Open the *Index.cshtml* file in the *Pages* directory and replace its contents with the following code:</span></span> 

    [!code-cshtml [IndexPage](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml)]

1. <span data-ttu-id="a294c-230">A continuación, agregue el código de estilo CSS al final de la página *site.css* en el directorio *wwwroot\css*:</span><span class="sxs-lookup"><span data-stu-id="a294c-230">Next, add css styling code to the end of the *site.css* page in the *wwwroot\css* directory:</span></span>

    [!code-css [CssStyling](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/css/site.css#L61-L105)]

1. <span data-ttu-id="a294c-231">Después, agregue código para enviar entradas desde la página web al controlador `OnGetAnalyzeSentiment`.</span><span class="sxs-lookup"><span data-stu-id="a294c-231">After that, add code to send inputs from the web page to the `OnGetAnalyzeSentiment` handler.</span></span>

    1. <span data-ttu-id="a294c-232">En el archivo *site.js* que se encuentra en el directorio *wwwroot\js*, cree una función llamada `getSentiment` para realizar una solicitud HTTP GET con la entrada del usuario al controlador `OnGetAnalyzeSentiment`.</span><span class="sxs-lookup"><span data-stu-id="a294c-232">In the *site.js* file located in the *wwwroot\js* directory, create a function called `getSentiment` to make a GET HTTP request with the user input to the `OnGetAnalyzeSentiment` handler.</span></span>

        [!code-javascript [GetSentimentMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L5-L10)]

    1. <span data-ttu-id="a294c-233">A continuación, agregue otra función llamada `updateMarker` para actualizar dinámicamente la posición del marcador en la página web cuando se predice el sentimiento.</span><span class="sxs-lookup"><span data-stu-id="a294c-233">Below that, add another function called `updateMarker` to dynamically update the position of the marker on the web page as sentiment is predicted.</span></span>

        [!code-javascript [UpdateMarkerMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L12-L15)]

    1. <span data-ttu-id="a294c-234">Cree una función de controlador de eventos llamada `updateSentiment` para obtener la entrada del usuario, envíela a la función `OnGetAnalyzeSentiment` mediante la función `getSentiment` y actualice el marcador con la función `updateMarker`.</span><span class="sxs-lookup"><span data-stu-id="a294c-234">Create an event handler function called `updateSentiment` to get the input from the user, send it to the `OnGetAnalyzeSentiment` function using the `getSentiment` function and update the marker with the `updateMarker` function.</span></span>

        [!code-javascript [UpdateSentimentMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L17-L34)]

    1. <span data-ttu-id="a294c-235">Por último, registre el controlador de eventos y enlácelo al elemento `textarea` con el atributo `id=Message`.</span><span class="sxs-lookup"><span data-stu-id="a294c-235">Finally, register the event handler and bind it to the `textarea` element with the `id=Message` attribute.</span></span>

        [!code-javascript [UpdateSentimentEvtHandler](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L36)]

## <a name="run-the-application"></a><span data-ttu-id="a294c-236">Ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="a294c-236">Run the application</span></span>

<span data-ttu-id="a294c-237">Ahora que la aplicación está configurada, ejecútela. Debería iniciarse en el explorador.</span><span class="sxs-lookup"><span data-stu-id="a294c-237">Now that your application is set up, run the application which should launch in your browser.</span></span>

<span data-ttu-id="a294c-238">Cuando se inicie la aplicación, escriba *¡El Generador de modelos es genial!*</span><span class="sxs-lookup"><span data-stu-id="a294c-238">When the application launches, enter *Model Builder is cool!*</span></span> <span data-ttu-id="a294c-239">en el área de texto.</span><span class="sxs-lookup"><span data-stu-id="a294c-239">into the text area.</span></span> <span data-ttu-id="a294c-240">El sentimiento de predicción que aparece debe ser *Not Toxic* (No tóxico).</span><span class="sxs-lookup"><span data-stu-id="a294c-240">The predicted sentiment displayed should be *Not Toxic*.</span></span>

![](./media/sentiment-analysis-model-builder/web-app.png)

<span data-ttu-id="a294c-241">Si tiene que hacer referencia a los proyectos generados por el Generador de modelos más adelante en otra solución, puede encontrarlos en el directorio `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools`.</span><span class="sxs-lookup"><span data-stu-id="a294c-241">If you need to reference the Model Builder generated projects at a later time inside of another solution, you can find them inside the `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools` directory.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a294c-242">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a294c-242">Next steps</span></span>

<span data-ttu-id="a294c-243">En este tutorial ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="a294c-243">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="a294c-244">Crear una aplicación Razor Pages de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a294c-244">Create an ASP.NET Core Razor Pages application</span></span>
> * <span data-ttu-id="a294c-245">Preparar y entender los datos</span><span class="sxs-lookup"><span data-stu-id="a294c-245">Prepare and understand the data</span></span>
> * <span data-ttu-id="a294c-246">Elección de un escenario</span><span class="sxs-lookup"><span data-stu-id="a294c-246">Choose a scenario</span></span>
> * <span data-ttu-id="a294c-247">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="a294c-247">Load the data</span></span>
> * <span data-ttu-id="a294c-248">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="a294c-248">Train the model</span></span>
> * <span data-ttu-id="a294c-249">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="a294c-249">Evaluate the model</span></span>
> * <span data-ttu-id="a294c-250">Usar el modelo para las predicciones</span><span class="sxs-lookup"><span data-stu-id="a294c-250">Use the model for predictions</span></span>

### <a name="additional-resources"></a><span data-ttu-id="a294c-251">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="a294c-251">Additional Resources</span></span>

<span data-ttu-id="a294c-252">Para más información sobre los temas mencionados en este tutorial, visite estos recursos:</span><span class="sxs-lookup"><span data-stu-id="a294c-252">To learn more about topics mentioned in this tutorial, visit the following resources:</span></span>

- [<span data-ttu-id="a294c-253">Escenarios del Generador de modelos</span><span class="sxs-lookup"><span data-stu-id="a294c-253">Model Builder Scenarios</span></span>](../automate-training-with-model-builder.md#scenarios)
- [<span data-ttu-id="a294c-254">Clasificación binaria</span><span class="sxs-lookup"><span data-stu-id="a294c-254">Binary Classification</span></span>](../resources/glossary.md#binary-classification)
- [<span data-ttu-id="a294c-255">Métricas del modelo de clasificación binaria</span><span class="sxs-lookup"><span data-stu-id="a294c-255">Binary Classification Model Metrics</span></span>](../resources/metrics.md#metrics-for-binary-classification)