---
title: IsTrue (Operador) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.istrue
helpviewer_keywords:
- IsTrue operator [Visual Basic]
- OrElse operator [Visual Basic]
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
ms.openlocfilehash: bf81384b0cecfd1ee3d438e4463949381279a181
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "43003195"
---
# <a name="istrue-operator-visual-basic"></a><span data-ttu-id="b5a3a-102">IsTrue (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b5a3a-102">IsTrue Operator (Visual Basic)</span></span>
<span data-ttu-id="b5a3a-103">Determina si una expresión es `True`.</span><span class="sxs-lookup"><span data-stu-id="b5a3a-103">Determines whether an expression is `True`.</span></span>  
  
 <span data-ttu-id="b5a3a-104">No se puede llamar a `IsTrue` explícitamente en el código, pero el de Visual Basic compilador puede usar para generar código desde `OrElse` cláusulas.</span><span class="sxs-lookup"><span data-stu-id="b5a3a-104">You cannot call `IsTrue` explicitly in your code, but the Visual Basic compiler can use it to generate code from `OrElse` clauses.</span></span> <span data-ttu-id="b5a3a-105">Si se define una clase o estructura y, a continuación, utilizar una variable de ese tipo en un `OrElse` cláusula, debe definir `IsTrue` en esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="b5a3a-105">If you define a class or structure and then use a variable of that type in an `OrElse` clause, you must define `IsTrue` on that class or structure.</span></span>  
  
 <span data-ttu-id="b5a3a-106">El compilador considera que el `IsTrue` y `IsFalse` operadores como un *par coincidente*.</span><span class="sxs-lookup"><span data-stu-id="b5a3a-106">The compiler considers the `IsTrue` and `IsFalse` operators as a *matched pair*.</span></span> <span data-ttu-id="b5a3a-107">Esto significa que si define uno de ellos, también debe definir el otro.</span><span class="sxs-lookup"><span data-stu-id="b5a3a-107">This means that if you define one of them, you must also define the other one.</span></span>  
  
## <a name="compiler-use-of-istrue"></a><span data-ttu-id="b5a3a-108">Uso del compilador de IsTrue</span><span class="sxs-lookup"><span data-stu-id="b5a3a-108">Compiler Use of IsTrue</span></span>  
 <span data-ttu-id="b5a3a-109">Cuando haya definido una clase o estructura, puede usar una variable de ese tipo en un `For`, `If`, `Else If`, o `While` instrucción, o en un `When` cláusula.</span><span class="sxs-lookup"><span data-stu-id="b5a3a-109">When you have defined a class or structure, you can use a variable of that type in a `For`, `If`, `Else If`, or `While` statement, or in a `When` clause.</span></span> <span data-ttu-id="b5a3a-110">Si lo hace, el compilador requiere un operador que convierte su tipo en un `Boolean` para que pueda probar una condición de valor.</span><span class="sxs-lookup"><span data-stu-id="b5a3a-110">If you do this, the compiler requires an operator that converts your type into a `Boolean` value so it can test a condition.</span></span> <span data-ttu-id="b5a3a-111">Busca un operador adecuado en el orden siguiente:</span><span class="sxs-lookup"><span data-stu-id="b5a3a-111">It searches for a suitable operator in the following order:</span></span>  
  
1.  <span data-ttu-id="b5a3a-112">Un operador de conversión de ampliación de la clase o estructura a `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="b5a3a-112">A widening conversion operator from your class or structure to `Boolean`.</span></span>  
  
2.  <span data-ttu-id="b5a3a-113">Un operador de conversión de ampliación de la clase o estructura a `Boolean?`.</span><span class="sxs-lookup"><span data-stu-id="b5a3a-113">A widening conversion operator from your class or structure to `Boolean?`.</span></span>  
  
3.  <span data-ttu-id="b5a3a-114">El `IsTrue` operador en la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="b5a3a-114">The `IsTrue` operator on your class or structure.</span></span>  
  
4.  <span data-ttu-id="b5a3a-115">Una conversión de restricción a `Boolean?` que no implica una conversión de `Boolean` a `Boolean?`.</span><span class="sxs-lookup"><span data-stu-id="b5a3a-115">A narrowing conversion to `Boolean?` that does not involve a conversion from `Boolean` to `Boolean?`.</span></span>  
  
5.  <span data-ttu-id="b5a3a-116">Un operador de conversión de restricción de la clase o estructura a `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="b5a3a-116">A narrowing conversion operator from your class or structure to `Boolean`.</span></span>  
  
 <span data-ttu-id="b5a3a-117">Si no ha definido ninguna conversión a `Boolean` o un `IsTrue` operador, el compilador señala un error.</span><span class="sxs-lookup"><span data-stu-id="b5a3a-117">If you have not defined any conversion to `Boolean` or an `IsTrue` operator, the compiler signals an error.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b5a3a-118">El `IsTrue` operador puede ser *sobrecargado*, lo que significa que una clase o estructura puede redefinir su comportamiento cuando su operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="b5a3a-118">The `IsTrue` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="b5a3a-119">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que conocer su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="b5a3a-119">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="b5a3a-120">Para obtener más información, consulte [procedimientos de operador](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="b5a3a-120">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5a3a-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b5a3a-121">Example</span></span>  
 <span data-ttu-id="b5a3a-122">En el ejemplo de código siguiente se define el esquema de una estructura que incluye las definiciones para el `IsFalse` y `IsTrue` operadores.</span><span class="sxs-lookup"><span data-stu-id="b5a3a-122">The following code example defines the outline of a structure that includes definitions for the `IsFalse` and `IsTrue` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/istrue-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="b5a3a-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="b5a3a-123">See Also</span></span>  
 [<span data-ttu-id="b5a3a-124">IsFalse (operador)</span><span class="sxs-lookup"><span data-stu-id="b5a3a-124">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)  
 [<span data-ttu-id="b5a3a-125">Definir un operador</span><span class="sxs-lookup"><span data-stu-id="b5a3a-125">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [<span data-ttu-id="b5a3a-126">OrElse (operador)</span><span class="sxs-lookup"><span data-stu-id="b5a3a-126">OrElse Operator</span></span>](../../../visual-basic/language-reference/operators/orelse-operator.md)
