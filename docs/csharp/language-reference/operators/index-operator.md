---
title: Operador [] (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '[]_CSharpKeyword'
helpviewer_keywords:
- subscript operator [C#]
- square brackets [ ] operator [C#]
- '[] operator [C#]'
- indexing operator [C#]
ms.assetid: 5c16bb45-88f7-45ff-b42c-1af1972b042c
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 03664f5604bb7d7dce9e8ae2ff0ec045c6a203b1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="c9552-102">Operador [] (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="c9552-102">[] Operator (C# Reference)</span></span>
<span data-ttu-id="c9552-103">Los corchetes (`[]`) se usan para matrices, indexadores y atributos.</span><span class="sxs-lookup"><span data-stu-id="c9552-103">Square brackets (`[]`) are used for arrays, indexers, and attributes.</span></span> <span data-ttu-id="c9552-104">También se pueden usar con punteros.</span><span class="sxs-lookup"><span data-stu-id="c9552-104">They can also be used with pointers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c9552-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c9552-105">Remarks</span></span>  
 <span data-ttu-id="c9552-106">El tipo de matriz es un tipo seguido de `[]`:</span><span class="sxs-lookup"><span data-stu-id="c9552-106">An array type is a type followed by `[]`:</span></span>  
  
 [!code-csharp[csRefOperators#43](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_1.cs)]  
  
 <span data-ttu-id="c9552-107">Para acceder a un elemento de una matriz, el índice del elemento deseado se encierra entre corchetes:</span><span class="sxs-lookup"><span data-stu-id="c9552-107">To access an element of an array, the index of the desired element is enclosed in brackets:</span></span>  
  
 [!code-csharp[csRefOperators#44](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_2.cs)]  
  
 <span data-ttu-id="c9552-108">Se produce una excepción si el índice de una matriz está fuera del intervalo.</span><span class="sxs-lookup"><span data-stu-id="c9552-108">An exception is thrown if an array index is out of range.</span></span>  
  
 <span data-ttu-id="c9552-109">No se puede sobrecargar el operador de indexación de la matriz. En cambio, los tipos pueden definir indexadores y propiedades que aceptan uno o varios parámetros.</span><span class="sxs-lookup"><span data-stu-id="c9552-109">The array indexing operator cannot be overloaded; however, types can define indexers, and properties that take one or more parameters.</span></span> <span data-ttu-id="c9552-110">Los parámetros del indexador van entre corchetes, al igual que los índices de matriz, pero se pueden declarar para que sean de cualquier tipo, a diferencia de los índices de matriz, que deben ser números enteros.</span><span class="sxs-lookup"><span data-stu-id="c9552-110">Indexer parameters are enclosed in square brackets, just like array indexes, but indexer parameters can be declared to be of any type, unlike array indexes, which must be integral.</span></span>  
  
 <span data-ttu-id="c9552-111">Por ejemplo, .NET Framework define un tipo `Hashtable` que asocia claves y valores de tipo arbitrario:</span><span class="sxs-lookup"><span data-stu-id="c9552-111">For example, the .NET Framework defines a `Hashtable` type that associates keys and values of arbitrary type:</span></span>  
  
 [!code-csharp[csRefOperators#45](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_3.cs)]  
  
 <span data-ttu-id="c9552-112">Los corchetes también se usan para especificar [atributos](../../../csharp/programming-guide/concepts/attributes/index.md):</span><span class="sxs-lookup"><span data-stu-id="c9552-112">Square brackets are also used to specify [Attributes](../../../csharp/programming-guide/concepts/attributes/index.md):</span></span>  
  
 [!code-csharp[csRefOperators#46](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_4.cs)]  
  
 <span data-ttu-id="c9552-113">Puede usar corchetes para indexar fuera de un puntero:</span><span class="sxs-lookup"><span data-stu-id="c9552-113">You can use square brackets to index off a pointer:</span></span>  
  
 [!code-csharp[csRefOperators#47](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_5.cs)]  
  
 <span data-ttu-id="c9552-114">No se realiza ninguna comprobación de límites.</span><span class="sxs-lookup"><span data-stu-id="c9552-114">No bounds checking is performed.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="c9552-115">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="c9552-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c9552-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="c9552-116">See Also</span></span>  
 [<span data-ttu-id="c9552-117">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="c9552-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="c9552-118">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="c9552-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="c9552-119">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="c9552-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="c9552-120">Matrices</span><span class="sxs-lookup"><span data-stu-id="c9552-120">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
 [<span data-ttu-id="c9552-121">Indizadores</span><span class="sxs-lookup"><span data-stu-id="c9552-121">Indexers</span></span>](../../../csharp/programming-guide/indexers/index.md)  
 [<span data-ttu-id="c9552-122">unsafe</span><span class="sxs-lookup"><span data-stu-id="c9552-122">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="c9552-123">fixed (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c9552-123">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
