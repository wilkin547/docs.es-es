---
title: Desarrollo de bibliotecas con la CLI de .NET Core
description: Aprenda a crear bibliotecas de .NET Core con la CLI de .NET Core. Creará una biblioteca que admite varios marcos de trabajo.
author: cartermp
ms.topic: how-to
ms.date: 05/01/2017
ms.openlocfilehash: e98ce9e08c8d92bb4c89348e21cece60de811848
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2020
ms.locfileid: "92223702"
---
# <a name="develop-libraries-with-the-net-core-cli"></a><span data-ttu-id="f91b3-104">Desarrollo de bibliotecas con la CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="f91b3-104">Develop libraries with the .NET Core CLI</span></span>

<span data-ttu-id="f91b3-105">En este artículo se explica cómo escribir bibliotecas para .NET con la CLI de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f91b3-105">This article covers how to write libraries for .NET using the .NET Core CLI.</span></span> <span data-ttu-id="f91b3-106">La CLI proporciona una experiencia eficaz y de bajo nivel que funciona en todos los SO compatibles.</span><span class="sxs-lookup"><span data-stu-id="f91b3-106">The CLI provides an efficient and low-level experience that works across any supported OS.</span></span> <span data-ttu-id="f91b3-107">De todos modos puede seguir compilando bibliotecas con Visual Studio; si esa es la experiencia de su preferencia, [consulte la guía sobre Visual Studio](library-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="f91b3-107">You can still build libraries with Visual Studio, and if that is your preferred experience [refer to the Visual Studio guide](library-with-visual-studio.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f91b3-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f91b3-108">Prerequisites</span></span>

