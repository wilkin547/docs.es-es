---
title: IsFalse (Operador) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
ms.openlocfilehash: e84b2162eb0763725f05bc52d5c4223d7c430b81
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33600053"
---
# <a name="isfalse-operator-visual-basic"></a><span data-ttu-id="7a81b-102">IsFalse (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7a81b-102">IsFalse Operator (Visual Basic)</span></span>
<span data-ttu-id="7a81b-103">Determina si una expresión es `False`.</span><span class="sxs-lookup"><span data-stu-id="7a81b-103">Determines whether an expression is `False`.</span></span>  
  
 <span data-ttu-id="7a81b-104">No se puede llamar `IsFalse` explícitamente en el código, pero Visual Basic compilador puede utilizarlo para generar código a partir `AndAlso` cláusulas.</span><span class="sxs-lookup"><span data-stu-id="7a81b-104">You cannot call `IsFalse` explicitly in your code, but the Visual Basic compiler can use it to generate code from `AndAlso` clauses.</span></span> <span data-ttu-id="7a81b-105">Si se define una clase o estructura y, a continuación, utilizar una variable de ese tipo en una `AndAlso` cláusula, debe definir `IsFalse` en esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="7a81b-105">If you define a class or structure and then use a variable of that type in an `AndAlso` clause, you must define `IsFalse` on that class or structure.</span></span>  
  
 <span data-ttu-id="7a81b-106">El compilador considera que el `IsFalse` y `IsTrue` operadores como un *par coincidente*.</span><span class="sxs-lookup"><span data-stu-id="7a81b-106">The compiler considers the `IsFalse` and `IsTrue` operators as a *matched pair*.</span></span> <span data-ttu-id="7a81b-107">Esto significa que si define uno de ellos, también debe definir el otro.</span><span class="sxs-lookup"><span data-stu-id="7a81b-107">This means that if you define one of them, you must also define the other one.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7a81b-108">El `IsFalse` puede ser *sobrecargados*, lo que significa que una clase o estructura puede definir de nuevo su comportamiento cuando su operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="7a81b-108">The `IsFalse` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="7a81b-109">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que conocer su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="7a81b-109">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="7a81b-110">Para obtener más información, consulte [procedimientos de operadores](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="7a81b-110">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a81b-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7a81b-111">Example</span></span>  
 <span data-ttu-id="7a81b-112">En el ejemplo de código siguiente se define el esquema de una estructura que incluye las definiciones para la `IsFalse` y `IsTrue` operadores.</span><span class="sxs-lookup"><span data-stu-id="7a81b-112">The following code example defines the outline of a structure that includes definitions for the `IsFalse` and `IsTrue` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/isfalse-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="7a81b-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="7a81b-113">See Also</span></span>  
 [<span data-ttu-id="7a81b-114">IsTrue (operador)</span><span class="sxs-lookup"><span data-stu-id="7a81b-114">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)  
 [<span data-ttu-id="7a81b-115">Definir un operador</span><span class="sxs-lookup"><span data-stu-id="7a81b-115">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [<span data-ttu-id="7a81b-116">AndAlso (operador)</span><span class="sxs-lookup"><span data-stu-id="7a81b-116">AndAlso Operator</span></span>](../../../visual-basic/language-reference/operators/andalso-operator.md)
