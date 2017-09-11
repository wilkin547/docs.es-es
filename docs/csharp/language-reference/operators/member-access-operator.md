---
title: . Operador (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ._CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- member access operator (.) [C#]
- . operator [C#]
- dot operator (.) [C#]
ms.assetid: a1f54b52-b686-4ae5-a48e-a2a9ebd0eb7b
caps.latest.revision: 21
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
ms.openlocfilehash: fdc7c1821548509f3a3750aef2836c034f7aa53b
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="4b568-103">.</span><span class="sxs-lookup"><span data-stu-id="4b568-103">.</span></span> <span data-ttu-id="4b568-104">Operador (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="4b568-104">Operator (C# Reference)</span></span>
<span data-ttu-id="4b568-105">El operador punto (`.`) se usa para el acceso a miembros.</span><span class="sxs-lookup"><span data-stu-id="4b568-105">The dot operator (`.`) is used for member access.</span></span> <span data-ttu-id="4b568-106">El operador punto especifica un miembro de un tipo o espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="4b568-106">The dot operator specifies a member of a type or namespace.</span></span> <span data-ttu-id="4b568-107">Por ejemplo, el operador punto se usa para tener acceso a métodos específicos de las bibliotecas de clases de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="4b568-107">For example, the dot operator is used to access specific methods within the .NET Framework class libraries:</span></span>  
  
 <span data-ttu-id="4b568-108">[!code-cs[csRefOperators#16](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="4b568-108">[!code-cs[csRefOperators#16](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_1.cs)]</span></span>  
  
 <span data-ttu-id="4b568-109">Por ejemplo, considere la siguiente clase:</span><span class="sxs-lookup"><span data-stu-id="4b568-109">For example, consider the following class:</span></span>  
  
 <span data-ttu-id="4b568-110">[!code-cs[csRefOperators#17](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="4b568-110">[!code-cs[csRefOperators#17](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_2.cs)]</span></span>  
  
 <span data-ttu-id="4b568-111">[!code-cs[csRefOperators#18](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="4b568-111">[!code-cs[csRefOperators#18](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_3.cs)]</span></span>  
  
 <span data-ttu-id="4b568-112">La variable `s` tiene dos miembros, `a` y `b`. Para obtener acceso a ellos, use el operador punto:</span><span class="sxs-lookup"><span data-stu-id="4b568-112">The variable `s` has two members, `a` and `b`; to access them, use the dot operator:</span></span>  
  
 <span data-ttu-id="4b568-113">[!code-cs[csRefOperators#19](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="4b568-113">[!code-cs[csRefOperators#19](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_4.cs)]</span></span>  
  
 <span data-ttu-id="4b568-114">El punto también se usa para formar nombres completos, que son nombres que especifican el espacio de nombres o la interfaz, por ejemplo, a los que pertenecen.</span><span class="sxs-lookup"><span data-stu-id="4b568-114">The dot is also used to form qualified names, which are names that specify the namespace or interface, for example, to which they belong.</span></span>  
  
 <span data-ttu-id="4b568-115">[!code-cs[csRefOperators#20](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="4b568-115">[!code-cs[csRefOperators#20](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_5.cs)]</span></span>  
  
 <span data-ttu-id="4b568-116">La directiva using hace que algunos elementos de calificación de nombres sean opcionales:</span><span class="sxs-lookup"><span data-stu-id="4b568-116">The using directive makes some name qualification optional:</span></span>  
  
 <span data-ttu-id="4b568-117">[!code-cs[csRefOperators#21](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="4b568-117">[!code-cs[csRefOperators#21](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_6.cs)]</span></span>  
  
 <span data-ttu-id="4b568-118">Pero cuando un identificador es ambiguo, debe calificarse:</span><span class="sxs-lookup"><span data-stu-id="4b568-118">But when an identifier is ambiguous, it must be qualified:</span></span>  
  
 <span data-ttu-id="4b568-119">[!code-cs[csRefOperators#22](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="4b568-119">[!code-cs[csRefOperators#22](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_7.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="4b568-120">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="4b568-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4b568-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b568-121">See Also</span></span>  
 <span data-ttu-id="4b568-122">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="4b568-122">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="4b568-123">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="4b568-123">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="4b568-124">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="4b568-124">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

