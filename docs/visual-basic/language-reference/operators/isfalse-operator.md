---
title: IsFalse (Operador) (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d85fc51a75f82c65cf226b8239a8eee6585bd18a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="isfalse-operator-visual-basic"></a><span data-ttu-id="92f81-102">IsFalse (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="92f81-102">IsFalse Operator (Visual Basic)</span></span>
<span data-ttu-id="92f81-103">Determina si una expresión es `False`.</span><span class="sxs-lookup"><span data-stu-id="92f81-103">Determines whether an expression is `False`.</span></span>  
  
 <span data-ttu-id="92f81-104">No se puede llamar `IsFalse` explícitamente en el código, pero Visual Basic compilador puede utilizarlo para generar código a partir `AndAlso` cláusulas.</span><span class="sxs-lookup"><span data-stu-id="92f81-104">You cannot call `IsFalse` explicitly in your code, but the Visual Basic compiler can use it to generate code from `AndAlso` clauses.</span></span> <span data-ttu-id="92f81-105">Si se define una clase o estructura y, a continuación, utilizar una variable de ese tipo en una `AndAlso` cláusula, debe definir `IsFalse` en esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="92f81-105">If you define a class or structure and then use a variable of that type in an `AndAlso` clause, you must define `IsFalse` on that class or structure.</span></span>  
  
 <span data-ttu-id="92f81-106">El compilador considera que el `IsFalse` y `IsTrue` operadores como un *par coincidente*.</span><span class="sxs-lookup"><span data-stu-id="92f81-106">The compiler considers the `IsFalse` and `IsTrue` operators as a *matched pair*.</span></span> <span data-ttu-id="92f81-107">Esto significa que si define uno de ellos, también debe definir el otro.</span><span class="sxs-lookup"><span data-stu-id="92f81-107">This means that if you define one of them, you must also define the other one.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="92f81-108">El `IsFalse` puede ser *sobrecargados*, lo que significa que una clase o estructura puede definir de nuevo su comportamiento cuando su operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="92f81-108">The `IsFalse` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="92f81-109">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que conocer su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="92f81-109">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="92f81-110">Para obtener más información, consulte [procedimientos de operadores](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="92f81-110">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="92f81-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="92f81-111">Example</span></span>  
 <span data-ttu-id="92f81-112">En el ejemplo de código siguiente se define el esquema de una estructura que incluye las definiciones para la `IsFalse` y `IsTrue` operadores.</span><span class="sxs-lookup"><span data-stu-id="92f81-112">The following code example defines the outline of a structure that includes definitions for the `IsFalse` and `IsTrue` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/isfalse-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="92f81-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="92f81-113">See Also</span></span>  
 [<span data-ttu-id="92f81-114">IsTrue (operador)</span><span class="sxs-lookup"><span data-stu-id="92f81-114">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)  
 [<span data-ttu-id="92f81-115">Definir un operador</span><span class="sxs-lookup"><span data-stu-id="92f81-115">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [<span data-ttu-id="92f81-116">AndAlso (operador)</span><span class="sxs-lookup"><span data-stu-id="92f81-116">AndAlso Operator</span></span>](../../../visual-basic/language-reference/operators/andalso-operator.md)
