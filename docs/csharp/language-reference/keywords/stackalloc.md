---
title: stackalloc (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- stackalloc_CSharpKeyword
- stackalloc
dev_langs:
- CSharp
helpviewer_keywords:
- stackalloc keyword [C#]
ms.assetid: adc04c28-3ed2-4326-807a-7545df92b852
caps.latest.revision: 27
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 53d61cfdcf4d356a28881c57ad923017c2b479ae
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="stackalloc-c-reference"></a><span data-ttu-id="97a0c-102">stackalloc (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="97a0c-102">stackalloc (C# Reference)</span></span>
<span data-ttu-id="97a0c-103">La palabra clave `stackalloc` se usa en un contexto de código no seguro para asignar un bloque de memoria a la pila.</span><span class="sxs-lookup"><span data-stu-id="97a0c-103">The `stackalloc` keyword is used in an unsafe code context to allocate a block of memory on the stack.</span></span>  
  
```  
int* block = stackalloc int[100];  
```  
  
## <a name="remarks"></a><span data-ttu-id="97a0c-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="97a0c-104">Remarks</span></span>  
 <span data-ttu-id="97a0c-105">La palabra clave solo es válida en inicializadores de variables locales.</span><span class="sxs-lookup"><span data-stu-id="97a0c-105">The keyword is valid only in local variable initializers.</span></span> <span data-ttu-id="97a0c-106">El código siguiente genera errores del compilador.</span><span class="sxs-lookup"><span data-stu-id="97a0c-106">The following code causes compiler errors.</span></span>  
  
```  
int* block;  
// The following assignment statement causes compiler errors. You  
// can use stackalloc only when declaring and initializing a local   
// variable.  
block = stackalloc int[100];  
```  
  
 <span data-ttu-id="97a0c-107">Como implica tipos de puntero, `stackalloc` requiere contexto [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="97a0c-107">Because pointer types are involved, `stackalloc` requires [unsafe](../../../csharp/language-reference/keywords/unsafe.md) context.</span></span> <span data-ttu-id="97a0c-108">Para obtener más información, vea [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md) (Código no seguro y punteros [Guía de programación de C#]).</span><span class="sxs-lookup"><span data-stu-id="97a0c-108">For more information, see [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span></span>  
  
 <span data-ttu-id="97a0c-109">`stackalloc` es como [_alloca](/cpp/c-runtime-library/reference/alloca) en la biblioteca en tiempo de ejecución de C.</span><span class="sxs-lookup"><span data-stu-id="97a0c-109">`stackalloc` is like [_alloca](/cpp/c-runtime-library/reference/alloca) in the C run-time library.</span></span>  
  
 <span data-ttu-id="97a0c-110">En el ejemplo siguiente se calculan y muestran los 20 primeros números de la secuencia de Fibonacci.</span><span class="sxs-lookup"><span data-stu-id="97a0c-110">The following example calculates and displays the first 20 numbers in the Fibonacci sequence.</span></span> <span data-ttu-id="97a0c-111">Cada número es la suma de los dos números anteriores.</span><span class="sxs-lookup"><span data-stu-id="97a0c-111">Each number is the sum of the previous two numbers.</span></span> <span data-ttu-id="97a0c-112">En el código, se asigna a la pila, no al montón, un bloque de memoria de tamaño suficiente para contener 20 elementos del tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="97a0c-112">In the code, a block of memory of sufficient size to contain 20 elements of type `int` is allocated on the stack, not the heap.</span></span> <span data-ttu-id="97a0c-113">La dirección del bloque se almacena en el puntero `fib`.</span><span class="sxs-lookup"><span data-stu-id="97a0c-113">The address of the block is stored in the pointer `fib`.</span></span> <span data-ttu-id="97a0c-114">Esta memoria no está sujeta a la recolección de elementos no utilizados y, por tanto, no necesita fijarse (mediante [fixed](../../../csharp/language-reference/keywords/fixed-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="97a0c-114">This memory is not subject to garbage collection and therefore does not have to be pinned (by using [fixed](../../../csharp/language-reference/keywords/fixed-statement.md)).</span></span> <span data-ttu-id="97a0c-115">La duración del bloque de memoria se limita a la duración del método que lo define.</span><span class="sxs-lookup"><span data-stu-id="97a0c-115">The lifetime of the memory block is limited to the lifetime of the method that defines it.</span></span> <span data-ttu-id="97a0c-116">No se puede liberar la memoria antes de que el método vuelva.</span><span class="sxs-lookup"><span data-stu-id="97a0c-116">You cannot free the memory before the method returns.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97a0c-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="97a0c-117">Example</span></span>  
 <span data-ttu-id="97a0c-118">[!code-cs[csrefKeywordsOperator#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/stackalloc_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="97a0c-118">[!code-cs[csrefKeywordsOperator#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/stackalloc_1.cs)]</span></span>  
  
## <a name="security"></a><span data-ttu-id="97a0c-119">Seguridad</span><span class="sxs-lookup"><span data-stu-id="97a0c-119">Security</span></span>  
 <span data-ttu-id="97a0c-120">El código no seguro es menos seguro que las alternativas seguras.</span><span class="sxs-lookup"><span data-stu-id="97a0c-120">Unsafe code is less secure than safe alternatives.</span></span> <span data-ttu-id="97a0c-121">Pero el uso de `stackalloc` habilita automáticamente las características de detección de saturación del búfer en el entorno Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="97a0c-121">However, the use of `stackalloc` automatically enables buffer overrun detection features in the common language runtime (CLR).</span></span> <span data-ttu-id="97a0c-122">Si se detecta saturación del búfer, se finaliza el proceso lo antes posible para minimizar el riesgo de que se ejecute código malintencionado.</span><span class="sxs-lookup"><span data-stu-id="97a0c-122">If a buffer overrun is detected, the process is terminated as quickly as possible to minimize the chance that malicious code is executed.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="97a0c-123">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="97a0c-123">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="97a0c-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="97a0c-124">See Also</span></span>  
 <span data-ttu-id="97a0c-125">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="97a0c-125">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="97a0c-126">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="97a0c-126">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="97a0c-127">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="97a0c-127">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="97a0c-128">[Operator Keywords](../../../csharp/language-reference/keywords/operator-keywords.md)  (Palabras clave de operador [Referencia de C#])</span><span class="sxs-lookup"><span data-stu-id="97a0c-128">[Operator Keywords](../../../csharp/language-reference/keywords/operator-keywords.md) </span></span>  
 [<span data-ttu-id="97a0c-129">Código no seguro y punteros</span><span class="sxs-lookup"><span data-stu-id="97a0c-129">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)

