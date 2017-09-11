---
title: "Novedades de C# - Guía de C#"
description: "Cómo evoluciona el lenguaje C#"
keywords: "C#, Características más recientes, Novedades, Roslyn"
author: BillWagner
ms.author: wiwagn
ms.date: 03/21/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 77deec51-a14d-46d4-9bb3-faf449477149
ms.translationtype: HT
ms.sourcegitcommit: df0438dd742db802bb0f935d840006236d5d9bf9
ms.openlocfilehash: 0a328f62a02aea223340fcc00e839e841041a7d6
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---

# <a name="whats-new-in-c"></a><span data-ttu-id="194c6-104">Novedades de C#</span><span class="sxs-lookup"><span data-stu-id="194c6-104">What's new in C#</span></span> #

<span data-ttu-id="194c6-105">En esta página se brinda una guía básica de las características nueva de cada versión importante del lenguaje C#.</span><span class="sxs-lookup"><span data-stu-id="194c6-105">This page provides a roadmap of new features in each major release of the C# language.</span></span> <span data-ttu-id="194c6-106">Los vínculos a continuación proporcionan información detallada sobre las características principales que se agregaron en cada versión.</span><span class="sxs-lookup"><span data-stu-id="194c6-106">The links below provide detailed information on the major features added in each release.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="194c6-107">El lenguaje C# se basa en tipos y métodos de una *biblioteca estándar* para algunas de las características.</span><span class="sxs-lookup"><span data-stu-id="194c6-107">The C# language relies on types and methods in a *standard library* for some of the features.</span></span> <span data-ttu-id="194c6-108">Un ejemplo es el procesamiento de excepciones.</span><span class="sxs-lookup"><span data-stu-id="194c6-108">One example is exception processing.</span></span> <span data-ttu-id="194c6-109">Cada expresión o instrucción `throw` se comprueba para asegurarse de que el objeto que se genera deriva de @System.Exception.</span><span class="sxs-lookup"><span data-stu-id="194c6-109">Every `throw` statement or expression is checked to ensure the object being thrown is derived from @System.Exception.</span></span> <span data-ttu-id="194c6-110">Del mismo modo, cada `catch` se comprueba para asegurarse de que el tipo que se captura deriva de @System.Exception.</span><span class="sxs-lookup"><span data-stu-id="194c6-110">Similarly, every `catch` is checked to ensure that the type being caught is derived from @System.Exception.</span></span> <span data-ttu-id="194c6-111">Cada versión puede agregar requisitos nuevos.</span><span class="sxs-lookup"><span data-stu-id="194c6-111">Each version may add new requirements.</span></span> <span data-ttu-id="194c6-112">Para usar las características más recientes del lenguaje en entornos anteriores, es posible que tenga que instalar bibliotecas específicas.</span><span class="sxs-lookup"><span data-stu-id="194c6-112">To use the latest language features in older environments, you may need to install specific libraries.</span></span> <span data-ttu-id="194c6-113">Estas están documentadas en la página de cada versión específica.</span><span class="sxs-lookup"><span data-stu-id="194c6-113">These are documented in the page for each specific version.</span></span> <span data-ttu-id="194c6-114">Puede obtener más información sobre las [relaciones entre lenguaje y biblioteca](relationships-between-language-and-library.md) para tener más antecedentes sobre esta dependencia.</span><span class="sxs-lookup"><span data-stu-id="194c6-114">You can learn more about the [relationships between language and library](relationships-between-language-and-library.md) for background on this dependency.</span></span> 

