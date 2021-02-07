---
description: 'Más información acerca de: operador IsFalse (Visual Basic)'
title: Operador IsFalse
ms.date: 07/20/2015
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
ms.openlocfilehash: 190399dd29ba2d643bd26dfe4f6191211c9a3740
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99665710"
---
# <a name="isfalse-operator-visual-basic"></a><span data-ttu-id="e508f-103">IsFalse (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e508f-103">IsFalse Operator (Visual Basic)</span></span>

<span data-ttu-id="e508f-104">Determina si una expresión es `False` .</span><span class="sxs-lookup"><span data-stu-id="e508f-104">Determines whether an expression is `False`.</span></span>  
  
 <span data-ttu-id="e508f-105">No se puede llamar a `IsFalse` explícitamente en el código, pero el compilador de Visual Basic puede utilizarlo para generar código a partir de `AndAlso` cláusulas.</span><span class="sxs-lookup"><span data-stu-id="e508f-105">You cannot call `IsFalse` explicitly in your code, but the Visual Basic compiler can use it to generate code from `AndAlso` clauses.</span></span> <span data-ttu-id="e508f-106">Si define una clase o estructura y, a continuación, usa una variable de ese tipo en una `AndAlso` cláusula, debe definir `IsFalse` en esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="e508f-106">If you define a class or structure and then use a variable of that type in an `AndAlso` clause, you must define `IsFalse` on that class or structure.</span></span>  
  
 <span data-ttu-id="e508f-107">El compilador tiene en cuenta los `IsFalse` `IsTrue` operadores y como un *par coincidente*.</span><span class="sxs-lookup"><span data-stu-id="e508f-107">The compiler considers the `IsFalse` and `IsTrue` operators as a *matched pair*.</span></span> <span data-ttu-id="e508f-108">Esto significa que si define uno de ellos, también debe definir el otro.</span><span class="sxs-lookup"><span data-stu-id="e508f-108">This means that if you define one of them, you must also define the other one.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e508f-109">El `IsFalse` operador se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando su operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="e508f-109">The `IsFalse` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="e508f-110">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="e508f-110">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="e508f-111">Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="e508f-111">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e508f-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e508f-112">Example</span></span>  

 <span data-ttu-id="e508f-113">En el ejemplo de código siguiente se define el contorno de una estructura que incluye definiciones para los `IsFalse` `IsTrue` operadores y.</span><span class="sxs-lookup"><span data-stu-id="e508f-113">The following code example defines the outline of a structure that includes definitions for the `IsFalse` and `IsTrue` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="e508f-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="e508f-114">See also</span></span>

- [<span data-ttu-id="e508f-115">Operador IsTrue</span><span class="sxs-lookup"><span data-stu-id="e508f-115">IsTrue Operator</span></span>](istrue-operator.md)
- [<span data-ttu-id="e508f-116">Procedimiento para definir un operador</span><span class="sxs-lookup"><span data-stu-id="e508f-116">How to: Define an Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="e508f-117">Operador AndAlso</span><span class="sxs-lookup"><span data-stu-id="e508f-117">AndAlso Operator</span></span>](andalso-operator.md)
