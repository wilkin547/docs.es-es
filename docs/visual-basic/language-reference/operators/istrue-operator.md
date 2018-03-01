---
title: IsTrue (Operador) (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.istrue
helpviewer_keywords:
- IsTrue operator [Visual Basic]
- OrElse operator [Visual Basic]
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c0d261186ce68f06cec95251e815248a189f6da5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="istrue-operator-visual-basic"></a><span data-ttu-id="1c887-102">IsTrue (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1c887-102">IsTrue Operator (Visual Basic)</span></span>
<span data-ttu-id="1c887-103">Determina si una expresión es `True`.</span><span class="sxs-lookup"><span data-stu-id="1c887-103">Determines whether an expression is `True`.</span></span>  
  
 <span data-ttu-id="1c887-104">No se puede llamar `IsTrue` explícitamente en el código, pero Visual Basic compilador puede utilizarlo para generar código a partir `OrElse` cláusulas.</span><span class="sxs-lookup"><span data-stu-id="1c887-104">You cannot call `IsTrue` explicitly in your code, but the Visual Basic compiler can use it to generate code from `OrElse` clauses.</span></span> <span data-ttu-id="1c887-105">Si se define una clase o estructura y, a continuación, utilizar una variable de ese tipo en una `OrElse` cláusula, debe definir `IsTrue` en esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="1c887-105">If you define a class or structure and then use a variable of that type in an `OrElse` clause, you must define `IsTrue` on that class or structure.</span></span>  
  
 <span data-ttu-id="1c887-106">El compilador considera que el `IsTrue` y `IsFalse` operadores como un *par coincidente*.</span><span class="sxs-lookup"><span data-stu-id="1c887-106">The compiler considers the `IsTrue` and `IsFalse` operators as a *matched pair*.</span></span> <span data-ttu-id="1c887-107">Esto significa que si define uno de ellos, también debe definir el otro.</span><span class="sxs-lookup"><span data-stu-id="1c887-107">This means that if you define one of them, you must also define the other one.</span></span>  
  
## <a name="compiler-use-of-istrue"></a><span data-ttu-id="1c887-108">Uso de IsTrue del compilador</span><span class="sxs-lookup"><span data-stu-id="1c887-108">Compiler Use of IsTrue</span></span>  
 <span data-ttu-id="1c887-109">Una vez haya definido una clase o estructura, puede utilizar una variable de ese tipo en una `For`, `If`, `Else``If`, o `While` (instrucción), o en un `When` cláusula.</span><span class="sxs-lookup"><span data-stu-id="1c887-109">When you have defined a class or structure, you can use a variable of that type in a `For`, `If`, `Else``If`, or `While` statement, or in a `When` clause.</span></span> <span data-ttu-id="1c887-110">Si lo hace, el compilador requiere un operador que convierta el tipo en un `Boolean` valor para que pueda probar una condición.</span><span class="sxs-lookup"><span data-stu-id="1c887-110">If you do this, the compiler requires an operator that converts your type into a `Boolean` value so it can test a condition.</span></span> <span data-ttu-id="1c887-111">Busca un operador adecuado en el orden siguiente:</span><span class="sxs-lookup"><span data-stu-id="1c887-111">It searches for a suitable operator in the following order:</span></span>  
  
1.  <span data-ttu-id="1c887-112">Un operador de conversión de ampliación de la clase o estructura a `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="1c887-112">A widening conversion operator from your class or structure to `Boolean`.</span></span>  
  
2.  <span data-ttu-id="1c887-113">Un operador de conversión de ampliación de la clase o estructura a `Boolean?`.</span><span class="sxs-lookup"><span data-stu-id="1c887-113">A widening conversion operator from your class or structure to `Boolean?`.</span></span>  
  
3.  <span data-ttu-id="1c887-114">El `IsTrue` operador en la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="1c887-114">The `IsTrue` operator on your class or structure.</span></span>  
  
4.  <span data-ttu-id="1c887-115">Una conversión de restricción a `Boolean?` que implican una conversión de `Boolean` a `Boolean?`.</span><span class="sxs-lookup"><span data-stu-id="1c887-115">A narrowing conversion to `Boolean?` that does not involve a conversion from `Boolean` to `Boolean?`.</span></span>  
  
5.  <span data-ttu-id="1c887-116">Un operador de conversión de restricción de la clase o estructura a `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="1c887-116">A narrowing conversion operator from your class or structure to `Boolean`.</span></span>  
  
 <span data-ttu-id="1c887-117">Si no ha definido ninguna conversión a `Boolean` o un `IsTrue` (operador), el compilador señala un error.</span><span class="sxs-lookup"><span data-stu-id="1c887-117">If you have not defined any conversion to `Boolean` or an `IsTrue` operator, the compiler signals an error.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1c887-118">El `IsTrue` puede ser *sobrecargados*, lo que significa que una clase o estructura puede definir de nuevo su comportamiento cuando su operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="1c887-118">The `IsTrue` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="1c887-119">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que conocer su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="1c887-119">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="1c887-120">Para obtener más información, consulte [procedimientos de operadores](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="1c887-120">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c887-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1c887-121">Example</span></span>  
 <span data-ttu-id="1c887-122">En el ejemplo de código siguiente se define el esquema de una estructura que incluye las definiciones para la `IsFalse` y `IsTrue` operadores.</span><span class="sxs-lookup"><span data-stu-id="1c887-122">The following code example defines the outline of a structure that includes definitions for the `IsFalse` and `IsTrue` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/istrue-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="1c887-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c887-123">See Also</span></span>  
 [<span data-ttu-id="1c887-124">IsFalse (operador)</span><span class="sxs-lookup"><span data-stu-id="1c887-124">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)  
 [<span data-ttu-id="1c887-125">Definir un operador</span><span class="sxs-lookup"><span data-stu-id="1c887-125">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [<span data-ttu-id="1c887-126">OrElse (operador)</span><span class="sxs-lookup"><span data-stu-id="1c887-126">OrElse Operator</span></span>](../../../visual-basic/language-reference/operators/orelse-operator.md)
