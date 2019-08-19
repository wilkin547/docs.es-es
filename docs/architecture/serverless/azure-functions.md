---
title: Aplicaciones sin servidor Azure Functions
description: Azure Functions proporciona funcionalidades sin servidor a través deC#varios lenguajes (, JavaScript, Java) y plataformas para proporcionar código de escalado instantáneo orientado a eventos.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 4febcc01eebf3efce3fc1eb42e19c2ec6c0baa52
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577608"
---
# <a name="azure-functions"></a><span data-ttu-id="5491b-103">Azure Functions</span><span class="sxs-lookup"><span data-stu-id="5491b-103">Azure Functions</span></span>

<span data-ttu-id="5491b-104">Azure Functions proporciona una experiencia de proceso sin servidor.</span><span class="sxs-lookup"><span data-stu-id="5491b-104">Azure functions provide a serverless compute experience.</span></span> <span data-ttu-id="5491b-105">Un desencadenador invoca una función ( como el acceso a un punto de conexión http o un temporizador) y ejecuta un bloque de código o lógica de negocios.</span><span class="sxs-lookup"><span data-stu-id="5491b-105">A function is invoked by a *trigger* (such as access to an HTTP endpoint or a timer) and executes a block of code or business logic.</span></span> <span data-ttu-id="5491b-106">Las funciones también admiten *enlaces* especializados que se conectan a recursos como almacenamiento y colas.</span><span class="sxs-lookup"><span data-stu-id="5491b-106">Functions also support specialized *bindings* that connect to resources like storage and queues.</span></span>

![Logotipo de Azure Functions](./media/azure-functions-logo.png)

<span data-ttu-id="5491b-108">Hay dos versiones de Azure Functions Framework.</span><span class="sxs-lookup"><span data-stu-id="5491b-108">There are two versions of the Azure Functions framework.</span></span> <span data-ttu-id="5491b-109">La versión heredada es compatible con el .NET Framework completo y el nuevo Runtime es compatible con las aplicaciones .NET Core multiplataforma.</span><span class="sxs-lookup"><span data-stu-id="5491b-109">The legacy version supports the full .NET Framework and the new runtime supports cross-platform .NET Core applications.</span></span> <span data-ttu-id="5491b-110">Se admiten C# lenguajes adicionales, F#además de JavaScript, y Java.</span><span class="sxs-lookup"><span data-stu-id="5491b-110">Additional languages besides C# such as JavaScript, F#, and Java are supported.</span></span> <span data-ttu-id="5491b-111">Las funciones creadas en el portal proporcionan una sintaxis de scripting enriquecida.</span><span class="sxs-lookup"><span data-stu-id="5491b-111">Functions created in the portal provide a rich scripting syntax.</span></span> <span data-ttu-id="5491b-112">Las funciones creadas como proyectos independientes se pueden implementar con capacidades y soporte técnico completo de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="5491b-112">Functions created as standalone projects can be deployed with full platform support and capabilities.</span></span>

