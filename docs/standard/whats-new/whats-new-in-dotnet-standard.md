---
title: Novedades de .NET Standard
description: En este artículo, se resumen las nuevas características y mejoras que se encuentran en cada nueva versión de .NET Standard.
ms.custom: updateeachrelease
ms.date: 04/12/2018
ms.technology: dotnet-standard
ms.openlocfilehash: a90df0360211c3b02f4f2d8697890180099c5807
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2020
ms.locfileid: "76921056"
---
# <a name="whats-new-in-the-net-standard"></a><span data-ttu-id="291bf-103">Novedades de .NET Standard</span><span class="sxs-lookup"><span data-stu-id="291bf-103">What's new in the .NET Standard</span></span>

<span data-ttu-id="291bf-104">.NET Standard es una especificación formal que define un conjunto de API con control de versiones que debe estar disponible en las implementaciones de .NET que cumplen con esa versión del estándar.</span><span class="sxs-lookup"><span data-stu-id="291bf-104">The .NET Standard is a formal specification that defines a versioned set of APIs that must be available on .NET implementations that comply with that version of the standard.</span></span> <span data-ttu-id="291bf-105">.NET Standard está dirigido a los desarrolladores de bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="291bf-105">The .NET Standard is targeted at library developers.</span></span> <span data-ttu-id="291bf-106">Una biblioteca que tenga como destino una versión estándar de .NET Standard se puede usar en cualquier implementación de .NET Framework, .NET Core o Xamarin que admita esa versión del estándar.</span><span class="sxs-lookup"><span data-stu-id="291bf-106">A library that targets a .NET Standard version can be used on any .NET Framework, .NET Core, or Xamarin implementation that supports that version of the standard.</span></span>

<span data-ttu-id="291bf-107">La versión más reciente de .NET Standard es la 2.0.</span><span class="sxs-lookup"><span data-stu-id="291bf-107">The most recent version of the .NET Standard is 2.0.</span></span> <span data-ttu-id="291bf-108">Se incluye con el SDK de .NET Core 2.0, así como con la versión 15.3 de Visual Studio 2017 con la carga de trabajo de .NET Core instalada.</span><span class="sxs-lookup"><span data-stu-id="291bf-108">It is included with the .NET Core 2.0 SDK, as well as with Visual Studio 2017 version 15.3 with the .NET Core workload installed.</span></span>

## <a name="supported-net-implementations"></a><span data-ttu-id="291bf-109">Implementaciones de .NET compatibles</span><span class="sxs-lookup"><span data-stu-id="291bf-109">Supported .NET implementations</span></span>

<span data-ttu-id="291bf-110">.NET Standard 2.0 es compatible con las siguientes implementaciones de .NET:</span><span class="sxs-lookup"><span data-stu-id="291bf-110">The .NET Standard 2.0 is supported by the following .NET implementations:</span></span>

- <span data-ttu-id="291bf-111">.NET Core 2.0 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="291bf-111">.NET Core 2.0 or later</span></span>
- <span data-ttu-id="291bf-112">.NET Framework 4.6.1 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="291bf-112">.NET Framework 4.6.1 or later</span></span>
- <span data-ttu-id="291bf-113">Mono 5.4 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="291bf-113">Mono 5.4 or later</span></span>
- <span data-ttu-id="291bf-114">Xamarin.iOS 10.14 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="291bf-114">Xamarin.iOS 10.14 or later</span></span>
- <span data-ttu-id="291bf-115">Xamarin.Mac 3.8 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="291bf-115">Xamarin.Mac 3.8 or later</span></span>
- <span data-ttu-id="291bf-116">Xamarin.Android 8.0 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="291bf-116">Xamarin.Android 8.0 or later</span></span>
- <span data-ttu-id="291bf-117">Plataforma universal de Windows 10.0.16299 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="291bf-117">Universal Windows Platform 10.0.16299 or later</span></span>

## <a name="whats-new-in-the-net-standard-20"></a><span data-ttu-id="291bf-118">Novedades de .NET Standard 2.0</span><span class="sxs-lookup"><span data-stu-id="291bf-118">What's new in the .NET Standard 2.0</span></span>

<span data-ttu-id="291bf-119">.NET Standard 2.0 incluye las siguientes características nuevas:</span><span class="sxs-lookup"><span data-stu-id="291bf-119">The .NET Standard 2.0 includes the following new features:</span></span>

