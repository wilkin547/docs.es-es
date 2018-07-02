---
title: Desarrollo de bibliotecas con herramientas multiplataforma
description: Obtenga información sobre cómo crear bibliotecas de .NET con las herramientas de la CLI de .NET Core.
author: cartermp
ms.author: mairaw
ms.date: 05/01/2017
ms.openlocfilehash: a6db7a15c484122600afd54814d19ea11bd1abc1
ms.sourcegitcommit: ceca5a1c027627abcca2767567703c3879f33325
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2018
ms.locfileid: "33218152"
---
# <a name="developing-libraries-with-cross-platform-tools"></a><span data-ttu-id="2aeda-103">Desarrollo de bibliotecas con herramientas multiplataforma</span><span class="sxs-lookup"><span data-stu-id="2aeda-103">Developing Libraries with Cross Platform Tools</span></span>

<span data-ttu-id="2aeda-104">En este artículo se explica cómo escribir bibliotecas para .NET mediante el uso de herramientas multiplataforma de la CLI.</span><span class="sxs-lookup"><span data-stu-id="2aeda-104">This article covers how to write libraries for .NET using cross-platform CLI tools.</span></span> <span data-ttu-id="2aeda-105">La CLI proporciona una experiencia eficaz y de bajo nivel que funciona en todos los SO compatibles.</span><span class="sxs-lookup"><span data-stu-id="2aeda-105">The CLI provides an efficient and low-level experience that works across any supported OS.</span></span> <span data-ttu-id="2aeda-106">De todos modos puede seguir compilando bibliotecas con Visual Studio; si esa es la experiencia de su preferencia, [consulte la guía sobre Visual Studio](libraries-with-vs.md).</span><span class="sxs-lookup"><span data-stu-id="2aeda-106">You can still build libraries with Visual Studio, and if that is your preferred experience [refer to the Visual Studio guide](libraries-with-vs.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2aeda-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="2aeda-107">Prerequisites</span></span>

<span data-ttu-id="2aeda-108">Necesita [la CLI y el SDK de .NET Core](https://www.microsoft.com/net/core) que están instalados en la máquina.</span><span class="sxs-lookup"><span data-stu-id="2aeda-108">You need [the .NET Core SDK and CLI](https://www.microsoft.com/net/core) installed on your machine.</span></span>

<span data-ttu-id="2aeda-109">En las secciones de este documento que se refieren a las versiones de .NET Framework, necesita tener instalado [.NET Framework](http://getdotnet.azurewebsites.net/) en una máquina con Windows.</span><span class="sxs-lookup"><span data-stu-id="2aeda-109">For the sections of this document dealing with .NET Framework versions, you need the [.NET Framework](http://getdotnet.azurewebsites.net/) installed on a Windows machine.</span></span>

<span data-ttu-id="2aeda-110">Además, si desea admitir destinos de .NET Framework anteriores, deberá instalar paquetes de compatibilidad/desarrollador para versiones anteriores del marco de trabajo que se encuentran en la [página de plataformas de destino .NET](http://getdotnet.azurewebsites.net/target-dotnet-platforms.html).</span><span class="sxs-lookup"><span data-stu-id="2aeda-110">Additionally, if you wish to support older .NET Framework targets, you need to install targeting/developer packs for older framework versions from the [.NET target platforms page](http://getdotnet.azurewebsites.net/target-dotnet-platforms.html).</span></span> <span data-ttu-id="2aeda-111">Consulte la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="2aeda-111">Refer to this table:</span></span>

| <span data-ttu-id="2aeda-112">Versión de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2aeda-112">.NET Framework Version</span></span> | <span data-ttu-id="2aeda-113">Qué debe descargar</span><span class="sxs-lookup"><span data-stu-id="2aeda-113">What to download</span></span>                                       |
| ---------------------- | ------------------------------------------------------ |
| <span data-ttu-id="2aeda-114">4.6.1</span><span class="sxs-lookup"><span data-stu-id="2aeda-114">4.6.1</span></span>                  | <span data-ttu-id="2aeda-115">Paquete de compatibilidad de .NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="2aeda-115">.NET Framework 4.6.1 Targeting Pack</span></span>                    |
| <span data-ttu-id="2aeda-116">4.6</span><span class="sxs-lookup"><span data-stu-id="2aeda-116">4.6</span></span>                    | <span data-ttu-id="2aeda-117">Paquete de compatibilidad de .NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="2aeda-117">.NET Framework 4.6 Targeting Pack</span></span>                      |
| <span data-ttu-id="2aeda-118">4.5.2</span><span class="sxs-lookup"><span data-stu-id="2aeda-118">4.5.2</span></span>                  | <span data-ttu-id="2aeda-119">Paquete de desarrollador de .NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="2aeda-119">.NET Framework 4.5.2 Developer Pack</span></span>                    |
| <span data-ttu-id="2aeda-120">4.5.1</span><span class="sxs-lookup"><span data-stu-id="2aeda-120">4.5.1</span></span>                  | <span data-ttu-id="2aeda-121">Paquete de desarrollador de .NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="2aeda-121">.NET Framework 4.5.1 Developer Pack</span></span>                    |
| <span data-ttu-id="2aeda-122">4.5</span><span class="sxs-lookup"><span data-stu-id="2aeda-122">4.5</span></span>                    | <span data-ttu-id="2aeda-123">Kit de desarrollo de software de Windows para Windows 8</span><span class="sxs-lookup"><span data-stu-id="2aeda-123">Windows Software Development Kit for Windows 8</span></span>         |
| <span data-ttu-id="2aeda-124">4.0</span><span class="sxs-lookup"><span data-stu-id="2aeda-124">4.0</span></span>                    | <span data-ttu-id="2aeda-125">Windows SDK para Windows 7 y .NET Framework 4</span><span class="sxs-lookup"><span data-stu-id="2aeda-125">Windows SDK for Windows 7 and .NET Framework 4</span></span>         |
| <span data-ttu-id="2aeda-126">2.0, 3.0 y 3.5</span><span class="sxs-lookup"><span data-stu-id="2aeda-126">2.0, 3.0, and 3.5</span></span>      | <span data-ttu-id="2aeda-127">Entorno de ejecución de .NET Framework 3.5 SP1 (o una versión posterior a Windows 8)</span><span class="sxs-lookup"><span data-stu-id="2aeda-127">.NET Framework 3.5 SP1 Runtime (or Windows 8+ version)</span></span> |

## <a name="how-to-target-the-net-standard"></a><span data-ttu-id="2aeda-128">Estándar .NET como destino</span><span class="sxs-lookup"><span data-stu-id="2aeda-128">How to target the .NET Standard</span></span>

<span data-ttu-id="2aeda-129">Si no conoce bien el estándar .NET, consulte el tema [Estándar .NET](../../standard/net-standard.md) para más información.</span><span class="sxs-lookup"><span data-stu-id="2aeda-129">If you're not quite familiar with the .NET Standard, refer to the [.NET Standard](../../standard/net-standard.md) to learn more.</span></span>

<span data-ttu-id="2aeda-130">En ese artículo podrá ver una tabla que asigna las versiones del estándar .NET a diversas implementaciones:</span><span class="sxs-lookup"><span data-stu-id="2aeda-130">In that article, there is a table which maps .NET Standard versions to various implementations:</span></span>

[!INCLUDE [net-standard-table](~/includes/net-standard-table.md)]

<span data-ttu-id="2aeda-131">Este es el significado de la tabla para crear una biblioteca:</span><span class="sxs-lookup"><span data-stu-id="2aeda-131">Here's what this table means for the purposes of creating a library:</span></span>

<span data-ttu-id="2aeda-132">La versión de .NET Standard que elija será un equilibrio entre el acceso a las API más recientes y la capacidad de apuntar a más implementaciones .NET y más versiones de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="2aeda-132">The version of the .NET Standard you pick will be a tradeoff between access to the newest APIs and the ability to target more .NET implementations and .NET Standard versions.</span></span> <span data-ttu-id="2aeda-133">Puede controlar el intervalo de versiones y plataformas de destino si elige una versión de `netstandardX.X` (donde `X.X` es un número de versión) y la agrega al archivo del proyecto (`.csproj` o `.fsproj`).</span><span class="sxs-lookup"><span data-stu-id="2aeda-133">You control the range of targetable platforms and versions by picking a version of `netstandardX.X` (Where `X.X` is a version number) and adding it to your project file (`.csproj` or `.fsproj`).</span></span>

<span data-ttu-id="2aeda-134">En función de sus necesidades, tiene 3 opciones principales cuando el destino es el estándar .NET.</span><span class="sxs-lookup"><span data-stu-id="2aeda-134">You have three primary options when targeting the .NET Standard, depending on your needs.</span></span>

1. <span data-ttu-id="2aeda-135">Puede usar la versión predeterminada de .NET Standard que se proporciona con plantillas, `netstandard1.4`, que le permite acceder a la mayoría de API en .NET Standard mientras sigue siendo compatible con UWP, .NET Framework 4.6.1 y el próximo .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="2aeda-135">You can use the default version of the .NET Standard supplied by templates - `netstandard1.4` - which gives you access to most APIs on .NET Standard while still being compatible with UWP, .NET Framework 4.6.1, and the forthcoming .NET Standard 2.0.</span></span>

    ```xml
    <Project Sdk="Microsoft.NET.Sdk">
      <PropertyGroup>
        <TargetFramework>netstandard1.4</TargetFramework>
      </PropertyGroup>
    </Project>
    ```

2. <span data-ttu-id="2aeda-136">Puede usar una versión anterior o posterior de .NET Standard modificando el valor en el nodo `TargetFramework` de su archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="2aeda-136">You can use a lower or higher version of the .NET Standard by modifying the value in the `TargetFramework` node of your project file.</span></span>
    
    <span data-ttu-id="2aeda-137">Las versiones del estándar .NET son compatibles con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="2aeda-137">.NET Standard versions are backward compatible.</span></span> <span data-ttu-id="2aeda-138">Eso significa que las bibliotecas `netstandard1.0` se pueden ejecutar en plataformas `netstandard1.1` y versiones superiores.</span><span class="sxs-lookup"><span data-stu-id="2aeda-138">That means that `netstandard1.0` libraries run on `netstandard1.1` platforms and higher.</span></span> <span data-ttu-id="2aeda-139">Sin embargo, no existe compatibilidad con versiones posteriores: las plataformas del estándar .NET inferiores no pueden hacer referencia a las superiores.</span><span class="sxs-lookup"><span data-stu-id="2aeda-139">However, there is no forward compatibility - lower .NET Standard platforms cannot reference higher ones.</span></span> <span data-ttu-id="2aeda-140">Esto significa que las bibliotecas `netstandard1.0` no pueden hacer referencia a las bibliotecas que tienen como destino `netstandard1.1` o una versión superior.</span><span class="sxs-lookup"><span data-stu-id="2aeda-140">This means that `netstandard1.0` libraries cannot reference libraries targeting `netstandard1.1` or higher.</span></span> <span data-ttu-id="2aeda-141">Seleccione la versión estándar que tiene la combinación adecuada de compatibilidad con API y plataformas que necesita.</span><span class="sxs-lookup"><span data-stu-id="2aeda-141">Select the Standard version that has the right mix of APIs and platform support for your needs.</span></span> <span data-ttu-id="2aeda-142">Por ahora le recomendamos `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="2aeda-142">We recommend `netstandard1.4` for now.</span></span>
    
3. <span data-ttu-id="2aeda-143">Si desea tener como destino .NET Framework versión 4.0 o inferior, o bien desea usar una API disponible en .NET Framework pero no disponible en el estándar .NET (por ejemplo, `System.Drawing`), lea las secciones siguientes y sepa cómo tener compatibilidad con múltiples versiones.</span><span class="sxs-lookup"><span data-stu-id="2aeda-143">If you want to target the .NET Framework versions 4.0 or below, or you wish to use an API available in the .NET Framework but not in the .NET Standard (for example, `System.Drawing`), read the following sections and learn how to multitarget.</span></span>

## <a name="how-to-target-the-net-framework"></a><span data-ttu-id="2aeda-144">.NET Framework como destino</span><span class="sxs-lookup"><span data-stu-id="2aeda-144">How to target the .NET Framework</span></span>

> [!NOTE]
> <span data-ttu-id="2aeda-145">Estas instrucciones suponen que tiene instalado .NET Framework en su máquina.</span><span class="sxs-lookup"><span data-stu-id="2aeda-145">These instructions assume you have the .NET Framework installed on your machine.</span></span> <span data-ttu-id="2aeda-146">Consulte los [requisitos previos](#prerequisites) para instalar las dependencias.</span><span class="sxs-lookup"><span data-stu-id="2aeda-146">Refer to the [Prerequisites](#prerequisites) to get dependencies installed.</span></span>

<span data-ttu-id="2aeda-147">Tenga en cuenta que algunas de las versiones de .NET Framework que se usan aquí ya no cuentan con soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="2aeda-147">Keep in mind that some of the .NET Framework versions used here are no longer in support.</span></span> <span data-ttu-id="2aeda-148">Consulte las [P+F sobre la directiva del ciclo de vida de soporte técnico de .NET Framework](https://support.microsoft.com/gp/framework_faq/en-us) sobre las versiones sin soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="2aeda-148">Refer to the [.NET Framework Support Lifecycle Policy FAQ](https://support.microsoft.com/gp/framework_faq/en-us) about unsupported versions.</span></span>

<span data-ttu-id="2aeda-149">Si quiere llegar a la mayor cantidad posible de desarrolladores y proyectos, use .NET Framework 4.0 como el destino de línea base.</span><span class="sxs-lookup"><span data-stu-id="2aeda-149">If you want to reach the maximum number of developers and projects, use the .NET Framework 4.0 as your baseline target.</span></span> <span data-ttu-id="2aeda-150">Para tener .NET Framework como destino, deberá comenzar por el uso del moniker de la plataforma de destino (TFM) correcto que corresponda a la versión de .NET Framework que desea admitir.</span><span class="sxs-lookup"><span data-stu-id="2aeda-150">To target the .NET Framework, you will need to begin by using the correct Target Framework Moniker (TFM) that corresponds to the .NET Framework version you wish to support.</span></span>

```
.NET Framework 2.0   --> net20
.NET Framework 3.0   --> net30
.NET Framework 3.5   --> net35
.NET Framework 4.0   --> net40
.NET Framework 4.5   --> net45
.NET Framework 4.5.1 --> net451
.NET Framework 4.5.2 --> net452
.NET Framework 4.6   --> net46
.NET Framework 4.6.1 --> net461
.NET Framework 4.6.2 --> net462
.NET Framework 4.7   --> net47
```

<span data-ttu-id="2aeda-151">Después, inserte el TFM en la sección `TargetFramework` de su archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="2aeda-151">You then insert this TFM into the `TargetFramework` section of your project file.</span></span> <span data-ttu-id="2aeda-152">El siguiente es un ejemplo de cómo podría escribir una biblioteca que tenga como destino la versión .NET Framework 4.0:</span><span class="sxs-lookup"><span data-stu-id="2aeda-152">For example, here's how you would write a library which targets the .NET Framework 4.0:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>net40</TargetFramework>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="2aeda-153">Y listo.</span><span class="sxs-lookup"><span data-stu-id="2aeda-153">And that's it!</span></span> <span data-ttu-id="2aeda-154">Aunque esto solo hace la compilación para .NET Framework 4, puede usar la biblioteca en las versiones más recientes de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2aeda-154">Although this compiled only for the .NET Framework 4, you can use the library on newer versions of the .NET Framework.</span></span>

## <a name="how-to-multitarget"></a><span data-ttu-id="2aeda-155">Cómo lograr la compatibilidad con múltiples versiones</span><span class="sxs-lookup"><span data-stu-id="2aeda-155">How to Multitarget</span></span>

> [!NOTE]
> <span data-ttu-id="2aeda-156">Las instrucciones siguientes suponen que tiene instalado .NET Framework en su máquina.</span><span class="sxs-lookup"><span data-stu-id="2aeda-156">The following instructions assume you have the .NET Framework installed on your machine.</span></span> <span data-ttu-id="2aeda-157">Consulte la sección de [requisitos previos](#prerequisites) para información sobre las dependencias que debe instalar y dónde descargarlas.</span><span class="sxs-lookup"><span data-stu-id="2aeda-157">Refer to the [Prerequisites](#prerequisites) section to learn which dependencies you need to install and where to download them from.</span></span>

<span data-ttu-id="2aeda-158">Es posible que deba tener como destino versiones anteriores de .NET Framework cuando el proyecto admite .NET Framework y .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2aeda-158">You may need to target older versions of the .NET Framework when your project supports both the .NET Framework and .NET Core.</span></span> <span data-ttu-id="2aeda-159">En este escenario, si desea usar API más recientes y construcciones de lenguaje para los destinos más recientes, use las directivas `#if` en el código.</span><span class="sxs-lookup"><span data-stu-id="2aeda-159">In this scenario, if you want to use newer APIs and language constructs for the newer targets, use `#if` directives in your code.</span></span> <span data-ttu-id="2aeda-160">También es posible que tenga que agregar distintos paquetes y dependencias para cada plataforma que tiene como destino para incluir las distintas API necesarias para cada caso.</span><span class="sxs-lookup"><span data-stu-id="2aeda-160">You also might need to add different packages and dependencies for each platform you're targeting to include the different APIs needed for each case.</span></span>

<span data-ttu-id="2aeda-161">Por ejemplo, digamos que tiene una biblioteca que realiza operaciones de red a través de HTTP.</span><span class="sxs-lookup"><span data-stu-id="2aeda-161">For example, let's say you have a library that performs networking operations over HTTP.</span></span> <span data-ttu-id="2aeda-162">En el estándar .NET y .NET Framework versión 4.5 o superiores, puede usar la clase `HttpClient` del espacio de nombres `System.Net.Http`.</span><span class="sxs-lookup"><span data-stu-id="2aeda-162">For .NET Standard and the .NET Framework versions 4.5 or higher, you can use the `HttpClient` class from the `System.Net.Http` namespace.</span></span> <span data-ttu-id="2aeda-163">Sin embargo, las versiones anteriores de .NET Framework no tienen la clase `HttpClient`, por lo que, en su lugar, podría usar la clase `WebClient` del espacio de nombres `System.Net` para esas versiones.</span><span class="sxs-lookup"><span data-stu-id="2aeda-163">However, earlier versions of the .NET Framework don't have the `HttpClient` class, so you could use the `WebClient` class from the `System.Net` namespace for those instead.</span></span>

<span data-ttu-id="2aeda-164">Su archivo del proyecto podría tener la siguiente apariencia:</span><span class="sxs-lookup"><span data-stu-id="2aeda-164">Your project file could look like this:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFrameworks>netstandard1.4;net40;net45</TargetFrameworks>
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

<span data-ttu-id="2aeda-165">Observará tres cambios principales aquí:</span><span class="sxs-lookup"><span data-stu-id="2aeda-165">You'll notice three major changes here:</span></span>

1. <span data-ttu-id="2aeda-166">El nodo `TargetFramework` se ha reemplazado por `TargetFrameworks`, y se expresan tres TFM dentro.</span><span class="sxs-lookup"><span data-stu-id="2aeda-166">The `TargetFramework` node has been replaced by `TargetFrameworks`, and three TFMs are expressed inside.</span></span>
1. <span data-ttu-id="2aeda-167">Existe un nodo `<ItemGroup>` para el destino `net40 ` que se dirige a una referencia de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2aeda-167">There is an `<ItemGroup>` node for the `net40 ` target pulling in one .NET Framework reference.</span></span>
1. <span data-ttu-id="2aeda-168">Existe un nodo `<ItemGroup>` para el destino `net45` que se dirige a dos referencias de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2aeda-168">There is an `<ItemGroup>` node for the `net45` target pulling in two .NET Framework references.</span></span>

<span data-ttu-id="2aeda-169">El sistema de compilación conoce los siguientes símbolos del preprocesador que se usan en las directivas `#if`:</span><span class="sxs-lookup"><span data-stu-id="2aeda-169">The build system is aware of the following preprocessor symbols used in `#if` directives:</span></span>

[!INCLUDE [Preprocessor symbols](~/includes/preprocessor-symbols.md)]

<span data-ttu-id="2aeda-170">Aquí se muestra un ejemplo en el que se usa la compilación condicional por destino:</span><span class="sxs-lookup"><span data-stu-id="2aeda-170">Here is an example making use of conditional compilation per-target:</span></span>

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
            string url = "http://www.dotnetfoundation.org/";

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
        // .NET 4.5+ can use async/await!
        public async Task<string> GetDotNetCountAsync()
        {
            string url = "http://www.dotnetfoundation.org/";

            // HttpClient is thread-safe, so no need to explicitly lock here
            var result = await _client.GetStringAsync(url);

            int dotNetCount = Regex.Matches(result, ".NET").Count;

            return $"dotnetfoundation.org mentions .NET {dotNetCount} times in its HTML!";
        }
#endif
    }
}
```

<span data-ttu-id="2aeda-171">Si crea este proyecto con `dotnet build`, observará tres directorios en la carpeta `bin/`:</span><span class="sxs-lookup"><span data-stu-id="2aeda-171">If you build this project with `dotnet build`, you'll notice three directories under the `bin/` folder:</span></span>

```
net40/
net45/
netstandard1.4/
```

<span data-ttu-id="2aeda-172">Cada uno de ellos contiene los archivos `.dll` para cada destino.</span><span class="sxs-lookup"><span data-stu-id="2aeda-172">Each of these contain the `.dll` files for each target.</span></span>

## <a name="how-to-test-libraries-on-net-core"></a><span data-ttu-id="2aeda-173">Prueba de las bibliotecas en .NET Core</span><span class="sxs-lookup"><span data-stu-id="2aeda-173">How to test libraries on .NET Core</span></span>

<span data-ttu-id="2aeda-174">Es importante poder probar las plataformas.</span><span class="sxs-lookup"><span data-stu-id="2aeda-174">It's important to be able to test across platforms.</span></span> <span data-ttu-id="2aeda-175">Puede usar [xUnit](http://xunit.github.io/) o MSTest de fábrica.</span><span class="sxs-lookup"><span data-stu-id="2aeda-175">You can use either [xUnit](http://xunit.github.io/) or MSTest out of the box.</span></span> <span data-ttu-id="2aeda-176">Ambos son perfectamente adecuados para las pruebas unitarias de su biblioteca en .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2aeda-176">Both are perfectly suitable for unit testing your library on .NET Core.</span></span> <span data-ttu-id="2aeda-177">Cómo configurar la solución con proyectos de prueba dependerá de la [estructura de la solución](#structuring-a-solution).</span><span class="sxs-lookup"><span data-stu-id="2aeda-177">How you set up your solution with test projects will depend on the [structure of your solution](#structuring-a-solution).</span></span> <span data-ttu-id="2aeda-178">En el ejemplo siguiente se presupone que los directorios de origen y de prueba residen en el mismo directorio de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="2aeda-178">The following example assumes that the test and source directories live in the same top-level directory.</span></span>

> [!NOTE]
> <span data-ttu-id="2aeda-179">Esto usa algunos [comandos de la CLI de .NET Core](../tools/index.md).</span><span class="sxs-lookup"><span data-stu-id="2aeda-179">This uses some [.NET Core CLI commands](../tools/index.md).</span></span> <span data-ttu-id="2aeda-180">Vea [dotnet new](../tools/dotnet-new.md) y [dotnet sln](../tools/dotnet-sln.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2aeda-180">See [dotnet new](../tools/dotnet-new.md) and [dotnet sln](../tools/dotnet-sln.md) for more information.</span></span>

1. <span data-ttu-id="2aeda-181">Configure la solución.</span><span class="sxs-lookup"><span data-stu-id="2aeda-181">Set up your solution.</span></span> <span data-ttu-id="2aeda-182">Puede hacerlo con los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="2aeda-182">You can do so with the following commands:</span></span>

   ```bash
   mkdir SolutionWithSrcAndTest
   cd SolutionWithSrcAndTest
   dotnet new sln
   dotnet new classlib -o MyProject
   dotnet new xunit -o MyProject.Test
   dotnet sln add MyProject/MyProject.csproj
   dotnet sln add MyProject.Test/MyProject.Test.csproj
   ```

   <span data-ttu-id="2aeda-183">Esto creará proyectos y se vincularán conjuntamente en una solución.</span><span class="sxs-lookup"><span data-stu-id="2aeda-183">This will create projects and link them together in a solution.</span></span> <span data-ttu-id="2aeda-184">Su directorio para `SolutionWithSrcAndTest` debe tener el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="2aeda-184">Your directory for `SolutionWithSrcAndTest` should look like this:</span></span>

   ```
   /SolutionWithSrcAndTest
   |__SolutionWithSrcAndTest.sln
   |__MyProject/
   |__MyProject.Test/
   ```

1. <span data-ttu-id="2aeda-185">Vaya al directorio del proyecto de prueba y agregue una referencia a `MyProject.Test` desde `MyProject`.</span><span class="sxs-lookup"><span data-stu-id="2aeda-185">Navigate to the test project's directory and add a reference to `MyProject.Test` from `MyProject`.</span></span>

   ```bash
   cd MyProject.Test
   dotnet add reference ../MyProject/MyProject.csproj
   ```

1. <span data-ttu-id="2aeda-186">Restaurar paquetes y crear proyectos:</span><span class="sxs-lookup"><span data-stu-id="2aeda-186">Restore packages and build projects:</span></span>

   ```bash
   dotnet restore
   dotnet build
   ```

   [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

1. <span data-ttu-id="2aeda-187">Compruebe que xUnit se ejecuta mediante la ejecución del comando `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="2aeda-187">Verify that xUnit runs by executing the `dotnet test` command.</span></span> <span data-ttu-id="2aeda-188">Si decide usar MSTest, entonces debe ejecutarse en su lugar el ejecutor de la consola de MSTest.</span><span class="sxs-lookup"><span data-stu-id="2aeda-188">If you chose to use MSTest, then the MSTest console runner should run instead.</span></span>
    
<span data-ttu-id="2aeda-189">Y listo.</span><span class="sxs-lookup"><span data-stu-id="2aeda-189">And that's it!</span></span> <span data-ttu-id="2aeda-190">Ahora puede probar la biblioteca en todas las plataformas; para ello, use herramientas de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="2aeda-190">You can now test your library across all platforms using command line tools.</span></span> <span data-ttu-id="2aeda-191">Para seguir con las pruebas ahora que ya está todo configurado, probar la biblioteca es un proceso muy simple:</span><span class="sxs-lookup"><span data-stu-id="2aeda-191">To continue testing now that you have everything set up, testing your library is very simple:</span></span>

1. <span data-ttu-id="2aeda-192">Haga los cambios en la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="2aeda-192">Make changes to your library.</span></span>
1. <span data-ttu-id="2aeda-193">Ejecute las pruebas desde la línea de comandos, en el directorio de prueba, con el comando `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="2aeda-193">Run tests from the command line, in your test directory, with `dotnet test` command.</span></span>

<span data-ttu-id="2aeda-194">El código se recompilará automáticamente cuando invoque el comando `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="2aeda-194">Your code will be automatically rebuilt when you invoke `dotnet test` command.</span></span>

## <a name="how-to-use-multiple-projects"></a><span data-ttu-id="2aeda-195">Uso de varios proyectos</span><span class="sxs-lookup"><span data-stu-id="2aeda-195">How to use multiple projects</span></span>

<span data-ttu-id="2aeda-196">Una necesidad en común de las bibliotecas de mayor tamaño es ubicar la funcionalidad en distintos proyectos.</span><span class="sxs-lookup"><span data-stu-id="2aeda-196">A common need for larger libraries is to place functionality in different projects.</span></span>

<span data-ttu-id="2aeda-197">Imagine que desea compilar una biblioteca que se pudiera consumir en C# y F# idiomático.</span><span class="sxs-lookup"><span data-stu-id="2aeda-197">Imagine you wished to build a library which could be consumed in idiomatic C# and F#.</span></span> <span data-ttu-id="2aeda-198">Eso significaría que los usuarios de las bibliotecas las consumirían de manera natural para C# o F#.</span><span class="sxs-lookup"><span data-stu-id="2aeda-198">That would mean that consumers of your library consume them in ways which are natural to C# or F#.</span></span> <span data-ttu-id="2aeda-199">Por ejemplo, en C#, podría consumir la biblioteca de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="2aeda-199">For example, in C# you might consume the library like this:</span></span>

```csharp
using AwesomeLibrary.CSharp;

public Task DoThings(Data data)
{
    var convertResult = await AwesomeLibrary.ConvertAsync(data);
    var result = AwesomeLibrary.Process(convertResult);
    // do something with result
}
```

<span data-ttu-id="2aeda-200">En F#, sería de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="2aeda-200">In F#, it might look like this:</span></span>

```fsharp
open AwesomeLibrary.FSharp

let doWork data = async {
    let! result = AwesomeLibrary.AsyncConvert data // Uses an F# async function rather than C# async method
    // do something with result
}
```

<span data-ttu-id="2aeda-201">Escenarios de consumo similares a este significan que las API a las que se tiene acceso deben tener una estructura distinta para C# y para F#.</span><span class="sxs-lookup"><span data-stu-id="2aeda-201">Consumption scenarios like this mean that the APIs being accessed have to have a different structure for C# and F#.</span></span>  <span data-ttu-id="2aeda-202">Un enfoque común para lograrlo es factorizar toda la lógica de una biblioteca en un proyecto central, con los proyectos de C# y F# definiendo los niveles de API que hacen llamadas a ese proyecto central.</span><span class="sxs-lookup"><span data-stu-id="2aeda-202">A common approach to accomplishing this is to factor all of the logic of a library into a core project, with C# and F# projects defining the API layers that call into that core project.</span></span>  <span data-ttu-id="2aeda-203">En el resto de la sección se usarán los siguientes nombres:</span><span class="sxs-lookup"><span data-stu-id="2aeda-203">The rest of the section will use the following names:</span></span>

* <span data-ttu-id="2aeda-204">**AwesomeLibrary.Core**: un proyecto central que contiene toda la lógica de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="2aeda-204">**AwesomeLibrary.Core** - A core project which contains all logic for the library</span></span>
* <span data-ttu-id="2aeda-205">**AwesomeLibrary.CSharp**: un proyecto con API públicas pensado para el consumo en C#</span><span class="sxs-lookup"><span data-stu-id="2aeda-205">**AwesomeLibrary.CSharp** - A project with public APIs intended for consumption in C#</span></span>
* <span data-ttu-id="2aeda-206">**AwesomeLibrary.FSharp**: un proyecto con API públicas pensado para el consumo en F#</span><span class="sxs-lookup"><span data-stu-id="2aeda-206">**AwesomeLibrary.FSharp** - A project with public APIs intended for consumption in F#</span></span>

<span data-ttu-id="2aeda-207">Puede ejecutar los siguientes comandos en su terminal para generar la misma estructura de esta guía:</span><span class="sxs-lookup"><span data-stu-id="2aeda-207">You can run the following commands in your terminal to produce the same structure as this guide:</span></span>

```console
mkdir AwesomeLibrary && cd AwesomeLibrary
dotnet new sln
mkdir AwesomeLibrary.Core && cd AwesomeLibrary.Core && dotnet new classlib
cd ..
mkdir AwesomeLibrary.CSharp && cd AwesomeLibrary.CSharp && dotnet new classlib
cd ..
mkdir AwesomeLibrary.FSharp && cd AwesomeLibrary.FSharp && dotnet new classlib -lang F#
cd ..
dotnet sln add AwesomeLibrary.Core/AwesomeLibrary.Core.csproj
dotnet sln add AwesomeLibrary.CSharp/AwesomeLibrary.CSharp.csproj
dotnet sln add AwesomeLibrary.FSharp/AwesomeLibrary.FSharp.fsproj
```

<span data-ttu-id="2aeda-208">Esto agregará los tres proyectos anteriores y un archivo de solución que los vincula conjuntamente.</span><span class="sxs-lookup"><span data-stu-id="2aeda-208">This will add the three projects above and a solution file which links them together.</span></span> <span data-ttu-id="2aeda-209">Crear el archivo de solución y vincular los proyectos le permitirá restaurar y crear proyectos desde un nivel superior.</span><span class="sxs-lookup"><span data-stu-id="2aeda-209">Creating the solution file and linking projects will allow you to restore and build projects from a top-level.</span></span>

### <a name="project-to-project-referencing"></a><span data-ttu-id="2aeda-210">Referencias entre proyectos</span><span class="sxs-lookup"><span data-stu-id="2aeda-210">Project-to-project referencing</span></span>

<span data-ttu-id="2aeda-211">La mejor manera de hacer referencia a un proyecto es usar la CLI de .NET Core para agregar una referencia de proyecto.</span><span class="sxs-lookup"><span data-stu-id="2aeda-211">The best way to reference a project is to use the .NET Core CLI to add a project reference.</span></span> <span data-ttu-id="2aeda-212">Desde los directorios del proyecto **AwesomeLibrary.CSharp** y **AwesomeLibrary.FSharp**, puede ejecutar el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="2aeda-212">From the **AwesomeLibrary.CSharp** and **AwesomeLibrary.FSharp** project directories, you can run the following command:</span></span>

```console
$ dotnet add reference ../AwesomeLibrary.Core/AwesomeLibrary.Core.csproj
```

<span data-ttu-id="2aeda-213">Los archivos del proyecto para **AwesomeLibrary.CSharp** y **AwesomeLibrary.FSharp** ahora harán referencia a **AwesomeLibrary.Core** como un destino `ProjectReference`.</span><span class="sxs-lookup"><span data-stu-id="2aeda-213">The project files for both **AwesomeLibrary.CSharp** and **AwesomeLibrary.FSharp** will now reference **AwesomeLibrary.Core** as a `ProjectReference` target.</span></span>  <span data-ttu-id="2aeda-214">Puede comprobar esto inspeccionando los archivos del proyecto y observando lo siguiente en ellos:</span><span class="sxs-lookup"><span data-stu-id="2aeda-214">You can verify this by inspecting the project files and seeing the following in them:</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\AwesomeLibrary.Core\AwesomeLibrary.Core.csproj" />
</ItemGroup>
```

<span data-ttu-id="2aeda-215">Puede agregar esta sección a cada archivo del proyecto manualmente si prefiere no usar la CLI de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2aeda-215">You can add this section to each project file manually if you prefer not to use the .NET Core CLI.</span></span>

### <a name="structuring-a-solution"></a><span data-ttu-id="2aeda-216">Estructura de una solución</span><span class="sxs-lookup"><span data-stu-id="2aeda-216">Structuring a solution</span></span>

<span data-ttu-id="2aeda-217">Otro aspecto importante de las soluciones de varios proyectos es establecer una buena estructura de proyecto general.</span><span class="sxs-lookup"><span data-stu-id="2aeda-217">Another important aspect of multi-project solutions is establishing a good overall project structure.</span></span> <span data-ttu-id="2aeda-218">Puede organizar el código de la manera que quiera, y siempre y cuando vincule cada proyecto a su archivo de solución con `dotnet sln add`, podrá ejecutar `dotnet restore` y `dotnet build` en el nivel de solución.</span><span class="sxs-lookup"><span data-stu-id="2aeda-218">You can organize code however you like, and as long as you link each project to your solution file with `dotnet sln add`, you will be able to run `dotnet restore` and `dotnet build` at the solution level.</span></span>
