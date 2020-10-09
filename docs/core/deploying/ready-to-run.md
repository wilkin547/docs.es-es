---
title: Información general sobre la implementación de ReadyToRun
description: Obtenga información sobre qué son las implementaciones de ReadyToRun y por qué debe considerar su uso en el marco de la publicación de la aplicación con .NET 5 y .NET Core 3.0 y versiones posteriores.
author: davidwr
ms.author: davidwr
ms.date: 09/21/2020
ms.openlocfilehash: b4052a0c0f4ed9f6cfd273abe5ef45d018bd0ae0
ms.sourcegitcommit: 4d45bda8cd9558ea8af4be591e3d5a29360c1ece
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2020
ms.locfileid: "91654952"
---
# <a name="readytorun-compilation"></a><span data-ttu-id="2563d-103">Compilación ReadyToRun</span><span class="sxs-lookup"><span data-stu-id="2563d-103">ReadyToRun Compilation</span></span>

<span data-ttu-id="2563d-104">La latencia y el tiempo de inicio de la aplicación .NET se pueden mejorar si se compilan los ensamblados de aplicación como formato ReadyToRun (R2R).</span><span class="sxs-lookup"><span data-stu-id="2563d-104">.NET application startup time and latency can be improved by compiling your application assemblies as ReadyToRun (R2R) format.</span></span> <span data-ttu-id="2563d-105">R2R es una forma de compilación Ahead Of Time (AOT).</span><span class="sxs-lookup"><span data-stu-id="2563d-105">R2R is a form of ahead-of-time (AOT) compilation.</span></span>

<span data-ttu-id="2563d-106">Los binarios de R2R mejoran el rendimiento de inicio reduciendo la cantidad de trabajo que el compilador Just-In-Time (JIT) debe llevar a cabo cuando se carga la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2563d-106">R2R binaries improve startup performance by reducing the amount of work the just-in-time (JIT) compiler needs to do as your application loads.</span></span> <span data-ttu-id="2563d-107">Los binarios contienen código nativo similar en comparación con lo que generaría el compilador JIT.</span><span class="sxs-lookup"><span data-stu-id="2563d-107">The binaries contain similar native code compared to what the JIT would produce.</span></span> <span data-ttu-id="2563d-108">Sin embargo, los binarios de R2R son más grandes porque contienen tanto el código de lenguaje intermedio (IL), que sigue siendo necesario para algunos escenarios, como la versión nativa del mismo código.</span><span class="sxs-lookup"><span data-stu-id="2563d-108">However, R2R binaries are larger because they contain both intermediate language (IL) code, which is still needed for some scenarios, and the native version of the same code.</span></span> <span data-ttu-id="2563d-109">R2R solo está disponible cuando publica una aplicación que tenga como destino entornos de tiempo de ejecución específicos (RID), como Linux x64 o Windows x64.</span><span class="sxs-lookup"><span data-stu-id="2563d-109">R2R is only available when you publish an app that targets specific runtime environments (RID) such as Linux x64 or Windows x64.</span></span>

<span data-ttu-id="2563d-110">Para compilar el proyecto como ReadyToRun, la aplicación debe publicarse con la propiedad PublishReadyToRun establecida en true.</span><span class="sxs-lookup"><span data-stu-id="2563d-110">To compile your project as ReadyToRun, the application must be published with the PublishReadyToRun property set to true.</span></span>

<span data-ttu-id="2563d-111">Hay dos maneras de publicar la aplicación como ReadyToRun:</span><span class="sxs-lookup"><span data-stu-id="2563d-111">There are two ways to publish your app as ReadyToRun:</span></span>

