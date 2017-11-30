---
title: stackalloc (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- stackalloc_CSharpKeyword
- stackalloc
helpviewer_keywords: stackalloc keyword [C#]
ms.assetid: adc04c28-3ed2-4326-807a-7545df92b852
caps.latest.revision: "27"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ad4453f889a344fcd44dfad44a30fef07380b6a3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="stackalloc-c-reference"></a><span data-ttu-id="6519b-102">stackalloc (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="6519b-102">stackalloc (C# Reference)</span></span>
<span data-ttu-id="6519b-103">La palabra clave `stackalloc` se usa en un contexto de código no seguro para asignar un bloque de memoria a la pila.</span><span class="sxs-lookup"><span data-stu-id="6519b-103">The `stackalloc` keyword is used in an unsafe code context to allocate a block of memory on the stack.</span></span>  
  
```  
int* block = stackalloc int[100];  
```  
  
## <a name="remarks"></a><span data-ttu-id="6519b-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6519b-104">Remarks</span></span>  
 <span data-ttu-id="6519b-105">La palabra clave solo es válida en inicializadores de variables locales.</span><span class="sxs-lookup"><span data-stu-id="6519b-105">The keyword is valid only in local variable initializers.</span></span> <span data-ttu-id="6519b-106">El código siguiente genera errores del compilador.</span><span class="sxs-lookup"><span data-stu-id="6519b-106">The following code causes compiler errors.</span></span>  
  
```  
int* block;  
// The following assignment statement causes compiler errors. You  
// can use stackalloc only when declaring and initializing a local   
// variable.  
block = stackalloc int[100];  
```  
  
 <span data-ttu-id="6519b-107">Como implica tipos de puntero, `stackalloc` requiere contexto [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="6519b-107">Because pointer types are involved, `stackalloc` requires [unsafe](../../../csharp/language-reference/keywords/unsafe.md) context.</span></span> <span data-ttu-id="6519b-108">Para obtener más información, vea [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md) (Código no seguro y punteros [Guía de programación de C#]).</span><span class="sxs-lookup"><span data-stu-id="6519b-108">For more information, see [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span></span>  
  
 <span data-ttu-id="6519b-109">`stackalloc` es como [_alloca](/cpp/c-runtime-library/reference/alloca) en la biblioteca en tiempo de ejecución de C.</span><span class="sxs-lookup"><span data-stu-id="6519b-109">`stackalloc` is like [_alloca](/cpp/c-runtime-library/reference/alloca) in the C run-time library.</span></span>  
  
 <span data-ttu-id="6519b-110">En el ejemplo siguiente se calculan y muestran los 20 primeros números de la secuencia de Fibonacci.</span><span class="sxs-lookup"><span data-stu-id="6519b-110">The following example calculates and displays the first 20 numbers in the Fibonacci sequence.</span></span> <span data-ttu-id="6519b-111">Cada número es la suma de los dos números anteriores.</span><span class="sxs-lookup"><span data-stu-id="6519b-111">Each number is the sum of the previous two numbers.</span></span> <span data-ttu-id="6519b-112">En el código, se asigna a la pila, no al montón, un bloque de memoria de tamaño suficiente para contener 20 elementos del tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="6519b-112">In the code, a block of memory of sufficient size to contain 20 elements of type `int` is allocated on the stack, not the heap.</span></span> <span data-ttu-id="6519b-113">La dirección del bloque se almacena en el puntero `fib`.</span><span class="sxs-lookup"><span data-stu-id="6519b-113">The address of the block is stored in the pointer `fib`.</span></span> <span data-ttu-id="6519b-114">Esta memoria no está sujeta a la recolección de elementos no utilizados y, por tanto, no necesita fijarse (mediante [fixed](../../../csharp/language-reference/keywords/fixed-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="6519b-114">This memory is not subject to garbage collection and therefore does not have to be pinned (by using [fixed](../../../csharp/language-reference/keywords/fixed-statement.md)).</span></span> <span data-ttu-id="6519b-115">La duración del bloque de memoria se limita a la duración del método que lo define.</span><span class="sxs-lookup"><span data-stu-id="6519b-115">The lifetime of the memory block is limited to the lifetime of the method that defines it.</span></span> <span data-ttu-id="6519b-116">No se puede liberar la memoria antes de que el método vuelva.</span><span class="sxs-lookup"><span data-stu-id="6519b-116">You cannot free the memory before the method returns.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6519b-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6519b-117">Example</span></span>  
 [!code-csharp[csrefKeywordsOperator#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/stackalloc_1.cs)]  
  
## <a name="security"></a><span data-ttu-id="6519b-118">Seguridad</span><span class="sxs-lookup"><span data-stu-id="6519b-118">Security</span></span>  
 <span data-ttu-id="6519b-119">El código no seguro es menos seguro que las alternativas seguras.</span><span class="sxs-lookup"><span data-stu-id="6519b-119">Unsafe code is less secure than safe alternatives.</span></span> <span data-ttu-id="6519b-120">Pero el uso de `stackalloc` habilita automáticamente las características de detección de saturación del búfer en el entorno Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="6519b-120">However, the use of `stackalloc` automatically enables buffer overrun detection features in the common language runtime (CLR).</span></span> <span data-ttu-id="6519b-121">Si se detecta saturación del búfer, se finaliza el proceso lo antes posible para minimizar el riesgo de que se ejecute código malintencionado.</span><span class="sxs-lookup"><span data-stu-id="6519b-121">If a buffer overrun is detected, the process is terminated as quickly as possible to minimize the chance that malicious code is executed.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="6519b-122">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="6519b-122">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6519b-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="6519b-123">See Also</span></span>  
 [<span data-ttu-id="6519b-124">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="6519b-124">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="6519b-125">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="6519b-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="6519b-126">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="6519b-126">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="6519b-127">Palabras clave de operador</span><span class="sxs-lookup"><span data-stu-id="6519b-127">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [<span data-ttu-id="6519b-128">Código no seguro y punteros</span><span class="sxs-lookup"><span data-stu-id="6519b-128">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)
