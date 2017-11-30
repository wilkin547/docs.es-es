---
title: "Novedades en el estándar de .NET"
ms.custom: updateeachrelease
ms.date: 11/08/2017
ms.prod: .net
ms.topic: article
ms.technology: dotnet-standard
ms.##devlang: dotnet
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e938c009b79af3b2f36094bbb74f4d38baeeac0b
ms.sourcegitcommit: 281070dee88db86ec3bb4634d5f558d1a4e159dd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2017
---
# <a name="whats-new-in-the-net-standard"></a><span data-ttu-id="ca36a-102">Novedades en el estándar de .NET</span><span class="sxs-lookup"><span data-stu-id="ca36a-102">What's new in the .NET Standard</span></span>

<span data-ttu-id="ca36a-103">El estándar de .NET es una especificación formal que define un conjunto con control de versiones de API que deben estar disponibles en las implementaciones de .NET es compatible con esa versión del estándar.</span><span class="sxs-lookup"><span data-stu-id="ca36a-103">The .NET Standard is a formal specification that defines a versioned set of APIs which must be available on .NET implementations that comply with that version of the standard.</span></span> <span data-ttu-id="ca36a-104">.NET Standard está dirigido a los desarrolladores de bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="ca36a-104">The .NET Standard is targeted at library developers.</span></span> <span data-ttu-id="ca36a-105">Una biblioteca que tenga como destino una versión estándar de .NET se puede usar en cualquier implementación de .NET Framework, .NET Core o Xamarin que admita esa versión del estándar.</span><span class="sxs-lookup"><span data-stu-id="ca36a-105">A library that targets a .NET Standard version can be used on any .NET Framework, .NET Core, or Xamarin implementation that supports that version of the standard.</span></span>

<span data-ttu-id="ca36a-106">La versión más reciente de la norma de .NET es 2.0.</span><span class="sxs-lookup"><span data-stu-id="ca36a-106">The most recent version of the .NET Standard is 2.0.</span></span> <span data-ttu-id="ca36a-107">Se incluye con el SDK de .NET Core 2.0, así como con Visual Studio 2017 versión 15.3 con la carga de trabajo de .NET Core instalado.</span><span class="sxs-lookup"><span data-stu-id="ca36a-107">It is included with the .NET Core 2.0 SDK, as well as with Visual Studio 2017 Version 15.3 with the .NET Core workload installed.</span></span>

## <a name="supported-net-implementations"></a><span data-ttu-id="ca36a-108">Implementaciones de .NET compatibles</span><span class="sxs-lookup"><span data-stu-id="ca36a-108">Supported .NET implementations</span></span>

<span data-ttu-id="ca36a-109">El estándar de .NET 2.0 es compatible con las siguientes implementaciones. NET:</span><span class="sxs-lookup"><span data-stu-id="ca36a-109">The .NET Standard 2.0 is supported by the following .NET implementations:</span></span>

- <span data-ttu-id="ca36a-110">Núcleo de .NET 2.0</span><span class="sxs-lookup"><span data-stu-id="ca36a-110">.NET Core 2.0</span></span>
- <span data-ttu-id="ca36a-111">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="ca36a-111">.NET Framework 4.6.1</span></span>
- <span data-ttu-id="ca36a-112">Mono 5.4.</span><span class="sxs-lookup"><span data-stu-id="ca36a-112">Mono 5.4</span></span>
- <span data-ttu-id="ca36a-113">Xamarin.iOS 10.14</span><span class="sxs-lookup"><span data-stu-id="ca36a-113">Xamarin.iOS 10.14</span></span>
- <span data-ttu-id="ca36a-114">Xamarin.Mac 3.8</span><span class="sxs-lookup"><span data-stu-id="ca36a-114">Xamarin.Mac 3.8</span></span>
- <span data-ttu-id="ca36a-115">Xamarin.Android 8.0</span><span class="sxs-lookup"><span data-stu-id="ca36a-115">Xamarin.Android 8.0</span></span>
- <span data-ttu-id="ca36a-116">Plataforma universal de Windows 10.0.16299</span><span class="sxs-lookup"><span data-stu-id="ca36a-116">Universal Windows Platform 10.0.16299</span></span>

## <a name="whats-new-in-the-net-standard-20"></a><span data-ttu-id="ca36a-117">Novedades en el estándar de .NET 2.0</span><span class="sxs-lookup"><span data-stu-id="ca36a-117">What's new in the .NET Standard 2.0</span></span>
 