* <span data-ttu-id="194c6-115">[C# 7.1](csharp-7-1.md):</span><span class="sxs-lookup"><span data-stu-id="194c6-115">[C# 7.1](csharp-7-1.md):</span></span>
    - <span data-ttu-id="194c6-116">En esta página se describen las características más recientes del lenguaje C#.</span><span class="sxs-lookup"><span data-stu-id="194c6-116">This page describes the latest features in the C# language.</span></span> <span data-ttu-id="194c6-117">En esta sección se trata C# 7.1, disponible actualmente en la [versión 15.3 de Visual Studio 2017](https://www.visualstudio.com/vs/whatsnew/) y el [SDK de .NET Core 2.0](../../core/whats-new/index.md).</span><span class="sxs-lookup"><span data-stu-id="194c6-117">This covers C# 7.1, currently available in [Visual Studio 2017 version 15.3](https://www.visualstudio.com/vs/whatsnew/), and in the [.NET Core 2.0 SDK](../../core/whats-new/index.md).</span></span>

* <span data-ttu-id="194c6-118">[C# 7](csharp-7.md):</span><span class="sxs-lookup"><span data-stu-id="194c6-118">[C# 7](csharp-7.md):</span></span>
    - <span data-ttu-id="194c6-119">En esta página se describen las características que se han agregado en C# 7.</span><span class="sxs-lookup"><span data-stu-id="194c6-119">This page describes the features added in C# 7.</span></span> <span data-ttu-id="194c6-120">Esto es lo que se ha incorporado a [Visual Studio 2017](https://www.visualstudio.com/vs/whatsnew/) y [.NET Core 1.0](../../core/whats-new/index.md) o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="194c6-120">Theses were added in [Visual Studio 2017](https://www.visualstudio.com/vs/whatsnew/) and [.NET Core 1.0](../../core/whats-new/index.md) and later</span></span>
     
* <span data-ttu-id="194c6-121">[C# 6](csharp-6.md):</span><span class="sxs-lookup"><span data-stu-id="194c6-121">[C# 6](csharp-6.md):</span></span>
    - <span data-ttu-id="194c6-122">En esta página se describen las características que se agregaron en C# 6.</span><span class="sxs-lookup"><span data-stu-id="194c6-122">This page describes the features that were added in C# 6.</span></span> <span data-ttu-id="194c6-123">Estas características están disponibles en Visual Studio 2015 para desarrolladores de Windows y en .NET Core 1.0 para desarrolladores que exploran C# en macOS y Linux.</span><span class="sxs-lookup"><span data-stu-id="194c6-123">These features are available in Visual Studio 2015 for Windows developers, and on .NET Core 1.0 for developers exploring C# on macOS and Linux.</span></span>

<!--* [C# Interactive](../interactive/index.md): 
    - This page describes C# Interactive, an interactive Read Eval Print Loop (REPL) that you can use to explore the C# language. You can use it to write code interactively and see it execute immediately, without any compile or build step.
-->
* <span data-ttu-id="194c6-124">[Compatibilidad multiplataforma](../../core/index.md):</span><span class="sxs-lookup"><span data-stu-id="194c6-124">[Cross Platform Support](../../core/index.md):</span></span>
    - <span data-ttu-id="194c6-125">C#, mediante la compatibilidad con .NET Core, se ejecuta en varias plataformas.</span><span class="sxs-lookup"><span data-stu-id="194c6-125">C#, through .NET Core support, runs on multiple platforms.</span></span> <span data-ttu-id="194c6-126">Si está interesado en probar C# en macOS o en alguna de las muchas distribuciones de Linux compatibles, puede obtener más información sobre .NET Core.</span><span class="sxs-lookup"><span data-stu-id="194c6-126">If you are interested in trying C# on macOS, or on one of the many supported Linux distributions, learn more about .NET Core.</span></span>

<!--
- [.NET Compiler Platform SDK](../roslyn/index.md):
    - The .NET Compiler Platform SDK enables you to write code that performs static analysis on C# code. You can use these APIs to find potential errors, or bad practices, suggest fixes, and even implement those fixes.
-->
  
## <a name="previous-versions"></a><span data-ttu-id="194c6-127">Versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="194c6-127">Previous Versions</span></span>
<span data-ttu-id="194c6-128">A continuación se enumeran las características clave que se presentaron en versiones anteriores del lenguaje C# y Visual Studio .NET.</span><span class="sxs-lookup"><span data-stu-id="194c6-128">The following lists key features that were introduced in previous versions of the C# language and Visual Studio .NET.</span></span>  
  
 * <span data-ttu-id="194c6-129">Visual Studio .NET 2013:</span><span class="sxs-lookup"><span data-stu-id="194c6-129">Visual Studio .NET 2013:</span></span> 
     - <span data-ttu-id="194c6-130">En esta versión de Visual Studio se incluyen correcciones de errores, mejoras de rendimiento y vistas previas de tecnología de .NET Compiler Platform (“Roslyn”), que pasó a ser el <!--Link to ../roslyn/index.md-->SDK de la plataforma de compilación .NET.</span><span class="sxs-lookup"><span data-stu-id="194c6-130">This version of Visual Studio included bug fixes, performance improvements, and technology previews of .NET Compiler Platform ("Roslyn") which became the .NET Compiler Platform SDK<!--Link to ../roslyn/index.md-->.</span></span>

 * <span data-ttu-id="194c6-131">C# 5, Visual Studio .NET 2012:</span><span class="sxs-lookup"><span data-stu-id="194c6-131">C# 5, Visual Studio .NET 2012:</span></span> 
     - <span data-ttu-id="194c6-132">Atributos `Async` / `await` e [información del llamador](../programming-guide/concepts/caller-information.md).</span><span class="sxs-lookup"><span data-stu-id="194c6-132">`Async` / `await`, and [caller information](../programming-guide/concepts/caller-information.md) attributes.</span></span>

 * <span data-ttu-id="194c6-133">C# 4, Visual Studio .NET 2010:</span><span class="sxs-lookup"><span data-stu-id="194c6-133">C# 4, Visual Studio .NET 2010:</span></span> 
     - <span data-ttu-id="194c6-134">`Dynamic`, [argumentos con nombre](../programming-guide/classes-and-structs/named-and-optional-arguments.md), parámetros opcionales y [covarianza y contravariancia](../programming-guide/concepts/covariance-contravariance/index.md) genéricas.</span><span class="sxs-lookup"><span data-stu-id="194c6-134">`Dynamic`, [named arguments](../programming-guide/classes-and-structs/named-and-optional-arguments.md), optional parameters, and generic [covariance and contra variance](../programming-guide/concepts/covariance-contravariance/index.md).</span></span>

 * <span data-ttu-id="194c6-135">C# 3, Visual Studio .NET 2008:</span><span class="sxs-lookup"><span data-stu-id="194c6-135">C# 3, Visual Studio .NET 2008:</span></span> 
     - <span data-ttu-id="194c6-136">Inicializadores de objeto y colección, expresiones lambda, métodos de extensión, tipos anónimos, propiedades automáticas, inferencia de tipo `var` local y [Language Integrated Query (LINQ)](../programming-guide/concepts/linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="194c6-136">Object and collection initializers, lambda expressions, extension methods, anonymous types, automatic properties, local `var` type inference, and [Language Integrated Query (LINQ)](../programming-guide/concepts/linq/index.md).</span></span>

 * <span data-ttu-id="194c6-137">C# 2, Visual Studio .NET 2005:</span><span class="sxs-lookup"><span data-stu-id="194c6-137">C# 2, Visual Studio .NET 2005:</span></span> 
     - <span data-ttu-id="194c6-138">Métodos anónimos, genéricos, tipos que aceptan valores NULL, iteradores/rendimiento, clases `static`, covarianza y contravarianza para delegados.</span><span class="sxs-lookup"><span data-stu-id="194c6-138">Anonymous methods, generics, nullable types, iterators/yield, `static` classes, and covariance and contra variance for delegates.</span></span>

 * <span data-ttu-id="194c6-139">C# 1.1, Visual Studio .NET 2003:</span><span class="sxs-lookup"><span data-stu-id="194c6-139">C# 1.1, Visual Studio .NET 2003:</span></span> 
     - <span data-ttu-id="194c6-140">Pragma `#line` y comentarios de documentos xml.</span><span class="sxs-lookup"><span data-stu-id="194c6-140">`#line` pragma and xml doc comments.</span></span>

 * <span data-ttu-id="194c6-141">C# 1, Visual Studio .NET 2002:</span><span class="sxs-lookup"><span data-stu-id="194c6-141">C# 1, Visual Studio .NET 2002:</span></span> 
     - <span data-ttu-id="194c6-142">La primera versión de [C#](../csharp.md).</span><span class="sxs-lookup"><span data-stu-id="194c6-142">The first release of [C#](../csharp.md).</span></span>   

