---
title: Novedades de .NET Standard
ms.custom: updateeachrelease
ms.date: 11/08/2017
ms.prod: .net
ms.topic: article
ms.technology: dotnet-standard
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3a5833bdfcf1e3433ea82403908e9a06a88cde27
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="whats-new-in-the-net-standard"></a><span data-ttu-id="c06a0-102">Novedades de .NET Standard</span><span class="sxs-lookup"><span data-stu-id="c06a0-102">What's new in the .NET Standard</span></span>

<span data-ttu-id="c06a0-103">.NET Standard es una especificación formal que define un conjunto de API con control de versiones que debe estar disponible en las implementaciones de .NET que cumplen con esa versión del estándar.</span><span class="sxs-lookup"><span data-stu-id="c06a0-103">The .NET Standard is a formal specification that defines a versioned set of APIs which must be available on .NET implementations that comply with that version of the standard.</span></span> <span data-ttu-id="c06a0-104">.NET Standard está dirigido a los desarrolladores de bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="c06a0-104">The .NET Standard is targeted at library developers.</span></span> <span data-ttu-id="c06a0-105">Una biblioteca que tenga como destino una versión estándar de .NET Standard se puede usar en cualquier implementación de .NET Framework, .NET Core o Xamarin que admita esa versión del estándar.</span><span class="sxs-lookup"><span data-stu-id="c06a0-105">A library that targets a .NET Standard version can be used on any .NET Framework, .NET Core, or Xamarin implementation that supports that version of the standard.</span></span>

<span data-ttu-id="c06a0-106">La versión más reciente de .NET Standard es la 2.0.</span><span class="sxs-lookup"><span data-stu-id="c06a0-106">The most recent version of the .NET Standard is 2.0.</span></span> <span data-ttu-id="c06a0-107">Se incluye con el SDK de .NET Core 2.0, así como con Visual Studio 2017 15.3 con la carga de trabajo de .NET Core instalada.</span><span class="sxs-lookup"><span data-stu-id="c06a0-107">It is included with the .NET Core 2.0 SDK, as well as with Visual Studio 2017 Version 15.3 with the .NET Core workload installed.</span></span>

## <a name="supported-net-implementations"></a><span data-ttu-id="c06a0-108">Implementaciones de .NET compatibles</span><span class="sxs-lookup"><span data-stu-id="c06a0-108">Supported .NET implementations</span></span>

<span data-ttu-id="c06a0-109">.NET Standard 2.0 es compatible con las siguientes implementaciones de .NET:</span><span class="sxs-lookup"><span data-stu-id="c06a0-109">The .NET Standard 2.0 is supported by the following .NET implementations:</span></span>

- <span data-ttu-id="c06a0-110">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="c06a0-110">.NET Core 2.0</span></span>
- <span data-ttu-id="c06a0-111">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="c06a0-111">.NET Framework 4.6.1</span></span>
- <span data-ttu-id="c06a0-112">Mono 5.4</span><span class="sxs-lookup"><span data-stu-id="c06a0-112">Mono 5.4</span></span>
- <span data-ttu-id="c06a0-113">Xamarin.iOS 10.14</span><span class="sxs-lookup"><span data-stu-id="c06a0-113">Xamarin.iOS 10.14</span></span>
- <span data-ttu-id="c06a0-114">Xamarin.Mac 3.8</span><span class="sxs-lookup"><span data-stu-id="c06a0-114">Xamarin.Mac 3.8</span></span>
- <span data-ttu-id="c06a0-115">Xamarin.Android 8.0</span><span class="sxs-lookup"><span data-stu-id="c06a0-115">Xamarin.Android 8.0</span></span>
- <span data-ttu-id="c06a0-116">Plataforma universal de Windows 10.0.16299</span><span class="sxs-lookup"><span data-stu-id="c06a0-116">Universal Windows Platform 10.0.16299</span></span>

## <a name="whats-new-in-the-net-standard-20"></a><span data-ttu-id="c06a0-117">Novedades de .NET Standard 2.0</span><span class="sxs-lookup"><span data-stu-id="c06a0-117">What's new in the .NET Standard 2.0</span></span>
 
