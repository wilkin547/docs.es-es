---
title: 'Excepciones generadas por el compilador: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions [C#], compiler-generated
ms.assetid: 53b52f97-b366-4ed7-b05b-9eb78096b7f9
ms.openlocfilehash: 1d2d561df3e496893657b050fa93b44c56542d97
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2020
ms.locfileid: "84240738"
---
# <a name="compiler-generated-exceptions-c-programming-guide"></a><span data-ttu-id="107ce-102">Excepciones generadas por el compilador (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="107ce-102">Compiler-Generated Exceptions (C# Programming Guide)</span></span>

<span data-ttu-id="107ce-103">Algunas excepciones las inicia automáticamente el entorno de ejecución .NET cuando se producen errores de operaciones básicas.</span><span class="sxs-lookup"><span data-stu-id="107ce-103">Some exceptions are thrown automatically by the .NET runtime when basic operations fail.</span></span> <span data-ttu-id="107ce-104">En la tabla siguiente se enumeran estas excepciones y sus condiciones de error.</span><span class="sxs-lookup"><span data-stu-id="107ce-104">These exceptions and their error conditions are listed in the following table.</span></span>  
  
|<span data-ttu-id="107ce-105">Excepción</span><span class="sxs-lookup"><span data-stu-id="107ce-105">Exception</span></span>|<span data-ttu-id="107ce-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="107ce-106">Description</span></span>|  
|---------------|-----------------|  
|<xref:System.ArithmeticException>|<span data-ttu-id="107ce-107">Una clase base para las excepciones que se producen durante las operaciones aritméticas, como <xref:System.DivideByZeroException> y <xref:System.OverflowException>.</span><span class="sxs-lookup"><span data-stu-id="107ce-107">A base class for exceptions that occur during arithmetic operations, such as <xref:System.DivideByZeroException> and <xref:System.OverflowException>.</span></span>|  
|<xref:System.ArrayTypeMismatchException>|<span data-ttu-id="107ce-108">Se inicia cuando una matriz no puede almacenar un elemento determinado porque el tipo real del elemento es incompatible con el tipo real de la matriz.</span><span class="sxs-lookup"><span data-stu-id="107ce-108">Thrown when an array cannot store a given element because the actual type of the element is incompatible with the actual type of the array.</span></span>|  
|<xref:System.DivideByZeroException>|<span data-ttu-id="107ce-109">Se inicia cuando se intenta dividir un valor entero entre cero.</span><span class="sxs-lookup"><span data-stu-id="107ce-109">Thrown when an attempt is made to divide an integral value by zero.</span></span>|  
|<xref:System.IndexOutOfRangeException>|<span data-ttu-id="107ce-110">Se inicia cuando se intenta indexar una matriz y el índice es menor que cero o queda fuera de los límites de la matriz.</span><span class="sxs-lookup"><span data-stu-id="107ce-110">Thrown when an attempt is made to index an array when the index is less than zero or outside the bounds of the array.</span></span>|  
|<xref:System.InvalidCastException>|<span data-ttu-id="107ce-111">Se inicia cuando se produce un error en una conversión explícita de un tipo base en una interfaz o un tipo derivado en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="107ce-111">Thrown when an explicit conversion from a base type to an interface or to a derived type fails at runtime.</span></span>|  
|<xref:System.NullReferenceException>|<span data-ttu-id="107ce-112">Se inicia cuando se intenta hacer referencia a un objeto cuyo valor es [null](../../language-reference/keywords/null.md).</span><span class="sxs-lookup"><span data-stu-id="107ce-112">Thrown when an attempt is made to reference an object whose value is [null](../../language-reference/keywords/null.md).</span></span>|  
|<xref:System.OutOfMemoryException>|<span data-ttu-id="107ce-113">Se inicia cuando se produce un error al intentar asignar memoria con el operador [new](../../language-reference/operators/new-operator.md).</span><span class="sxs-lookup"><span data-stu-id="107ce-113">Thrown when an attempt to allocate memory using the [new](../../language-reference/operators/new-operator.md) operator fails.</span></span> <span data-ttu-id="107ce-114">Indica que se ha agotado la memoria disponible para el entorno Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="107ce-114">This indicates that the memory available to the common language runtime has been exhausted.</span></span>|  
|<xref:System.OverflowException>|<span data-ttu-id="107ce-115">Se inicia cuando se desborda una operación aritmética en un contexto `checked`.</span><span class="sxs-lookup"><span data-stu-id="107ce-115">Thrown when an arithmetic operation in a `checked` context overflows.</span></span>|  
|<xref:System.StackOverflowException>|<span data-ttu-id="107ce-116">Se inicia cuando se agota la pila de ejecución por tener demasiadas llamadas a métodos pendientes. Normalmente, indica una recursividad muy profunda o infinita.</span><span class="sxs-lookup"><span data-stu-id="107ce-116">Thrown when the execution stack is exhausted by having too many pending method calls; usually indicates a very deep or infinite recursion.</span></span>|  
|<xref:System.TypeInitializationException>|<span data-ttu-id="107ce-117">Se inicia cuando un constructor estático inicia una excepción y no existe una cláusula `catch` compatible para capturarla.</span><span class="sxs-lookup"><span data-stu-id="107ce-117">Thrown when a static constructor throws an exception and no compatible `catch` clause exists to catch it.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="107ce-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="107ce-118">See also</span></span>

- [<span data-ttu-id="107ce-119">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="107ce-119">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="107ce-120">Excepciones y control de excepciones</span><span class="sxs-lookup"><span data-stu-id="107ce-120">Exceptions and Exception Handling</span></span>](./index.md)
- [<span data-ttu-id="107ce-121">Control de excepciones</span><span class="sxs-lookup"><span data-stu-id="107ce-121">Exception Handling</span></span>](./exception-handling.md)
- [<span data-ttu-id="107ce-122">try-catch</span><span class="sxs-lookup"><span data-stu-id="107ce-122">try-catch</span></span>](../../language-reference/keywords/try-catch.md)
- [<span data-ttu-id="107ce-123">try-finally</span><span class="sxs-lookup"><span data-stu-id="107ce-123">try-finally</span></span>](../../language-reference/keywords/try-finally.md)
- [<span data-ttu-id="107ce-124">try-catch-finally</span><span class="sxs-lookup"><span data-stu-id="107ce-124">try-catch-finally</span></span>](../../language-reference/keywords/try-catch-finally.md)
