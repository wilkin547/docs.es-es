---
title: Guía de programación de C#
ms.date: 05/02/2017
f1_keywords:
- cs.langref
helpviewer_keywords:
- reference tables [C#]
- C# language, programming guide
- Visual C#, programming concepts
- C# language, concepts
ms.assetid: ac0f23a2-6bf3-4077-be99-538ae5fd3bc5
ms.openlocfilehash: de40369a661c347a2125075e820420af4eb71cac
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "75337250"
---
# <a name="c-programming-guide"></a><span data-ttu-id="cbd21-102">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="cbd21-102">C# programming guide</span></span>

<span data-ttu-id="cbd21-103">Esta sección proporciona información detallada sobre las funcionalidades y características claves del lenguaje C# a las que C# puede acceder a través de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cbd21-103">This section provides detailed information on key C# language features and features accessible to C# through the .NET Framework.</span></span>  
  
 <span data-ttu-id="cbd21-104">En la mayor parte de esta sección se supone que ya sabe algo sobre C# y que conoce los conceptos de programación generales.</span><span class="sxs-lookup"><span data-stu-id="cbd21-104">Most of this section assumes that you already know something about C# and general programming concepts.</span></span> <span data-ttu-id="cbd21-105">Si nunca ha programado ni ha trabajado con C#, puede visitar los tutoriales de [Introducción a C#](../tutorials/intro-to-csharp/index.md) o el [tutorial de .NET en explorador](https://dotnet.microsoft.com/learn/dotnet/in-browser-tutorial/1), que no requiere ningún conocimiento previo de programación.</span><span class="sxs-lookup"><span data-stu-id="cbd21-105">If you are a complete beginner with programming or with C#, you might want to visit the [Introduction to C# Tutorials](../tutorials/intro-to-csharp/index.md) or [.NET In-Browser Tutorial](https://dotnet.microsoft.com/learn/dotnet/in-browser-tutorial/1), where no prior programming knowledge is required.</span></span>  
  
 <span data-ttu-id="cbd21-106">Para obtener información sobre determinadas palabras clave, operadores y directivas de preprocesador, vea [Referencia de C#](../language-reference/index.md).</span><span class="sxs-lookup"><span data-stu-id="cbd21-106">For information about specific keywords, operators and preprocessor directives, see [C# Reference](../language-reference/index.md).</span></span> <span data-ttu-id="cbd21-107">Para obtener información sobre la especificación del lenguaje C#, vea [Especificación del lenguaje C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="cbd21-107">For information about the C# Language Specification, see [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span>  
  
## <a name="program-sections"></a><span data-ttu-id="cbd21-108">Secciones de programa</span><span class="sxs-lookup"><span data-stu-id="cbd21-108">Program sections</span></span>

[<span data-ttu-id="cbd21-109">Dentro de un programa de C#</span><span class="sxs-lookup"><span data-stu-id="cbd21-109">Inside a C# Program</span></span>](./inside-a-program/index.md)  
  
[<span data-ttu-id="cbd21-110">Main() y argumentos de la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="cbd21-110">Main() and Command-Line Arguments</span></span>](./main-and-command-args/index.md)  

## <a name="language-sections"></a><span data-ttu-id="cbd21-111">Secciones de lenguaje</span><span class="sxs-lookup"><span data-stu-id="cbd21-111">Language Sections</span></span>

[<span data-ttu-id="cbd21-112">Instrucciones, expresiones y operadores</span><span class="sxs-lookup"><span data-stu-id="cbd21-112">Statements, Expressions, and Operators</span></span>](./statements-expressions-operators/index.md)  

 [<span data-ttu-id="cbd21-113">Tipos</span><span class="sxs-lookup"><span data-stu-id="cbd21-113">Types</span></span>](./types/index.md)  

 [<span data-ttu-id="cbd21-114">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="cbd21-114">Classes and Structs</span></span>](./classes-and-structs/index.md)  
  
 [<span data-ttu-id="cbd21-115">Interfaces</span><span class="sxs-lookup"><span data-stu-id="cbd21-115">Interfaces</span></span>](./interfaces/index.md)  

 [<span data-ttu-id="cbd21-116">Delegados</span><span class="sxs-lookup"><span data-stu-id="cbd21-116">Delegates</span></span>](./delegates/index.md)  

 [<span data-ttu-id="cbd21-117">Matrices</span><span class="sxs-lookup"><span data-stu-id="cbd21-117">Arrays</span></span>](./arrays/index.md)  
  
 [<span data-ttu-id="cbd21-118">Cadenas</span><span class="sxs-lookup"><span data-stu-id="cbd21-118">Strings</span></span>](./strings/index.md)  
  
 [<span data-ttu-id="cbd21-119">Propiedades</span><span class="sxs-lookup"><span data-stu-id="cbd21-119">Properties</span></span>](./classes-and-structs/properties.md)  
  
 [<span data-ttu-id="cbd21-120">Indizadores</span><span class="sxs-lookup"><span data-stu-id="cbd21-120">Indexers</span></span>](./indexers/index.md)  
  
 [<span data-ttu-id="cbd21-121">Eventos</span><span class="sxs-lookup"><span data-stu-id="cbd21-121">Events</span></span>](./events/index.md)  
  
 [<span data-ttu-id="cbd21-122">Genéricos</span><span class="sxs-lookup"><span data-stu-id="cbd21-122">Generics</span></span>](./generics/index.md)  
  
 [<span data-ttu-id="cbd21-123">Iteradores</span><span class="sxs-lookup"><span data-stu-id="cbd21-123">Iterators</span></span>](./concepts/iterators.md)
  
 [<span data-ttu-id="cbd21-124">Expresiones de consulta LINQ</span><span class="sxs-lookup"><span data-stu-id="cbd21-124">LINQ Query Expressions</span></span>](../linq/index.md)  
  
 [<span data-ttu-id="cbd21-125">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="cbd21-125">Lambda Expressions</span></span>](./statements-expressions-operators/lambda-expressions.md)  
  
 [<span data-ttu-id="cbd21-126">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="cbd21-126">Namespaces</span></span>](./namespaces/index.md)  
  
 [<span data-ttu-id="cbd21-127">Código no seguro y punteros</span><span class="sxs-lookup"><span data-stu-id="cbd21-127">Unsafe Code and Pointers</span></span>](./unsafe-code-pointers/index.md)  
  
 [<span data-ttu-id="cbd21-128">Comentarios de documentación XML</span><span class="sxs-lookup"><span data-stu-id="cbd21-128">XML Documentation Comments</span></span>](./xmldoc/index.md)  
  
## <a name="platform-sections"></a><span data-ttu-id="cbd21-129">Secciones de la plataforma</span><span class="sxs-lookup"><span data-stu-id="cbd21-129">Platform Sections</span></span>

 [<span data-ttu-id="cbd21-130">Dominios de aplicación</span><span class="sxs-lookup"><span data-stu-id="cbd21-130">Application Domains</span></span>](../../framework/app-domains/application-domains.md)  
  
 [<span data-ttu-id="cbd21-131">Ensamblados de .NET</span><span class="sxs-lookup"><span data-stu-id="cbd21-131">Assemblies in .NET</span></span>](../../standard/assembly/index.md)  
  
 [<span data-ttu-id="cbd21-132">Atributos</span><span class="sxs-lookup"><span data-stu-id="cbd21-132">Attributes</span></span>](./concepts/attributes/index.md)  
  
 [<span data-ttu-id="cbd21-133">Colecciones</span><span class="sxs-lookup"><span data-stu-id="cbd21-133">Collections</span></span>](./concepts/collections.md)  
  
 [<span data-ttu-id="cbd21-134">Excepciones y control de excepciones</span><span class="sxs-lookup"><span data-stu-id="cbd21-134">Exceptions and Exception Handling</span></span>](./exceptions/index.md)  
  
 [<span data-ttu-id="cbd21-135">Registro y sistema de archivos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="cbd21-135">File System and the Registry (C# Programming Guide)</span></span>](./file-system/index.md)  
  
 [<span data-ttu-id="cbd21-136">Interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="cbd21-136">Interoperability</span></span>](./interop/index.md)  
  
 [<span data-ttu-id="cbd21-137">Reflexión</span><span class="sxs-lookup"><span data-stu-id="cbd21-137">Reflection</span></span>](./concepts/reflection.md)  
  
## <a name="see-also"></a><span data-ttu-id="cbd21-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="cbd21-138">See also</span></span>

- [<span data-ttu-id="cbd21-139">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="cbd21-139">C# Reference</span></span>](../language-reference/index.md)
