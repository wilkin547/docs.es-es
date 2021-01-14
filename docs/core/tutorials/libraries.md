---
title: Desarrollo de bibliotecas con la CLI de .NET
description: Aprenda a crear bibliotecas de .NET con la CLI de .NET. Creará una biblioteca que admite varios marcos de trabajo.
author: cartermp
ms.topic: how-to
ms.date: 12/14/2020
ms.openlocfilehash: 6f4c1feac7630a6a0250e4b0b39ef01152f5a400
ms.sourcegitcommit: 635a0ff775d2447a81ef7233a599b8f88b162e5d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2020
ms.locfileid: "97633681"
---
# <a name="develop-libraries-with-the-net-cli"></a><span data-ttu-id="e7cf3-104">Desarrollo de bibliotecas con la CLI de .NET</span><span class="sxs-lookup"><span data-stu-id="e7cf3-104">Develop libraries with the .NET CLI</span></span>

<span data-ttu-id="e7cf3-105">En este artículo se explica cómo escribir bibliotecas para .NET con la CLI de .NET.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-105">This article covers how to write libraries for .NET using the .NET CLI.</span></span> <span data-ttu-id="e7cf3-106">La CLI proporciona una experiencia eficaz y de bajo nivel que funciona en todos los SO compatibles.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-106">The CLI provides an efficient and low-level experience that works across any supported OS.</span></span> <span data-ttu-id="e7cf3-107">De todos modos puede seguir compilando bibliotecas con Visual Studio; si esa es la experiencia de su preferencia, [consulte la guía sobre Visual Studio](library-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="e7cf3-107">You can still build libraries with Visual Studio, and if that is your preferred experience [refer to the Visual Studio guide](library-with-visual-studio.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e7cf3-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="e7cf3-108">Prerequisites</span></span>

<span data-ttu-id="e7cf3-109">Necesita tener instalados en la máquina [la CLI y el SDK de .NET](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="e7cf3-109">You need [the .NET SDK and CLI](https://dotnet.microsoft.com/download) installed on your machine.</span></span>

<span data-ttu-id="e7cf3-110">En las secciones de este documento que se refieren a las versiones de .NET Framework, necesita tener instalado [.NET Framework](https://dotnet.microsoft.com) en una máquina con Windows.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-110">For the sections of this document dealing with .NET Framework versions, you need the [.NET Framework](https://dotnet.microsoft.com) installed on a Windows machine.</span></span>

<span data-ttu-id="e7cf3-111">Además, si desea admitir destinos de .NET Framework anteriores, deberá instalar paquetes de destino o desarrollador desde la [página de archivos de descarga de .NET](https://dotnet.microsoft.com/download/archives).</span><span class="sxs-lookup"><span data-stu-id="e7cf3-111">Additionally, if you wish to support older .NET Framework targets, you need to install targeting packs or developer packs from the [.NET download archives page](https://dotnet.microsoft.com/download/archives).</span></span> <span data-ttu-id="e7cf3-112">Consulte la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="e7cf3-112">Refer to this table:</span></span>

| <span data-ttu-id="e7cf3-113">Versión de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e7cf3-113">.NET Framework version</span></span> | <span data-ttu-id="e7cf3-114">Qué debe descargar</span><span class="sxs-lookup"><span data-stu-id="e7cf3-114">What to download</span></span>                                       |
| ---------------------- | ------------------------------------------------------ |
| <span data-ttu-id="e7cf3-115">4.6.1</span><span class="sxs-lookup"><span data-stu-id="e7cf3-115">4.6.1</span></span>                  | <span data-ttu-id="e7cf3-116">Paquete de compatibilidad de .NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="e7cf3-116">.NET Framework 4.6.1 Targeting Pack</span></span>                    |
| <span data-ttu-id="e7cf3-117">4.6</span><span class="sxs-lookup"><span data-stu-id="e7cf3-117">4.6</span></span>                    | <span data-ttu-id="e7cf3-118">Paquete de compatibilidad de .NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="e7cf3-118">.NET Framework 4.6 Targeting Pack</span></span>                      |
| <span data-ttu-id="e7cf3-119">4.5.2</span><span class="sxs-lookup"><span data-stu-id="e7cf3-119">4.5.2</span></span>                  | <span data-ttu-id="e7cf3-120">Paquete de desarrollador de .NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="e7cf3-120">.NET Framework 4.5.2 Developer Pack</span></span>                    |
| <span data-ttu-id="e7cf3-121">4.5.1</span><span class="sxs-lookup"><span data-stu-id="e7cf3-121">4.5.1</span></span>                  | <span data-ttu-id="e7cf3-122">Paquete de desarrollador de .NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="e7cf3-122">.NET Framework 4.5.1 Developer Pack</span></span>                    |
| <span data-ttu-id="e7cf3-123">4.5</span><span class="sxs-lookup"><span data-stu-id="e7cf3-123">4.5</span></span>                    | <span data-ttu-id="e7cf3-124">Kit de desarrollo de software de Windows para Windows 8</span><span class="sxs-lookup"><span data-stu-id="e7cf3-124">Windows Software Development Kit for Windows 8</span></span>         |
| <span data-ttu-id="e7cf3-125">4.0</span><span class="sxs-lookup"><span data-stu-id="e7cf3-125">4.0</span></span>                    | <span data-ttu-id="e7cf3-126">Windows SDK para Windows 7 y .NET Framework 4</span><span class="sxs-lookup"><span data-stu-id="e7cf3-126">Windows SDK for Windows 7 and .NET Framework 4</span></span>         |
| <span data-ttu-id="e7cf3-127">2.0, 3.0 y 3.5</span><span class="sxs-lookup"><span data-stu-id="e7cf3-127">2.0, 3.0, and 3.5</span></span>      | <span data-ttu-id="e7cf3-128">Entorno de ejecución de .NET Framework 3.5 SP1 (o una versión posterior a Windows 8)</span><span class="sxs-lookup"><span data-stu-id="e7cf3-128">.NET Framework 3.5 SP1 Runtime (or Windows 8+ version)</span></span> |

## <a name="how-to-target-net-50-or-net-standard"></a><span data-ttu-id="e7cf3-129">Establecimiento de .NET 5.0 o .NET Standard como destino</span><span class="sxs-lookup"><span data-stu-id="e7cf3-129">How to target .NET 5.0 or .NET Standard</span></span>

<span data-ttu-id="e7cf3-130">Para controlar la plataforma de destino del proyecto, agréguela al archivo de proyecto ( *.csproj* o *.fsproj*).</span><span class="sxs-lookup"><span data-stu-id="e7cf3-130">You control your project's target framework by adding it to your project file (*.csproj* or *.fsproj*).</span></span> <span data-ttu-id="e7cf3-131">Para obtener instrucciones sobre cómo elegir entre los destinos .NET 5.0 o .NET Standard consulte [.NET 5 y .NET Standard](../../standard/net-standard.md#net-5-and-net-standard).</span><span class="sxs-lookup"><span data-stu-id="e7cf3-131">For guidance on how to choose between targeting .NET 5.0 or .NET Standard see [.NET 5 and .NET Standard](../../standard/net-standard.md#net-5-and-net-standard).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>net5.0</TargetFramework>
  </PropertyGroup>
</Project>
```

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netstandard2.0</TargetFramework>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="e7cf3-132">Si desea tener como destino .NET Framework versión 4.0 o inferior, o bien desea usar una API disponible en .NET Framework pero no disponible en el estándar .NET (por ejemplo, `System.Drawing`), lea las secciones siguientes y sepa cómo tener compatibilidad con múltiples versiones.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-132">If you want to target .NET Framework versions 4.0 or below, or you wish to use an API available in .NET Framework but not in .NET Standard (for example, `System.Drawing`), read the following sections and learn how to multitarget.</span></span>

## <a name="how-to-target-net-framework"></a><span data-ttu-id="e7cf3-133">Uso de .NET Framework como destino</span><span class="sxs-lookup"><span data-stu-id="e7cf3-133">How to target .NET Framework</span></span>

> [!NOTE]
> <span data-ttu-id="e7cf3-134">En estas instrucciones se supone que tiene instalado .NET Framework en su máquina.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-134">These instructions assume you have .NET Framework installed on your machine.</span></span> <span data-ttu-id="e7cf3-135">Consulte los [requisitos previos](#prerequisites) para instalar las dependencias.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-135">Refer to the [Prerequisites](#prerequisites) to get dependencies installed.</span></span>

<span data-ttu-id="e7cf3-136">Tenga en cuenta que algunas de las versiones de .NET Framework que se usan aquí ya no cuentan con soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-136">Keep in mind that some of the .NET Framework versions used here are no longer supported.</span></span> <span data-ttu-id="e7cf3-137">Consulte las [P+F sobre la directiva del ciclo de vida de soporte técnico de .NET Framework](https://support.microsoft.com/gp/framework_faq/en-us) sobre las versiones sin soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-137">Refer to the [.NET Framework Support Lifecycle Policy FAQ](https://support.microsoft.com/gp/framework_faq/en-us) about unsupported versions.</span></span>

<span data-ttu-id="e7cf3-138">Si quiere llegar a la mayor cantidad posible de desarrolladores y proyectos, use .NET Framework 4.0 como el destino de línea base.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-138">If you want to reach the maximum number of developers and projects, use .NET Framework 4.0 as your baseline target.</span></span> <span data-ttu-id="e7cf3-139">Para tener .NET Framework como destino, comience utilizando el moniker de la plataforma de destino (TFM) correcto que corresponda a la versión de .NET Framework que desea admitir.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-139">To target .NET Framework, begin by using the correct Target Framework Moniker (TFM) that corresponds to the .NET Framework version you wish to support.</span></span>

| <span data-ttu-id="e7cf3-140">Versión de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e7cf3-140">.NET Framework version</span></span> | <span data-ttu-id="e7cf3-141">TFM</span><span class="sxs-lookup"><span data-stu-id="e7cf3-141">TFM</span></span>      |
| ---------------------- | -------- |
| <span data-ttu-id="e7cf3-142">.NET Framework 2.0</span><span class="sxs-lookup"><span data-stu-id="e7cf3-142">.NET Framework 2.0</span></span>     | `net20`  |
| <span data-ttu-id="e7cf3-143">.NET Framework 3.0</span><span class="sxs-lookup"><span data-stu-id="e7cf3-143">.NET Framework 3.0</span></span>     | `net30`  |
| <span data-ttu-id="e7cf3-144">.NET Framework 3,5</span><span class="sxs-lookup"><span data-stu-id="e7cf3-144">.NET Framework 3.5</span></span>     | `net35`  |
| <span data-ttu-id="e7cf3-145">.NET Framework 4.0</span><span class="sxs-lookup"><span data-stu-id="e7cf3-145">.NET Framework 4.0</span></span>     | `net40`  |
| <span data-ttu-id="e7cf3-146">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="e7cf3-146">.NET Framework 4.5</span></span>     | `net45`  |
| <span data-ttu-id="e7cf3-147">.NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="e7cf3-147">.NET Framework 4.5.1</span></span>   | `net451` |
| <span data-ttu-id="e7cf3-148">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="e7cf3-148">.NET Framework 4.5.2</span></span>   | `net452` |
| <span data-ttu-id="e7cf3-149">.NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="e7cf3-149">.NET Framework 4.6</span></span>     | `net46`  |
| <span data-ttu-id="e7cf3-150">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="e7cf3-150">.NET Framework 4.6.1</span></span>   | `net461` |
| <span data-ttu-id="e7cf3-151">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="e7cf3-151">.NET Framework 4.6.2</span></span>   | `net462` |
| <span data-ttu-id="e7cf3-152">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="e7cf3-152">.NET Framework 4.7</span></span>     | `net47`  |
| <span data-ttu-id="e7cf3-153">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="e7cf3-153">.NET Framework 4.8</span></span>     | `net48`  |

<span data-ttu-id="e7cf3-154">Después, inserte el TFM en la sección `TargetFramework` de su archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-154">You then insert this TFM into the `TargetFramework` section of your project file.</span></span> <span data-ttu-id="e7cf3-155">El siguiente es un ejemplo de cómo podría escribir una biblioteca que tenga como destino .NET Framework 4.0:</span><span class="sxs-lookup"><span data-stu-id="e7cf3-155">For example, here's how you would write a library that targets .NET Framework 4.0:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>net40</TargetFramework>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="e7cf3-156">Y listo.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-156">And that's it!</span></span> <span data-ttu-id="e7cf3-157">Aunque esto solo hace la compilación para .NET Framework 4, puede usar la biblioteca en las versiones más recientes de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-157">Although this compiled only for .NET Framework 4, you can use the library on newer versions of .NET Framework.</span></span>

## <a name="how-to-multitarget"></a><span data-ttu-id="e7cf3-158">Cómo lograr la compatibilidad con varias versiones</span><span class="sxs-lookup"><span data-stu-id="e7cf3-158">How to multitarget</span></span>

> [!NOTE]
> <span data-ttu-id="e7cf3-159">Las instrucciones siguientes suponen que tiene instalado .NET Framework en su máquina.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-159">The following instructions assume you have the .NET Framework installed on your machine.</span></span> <span data-ttu-id="e7cf3-160">Consulte la sección de [requisitos previos](#prerequisites) para información sobre las dependencias que debe instalar y dónde descargarlas.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-160">Refer to the [Prerequisites](#prerequisites) section to learn which dependencies you need to install and where to download them from.</span></span>

<span data-ttu-id="e7cf3-161">Es posible que deba tener como destino versiones anteriores de .NET Framework cuando el proyecto admite .NET Framework y .NET.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-161">You may need to target older versions of the .NET Framework when your project supports both the .NET Framework and .NET.</span></span> <span data-ttu-id="e7cf3-162">En este escenario, si desea usar API más recientes y construcciones de lenguaje para los destinos más recientes, use las directivas `#if` en el código.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-162">In this scenario, if you want to use newer APIs and language constructs for the newer targets, use `#if` directives in your code.</span></span> <span data-ttu-id="e7cf3-163">También es posible que tenga que agregar distintos paquetes y dependencias para cada plataforma que tiene como destino para incluir las distintas API necesarias para cada caso.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-163">You also might need to add different packages and dependencies for each platform you're targeting to include the different APIs needed for each case.</span></span>

<span data-ttu-id="e7cf3-164">Por ejemplo, digamos que tiene una biblioteca que realiza operaciones de red a través de HTTP.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-164">For example, let's say you have a library that performs networking operations over HTTP.</span></span> <span data-ttu-id="e7cf3-165">En el estándar .NET y .NET Framework versión 4.5 o superiores, puede usar la clase `HttpClient` del espacio de nombres `System.Net.Http`.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-165">For .NET Standard and the .NET Framework versions 4.5 or higher, you can use the `HttpClient` class from the `System.Net.Http` namespace.</span></span> <span data-ttu-id="e7cf3-166">Sin embargo, las versiones anteriores de .NET Framework no tienen la clase `HttpClient`, por lo que, en su lugar, podría usar la clase `WebClient` del espacio de nombres `System.Net` para esas versiones.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-166">However, earlier versions of the .NET Framework don't have the `HttpClient` class, so you could use the `WebClient` class from the `System.Net` namespace for those instead.</span></span>

<span data-ttu-id="e7cf3-167">Su archivo del proyecto podría tener la siguiente apariencia:</span><span class="sxs-lookup"><span data-stu-id="e7cf3-167">Your project file could look like this:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFrameworks>netstandard2.0;net40;net45</TargetFrameworks>
  </PropertyGroup>

  <!-- Need to conditionally bring in references for the .NET Framework 4.0 target -->
  <ItemGroup Condition="'$(TargetFramework)' == 'net40'">
    <Reference Include="System.Net" />
  </ItemGroup>

  <!-- Need to conditionally bring in references for the .NET Framework 4.5 target -->
  <ItemGroup Condition="'$(TargetFramework)' == 'net45'">
    <Reference Include="System.Net.Http" />
    <Reference Include="System.Threading.Tasks" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="e7cf3-168">Observará tres cambios principales aquí:</span><span class="sxs-lookup"><span data-stu-id="e7cf3-168">You'll notice three major changes here:</span></span>

1. <span data-ttu-id="e7cf3-169">El nodo `TargetFramework` se ha reemplazado por `TargetFrameworks`, y se expresan tres TFM dentro.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-169">The `TargetFramework` node has been replaced by `TargetFrameworks`, and three TFMs are expressed inside.</span></span>
1. <span data-ttu-id="e7cf3-170">Existe un nodo `<ItemGroup>` para el destino `net40` que se dirige a una referencia de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-170">There is an `<ItemGroup>` node for the `net40` target pulling in one .NET Framework reference.</span></span>
1. <span data-ttu-id="e7cf3-171">Existe un nodo `<ItemGroup>` para el destino `net45` que se dirige a dos referencias de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-171">There is an `<ItemGroup>` node for the `net45` target pulling in two .NET Framework references.</span></span>

<span data-ttu-id="e7cf3-172">El sistema de compilación conoce los siguientes símbolos del preprocesador que se usan en las directivas `#if`:</span><span class="sxs-lookup"><span data-stu-id="e7cf3-172">The build system is aware of the following preprocessor symbols used in `#if` directives:</span></span>

[!INCLUDE [Preprocessor symbols](../../../includes/preprocessor-symbols.md)]

<span data-ttu-id="e7cf3-173">Aquí se muestra un ejemplo en el que se usa la compilación condicional por destino:</span><span class="sxs-lookup"><span data-stu-id="e7cf3-173">Here is an example making use of conditional compilation per-target:</span></span>

```csharp
using System;
using System.Text.RegularExpressions;
#if NET40
// This only compiles for the .NET Framework 4 targets
using System.Net;
#else
 // This compiles for all other targets
using System.Net.Http;
using System.Threading.Tasks;
#endif

namespace MultitargetLib
{
    public class Library
    {
#if NET40
        private readonly WebClient _client = new WebClient();
        private readonly object _locker = new object();
#else
        private readonly HttpClient _client = new HttpClient();
#endif

#if NET40
        // .NET Framework 4.0 does not have async/await
        public string GetDotNetCount()
        {
            string url = "https://www.dotnetfoundation.org/";

            var uri = new Uri(url);

            string result = "";

            // Lock here to provide thread-safety.
            lock(_locker)
            {
                result = _client.DownloadString(uri);
            }

            int dotNetCount = Regex.Matches(result, ".NET").Count;

            return $"Dotnet Foundation mentions .NET {dotNetCount} times!";
        }
#else
        // .NET Framework 4.5+ can use async/await!
        public async Task<string> GetDotNetCountAsync()
        {
            string url = "https://www.dotnetfoundation.org/";

            // HttpClient is thread-safe, so no need to explicitly lock here
            var result = await _client.GetStringAsync(url);

            int dotNetCount = Regex.Matches(result, ".NET").Count;

            return $"dotnetfoundation.org mentions .NET {dotNetCount} times in its HTML!";
        }
#endif
    }
}
```

<span data-ttu-id="e7cf3-174">Si crea este proyecto con `dotnet build`, observará tres directorios en la carpeta `bin/`:</span><span class="sxs-lookup"><span data-stu-id="e7cf3-174">If you build this project with `dotnet build`, you'll notice three directories under the `bin/` folder:</span></span>

```
net40/
net45/
netstandard2.0/
```

<span data-ttu-id="e7cf3-175">Cada uno de ellos contiene los archivos `.dll` para cada destino.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-175">Each of these contains the `.dll` files for each target.</span></span>

## <a name="how-to-test-libraries-on-net"></a><span data-ttu-id="e7cf3-176">Prueba de las bibliotecas en .NET</span><span class="sxs-lookup"><span data-stu-id="e7cf3-176">How to test libraries on .NET</span></span>

<span data-ttu-id="e7cf3-177">Es importante poder probar las plataformas.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-177">It's important to be able to test across platforms.</span></span> <span data-ttu-id="e7cf3-178">Puede usar [xUnit](https://xunit.net/) o MSTest de fábrica.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-178">You can use either [xUnit](https://xunit.net/) or MSTest out of the box.</span></span> <span data-ttu-id="e7cf3-179">Ambos son perfectamente adecuados para las pruebas unitarias de su biblioteca en .NET.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-179">Both are perfectly suitable for unit testing your library on .NET.</span></span> <span data-ttu-id="e7cf3-180">Cómo configurar la solución con proyectos de prueba dependerá de la [estructura de la solución](#structuring-a-solution).</span><span class="sxs-lookup"><span data-stu-id="e7cf3-180">How you set up your solution with test projects will depend on the [structure of your solution](#structuring-a-solution).</span></span> <span data-ttu-id="e7cf3-181">En el ejemplo siguiente se presupone que los directorios de origen y de prueba residen en el mismo directorio de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-181">The following example assumes that the test and source directories live in the same top-level directory.</span></span>

> [!NOTE]
> <span data-ttu-id="e7cf3-182">Esto usa algunos [comandos de la CLI de .NET](../tools/index.md).</span><span class="sxs-lookup"><span data-stu-id="e7cf3-182">This uses some [.NET CLI](../tools/index.md) commands.</span></span> <span data-ttu-id="e7cf3-183">Vea [dotnet new](../tools/dotnet-new.md) y [dotnet sln](../tools/dotnet-sln.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-183">See [dotnet new](../tools/dotnet-new.md) and [dotnet sln](../tools/dotnet-sln.md) for more information.</span></span>

1. <span data-ttu-id="e7cf3-184">Configure la solución.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-184">Set up your solution.</span></span> <span data-ttu-id="e7cf3-185">Puede hacerlo con los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="e7cf3-185">You can do so with the following commands:</span></span>

   ```dotnetcli
   mkdir SolutionWithSrcAndTest
   cd SolutionWithSrcAndTest
   dotnet new sln
   dotnet new classlib -o MyProject
   dotnet new xunit -o MyProject.Test
   dotnet sln add MyProject/MyProject.csproj
   dotnet sln add MyProject.Test/MyProject.Test.csproj
   ```

   <span data-ttu-id="e7cf3-186">Esto creará proyectos y se vincularán conjuntamente en una solución.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-186">This will create projects and link them together in a solution.</span></span> <span data-ttu-id="e7cf3-187">Su directorio para `SolutionWithSrcAndTest` debe tener el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="e7cf3-187">Your directory for `SolutionWithSrcAndTest` should look like this:</span></span>

   ```
   /SolutionWithSrcAndTest
   |__SolutionWithSrcAndTest.sln
   |__MyProject/
   |__MyProject.Test/
   ```

1. <span data-ttu-id="e7cf3-188">Vaya al directorio del proyecto de prueba y agregue una referencia a `MyProject.Test` desde `MyProject`.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-188">Navigate to the test project's directory and add a reference to `MyProject.Test` from `MyProject`.</span></span>

   ```dotnetcli
   cd MyProject.Test
   dotnet add reference ../MyProject/MyProject.csproj
   ```

1. <span data-ttu-id="e7cf3-189">Restaurar paquetes y crear proyectos:</span><span class="sxs-lookup"><span data-stu-id="e7cf3-189">Restore packages and build projects:</span></span>

   ```dotnetcli
   dotnet restore
   dotnet build
   ```

1. <span data-ttu-id="e7cf3-190">Compruebe que xUnit se ejecuta mediante la ejecución del comando `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-190">Verify that xUnit runs by executing the `dotnet test` command.</span></span> <span data-ttu-id="e7cf3-191">Si decide usar MSTest, entonces debe ejecutarse en su lugar el ejecutor de la consola de MSTest.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-191">If you chose to use MSTest, then the MSTest console runner should run instead.</span></span>

<span data-ttu-id="e7cf3-192">Y listo.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-192">And that's it!</span></span> <span data-ttu-id="e7cf3-193">Ahora puede probar la biblioteca en todas las plataformas; para ello, use herramientas de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-193">You can now test your library across all platforms using command-line tools.</span></span> <span data-ttu-id="e7cf3-194">Para seguir con las pruebas ahora que ya está todo configurado, probar la biblioteca es un proceso muy simple:</span><span class="sxs-lookup"><span data-stu-id="e7cf3-194">To continue testing now that you have everything set up, testing your library is very simple:</span></span>

1. <span data-ttu-id="e7cf3-195">Haga los cambios en la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-195">Make changes to your library.</span></span>
1. <span data-ttu-id="e7cf3-196">Ejecute las pruebas desde la línea de comandos, en el directorio de prueba, con el comando `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-196">Run tests from the command line, in your test directory, with `dotnet test` command.</span></span>

<span data-ttu-id="e7cf3-197">El código se recompilará automáticamente cuando invoque el comando `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-197">Your code will be automatically rebuilt when you invoke `dotnet test` command.</span></span>

## <a name="how-to-use-multiple-projects"></a><span data-ttu-id="e7cf3-198">Uso de varios proyectos</span><span class="sxs-lookup"><span data-stu-id="e7cf3-198">How to use multiple projects</span></span>

<span data-ttu-id="e7cf3-199">Una necesidad en común de las bibliotecas de mayor tamaño es ubicar la funcionalidad en distintos proyectos.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-199">A common need for larger libraries is to place functionality in different projects.</span></span>

<span data-ttu-id="e7cf3-200">Imagine que desea compilar una biblioteca que se pudiera consumir en C# y F# idiomático.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-200">Imagine you want to build a library that could be consumed in idiomatic C# and F#.</span></span> <span data-ttu-id="e7cf3-201">Eso significaría que los usuarios de las bibliotecas las consumirían de manera natural para C# o F#.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-201">That would mean that consumers of your library consume it in ways that are natural to C# or F#.</span></span> <span data-ttu-id="e7cf3-202">Por ejemplo, en C#, podría consumir la biblioteca de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="e7cf3-202">For example, in C# you might consume the library like this:</span></span>

```csharp
using AwesomeLibrary.CSharp;

public Task DoThings(Data data)
{
    var convertResult = await AwesomeLibrary.ConvertAsync(data);
    var result = AwesomeLibrary.Process(convertResult);
    // do something with result
}
```

<span data-ttu-id="e7cf3-203">En F#, sería de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="e7cf3-203">In F#, it might look like this:</span></span>

```fsharp
open AwesomeLibrary.FSharp

let doWork data = async {
    let! result = AwesomeLibrary.AsyncConvert data // Uses an F# async function rather than C# async method
    // do something with result
}
```

<span data-ttu-id="e7cf3-204">Escenarios de consumo similares a este significan que las API a las que se tiene acceso deben tener una estructura distinta para C# y para F#.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-204">Consumption scenarios like this mean that the APIs being accessed have to have a different structure for C# and F#.</span></span>  <span data-ttu-id="e7cf3-205">Un enfoque común para lograrlo es factorizar toda la lógica de una biblioteca en un proyecto central, con los proyectos de C# y F# definiendo los niveles de API que hacen llamadas a ese proyecto central.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-205">A common approach to accomplishing this is to factor all of the logic of a library into a core project, with C# and F# projects defining the API layers that call into that core project.</span></span>  <span data-ttu-id="e7cf3-206">En el resto de la sección se usarán los siguientes nombres:</span><span class="sxs-lookup"><span data-stu-id="e7cf3-206">The rest of the section will use the following names:</span></span>

* <span data-ttu-id="e7cf3-207">**AwesomeLibrary.Core**: un proyecto central que contiene toda la lógica de la biblioteca</span><span class="sxs-lookup"><span data-stu-id="e7cf3-207">**AwesomeLibrary.Core** - A core project that contains all logic for the library</span></span>
* <span data-ttu-id="e7cf3-208">**AwesomeLibrary.CSharp**: un proyecto con API públicas pensado para el consumo en C#</span><span class="sxs-lookup"><span data-stu-id="e7cf3-208">**AwesomeLibrary.CSharp** - A project with public APIs intended for consumption in C#</span></span>
* <span data-ttu-id="e7cf3-209">**AwesomeLibrary.FSharp**: un proyecto con API públicas pensado para el consumo en F#</span><span class="sxs-lookup"><span data-stu-id="e7cf3-209">**AwesomeLibrary.FSharp** - A project with public APIs intended for consumption in F#</span></span>

<span data-ttu-id="e7cf3-210">Puede ejecutar los siguientes comandos en su terminal para generar la misma estructura de esta guía:</span><span class="sxs-lookup"><span data-stu-id="e7cf3-210">You can run the following commands in your terminal to produce the same structure as this guide:</span></span>

```dotnetcli
mkdir AwesomeLibrary && cd AwesomeLibrary
dotnet new sln
mkdir AwesomeLibrary.Core && cd AwesomeLibrary.Core && dotnet new classlib
cd ..
mkdir AwesomeLibrary.CSharp && cd AwesomeLibrary.CSharp && dotnet new classlib
cd ..
mkdir AwesomeLibrary.FSharp && cd AwesomeLibrary.FSharp && dotnet new classlib -lang "F#"
cd ..
dotnet sln add AwesomeLibrary.Core/AwesomeLibrary.Core.csproj
dotnet sln add AwesomeLibrary.CSharp/AwesomeLibrary.CSharp.csproj
dotnet sln add AwesomeLibrary.FSharp/AwesomeLibrary.FSharp.fsproj
```

<span data-ttu-id="e7cf3-211">Esto agregará los tres proyectos anteriores y un archivo de solución que los vincula conjuntamente.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-211">This will add the three projects above and a solution file that links them together.</span></span> <span data-ttu-id="e7cf3-212">Crear el archivo de solución y vincular los proyectos le permitirá restaurar y crear proyectos desde un nivel superior.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-212">Creating the solution file and linking projects will allow you to restore and build projects from a top level.</span></span>

### <a name="project-to-project-referencing"></a><span data-ttu-id="e7cf3-213">Referencias entre proyectos</span><span class="sxs-lookup"><span data-stu-id="e7cf3-213">Project-to-project referencing</span></span>

<span data-ttu-id="e7cf3-214">La mejor manera de hacer referencia a un proyecto es usar la CLI de .NET para agregar una referencia de proyecto.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-214">The best way to reference a project is to use the .NET CLI to add a project reference.</span></span> <span data-ttu-id="e7cf3-215">Desde los directorios del proyecto **AwesomeLibrary.CSharp** y **AwesomeLibrary.FSharp**, puede ejecutar el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="e7cf3-215">From the **AwesomeLibrary.CSharp** and **AwesomeLibrary.FSharp** project directories, you can run the following command:</span></span>

```dotnetcli
dotnet add reference ../AwesomeLibrary.Core/AwesomeLibrary.Core.csproj
```

<span data-ttu-id="e7cf3-216">Los archivos del proyecto para **AwesomeLibrary.CSharp** y **AwesomeLibrary.FSharp** ahora harán referencia a **AwesomeLibrary.Core** como un destino `ProjectReference`.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-216">The project files for both **AwesomeLibrary.CSharp** and **AwesomeLibrary.FSharp** will now reference **AwesomeLibrary.Core** as a `ProjectReference` target.</span></span>  <span data-ttu-id="e7cf3-217">Puede comprobar esto inspeccionando los archivos del proyecto y observando lo siguiente en ellos:</span><span class="sxs-lookup"><span data-stu-id="e7cf3-217">You can verify this by inspecting the project files and seeing the following in them:</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\AwesomeLibrary.Core\AwesomeLibrary.Core.csproj" />
</ItemGroup>
```

<span data-ttu-id="e7cf3-218">Puede agregar esta sección a cada archivo del proyecto manualmente si prefiere no usar la CLI de .NET.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-218">You can add this section to each project file manually if you prefer not to use the .NET CLI.</span></span>

### <a name="structuring-a-solution"></a><span data-ttu-id="e7cf3-219">Estructura de una solución</span><span class="sxs-lookup"><span data-stu-id="e7cf3-219">Structuring a solution</span></span>

<span data-ttu-id="e7cf3-220">Otro aspecto importante de las soluciones de varios proyectos es establecer una buena estructura de proyecto general.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-220">Another important aspect of multi-project solutions is establishing a good overall project structure.</span></span> <span data-ttu-id="e7cf3-221">Puede organizar el código de la manera que quiera, y siempre y cuando vincule cada proyecto a su archivo de solución con `dotnet sln add`, podrá ejecutar `dotnet restore` y `dotnet build` en el nivel de solución.</span><span class="sxs-lookup"><span data-stu-id="e7cf3-221">You can organize code however you like, and as long as you link each project to your solution file with `dotnet sln add`, you will be able to run `dotnet restore` and `dotnet build` at the solution level.</span></span>