<span data-ttu-id="5491b-113">Para obtener más información, consulte la [documentación de Azure Functions](https://docs.microsoft.com/azure/azure-functions).</span><span class="sxs-lookup"><span data-stu-id="5491b-113">For more information, see [Azure Functions documentation](https://docs.microsoft.com/azure/azure-functions).</span></span>

## <a name="functions-v1-vs-v2"></a><span data-ttu-id="5491b-114">Funciones v1 frente a V2</span><span class="sxs-lookup"><span data-stu-id="5491b-114">Functions v1 vs. v2</span></span>

<span data-ttu-id="5491b-115">Hay dos versiones del tiempo de ejecución de Azure Functions: 1. x y 2. x.</span><span class="sxs-lookup"><span data-stu-id="5491b-115">There are two versions of the Azure Functions runtime: 1.x and 2.x.</span></span> <span data-ttu-id="5491b-116">La versión 1. x está disponible con carácter general (GA).</span><span class="sxs-lookup"><span data-stu-id="5491b-116">Version 1.x is generally available (GA).</span></span> <span data-ttu-id="5491b-117">Admite el desarrollo de .NET desde el portal o las máquinas de Windows y usa el .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5491b-117">It supports .NET development from the portal or Windows machines and uses the .NET Framework.</span></span> <span data-ttu-id="5491b-118">1. x admite C#, JavaScript y F#, con compatibilidad experimental con Python, PHP, TypeScript, Batch, bash y PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5491b-118">1.x supports C#, JavaScript, and F#, with experimental support for Python, PHP, TypeScript, Batch, Bash, and PowerShell.</span></span>

<span data-ttu-id="5491b-119">La [versión 2. x también está disponible con carácter general](https://azure.microsoft.com/blog/introducing-azure-functions-2-0/).</span><span class="sxs-lookup"><span data-stu-id="5491b-119">[Version 2.x is also generally available now](https://azure.microsoft.com/blog/introducing-azure-functions-2-0/).</span></span> <span data-ttu-id="5491b-120">Aprovecha .NET Core y admite el desarrollo multiplataforma en máquinas Windows, macOS y Linux.</span><span class="sxs-lookup"><span data-stu-id="5491b-120">It leverages .NET Core and supports cross-platform development on Windows, macOS, and Linux machines.</span></span> <span data-ttu-id="5491b-121">2. x agrega compatibilidad de primera clase para Java, pero aún no es compatible directamente con ninguno de los lenguajes experimentales.</span><span class="sxs-lookup"><span data-stu-id="5491b-121">2.x adds first-class support for Java but doesn't yet directly support any of the experimental languages.</span></span> <span data-ttu-id="5491b-122">La versión 2. x usa un nuevo modelo de extensibilidad de enlaces que permite extensiones de terceros a la plataforma, control de versiones independiente de los enlaces y un entorno de ejecución más sencillo.</span><span class="sxs-lookup"><span data-stu-id="5491b-122">Version 2.x uses a new binding extensibility model that enables third-party extensions to the platform, independent versioning of bindings, and a more streamlined execution environment.</span></span>

> <span data-ttu-id="5491b-123">**Hay un problema conocido en 1. x con compatibilidad con la redirección de [enlaces](https://github.com/Azure/azure-functions-host/issues/992).**</span><span class="sxs-lookup"><span data-stu-id="5491b-123">**There is a known issue in 1.x with [binding redirect support](https://github.com/Azure/azure-functions-host/issues/992).**</span></span> <span data-ttu-id="5491b-124">El problema es específico del desarrollo de .NET.</span><span class="sxs-lookup"><span data-stu-id="5491b-124">The issue is specific to .NET development.</span></span> <span data-ttu-id="5491b-125">Los proyectos con dependencias en bibliotecas que tienen una versión diferente de las bibliotecas incluidas en el tiempo de ejecución se ven afectados.</span><span class="sxs-lookup"><span data-stu-id="5491b-125">Projects with dependencies on libraries that are a different version from the libraries included in the runtime are impacted.</span></span> <span data-ttu-id="5491b-126">El equipo de funciones se ha confirmado para hacer un progreso concreto del problema.</span><span class="sxs-lookup"><span data-stu-id="5491b-126">The functions team has committed to making concrete progress on the problem.</span></span> <span data-ttu-id="5491b-127">El equipo tratará las redirecciones de enlace en 2. x antes de que pase a la disponibilidad general.</span><span class="sxs-lookup"><span data-stu-id="5491b-127">The team will address binding redirects in 2.x before it goes into general availability.</span></span> <span data-ttu-id="5491b-128">La declaración oficial del equipo con correcciones y soluciones recomendadas está disponible aquí: [Resolución de ensamblados en Azure Functions](https://github.com/Azure/azure-functions-host/wiki/Assembly-Resolution-in-Azure-Functions).</span><span class="sxs-lookup"><span data-stu-id="5491b-128">The official team statement with suggested fixes and workarounds is available here: [Assembly resolution in Azure Functions](https://github.com/Azure/azure-functions-host/wiki/Assembly-Resolution-in-Azure-Functions).</span></span>

<span data-ttu-id="5491b-129">Para obtener más información, vea [Compare 1. x y 2. x](https://docs.microsoft.com/azure/azure-functions/functions-versions).</span><span class="sxs-lookup"><span data-stu-id="5491b-129">For more information, see [Compare 1.x and 2.x](https://docs.microsoft.com/azure/azure-functions/functions-versions).</span></span>

## <a name="programming-language-support"></a><span data-ttu-id="5491b-130">Compatibilidad con el lenguaje de programación</span><span class="sxs-lookup"><span data-stu-id="5491b-130">Programming language support</span></span>

<span data-ttu-id="5491b-131">Los siguientes idiomas son compatibles con la disponibilidad general (GA), la versión preliminar o el experimental.</span><span class="sxs-lookup"><span data-stu-id="5491b-131">The following languages are supported either in general availability (GA), preview, or experimental.</span></span>

|<span data-ttu-id="5491b-132">Idioma</span><span class="sxs-lookup"><span data-stu-id="5491b-132">Language</span></span>      |<span data-ttu-id="5491b-133">1.x</span><span class="sxs-lookup"><span data-stu-id="5491b-133">1.x</span></span>         |<span data-ttu-id="5491b-134">2.x</span><span class="sxs-lookup"><span data-stu-id="5491b-134">2.x</span></span>      |
|--------------|------------|---------|
|<span data-ttu-id="5491b-135">**C#**</span><span class="sxs-lookup"><span data-stu-id="5491b-135">**C#**</span></span>        |<span data-ttu-id="5491b-136">GA</span><span class="sxs-lookup"><span data-stu-id="5491b-136">GA</span></span>          |<span data-ttu-id="5491b-137">Vista previa</span><span class="sxs-lookup"><span data-stu-id="5491b-137">Preview</span></span>  |
|<span data-ttu-id="5491b-138">**JavaScript**</span><span class="sxs-lookup"><span data-stu-id="5491b-138">**JavaScript**</span></span>|<span data-ttu-id="5491b-139">GA</span><span class="sxs-lookup"><span data-stu-id="5491b-139">GA</span></span>          |<span data-ttu-id="5491b-140">Vista previa</span><span class="sxs-lookup"><span data-stu-id="5491b-140">Preview</span></span>  |
|<span data-ttu-id="5491b-141">**F#**</span><span class="sxs-lookup"><span data-stu-id="5491b-141">**F#**</span></span>        |<span data-ttu-id="5491b-142">GA</span><span class="sxs-lookup"><span data-stu-id="5491b-142">GA</span></span>          |         |
|<span data-ttu-id="5491b-143">**Java**</span><span class="sxs-lookup"><span data-stu-id="5491b-143">**Java**</span></span>      |            |<span data-ttu-id="5491b-144">Vista previa</span><span class="sxs-lookup"><span data-stu-id="5491b-144">Preview</span></span>  |
|<span data-ttu-id="5491b-145">**Python**</span><span class="sxs-lookup"><span data-stu-id="5491b-145">**Python**</span></span>    |<span data-ttu-id="5491b-146">Habilitación de características</span><span class="sxs-lookup"><span data-stu-id="5491b-146">Experimental</span></span>|         |
|<span data-ttu-id="5491b-147">**PHP**</span><span class="sxs-lookup"><span data-stu-id="5491b-147">**PHP**</span></span>       |<span data-ttu-id="5491b-148">Habilitación de características</span><span class="sxs-lookup"><span data-stu-id="5491b-148">Experimental</span></span>|         |
|<span data-ttu-id="5491b-149">**TypeScript**</span><span class="sxs-lookup"><span data-stu-id="5491b-149">**TypeScript**</span></span>|<span data-ttu-id="5491b-150">Habilitación de características</span><span class="sxs-lookup"><span data-stu-id="5491b-150">Experimental</span></span>|         |
|<span data-ttu-id="5491b-151">**Batch**</span><span class="sxs-lookup"><span data-stu-id="5491b-151">**Batch**</span></span>     |<span data-ttu-id="5491b-152">Habilitación de características</span><span class="sxs-lookup"><span data-stu-id="5491b-152">Experimental</span></span>|         |
|<span data-ttu-id="5491b-153">**Sucesión**</span><span class="sxs-lookup"><span data-stu-id="5491b-153">**Bash**</span></span>      |<span data-ttu-id="5491b-154">Habilitación de características</span><span class="sxs-lookup"><span data-stu-id="5491b-154">Experimental</span></span>|         |
|<span data-ttu-id="5491b-155">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="5491b-155">**PowerShell**</span></span>|<span data-ttu-id="5491b-156">Habilitación de características</span><span class="sxs-lookup"><span data-stu-id="5491b-156">Experimental</span></span>|         |

<span data-ttu-id="5491b-157">Para obtener más información, consulte [idiomas admitidos](https://docs.microsoft.com/azure/azure-functions/supported-languages).</span><span class="sxs-lookup"><span data-stu-id="5491b-157">For more information, see [Supported languages](https://docs.microsoft.com/azure/azure-functions/supported-languages).</span></span>

## <a name="app-service-plans"></a><span data-ttu-id="5491b-158">Planes de App Service</span><span class="sxs-lookup"><span data-stu-id="5491b-158">App service plans</span></span>

<span data-ttu-id="5491b-159">Las funciones están respaldadas por un *plan de App Service*.</span><span class="sxs-lookup"><span data-stu-id="5491b-159">Functions are backed by an *app service plan*.</span></span> <span data-ttu-id="5491b-160">El plan define los recursos usados por la aplicación de functions.</span><span class="sxs-lookup"><span data-stu-id="5491b-160">The plan defines the resources used by the functions app.</span></span> <span data-ttu-id="5491b-161">Puede asignar planes a una región, determinar el tamaño y el número de máquinas virtuales que se usarán y elegir un plan de tarifa.</span><span class="sxs-lookup"><span data-stu-id="5491b-161">You can assign plans to a region, determine the size and number of virtual machines that will be used, and pick a pricing tier.</span></span> <span data-ttu-id="5491b-162">Para un enfoque real sin servidor, las aplicaciones de función pueden usar el plan de **consumo** .</span><span class="sxs-lookup"><span data-stu-id="5491b-162">For a true serverless approach, function apps may use the **consumption** plan.</span></span> <span data-ttu-id="5491b-163">El plan de consumo escalará automáticamente el back-end en función de la carga.</span><span class="sxs-lookup"><span data-stu-id="5491b-163">The consumption plan will scale the back end automatically based on load.</span></span>

<span data-ttu-id="5491b-164">Para obtener más información, consulte [planes de App Service](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).</span><span class="sxs-lookup"><span data-stu-id="5491b-164">For more information, see [App service plans](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).</span></span>

## <a name="create-your-first-function"></a><span data-ttu-id="5491b-165">Creación de la primera función</span><span class="sxs-lookup"><span data-stu-id="5491b-165">Create your first function</span></span>

<span data-ttu-id="5491b-166">Existen tres formas comunes de crear aplicaciones de función.</span><span class="sxs-lookup"><span data-stu-id="5491b-166">There are three common ways you can create function apps.</span></span>

* <span data-ttu-id="5491b-167">Funciones de script en el portal.</span><span class="sxs-lookup"><span data-stu-id="5491b-167">Script functions in the portal.</span></span>
* <span data-ttu-id="5491b-168">Cree los recursos necesarios mediante la interfaz de la línea de comandos (CLI) de Azure.</span><span class="sxs-lookup"><span data-stu-id="5491b-168">Create the necessary resources using the Azure Command Line Interface (CLI).</span></span>
* <span data-ttu-id="5491b-169">Cree funciones localmente mediante su IDE favorito y publíquelos en Azure.</span><span class="sxs-lookup"><span data-stu-id="5491b-169">Build functions locally using your favorite IDE and publish them to Azure.</span></span>

<span data-ttu-id="5491b-170">Para obtener más información sobre la creación de una función con scripts en el portal, consulte Creación de la [primera función en el Azure portal](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function).</span><span class="sxs-lookup"><span data-stu-id="5491b-170">For more information on creating a scripted function in the portal, see [Create your first function in the Azure portal](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function).</span></span>

<span data-ttu-id="5491b-171">Para compilar desde el CLI de Azure, consulte [crear la primera función mediante el CLI de Azure](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli).</span><span class="sxs-lookup"><span data-stu-id="5491b-171">To build from the Azure CLI, see [Create your first function using the Azure CLI](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli).</span></span>

<span data-ttu-id="5491b-172">Para crear una función desde Visual Studio, consulte [crear la primera función con Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="5491b-172">To create a function from Visual Studio, see [Create your first function using Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio).</span></span>

## <a name="understand-triggers-and-bindings"></a><span data-ttu-id="5491b-173">Descripción de los desencadenadores y los enlaces</span><span class="sxs-lookup"><span data-stu-id="5491b-173">Understand triggers and bindings</span></span>

<span data-ttu-id="5491b-174">Las funciones se invocan mediante un desencadenador y pueden tener exactamente una.</span><span class="sxs-lookup"><span data-stu-id="5491b-174">Functions are invoked by a *trigger* and can have exactly one.</span></span> <span data-ttu-id="5491b-175">Además de invocar la función, algunos desencadenadores también sirven como enlaces.</span><span class="sxs-lookup"><span data-stu-id="5491b-175">In addition to invoking the function, certain triggers also serve as bindings.</span></span> <span data-ttu-id="5491b-176">También puede definir varios enlaces además del desencadenador.</span><span class="sxs-lookup"><span data-stu-id="5491b-176">You may also define multiple bindings in addition to the trigger.</span></span> <span data-ttu-id="5491b-177">Los *enlaces* proporcionan una manera declarativa de conectar los datos al código.</span><span class="sxs-lookup"><span data-stu-id="5491b-177">*Bindings* provide a declarative way to connect data to your code.</span></span> <span data-ttu-id="5491b-178">Se pueden pasar (entrada) o recibir datos (salida).</span><span class="sxs-lookup"><span data-stu-id="5491b-178">They can be passed in (input) or receive data (output).</span></span> <span data-ttu-id="5491b-179">Los desencadenadores y los enlaces facilitan el trabajo con las funciones.</span><span class="sxs-lookup"><span data-stu-id="5491b-179">Triggers and bindings make functions easy to work with.</span></span> <span data-ttu-id="5491b-180">Los enlaces quitan la sobrecarga de crear manualmente las conexiones de base de datos o del sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="5491b-180">Bindings remove the overhead of manually creating database or file system connections.</span></span> <span data-ttu-id="5491b-181">Toda la información necesaria para los enlaces está contenida en un archivo *functions. JSON* especial para scripts o declarado con atributos en el código.</span><span class="sxs-lookup"><span data-stu-id="5491b-181">All of the information needed for the bindings is contained in a special *functions.json* file for scripts or declared with attributes in code.</span></span>

<span data-ttu-id="5491b-182">Algunos desencadenadores comunes son:</span><span class="sxs-lookup"><span data-stu-id="5491b-182">Some common triggers include:</span></span>

* <span data-ttu-id="5491b-183">Blob Storage: invocar la función cuando se carga o se cambia un archivo o una carpeta en el almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="5491b-183">Blob Storage: invoke your function when a file or folder is uploaded or changed in storage.</span></span>
* <span data-ttu-id="5491b-184">HTTP: invocar la función como una API de REST.</span><span class="sxs-lookup"><span data-stu-id="5491b-184">HTTP: invoke your function like a REST API.</span></span>
* <span data-ttu-id="5491b-185">Queue: invoca la función cuando existen elementos en una cola.</span><span class="sxs-lookup"><span data-stu-id="5491b-185">Queue: invoke your function when items exist in a queue.</span></span>
* <span data-ttu-id="5491b-186">Temporizador: invoque la función a una cadencia regular.</span><span class="sxs-lookup"><span data-stu-id="5491b-186">Timer: invoke your function on a regular cadence.</span></span>

<span data-ttu-id="5491b-187">Entre los ejemplos de enlaces se incluyen:</span><span class="sxs-lookup"><span data-stu-id="5491b-187">Examples of bindings include:</span></span>

* <span data-ttu-id="5491b-188">CosmosDB: Conéctese fácilmente a la base de datos para cargar o guardar archivos.</span><span class="sxs-lookup"><span data-stu-id="5491b-188">CosmosDB: easily connect to the database to load or save files.</span></span>
* <span data-ttu-id="5491b-189">Table Storage: trabaje con el almacenamiento de clave y valor de la aplicación de función.</span><span class="sxs-lookup"><span data-stu-id="5491b-189">Table Storage: work with key/value storage from your function app.</span></span>
* <span data-ttu-id="5491b-190">Queue Storage: recuperar fácilmente los elementos de una cola o colocar nuevos elementos en la cola.</span><span class="sxs-lookup"><span data-stu-id="5491b-190">Queue Storage: easily retrieve items from a queue, or place new items on the queue.</span></span>

<span data-ttu-id="5491b-191">En el ejemplo siguiente, el archivo *functions. JSON* define un desencadenador y un enlace:</span><span class="sxs-lookup"><span data-stu-id="5491b-191">The following example *functions.json* file defines a trigger and a binding:</span></span>

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

<span data-ttu-id="5491b-192">En este ejemplo, la función se desencadena mediante un cambio en el almacenamiento de blobs `images` en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="5491b-192">In this example, the function is triggered by a change to blob storage in the `images` container.</span></span> <span data-ttu-id="5491b-193">La información del archivo se pasa, por lo que el desencadenador también actúa como un enlace.</span><span class="sxs-lookup"><span data-stu-id="5491b-193">The information for the file is passed in, so the trigger also acts as a binding.</span></span> <span data-ttu-id="5491b-194">Existe otro enlace para colocar información en una cola denominada `images`.</span><span class="sxs-lookup"><span data-stu-id="5491b-194">Another binding exists to put information onto a queue named `images`.</span></span>

<span data-ttu-id="5491b-195">Este es el C# script de la función:</span><span class="sxs-lookup"><span data-stu-id="5491b-195">Here is the C# script for the function:</span></span>

```csharp
public static string Run(Stream myBlob, string name, TraceWriter log)
{
    log.Info($"C# Blob trigger function Processed blob\n Name:{name} \n Size: {myBlob.Length} Bytes");
    return name;
}
```

<span data-ttu-id="5491b-196">El ejemplo es una función simple que toma el nombre del archivo que se modificó o cargó en el almacenamiento de blobs y lo coloca en una cola para su procesamiento posterior.</span><span class="sxs-lookup"><span data-stu-id="5491b-196">The example is a simple function that takes the name of the file that was modified or uploaded to blob storage, and places it on a queue for later processing.</span></span>

<span data-ttu-id="5491b-197">Para obtener una lista completa de los desencadenadores y enlaces, vea [Azure Functions conceptos de desencadenadores y enlaces](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings).</span><span class="sxs-lookup"><span data-stu-id="5491b-197">For a full list of triggers and bindings, see [Azure Functions triggers and bindings concepts](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings).</span></span>

## <a name="proxies"></a><span data-ttu-id="5491b-198">Servidores proxy</span><span class="sxs-lookup"><span data-stu-id="5491b-198">Proxies</span></span>

<span data-ttu-id="5491b-199">Los servidores proxy proporcionan funcionalidad de redirección para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5491b-199">Proxies provide redirect functionality for your application.</span></span> <span data-ttu-id="5491b-200">Los servidores proxy exponen un punto de conexión y lo asignan a otro recurso.</span><span class="sxs-lookup"><span data-stu-id="5491b-200">Proxies expose an endpoint and map that endpoint to another resource.</span></span> <span data-ttu-id="5491b-201">Con servidores proxy, puede:</span><span class="sxs-lookup"><span data-stu-id="5491b-201">With proxies, you can:</span></span>

* <span data-ttu-id="5491b-202">Reenruta una solicitud entrante a otro punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="5491b-202">Reroute an incoming request to another endpoint.</span></span>
* <span data-ttu-id="5491b-203">Modifique la solicitud entrante antes de que se pase.</span><span class="sxs-lookup"><span data-stu-id="5491b-203">Modify the incoming request before it's passed along.</span></span>
* <span data-ttu-id="5491b-204">Modifique o proporcione una respuesta.</span><span class="sxs-lookup"><span data-stu-id="5491b-204">Modify or provide a response.</span></span>

<span data-ttu-id="5491b-205">Los servidores proxy se utilizan para escenarios como los siguientes:</span><span class="sxs-lookup"><span data-stu-id="5491b-205">Proxies are used for scenarios such as:</span></span>

* <span data-ttu-id="5491b-206">Simplificar, acortar o cambiar la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="5491b-206">Simplifying, shortening, or changing the URL.</span></span>
* <span data-ttu-id="5491b-207">Proporcionar un prefijo de API coherente a varios servicios back-end.</span><span class="sxs-lookup"><span data-stu-id="5491b-207">Providing a consistent API prefix to multiple back-end services.</span></span>
* <span data-ttu-id="5491b-208">Simular una respuesta a un extremo que se está desarrollando.</span><span class="sxs-lookup"><span data-stu-id="5491b-208">Mocking a response to an endpoint being developed.</span></span>
* <span data-ttu-id="5491b-209">Proporcionar una respuesta estática a un punto de conexión conocido.</span><span class="sxs-lookup"><span data-stu-id="5491b-209">Providing a static response to a well-known endpoint.</span></span>
* <span data-ttu-id="5491b-210">Mantener un punto de conexión de API coherente mientras se mueve o migra el back-end.</span><span class="sxs-lookup"><span data-stu-id="5491b-210">Keeping an API endpoint consistent while the back end is moved or migrated.</span></span>

<span data-ttu-id="5491b-211">Los servidores proxy se almacenan como definiciones de JSON.</span><span class="sxs-lookup"><span data-stu-id="5491b-211">Proxies are stored as JSON definitions.</span></span> <span data-ttu-id="5491b-212">Este es un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5491b-212">Here is an example:</span></span>

```json
{
  "$schema": "http://json.schemastore.org/proxies",
  "proxies": {
    "Domain Redirect": {
      "matchCondition": {
        "route": "/{shortUrl}"
      },
      "backendUri": "http://%WEBSITE_HOSTNAME%/api/UrlRedirect/{shortUrl}"
    },
    "Root": {
      "matchCondition": {
        "route": "/"
      },
      "responseOverrides": {
        "response.statusCode": "301",
        "response.statusReason": "Moved Permanently",
        "response.headers.location": "https://docs.microsoft.com/"
      }
    }
  }
}
```

<span data-ttu-id="5491b-213">El `Domain Redirect` proxy toma una ruta abreviada y la asigna al recurso de función más largo.</span><span class="sxs-lookup"><span data-stu-id="5491b-213">The `Domain Redirect` proxy takes a shortened route and maps it to the longer function resource.</span></span> <span data-ttu-id="5491b-214">La transformación tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="5491b-214">The transformation looks like:</span></span>

`https://--shorturl--/123` -> `https://--longurl--.azurewebsites.net/api/UrlRedirect/123`

<span data-ttu-id="5491b-215">El `Root` proxy toma todo lo que se envía a la`https://--shorturl--/`dirección URL raíz () y lo redirige al sitio de documentación.</span><span class="sxs-lookup"><span data-stu-id="5491b-215">The `Root` proxy takes anything sent to the root URL (`https://--shorturl--/`) and redirects it to the documentation site.</span></span>

<span data-ttu-id="5491b-216">En el vídeo [Azure se muestra un ejemplo de uso de servidores proxy: Lleve su aplicación a la nube con Azure Functions](https://channel9.msdn.com/events/Connect/2017/E102)sin servidor.</span><span class="sxs-lookup"><span data-stu-id="5491b-216">An example of using proxies is shown in the video [Azure: Bring your app to the cloud with serverless Azure Functions](https://channel9.msdn.com/events/Connect/2017/E102).</span></span> <span data-ttu-id="5491b-217">En tiempo real, una aplicación ASP.NET Core que se ejecuta en el SQL Server local se migra a la nube de Azure.</span><span class="sxs-lookup"><span data-stu-id="5491b-217">In real time, an ASP.NET Core application running on local SQL Server is migrated to the Azure Cloud.</span></span> <span data-ttu-id="5491b-218">Los proxies se usan para ayudar a refactorizar un proyecto de API Web tradicional para usar las funciones.</span><span class="sxs-lookup"><span data-stu-id="5491b-218">Proxies are used to help refactor a traditional Web API project to use functions.</span></span>

<span data-ttu-id="5491b-219">Para obtener más información acerca de los servidores proxy, consulte [trabajar con Azure Functions proxies](https://docs.microsoft.com/azure/azure-functions/functions-proxies).</span><span class="sxs-lookup"><span data-stu-id="5491b-219">For more information about Proxies, see [Work with Azure Functions Proxies](https://docs.microsoft.com/azure/azure-functions/functions-proxies).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="5491b-220">[Anterior](azure-serverless-platform.md)
>[Siguiente](application-insights.md)</span><span class="sxs-lookup"><span data-stu-id="5491b-220">[Previous](azure-serverless-platform.md)
[Next](application-insights.md)</span></span>
