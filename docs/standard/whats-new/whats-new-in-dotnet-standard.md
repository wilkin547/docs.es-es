---
title: Novedades de .NET Standard
description: En este artículo, se resumen las nuevas características y mejoras que se encuentran en cada nueva versión de .NET Standard.
ms.custom: updateeachrelease
ms.date: 04/12/2018
ms.technology: dotnet-standard
ms.openlocfilehash: 28d6a3546e08bbc3a7d4a26f08ba9cc5e16a901b
ms.sourcegitcommit: 2ff49dcf9ddf107d139b4055534681052febad62
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2020
ms.locfileid: "80438200"
---
# <a name="whats-new-in-net-standard"></a><span data-ttu-id="9771c-103">Novedades de .NET Standard</span><span class="sxs-lookup"><span data-stu-id="9771c-103">What's new in .NET Standard</span></span>

<span data-ttu-id="9771c-104">.NET Standard es una especificación formal que define un conjunto de API con control de versiones que debe estar disponible en las implementaciones de .NET que cumplen con esa versión del estándar.</span><span class="sxs-lookup"><span data-stu-id="9771c-104">.NET Standard is a formal specification that defines a versioned set of APIs that must be available on .NET implementations that comply with that version of the standard.</span></span> <span data-ttu-id="9771c-105">.NET Standard está dirigido a los desarrolladores de bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="9771c-105">.NET Standard is targeted at library developers.</span></span> <span data-ttu-id="9771c-106">Una biblioteca que tenga como destino una versión estándar de .NET Standard se puede usar en cualquier implementación de .NET Framework, .NET Core o Xamarin que admita esa versión del estándar.</span><span class="sxs-lookup"><span data-stu-id="9771c-106">A library that targets a .NET Standard version can be used on any .NET Framework, .NET Core, or Xamarin implementation that supports that version of the standard.</span></span>

<span data-ttu-id="9771c-107">.NET Standard se incluye con el SDK de .NET Core, así como con Visual Studio cuando se selecciona la carga de trabajo de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9771c-107">.NET Standard is included with the .NET Core SDK, as well as with Visual Studio when you select the .NET Core workload.</span></span>

## <a name="supported-net-implementations"></a><span data-ttu-id="9771c-108">Implementaciones de .NET compatibles</span><span class="sxs-lookup"><span data-stu-id="9771c-108">Supported .NET implementations</span></span>

<span data-ttu-id="9771c-109">.NET Standard 2.0 es compatible con las implementaciones siguientes de .NET:</span><span class="sxs-lookup"><span data-stu-id="9771c-109">.NET Standard 2.0 is supported by the following .NET implementations:</span></span>

- <span data-ttu-id="9771c-110">.NET Core 2.0 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="9771c-110">.NET Core 2.0 or later</span></span>
- <span data-ttu-id="9771c-111">.NET Framework 4.6.1 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="9771c-111">.NET Framework 4.6.1 or later</span></span>
- <span data-ttu-id="9771c-112">Mono 5.4 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="9771c-112">Mono 5.4 or later</span></span>
- <span data-ttu-id="9771c-113">Xamarin.iOS 10.14 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="9771c-113">Xamarin.iOS 10.14 or later</span></span>
- <span data-ttu-id="9771c-114">Xamarin.Mac 3.8 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="9771c-114">Xamarin.Mac 3.8 or later</span></span>
- <span data-ttu-id="9771c-115">Xamarin.Android 8.0 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="9771c-115">Xamarin.Android 8.0 or later</span></span>
- <span data-ttu-id="9771c-116">Plataforma universal de Windows 10.0.16299 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="9771c-116">Universal Windows Platform 10.0.16299 or later</span></span>

## <a name="whats-new-in-net-standard-20"></a><span data-ttu-id="9771c-117">Novedades de .NET Standard 2.0</span><span class="sxs-lookup"><span data-stu-id="9771c-117">What's new in .NET Standard 2.0</span></span>

<span data-ttu-id="9771c-118">.NET Standard 2.0 incluye las siguientes características nuevas:</span><span class="sxs-lookup"><span data-stu-id="9771c-118">.NET Standard 2.0 includes the following new features:</span></span>

