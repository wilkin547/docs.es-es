---
title: Analizador de API en .NET
description: "Obtenga información sobre cómo el analizador de API de .NET puede ayudar a detectar problemas de compatibilidad de plataforma y de API en desuso."
author: oliag
ms.author: mairaw
ms.date: 01/30/2018
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.openlocfilehash: 81ab7e32b2af6048d822243226f1054ebd1ca419
ms.sourcegitcommit: cf22b29db780e532e1090c6e755aa52d28273fa6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2018
---
# <a name="net-api-analyzer"></a><span data-ttu-id="7aaff-103">Analizador de API en .NET</span><span class="sxs-lookup"><span data-stu-id="7aaff-103">.NET API analyzer</span></span>

<span data-ttu-id="7aaff-104">El analizador de API de .NET es un analizador Roslyn que detecta posibles riesgos de compatibilidad de API de C# en distintas plataformas y detecta llamadas a API en desuso.</span><span class="sxs-lookup"><span data-stu-id="7aaff-104">The .NET API Analyzer is a Roslyn analyzer that discovers potential compatibility risks for C# APIs on different platforms and detects calls to deprecated APIs.</span></span> <span data-ttu-id="7aaff-105">Puede ser útil para todos los programadores de C# en cualquier fase de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="7aaff-105">It can be useful for all C# developers at any stage of development.</span></span>

