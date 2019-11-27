---
title: IsTrue (Operador)
ms.date: 07/20/2015
f1_keywords:
- vb.istrue
helpviewer_keywords:
- IsTrue operator [Visual Basic]
- OrElse operator [Visual Basic]
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
ms.openlocfilehash: 4b863eed8406a10b9a44d7139f8659ac5cb758ad
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349512"
---
# <a name="istrue-operator-visual-basic"></a><span data-ttu-id="4b7ad-102">IsTrue (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4b7ad-102">IsTrue Operator (Visual Basic)</span></span>
<span data-ttu-id="4b7ad-103">Determina si una expresión es `True`.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-103">Determines whether an expression is `True`.</span></span>  
  
 <span data-ttu-id="4b7ad-104">No se puede llamar a `IsTrue` explícitamente en el código, pero el compilador Visual Basic puede usarlo para generar código a partir de cláusulas `OrElse`.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-104">You cannot call `IsTrue` explicitly in your code, but the Visual Basic compiler can use it to generate code from `OrElse` clauses.</span></span> <span data-ttu-id="4b7ad-105">Si define una clase o estructura y, a continuación, usa una variable de ese tipo en una cláusula `OrElse`, debe definir `IsTrue` en esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-105">If you define a class or structure and then use a variable of that type in an `OrElse` clause, you must define `IsTrue` on that class or structure.</span></span>  
  
 <span data-ttu-id="4b7ad-106">El compilador tiene en cuenta los operadores `IsTrue` y `IsFalse` como un *par coincidente*.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-106">The compiler considers the `IsTrue` and `IsFalse` operators as a *matched pair*.</span></span> <span data-ttu-id="4b7ad-107">Esto significa que si define uno de ellos, también debe definir el otro.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-107">This means that if you define one of them, you must also define the other one.</span></span>  
  
## <a name="compiler-use-of-istrue"></a><span data-ttu-id="4b7ad-108">Uso del compilador de IsTrue</span><span class="sxs-lookup"><span data-stu-id="4b7ad-108">Compiler Use of IsTrue</span></span>  
 <span data-ttu-id="4b7ad-109">Cuando haya definido una clase o estructura, puede usar una variable de ese tipo en una instrucción `For`, `If`, `Else If`o `While`, o en una cláusula `When`.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-109">When you have defined a class or structure, you can use a variable of that type in a `For`, `If`, `Else If`, or `While` statement, or in a `When` clause.</span></span> <span data-ttu-id="4b7ad-110">Si lo hace, el compilador requiere un operador que convierta el tipo en un valor `Boolean` para que pueda probar una condición.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-110">If you do this, the compiler requires an operator that converts your type into a `Boolean` value so it can test a condition.</span></span> <span data-ttu-id="4b7ad-111">Busca un operador adecuado en el orden siguiente:</span><span class="sxs-lookup"><span data-stu-id="4b7ad-111">It searches for a suitable operator in the following order:</span></span>  
  
1. <span data-ttu-id="4b7ad-112">Operador de conversión de ampliación de la clase o estructura que se va a `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-112">A widening conversion operator from your class or structure to `Boolean`.</span></span>  
  
2. <span data-ttu-id="4b7ad-113">Operador de conversión de ampliación de la clase o estructura que se va a `Boolean?`.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-113">A widening conversion operator from your class or structure to `Boolean?`.</span></span>  
  
3. <span data-ttu-id="4b7ad-114">Operador de `IsTrue` en la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-114">The `IsTrue` operator on your class or structure.</span></span>  
  
4. <span data-ttu-id="4b7ad-115">Conversión de restricción a `Boolean?` que no implica una conversión de `Boolean` a `Boolean?`.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-115">A narrowing conversion to `Boolean?` that does not involve a conversion from `Boolean` to `Boolean?`.</span></span>  
  
5. <span data-ttu-id="4b7ad-116">Operador de conversión de restricción de la clase o estructura que se va a `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-116">A narrowing conversion operator from your class or structure to `Boolean`.</span></span>  
  
 <span data-ttu-id="4b7ad-117">Si no ha definido ninguna conversión a `Boolean` o a un operador de `IsTrue`, el compilador indicará un error.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-117">If you have not defined any conversion to `Boolean` or an `IsTrue` operator, the compiler signals an error.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4b7ad-118">El operador de `IsTrue` se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando su operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-118">The `IsTrue` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="4b7ad-119">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-119">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="4b7ad-120">Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="4b7ad-120">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b7ad-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4b7ad-121">Example</span></span>  
 <span data-ttu-id="4b7ad-122">En el ejemplo de código siguiente se define el contorno de una estructura que incluye definiciones para los operadores `IsFalse` y `IsTrue`.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-122">The following code example defines the outline of a structure that includes definitions for the `IsFalse` and `IsTrue` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="4b7ad-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b7ad-123">See also</span></span>

- [<span data-ttu-id="4b7ad-124">IsFalse (operador)</span><span class="sxs-lookup"><span data-stu-id="4b7ad-124">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [<span data-ttu-id="4b7ad-125">Definir un operador</span><span class="sxs-lookup"><span data-stu-id="4b7ad-125">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="4b7ad-126">OrElse (operador)</span><span class="sxs-lookup"><span data-stu-id="4b7ad-126">OrElse Operator</span></span>](../../../visual-basic/language-reference/operators/orelse-operator.md)
