---
title: "fixed (Instrucción, Referencia de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- fixed_CSharpKeyword
- fixed
helpviewer_keywords:
- fixed keyword [C#]
ms.assetid: 7ea6db08-ad49-4a7a-b934-d8c4acad1c3a
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 13633e71c863b075eede41c9a18419d65350bdb0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="fixed-statement-c-reference"></a><span data-ttu-id="53662-102">fixed (Instrucción, Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="53662-102">fixed Statement (C# Reference)</span></span>
<span data-ttu-id="53662-103">La instrucción `fixed` evita que el recolector de elementos no utilizados reubique una variable móvil.</span><span class="sxs-lookup"><span data-stu-id="53662-103">The `fixed` statement prevents the garbage collector from relocating a movable variable.</span></span> <span data-ttu-id="53662-104">La instrucción `fixed` solo se permite en un contexto de [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="53662-104">The `fixed` statement is only permitted in an [unsafe](../../../csharp/language-reference/keywords/unsafe.md) context.</span></span> <span data-ttu-id="53662-105">`Fixed` también puede usarse para crear [búferes de tamaño fijo](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span><span class="sxs-lookup"><span data-stu-id="53662-105">`Fixed` can also be used to create [fixed size buffers](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span></span>  
  
 <span data-ttu-id="53662-106">La instrucción `fixed` establece un puntero a una variable administrada y "ancla" esa variable durante su ejecución.</span><span class="sxs-lookup"><span data-stu-id="53662-106">The `fixed` statement sets a pointer to a managed variable and "pins" that variable during the execution of the statement.</span></span> <span data-ttu-id="53662-107">Sin `fixed`, los punteros a variables administradas móviles serían de poca utilidad, puesto que la recolección de elementos no utilizados podría reubicar las variables de forma impredecible.</span><span class="sxs-lookup"><span data-stu-id="53662-107">Without `fixed`, pointers to movable managed variables would be of little use since garbage collection could relocate the variables unpredictably.</span></span> <span data-ttu-id="53662-108">El compilador de C# solo permite asignar un puntero a una variable administrada en una instrucción `fixed`.</span><span class="sxs-lookup"><span data-stu-id="53662-108">The C# compiler only lets you assign a pointer to a managed variable in a `fixed` statement.</span></span>  
  
 [!code-csharp[csrefKeywordsFixedLock#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_1.cs)]  
  
 <span data-ttu-id="53662-109">Puede inicializar un puntero mediante una matriz, una cadena, un búfer de tamaño fijo o la dirección de una variable.</span><span class="sxs-lookup"><span data-stu-id="53662-109">You can initialize a pointer by using an array, a string, a fixed-size buffer, or the address of a variable.</span></span> <span data-ttu-id="53662-110">En el ejemplo siguiente se muestra el uso de direcciones, matrices y cadenas de variables.</span><span class="sxs-lookup"><span data-stu-id="53662-110">The following example illustrates the use of variable addresses, arrays, and strings.</span></span> <span data-ttu-id="53662-111">Para obtener más información sobre los búferes de tamaño fijo, consulte [Fixed Size Buffers](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md) (Búferes de tamaño fijo).</span><span class="sxs-lookup"><span data-stu-id="53662-111">For more information about fixed-size buffers, see [Fixed Size Buffers](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span></span>  
  
 [!code-csharp[csrefKeywordsFixedLock#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_2.cs)]  
  
 <span data-ttu-id="53662-112">Puede inicializar varios punteros, siempre que sean del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="53662-112">You can initialize multiple pointers, as long as they are all of the same type.</span></span>  
  
```csharp
fixed (byte* ps = srcarray, pd = dstarray) {...}  
```
  
 <span data-ttu-id="53662-113">Para inicializar punteros de tipos diferentes, simplemente anide instrucciones `fixed`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="53662-113">To initialize pointers of different types, simply nest `fixed` statements, as shown in the following example.</span></span>  
  
 [!code-csharp[csrefKeywordsFixedLock#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_3.cs)]  
  
 <span data-ttu-id="53662-114">Después de ejecutar el código de la instrucción, las variables ancladas se desanclan y quedan sujetas a la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="53662-114">After the code in the statement is executed, any pinned variables are unpinned and subject to garbage collection.</span></span> <span data-ttu-id="53662-115">Por lo tanto, no debe apuntar a esas variables fuera de la instrucción `fixed`.</span><span class="sxs-lookup"><span data-stu-id="53662-115">Therefore, do not point to those variables outside the `fixed` statement.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="53662-116">Los punteros inicializados en instrucciones fijas no pueden modificarse.</span><span class="sxs-lookup"><span data-stu-id="53662-116">Pointers initialized in fixed statements cannot be modified.</span></span>  
  
 <span data-ttu-id="53662-117">En el modo no seguro, puede asignar memoria en la pila, en la que no está sujeta a la recolección de elementos no utilizados y, por tanto, no necesita anclarse.</span><span class="sxs-lookup"><span data-stu-id="53662-117">In unsafe mode, you can allocate memory on the stack, where it is not subject to garbage collection and therefore does not need to be pinned.</span></span> <span data-ttu-id="53662-118">Para obtener más información, consulte [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md).</span><span class="sxs-lookup"><span data-stu-id="53662-118">For more information, see [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="53662-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="53662-119">Example</span></span>  
 [!code-csharp[csrefKeywordsFixedLock#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_4.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="53662-120">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="53662-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="53662-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="53662-121">See Also</span></span>  
 [<span data-ttu-id="53662-122">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="53662-122">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="53662-123">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="53662-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="53662-124">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="53662-124">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="53662-125">unsafe</span><span class="sxs-lookup"><span data-stu-id="53662-125">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="53662-126">Búferes de tamaño fijo</span><span class="sxs-lookup"><span data-stu-id="53662-126">Fixed Size Buffers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
