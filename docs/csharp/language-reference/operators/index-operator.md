---
title: Operador [] (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '[]_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- subscript operator [C#]
- square brackets [ ] operator [C#]
- '[] operator [C#]'
- indexing operator [C#]
ms.assetid: 5c16bb45-88f7-45ff-b42c-1af1972b042c
caps.latest.revision: 20
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
ms.openlocfilehash: b49d41af0dd4dc34b1b74c62ce8779aa31d69f77
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="3958e-102">Operador [] (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="3958e-102">[] Operator (C# Reference)</span></span>
<span data-ttu-id="3958e-103">Los corchetes (`[]`) se usan para matrices, indexadores y atributos.</span><span class="sxs-lookup"><span data-stu-id="3958e-103">Square brackets (`[]`) are used for arrays, indexers, and attributes.</span></span> <span data-ttu-id="3958e-104">También se pueden usar con punteros.</span><span class="sxs-lookup"><span data-stu-id="3958e-104">They can also be used with pointers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3958e-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3958e-105">Remarks</span></span>  
 <span data-ttu-id="3958e-106">El tipo de matriz es un tipo seguido de `[]`:</span><span class="sxs-lookup"><span data-stu-id="3958e-106">An array type is a type followed by `[]`:</span></span>  
  
 <span data-ttu-id="3958e-107">[!code-cs[csRefOperators#43](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="3958e-107">[!code-cs[csRefOperators#43](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_1.cs)]</span></span>  
  
 <span data-ttu-id="3958e-108">Para acceder a un elemento de una matriz, el índice del elemento deseado se encierra entre corchetes:</span><span class="sxs-lookup"><span data-stu-id="3958e-108">To access an element of an array, the index of the desired element is enclosed in brackets:</span></span>  
  
 <span data-ttu-id="3958e-109">[!code-cs[csRefOperators#44](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="3958e-109">[!code-cs[csRefOperators#44](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_2.cs)]</span></span>  
  
 <span data-ttu-id="3958e-110">Se produce una excepción si el índice de una matriz está fuera del intervalo.</span><span class="sxs-lookup"><span data-stu-id="3958e-110">An exception is thrown if an array index is out of range.</span></span>  
  
 <span data-ttu-id="3958e-111">No se puede sobrecargar el operador de indexación de la matriz. En cambio, los tipos pueden definir indexadores y propiedades que aceptan uno o varios parámetros.</span><span class="sxs-lookup"><span data-stu-id="3958e-111">The array indexing operator cannot be overloaded; however, types can define indexers, and properties that take one or more parameters.</span></span> <span data-ttu-id="3958e-112">Los parámetros del indexador van entre corchetes, al igual que los índices de matriz, pero se pueden declarar para que sean de cualquier tipo, a diferencia de los índices de matriz, que deben ser números enteros.</span><span class="sxs-lookup"><span data-stu-id="3958e-112">Indexer parameters are enclosed in square brackets, just like array indexes, but indexer parameters can be declared to be of any type, unlike array indexes, which must be integral.</span></span>  
  
 <span data-ttu-id="3958e-113">Por ejemplo, .NET Framework define un tipo `Hashtable` que asocia claves y valores de tipo arbitrario:</span><span class="sxs-lookup"><span data-stu-id="3958e-113">For example, the .NET Framework defines a `Hashtable` type that associates keys and values of arbitrary type:</span></span>  
  
 <span data-ttu-id="3958e-114">[!code-cs[csRefOperators#45](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="3958e-114">[!code-cs[csRefOperators#45](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_3.cs)]</span></span>  
  
 <span data-ttu-id="3958e-115">Los corchetes también se usan para especificar [atributos](../../../csharp/programming-guide/concepts/attributes/index.md):</span><span class="sxs-lookup"><span data-stu-id="3958e-115">Square brackets are also used to specify [Attributes](../../../csharp/programming-guide/concepts/attributes/index.md):</span></span>  
  
 <span data-ttu-id="3958e-116">[!code-cs[csRefOperators#46](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="3958e-116">[!code-cs[csRefOperators#46](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_4.cs)]</span></span>  
  
 <span data-ttu-id="3958e-117">Puede usar corchetes para indexar fuera de un puntero:</span><span class="sxs-lookup"><span data-stu-id="3958e-117">You can use square brackets to index off a pointer:</span></span>  
  
 <span data-ttu-id="3958e-118">[!code-cs[csRefOperators#47](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="3958e-118">[!code-cs[csRefOperators#47](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_5.cs)]</span></span>  
  
 <span data-ttu-id="3958e-119">No se realiza ninguna comprobación de límites.</span><span class="sxs-lookup"><span data-stu-id="3958e-119">No bounds checking is performed.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="3958e-120">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="3958e-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3958e-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="3958e-121">See Also</span></span>  
 <span data-ttu-id="3958e-122">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="3958e-122">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="3958e-123">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="3958e-123">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="3958e-124">[Operadores de C#](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="3958e-124">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 <span data-ttu-id="3958e-125">[Arrays](../../../csharp/programming-guide/arrays/index.md)  (Matrices)</span><span class="sxs-lookup"><span data-stu-id="3958e-125">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span></span>  
 <span data-ttu-id="3958e-126">[Indexers](../../../csharp/programming-guide/indexers/index.md)  (Indexadores)</span><span class="sxs-lookup"><span data-stu-id="3958e-126">[Indexers](../../../csharp/programming-guide/indexers/index.md) </span></span>  
 <span data-ttu-id="3958e-127">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span><span class="sxs-lookup"><span data-stu-id="3958e-127">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span></span>  
 [<span data-ttu-id="3958e-128">fixed (instrucción)</span><span class="sxs-lookup"><span data-stu-id="3958e-128">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)

