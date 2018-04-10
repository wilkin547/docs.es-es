---
title: Novedades de C# - Guía de C#
description: Cómo evoluciona el lenguaje C#
keywords: C#, Características más recientes, Novedades, Roslyn
author: BillWagner
ms.author: wiwagn
ms.date: 11/13/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 77deec51-a14d-46d4-9bb3-faf449477149
ms.openlocfilehash: 719fbe826b0b115b19067dbaf0d04f14e6534890
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="whats-new-in-c"></a><span data-ttu-id="db06c-104">Novedades de C#</span><span class="sxs-lookup"><span data-stu-id="db06c-104">What's new in C#</span></span> #

<span data-ttu-id="db06c-105">En esta página se brinda una guía básica de las características nueva de cada versión importante del lenguaje C#.</span><span class="sxs-lookup"><span data-stu-id="db06c-105">This page provides a roadmap of new features in each major release of the C# language.</span></span> <span data-ttu-id="db06c-106">Los vínculos siguientes proporcionan información detallada sobre las características principales que se agregaron en cada versión.</span><span class="sxs-lookup"><span data-stu-id="db06c-106">The following links provide detailed information on the major features added in each release.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="db06c-107">El lenguaje C# se basa en tipos y métodos de una *biblioteca estándar* para algunas de las características.</span><span class="sxs-lookup"><span data-stu-id="db06c-107">The C# language relies on types and methods in a *standard library* for some of the features.</span></span> <span data-ttu-id="db06c-108">Un ejemplo es el procesamiento de excepciones.</span><span class="sxs-lookup"><span data-stu-id="db06c-108">One example is exception processing.</span></span> <span data-ttu-id="db06c-109">Cada expresión o instrucción `throw` se comprueba para asegurarse de que el objeto que se genera deriva de <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="db06c-109">Every `throw` statement or expression is checked to ensure the object being thrown is derived from <xref:System.Exception>.</span></span> <span data-ttu-id="db06c-110">Del mismo modo, cada `catch` se comprueba para asegurarse de que el tipo que se captura deriva de <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="db06c-110">Similarly, every `catch` is checked to ensure that the type being caught is derived from <xref:System.Exception>.</span></span> <span data-ttu-id="db06c-111">Cada versión puede agregar requisitos nuevos.</span><span class="sxs-lookup"><span data-stu-id="db06c-111">Each version may add new requirements.</span></span> <span data-ttu-id="db06c-112">Para usar las características más recientes del lenguaje en entornos anteriores, es posible que tenga que instalar bibliotecas específicas.</span><span class="sxs-lookup"><span data-stu-id="db06c-112">To use the latest language features in older environments, you may need to install specific libraries.</span></span> <span data-ttu-id="db06c-113">Estas dependencias están documentadas en la página de cada versión específica.</span><span class="sxs-lookup"><span data-stu-id="db06c-113">These dependencies are documented in the page for each specific version.</span></span> <span data-ttu-id="db06c-114">Puede obtener más información sobre las [relaciones entre lenguaje y biblioteca](relationships-between-language-and-library.md) para tener más antecedentes sobre esta dependencia.</span><span class="sxs-lookup"><span data-stu-id="db06c-114">You can learn more about the [relationships between language and library](relationships-between-language-and-library.md) for background on this dependency.</span></span> 


