---
title: . Operador (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- ._CSharpKeyword
helpviewer_keywords:
- member access operator (.) [C#]
- . operator [C#]
- dot operator (.) [C#]
ms.assetid: a1f54b52-b686-4ae5-a48e-a2a9ebd0eb7b
ms.openlocfilehash: a092c1a916e3dc4bf6d96660c532540945e57554
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2018
ms.locfileid: "43408012"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="14128-103">.</span><span class="sxs-lookup"><span data-stu-id="14128-103">.</span></span> <span data-ttu-id="14128-104">Operador (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="14128-104">Operator (C# Reference)</span></span>
<span data-ttu-id="14128-105">El operador punto (`.`) se usa para el acceso a miembros.</span><span class="sxs-lookup"><span data-stu-id="14128-105">The dot operator (`.`) is used for member access.</span></span> <span data-ttu-id="14128-106">El operador punto especifica un miembro de un tipo o espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="14128-106">The dot operator specifies a member of a type or namespace.</span></span> <span data-ttu-id="14128-107">Por ejemplo, el operador punto se usa para tener acceso a métodos específicos de las bibliotecas de clases de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="14128-107">For example, the dot operator is used to access specific methods within the .NET Framework class libraries:</span></span>  
  
 [!code-csharp[csRefOperators#16](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_1.cs)]  
  
 <span data-ttu-id="14128-108">Por ejemplo, considere la siguiente clase:</span><span class="sxs-lookup"><span data-stu-id="14128-108">For example, consider the following class:</span></span>  
  
 [!code-csharp[csRefOperators#17](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_2.cs)]  
  
 [!code-csharp[csRefOperators#18](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_3.cs)]  
  
 <span data-ttu-id="14128-109">La variable `s` tiene dos miembros, `a` y `b`. Para obtener acceso a ellos, use el operador punto:</span><span class="sxs-lookup"><span data-stu-id="14128-109">The variable `s` has two members, `a` and `b`; to access them, use the dot operator:</span></span>  
  
 [!code-csharp[csRefOperators#19](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_4.cs)]  
  
 <span data-ttu-id="14128-110">El punto también se usa para formar nombres completos, que son nombres que especifican el espacio de nombres o la interfaz, por ejemplo, a los que pertenecen.</span><span class="sxs-lookup"><span data-stu-id="14128-110">The dot is also used to form qualified names, which are names that specify the namespace or interface, for example, to which they belong.</span></span>  
  
 [!code-csharp[csRefOperators#20](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_5.cs)]  
  
 <span data-ttu-id="14128-111">La directiva using hace que algunos elementos de calificación de nombres sean opcionales:</span><span class="sxs-lookup"><span data-stu-id="14128-111">The using directive makes some name qualification optional:</span></span>  
  
 [!code-csharp[csRefOperators#21](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_6.cs)]  
  
 <span data-ttu-id="14128-112">Pero cuando un identificador es ambiguo, debe calificarse:</span><span class="sxs-lookup"><span data-stu-id="14128-112">But when an identifier is ambiguous, it must be qualified:</span></span>  
  
 [!code-csharp[csRefOperators#22](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_7.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="14128-113">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="14128-113">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="14128-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="14128-114">See Also</span></span>

- [<span data-ttu-id="14128-115">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="14128-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="14128-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="14128-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="14128-117">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="14128-117">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