<span data-ttu-id="c06a0-118">.NET Standard 2.0 incluye las siguientes características nuevas:</span><span class="sxs-lookup"><span data-stu-id="c06a0-118">The .NET Standard 2.0 includes the following new features:</span></span>

<span data-ttu-id="c06a0-119">**Un conjunto de API ampliamente expandido**</span><span class="sxs-lookup"><span data-stu-id="c06a0-119">**A vastly expanded set of APIs**</span></span>

<span data-ttu-id="c06a0-120">Con la versión 1.6, .NET Standard incluía un subconjunto relativamente pequeño de API.</span><span class="sxs-lookup"><span data-stu-id="c06a0-120">Through version 1.6, the .NET Standard included a comparatively small subset of APIs.</span></span> <span data-ttu-id="c06a0-121">Entre las excluidas estaban muchas API utilizadas habitualmente en .NET Framework o Xamarin.</span><span class="sxs-lookup"><span data-stu-id="c06a0-121">Among those excluded were many APIs that were commonly used in the .NET Framework or Xamarin.</span></span> <span data-ttu-id="c06a0-122">Esto complica el desarrollo, ya que los desarrolladores tienen que encontrar sustitutas adecuadas para API familiares para desarrollar aplicaciones y bibliotecas destinadas a varias implementaciones de .NET.</span><span class="sxs-lookup"><span data-stu-id="c06a0-122">This complicates development, since it requires that developers find suitable replacements for familiar APIs when they develop applications and libraries that target multiple .NET implementations.</span></span> <span data-ttu-id="c06a0-123">.NET Standard 2.0 soluciona esta limitación con la adición de más de 20 000 API que estaban disponibles en .NET Standard 1.6, la versión anterior del estándar.</span><span class="sxs-lookup"><span data-stu-id="c06a0-123">The .NET Standard 2.0 addresses this limitation by adding over 20,000 more APIs than were available in .NET Standard 1.6, the previous version of the standard.</span></span> <span data-ttu-id="c06a0-124">Si desea consultar una lista de las API agregadas a .NET Standard 2.0, vea [la comparación entre .NET Standard 2.0 y 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span><span class="sxs-lookup"><span data-stu-id="c06a0-124">For a list of the APIs that have been added to the .NET Standard 2.0, see [.NET Standard 2.0 vs 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span></span> 

<span data-ttu-id="c06a0-125">Alguna de las adiciones al espacio de nombres <xref:System> de .NET Standard 2.0 incluyen:</span><span class="sxs-lookup"><span data-stu-id="c06a0-125">Some of the additions to the <xref:System> namespace in .NET Standard 2.0 include:</span></span>

- <span data-ttu-id="c06a0-126">Compatibilidad con la clase <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="c06a0-126">Support for the <xref:System.AppDomain> class.</span></span>
- <span data-ttu-id="c06a0-127">Mayor compatibilidad para trabajar con matrices de miembros adicionales en la clase <xref:System.Array>.</span><span class="sxs-lookup"><span data-stu-id="c06a0-127">Better support for working with arrays from additional members in the <xref:System.Array> class.</span></span>
- <span data-ttu-id="c06a0-128">Mayor compatibilidad para trabajar con atributos de miembros adicionales en la clase <xref:System.Attribute>.</span><span class="sxs-lookup"><span data-stu-id="c06a0-128">Better support for working with attributes from additional members in the <xref:System.Attribute> class.</span></span>
- <span data-ttu-id="c06a0-129">Mayor compatibilidad del calendario y opciones de formato adicionales para los valores <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="c06a0-129">Better calendar support and additional formatting options for <xref:System.DateTime> values.</span></span>
- <span data-ttu-id="c06a0-130">Funcionalidad de redondeo <xref:System.Decimal> adicional.</span><span class="sxs-lookup"><span data-stu-id="c06a0-130">Additional <xref:System.Decimal> rounding functionality.</span></span>
- <span data-ttu-id="c06a0-131">Funcionalidad adicional en la clase <xref:System.Environment>.</span><span class="sxs-lookup"><span data-stu-id="c06a0-131">Additional functionality in the <xref:System.Environment> class.</span></span>
- <span data-ttu-id="c06a0-132">Control mejorado sobre el recolector de elementos no utilizados en la clase <xref:System.GC>.</span><span class="sxs-lookup"><span data-stu-id="c06a0-132">Enhanced control over the garbage collector through the <xref:System.GC> class.</span></span>
- <span data-ttu-id="c06a0-133">Compatibilidad mejorada para la comparación de cadenas, la enumeración y la normalización en la clase <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="c06a0-133">Enhanced support for string comparison, enumeration, and normalization in the <xref:System.String> class.</span></span>
- <span data-ttu-id="c06a0-134">Compatibilidad para los tiempos de transición y los ajustes del horario de verano en las clases <xref:System.TimeZoneInfo.AdjustmentRule> y <xref:System.TimeZoneInfo.TransitionTime>.</span><span class="sxs-lookup"><span data-stu-id="c06a0-134">Support for daylight saving adjustments and transition times in the <xref:System.TimeZoneInfo.AdjustmentRule> and <xref:System.TimeZoneInfo.TransitionTime> classes.</span></span>
- <span data-ttu-id="c06a0-135">Funcionalidad mejorada significativamente en la clase <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="c06a0-135">Significantly enhanced functionality in the <xref:System.Type> class.</span></span>
- <span data-ttu-id="c06a0-136">Mejor compatibilidad para la deserialización de objetos de excepción mediante la adición de un constructor de excepción con los parámetros <xref:System.Runtime.Serialization.SerializationInfo> y <xref:System.Runtime.Serialization.StreamingContext>.</span><span class="sxs-lookup"><span data-stu-id="c06a0-136">Better support for deserialization of exception objects by adding an exception constructor with <xref:System.Runtime.Serialization.SerializationInfo> and <xref:System.Runtime.Serialization.StreamingContext> parameters.</span></span>

<span data-ttu-id="c06a0-137">**Compatibilidad con las bibliotecas .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="c06a0-137">**Support for .NET Framework libraries**</span></span>

<span data-ttu-id="c06a0-138">La gran mayoría de las bibliotecas tienen como destino .NET Framework en lugar de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="c06a0-138">The overwhelming majority of libraries target the .NET Framework rather than .NET Standard.</span></span> <span data-ttu-id="c06a0-139">Sin embargo, la mayoría de las llamadas de esas bibliotecas se realizan a las API incluidas en .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="c06a0-139">However, most of the calls in those libraries are to APIs that are included in the .NET Standard 2.0.</span></span> <span data-ttu-id="c06a0-140">A partir de .NET Standard 2.0, puede acceder a las bibliotecas de .NET Framework desde una biblioteca de .NET Standard con el uso de una [corrección de compatibilidad](https://github.com/dotnet/standard/blob/master/docs/netstandard-20/README.md#assembly-unification).</span><span class="sxs-lookup"><span data-stu-id="c06a0-140">Starting with the .NET Standard 2.0, you can access .NET Framework libraries from a .NET Standard library by using a [compatibility shim](https://github.com/dotnet/standard/blob/master/docs/netstandard-20/README.md#assembly-unification).</span></span> <span data-ttu-id="c06a0-141">Este nivel de compatibilidad es transparente para los desarrolladores; no tiene que hacer nada para aprovechar las ventajas de las bibliotecas de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c06a0-141">This compatibility layer is transparent to developers; you don't have to do anything to take advantage of .NET Framework libraries.</span></span>

<span data-ttu-id="c06a0-142">El único requisito es que las API a las que llaman las bibliotecas de clases de .NET Framework estén incluidas en .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="c06a0-142">The single requirement is that the APIs called by the .NET Framework class library must be included in the .NET Standard 2.0.</span></span>

<span data-ttu-id="c06a0-143">**Compatibilidad con Visual Basic**</span><span class="sxs-lookup"><span data-stu-id="c06a0-143">**Support for Visual Basic**</span></span>

<span data-ttu-id="c06a0-144">Ahora puede desarrollar bibliotecas de .NET Standard en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c06a0-144">You can now develop .NET Standard libraries in Visual Basic.</span></span> <span data-ttu-id="c06a0-145">Para los desarrolladores de Visual Basic que usan Visual Studio 2017 15.3 o posterior con la carga de trabajo de .NET Core instalada, Visual Studio ahora incluye una plantilla de la biblioteca de clases de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="c06a0-145">For Visual Basic developers using Visual Studio 2017 Version 15.3 or later with the .NET Core workload installed, Visual Studio now includes a .NET Standard Class Library template.</span></span> <span data-ttu-id="c06a0-146">Para los desarrolladores de Visual Basic que usan otras herramientas y entornos de desarrollo, puede usar el comando [dotnet new](../../core/tools/dotnet-new.md) para crear un proyecto de biblioteca de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="c06a0-146">For Visual Basic developers who use other development tools and environments, you can use the [dotnet new](../../core/tools/dotnet-new.md) command to create a .NET Standard Library project.</span></span> <span data-ttu-id="c06a0-147">Para más información, vea [Compatibilidad con herramientas de bibliotecas estándar de .NET](#tooling).</span><span class="sxs-lookup"><span data-stu-id="c06a0-147">For more information, see the [Tooling support for .NET Standard libraries](#tooling).</span></span>

<span data-ttu-id="c06a0-148"><a name="tooling" />**Compatibilidad con herramientas de bibliotecas estándar de .NET**</span><span class="sxs-lookup"><span data-stu-id="c06a0-148"><a name="tooling" />**Tooling support for .NET Standard libraries**</span></span>

<span data-ttu-id="c06a0-149">Con la versión de .NET Core 2.0 y .NET Standard 2.0, Visual Studio 2017 y la [interfaz de la línea de comandos (CLI) de .NET Core](../../core/tools/index.md) incluyen compatibilidad con herramientas para crear bibliotecas de NET Standard.</span><span class="sxs-lookup"><span data-stu-id="c06a0-149">With the release of .NET Core 2.0 and .NET Standard 2.0, both Visual Studio 2017 and the [.NET Core Command Line Interface (CLI)](../../core/tools/index.md) include tooling support for creating .NET Standard libraries.</span></span> 

<span data-ttu-id="c06a0-150">Si instala Visual Studio con la carga de trabajo de **desarrollo multiplataforma de .NET Core**, puede crear un proyecto de biblioteca de .NET Standard 2.0 con el uso de una plantilla de proyecto, como se muestra en la figura siguiente.</span><span class="sxs-lookup"><span data-stu-id="c06a0-150">If you install Visual Studio with the **.NET Core cross-platform development** workload, you can create a .NET Standard 2.0 library project by using a project template, as the following figure shows.</span></span> 

# <a name="ctabcsharp"></a>[<span data-ttu-id="c06a0-151">C#</span><span class="sxs-lookup"><span data-stu-id="c06a0-151">C#</span></span>](#tab/csharp)
![Agregar un proyecto de biblioteca nuevo de .NET Standard](./media/std-project-cs.png)
# <a name="visual-basictabvisual-basic"></a>[<span data-ttu-id="c06a0-153">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c06a0-153">Visual Basic</span></span>](#tab/visual-basic)
<a name="add-new-net-standard-library-projectmediastd-project-vbpng"></a>![Agregar un proyecto de biblioteca nuevo de .NET Standard](./media/std-project-vb.png)
---

<span data-ttu-id="c06a0-155">Si usa la CLI de .NET Core, el siguiente comando [dotnet new](../../core/tools/dotnet-new.md) crea un proyecto de biblioteca de clases que tenga como destino .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="c06a0-155">If you are using the .NET Core CLI, the following [dotnet new](../../core/tools/dotnet-new.md) command creates a class library project that targets the .NET Standard 2.0.</span></span>

```csharp
dotnet new classlib
```
```vb
dotnet new classlib -lang vb
```
  
## <a name="see-also"></a><span data-ttu-id="c06a0-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="c06a0-156">See Also</span></span>
<span data-ttu-id="c06a0-157">[.NET Standard](../net-standard.md)
[Introducing .NET Standard](https://blogs.msdn.microsoft.com/dotnet/2016/09/26/introducing-net-standard/) (Introducción a .NET Standard)</span><span class="sxs-lookup"><span data-stu-id="c06a0-157">[.NET Standard](../net-standard.md)
[Introducing .NET Standard](https://blogs.msdn.microsoft.com/dotnet/2016/09/26/introducing-net-standard/)</span></span>
