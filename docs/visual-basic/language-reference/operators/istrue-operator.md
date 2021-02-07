---
description: 'Más información acerca de: operador IsTrue (Visual Basic)'
title: Operador IsTrue
ms.date: 07/20/2015
f1_keywords:
- vb.istrue
helpviewer_keywords:
- IsTrue operator [Visual Basic]
- OrElse operator [Visual Basic]
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
ms.openlocfilehash: 50b618c888ce988da5241041fb2f728e0a581c70
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99665658"
---
# <a name="istrue-operator-visual-basic"></a><span data-ttu-id="13577-103">IsTrue (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="13577-103">IsTrue Operator (Visual Basic)</span></span>

<span data-ttu-id="13577-104">Determina si una expresión es `True` .</span><span class="sxs-lookup"><span data-stu-id="13577-104">Determines whether an expression is `True`.</span></span>  
  
 <span data-ttu-id="13577-105">No se puede llamar a `IsTrue` explícitamente en el código, pero el compilador de Visual Basic puede utilizarlo para generar código a partir de `OrElse` cláusulas.</span><span class="sxs-lookup"><span data-stu-id="13577-105">You cannot call `IsTrue` explicitly in your code, but the Visual Basic compiler can use it to generate code from `OrElse` clauses.</span></span> <span data-ttu-id="13577-106">Si define una clase o estructura y, a continuación, usa una variable de ese tipo en una `OrElse` cláusula, debe definir `IsTrue` en esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="13577-106">If you define a class or structure and then use a variable of that type in an `OrElse` clause, you must define `IsTrue` on that class or structure.</span></span>  
  
 <span data-ttu-id="13577-107">El compilador tiene en cuenta los `IsTrue` `IsFalse` operadores y como un *par coincidente*.</span><span class="sxs-lookup"><span data-stu-id="13577-107">The compiler considers the `IsTrue` and `IsFalse` operators as a *matched pair*.</span></span> <span data-ttu-id="13577-108">Esto significa que si define uno de ellos, también debe definir el otro.</span><span class="sxs-lookup"><span data-stu-id="13577-108">This means that if you define one of them, you must also define the other one.</span></span>  
  
## <a name="compiler-use-of-istrue"></a><span data-ttu-id="13577-109">Uso del compilador de IsTrue</span><span class="sxs-lookup"><span data-stu-id="13577-109">Compiler Use of IsTrue</span></span>  

 <span data-ttu-id="13577-110">Cuando haya definido una clase o estructura, puede usar una variable de ese tipo en una `For` `If` instrucción,, `Else If` o `While` , o en una `When` cláusula.</span><span class="sxs-lookup"><span data-stu-id="13577-110">When you have defined a class or structure, you can use a variable of that type in a `For`, `If`, `Else If`, or `While` statement, or in a `When` clause.</span></span> <span data-ttu-id="13577-111">Si lo hace, el compilador requiere un operador que convierta el tipo en un `Boolean` valor para que pueda probar una condición.</span><span class="sxs-lookup"><span data-stu-id="13577-111">If you do this, the compiler requires an operator that converts your type into a `Boolean` value so it can test a condition.</span></span> <span data-ttu-id="13577-112">Busca un operador adecuado en el orden siguiente:</span><span class="sxs-lookup"><span data-stu-id="13577-112">It searches for a suitable operator in the following order:</span></span>  
  
1. <span data-ttu-id="13577-113">Un operador de conversión de ampliación de la clase o estructura a `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="13577-113">A widening conversion operator from your class or structure to `Boolean`.</span></span>  
  
2. <span data-ttu-id="13577-114">Un operador de conversión de ampliación de la clase o estructura a `Boolean?` .</span><span class="sxs-lookup"><span data-stu-id="13577-114">A widening conversion operator from your class or structure to `Boolean?`.</span></span>  
  
3. <span data-ttu-id="13577-115">`IsTrue`Operador de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="13577-115">The `IsTrue` operator on your class or structure.</span></span>  
  
4. <span data-ttu-id="13577-116">Una conversión de restricción en `Boolean?` que no implica una conversión de `Boolean` a `Boolean?` .</span><span class="sxs-lookup"><span data-stu-id="13577-116">A narrowing conversion to `Boolean?` that does not involve a conversion from `Boolean` to `Boolean?`.</span></span>  
  
5. <span data-ttu-id="13577-117">Un operador de conversión de restricción de la clase o estructura a `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="13577-117">A narrowing conversion operator from your class or structure to `Boolean`.</span></span>  
  
 <span data-ttu-id="13577-118">Si no ha definido ninguna conversión a `Boolean` o a un `IsTrue` operador, el compilador indicará un error.</span><span class="sxs-lookup"><span data-stu-id="13577-118">If you have not defined any conversion to `Boolean` or an `IsTrue` operator, the compiler signals an error.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="13577-119">El `IsTrue` operador se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando su operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="13577-119">The `IsTrue` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="13577-120">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="13577-120">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="13577-121">Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="13577-121">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="13577-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="13577-122">Example</span></span>  

 <span data-ttu-id="13577-123">En el ejemplo de código siguiente se define el contorno de una estructura que incluye definiciones para los `IsFalse` `IsTrue` operadores y.</span><span class="sxs-lookup"><span data-stu-id="13577-123">The following code example defines the outline of a structure that includes definitions for the `IsFalse` and `IsTrue` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="13577-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="13577-124">See also</span></span>

- [<span data-ttu-id="13577-125">Operador IsFalse</span><span class="sxs-lookup"><span data-stu-id="13577-125">IsFalse Operator</span></span>](isfalse-operator.md)
- [<span data-ttu-id="13577-126">Procedimiento para definir un operador</span><span class="sxs-lookup"><span data-stu-id="13577-126">How to: Define an Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="13577-127">Operador OrElse</span><span class="sxs-lookup"><span data-stu-id="13577-127">OrElse Operator</span></span>](orelse-operator.md)
