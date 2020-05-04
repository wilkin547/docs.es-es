---
title: 'Azure Functions: Aplicaciones sin servidor'
description: Azure Functions proporciona funcionalidades sin servidor mediante varios lenguajes (C#, JavaScript, Java) y plataformas para proporcionar código de escalado instantáneo orientado a eventos.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 04/06/2020
ms.openlocfilehash: 2dee60e3635be94a55ee26a7f04942bc59cb8dec
ms.sourcegitcommit: 8b02d42f93adda304246a47f49f6449fc74a3af4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/24/2020
ms.locfileid: "82135729"
---
# <a name="azure-functions"></a><span data-ttu-id="dea9a-103">Comprobación de</span><span class="sxs-lookup"><span data-stu-id="dea9a-103">Azure Functions</span></span>

<span data-ttu-id="dea9a-104">Azure Functions proporciona una experiencia de proceso sin servidor.</span><span class="sxs-lookup"><span data-stu-id="dea9a-104">Azure functions provide a serverless compute experience.</span></span> <span data-ttu-id="dea9a-105">Un *desencadenador* invoca una función (por ejemplo, el acceso a un punto de conexión HTTP o un temporizador) y ejecuta un bloque de código o lógica de negocios.</span><span class="sxs-lookup"><span data-stu-id="dea9a-105">A function is invoked by a *trigger* (such as access to an HTTP endpoint or a timer) and executes a block of code or business logic.</span></span> <span data-ttu-id="dea9a-106">Las funciones también admiten *enlaces* especializados que se conectan a recursos como los de almacenamiento y colas.</span><span class="sxs-lookup"><span data-stu-id="dea9a-106">Functions also support specialized *bindings* that connect to resources like storage and queues.</span></span>

![Logotipo de Azure Functions](./media/azure-functions-logo.png)

<span data-ttu-id="dea9a-108">La versión del entorno de ejecución actual 3.0 es compatible con aplicaciones de .NET Core 3.1 multiplataforma.</span><span class="sxs-lookup"><span data-stu-id="dea9a-108">The current runtime version 3.0 supports cross-platform .NET Core 3.1 applications.</span></span> <span data-ttu-id="dea9a-109">También se admiten lenguajes adicionales además de C#, como JavaScript, F# y Java.</span><span class="sxs-lookup"><span data-stu-id="dea9a-109">Additional languages besides C# such as JavaScript, F#, and Java are supported.</span></span> <span data-ttu-id="dea9a-110">Las funciones creadas en el portal proporcionan una sintaxis de scripting enriquecida.</span><span class="sxs-lookup"><span data-stu-id="dea9a-110">Functions created in the portal provide a rich scripting syntax.</span></span> <span data-ttu-id="dea9a-111">Las funciones creadas como proyectos independientes se pueden implementar con funcionalidades y compatibilidad completas con la plataforma.</span><span class="sxs-lookup"><span data-stu-id="dea9a-111">Functions created as standalone projects can be deployed with full platform support and capabilities.</span></span>

<span data-ttu-id="dea9a-112">Para más información, consulte la [documentación de Azure Functions](https://docs.microsoft.com/azure/azure-functions).</span><span class="sxs-lookup"><span data-stu-id="dea9a-112">For more information, see [Azure Functions documentation](https://docs.microsoft.com/azure/azure-functions).</span></span>

## <a name="programming-language-support"></a><span data-ttu-id="dea9a-113">Compatibilidad con lenguajes de programación</span><span class="sxs-lookup"><span data-stu-id="dea9a-113">Programming language support</span></span>

<span data-ttu-id="dea9a-114">Todos los siguientes idiomas se admiten en la disponibilidad general (GA).</span><span class="sxs-lookup"><span data-stu-id="dea9a-114">The following languages are all supported in general availability (GA).</span></span>

|<span data-ttu-id="dea9a-115">Lenguaje</span><span class="sxs-lookup"><span data-stu-id="dea9a-115">Language</span></span>      |<span data-ttu-id="dea9a-116">Entornos de ejecución admitidos</span><span class="sxs-lookup"><span data-stu-id="dea9a-116">Supported runtimes</span></span>|
|--------------|------------------|
|<span data-ttu-id="dea9a-117">**C#**</span><span class="sxs-lookup"><span data-stu-id="dea9a-117">**C#**</span></span>        |<span data-ttu-id="dea9a-118">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="dea9a-118">.NET Core 3.1</span></span>     |
|<span data-ttu-id="dea9a-119">**JavaScript**</span><span class="sxs-lookup"><span data-stu-id="dea9a-119">**JavaScript**</span></span>|<span data-ttu-id="dea9a-120">Nodo 10 y 12</span><span class="sxs-lookup"><span data-stu-id="dea9a-120">Node 10 & 12</span></span>      |
|<span data-ttu-id="dea9a-121">**F#**</span><span class="sxs-lookup"><span data-stu-id="dea9a-121">**F#**</span></span>        |<span data-ttu-id="dea9a-122">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="dea9a-122">.NET Core 3.1</span></span>     |
|<span data-ttu-id="dea9a-123">**Java**</span><span class="sxs-lookup"><span data-stu-id="dea9a-123">**Java**</span></span>      |<span data-ttu-id="dea9a-124">Java 8</span><span class="sxs-lookup"><span data-stu-id="dea9a-124">Java 8</span></span>            |
|<span data-ttu-id="dea9a-125">**Python**</span><span class="sxs-lookup"><span data-stu-id="dea9a-125">**Python**</span></span>    |<span data-ttu-id="dea9a-126">Python 3.6, 3.7 y 3.8</span><span class="sxs-lookup"><span data-stu-id="dea9a-126">Python 3.6, 3.7, & 3.8</span></span>|
|<span data-ttu-id="dea9a-127">**TypeScript**</span><span class="sxs-lookup"><span data-stu-id="dea9a-127">**TypeScript**</span></span>|<span data-ttu-id="dea9a-128">Nodo 10 y 12 (mediante JavaScript)</span><span class="sxs-lookup"><span data-stu-id="dea9a-128">Node 10 & 12 (via JavaScript)</span></span>|
|<span data-ttu-id="dea9a-129">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="dea9a-129">**PowerShell**</span></span>|<span data-ttu-id="dea9a-130">PowerShell Core 6</span><span class="sxs-lookup"><span data-stu-id="dea9a-130">PowerShell Core 6</span></span>|

<span data-ttu-id="dea9a-131">Para más información, consulte [Lenguajes admitidos](https://docs.microsoft.com/azure/azure-functions/supported-languages).</span><span class="sxs-lookup"><span data-stu-id="dea9a-131">For more information, see [Supported languages](https://docs.microsoft.com/azure/azure-functions/supported-languages).</span></span>

## <a name="app-service-plans"></a><span data-ttu-id="dea9a-132">Planes de App Service</span><span class="sxs-lookup"><span data-stu-id="dea9a-132">App service plans</span></span>

<span data-ttu-id="dea9a-133">Las funciones están respaldadas por un *plan de App Service*.</span><span class="sxs-lookup"><span data-stu-id="dea9a-133">Functions are backed by an *app service plan*.</span></span> <span data-ttu-id="dea9a-134">El plan define los recursos que usa la aplicación de funciones.</span><span class="sxs-lookup"><span data-stu-id="dea9a-134">The plan defines the resources used by the functions app.</span></span> <span data-ttu-id="dea9a-135">Puede asignar planes a una región, determinar el tamaño y el número de máquinas virtuales que se usarán y elegir un plan de tarifa.</span><span class="sxs-lookup"><span data-stu-id="dea9a-135">You can assign plans to a region, determine the size and number of virtual machines that will be used, and pick a pricing tier.</span></span> <span data-ttu-id="dea9a-136">Para un enfoque sin servidor auténtico, las aplicaciones de funciones pueden usar el plan de **consumo**.</span><span class="sxs-lookup"><span data-stu-id="dea9a-136">For a true serverless approach, function apps may use the **consumption** plan.</span></span> <span data-ttu-id="dea9a-137">El plan de consumo escalará automáticamente el back-end en función de la carga.</span><span class="sxs-lookup"><span data-stu-id="dea9a-137">The consumption plan will scale the back end automatically based on load.</span></span>

<span data-ttu-id="dea9a-138">Otra opción de hospedaje para las aplicaciones de función es el [plan Premium](https://docs.microsoft.com/azure/azure-functions/functions-premium-plan).</span><span class="sxs-lookup"><span data-stu-id="dea9a-138">Another hosting option for function apps is the [Premium plan](https://docs.microsoft.com/azure/azure-functions/functions-premium-plan).</span></span> <span data-ttu-id="dea9a-139">Este plan proporciona una instancia siempre activada para evitar el inicio en frío, admite características avanzadas como la conectividad de VNet y se ejecuta en hardware premium.</span><span class="sxs-lookup"><span data-stu-id="dea9a-139">This plan provides an "always on" instance to avoid cold start, supports advanced features like VNet connectivity, and runs on premium hardware.</span></span>

<span data-ttu-id="dea9a-140">Para más información, consulte [Planes de App Service](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).</span><span class="sxs-lookup"><span data-stu-id="dea9a-140">For more information, see [App service plans](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).</span></span>

## <a name="create-your-first-function"></a><span data-ttu-id="dea9a-141">Crear su primera función</span><span class="sxs-lookup"><span data-stu-id="dea9a-141">Create your first function</span></span>

<span data-ttu-id="dea9a-142">Existen tres formas comunes de crear aplicaciones de funciones.</span><span class="sxs-lookup"><span data-stu-id="dea9a-142">There are three common ways you can create function apps.</span></span>

- <span data-ttu-id="dea9a-143">Hacer scripting de funciones en el portal.</span><span class="sxs-lookup"><span data-stu-id="dea9a-143">Script functions in the portal.</span></span>
- <span data-ttu-id="dea9a-144">Cree los recursos necesarios con la CLI de Azure.</span><span class="sxs-lookup"><span data-stu-id="dea9a-144">Create the necessary resources using the Azure CLI.</span></span>
- <span data-ttu-id="dea9a-145">Crear las funciones localmente mediante su entorno de desarrollo integrado favorito y publicarlas en Azure.</span><span class="sxs-lookup"><span data-stu-id="dea9a-145">Build functions locally using your favorite IDE and publish them to Azure.</span></span>

<span data-ttu-id="dea9a-146">Para más información sobre la creación de una función con scripts en el portal, consulte [Creación de su primera función en Azure Portal](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function).</span><span class="sxs-lookup"><span data-stu-id="dea9a-146">For more information on creating a scripted function in the portal, see [Create your first function in the Azure portal](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function).</span></span>

<span data-ttu-id="dea9a-147">Para compilar desde la CLI de Azure, consulte [Creación de su primera función con la CLI de Azure](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli).</span><span class="sxs-lookup"><span data-stu-id="dea9a-147">To build from the Azure CLI, see [Create your first function using the Azure CLI](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli).</span></span>

<span data-ttu-id="dea9a-148">Para crear una función desde Visual Studio, consulte [Creación de la primera función mediante Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="dea9a-148">To create a function from Visual Studio, see [Create your first function using Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio).</span></span>

## <a name="understand-triggers-and-bindings"></a><span data-ttu-id="dea9a-149">Descripción de los desencadenadores y enlaces</span><span class="sxs-lookup"><span data-stu-id="dea9a-149">Understand triggers and bindings</span></span>

<span data-ttu-id="dea9a-150">Un *desencadenador* invoca las funciones y solo pueden tener uno.</span><span class="sxs-lookup"><span data-stu-id="dea9a-150">Functions are invoked by a *trigger* and can have exactly one.</span></span> <span data-ttu-id="dea9a-151">Además de invocar la función, algunos desencadenadores también sirven como enlaces.</span><span class="sxs-lookup"><span data-stu-id="dea9a-151">In addition to invoking the function, certain triggers also serve as bindings.</span></span> <span data-ttu-id="dea9a-152">También puede definir varios enlaces además del desencadenador.</span><span class="sxs-lookup"><span data-stu-id="dea9a-152">You may also define multiple bindings in addition to the trigger.</span></span> <span data-ttu-id="dea9a-153">Los *enlaces* proporcionan una manera declarativa de conectar los datos al código.</span><span class="sxs-lookup"><span data-stu-id="dea9a-153">*Bindings* provide a declarative way to connect data to your code.</span></span> <span data-ttu-id="dea9a-154">Se pueden pasar (entrada) o recibir datos (salida).</span><span class="sxs-lookup"><span data-stu-id="dea9a-154">They can be passed in (input) or receive data (output).</span></span> <span data-ttu-id="dea9a-155">Los desencadenadores y enlaces facilitan el trabajo con las funciones.</span><span class="sxs-lookup"><span data-stu-id="dea9a-155">Triggers and bindings make functions easy to work with.</span></span> <span data-ttu-id="dea9a-156">Los enlaces eliminan la sobrecarga que supone crear manualmente las conexiones de la base de datos o del sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="dea9a-156">Bindings remove the overhead of manually creating database or file system connections.</span></span> <span data-ttu-id="dea9a-157">Toda la información necesaria para los enlaces está contenida en un archivo especial *functions.json* para scripts o se declara con atributos en el código.</span><span class="sxs-lookup"><span data-stu-id="dea9a-157">All of the information needed for the bindings is contained in a special *functions.json* file for scripts or declared with attributes in code.</span></span>

<span data-ttu-id="dea9a-158">Algunos desencadenadores comunes son:</span><span class="sxs-lookup"><span data-stu-id="dea9a-158">Some common triggers include:</span></span>

- <span data-ttu-id="dea9a-159">Blob Storage: se invoca la función cuando se carga o se cambia un archivo o una carpeta en el almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="dea9a-159">Blob Storage: invoke your function when a file or folder is uploaded or changed in storage.</span></span>
- <span data-ttu-id="dea9a-160">HTTP: se invoca la función como una API REST.</span><span class="sxs-lookup"><span data-stu-id="dea9a-160">HTTP: invoke your function like a REST API.</span></span>
- <span data-ttu-id="dea9a-161">Queue: se invoca la función cuando existen elementos en una cola.</span><span class="sxs-lookup"><span data-stu-id="dea9a-161">Queue: invoke your function when items exist in a queue.</span></span>
- <span data-ttu-id="dea9a-162">Timer: se invoca la función según una cadencia regular.</span><span class="sxs-lookup"><span data-stu-id="dea9a-162">Timer: invoke your function on a regular cadence.</span></span>

<span data-ttu-id="dea9a-163">Entre los ejemplos de enlaces se incluyen:</span><span class="sxs-lookup"><span data-stu-id="dea9a-163">Examples of bindings include:</span></span>

- <span data-ttu-id="dea9a-164">CosmosDB: conéctese fácilmente a la base de datos para cargar o guardar archivos.</span><span class="sxs-lookup"><span data-stu-id="dea9a-164">CosmosDB: easily connect to the database to load or save files.</span></span>
- <span data-ttu-id="dea9a-165">Table Storage: trabaje con el almacenamiento de clave-valor de la aplicación de funciones.</span><span class="sxs-lookup"><span data-stu-id="dea9a-165">Table Storage: work with key/value storage from your function app.</span></span>
- <span data-ttu-id="dea9a-166">Queue Storage: recupere fácilmente elementos de una cola o coloque otros nuevos en ella.</span><span class="sxs-lookup"><span data-stu-id="dea9a-166">Queue Storage: easily retrieve items from a queue, or place new items on the queue.</span></span>

<span data-ttu-id="dea9a-167">En el siguiente archivo *functions.json* de ejemplo se define un desencadenador y un enlace:</span><span class="sxs-lookup"><span data-stu-id="dea9a-167">The following example *functions.json* file defines a trigger and a binding:</span></span>

```json
{
  "bindings": [
    {
      "name": "myBlob",
      "type": "blobTrigger",
      "direction": "in",
      "path": "images/{name}",
      "connection": "AzureWebJobsStorage"
    },
    {
      "name": "$return",
      "type": "queue",
      "direction": "out",
      "queueName": "images",
      "connection": "AzureWebJobsStorage"
    }
  ],
  "disabled": false
}
```

<span data-ttu-id="dea9a-168">En este ejemplo, la función se desencadena mediante un cambio en Blob Storage en el contenedor `images`.</span><span class="sxs-lookup"><span data-stu-id="dea9a-168">In this example, the function is triggered by a change to blob storage in the `images` container.</span></span> <span data-ttu-id="dea9a-169">La información del archivo se pasa, por lo que el desencadenador también actúa como un enlace.</span><span class="sxs-lookup"><span data-stu-id="dea9a-169">The information for the file is passed in, so the trigger also acts as a binding.</span></span> <span data-ttu-id="dea9a-170">Existe otro enlace para colocar la información en una cola denominada `images`.</span><span class="sxs-lookup"><span data-stu-id="dea9a-170">Another binding exists to put information onto a queue named `images`.</span></span>

<span data-ttu-id="dea9a-171">Este es el script en C# de la función:</span><span class="sxs-lookup"><span data-stu-id="dea9a-171">Here is the C# script for the function:</span></span>

```csharp
public static string Run(Stream myBlob, string name, TraceWriter log)
{
    log.Info($"C# Blob trigger function Processed blob\n Name:{name} \n Size: {myBlob.Length} Bytes");
    return name;
}
```

<span data-ttu-id="dea9a-172">El ejemplo es una función simple que toma el nombre del archivo que se modificó o cargó en Blob Storage y lo coloca en una cola para su procesamiento posterior.</span><span class="sxs-lookup"><span data-stu-id="dea9a-172">The example is a simple function that takes the name of the file that was modified or uploaded to blob storage, and places it on a queue for later processing.</span></span>

<span data-ttu-id="dea9a-173">Para obtener una lista completa de los desencadenadores y enlaces, consulte [Conceptos básicos sobre los enlaces y desencadenadores de Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings).</span><span class="sxs-lookup"><span data-stu-id="dea9a-173">For a full list of triggers and bindings, see [Azure Functions triggers and bindings concepts](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="dea9a-174">[Anterior](azure-serverless-platform.md)
>[Siguiente](application-insights.md)</span><span class="sxs-lookup"><span data-stu-id="dea9a-174">[Previous](azure-serverless-platform.md)
[Next](application-insights.md)</span></span>