<span data-ttu-id="7aaff-106">El analizador de API está disponible como un paquete NuGet [Microsoft.DotNet.Analyzers.Compatibility](https://www.nuget.org/packages/Microsoft.DotNet.Analyzers.Compatibility/).</span><span class="sxs-lookup"><span data-stu-id="7aaff-106">API Analyzer comes as a NuGet package [Microsoft.DotNet.Analyzers.Compatibility](https://www.nuget.org/packages/Microsoft.DotNet.Analyzers.Compatibility/).</span></span> <span data-ttu-id="7aaff-107">Tras hacer referencia a él en un proyecto, supervisa automáticamente el código e indica el uso de API problemático.</span><span class="sxs-lookup"><span data-stu-id="7aaff-107">After you reference it in a project, it automatically monitors the code and indicates problematic API usage.</span></span> <span data-ttu-id="7aaff-108">También puede obtener sugerencias sobre posibles soluciones; para ello, haga clic en la bombilla.</span><span class="sxs-lookup"><span data-stu-id="7aaff-108">You can also get suggestions on possible fixes by clicking on the light bulb.</span></span> <span data-ttu-id="7aaff-109">El menú desplegable incluye una opción para suprimir las advertencias.</span><span class="sxs-lookup"><span data-stu-id="7aaff-109">The drop-down menu includes an option to suppress the warnings.</span></span>

> [!NOTE]
> <span data-ttu-id="7aaff-110">El analizador de API de .NET aún está en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="7aaff-110">The .NET API analyzer is still a pre-release version.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7aaff-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="7aaff-111">Prerequisites</span></span>

* <span data-ttu-id="7aaff-112">Visual Studio 2017 o Visual Studio para Mac (todas las versiones).</span><span class="sxs-lookup"><span data-stu-id="7aaff-112">Visual Studio 2017 or Visual Studio for Mac (all versions).</span></span>

## <a name="discovering-deprecated-apis"></a><span data-ttu-id="7aaff-113">Detección de API en desuso</span><span class="sxs-lookup"><span data-stu-id="7aaff-113">Discovering deprecated APIs</span></span>

### <a name="what-are-deprecated-apis"></a><span data-ttu-id="7aaff-114">¿Qué son las API en desuso?</span><span class="sxs-lookup"><span data-stu-id="7aaff-114">What are deprecated APIs?</span></span>

<span data-ttu-id="7aaff-115">La familia de .NET es un conjunto de productos de gran tamaño que se actualizan constantemente para satisfacer mejor las necesidades del cliente.</span><span class="sxs-lookup"><span data-stu-id="7aaff-115">The .NET family is a set of large products that are constantly upgraded to better serve customer needs.</span></span> <span data-ttu-id="7aaff-116">Es natural dejar de utilizar algunas API y sustituirlas por otras nuevas.</span><span class="sxs-lookup"><span data-stu-id="7aaff-116">It's natural to deprecate some APIs and replace them with new ones.</span></span> <span data-ttu-id="7aaff-117">Se considera que una API está en desuso cuando existen alternativas mejores.</span><span class="sxs-lookup"><span data-stu-id="7aaff-117">An API is considered deprecated when a better alternative exists.</span></span> <span data-ttu-id="7aaff-118">Una manera de notificar que una API está en desuso y que no debe utilizarse consiste en marcarla con el atributo <xref:System.ObsoleteAttribute>.</span><span class="sxs-lookup"><span data-stu-id="7aaff-118">One way to inform that an API is deprecated and shouldn't be used is to mark it with the <xref:System.ObsoleteAttribute> attribute.</span></span> <span data-ttu-id="7aaff-119">El inconveniente de este enfoque es que hay un único identificador de diagnóstico para todas las API en desuso (en C#, [CS0612](../../csharp/misc/cs0612.md)).</span><span class="sxs-lookup"><span data-stu-id="7aaff-119">The disadvantage of this approach is that there is only one diagnostic ID for all obsolete APIs (for C#, [CS0612](../../csharp/misc/cs0612.md)).</span></span> <span data-ttu-id="7aaff-120">Esto significa que:</span><span class="sxs-lookup"><span data-stu-id="7aaff-120">This means that:</span></span>
- <span data-ttu-id="7aaff-121">Es imposible dedicar documentos a cada caso.</span><span class="sxs-lookup"><span data-stu-id="7aaff-121">It's impossible to have dedicated documents for each case.</span></span>
- <span data-ttu-id="7aaff-122">Es imposible suprimir determinadas categorías de advertencias.</span><span class="sxs-lookup"><span data-stu-id="7aaff-122">It's impossible to suppress certain category of warnings.</span></span> <span data-ttu-id="7aaff-123">Puede suprimirlas todas o ninguna.</span><span class="sxs-lookup"><span data-stu-id="7aaff-123">You can suppress either all or none of them.</span></span>
- <span data-ttu-id="7aaff-124">Para informar a los usuarios de una nueva degradación, es necesario actualizar un paquete de destino o un ensamblado de referencia.</span><span class="sxs-lookup"><span data-stu-id="7aaff-124">To inform users of a new deprecation, a referenced assembly or targeting package has to be updated.</span></span>

<span data-ttu-id="7aaff-125">El analizador de API usa códigos de error específicos de API que empiezan por DE (que significa error de degradación), que permite controlar la visualización de advertencias individuales.</span><span class="sxs-lookup"><span data-stu-id="7aaff-125">The API Analyzer uses API-specific error codes that begin with DE (which stands for Deprecation Error), which allows control over the display of individual warnings.</span></span> <span data-ttu-id="7aaff-126">Las API en desuso identificadas por el analizador se definen en el repositorio [dotnet/platform-compat](https://github.com/dotnet/platform-compat).</span><span class="sxs-lookup"><span data-stu-id="7aaff-126">The deprecated APIs identified by the analyzer are defined in the [dotnet/platform-compat](https://github.com/dotnet/platform-compat) repo.</span></span>

### <a name="using-the-api-analyzer"></a><span data-ttu-id="7aaff-127">Uso del analizador de API</span><span class="sxs-lookup"><span data-stu-id="7aaff-127">Using the API Analyzer</span></span>

<span data-ttu-id="7aaff-128">Cuando una API en desuso, como <xref:System.Net.WebClient>, se utiliza en un código, el analizador de API la destaca con una línea ondulada de color verde.</span><span class="sxs-lookup"><span data-stu-id="7aaff-128">When a deprecated API, such as <xref:System.Net.WebClient>, is used in a code, API Analyzer highlights it with a green squiggly line.</span></span> <span data-ttu-id="7aaff-129">Si mantiene el puntero sobre la llamada API, se muestra una bombilla con información sobre la degradación de la API, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7aaff-129">When you hover over the API call, a light bulb is displayed with information about the API deprecation, as in the following example:</span></span>

!["Captura de pantalla de WebClient API con una línea ondulada de color verde y una bombilla a la izquierda"](media/api-analyzer/green-squiggle.jpg)

<span data-ttu-id="7aaff-131">La ventana **Lista de errores** contiene advertencias con un identificador exclusivo por cada API en desuso, como se muestra en el ejemplo siguiente (`DE004`):</span><span class="sxs-lookup"><span data-stu-id="7aaff-131">The **Error List** window contains warnings with a unique ID per deprecated API, as shown in the following example (`DE004`):</span></span> 

!["Captura de pantalla de la ventana Lista de errores en que se muestra el identificador de la advertencia y su descripción"](media/api-analyzer/warnings.jpg)

<span data-ttu-id="7aaff-133">Al hacer clic en el identificador, se le remite a una página web que contiene información detallada sobre la API en desuso y sugerencias sobre las API alternativas que pueden usarse.</span><span class="sxs-lookup"><span data-stu-id="7aaff-133">By clicking on the ID, you go to a webpage with detailed information about why the API was deprecated and suggestions regarding alternative APIs that can be used.</span></span>

<span data-ttu-id="7aaff-134">Las advertencias pueden suprimirse si se hace clic con el botón derecho del ratón en el miembro resaltado y se selecciona **Suprimir \<Id. de diagnóstico>**.</span><span class="sxs-lookup"><span data-stu-id="7aaff-134">Any warnings can be suppressed by right-clicking on the highlighted member and selecting **Suppress \<diagnostic ID>**.</span></span> <span data-ttu-id="7aaff-135">Hay dos maneras de suprimir las advertencias:</span><span class="sxs-lookup"><span data-stu-id="7aaff-135">There are two ways to suppress warnings:</span></span> 

* [<span data-ttu-id="7aaff-136">localmente (en el origen)</span><span class="sxs-lookup"><span data-stu-id="7aaff-136">locally (in source)</span></span>](#suppressing-warnings-locally)
* <span data-ttu-id="7aaff-137">[globalmente (en un archivo de supresión)](#suppressing-warnings-globally); se trata de la opción recomendada</span><span class="sxs-lookup"><span data-stu-id="7aaff-137">[globally (in a suppression file)](#suppressing-warnings-globally) - recommended</span></span>

### <a name="suppressing-warnings-locally"></a><span data-ttu-id="7aaff-138">Supresión local de advertencias</span><span class="sxs-lookup"><span data-stu-id="7aaff-138">Suppressing warnings locally</span></span>

<span data-ttu-id="7aaff-139">Para suprimir advertencias localmente, haga clic con el botón derecho en el miembro del que desea suprimir las advertencias y luego seleccione **Acciones rápidas y refactorizaciones** > **Suprimir *Id. de diagnóstico*\<Id. de diagnóstico>** > **en origen**.</span><span class="sxs-lookup"><span data-stu-id="7aaff-139">To suppress warnings locally, right-click on the member you want to suppress warnings for and then select **Quick Actions and Refactorings** > **Suppress *diagnostic ID*\<diagnostic ID>** > **in Source**.</span></span> <span data-ttu-id="7aaff-140">La directiva del preprocesador de advertencias [#pragma](../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md) se agrega al código fuente en el ámbito definido: !["Captura de pantalla encuadrada con la advertencia #pragma deshabilitada"](media/api-analyzer/suppress-in-source.jpg).</span><span class="sxs-lookup"><span data-stu-id="7aaff-140">The [#pragma](../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md) warning preprocessor directive is added to your source code in the scope defined: !["Screenshot of code framed with #pragma warning disable"](media/api-analyzer/suppress-in-source.jpg)</span></span>

### <a name="suppressing-warnings-globally"></a><span data-ttu-id="7aaff-141">Supresión global de advertencias</span><span class="sxs-lookup"><span data-stu-id="7aaff-141">Suppressing warnings globally</span></span>

<span data-ttu-id="7aaff-142">Para suprimir advertencias globalmente, haga clic con el botón derecho en el miembro del que desea suprimir las advertencias y luego seleccione **Acciones rápidas y refactorizaciones** > **Suprimir *Id. de diagnóstico*\<Id. de diagnóstico>** > **en archivo de supresión**.</span><span class="sxs-lookup"><span data-stu-id="7aaff-142">To suppress warnings globally, right-click on the member you want to suppress warnings for and then select **Quick Actions and Refactorings** > **Suppress *diagnostic ID*\<diagnostic ID>** > **in Suppression File**.</span></span>

!["Captura de pantalla de WebClient API con una línea ondulada de color verde y una bombilla a la izquierda"](media/api-analyzer/suppress-in-sup-file.jpg)

<span data-ttu-id="7aaff-144">Se agrega un archivo *GlobalSuppressions.cs* al proyecto después de su primera supresión.</span><span class="sxs-lookup"><span data-stu-id="7aaff-144">A *GlobalSuppressions.cs* file is added to your project after the first suppression.</span></span> <span data-ttu-id="7aaff-145">Las nuevas supresiones globales se anexan a este archivo.</span><span class="sxs-lookup"><span data-stu-id="7aaff-145">New global suppressions are appended to this file.</span></span>

!["Captura de pantalla de WebClient API con una línea ondulada de color verde y una bombilla a la izquierda"](media/api-analyzer/suppression-file.jpg)

<span data-ttu-id="7aaff-147">La supresión global es el método recomendado para garantizar la coherencia del uso de API en los proyectos.</span><span class="sxs-lookup"><span data-stu-id="7aaff-147">Global suppression is the recommended way to ensure consistency of API usage across projects.</span></span>

## <a name="discovering-cross-platform-issues"></a><span data-ttu-id="7aaff-148">Detección de problemas multiplataforma</span><span class="sxs-lookup"><span data-stu-id="7aaff-148">Discovering cross-platform issues</span></span>

<span data-ttu-id="7aaff-149">De forma similar a las API en desuso, el analizador identifica todas las API que no son multiplataforma.</span><span class="sxs-lookup"><span data-stu-id="7aaff-149">Similar to deprecated APIs, the analyzer identifies all APIs that are not cross-platform.</span></span> <span data-ttu-id="7aaff-150">Por ejemplo, <xref:System.Console.WindowWidth?displayProperty=nameWithType> funciona en Windows, pero no en Linux y macOS.</span><span class="sxs-lookup"><span data-stu-id="7aaff-150">For example, <xref:System.Console.WindowWidth?displayProperty=nameWithType> works on Windows but not on Linux and macOS.</span></span> <span data-ttu-id="7aaff-151">El Id. de diagnóstico se muestra en la ventana **Lista de errores**.</span><span class="sxs-lookup"><span data-stu-id="7aaff-151">The diagnostic ID is shown in the **Error List** window.</span></span> <span data-ttu-id="7aaff-152">Puede suprimir dicha advertencia si hace clic con el botón derecho y selecciona **Acciones rápidas y refactorizaciones**.</span><span class="sxs-lookup"><span data-stu-id="7aaff-152">You can suppress that warning by right-clicking and selecting **Quick Actions and Refactorings**.</span></span> <span data-ttu-id="7aaff-153">A diferencia de los casos de degradación donde tiene dos opciones (seguir usando el miembro en desuso y suprimir advertencias o no utilizarlo en absoluto), en este caso, si va a desarrollar el código solo para algunas plataformas, puede suprimir todas las advertencias para todas las demás plataformas en las que no pretende ejecutar el código.</span><span class="sxs-lookup"><span data-stu-id="7aaff-153">Unlike deprecation cases where you have two options (either keep using the deprecated member and suppress warnings or not use it at all), here if you're developing your code only for certain platforms, you can suppress all warnings for all other platforms you don't plan to run your code on.</span></span> <span data-ttu-id="7aaff-154">Para ello, solo tiene que editar el archivo de proyecto y agregar la propiedad `PlatformCompatIgnore` que enumera todas las plataformas que se deben ignorar.</span><span class="sxs-lookup"><span data-stu-id="7aaff-154">To do so, you just need to edit your project file and add the `PlatformCompatIgnore` property that lists all platforms to be ignored.</span></span> <span data-ttu-id="7aaff-155">Los valores permitidos son: `Linux`, `MacOSX` y `Windows`.</span><span class="sxs-lookup"><span data-stu-id="7aaff-155">The accepted values are: `Linux`, `MacOSX`, and `Windows`.</span></span>

```xml
<PropertyGroup>
    <PlatformCompatIgnore>Linux;MacOS</PlatformCompatIgnore>
</PropertyGroup>
```

<span data-ttu-id="7aaff-156">Si el código tiene como destino varias plataformas y desea beneficiarse de una API que no es compatible en algunas de ellas, puede proteger esa parte del código con una instrucción `if`:</span><span class="sxs-lookup"><span data-stu-id="7aaff-156">If your code targets multiple platforms and you want to take advantage of an API not supported on some of them, you can guard that part of the code with an `if` statement:</span></span>

```csharp
if (RuntimeInformation.IsOSPlatform(OSPlatform.Windows))
{
     var w = Console.WindowWidth;
     // More code
}
```

<span data-ttu-id="7aaff-157">También puede compilar de forma condicional pro sistema operativo/marco de destino, pero actualmente necesita hacerlo [manualmente](../frameworks.md#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="7aaff-157">You can also conditionally compile per target framework/operating system, but you currently need to do that [manually](../frameworks.md#how-to-specify-target-frameworks).</span></span>

## <a name="supported-diagnostics"></a><span data-ttu-id="7aaff-158">Diagnóstico admitido</span><span class="sxs-lookup"><span data-stu-id="7aaff-158">Supported diagnostics</span></span>

<span data-ttu-id="7aaff-159">Actualmente, el analizador controla los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="7aaff-159">Currently, the analyzer handles the following cases:</span></span>

* <span data-ttu-id="7aaff-160">Uso de una API de .NET Standard que genera <xref:System.PlatformNotSupportedException> (PC001).</span><span class="sxs-lookup"><span data-stu-id="7aaff-160">Usage of a .NET Standard API that throws <xref:System.PlatformNotSupportedException> (PC001).</span></span>
* <span data-ttu-id="7aaff-161">Uso de una API de .NET Standard que no está disponible en .NET Framework 4.6.1 (PC002).</span><span class="sxs-lookup"><span data-stu-id="7aaff-161">Usage of a .NET Standard API that isn't available on the .NET Framework 4.6.1 (PC002).</span></span>
* <span data-ttu-id="7aaff-162">Uso de una API nativa que no existe en UWP (PC003).</span><span class="sxs-lookup"><span data-stu-id="7aaff-162">Usage of a native API that doesn’t exist in UWP (PC003).</span></span>
* <span data-ttu-id="7aaff-163">Uso de una API que está marcada como en desuso (DEXXXX).</span><span class="sxs-lookup"><span data-stu-id="7aaff-163">Usage of an API that is marked as deprecated (DEXXXX).</span></span>

## <a name="ci-machine"></a><span data-ttu-id="7aaff-164">Equipo de integración continua</span><span class="sxs-lookup"><span data-stu-id="7aaff-164">CI machine</span></span>

<span data-ttu-id="7aaff-165">Todos estos diagnósticos están disponibles no solo en el IDE, sino también en la línea de comandos como parte de la creación del proyecto, que incluye el servidor de integración continua.</span><span class="sxs-lookup"><span data-stu-id="7aaff-165">All these diagnostics are available not only in the IDE, but also on the command line as part of building your project, which includes the CI server.</span></span>

## <a name="configuration"></a><span data-ttu-id="7aaff-166">Configuración</span><span class="sxs-lookup"><span data-stu-id="7aaff-166">Configuration</span></span>

<span data-ttu-id="7aaff-167">El usuario decide cómo se deben tratar los diagnósticos: como advertencias, errores, sugerencias o estar desactivados.</span><span class="sxs-lookup"><span data-stu-id="7aaff-167">The user decides how the diagnostics should be treated: as warnings, errors, suggestions, or to be turned off.</span></span> <span data-ttu-id="7aaff-168">Por ejemplo, como un arquitecto, puede decidir que los problemas de compatibilidad deben tratarse como errores y que las llamadas a algunas API en desuso generen advertencias, mientras que otras solo generan sugerencias.</span><span class="sxs-lookup"><span data-stu-id="7aaff-168">For example, as an architect, you can decide that compatibility issues should be treated as errors, calls to some deprecated APIs generate warnings, while others only generate suggestions.</span></span> <span data-ttu-id="7aaff-169">Puede configurar esto por separado por identificador de diagnóstico y por proyecto.</span><span class="sxs-lookup"><span data-stu-id="7aaff-169">You can configure this separately by diagnostic ID and by project.</span></span> <span data-ttu-id="7aaff-170">Para ello, en el **Explorador de soluciones**, vaya al nodo **Dependencias** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7aaff-170">To do so in **Solution Explorer**, navigate to the **Dependencies** node under your project.</span></span> <span data-ttu-id="7aaff-171">Expanda los nodos **Dependencias** > **Analizadores** > **Microsoft.DotNet.Analyzers.Compatibility**.</span><span class="sxs-lookup"><span data-stu-id="7aaff-171">Expand the nodes **Dependencies** > **Analyzers** > **Microsoft.DotNet.Analyzers.Compatibility**.</span></span> <span data-ttu-id="7aaff-172">Haga clic con el botón derecho en el identificador de diagnóstico, seleccione **Configurar gravedad del conjunto de reglas** y elija la opción deseada.</span><span class="sxs-lookup"><span data-stu-id="7aaff-172">Right click on the diagnostic ID, select **Set Rule Set Severity** and pick the desired option.</span></span>

!["Captura de pantalla del Explorador de soluciones donde se muestran los diagnósticos y el cuadro de diálogo emergente con el menú Configurar gravedad del conjunto de reglas"](media/api-analyzer/disable-notifications.jpg)

## <a name="see-also"></a><span data-ttu-id="7aaff-174">Vea también</span><span class="sxs-lookup"><span data-stu-id="7aaff-174">See also</span></span>

* <span data-ttu-id="7aaff-175">Entrada de blog de [introducción al analizador de API](https://blogs.msdn.microsoft.com/dotnet/2017/10/31/introducing-api-analyzer/).</span><span class="sxs-lookup"><span data-stu-id="7aaff-175">[Introducing API Analyzer](https://blogs.msdn.microsoft.com/dotnet/2017/10/31/introducing-api-analyzer/) blog post.</span></span>
* <span data-ttu-id="7aaff-176">Vídeo de demostración del [analizador de API](https://youtu.be/eeBEahYXGd0) de YouTube.</span><span class="sxs-lookup"><span data-stu-id="7aaff-176">[API Analyzer](https://youtu.be/eeBEahYXGd0) demo video on YouTube.</span></span>