<span data-ttu-id="ca36a-118">El estándar de .NET 2.0 incluye las siguientes características nuevas:</span><span class="sxs-lookup"><span data-stu-id="ca36a-118">The .NET Standard 2.0 includes the following new features:</span></span>

<span data-ttu-id="ca36a-119">**Un conjunto de API ampliamente expandido**</span><span class="sxs-lookup"><span data-stu-id="ca36a-119">**A vastly expanded set of APIs**</span></span>

<span data-ttu-id="ca36a-120">A través de la versión 1.6, el estándar de .NET incluyen un subconjunto relativamente pequeño de API.</span><span class="sxs-lookup"><span data-stu-id="ca36a-120">Through version 1.6, the .NET Standard included a comparatively small subset of APIs.</span></span> <span data-ttu-id="ca36a-121">Entre los que quedan excluidos estaban muchas API que se utilizan con frecuencia en .NET Framework o Xamarin.</span><span class="sxs-lookup"><span data-stu-id="ca36a-121">Among those excluded were many APIs that were commonly used in the .NET Framework or Xamarin.</span></span> <span data-ttu-id="ca36a-122">Esto complica desarrollo, ya que requiere que los desarrolladores encuentran sustitutos adecuados para las API familiarizadas cuando desarrollan aplicaciones y bibliotecas destinadas a varias implementaciones. NET.</span><span class="sxs-lookup"><span data-stu-id="ca36a-122">This complicates development, since it requires that developers find suitable replacements for familiar APIs when they develop applications and libraries that target multiple .NET implementations.</span></span> <span data-ttu-id="ca36a-123">El estándar de .NET 2.0 aborda esta limitación mediante la adición de más de 20.000 API más que estaban disponibles en .NET estándar 1.6, la versión anterior del estándar.</span><span class="sxs-lookup"><span data-stu-id="ca36a-123">The .NET Standard 2.0 addresses this limitation by adding over 20,000 more APIs than were available in .NET Standard 1.6, the previous version of the standard.</span></span> <span data-ttu-id="ca36a-124">Para obtener una lista de las API que se han agregado para el estándar de .NET 2.0, consulte [.NET 2.0 estándar vs 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span><span class="sxs-lookup"><span data-stu-id="ca36a-124">For a list of the APIs that have been added to the .NET Standard 2.0, see [.NET Standard 2.0 vs 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span></span> 

<span data-ttu-id="ca36a-125">Algunas de las adiciones a la <xref:System> incluir el espacio de nombres estándar de .NET 2.0:</span><span class="sxs-lookup"><span data-stu-id="ca36a-125">Some of the additions to the <xref:System> namespace in .NET Standard 2.0 include:</span></span>

- <span data-ttu-id="ca36a-126">Compatibilidad con la <xref:System.AppDomain> clase.</span><span class="sxs-lookup"><span data-stu-id="ca36a-126">Support for the <xref:System.AppDomain> class.</span></span>
- <span data-ttu-id="ca36a-127">Mejor compatibilidad para trabajar con matrices de miembros adicionales en la <xref:System.Array> clase.</span><span class="sxs-lookup"><span data-stu-id="ca36a-127">Better support for working with arrays from additional members in the <xref:System.Array> class.</span></span>
- <span data-ttu-id="ca36a-128">Mejor compatibilidad para trabajar con atributos de miembros adicionales en la <xref:System.Attribute> clase.</span><span class="sxs-lookup"><span data-stu-id="ca36a-128">Better support for working with attributes from additional members in the <xref:System.Attribute> class.</span></span>
- <span data-ttu-id="ca36a-129">Calendario mejor compatibilidad con y opciones de formato adicionales para <xref:System.DateTime> valores.</span><span class="sxs-lookup"><span data-stu-id="ca36a-129">Better calendar support and additional formatting options for <xref:System.DateTime> values.</span></span>
- <span data-ttu-id="ca36a-130">Adicionales <xref:System.Decimal> funcionalidad de redondeo.</span><span class="sxs-lookup"><span data-stu-id="ca36a-130">Additional <xref:System.Decimal> rounding functionality.</span></span>
- <span data-ttu-id="ca36a-131">Funcionalidad adicional en la <xref:System.Environment> clase.</span><span class="sxs-lookup"><span data-stu-id="ca36a-131">Additional functionality in the <xref:System.Environment> class.</span></span>
- <span data-ttu-id="ca36a-132">Mejorado control sobre el recolector de elementos no utilizados a través de la <xref:System.GC> clase.</span><span class="sxs-lookup"><span data-stu-id="ca36a-132">Enhanced control over the garbage collector through the <xref:System.GC> class.</span></span>
- <span data-ttu-id="ca36a-133">Compatibilidad mejorada para la comparación de cadenas, la enumeración y la normalización en el <xref:System.String> clase.</span><span class="sxs-lookup"><span data-stu-id="ca36a-133">Enhanced support for string comparison, enumeration, and normalization in the <xref:System.String> class.</span></span>
- <span data-ttu-id="ca36a-134">Soporte técnico para el horario de verano ajustes y tiempos de transición en el <xref:System.TimeZoneInfo.AdjustmentRule> y <xref:System.TimeZoneInfo.TransitionTime> clases.</span><span class="sxs-lookup"><span data-stu-id="ca36a-134">Support for daylight saving adjustments and transition times in the <xref:System.TimeZoneInfo.AdjustmentRule> and <xref:System.TimeZoneInfo.TransitionTime> classes.</span></span>
- <span data-ttu-id="ca36a-135">Mejoran significativamente la funcionalidad en el <xref:System.Type> clase.</span><span class="sxs-lookup"><span data-stu-id="ca36a-135">Significantly enhanced functionality in the <xref:System.Type> class.</span></span>
- <span data-ttu-id="ca36a-136">Mejor compatibilidad para la deserialización de objetos de excepción mediante la adición de un constructor de excepción con <xref:System.Runtime.Serialization.SerializationInfo> y <xref:System.Runtime.Serialization.StreamingContext> parámetros.</span><span class="sxs-lookup"><span data-stu-id="ca36a-136">Better support for deserialization of exception objects by adding an exception constructor with <xref:System.Runtime.Serialization.SerializationInfo> and <xref:System.Runtime.Serialization.StreamingContext> parameters.</span></span>

<span data-ttu-id="ca36a-137">**Compatibilidad con bibliotecas de .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="ca36a-137">**Support for .NET Framework libraries**</span></span>

<span data-ttu-id="ca36a-138">La gran mayoría de las bibliotecas de tener como destino el .NET Framework en lugar de .NET estándar.</span><span class="sxs-lookup"><span data-stu-id="ca36a-138">The overwhelming majority of libraries target the .NET Framework rather than .NET Standard.</span></span> <span data-ttu-id="ca36a-139">Sin embargo, la mayoría de las llamadas de esas bibliotecas es para las API que se incluyen en el estándar de .NET 2.0.</span><span class="sxs-lookup"><span data-stu-id="ca36a-139">However, most of the calls in those libraries are to APIs that are included in the .NET Standard 2.0.</span></span> <span data-ttu-id="ca36a-140">A partir de .NET estándar 2.0, se pueden tener acceso a las bibliotecas de .NET Framework de una biblioteca estándar de .NET mediante el uso de un [schim](https://github.com/dotnet/standard/blob/master/docs/netstandard-20/README.md#assembly-unification).</span><span class="sxs-lookup"><span data-stu-id="ca36a-140">Starting with the .NET Standard 2.0, you can access .NET Framework libraries from a .NET Standard library by using a [compatibility shim](https://github.com/dotnet/standard/blob/master/docs/netstandard-20/README.md#assembly-unification).</span></span> <span data-ttu-id="ca36a-141">Este nivel de compatibilidad es transparente para los desarrolladores; no tienes que hacer nada para aprovechar las ventajas de las bibliotecas de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ca36a-141">This compatibility layer is transparent to developers; you don't have to do anything to take advantage of .NET Framework libraries.</span></span>

<span data-ttu-id="ca36a-142">El único requisito es que las API que se llama a la biblioteca de clases de .NET Framework deben incluirse en el estándar de .NET 2.0.</span><span class="sxs-lookup"><span data-stu-id="ca36a-142">The single requirement is that the APIs called by the .NET Framework class library must be included in the .NET Standard 2.0.</span></span>

<span data-ttu-id="ca36a-143">**Compatibilidad con Visual Basic**</span><span class="sxs-lookup"><span data-stu-id="ca36a-143">**Support for Visual Basic**</span></span>

<span data-ttu-id="ca36a-144">Ahora puede desarrollar bibliotecas estándar de .NET en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ca36a-144">You can now develop .NET Standard libraries in Visual Basic.</span></span> <span data-ttu-id="ca36a-145">Para los desarrolladores de Visual Basic mediante Visual Studio 2017 versión 15.3 o posterior con la carga de trabajo de .NET Core instalado, Visual Studio ahora incluye una plantilla de biblioteca de clases de .NET estándar.</span><span class="sxs-lookup"><span data-stu-id="ca36a-145">For Visual Basic developers using Visual Studio 2017 Version 15.3 or later with the .NET Core workload installed, Visual Studio now includes a .NET Standard Class Library template.</span></span> <span data-ttu-id="ca36a-146">Para los desarrolladores de Visual Basic que utilizan otras herramientas de desarrollo y los entornos, puede usar el [dotnet nueva](../../core/tools/dotnet-new.md) comando para crear un proyecto de biblioteca de .NET estándar.</span><span class="sxs-lookup"><span data-stu-id="ca36a-146">For Visual Basic developers who use other development tools and environments, you can use the [dotnet new](../../core/tools/dotnet-new.md) command to create a .NET Standard Library project.</span></span> <span data-ttu-id="ca36a-147">Para obtener más información, consulte el [compatibilidad con herramientas de bibliotecas estándar de .NET](#tooling).</span><span class="sxs-lookup"><span data-stu-id="ca36a-147">For more information, see the [Tooling support for .NET Standard libraries](#tooling).</span></span>

<span data-ttu-id="ca36a-148"><a name="tooling" />**Compatibilidad con herramientas de bibliotecas estándar de .NET**</span><span class="sxs-lookup"><span data-stu-id="ca36a-148"><a name="tooling" />**Tooling support for .NET Standard libraries**</span></span>

<span data-ttu-id="ca36a-149">Con la versión de .NET Core 2.0 y .NET 2.0 estándar, tanto Visual Studio de 2017 y [.NET Core interfaz de línea de comandos (CLI)](../../core/tools/index.md) incluyen compatibilidad con herramientas de creación de bibliotecas de .NET estándar.</span><span class="sxs-lookup"><span data-stu-id="ca36a-149">With the release of .NET Core 2.0 and .NET Standard 2.0, both Visual Studio 2017 and the [.NET Core Command Line Interface (CLI)](../../core/tools/index.md) include tooling support for creating .NET Standard libraries.</span></span> 

<span data-ttu-id="ca36a-150">Si instala Visual Studio con la **.NET Core el desarrollo multiplataforma** carga de trabajo, puede crear un proyecto de biblioteca estándar de .NET 2.0 mediante el uso de una plantilla de proyecto, como se muestra en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="ca36a-150">If you install Visual Studio with the **.NET Core cross-platform development** workload, you can create a .NET Standard 2.0 library project by using a project template, as the following figure shows.</span></span> 

# <a name="ctabcsharp"></a>[<span data-ttu-id="ca36a-151">C#</span><span class="sxs-lookup"><span data-stu-id="ca36a-151">C#</span></span>](#tab/csharp)
![Agregar proyecto de biblioteca nuevo estándar de .NET](./media/std-project-cs.png)
# <a name="visual-basictabvisual-basic"></a>[<span data-ttu-id="ca36a-153">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ca36a-153">Visual Basic</span></span>](#tab/visual-basic)
<a name="add-new-net-standard-library-projectmediastd-project-vbpng"></a>![Agregar proyecto de biblioteca nuevo estándar de .NET](./media/std-project-vb.png)
---

<span data-ttu-id="ca36a-155">Si está usando la CLI de .NET Core, el siguiente [dotnet nueva](../../core/tools/dotnet-new.md) comando crea un proyecto de biblioteca de clases que tenga como destino el estándar de .NET 2.0.</span><span class="sxs-lookup"><span data-stu-id="ca36a-155">If you are using the .NET Core CLI, the following [dotnet new](../../core/tools/dotnet-new.md) command creates a class library project that targets the .NET Standard 2.0.</span></span>

```csharp
dotnet new classlib
```
```vb
dotnet new classlib -lang vb
```
  
## <a name="see-also"></a><span data-ttu-id="ca36a-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca36a-156">See Also</span></span>
<span data-ttu-id="ca36a-157">[Estándar de .NET](../net-standard.md)
[presentación estándar de .NET](https://blogs.msdn.microsoft.com/dotnet/2016/09/26/introducing-net-standard/)</span><span class="sxs-lookup"><span data-stu-id="ca36a-157">[.NET Standard](../net-standard.md)
[Introducing .NET Standard](https://blogs.msdn.microsoft.com/dotnet/2016/09/26/introducing-net-standard/)</span></span>
