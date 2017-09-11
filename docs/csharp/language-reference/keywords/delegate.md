---
title: delegado (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- delegate_CSharpKeyword
- delegate
- CS0123
dev_langs:
- CSharp
helpviewer_keywords:
- delegate keyword [C#]
- function pointers [C#]
ms.assetid: 0bb8cb6d-2f87-47c7-9d1f-d65c1cd01e9f
caps.latest.revision: 24
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
ms.openlocfilehash: 402eedd0c59b5c95e1a9b44faca66ccb4d4e04e7
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="delegate-c-reference"></a><span data-ttu-id="fe18e-102">delegado (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="fe18e-102">delegate (C# Reference)</span></span>
<span data-ttu-id="fe18e-103">La declaración de un tipo delegado es similar a una firma de método.</span><span class="sxs-lookup"><span data-stu-id="fe18e-103">The declaration of a delegate type is similar to a method signature.</span></span> <span data-ttu-id="fe18e-104">Tiene un valor devuelto y un número cualquiera de parámetros de cualquier tipo:</span><span class="sxs-lookup"><span data-stu-id="fe18e-104">It has a return value and any number of parameters of any type:</span></span>  
  
```  
public delegate void TestDelegate(string message);  
public delegate int TestDelegate(MyType m, long num);  
```  
  
 <span data-ttu-id="fe18e-105">Un `delegate` es un tipo de referencia que puede usarse para encapsular un método con nombre o anónimo.</span><span class="sxs-lookup"><span data-stu-id="fe18e-105">A `delegate` is a reference type that can be used to encapsulate a named or an anonymous method.</span></span> <span data-ttu-id="fe18e-106">Los delegados son similares a los punteros de función en C++; pero son más seguros y proporcionan mayor seguridad de tipos.</span><span class="sxs-lookup"><span data-stu-id="fe18e-106">Delegates are similar to function pointers in C++; however, delegates are type-safe and secure.</span></span> <span data-ttu-id="fe18e-107">Para las aplicaciones de delegados, vea [Delegados](../../../csharp/programming-guide/delegates/index.md) y [Delegados genéricos](../../../csharp/programming-guide/generics/generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="fe18e-107">For applications of delegates, see [Delegates](../../../csharp/programming-guide/delegates/index.md) and [Generic Delegates](../../../csharp/programming-guide/generics/generic-delegates.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe18e-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fe18e-108">Remarks</span></span>  
 <span data-ttu-id="fe18e-109">Los delegados son la base de los [eventos](../../../csharp/programming-guide/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="fe18e-109">Delegates are the basis for [Events](../../../csharp/programming-guide/events/index.md).</span></span>  
  
 <span data-ttu-id="fe18e-110">Se pueden crear instancias de un delegado asociándolo a un método con nombre o anónimo.</span><span class="sxs-lookup"><span data-stu-id="fe18e-110">A delegate can be instantiated by associating it either with a named or anonymous method.</span></span> <span data-ttu-id="fe18e-111">Para obtener más información, vea [Métodos con nombre](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) y [Métodos anónimos](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).</span><span class="sxs-lookup"><span data-stu-id="fe18e-111">For more information, see [Named Methods](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) and [Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).</span></span>  
  
 <span data-ttu-id="fe18e-112">Para crear instancias del delegado debe usarse un método o una expresión lambda que tenga un tipo de valor devuelto y parámetros de entrada compatibles.</span><span class="sxs-lookup"><span data-stu-id="fe18e-112">The delegate must be instantiated with a method or lambda expression that has a compatible return type and input parameters.</span></span> <span data-ttu-id="fe18e-113">Para obtener más información sobre el grado de variación permitida en la firma de método, vea [Varianza en delegados](http://msdn.microsoft.com/library/e3b98197-6c5b-4e55-9c6e-9739b60645ca).</span><span class="sxs-lookup"><span data-stu-id="fe18e-113">For more information on the degree of variance that is allowed in the method signature, see [Variance in Delegates](http://msdn.microsoft.com/library/e3b98197-6c5b-4e55-9c6e-9739b60645ca).</span></span> <span data-ttu-id="fe18e-114">Para el uso con métodos anónimos, el delegado y el código que se van a asociar se declaran juntos.</span><span class="sxs-lookup"><span data-stu-id="fe18e-114">For use with anonymous methods, the delegate and the code to be associated with it are declared together.</span></span> <span data-ttu-id="fe18e-115">En esta sección se describen las dos maneras de crear instancias de delegados.</span><span class="sxs-lookup"><span data-stu-id="fe18e-115">Both ways of instantiating delegates are discussed in this section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe18e-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fe18e-116">Example</span></span>  
 <span data-ttu-id="fe18e-117">[!code-cs[csrefKeywordsTypes#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/delegate_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="fe18e-117">[!code-cs[csrefKeywordsTypes#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/delegate_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="fe18e-118">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="fe18e-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fe18e-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe18e-119">See Also</span></span>  
 <span data-ttu-id="fe18e-120">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="fe18e-120">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="fe18e-121">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="fe18e-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="fe18e-122">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="fe18e-122">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="fe18e-123">[Tipos de referencia](../../../csharp/language-reference/keywords/reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="fe18e-123">[Reference Types](../../../csharp/language-reference/keywords/reference-types.md) </span></span>  
 <span data-ttu-id="fe18e-124">[Delegados](../../../csharp/programming-guide/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="fe18e-124">[Delegates](../../../csharp/programming-guide/delegates/index.md) </span></span>  
 <span data-ttu-id="fe18e-125">[Eventos](../../../csharp/programming-guide/events/index.md) </span><span class="sxs-lookup"><span data-stu-id="fe18e-125">[Events](../../../csharp/programming-guide/events/index.md) </span></span>  
 <span data-ttu-id="fe18e-126">[Delegados con métodos con nombre y delegados con métodos anónimos](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) </span><span class="sxs-lookup"><span data-stu-id="fe18e-126">[Delegates with Named vs. Anonymous Methods](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) </span></span>  
 [<span data-ttu-id="fe18e-127">Métodos anónimos</span><span class="sxs-lookup"><span data-stu-id="fe18e-127">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)