### <a name="a-vastly-expanded-set-of-apis"></a><span data-ttu-id="291bf-120">Un conjunto de API ampliamente expandido</span><span class="sxs-lookup"><span data-stu-id="291bf-120">A vastly expanded set of APIs</span></span>

<span data-ttu-id="291bf-121">Con la versión 1.6, .NET Standard incluía un subconjunto relativamente pequeño de API.</span><span class="sxs-lookup"><span data-stu-id="291bf-121">Through version 1.6, the .NET Standard included a comparatively small subset of APIs.</span></span> <span data-ttu-id="291bf-122">Entre las excluidas estaban muchas API utilizadas habitualmente en .NET Framework o Xamarin.</span><span class="sxs-lookup"><span data-stu-id="291bf-122">Among those excluded were many APIs that were commonly used in the .NET Framework or Xamarin.</span></span> <span data-ttu-id="291bf-123">Esto complica el desarrollo, ya que los desarrolladores tienen que encontrar sustitutas adecuadas para API familiares para desarrollar aplicaciones y bibliotecas destinadas a varias implementaciones de .NET.</span><span class="sxs-lookup"><span data-stu-id="291bf-123">This complicates development, since it requires that developers find suitable replacements for familiar APIs when they develop applications and libraries that target multiple .NET implementations.</span></span> <span data-ttu-id="291bf-124">.NET Standard 2.0 soluciona esta limitación con la adición de más de 20 000 API que estaban disponibles en .NET Standard 1.6, la versión anterior del estándar.</span><span class="sxs-lookup"><span data-stu-id="291bf-124">The .NET Standard 2.0 addresses this limitation by adding over 20,000 more APIs than were available in .NET Standard 1.6, the previous version of the standard.</span></span> <span data-ttu-id="291bf-125">Si desea consultar una lista de las API agregadas a .NET Standard 2.0, vea [la comparación entre .NET Standard 2.0 y 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span><span class="sxs-lookup"><span data-stu-id="291bf-125">For a list of the APIs that have been added to the .NET Standard 2.0, see [.NET Standard 2.0 vs 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span></span>

<span data-ttu-id="291bf-126">Alguna de las adiciones al espacio de nombres <xref:System> de .NET Standard 2.0 incluyen:</span><span class="sxs-lookup"><span data-stu-id="291bf-126">Some of the additions to the <xref:System> namespace in .NET Standard 2.0 include:</span></span>

- <span data-ttu-id="291bf-127">Compatibilidad con la clase <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="291bf-127">Support for the <xref:System.AppDomain> class.</span></span>
- <span data-ttu-id="291bf-128">Mayor compatibilidad para trabajar con matrices de miembros adicionales en la clase <xref:System.Array>.</span><span class="sxs-lookup"><span data-stu-id="291bf-128">Better support for working with arrays from additional members in the <xref:System.Array> class.</span></span>
- <span data-ttu-id="291bf-129">Mayor compatibilidad para trabajar con atributos de miembros adicionales en la clase <xref:System.Attribute>.</span><span class="sxs-lookup"><span data-stu-id="291bf-129">Better support for working with attributes from additional members in the <xref:System.Attribute> class.</span></span>
- <span data-ttu-id="291bf-130">Mayor compatibilidad del calendario y opciones de formato adicionales para los valores <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="291bf-130">Better calendar support and additional formatting options for <xref:System.DateTime> values.</span></span>
- <span data-ttu-id="291bf-131">Funcionalidad de redondeo <xref:System.Decimal> adicional.</span><span class="sxs-lookup"><span data-stu-id="291bf-131">Additional <xref:System.Decimal> rounding functionality.</span></span>
- <span data-ttu-id="291bf-132">Funcionalidad adicional en la clase <xref:System.Environment>.</span><span class="sxs-lookup"><span data-stu-id="291bf-132">Additional functionality in the <xref:System.Environment> class.</span></span>
- <span data-ttu-id="291bf-133">Control mejorado sobre el recolector de elementos no utilizados en la clase <xref:System.GC>.</span><span class="sxs-lookup"><span data-stu-id="291bf-133">Enhanced control over the garbage collector through the <xref:System.GC> class.</span></span>
- <span data-ttu-id="291bf-134">Compatibilidad mejorada para la comparación de cadenas, la enumeración y la normalización en la clase <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="291bf-134">Enhanced support for string comparison, enumeration, and normalization in the <xref:System.String> class.</span></span>
- <span data-ttu-id="291bf-135">Compatibilidad para los tiempos de transición y los ajustes del horario de verano en las clases <xref:System.TimeZoneInfo.AdjustmentRule> y <xref:System.TimeZoneInfo.TransitionTime>.</span><span class="sxs-lookup"><span data-stu-id="291bf-135">Support for daylight saving adjustments and transition times in the <xref:System.TimeZoneInfo.AdjustmentRule> and <xref:System.TimeZoneInfo.TransitionTime> classes.</span></span>
- <span data-ttu-id="291bf-136">Funcionalidad mejorada significativamente en la clase <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="291bf-136">Significantly enhanced functionality in the <xref:System.Type> class.</span></span>
- <span data-ttu-id="291bf-137">Mejor compatibilidad para la deserialización de objetos de excepción mediante la adición de un constructor de excepción con los parámetros <xref:System.Runtime.Serialization.SerializationInfo> y <xref:System.Runtime.Serialization.StreamingContext>.</span><span class="sxs-lookup"><span data-stu-id="291bf-137">Better support for deserialization of exception objects by adding an exception constructor with <xref:System.Runtime.Serialization.SerializationInfo> and <xref:System.Runtime.Serialization.StreamingContext> parameters.</span></span>

### <a name="support-for-net-framework-libraries"></a><span data-ttu-id="291bf-138">Compatibilidad con las bibliotecas .NET Framework</span><span class="sxs-lookup"><span data-stu-id="291bf-138">Support for .NET Framework libraries</span></span>

<span data-ttu-id="291bf-139">La gran mayoría de las bibliotecas tienen como destino .NET Framework en lugar de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="291bf-139">The overwhelming majority of libraries target the .NET Framework rather than .NET Standard.</span></span> <span data-ttu-id="291bf-140">Sin embargo, la mayoría de las llamadas de esas bibliotecas se realizan a las API incluidas en .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="291bf-140">However, most of the calls in those libraries are to APIs that are included in the .NET Standard 2.0.</span></span> <span data-ttu-id="291bf-141">A partir de .NET Standard 2.0, puede acceder a las bibliotecas de .NET Framework desde una biblioteca de .NET Standard con el uso de una [corrección de compatibilidad](https://github.com/dotnet/standard/blob/master/docs/planning/netstandard-2.0/README.md#assembly-unification).</span><span class="sxs-lookup"><span data-stu-id="291bf-141">Starting with the .NET Standard 2.0, you can access .NET Framework libraries from a .NET Standard library by using a [compatibility shim](https://github.com/dotnet/standard/blob/master/docs/planning/netstandard-2.0/README.md#assembly-unification).</span></span> <span data-ttu-id="291bf-142">Este nivel de compatibilidad es transparente para los desarrolladores; no tiene que hacer nada para aprovechar las ventajas de las bibliotecas de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="291bf-142">This compatibility layer is transparent to developers; you don't have to do anything to take advantage of .NET Framework libraries.</span></span>

<span data-ttu-id="291bf-143">El único requisito es que las API a las que llaman las bibliotecas de clases de .NET Framework estén incluidas en .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="291bf-143">The single requirement is that the APIs called by the .NET Framework class library must be included in the .NET Standard 2.0.</span></span>

### <a name="support-for-visual-basic"></a><span data-ttu-id="291bf-144">Compatibilidad con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="291bf-144">Support for Visual Basic</span></span>

<span data-ttu-id="291bf-145">Ahora puede desarrollar bibliotecas de .NET Standard en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="291bf-145">You can now develop .NET Standard libraries in Visual Basic.</span></span> <span data-ttu-id="291bf-146">Para los desarrolladores de Visual Basic que usan la versión 15.3 de Visual Studio 2017 o posterior con la carga de trabajo de .NET Core instalada, Visual Studio ahora incluye una plantilla de la biblioteca de clases de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="291bf-146">For Visual Basic developers using Visual Studio 2017 version 15.3 or later with the .NET Core workload installed, Visual Studio now includes a .NET Standard Class Library template.</span></span> <span data-ttu-id="291bf-147">Para los desarrolladores de Visual Basic que usan otras herramientas y entornos de desarrollo, puede usar el comando [dotnet new](../../core/tools/dotnet-new.md) para crear un proyecto de biblioteca de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="291bf-147">For Visual Basic developers who use other development tools and environments, you can use the [dotnet new](../../core/tools/dotnet-new.md) command to create a .NET Standard Library project.</span></span> <span data-ttu-id="291bf-148">Para más información, vea [Compatibilidad con herramientas de bibliotecas estándar de .NET](#tooling-support-for-net-standard-libraries).</span><span class="sxs-lookup"><span data-stu-id="291bf-148">For more information, see the [Tooling support for .NET Standard libraries](#tooling-support-for-net-standard-libraries).</span></span>

### <a name="tooling-support-for-net-standard-libraries"></a><span data-ttu-id="291bf-149">Compatibilidad con herramientas de bibliotecas de .NET Standard</span><span class="sxs-lookup"><span data-stu-id="291bf-149">Tooling support for .NET Standard libraries</span></span>

<span data-ttu-id="291bf-150">Con la versión de .NET Core 2.0 y .NET Standard 2.0, Visual Studio 2017 y la [CLI de .NET Core](../../core/tools/index.md) incluyen compatibilidad con herramientas para crear bibliotecas de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="291bf-150">With the release of .NET Core 2.0 and .NET Standard 2.0, both Visual Studio 2017 and the [.NET Core CLI](../../core/tools/index.md) include tooling support for creating .NET Standard libraries.</span></span>

<span data-ttu-id="291bf-151">Si instala Visual Studio con la carga de trabajo de **desarrollo multiplataforma de .NET Core**, puede crear un proyecto de biblioteca de .NET Standard 2.0 al usar una plantilla de proyecto, como se muestra en la ilustración siguiente:</span><span class="sxs-lookup"><span data-stu-id="291bf-151">If you install Visual Studio with the **.NET Core cross-platform development** workload, you can create a .NET Standard 2.0 library project by using a project template, as the following figure shows:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="ctabcsharp"></a>[<span data-ttu-id="291bf-152">C#</span><span class="sxs-lookup"><span data-stu-id="291bf-152">C#</span></span>](#tab/csharp)

![Agregar un proyecto de biblioteca nuevo de .NET Standard](./media/std-project-cs.png)

<span data-ttu-id="291bf-154">Si usa la CLI de .NET Core, el siguiente comando [dotnet new](../../core/tools/dotnet-new.md) crea un proyecto de biblioteca de clases que tenga como destino .NET Standard 2.0:</span><span class="sxs-lookup"><span data-stu-id="291bf-154">If you're using the .NET Core CLI, the following [dotnet new](../../core/tools/dotnet-new.md) command creates a class library project that targets the .NET Standard 2.0:</span></span>

```dotnetcli
dotnet new classlib
```

# <a name="visual-basictabvb"></a>[<span data-ttu-id="291bf-155">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="291bf-155">Visual Basic</span></span>](#tab/vb)

![Agregar un proyecto de biblioteca nuevo de .NET Standard](./media/std-project-vb.png)

<span data-ttu-id="291bf-157">Si usa la CLI de .NET Core, el siguiente comando [dotnet new](../../core/tools/dotnet-new.md) crea un proyecto de biblioteca de clases que tenga como destino .NET Standard 2.0:</span><span class="sxs-lookup"><span data-stu-id="291bf-157">If you're using the .NET Core CLI, the following [dotnet new](../../core/tools/dotnet-new.md) command creates a class library project that targets the .NET Standard 2.0:</span></span>

```dotnetcli
dotnet new classlib -lang vb
```

---

## <a name="see-also"></a><span data-ttu-id="291bf-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="291bf-158">See also</span></span>

- [<span data-ttu-id="291bf-159">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="291bf-159">.NET Standard</span></span>](../net-standard.md)
- <span data-ttu-id="291bf-160">[Introducing .NET Standard](https://devblogs.microsoft.com/dotnet/introducing-net-standard/) (Introducción a .NET Standard)</span><span class="sxs-lookup"><span data-stu-id="291bf-160">[Introducing .NET Standard](https://devblogs.microsoft.com/dotnet/introducing-net-standard/)</span></span>