### <a name="a-vastly-expanded-set-of-apis"></a><span data-ttu-id="9771c-119">Un conjunto de API ampliamente expandido</span><span class="sxs-lookup"><span data-stu-id="9771c-119">A vastly expanded set of APIs</span></span>

<span data-ttu-id="9771c-120">Con la versión 1.6, .NET Standard incluía un subconjunto relativamente pequeño de API.</span><span class="sxs-lookup"><span data-stu-id="9771c-120">Through version 1.6, .NET Standard included a comparatively small subset of APIs.</span></span> <span data-ttu-id="9771c-121">Entre las excluidas estaban muchas API utilizadas habitualmente en .NET Framework o Xamarin.</span><span class="sxs-lookup"><span data-stu-id="9771c-121">Among those excluded were many APIs that were commonly used in the .NET Framework or Xamarin.</span></span> <span data-ttu-id="9771c-122">Esto complica el desarrollo, ya que los desarrolladores tienen que encontrar sustitutas adecuadas para API familiares para desarrollar aplicaciones y bibliotecas destinadas a varias implementaciones de .NET.</span><span class="sxs-lookup"><span data-stu-id="9771c-122">This complicates development, since it requires that developers find suitable replacements for familiar APIs when they develop applications and libraries that target multiple .NET implementations.</span></span> <span data-ttu-id="9771c-123">.NET Standard 2.0 soluciona esta limitación con la incorporación de más de 20 000 API más de las que estaban disponibles en .NET Standard 1.6, la versión anterior del estándar.</span><span class="sxs-lookup"><span data-stu-id="9771c-123">.NET Standard 2.0 addresses this limitation by adding over 20,000 more APIs than were available in .NET Standard 1.6, the previous version of the standard.</span></span> <span data-ttu-id="9771c-124">Si quiere obtener una lista de las API agregadas a .NET Standard 2.0, vea [comparación entre .NET Standard 2.0 y 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span><span class="sxs-lookup"><span data-stu-id="9771c-124">For a list of the APIs that have been added to .NET Standard 2.0, see [.NET Standard 2.0 vs 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span></span>

<span data-ttu-id="9771c-125">Alguna de las adiciones al espacio de nombres <xref:System> de .NET Standard 2.0 incluyen:</span><span class="sxs-lookup"><span data-stu-id="9771c-125">Some of the additions to the <xref:System> namespace in .NET Standard 2.0 include:</span></span>

- <span data-ttu-id="9771c-126">Compatibilidad con la clase <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="9771c-126">Support for the <xref:System.AppDomain> class.</span></span>
- <span data-ttu-id="9771c-127">Mayor compatibilidad para trabajar con matrices de miembros adicionales en la clase <xref:System.Array>.</span><span class="sxs-lookup"><span data-stu-id="9771c-127">Better support for working with arrays from additional members in the <xref:System.Array> class.</span></span>
- <span data-ttu-id="9771c-128">Mayor compatibilidad para trabajar con atributos de miembros adicionales en la clase <xref:System.Attribute>.</span><span class="sxs-lookup"><span data-stu-id="9771c-128">Better support for working with attributes from additional members in the <xref:System.Attribute> class.</span></span>
- <span data-ttu-id="9771c-129">Mayor compatibilidad del calendario y opciones de formato adicionales para los valores <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="9771c-129">Better calendar support and additional formatting options for <xref:System.DateTime> values.</span></span>
- <span data-ttu-id="9771c-130">Funcionalidad de redondeo <xref:System.Decimal> adicional.</span><span class="sxs-lookup"><span data-stu-id="9771c-130">Additional <xref:System.Decimal> rounding functionality.</span></span>
- <span data-ttu-id="9771c-131">Funcionalidad adicional en la clase <xref:System.Environment>.</span><span class="sxs-lookup"><span data-stu-id="9771c-131">Additional functionality in the <xref:System.Environment> class.</span></span>
- <span data-ttu-id="9771c-132">Control mejorado sobre el recolector de elementos no utilizados en la clase <xref:System.GC>.</span><span class="sxs-lookup"><span data-stu-id="9771c-132">Enhanced control over the garbage collector through the <xref:System.GC> class.</span></span>
- <span data-ttu-id="9771c-133">Compatibilidad mejorada para la comparación de cadenas, la enumeración y la normalización en la clase <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="9771c-133">Enhanced support for string comparison, enumeration, and normalization in the <xref:System.String> class.</span></span>
- <span data-ttu-id="9771c-134">Compatibilidad para los tiempos de transición y los ajustes del horario de verano en las clases <xref:System.TimeZoneInfo.AdjustmentRule> y <xref:System.TimeZoneInfo.TransitionTime>.</span><span class="sxs-lookup"><span data-stu-id="9771c-134">Support for daylight saving adjustments and transition times in the <xref:System.TimeZoneInfo.AdjustmentRule> and <xref:System.TimeZoneInfo.TransitionTime> classes.</span></span>
- <span data-ttu-id="9771c-135">Funcionalidad mejorada significativamente en la clase <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="9771c-135">Significantly enhanced functionality in the <xref:System.Type> class.</span></span>
- <span data-ttu-id="9771c-136">Mejor compatibilidad para la deserialización de objetos de excepción mediante la adición de un constructor de excepción con los parámetros <xref:System.Runtime.Serialization.SerializationInfo> y <xref:System.Runtime.Serialization.StreamingContext>.</span><span class="sxs-lookup"><span data-stu-id="9771c-136">Better support for deserialization of exception objects by adding an exception constructor with <xref:System.Runtime.Serialization.SerializationInfo> and <xref:System.Runtime.Serialization.StreamingContext> parameters.</span></span>

### <a name="support-for-net-framework-libraries"></a><span data-ttu-id="9771c-137">Compatibilidad con las bibliotecas .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9771c-137">Support for .NET Framework libraries</span></span>

<span data-ttu-id="9771c-138">La gran mayoría de las bibliotecas tienen como destino .NET Framework en lugar de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="9771c-138">The overwhelming majority of libraries target .NET Framework rather than .NET Standard.</span></span> <span data-ttu-id="9771c-139">Sin embargo, la mayoría de las llamadas de esas bibliotecas se realizan a las API incluidas en .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="9771c-139">However, most of the calls in those libraries are to APIs that are included in .NET Standard 2.0.</span></span> <span data-ttu-id="9771c-140">A partir de .NET Standard 2.0, puede acceder a las bibliotecas de .NET Framework desde una biblioteca de .NET Standard usando una [corrección de compatibilidad](https://github.com/dotnet/standard/blob/master/docs/planning/netstandard-2.0/README.md#assembly-unification).</span><span class="sxs-lookup"><span data-stu-id="9771c-140">Starting with .NET Standard 2.0, you can access .NET Framework libraries from a .NET Standard library by using a [compatibility shim](https://github.com/dotnet/standard/blob/master/docs/planning/netstandard-2.0/README.md#assembly-unification).</span></span> <span data-ttu-id="9771c-141">Este nivel de compatibilidad es transparente para los desarrolladores; no tiene que hacer nada para aprovechar las ventajas de las bibliotecas de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9771c-141">This compatibility layer is transparent to developers; you don't have to do anything to take advantage of .NET Framework libraries.</span></span>

<span data-ttu-id="9771c-142">El único requisito es que las API a las que llaman las bibliotecas de clases .NET Framework estén incluidas en .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="9771c-142">The single requirement is that the APIs called by the .NET Framework class library must be included in .NET Standard 2.0.</span></span>

### <a name="support-for-visual-basic"></a><span data-ttu-id="9771c-143">Compatibilidad con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9771c-143">Support for Visual Basic</span></span>

<span data-ttu-id="9771c-144">Ahora puede desarrollar bibliotecas de .NET Standard en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9771c-144">You can now develop .NET Standard libraries in Visual Basic.</span></span> <span data-ttu-id="9771c-145">Visual Studio 2019 y Visual Studio 2017, versión 15.3 o una posterior con la carga de trabajo de .NET Core instalada, incluyen una plantilla de la biblioteca de clases .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="9771c-145">Visual Studio 2019 and Visual Studio 2017 version 15.3 or later with the .NET Core workload installed include a .NET Standard Class Library template.</span></span> <span data-ttu-id="9771c-146">Para los desarrolladores de Visual Basic que usan otras herramientas y entornos de desarrollo, puede usar el comando [dotnet new](../../core/tools/dotnet-new.md) para crear un proyecto de biblioteca de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="9771c-146">For Visual Basic developers who use other development tools and environments, you can use the [dotnet new](../../core/tools/dotnet-new.md) command to create a .NET Standard Library project.</span></span> <span data-ttu-id="9771c-147">Para más información, vea [Compatibilidad con herramientas de bibliotecas estándar de .NET](#tooling-support-for-net-standard-libraries).</span><span class="sxs-lookup"><span data-stu-id="9771c-147">For more information, see the [Tooling support for .NET Standard libraries](#tooling-support-for-net-standard-libraries).</span></span>

### <a name="tooling-support-for-net-standard-libraries"></a><span data-ttu-id="9771c-148">Compatibilidad con herramientas de bibliotecas de .NET Standard</span><span class="sxs-lookup"><span data-stu-id="9771c-148">Tooling support for .NET Standard libraries</span></span>

<span data-ttu-id="9771c-149">Con la versión de .NET Core 2.0 y .NET Standard 2.0, Visual Studio 2017 y la [CLI de .NET Core](../../core/tools/index.md) incluyen compatibilidad con herramientas para crear bibliotecas de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="9771c-149">With the release of .NET Core 2.0 and .NET Standard 2.0, both Visual Studio 2017 and the [.NET Core CLI](../../core/tools/index.md) include tooling support for creating .NET Standard libraries.</span></span>

<span data-ttu-id="9771c-150">Si instala Visual Studio con la carga de trabajo de **desarrollo multiplataforma de .NET Core**, puede crear un proyecto de biblioteca de .NET Standard 2.0 al usar una plantilla de proyecto, como se muestra en la ilustración siguiente:</span><span class="sxs-lookup"><span data-stu-id="9771c-150">If you install Visual Studio with the **.NET Core cross-platform development** workload, you can create a .NET Standard 2.0 library project by using a project template, as the following figure shows:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="c"></a>[<span data-ttu-id="9771c-151">C#</span><span class="sxs-lookup"><span data-stu-id="9771c-151">C#</span></span>](#tab/csharp)

![Agregar un proyecto de biblioteca nuevo de .NET Standard](./media/std-project-cs.png)

<span data-ttu-id="9771c-153">Si usa la CLI de .NET Core, el comando [dotnet new](../../core/tools/dotnet-new.md) siguiente crea un proyecto de biblioteca de clases que tiene como destino .NET Standard 2.0:</span><span class="sxs-lookup"><span data-stu-id="9771c-153">If you're using the .NET Core CLI, the following [dotnet new](../../core/tools/dotnet-new.md) command creates a class library project that targets .NET Standard 2.0:</span></span>

```dotnetcli
dotnet new classlib
```

# <a name="visual-basic"></a>[<span data-ttu-id="9771c-154">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9771c-154">Visual Basic</span></span>](#tab/vb)

![Agregar un proyecto de biblioteca nuevo de .NET Standard](./media/std-project-vb.png)

<span data-ttu-id="9771c-156">Si usa la CLI de .NET Core, el comando [dotnet new](../../core/tools/dotnet-new.md) siguiente crea un proyecto de biblioteca de clases que tiene como destino .NET Standard 2.0:</span><span class="sxs-lookup"><span data-stu-id="9771c-156">If you're using the .NET Core CLI, the following [dotnet new](../../core/tools/dotnet-new.md) command creates a class library project that targets .NET Standard 2.0:</span></span>

```dotnetcli
dotnet new classlib -lang vb
```

---

## <a name="see-also"></a><span data-ttu-id="9771c-157">Vea también</span><span class="sxs-lookup"><span data-stu-id="9771c-157">See also</span></span>

- [<span data-ttu-id="9771c-158">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="9771c-158">.NET Standard</span></span>](../net-standard.md)
- <span data-ttu-id="9771c-159">[Introducing .NET Standard](https://devblogs.microsoft.com/dotnet/introducing-net-standard/) (Introducción a .NET Standard)</span><span class="sxs-lookup"><span data-stu-id="9771c-159">[Introducing .NET Standard](https://devblogs.microsoft.com/dotnet/introducing-net-standard/)</span></span>