01. <span data-ttu-id="2563d-112">Especifique la marca PublishReadyToRun directamente en el comando dotnet publish.</span><span class="sxs-lookup"><span data-stu-id="2563d-112">Specify the PublishReadyToRun flag directly to the dotnet publish command.</span></span> <span data-ttu-id="2563d-113">Consulte [dotnet publish](../tools/dotnet-publish.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2563d-113">See [dotnet publish](../tools/dotnet-publish.md) for details.</span></span>

    ```dotnetcli
    dotnet publish -c Release -r win-x64 -p:PublishReadyToRun=true
    ```

02. <span data-ttu-id="2563d-114">Especificación de la propiedad en el proyecto</span><span class="sxs-lookup"><span data-stu-id="2563d-114">Specify the property in the project</span></span>

    - <span data-ttu-id="2563d-115">Agregue el valor `<PublishReadyToRun>` al proyecto.</span><span class="sxs-lookup"><span data-stu-id="2563d-115">Add the `<PublishReadyToRun>` setting to your project.</span></span>

    ```xml
    <PropertyGroup>
      <PublishReadyToRun>true</PublishReadyToRun>
    </PropertyGroup>
    ```

    - <span data-ttu-id="2563d-116">Publique la aplicación sin ningún parámetro especial.</span><span class="sxs-lookup"><span data-stu-id="2563d-116">Publish the application without any special parameters.</span></span>

    ```dotnetcli
    dotnet publish -c Release -r win-x64
    ```

## <a name="impact-of-using-the-readytorun-feature"></a><span data-ttu-id="2563d-117">Impacto del uso de la característica ReadyToRun</span><span class="sxs-lookup"><span data-stu-id="2563d-117">Impact of using the ReadyToRun feature</span></span>

<span data-ttu-id="2563d-118">La compilación anticipada tiene un impacto complejo en el rendimiento de la aplicación, que puede ser difícil de predecir.</span><span class="sxs-lookup"><span data-stu-id="2563d-118">Ahead-of-time compilation has complex performance impact on application performance, which may be difficult to predict.</span></span> <span data-ttu-id="2563d-119">En general, el tamaño de un ensamblado aumentará entre dos y tres veces.</span><span class="sxs-lookup"><span data-stu-id="2563d-119">In general, the size of an assembly will grow to between two to three times larger.</span></span> <span data-ttu-id="2563d-120">Este aumento en el tamaño físico del archivo puede reducir el rendimiento de la carga del ensamblado desde el disco y aumentar el espacio de trabajo del proceso.</span><span class="sxs-lookup"><span data-stu-id="2563d-120">This increase in the physical size of the file may reduce the performance of loading the assembly from disk, and increase working set of the process.</span></span> <span data-ttu-id="2563d-121">Sin embargo, a cambio, el número de métodos compilados en el entorno de ejecución suele reducirse considerablemente.</span><span class="sxs-lookup"><span data-stu-id="2563d-121">However, in return the number of methods compiled at runtime is typically reduced substantially.</span></span> <span data-ttu-id="2563d-122">El resultado es que la mayoría de las aplicaciones que tienen grandes cantidades de código obtienen beneficios de rendimiento elevados de la habilitación de ReadyToRun.</span><span class="sxs-lookup"><span data-stu-id="2563d-122">The result is that most applications that large amounts of code receive large performance benefits from enabling ReadyToRun.</span></span> <span data-ttu-id="2563d-123">Las aplicaciones con pequeñas cantidades de código probablemente no experimentarán una mejora significativa en la habilitación de ReadyToRun, ya que las bibliotecas del entorno de ejecución de .NET ya se han precompilado con ReadyToRun.</span><span class="sxs-lookup"><span data-stu-id="2563d-123">Applications, which have small amounts of code will likely not experience a significant improvement from enabling ReadyToRun, as the .NET runtime libraries have already been precompiled with ReadyToRun.</span></span>

<span data-ttu-id="2563d-124">La mejora de inicio que se describe aquí no solo se aplica al inicio de la aplicación, sino también al primer uso de cualquier código de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2563d-124">The startup improvement discussed here applies not only to application startup, but also to the first use of any code in the application.</span></span> <span data-ttu-id="2563d-125">Por ejemplo, ReadyToRun se puede usar para reducir la latencia de respuesta del primer uso de la API web en una aplicación de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="2563d-125">For instance, ReadyToRun can be used to reduce the response latency of the first use  of Web API in an ASP.NET application.</span></span>

### <a name="interaction-with-tiered-compilation"></a><span data-ttu-id="2563d-126">Interacción con la compilación en capas</span><span class="sxs-lookup"><span data-stu-id="2563d-126">Interaction with tiered compilation</span></span>

<span data-ttu-id="2563d-127">La compilación anticipada generada no está tan optimizada como el código generado por JIT.</span><span class="sxs-lookup"><span data-stu-id="2563d-127">Ahead-of-time generated is not as highly optimized as code produced by the JIT.</span></span> <span data-ttu-id="2563d-128">Para solucionar este problema, la compilación en capas reemplazará los métodos de ReadyToRun usados comúnmente con métodos generados por JIT.</span><span class="sxs-lookup"><span data-stu-id="2563d-128">To address this issue, tiered compilation will replace commonly used ReadyToRun methods with JIT-generated methods.</span></span>

## <a name="how-is-the-set-of-precompiled-assemblies-chosen"></a><span data-ttu-id="2563d-129">¿Cómo se elige el conjunto de ensamblados precompilados?</span><span class="sxs-lookup"><span data-stu-id="2563d-129">How is the set of precompiled assemblies chosen?</span></span>

<span data-ttu-id="2563d-130">El SDK precompilará los ensamblados que se distribuyen con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2563d-130">The SDK will precompile the assemblies that are distributed with the application.</span></span> <span data-ttu-id="2563d-131">En el caso de las aplicaciones independientes, este conjunto de ensamblados incluirá el marco.</span><span class="sxs-lookup"><span data-stu-id="2563d-131">For self-contained applications, this set of assemblies will include the framework.</span></span> <span data-ttu-id="2563d-132">Los archivos binarios de C++/CLI no son válidos para la compilación de ReadyToRun.</span><span class="sxs-lookup"><span data-stu-id="2563d-132">C++/CLI binaries are not eligible for ReadyToRun compilation.</span></span>

## <a name="how-is-the-set-of-methods-to-precompile-chosen"></a><span data-ttu-id="2563d-133">¿Cómo se elige el conjunto de métodos para la precompilación?</span><span class="sxs-lookup"><span data-stu-id="2563d-133">How is the set of methods to precompile chosen?</span></span>

<span data-ttu-id="2563d-134">El compilador intentará precompilar todos los métodos que pueda.</span><span class="sxs-lookup"><span data-stu-id="2563d-134">The compiler will attempt to pre-compile as many methods as it can.</span></span> <span data-ttu-id="2563d-135">Sin embargo, por varias razones, no se espera que el uso de la característica ReadyToRun impida la ejecución de JIT.</span><span class="sxs-lookup"><span data-stu-id="2563d-135">However various reasons it is not expected that using the ReadyToRun feature will result in preventing the JIT from executing.</span></span>

<span data-ttu-id="2563d-136">Estos motivos pueden incluir, entre otros, los siguientes:</span><span class="sxs-lookup"><span data-stu-id="2563d-136">Such reasons may include, but are not limited to:</span></span>

- <span data-ttu-id="2563d-137">Uso de tipos genéricos definidos en ensamblados independientes</span><span class="sxs-lookup"><span data-stu-id="2563d-137">Use of generic types defined in separate assemblies</span></span>
- <span data-ttu-id="2563d-138">Interoperabilidad con código nativo</span><span class="sxs-lookup"><span data-stu-id="2563d-138">Interop with native code</span></span>
- <span data-ttu-id="2563d-139">Uso de elementos intrínsecos de hardware que el compilador no puede probar que sean seguros de usar en una máquina de destino</span><span class="sxs-lookup"><span data-stu-id="2563d-139">Use of hardware intrinsics that the compiler cannot prove are safe to use on a target machine</span></span>
- <span data-ttu-id="2563d-140">Ciertos patrones de IL inusuales</span><span class="sxs-lookup"><span data-stu-id="2563d-140">Certain unusual IL patterns</span></span>
- <span data-ttu-id="2563d-141">Creación de métodos dinámicos mediante reflexión o LINQ</span><span class="sxs-lookup"><span data-stu-id="2563d-141">Dynamic method creation via reflection, or LINQ</span></span>

## <a name="cross-platformarchitecture-restrictions"></a><span data-ttu-id="2563d-142">Restricciones multiplataforma y de arquitectura</span><span class="sxs-lookup"><span data-stu-id="2563d-142">Cross platform/architecture restrictions</span></span>

<span data-ttu-id="2563d-143">Para algunas plataformas SDK, el compilador ReadyToRun es capaz de realizar una compilación cruzada para otras plataformas de destino.</span><span class="sxs-lookup"><span data-stu-id="2563d-143">For some SDK platforms, the ReadyToRun compiler is capable of cross-compiling for other target platforms.</span></span> <span data-ttu-id="2563d-144">Los destinos de compilación admitidos se describen en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="2563d-144">Supported compilation targets are described in the table below.</span></span>

| <span data-ttu-id="2563d-145">Plataforma de SDK</span><span class="sxs-lookup"><span data-stu-id="2563d-145">SDK platform</span></span> | <span data-ttu-id="2563d-146">Plataformas de destino compatibles</span><span class="sxs-lookup"><span data-stu-id="2563d-146">Supported target platforms</span></span> |
| ------------ | --------------------------- |
| <span data-ttu-id="2563d-147">Windows X64</span><span class="sxs-lookup"><span data-stu-id="2563d-147">Windows X64</span></span>  | <span data-ttu-id="2563d-148">Windows X86, Windows X64, Windows ARM32, Windows ARM64</span><span class="sxs-lookup"><span data-stu-id="2563d-148">Windows X86, Windows X64, Windows ARM32, Windows ARM64</span></span> |
| <span data-ttu-id="2563d-149">Windows X86</span><span class="sxs-lookup"><span data-stu-id="2563d-149">Windows X86</span></span>  | <span data-ttu-id="2563d-150">Windows X86, Windows ARM32</span><span class="sxs-lookup"><span data-stu-id="2563d-150">Windows X86, Windows ARM32</span></span> |
| <span data-ttu-id="2563d-151">Linux X64</span><span class="sxs-lookup"><span data-stu-id="2563d-151">Linux X64</span></span>    | <span data-ttu-id="2563d-152">Linux X86, Linux X64, Linux ARM32, Linux ARM64</span><span class="sxs-lookup"><span data-stu-id="2563d-152">Linux X86, Linux X64, Linux ARM32, Linux ARM64</span></span> |
| <span data-ttu-id="2563d-153">Linux ARM32</span><span class="sxs-lookup"><span data-stu-id="2563d-153">Linux ARM32</span></span>  | <span data-ttu-id="2563d-154">Linux ARM32</span><span class="sxs-lookup"><span data-stu-id="2563d-154">Linux ARM32</span></span> |
| <span data-ttu-id="2563d-155">Linux ARM64</span><span class="sxs-lookup"><span data-stu-id="2563d-155">Linux ARM64</span></span>  | <span data-ttu-id="2563d-156">Linux ARM64</span><span class="sxs-lookup"><span data-stu-id="2563d-156">Linux ARM64</span></span> |
| <span data-ttu-id="2563d-157">macOS X64</span><span class="sxs-lookup"><span data-stu-id="2563d-157">macOS X64</span></span>    | <span data-ttu-id="2563d-158">macOS X64</span><span class="sxs-lookup"><span data-stu-id="2563d-158">macOS X64</span></span> |
