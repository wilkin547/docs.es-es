---
title: Desarrollo de bibliotecas con herramientas multiplataforma
description: Obtenga información sobre cómo crear bibliotecas de .NET Core con las herramientas de la CLI de .NET Core. Creará una biblioteca que admite varios marcos de trabajo.
author: cartermp
ms.date: 05/01/2017
ms.custom: seodec18
ms.openlocfilehash: 536319bc02b45e7948c89ae67988e821a55a842d
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117413"
---
# <a name="developing-libraries-with-cross-platform-tools"></a><span data-ttu-id="975d8-104">Desarrollo de bibliotecas con herramientas multiplataforma</span><span class="sxs-lookup"><span data-stu-id="975d8-104">Developing Libraries with Cross Platform Tools</span></span>

<span data-ttu-id="975d8-105">En este artículo se explica cómo escribir bibliotecas para .NET mediante el uso de herramientas multiplataforma de la CLI.</span><span class="sxs-lookup"><span data-stu-id="975d8-105">This article covers how to write libraries for .NET using cross-platform CLI tools.</span></span> <span data-ttu-id="975d8-106">La CLI proporciona una experiencia eficaz y de bajo nivel que funciona en todos los SO compatibles.</span><span class="sxs-lookup"><span data-stu-id="975d8-106">The CLI provides an efficient and low-level experience that works across any supported OS.</span></span> <span data-ttu-id="975d8-107">De todos modos puede seguir compilando bibliotecas con Visual Studio; si esa es la experiencia de su preferencia, [consulte la guía sobre Visual Studio](libraries-with-vs.md).</span><span class="sxs-lookup"><span data-stu-id="975d8-107">You can still build libraries with Visual Studio, and if that is your preferred experience [refer to the Visual Studio guide](libraries-with-vs.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="975d8-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="975d8-108">Prerequisites</span></span>

<span data-ttu-id="975d8-109">Necesita [la CLI y el SDK de .NET Core](https://dotnet.microsoft.com/download) que están instalados en la máquina.</span><span class="sxs-lookup"><span data-stu-id="975d8-109">You need [the .NET Core SDK and CLI](https://dotnet.microsoft.com/download) installed on your machine.</span></span>

<span data-ttu-id="975d8-110">En las secciones de este documento que se refieren a las versiones de .NET Framework, necesita tener instalado [.NET Framework](https://dotnet.microsoft.com) en una máquina con Windows.</span><span class="sxs-lookup"><span data-stu-id="975d8-110">For the sections of this document dealing with .NET Framework versions, you need the [.NET Framework](https://dotnet.microsoft.com) installed on a Windows machine.</span></span>

<span data-ttu-id="975d8-111">Además, si desea admitir destinos de .NET Framework anteriores, deberá instalar paquetes de compatibilidad/desarrollador para versiones anteriores del marco que se encuentran en la [página de archivos de descarga de .NET](https://dotnet.microsoft.com/download/archives).</span><span class="sxs-lookup"><span data-stu-id="975d8-111">Additionally, if you wish to support older .NET Framework targets, you need to install targeting/developer packs for older framework versions from the [.NET download archives page](https://dotnet.microsoft.com/download/archives).</span></span> <span data-ttu-id="975d8-112">Consulte la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="975d8-112">Refer to this table:</span></span>

| <span data-ttu-id="975d8-113">Versión de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="975d8-113">.NET Framework Version</span></span> | <span data-ttu-id="975d8-114">Qué debe descargar</span><span class="sxs-lookup"><span data-stu-id="975d8-114">What to download</span></span>                                       |
| ---------------------- | ------------------------------------------------------ |
| <span data-ttu-id="975d8-115">4.6.1</span><span class="sxs-lookup"><span data-stu-id="975d8-115">4.6.1</span></span>                  | <span data-ttu-id="975d8-116">Paquete de compatibilidad de .NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="975d8-116">.NET Framework 4.6.1 Targeting Pack</span></span>                    |
| <span data-ttu-id="975d8-117">4.6</span><span class="sxs-lookup"><span data-stu-id="975d8-117">4.6</span></span>                    | <span data-ttu-id="975d8-118">Paquete de compatibilidad de .NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="975d8-118">.NET Framework 4.6 Targeting Pack</span></span>                      |
| <span data-ttu-id="975d8-119">4.5.2</span><span class="sxs-lookup"><span data-stu-id="975d8-119">4.5.2</span></span>                  | <span data-ttu-id="975d8-120">Paquete de desarrollador de .NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="975d8-120">.NET Framework 4.5.2 Developer Pack</span></span>                    |
| <span data-ttu-id="975d8-121">4.5.1</span><span class="sxs-lookup"><span data-stu-id="975d8-121">4.5.1</span></span>                  | <span data-ttu-id="975d8-122">Paquete de desarrollador de .NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="975d8-122">.NET Framework 4.5.1 Developer Pack</span></span>                    |
| <span data-ttu-id="975d8-123">4.5</span><span class="sxs-lookup"><span data-stu-id="975d8-123">4.5</span></span>                    | <span data-ttu-id="975d8-124">Kit de desarrollo de software de Windows para Windows 8</span><span class="sxs-lookup"><span data-stu-id="975d8-124">Windows Software Development Kit for Windows 8</span></span>         |
| <span data-ttu-id="975d8-125">4.0</span><span class="sxs-lookup"><span data-stu-id="975d8-125">4.0</span></span>                    | <span data-ttu-id="975d8-126">Windows SDK para Windows 7 y .NET Framework 4</span><span class="sxs-lookup"><span data-stu-id="975d8-126">Windows SDK for Windows 7 and .NET Framework 4</span></span>         |
| <span data-ttu-id="975d8-127">2.0, 3.0 y 3.5</span><span class="sxs-lookup"><span data-stu-id="975d8-127">2.0, 3.0, and 3.5</span></span>      | <span data-ttu-id="975d8-128">Entorno de ejecución de .NET Framework 3.5 SP1 (o una versión posterior a Windows 8)</span><span class="sxs-lookup"><span data-stu-id="975d8-128">.NET Framework 3.5 SP1 Runtime (or Windows 8+ version)</span></span> |

## <a name="how-to-target-the-net-standard"></a><span data-ttu-id="975d8-129">Estándar .NET como destino</span><span class="sxs-lookup"><span data-stu-id="975d8-129">How to target the .NET Standard</span></span>

<span data-ttu-id="975d8-130">Si no conoce bien el estándar .NET, consulte el tema [Estándar .NET](../../standard/net-standard.md) para más información.</span><span class="sxs-lookup"><span data-stu-id="975d8-130">If you're not quite familiar with the .NET Standard, refer to the [.NET Standard](../../standard/net-standard.md) to learn more.</span></span>

<span data-ttu-id="975d8-131">En ese artículo podrá ver una tabla que asigna las versiones del estándar .NET a diversas implementaciones:</span><span class="sxs-lookup"><span data-stu-id="975d8-131">In that article, there is a table which maps .NET Standard versions to various implementations:</span></span>

[!INCLUDE [net-standard-table](../../../includes/net-standard-table.md)]

<span data-ttu-id="975d8-132">Este es el significado de la tabla para crear una biblioteca:</span><span class="sxs-lookup"><span data-stu-id="975d8-132">Here's what this table means for the purposes of creating a library:</span></span>

<span data-ttu-id="975d8-133">La versión de .NET Standard que elija será un equilibrio entre el acceso a las API más recientes y la capacidad de apuntar a más implementaciones .NET y más versiones de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="975d8-133">The version of the .NET Standard you pick will be a tradeoff between access to the newest APIs and the ability to target more .NET implementations and .NET Standard versions.</span></span> <span data-ttu-id="975d8-134">Puede controlar el intervalo de versiones y plataformas de destino si elige una versión de `netstandardX.X` (donde `X.X` es un número de versión) y la agrega al archivo del proyecto (`.csproj` o `.fsproj`).</span><span class="sxs-lookup"><span data-stu-id="975d8-134">You control the range of targetable platforms and versions by picking a version of `netstandardX.X` (Where `X.X` is a version number) and adding it to your project file (`.csproj` or `.fsproj`).</span></span>

<span data-ttu-id="975d8-135">En función de sus necesidades, tiene 3 opciones principales cuando el destino es el estándar .NET.</span><span class="sxs-lookup"><span data-stu-id="975d8-135">You have three primary options when targeting the .NET Standard, depending on your needs.</span></span>

1. <span data-ttu-id="975d8-136">Puede usar la versión predeterminada de .NET Standard que se proporciona con plantillas, `netstandard1.4`, que le permite acceder a la mayoría de API en .NET Standard mientras sigue siendo compatible con UWP, .NET Framework 4.6.1 y el próximo .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="975d8-136">You can use the default version of the .NET Standard supplied by templates - `netstandard1.4` - which gives you access to most APIs on .NET Standard while still being compatible with UWP, .NET Framework 4.6.1, and the forthcoming .NET Standard 2.0.</span></span>

    ```xml
    <Project Sdk="Microsoft.NET.Sdk">
      <PropertyGroup>
        <TargetFramework>netstandard1.4</TargetFramework>
      </PropertyGroup>
    </Project>
    ```

2. <span data-ttu-id="975d8-137">Puede usar una versión anterior o posterior de .NET Standard modificando el valor en el nodo `TargetFramework` de su archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="975d8-137">You can use a lower or higher version of the .NET Standard by modifying the value in the `TargetFramework` node of your project file.</span></span>

    <span data-ttu-id="975d8-138">Las versiones del estándar .NET son compatibles con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="975d8-138">.NET Standard versions are backward compatible.</span></span> <span data-ttu-id="975d8-139">Eso significa que las bibliotecas `netstandard1.0` se pueden ejecutar en plataformas `netstandard1.1` y versiones superiores.</span><span class="sxs-lookup"><span data-stu-id="975d8-139">That means that `netstandard1.0` libraries run on `netstandard1.1` platforms and higher.</span></span> <span data-ttu-id="975d8-140">Sin embargo, no existe compatibilidad con versiones posteriores: las plataformas del estándar .NET inferiores no pueden hacer referencia a las superiores.</span><span class="sxs-lookup"><span data-stu-id="975d8-140">However, there is no forward compatibility - lower .NET Standard platforms cannot reference higher ones.</span></span> <span data-ttu-id="975d8-141">Esto significa que las bibliotecas `netstandard1.0` no pueden hacer referencia a las bibliotecas que tienen como destino `netstandard1.1` o una versión superior.</span><span class="sxs-lookup"><span data-stu-id="975d8-141">This means that `netstandard1.0` libraries cannot reference libraries targeting `netstandard1.1` or higher.</span></span> <span data-ttu-id="975d8-142">Seleccione la versión estándar que tiene la combinación adecuada de compatibilidad con API y plataformas que necesita.</span><span class="sxs-lookup"><span data-stu-id="975d8-142">Select the Standard version that has the right mix of APIs and platform support for your needs.</span></span> <span data-ttu-id="975d8-143">Por ahora le recomendamos `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="975d8-143">We recommend `netstandard1.4` for now.</span></span>

3. <span data-ttu-id="975d8-144">Si desea tener como destino .NET Framework versión 4.0 o inferior, o bien desea usar una API disponible en .NET Framework pero no disponible en el estándar .NET (por ejemplo, `System.Drawing`), lea las secciones siguientes y sepa cómo tener compatibilidad con múltiples versiones.</span><span class="sxs-lookup"><span data-stu-id="975d8-144">If you want to target the .NET Framework versions 4.0 or below, or you wish to use an API available in the .NET Framework but not in the .NET Standard (for example, `System.Drawing`), read the following sections and learn how to multitarget.</span></span>

## <a name="how-to-target-the-net-framework"></a><span data-ttu-id="975d8-145">.NET Framework como destino</span><span class="sxs-lookup"><span data-stu-id="975d8-145">How to target the .NET Framework</span></span>

> [!NOTE]
> <span data-ttu-id="975d8-146">Estas instrucciones suponen que tiene instalado .NET Framework en su máquina.</span><span class="sxs-lookup"><span data-stu-id="975d8-146">These instructions assume you have the .NET Framework installed on your machine.</span></span> <span data-ttu-id="975d8-147">Consulte los [requisitos previos](#prerequisites) para instalar las dependencias.</span><span class="sxs-lookup"><span data-stu-id="975d8-147">Refer to the [Prerequisites](#prerequisites) to get dependencies installed.</span></span>

<span data-ttu-id="975d8-148">Tenga en cuenta que algunas de las versiones de .NET Framework que se usan aquí ya no cuentan con soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="975d8-148">Keep in mind that some of the .NET Framework versions used here are no longer in support.</span></span> <span data-ttu-id="975d8-149">Consulte las [P+F sobre la directiva del ciclo de vida de soporte técnico de .NET Framework](https://support.microsoft.com/gp/framework_faq/en-us) sobre las versiones sin soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="975d8-149">Refer to the [.NET Framework Support Lifecycle Policy FAQ](https://support.microsoft.com/gp/framework_faq/en-us) about unsupported versions.</span></span>

<span data-ttu-id="975d8-150">Si quiere llegar a la mayor cantidad posible de desarrolladores y proyectos, use .NET Framework 4.0 como el destino de línea base.</span><span class="sxs-lookup"><span data-stu-id="975d8-150">If you want to reach the maximum number of developers and projects, use the .NET Framework 4.0 as your baseline target.</span></span> <span data-ttu-id="975d8-151">Para tener .NET Framework como destino, deberá comenzar por el uso del moniker de la plataforma de destino (TFM) correcto que corresponda a la versión de .NET Framework que desea admitir.</span><span class="sxs-lookup"><span data-stu-id="975d8-151">To target the .NET Framework, you will need to begin by using the correct Target Framework Moniker (TFM) that corresponds to the .NET Framework version you wish to support.</span></span>

| <span data-ttu-id="975d8-152">Versión de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="975d8-152">.NET Framework version</span></span> | <span data-ttu-id="975d8-153">TFM</span><span class="sxs-lookup"><span data-stu-id="975d8-153">TFM</span></span>      |
| ---------------------- | -------- |
| <span data-ttu-id="975d8-154">.NET Framework 2.0</span><span class="sxs-lookup"><span data-stu-id="975d8-154">.NET Framework 2.0</span></span>     | `net20`  |
| <span data-ttu-id="975d8-155">.NET Framework 3.0</span><span class="sxs-lookup"><span data-stu-id="975d8-155">.NET Framework 3.0</span></span>     | `net30`  |
| <span data-ttu-id="975d8-156">.NET Framework 3,5</span><span class="sxs-lookup"><span data-stu-id="975d8-156">.NET Framework 3.5</span></span>     | `net35`  |
| <span data-ttu-id="975d8-157">.NET Framework 4.0</span><span class="sxs-lookup"><span data-stu-id="975d8-157">.NET Framework 4.0</span></span>     | `net40`  |
| <span data-ttu-id="975d8-158">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="975d8-158">.NET Framework 4.5</span></span>     | `net45`  |
| <span data-ttu-id="975d8-159">.NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="975d8-159">.NET Framework 4.5.1</span></span>   | `net451` |
| <span data-ttu-id="975d8-160">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="975d8-160">.NET Framework 4.5.2</span></span>   | `net452` |
| <span data-ttu-id="975d8-161">.NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="975d8-161">.NET Framework 4.6</span></span>     | `net46`  |
| <span data-ttu-id="975d8-162">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="975d8-162">.NET Framework 4.6.1</span></span>   | `net461` |
| <span data-ttu-id="975d8-163">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="975d8-163">.NET Framework 4.6.2</span></span>   | `net462` |
| <span data-ttu-id="975d8-164">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="975d8-164">.NET Framework 4.7</span></span>     | `net47`  |
| <span data-ttu-id="975d8-165">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="975d8-165">.NET Framework 4.8</span></span>     | `net48`  |

<span data-ttu-id="975d8-166">Después, inserte el TFM en la sección `TargetFramework` de su archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="975d8-166">You then insert this TFM into the `TargetFramework` section of your project file.</span></span> <span data-ttu-id="975d8-167">El siguiente es un ejemplo de cómo podría escribir una biblioteca que tenga como destino la versión .NET Framework 4.0:</span><span class="sxs-lookup"><span data-stu-id="975d8-167">For example, here's how you would write a library which targets the .NET Framework 4.0:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>net40</TargetFramework>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="975d8-168">Y listo.</span><span class="sxs-lookup"><span data-stu-id="975d8-168">And that's it!</span></span> <span data-ttu-id="975d8-169">Aunque esto solo hace la compilación para .NET Framework 4, puede usar la biblioteca en las versiones más recientes de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="975d8-169">Although this compiled only for the .NET Framework 4, you can use the library on newer versions of the .NET Framework.</span></span>

## <a name="how-to-multitarget"></a><span data-ttu-id="975d8-170">Cómo lograr la compatibilidad con múltiples versiones</span><span class="sxs-lookup"><span data-stu-id="975d8-170">How to Multitarget</span></span>

> [!NOTE]
> <span data-ttu-id="975d8-171">Las instrucciones siguientes suponen que tiene instalado .NET Framework en su máquina.</span><span class="sxs-lookup"><span data-stu-id="975d8-171">The following instructions assume you have the .NET Framework installed on your machine.</span></span> <span data-ttu-id="975d8-172">Consulte la sección de [requisitos previos](#prerequisites) para información sobre las dependencias que debe instalar y dónde descargarlas.</span><span class="sxs-lookup"><span data-stu-id="975d8-172">Refer to the [Prerequisites](#prerequisites) section to learn which dependencies you need to install and where to download them from.</span></span>

<span data-ttu-id="975d8-173">Es posible que deba tener como destino versiones anteriores de .NET Framework cuando el proyecto admite .NET Framework y .NET Core.</span><span class="sxs-lookup"><span data-stu-id="975d8-173">You may need to target older versions of the .NET Framework when your project supports both the .NET Framework and .NET Core.</span></span> <span data-ttu-id="975d8-174">En este escenario, si desea usar API más recientes y construcciones de lenguaje para los destinos más recientes, use las directivas `#if` en el código.</span><span class="sxs-lookup"><span data-stu-id="975d8-174">In this scenario, if you want to use newer APIs and language constructs for the newer targets, use `#if` directives in your code.</span></span> <span data-ttu-id="975d8-175">También es posible que tenga que agregar distintos paquetes y dependencias para cada plataforma que tiene como destino para incluir las distintas API necesarias para cada caso.</span><span class="sxs-lookup"><span data-stu-id="975d8-175">You also might need to add different packages and dependencies for each platform you're targeting to include the different APIs needed for each case.</span></span>

<span data-ttu-id="975d8-176">Por ejemplo, digamos que tiene una biblioteca que realiza operaciones de red a través de HTTP.</span><span class="sxs-lookup"><span data-stu-id="975d8-176">For example, let's say you have a library that performs networking operations over HTTP.</span></span> <span data-ttu-id="975d8-177">En el estándar .NET y .NET Framework versión 4.5 o superiores, puede usar la clase `HttpClient` del espacio de nombres `System.Net.Http`.</span><span class="sxs-lookup"><span data-stu-id="975d8-177">For .NET Standard and the .NET Framework versions 4.5 or higher, you can use the `HttpClient` class from the `System.Net.Http` namespace.</span></span> <span data-ttu-id="975d8-178">Sin embargo, las versiones anteriores de .NET Framework no tienen la clase `HttpClient`, por lo que, en su lugar, podría usar la clase `WebClient` del espacio de nombres `System.Net` para esas versiones.</span><span class="sxs-lookup"><span data-stu-id="975d8-178">However, earlier versions of the .NET Framework don't have the `HttpClient` class, so you could use the `WebClient` class from the `System.Net` namespace for those instead.</span></span>

<span data-ttu-id="975d8-179">Su archivo del proyecto podría tener la siguiente apariencia:</span><span class="sxs-lookup"><span data-stu-id="975d8-179">Your project file could look like this:</span></span>

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

<span data-ttu-id="975d8-180">Observará tres cambios principales aquí:</span><span class="sxs-lookup"><span data-stu-id="975d8-180">You'll notice three major changes here:</span></span>

1. <span data-ttu-id="975d8-181">El nodo `TargetFramework` se ha reemplazado por `TargetFrameworks`, y se expresan tres TFM dentro.</span><span class="sxs-lookup"><span data-stu-id="975d8-181">The `TargetFramework` node has been replaced by `TargetFrameworks`, and three TFMs are expressed inside.</span></span>
1. <span data-ttu-id="975d8-182">Existe un nodo `<ItemGroup>` para el destino `net40` que se dirige a una referencia de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="975d8-182">There is an `<ItemGroup>` node for the `net40` target pulling in one .NET Framework reference.</span></span>
1. <span data-ttu-id="975d8-183">Existe un nodo `<ItemGroup>` para el destino `net45` que se dirige a dos referencias de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="975d8-183">There is an `<ItemGroup>` node for the `net45` target pulling in two .NET Framework references.</span></span>

<span data-ttu-id="975d8-184">El sistema de compilación conoce los siguientes símbolos del preprocesador que se usan en las directivas `#if`:</span><span class="sxs-lookup"><span data-stu-id="975d8-184">The build system is aware of the following preprocessor symbols used in `#if` directives:</span></span>

[!INCLUDE [Preprocessor symbols](../../../includes/preprocessor-symbols.md)]

<span data-ttu-id="975d8-185">Aquí se muestra un ejemplo en el que se usa la compilación condicional por destino:</span><span class="sxs-lookup"><span data-stu-id="975d8-185">Here is an example making use of conditional compilation per-target:</span></span>

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
        // .NET 4.5+ can use async/await!
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

<span data-ttu-id="975d8-186">Si crea este proyecto con `dotnet build`, observará tres directorios en la carpeta `bin/`:</span><span class="sxs-lookup"><span data-stu-id="975d8-186">If you build this project with `dotnet build`, you'll notice three directories under the `bin/` folder:</span></span>

```
net40/
net45/
netstandard1.4/
```

<span data-ttu-id="975d8-187">Cada uno de ellos contiene los archivos `.dll` para cada destino.</span><span class="sxs-lookup"><span data-stu-id="975d8-187">Each of these contain the `.dll` files for each target.</span></span>

## <a name="how-to-test-libraries-on-net-core"></a><span data-ttu-id="975d8-188">Prueba de las bibliotecas en .NET Core</span><span class="sxs-lookup"><span data-stu-id="975d8-188">How to test libraries on .NET Core</span></span>

<span data-ttu-id="975d8-189">Es importante poder probar las plataformas.</span><span class="sxs-lookup"><span data-stu-id="975d8-189">It's important to be able to test across platforms.</span></span> <span data-ttu-id="975d8-190">Puede usar [xUnit](https://xunit.github.io/) o MSTest de fábrica.</span><span class="sxs-lookup"><span data-stu-id="975d8-190">You can use either [xUnit](https://xunit.github.io/) or MSTest out of the box.</span></span> <span data-ttu-id="975d8-191">Ambos son perfectamente adecuados para las pruebas unitarias de su biblioteca en .NET Core.</span><span class="sxs-lookup"><span data-stu-id="975d8-191">Both are perfectly suitable for unit testing your library on .NET Core.</span></span> <span data-ttu-id="975d8-192">Cómo configurar la solución con proyectos de prueba dependerá de la [estructura de la solución](#structuring-a-solution).</span><span class="sxs-lookup"><span data-stu-id="975d8-192">How you set up your solution with test projects will depend on the [structure of your solution](#structuring-a-solution).</span></span> <span data-ttu-id="975d8-193">En el ejemplo siguiente se presupone que los directorios de origen y de prueba residen en el mismo directorio de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="975d8-193">The following example assumes that the test and source directories live in the same top-level directory.</span></span>

> [!NOTE]
> <span data-ttu-id="975d8-194">Esto usa algunos [comandos de la CLI de .NET Core](../tools/index.md).</span><span class="sxs-lookup"><span data-stu-id="975d8-194">This uses some [.NET Core CLI commands](../tools/index.md).</span></span> <span data-ttu-id="975d8-195">Vea [dotnet new](../tools/dotnet-new.md) y [dotnet sln](../tools/dotnet-sln.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="975d8-195">See [dotnet new](../tools/dotnet-new.md) and [dotnet sln](../tools/dotnet-sln.md) for more information.</span></span>

1. <span data-ttu-id="975d8-196">Configure la solución.</span><span class="sxs-lookup"><span data-stu-id="975d8-196">Set up your solution.</span></span> <span data-ttu-id="975d8-197">Puede hacerlo con los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="975d8-197">You can do so with the following commands:</span></span>

   ```bash
   mkdir SolutionWithSrcAndTest
   cd SolutionWithSrcAndTest
   dotnet new sln
   dotnet new classlib -o MyProject
   dotnet new xunit -o MyProject.Test
   dotnet sln add MyProject/MyProject.csproj
   dotnet sln add MyProject.Test/MyProject.Test.csproj
   ```

   <span data-ttu-id="975d8-198">Esto creará proyectos y se vincularán conjuntamente en una solución.</span><span class="sxs-lookup"><span data-stu-id="975d8-198">This will create projects and link them together in a solution.</span></span> <span data-ttu-id="975d8-199">Su directorio para `SolutionWithSrcAndTest` debe tener el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="975d8-199">Your directory for `SolutionWithSrcAndTest` should look like this:</span></span>

   ```
   /SolutionWithSrcAndTest
   |__SolutionWithSrcAndTest.sln
   |__MyProject/
   |__MyProject.Test/
   ```

1. <span data-ttu-id="975d8-200">Vaya al directorio del proyecto de prueba y agregue una referencia a `MyProject.Test` desde `MyProject`.</span><span class="sxs-lookup"><span data-stu-id="975d8-200">Navigate to the test project's directory and add a reference to `MyProject.Test` from `MyProject`.</span></span>

   ```bash
   cd MyProject.Test
   dotnet add reference ../MyProject/MyProject.csproj
   ```

1. <span data-ttu-id="975d8-201">Restaurar paquetes y crear proyectos:</span><span class="sxs-lookup"><span data-stu-id="975d8-201">Restore packages and build projects:</span></span>

   ```dotnetcli
   dotnet restore
   dotnet build
   ```

   [!INCLUDE[DotNet Restore Note](../../../includes/dotnet-restore-note.md)]

1. <span data-ttu-id="975d8-202">Compruebe que xUnit se ejecuta mediante la ejecución del comando `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="975d8-202">Verify that xUnit runs by executing the `dotnet test` command.</span></span> <span data-ttu-id="975d8-203">Si decide usar MSTest, entonces debe ejecutarse en su lugar el ejecutor de la consola de MSTest.</span><span class="sxs-lookup"><span data-stu-id="975d8-203">If you chose to use MSTest, then the MSTest console runner should run instead.</span></span>

<span data-ttu-id="975d8-204">Y listo.</span><span class="sxs-lookup"><span data-stu-id="975d8-204">And that's it!</span></span> <span data-ttu-id="975d8-205">Ahora puede probar la biblioteca en todas las plataformas; para ello, use herramientas de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="975d8-205">You can now test your library across all platforms using command line tools.</span></span> <span data-ttu-id="975d8-206">Para seguir con las pruebas ahora que ya está todo configurado, probar la biblioteca es un proceso muy simple:</span><span class="sxs-lookup"><span data-stu-id="975d8-206">To continue testing now that you have everything set up, testing your library is very simple:</span></span>

1. <span data-ttu-id="975d8-207">Haga los cambios en la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="975d8-207">Make changes to your library.</span></span>
1. <span data-ttu-id="975d8-208">Ejecute las pruebas desde la línea de comandos, en el directorio de prueba, con el comando `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="975d8-208">Run tests from the command line, in your test directory, with `dotnet test` command.</span></span>

<span data-ttu-id="975d8-209">El código se recompilará automáticamente cuando invoque el comando `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="975d8-209">Your code will be automatically rebuilt when you invoke `dotnet test` command.</span></span>

## <a name="how-to-use-multiple-projects"></a><span data-ttu-id="975d8-210">Uso de varios proyectos</span><span class="sxs-lookup"><span data-stu-id="975d8-210">How to use multiple projects</span></span>

<span data-ttu-id="975d8-211">Una necesidad en común de las bibliotecas de mayor tamaño es ubicar la funcionalidad en distintos proyectos.</span><span class="sxs-lookup"><span data-stu-id="975d8-211">A common need for larger libraries is to place functionality in different projects.</span></span>

<span data-ttu-id="975d8-212">Imagine que desea compilar una biblioteca que se pudiera consumir en C# y F# idiomático.</span><span class="sxs-lookup"><span data-stu-id="975d8-212">Imagine you wished to build a library which could be consumed in idiomatic C# and F#.</span></span> <span data-ttu-id="975d8-213">Eso significaría que los usuarios de las bibliotecas las consumirían de manera natural para C# o F#.</span><span class="sxs-lookup"><span data-stu-id="975d8-213">That would mean that consumers of your library consume them in ways which are natural to C# or F#.</span></span> <span data-ttu-id="975d8-214">Por ejemplo, en C#, podría consumir la biblioteca de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="975d8-214">For example, in C# you might consume the library like this:</span></span>

```csharp
using AwesomeLibrary.CSharp;

public Task DoThings(Data data)
{
    var convertResult = await AwesomeLibrary.ConvertAsync(data);
    var result = AwesomeLibrary.Process(convertResult);
    // do something with result
}
```

<span data-ttu-id="975d8-215">En F#, sería de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="975d8-215">In F#, it might look like this:</span></span>

```fsharp
open AwesomeLibrary.FSharp

let doWork data = async {
    let! result = AwesomeLibrary.AsyncConvert data // Uses an F# async function rather than C# async method
    // do something with result
}
```

<span data-ttu-id="975d8-216">Escenarios de consumo similares a este significan que las API a las que se tiene acceso deben tener una estructura distinta para C# y para F#.</span><span class="sxs-lookup"><span data-stu-id="975d8-216">Consumption scenarios like this mean that the APIs being accessed have to have a different structure for C# and F#.</span></span>  <span data-ttu-id="975d8-217">Un enfoque común para lograrlo es factorizar toda la lógica de una biblioteca en un proyecto central, con los proyectos de C# y F# definiendo los niveles de API que hacen llamadas a ese proyecto central.</span><span class="sxs-lookup"><span data-stu-id="975d8-217">A common approach to accomplishing this is to factor all of the logic of a library into a core project, with C# and F# projects defining the API layers that call into that core project.</span></span>  <span data-ttu-id="975d8-218">En el resto de la sección se usarán los siguientes nombres:</span><span class="sxs-lookup"><span data-stu-id="975d8-218">The rest of the section will use the following names:</span></span>

* <span data-ttu-id="975d8-219">**AwesomeLibrary.Core**: un proyecto central que contiene toda la lógica de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="975d8-219">**AwesomeLibrary.Core** - A core project which contains all logic for the library</span></span>
* <span data-ttu-id="975d8-220">**AwesomeLibrary.CSharp**: un proyecto con API públicas pensado para el consumo en C#</span><span class="sxs-lookup"><span data-stu-id="975d8-220">**AwesomeLibrary.CSharp** - A project with public APIs intended for consumption in C#</span></span>
* <span data-ttu-id="975d8-221">**AwesomeLibrary.FSharp**: un proyecto con API públicas pensado para el consumo en F#</span><span class="sxs-lookup"><span data-stu-id="975d8-221">**AwesomeLibrary.FSharp** - A project with public APIs intended for consumption in F#</span></span>

<span data-ttu-id="975d8-222">Puede ejecutar los siguientes comandos en su terminal para generar la misma estructura de esta guía:</span><span class="sxs-lookup"><span data-stu-id="975d8-222">You can run the following commands in your terminal to produce the same structure as this guide:</span></span>

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

<span data-ttu-id="975d8-223">Esto agregará los tres proyectos anteriores y un archivo de solución que los vincula conjuntamente.</span><span class="sxs-lookup"><span data-stu-id="975d8-223">This will add the three projects above and a solution file which links them together.</span></span> <span data-ttu-id="975d8-224">Crear el archivo de solución y vincular los proyectos le permitirá restaurar y crear proyectos desde un nivel superior.</span><span class="sxs-lookup"><span data-stu-id="975d8-224">Creating the solution file and linking projects will allow you to restore and build projects from a top-level.</span></span>

### <a name="project-to-project-referencing"></a><span data-ttu-id="975d8-225">Referencias entre proyectos</span><span class="sxs-lookup"><span data-stu-id="975d8-225">Project-to-project referencing</span></span>

<span data-ttu-id="975d8-226">La mejor manera de hacer referencia a un proyecto es usar la CLI de .NET Core para agregar una referencia de proyecto.</span><span class="sxs-lookup"><span data-stu-id="975d8-226">The best way to reference a project is to use the .NET Core CLI to add a project reference.</span></span> <span data-ttu-id="975d8-227">Desde los directorios del proyecto **AwesomeLibrary.CSharp** y **AwesomeLibrary.FSharp**, puede ejecutar el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="975d8-227">From the **AwesomeLibrary.CSharp** and **AwesomeLibrary.FSharp** project directories, you can run the following command:</span></span>

```dotnetcli
dotnet add reference ../AwesomeLibrary.Core/AwesomeLibrary.Core.csproj
```

<span data-ttu-id="975d8-228">Los archivos del proyecto para **AwesomeLibrary.CSharp** y **AwesomeLibrary.FSharp** ahora harán referencia a **AwesomeLibrary.Core** como un destino `ProjectReference`.</span><span class="sxs-lookup"><span data-stu-id="975d8-228">The project files for both **AwesomeLibrary.CSharp** and **AwesomeLibrary.FSharp** will now reference **AwesomeLibrary.Core** as a `ProjectReference` target.</span></span>  <span data-ttu-id="975d8-229">Puede comprobar esto inspeccionando los archivos del proyecto y observando lo siguiente en ellos:</span><span class="sxs-lookup"><span data-stu-id="975d8-229">You can verify this by inspecting the project files and seeing the following in them:</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\AwesomeLibrary.Core\AwesomeLibrary.Core.csproj" />
</ItemGroup>
```

<span data-ttu-id="975d8-230">Puede agregar esta sección a cada archivo del proyecto manualmente si prefiere no usar la CLI de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="975d8-230">You can add this section to each project file manually if you prefer not to use the .NET Core CLI.</span></span>

### <a name="structuring-a-solution"></a><span data-ttu-id="975d8-231">Estructura de una solución</span><span class="sxs-lookup"><span data-stu-id="975d8-231">Structuring a solution</span></span>

<span data-ttu-id="975d8-232">Otro aspecto importante de las soluciones de varios proyectos es establecer una buena estructura de proyecto general.</span><span class="sxs-lookup"><span data-stu-id="975d8-232">Another important aspect of multi-project solutions is establishing a good overall project structure.</span></span> <span data-ttu-id="975d8-233">Puede organizar el código de la manera que quiera, y siempre y cuando vincule cada proyecto a su archivo de solución con `dotnet sln add`, podrá ejecutar `dotnet restore` y `dotnet build` en el nivel de solución.</span><span class="sxs-lookup"><span data-stu-id="975d8-233">You can organize code however you like, and as long as you link each project to your solution file with `dotnet sln add`, you will be able to run `dotnet restore` and `dotnet build` at the solution level.</span></span>