<span data-ttu-id="f91b3-109">Necesita [la CLI y el SDK de .NET Core](https://dotnet.microsoft.com/download) que están instalados en la máquina.</span><span class="sxs-lookup"><span data-stu-id="f91b3-109">You need [the .NET Core SDK and CLI](https://dotnet.microsoft.com/download) installed on your machine.</span></span>

<span data-ttu-id="f91b3-110">En las secciones de este documento que se refieren a las versiones de .NET Framework, necesita tener instalado [.NET Framework](https://dotnet.microsoft.com) en una máquina con Windows.</span><span class="sxs-lookup"><span data-stu-id="f91b3-110">For the sections of this document dealing with .NET Framework versions, you need the [.NET Framework](https://dotnet.microsoft.com) installed on a Windows machine.</span></span>

<span data-ttu-id="f91b3-111">Además, si desea admitir destinos de .NET Framework anteriores, deberá instalar paquetes de destino o desarrollador desde la [página de archivos de descarga de .NET](https://dotnet.microsoft.com/download/archives).</span><span class="sxs-lookup"><span data-stu-id="f91b3-111">Additionally, if you wish to support older .NET Framework targets, you need to install targeting packs or developer packs from the [.NET download archives page](https://dotnet.microsoft.com/download/archives).</span></span> <span data-ttu-id="f91b3-112">Consulte la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="f91b3-112">Refer to this table:</span></span>

| <span data-ttu-id="f91b3-113">Versión de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f91b3-113">.NET Framework version</span></span> | <span data-ttu-id="f91b3-114">Qué debe descargar</span><span class="sxs-lookup"><span data-stu-id="f91b3-114">What to download</span></span>                                       |
| ---------------------- | ------------------------------------------------------ |
| <span data-ttu-id="f91b3-115">4.6.1</span><span class="sxs-lookup"><span data-stu-id="f91b3-115">4.6.1</span></span>                  | <span data-ttu-id="f91b3-116">Paquete de compatibilidad de .NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="f91b3-116">.NET Framework 4.6.1 Targeting Pack</span></span>                    |
| <span data-ttu-id="f91b3-117">4.6</span><span class="sxs-lookup"><span data-stu-id="f91b3-117">4.6</span></span>                    | <span data-ttu-id="f91b3-118">Paquete de compatibilidad de .NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="f91b3-118">.NET Framework 4.6 Targeting Pack</span></span>                      |
| <span data-ttu-id="f91b3-119">4.5.2</span><span class="sxs-lookup"><span data-stu-id="f91b3-119">4.5.2</span></span>                  | <span data-ttu-id="f91b3-120">Paquete de desarrollador de .NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="f91b3-120">.NET Framework 4.5.2 Developer Pack</span></span>                    |
| <span data-ttu-id="f91b3-121">4.5.1</span><span class="sxs-lookup"><span data-stu-id="f91b3-121">4.5.1</span></span>                  | <span data-ttu-id="f91b3-122">Paquete de desarrollador de .NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="f91b3-122">.NET Framework 4.5.1 Developer Pack</span></span>                    |
| <span data-ttu-id="f91b3-123">4.5</span><span class="sxs-lookup"><span data-stu-id="f91b3-123">4.5</span></span>                    | <span data-ttu-id="f91b3-124">Kit de desarrollo de software de Windows para Windows 8</span><span class="sxs-lookup"><span data-stu-id="f91b3-124">Windows Software Development Kit for Windows 8</span></span>         |
| <span data-ttu-id="f91b3-125">4.0</span><span class="sxs-lookup"><span data-stu-id="f91b3-125">4.0</span></span>                    | <span data-ttu-id="f91b3-126">Windows SDK para Windows 7 y .NET Framework 4</span><span class="sxs-lookup"><span data-stu-id="f91b3-126">Windows SDK for Windows 7 and .NET Framework 4</span></span>         |
| <span data-ttu-id="f91b3-127">2.0, 3.0 y 3.5</span><span class="sxs-lookup"><span data-stu-id="f91b3-127">2.0, 3.0, and 3.5</span></span>      | <span data-ttu-id="f91b3-128">Entorno de ejecución de .NET Framework 3.5 SP1 (o una versión posterior a Windows 8)</span><span class="sxs-lookup"><span data-stu-id="f91b3-128">.NET Framework 3.5 SP1 Runtime (or Windows 8+ version)</span></span> |

## <a name="how-to-target-net-standard"></a><span data-ttu-id="f91b3-129">Establecimiento de .NET Standard como destino</span><span class="sxs-lookup"><span data-stu-id="f91b3-129">How to target .NET Standard</span></span>

<span data-ttu-id="f91b3-130">Si no conoce .NET Standard, consulte el tema [.NET Standard](../../standard/net-standard.md) para más información.</span><span class="sxs-lookup"><span data-stu-id="f91b3-130">If you're not familiar with .NET Standard, refer to [.NET Standard](../../standard/net-standard.md) to learn more.</span></span>

<span data-ttu-id="f91b3-131">En ese artículo podrá ver una tabla que asigna las versiones de .NET Standard a diversas implementaciones:</span><span class="sxs-lookup"><span data-stu-id="f91b3-131">In that article, there is a table that maps .NET Standard versions to various implementations:</span></span>

[!INCLUDE [net-standard-table](../../../includes/net-standard-table.md)]

<span data-ttu-id="f91b3-132">Este es el significado de la tabla para crear una biblioteca:</span><span class="sxs-lookup"><span data-stu-id="f91b3-132">Here's what this table means for the purposes of creating a library:</span></span>

<span data-ttu-id="f91b3-133">La versión de .NET Standard que elija será un equilibrio entre el acceso a las API más recientes y la capacidad de apuntar a más implementaciones .NET y más versiones de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="f91b3-133">The version of .NET Standard you pick will be a tradeoff between access to the newest APIs and the ability to target more .NET implementations and .NET Standard versions.</span></span> <span data-ttu-id="f91b3-134">Puede controlar el intervalo de versiones y plataformas de destino si elige una versión de `netstandardX.X` (donde `X.X` es un número de versión) y la agrega al archivo del proyecto (`.csproj` o `.fsproj`).</span><span class="sxs-lookup"><span data-stu-id="f91b3-134">You control the range of targetable platforms and versions by picking a version of `netstandardX.X` (where `X.X` is a version number) and adding it to your project file (`.csproj` or `.fsproj`).</span></span>

<span data-ttu-id="f91b3-135">En función de sus necesidades, tiene tres opciones principales cuando el destino es .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="f91b3-135">You have three primary options when targeting .NET Standard, depending on your needs.</span></span>

1. <span data-ttu-id="f91b3-136">Puede usar la versión predeterminada de .NET Standard que se proporciona con plantillas, `netstandard1.4`, que le permite acceder a la mayoría de API en .NET Standard mientras sigue siendo compatible con UWP, .NET Framework 4.6.1 y .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="f91b3-136">You can use the default version of .NET Standard supplied by templates, `netstandard1.4`, which gives you access to most APIs on .NET Standard while still being compatible with UWP, .NET Framework 4.6.1, and .NET Standard 2.0.</span></span>

    ```xml
    <Project Sdk="Microsoft.NET.Sdk">
      <PropertyGroup>
        <TargetFramework>netstandard1.4</TargetFramework>
      </PropertyGroup>
    </Project>
    ```

2. <span data-ttu-id="f91b3-137">Puede usar una versión anterior o posterior de .NET Standard modificando el valor en el nodo `TargetFramework` de su archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="f91b3-137">You can use a lower or higher version of .NET Standard by modifying the value in the `TargetFramework` node of your project file.</span></span>

    <span data-ttu-id="f91b3-138">Las versiones del estándar .NET son compatibles con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="f91b3-138">.NET Standard versions are backward compatible.</span></span> <span data-ttu-id="f91b3-139">Eso significa que las bibliotecas `netstandard1.0` se pueden ejecutar en plataformas `netstandard1.1` y versiones superiores.</span><span class="sxs-lookup"><span data-stu-id="f91b3-139">That means that `netstandard1.0` libraries run on `netstandard1.1` platforms and higher.</span></span> <span data-ttu-id="f91b3-140">Sin embargo, no hay compatibilidad con versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="f91b3-140">However, there is no forward compatibility.</span></span> <span data-ttu-id="f91b3-141">Las plataformas de .NET Standard anteriores no pueden hacer referencia a las posteriores.</span><span class="sxs-lookup"><span data-stu-id="f91b3-141">Lower .NET Standard platforms cannot reference higher ones.</span></span> <span data-ttu-id="f91b3-142">Esto significa que las bibliotecas `netstandard1.0` no pueden hacer referencia a las bibliotecas que tienen como destino `netstandard1.1` o una versión superior.</span><span class="sxs-lookup"><span data-stu-id="f91b3-142">This means that `netstandard1.0` libraries cannot reference libraries targeting `netstandard1.1` or higher.</span></span> <span data-ttu-id="f91b3-143">Seleccione la versión estándar que tiene la combinación adecuada de compatibilidad con API y plataformas que necesita.</span><span class="sxs-lookup"><span data-stu-id="f91b3-143">Select the Standard version that has the right mix of APIs and platform support for your needs.</span></span> <span data-ttu-id="f91b3-144">Por ahora le recomendamos `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="f91b3-144">We recommend `netstandard1.4` for now.</span></span>

3. <span data-ttu-id="f91b3-145">Si desea tener como destino .NET Framework versión 4.0 o inferior, o bien desea usar una API disponible en .NET Framework pero no disponible en el estándar .NET (por ejemplo, `System.Drawing`), lea las secciones siguientes y sepa cómo tener compatibilidad con múltiples versiones.</span><span class="sxs-lookup"><span data-stu-id="f91b3-145">If you want to target .NET Framework versions 4.0 or below, or you wish to use an API available in .NET Framework but not in .NET Standard (for example, `System.Drawing`), read the following sections and learn how to multitarget.</span></span>

## <a name="how-to-target-net-framework"></a><span data-ttu-id="f91b3-146">Uso de .NET Framework como destino</span><span class="sxs-lookup"><span data-stu-id="f91b3-146">How to target .NET Framework</span></span>

> [!NOTE]
> <span data-ttu-id="f91b3-147">En estas instrucciones se supone que tiene instalado .NET Framework en su máquina.</span><span class="sxs-lookup"><span data-stu-id="f91b3-147">These instructions assume you have .NET Framework installed on your machine.</span></span> <span data-ttu-id="f91b3-148">Consulte los [requisitos previos](#prerequisites) para instalar las dependencias.</span><span class="sxs-lookup"><span data-stu-id="f91b3-148">Refer to the [Prerequisites](#prerequisites) to get dependencies installed.</span></span>

<span data-ttu-id="f91b3-149">Tenga en cuenta que algunas de las versiones de .NET Framework que se usan aquí ya no cuentan con soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="f91b3-149">Keep in mind that some of the .NET Framework versions used here are no longer supported.</span></span> <span data-ttu-id="f91b3-150">Consulte las [P+F sobre la directiva del ciclo de vida de soporte técnico de .NET Framework](https://support.microsoft.com/gp/framework_faq/en-us) sobre las versiones sin soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="f91b3-150">Refer to the [.NET Framework Support Lifecycle Policy FAQ](https://support.microsoft.com/gp/framework_faq/en-us) about unsupported versions.</span></span>

<span data-ttu-id="f91b3-151">Si quiere llegar a la mayor cantidad posible de desarrolladores y proyectos, use .NET Framework 4.0 como el destino de línea base.</span><span class="sxs-lookup"><span data-stu-id="f91b3-151">If you want to reach the maximum number of developers and projects, use .NET Framework 4.0 as your baseline target.</span></span> <span data-ttu-id="f91b3-152">Para tener .NET Framework como destino, comience utilizando el moniker de la plataforma de destino (TFM) correcto que corresponda a la versión de .NET Framework que desea admitir.</span><span class="sxs-lookup"><span data-stu-id="f91b3-152">To target .NET Framework, begin by using the correct Target Framework Moniker (TFM) that corresponds to the .NET Framework version you wish to support.</span></span>

| <span data-ttu-id="f91b3-153">Versión de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f91b3-153">.NET Framework version</span></span> | <span data-ttu-id="f91b3-154">TFM</span><span class="sxs-lookup"><span data-stu-id="f91b3-154">TFM</span></span>      |
| ---------------------- | -------- |
| <span data-ttu-id="f91b3-155">.NET Framework 2.0</span><span class="sxs-lookup"><span data-stu-id="f91b3-155">.NET Framework 2.0</span></span>     | `net20`  |
| <span data-ttu-id="f91b3-156">.NET Framework 3.0</span><span class="sxs-lookup"><span data-stu-id="f91b3-156">.NET Framework 3.0</span></span>     | `net30`  |
| <span data-ttu-id="f91b3-157">.NET Framework 3,5</span><span class="sxs-lookup"><span data-stu-id="f91b3-157">.NET Framework 3.5</span></span>     | `net35`  |
| <span data-ttu-id="f91b3-158">.NET Framework 4.0</span><span class="sxs-lookup"><span data-stu-id="f91b3-158">.NET Framework 4.0</span></span>     | `net40`  |
| <span data-ttu-id="f91b3-159">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="f91b3-159">.NET Framework 4.5</span></span>     | `net45`  |
| <span data-ttu-id="f91b3-160">.NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="f91b3-160">.NET Framework 4.5.1</span></span>   | `net451` |
| <span data-ttu-id="f91b3-161">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="f91b3-161">.NET Framework 4.5.2</span></span>   | `net452` |
| <span data-ttu-id="f91b3-162">.NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="f91b3-162">.NET Framework 4.6</span></span>     | `net46`  |
| <span data-ttu-id="f91b3-163">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="f91b3-163">.NET Framework 4.6.1</span></span>   | `net461` |
| <span data-ttu-id="f91b3-164">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="f91b3-164">.NET Framework 4.6.2</span></span>   | `net462` |
| <span data-ttu-id="f91b3-165">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="f91b3-165">.NET Framework 4.7</span></span>     | `net47`  |
| <span data-ttu-id="f91b3-166">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="f91b3-166">.NET Framework 4.8</span></span>     | `net48`  |

<span data-ttu-id="f91b3-167">Después, inserte el TFM en la sección `TargetFramework` de su archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="f91b3-167">You then insert this TFM into the `TargetFramework` section of your project file.</span></span> <span data-ttu-id="f91b3-168">El siguiente es un ejemplo de cómo podría escribir una biblioteca que tenga como destino .NET Framework 4.0:</span><span class="sxs-lookup"><span data-stu-id="f91b3-168">For example, here's how you would write a library that targets .NET Framework 4.0:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>net40</TargetFramework>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="f91b3-169">Y listo.</span><span class="sxs-lookup"><span data-stu-id="f91b3-169">And that's it!</span></span> <span data-ttu-id="f91b3-170">Aunque esto solo hace la compilación para .NET Framework 4, puede usar la biblioteca en las versiones más recientes de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f91b3-170">Although this compiled only for .NET Framework 4, you can use the library on newer versions of .NET Framework.</span></span>

## <a name="how-to-multitarget"></a><span data-ttu-id="f91b3-171">Cómo lograr la compatibilidad con varias versiones</span><span class="sxs-lookup"><span data-stu-id="f91b3-171">How to multitarget</span></span>

> [!NOTE]
> <span data-ttu-id="f91b3-172">Las instrucciones siguientes suponen que tiene instalado .NET Framework en su máquina.</span><span class="sxs-lookup"><span data-stu-id="f91b3-172">The following instructions assume you have the .NET Framework installed on your machine.</span></span> <span data-ttu-id="f91b3-173">Consulte la sección de [requisitos previos](#prerequisites) para información sobre las dependencias que debe instalar y dónde descargarlas.</span><span class="sxs-lookup"><span data-stu-id="f91b3-173">Refer to the [Prerequisites](#prerequisites) section to learn which dependencies you need to install and where to download them from.</span></span>

<span data-ttu-id="f91b3-174">Es posible que deba tener como destino versiones anteriores de .NET Framework cuando el proyecto admite .NET Framework y .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f91b3-174">You may need to target older versions of the .NET Framework when your project supports both the .NET Framework and .NET Core.</span></span> <span data-ttu-id="f91b3-175">En este escenario, si desea usar API más recientes y construcciones de lenguaje para los destinos más recientes, use las directivas `#if` en el código.</span><span class="sxs-lookup"><span data-stu-id="f91b3-175">In this scenario, if you want to use newer APIs and language constructs for the newer targets, use `#if` directives in your code.</span></span> <span data-ttu-id="f91b3-176">También es posible que tenga que agregar distintos paquetes y dependencias para cada plataforma que tiene como destino para incluir las distintas API necesarias para cada caso.</span><span class="sxs-lookup"><span data-stu-id="f91b3-176">You also might need to add different packages and dependencies for each platform you're targeting to include the different APIs needed for each case.</span></span>

<span data-ttu-id="f91b3-177">Por ejemplo, digamos que tiene una biblioteca que realiza operaciones de red a través de HTTP.</span><span class="sxs-lookup"><span data-stu-id="f91b3-177">For example, let's say you have a library that performs networking operations over HTTP.</span></span> <span data-ttu-id="f91b3-178">En el estándar .NET y .NET Framework versión 4.5 o superiores, puede usar la clase `HttpClient` del espacio de nombres `System.Net.Http`.</span><span class="sxs-lookup"><span data-stu-id="f91b3-178">For .NET Standard and the .NET Framework versions 4.5 or higher, you can use the `HttpClient` class from the `System.Net.Http` namespace.</span></span> <span data-ttu-id="f91b3-179">Sin embargo, las versiones anteriores de .NET Framework no tienen la clase `HttpClient`, por lo que, en su lugar, podría usar la clase `WebClient` del espacio de nombres `System.Net` para esas versiones.</span><span class="sxs-lookup"><span data-stu-id="f91b3-179">However, earlier versions of the .NET Framework don't have the `HttpClient` class, so you could use the `WebClient` class from the `System.Net` namespace for those instead.</span></span>

<span data-ttu-id="f91b3-180">Su archivo del proyecto podría tener la siguiente apariencia:</span><span class="sxs-lookup"><span data-stu-id="f91b3-180">Your project file could look like this:</span></span>

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

<span data-ttu-id="f91b3-181">Observará tres cambios principales aquí:</span><span class="sxs-lookup"><span data-stu-id="f91b3-181">You'll notice three major changes here:</span></span>

1. <span data-ttu-id="f91b3-182">El nodo `TargetFramework` se ha reemplazado por `TargetFrameworks`, y se expresan tres TFM dentro.</span><span class="sxs-lookup"><span data-stu-id="f91b3-182">The `TargetFramework` node has been replaced by `TargetFrameworks`, and three TFMs are expressed inside.</span></span>
1. <span data-ttu-id="f91b3-183">Existe un nodo `<ItemGroup>` para el destino `net40` que se dirige a una referencia de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f91b3-183">There is an `<ItemGroup>` node for the `net40` target pulling in one .NET Framework reference.</span></span>
1. <span data-ttu-id="f91b3-184">Existe un nodo `<ItemGroup>` para el destino `net45` que se dirige a dos referencias de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f91b3-184">There is an `<ItemGroup>` node for the `net45` target pulling in two .NET Framework references.</span></span>

<span data-ttu-id="f91b3-185">El sistema de compilación conoce los siguientes símbolos del preprocesador que se usan en las directivas `#if`:</span><span class="sxs-lookup"><span data-stu-id="f91b3-185">The build system is aware of the following preprocessor symbols used in `#if` directives:</span></span>

[!INCLUDE [Preprocessor symbols](../../../includes/preprocessor-symbols.md)]

<span data-ttu-id="f91b3-186">Aquí se muestra un ejemplo en el que se usa la compilación condicional por destino:</span><span class="sxs-lookup"><span data-stu-id="f91b3-186">Here is an example making use of conditional compilation per-target:</span></span>

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

<span data-ttu-id="f91b3-187">Si crea este proyecto con `dotnet build`, observará tres directorios en la carpeta `bin/`:</span><span class="sxs-lookup"><span data-stu-id="f91b3-187">If you build this project with `dotnet build`, you'll notice three directories under the `bin/` folder:</span></span>

```
net40/
net45/
netstandard1.4/
```

<span data-ttu-id="f91b3-188">Cada uno de ellos contiene los archivos `.dll` para cada destino.</span><span class="sxs-lookup"><span data-stu-id="f91b3-188">Each of these contain the `.dll` files for each target.</span></span>

## <a name="how-to-test-libraries-on-net-core"></a><span data-ttu-id="f91b3-189">Prueba de las bibliotecas en .NET Core</span><span class="sxs-lookup"><span data-stu-id="f91b3-189">How to test libraries on .NET Core</span></span>

<span data-ttu-id="f91b3-190">Es importante poder probar las plataformas.</span><span class="sxs-lookup"><span data-stu-id="f91b3-190">It's important to be able to test across platforms.</span></span> <span data-ttu-id="f91b3-191">Puede usar [xUnit](https://xunit.github.io/) o MSTest de fábrica.</span><span class="sxs-lookup"><span data-stu-id="f91b3-191">You can use either [xUnit](https://xunit.github.io/) or MSTest out of the box.</span></span> <span data-ttu-id="f91b3-192">Ambos son perfectamente adecuados para las pruebas unitarias de su biblioteca en .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f91b3-192">Both are perfectly suitable for unit testing your library on .NET Core.</span></span> <span data-ttu-id="f91b3-193">Cómo configurar la solución con proyectos de prueba dependerá de la [estructura de la solución](#structuring-a-solution).</span><span class="sxs-lookup"><span data-stu-id="f91b3-193">How you set up your solution with test projects will depend on the [structure of your solution](#structuring-a-solution).</span></span> <span data-ttu-id="f91b3-194">En el ejemplo siguiente se presupone que los directorios de origen y de prueba residen en el mismo directorio de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="f91b3-194">The following example assumes that the test and source directories live in the same top-level directory.</span></span>

> [!NOTE]
> <span data-ttu-id="f91b3-195">Esto usa algunos comandos de la [CLI de .NET Core](../tools/index.md).</span><span class="sxs-lookup"><span data-stu-id="f91b3-195">This uses some [.NET Core CLI](../tools/index.md) commands.</span></span> <span data-ttu-id="f91b3-196">Vea [dotnet new](../tools/dotnet-new.md) y [dotnet sln](../tools/dotnet-sln.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f91b3-196">See [dotnet new](../tools/dotnet-new.md) and [dotnet sln](../tools/dotnet-sln.md) for more information.</span></span>

1. <span data-ttu-id="f91b3-197">Configure la solución.</span><span class="sxs-lookup"><span data-stu-id="f91b3-197">Set up your solution.</span></span> <span data-ttu-id="f91b3-198">Puede hacerlo con los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="f91b3-198">You can do so with the following commands:</span></span>

   ```dotnetcli
   mkdir SolutionWithSrcAndTest
   cd SolutionWithSrcAndTest
   dotnet new sln
   dotnet new classlib -o MyProject
   dotnet new xunit -o MyProject.Test
   dotnet sln add MyProject/MyProject.csproj
   dotnet sln add MyProject.Test/MyProject.Test.csproj
   ```

   <span data-ttu-id="f91b3-199">Esto creará proyectos y se vincularán conjuntamente en una solución.</span><span class="sxs-lookup"><span data-stu-id="f91b3-199">This will create projects and link them together in a solution.</span></span> <span data-ttu-id="f91b3-200">Su directorio para `SolutionWithSrcAndTest` debe tener el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="f91b3-200">Your directory for `SolutionWithSrcAndTest` should look like this:</span></span>

   ```
   /SolutionWithSrcAndTest
   |__SolutionWithSrcAndTest.sln
   |__MyProject/
   |__MyProject.Test/
   ```

1. <span data-ttu-id="f91b3-201">Vaya al directorio del proyecto de prueba y agregue una referencia a `MyProject.Test` desde `MyProject`.</span><span class="sxs-lookup"><span data-stu-id="f91b3-201">Navigate to the test project's directory and add a reference to `MyProject.Test` from `MyProject`.</span></span>

   ```dotnetcli
   cd MyProject.Test
   dotnet add reference ../MyProject/MyProject.csproj
   ```

1. <span data-ttu-id="f91b3-202">Restaurar paquetes y crear proyectos:</span><span class="sxs-lookup"><span data-stu-id="f91b3-202">Restore packages and build projects:</span></span>

   ```dotnetcli
   dotnet restore
   dotnet build
   ```

   [!INCLUDE[DotNet Restore Note](../../../includes/dotnet-restore-note.md)]

1. <span data-ttu-id="f91b3-203">Compruebe que xUnit se ejecuta mediante la ejecución del comando `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="f91b3-203">Verify that xUnit runs by executing the `dotnet test` command.</span></span> <span data-ttu-id="f91b3-204">Si decide usar MSTest, entonces debe ejecutarse en su lugar el ejecutor de la consola de MSTest.</span><span class="sxs-lookup"><span data-stu-id="f91b3-204">If you chose to use MSTest, then the MSTest console runner should run instead.</span></span>

<span data-ttu-id="f91b3-205">Y listo.</span><span class="sxs-lookup"><span data-stu-id="f91b3-205">And that's it!</span></span> <span data-ttu-id="f91b3-206">Ahora puede probar la biblioteca en todas las plataformas; para ello, use herramientas de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="f91b3-206">You can now test your library across all platforms using command-line tools.</span></span> <span data-ttu-id="f91b3-207">Para seguir con las pruebas ahora que ya está todo configurado, probar la biblioteca es un proceso muy simple:</span><span class="sxs-lookup"><span data-stu-id="f91b3-207">To continue testing now that you have everything set up, testing your library is very simple:</span></span>

1. <span data-ttu-id="f91b3-208">Haga los cambios en la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="f91b3-208">Make changes to your library.</span></span>
1. <span data-ttu-id="f91b3-209">Ejecute las pruebas desde la línea de comandos, en el directorio de prueba, con el comando `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="f91b3-209">Run tests from the command line, in your test directory, with `dotnet test` command.</span></span>

<span data-ttu-id="f91b3-210">El código se recompilará automáticamente cuando invoque el comando `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="f91b3-210">Your code will be automatically rebuilt when you invoke `dotnet test` command.</span></span>

## <a name="how-to-use-multiple-projects"></a><span data-ttu-id="f91b3-211">Uso de varios proyectos</span><span class="sxs-lookup"><span data-stu-id="f91b3-211">How to use multiple projects</span></span>

<span data-ttu-id="f91b3-212">Una necesidad en común de las bibliotecas de mayor tamaño es ubicar la funcionalidad en distintos proyectos.</span><span class="sxs-lookup"><span data-stu-id="f91b3-212">A common need for larger libraries is to place functionality in different projects.</span></span>

<span data-ttu-id="f91b3-213">Imagine que desea compilar una biblioteca que se pudiera consumir en C# y F# idiomático.</span><span class="sxs-lookup"><span data-stu-id="f91b3-213">Imagine you want to build a library that could be consumed in idiomatic C# and F#.</span></span> <span data-ttu-id="f91b3-214">Eso significaría que los usuarios de las bibliotecas las consumirían de manera natural para C# o F#.</span><span class="sxs-lookup"><span data-stu-id="f91b3-214">That would mean that consumers of your library consume it in ways that are natural to C# or F#.</span></span> <span data-ttu-id="f91b3-215">Por ejemplo, en C#, podría consumir la biblioteca de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="f91b3-215">For example, in C# you might consume the library like this:</span></span>

```csharp
using AwesomeLibrary.CSharp;

public Task DoThings(Data data)
{
    var convertResult = await AwesomeLibrary.ConvertAsync(data);
    var result = AwesomeLibrary.Process(convertResult);
    // do something with result
}
```

<span data-ttu-id="f91b3-216">En F#, sería de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="f91b3-216">In F#, it might look like this:</span></span>

```fsharp
open AwesomeLibrary.FSharp

let doWork data = async {
    let! result = AwesomeLibrary.AsyncConvert data // Uses an F# async function rather than C# async method
    // do something with result
}
```

<span data-ttu-id="f91b3-217">Escenarios de consumo similares a este significan que las API a las que se tiene acceso deben tener una estructura distinta para C# y para F#.</span><span class="sxs-lookup"><span data-stu-id="f91b3-217">Consumption scenarios like this mean that the APIs being accessed have to have a different structure for C# and F#.</span></span>  <span data-ttu-id="f91b3-218">Un enfoque común para lograrlo es factorizar toda la lógica de una biblioteca en un proyecto central, con los proyectos de C# y F# definiendo los niveles de API que hacen llamadas a ese proyecto central.</span><span class="sxs-lookup"><span data-stu-id="f91b3-218">A common approach to accomplishing this is to factor all of the logic of a library into a core project, with C# and F# projects defining the API layers that call into that core project.</span></span>  <span data-ttu-id="f91b3-219">En el resto de la sección se usarán los siguientes nombres:</span><span class="sxs-lookup"><span data-stu-id="f91b3-219">The rest of the section will use the following names:</span></span>

* <span data-ttu-id="f91b3-220">**AwesomeLibrary.Core** : un proyecto central que contiene toda la lógica de la biblioteca</span><span class="sxs-lookup"><span data-stu-id="f91b3-220">**AwesomeLibrary.Core** - A core project that contains all logic for the library</span></span>
* <span data-ttu-id="f91b3-221">**AwesomeLibrary.CSharp** : un proyecto con API públicas pensado para el consumo en C#</span><span class="sxs-lookup"><span data-stu-id="f91b3-221">**AwesomeLibrary.CSharp** - A project with public APIs intended for consumption in C#</span></span>
* <span data-ttu-id="f91b3-222">**AwesomeLibrary.FSharp** : un proyecto con API públicas pensado para el consumo en F#</span><span class="sxs-lookup"><span data-stu-id="f91b3-222">**AwesomeLibrary.FSharp** - A project with public APIs intended for consumption in F#</span></span>

<span data-ttu-id="f91b3-223">Puede ejecutar los siguientes comandos en su terminal para generar la misma estructura de esta guía:</span><span class="sxs-lookup"><span data-stu-id="f91b3-223">You can run the following commands in your terminal to produce the same structure as this guide:</span></span>

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

<span data-ttu-id="f91b3-224">Esto agregará los tres proyectos anteriores y un archivo de solución que los vincula conjuntamente.</span><span class="sxs-lookup"><span data-stu-id="f91b3-224">This will add the three projects above and a solution file that links them together.</span></span> <span data-ttu-id="f91b3-225">Crear el archivo de solución y vincular los proyectos le permitirá restaurar y crear proyectos desde un nivel superior.</span><span class="sxs-lookup"><span data-stu-id="f91b3-225">Creating the solution file and linking projects will allow you to restore and build projects from a top level.</span></span>

### <a name="project-to-project-referencing"></a><span data-ttu-id="f91b3-226">Referencias entre proyectos</span><span class="sxs-lookup"><span data-stu-id="f91b3-226">Project-to-project referencing</span></span>

<span data-ttu-id="f91b3-227">La mejor manera de hacer referencia a un proyecto es usar la CLI de .NET Core para agregar una referencia de proyecto.</span><span class="sxs-lookup"><span data-stu-id="f91b3-227">The best way to reference a project is to use the .NET Core CLI to add a project reference.</span></span> <span data-ttu-id="f91b3-228">Desde los directorios del proyecto **AwesomeLibrary.CSharp** y **AwesomeLibrary.FSharp** , puede ejecutar el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="f91b3-228">From the **AwesomeLibrary.CSharp** and **AwesomeLibrary.FSharp** project directories, you can run the following command:</span></span>

```dotnetcli
dotnet add reference ../AwesomeLibrary.Core/AwesomeLibrary.Core.csproj
```

<span data-ttu-id="f91b3-229">Los archivos del proyecto para **AwesomeLibrary.CSharp** y **AwesomeLibrary.FSharp** ahora harán referencia a **AwesomeLibrary.Core** como un destino `ProjectReference`.</span><span class="sxs-lookup"><span data-stu-id="f91b3-229">The project files for both **AwesomeLibrary.CSharp** and **AwesomeLibrary.FSharp** will now reference **AwesomeLibrary.Core** as a `ProjectReference` target.</span></span>  <span data-ttu-id="f91b3-230">Puede comprobar esto inspeccionando los archivos del proyecto y observando lo siguiente en ellos:</span><span class="sxs-lookup"><span data-stu-id="f91b3-230">You can verify this by inspecting the project files and seeing the following in them:</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\AwesomeLibrary.Core\AwesomeLibrary.Core.csproj" />
</ItemGroup>
```

<span data-ttu-id="f91b3-231">Puede agregar esta sección a cada archivo del proyecto manualmente si prefiere no usar la CLI de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f91b3-231">You can add this section to each project file manually if you prefer not to use the .NET Core CLI.</span></span>

### <a name="structuring-a-solution"></a><span data-ttu-id="f91b3-232">Estructura de una solución</span><span class="sxs-lookup"><span data-stu-id="f91b3-232">Structuring a solution</span></span>

<span data-ttu-id="f91b3-233">Otro aspecto importante de las soluciones de varios proyectos es establecer una buena estructura de proyecto general.</span><span class="sxs-lookup"><span data-stu-id="f91b3-233">Another important aspect of multi-project solutions is establishing a good overall project structure.</span></span> <span data-ttu-id="f91b3-234">Puede organizar el código de la manera que quiera, y siempre y cuando vincule cada proyecto a su archivo de solución con `dotnet sln add`, podrá ejecutar `dotnet restore` y `dotnet build` en el nivel de solución.</span><span class="sxs-lookup"><span data-stu-id="f91b3-234">You can organize code however you like, and as long as you link each project to your solution file with `dotnet sln add`, you will be able to run `dotnet restore` and `dotnet build` at the solution level.</span></span>