* <span data-ttu-id="db06c-115">[C# 7.2](csharp-7-2.md):</span><span class="sxs-lookup"><span data-stu-id="db06c-115">[C# 7.2](csharp-7-2.md):</span></span>
    - <span data-ttu-id="db06c-116">En esta página se describen las características más recientes del lenguaje C#.</span><span class="sxs-lookup"><span data-stu-id="db06c-116">This page describes the latest features in the C# language.</span></span> <span data-ttu-id="db06c-117">C# 7.2 se encuentra disponible actualmente en la [versión 15.5 de Visual Studio 2017](https://www.visualstudio.com/vs/whatsnew/) y en el [SDK de .NET Core 2.0](../../core/whats-new/index.md).</span><span class="sxs-lookup"><span data-stu-id="db06c-117">C# 7.2 is currently available in [Visual Studio 2017 version 15.5](https://www.visualstudio.com/vs/whatsnew/), and in the [.NET Core 2.0 SDK](../../core/whats-new/index.md).</span></span>

* <span data-ttu-id="db06c-118">[C# 7.1](csharp-7-1.md):</span><span class="sxs-lookup"><span data-stu-id="db06c-118">[C# 7.1](csharp-7-1.md):</span></span>
    - <span data-ttu-id="db06c-119">En esta página se describen las características de C# 7.1.</span><span class="sxs-lookup"><span data-stu-id="db06c-119">This page describes the features in C# 7.1.</span></span> <span data-ttu-id="db06c-120">Estas características se agregaron en la [versión 15.3 de Visual Studio 2017](https://www.visualstudio.com/vs/whatsnew/) y en el [SDK de .NET Core 2.0](../../core/whats-new/index.md).</span><span class="sxs-lookup"><span data-stu-id="db06c-120">These features were added in [Visual Studio 2017 version 15.3](https://www.visualstudio.com/vs/whatsnew/), and in the [.NET Core 2.0 SDK](../../core/whats-new/index.md).</span></span>

* <span data-ttu-id="db06c-121">[C# 7](csharp-7.md):</span><span class="sxs-lookup"><span data-stu-id="db06c-121">[C# 7](csharp-7.md):</span></span>
    - <span data-ttu-id="db06c-122">En esta página se describen las características que se han agregado en C# 7.</span><span class="sxs-lookup"><span data-stu-id="db06c-122">This page describes the features added in C# 7.</span></span> <span data-ttu-id="db06c-123">Estas características se agregaron a [Visual Studio 2017](https://www.visualstudio.com/vs/whatsnew/) y [.NET Core 1.0](../../core/whats-new/index.md) y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="db06c-123">These features were added in [Visual Studio 2017](https://www.visualstudio.com/vs/whatsnew/) and [.NET Core 1.0](../../core/whats-new/index.md) and later</span></span>
     
* <span data-ttu-id="db06c-124">[C# 6](csharp-6.md):</span><span class="sxs-lookup"><span data-stu-id="db06c-124">[C# 6](csharp-6.md):</span></span>
    - <span data-ttu-id="db06c-125">En esta página se describen las características que se agregaron en C# 6.</span><span class="sxs-lookup"><span data-stu-id="db06c-125">This page describes the features that were added in C# 6.</span></span> <span data-ttu-id="db06c-126">Estas características están disponibles en Visual Studio 2015 para desarrolladores de Windows y en .NET Core 1.0 para desarrolladores que exploran C# en macOS y Linux.</span><span class="sxs-lookup"><span data-stu-id="db06c-126">These features are available in Visual Studio 2015 for Windows developers, and on .NET Core 1.0 for developers exploring C# on macOS and Linux.</span></span>

<!--* [C# Interactive](../interactive/index.md): 
    - This page describes C# Interactive, an interactive Read Eval Print Loop (REPL) that you can use to explore the C# language. You can use it to write code interactively and see it execute immediately, without any compile or build step.
-->
* <span data-ttu-id="db06c-127">[Compatibilidad multiplataforma](../../core/index.md):</span><span class="sxs-lookup"><span data-stu-id="db06c-127">[Cross Platform Support](../../core/index.md):</span></span>
    - <span data-ttu-id="db06c-128">C#, mediante la compatibilidad con .NET Core, se ejecuta en varias plataformas.</span><span class="sxs-lookup"><span data-stu-id="db06c-128">C#, through .NET Core support, runs on multiple platforms.</span></span> <span data-ttu-id="db06c-129">Si está interesado en probar C# en macOS o en alguna de las muchas distribuciones de Linux compatibles, puede obtener más información sobre .NET Core.</span><span class="sxs-lookup"><span data-stu-id="db06c-129">If you are interested in trying C# on macOS, or on one of the many supported Linux distributions, learn more about .NET Core.</span></span>

<!--
- [.NET Compiler Platform SDK](../roslyn/index.md):
    - The .NET Compiler Platform SDK enables you to write code that performs static analysis on C# code. You can use these APIs to find potential errors, or bad practices, suggest fixes, and even implement those fixes.
-->
  
## <a name="previous-versions"></a><span data-ttu-id="db06c-130">Versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="db06c-130">Previous Versions</span></span>
<span data-ttu-id="db06c-131">A continuación se enumeran las características clave que se presentaron en versiones anteriores del lenguaje C# y Visual Studio .NET.</span><span class="sxs-lookup"><span data-stu-id="db06c-131">The following lists key features that were introduced in previous versions of the C# language and Visual Studio .NET.</span></span>  
  
 * <span data-ttu-id="db06c-132">Visual Studio .NET 2013:</span><span class="sxs-lookup"><span data-stu-id="db06c-132">Visual Studio .NET 2013:</span></span> 
     - <span data-ttu-id="db06c-133">En esta versión de Visual Studio se incluyen correcciones de errores, mejoras de rendimiento y vistas previas de tecnología de .NET Compiler Platform (“Roslyn”), que pasó a ser el <!--Link to ../roslyn/index.md-->SDK de la plataforma de compilación .NET.</span><span class="sxs-lookup"><span data-stu-id="db06c-133">This version of Visual Studio included bug fixes, performance improvements, and technology previews of .NET Compiler Platform ("Roslyn") which became the .NET Compiler Platform SDK<!--Link to ../roslyn/index.md-->.</span></span>

 * <span data-ttu-id="db06c-134">C# 5, Visual Studio .NET 2012:</span><span class="sxs-lookup"><span data-stu-id="db06c-134">C# 5, Visual Studio .NET 2012:</span></span> 
     - <span data-ttu-id="db06c-135">Atributos `Async` / `await` e [información del llamador](../programming-guide/concepts/caller-information.md).</span><span class="sxs-lookup"><span data-stu-id="db06c-135">`Async` / `await`, and [caller information](../programming-guide/concepts/caller-information.md) attributes.</span></span>

 * <span data-ttu-id="db06c-136">C# 4, Visual Studio .NET 2010:</span><span class="sxs-lookup"><span data-stu-id="db06c-136">C# 4, Visual Studio .NET 2010:</span></span> 
     - <span data-ttu-id="db06c-137">`Dynamic`, [argumentos con nombre](../programming-guide/classes-and-structs/named-and-optional-arguments.md), parámetros opcionales y [covarianza y contravariancia](../programming-guide/concepts/covariance-contravariance/index.md) genéricas.</span><span class="sxs-lookup"><span data-stu-id="db06c-137">`Dynamic`, [named arguments](../programming-guide/classes-and-structs/named-and-optional-arguments.md), optional parameters, and generic [covariance and contra variance](../programming-guide/concepts/covariance-contravariance/index.md).</span></span>

 * <span data-ttu-id="db06c-138">C# 3, Visual Studio .NET 2008:</span><span class="sxs-lookup"><span data-stu-id="db06c-138">C# 3, Visual Studio .NET 2008:</span></span> 
     - <span data-ttu-id="db06c-139">Inicializadores de objeto y colección, expresiones lambda, métodos de extensión, tipos anónimos, propiedades automáticas, inferencia de tipo `var` local y [Language Integrated Query (LINQ)](../programming-guide/concepts/linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="db06c-139">Object and collection initializers, lambda expressions, extension methods, anonymous types, automatic properties, local `var` type inference, and [Language Integrated Query (LINQ)](../programming-guide/concepts/linq/index.md).</span></span>

 * <span data-ttu-id="db06c-140">C# 2, Visual Studio .NET 2005:</span><span class="sxs-lookup"><span data-stu-id="db06c-140">C# 2, Visual Studio .NET 2005:</span></span> 
     - <span data-ttu-id="db06c-141">Métodos anónimos, genéricos, tipos que aceptan valores NULL, iteradores/rendimiento, clases `static`, covarianza y contravarianza para delegados.</span><span class="sxs-lookup"><span data-stu-id="db06c-141">Anonymous methods, generics, nullable types, iterators/yield, `static` classes, and covariance and contra variance for delegates.</span></span>

 * <span data-ttu-id="db06c-142">C# 1.1, Visual Studio .NET 2003:</span><span class="sxs-lookup"><span data-stu-id="db06c-142">C# 1.1, Visual Studio .NET 2003:</span></span> 
     - <span data-ttu-id="db06c-143">Pragma `#line` y comentarios de documentos xml.</span><span class="sxs-lookup"><span data-stu-id="db06c-143">`#line` pragma and xml doc comments.</span></span>

 * <span data-ttu-id="db06c-144">C# 1, Visual Studio .NET 2002:</span><span class="sxs-lookup"><span data-stu-id="db06c-144">C# 1, Visual Studio .NET 2002:</span></span> 
     - <span data-ttu-id="db06c-145">La primera versión de [C#](../csharp.md).</span><span class="sxs-lookup"><span data-stu-id="db06c-145">The first release of [C#](../csharp.md).</span></span>   
