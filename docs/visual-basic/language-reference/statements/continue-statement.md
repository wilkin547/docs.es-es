---
title: Continue (Instrucción, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.continue
helpviewer_keywords:
- Continue statement [Visual Basic]
- loops, transferring to next iteration
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
ms.openlocfilehash: 9ee5fb19db6eafeb7e4bed12935d0b950d6368d6
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005105"
---
# <a name="continue-statement-visual-basic"></a><span data-ttu-id="37049-102">Continue (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37049-102">Continue Statement (Visual Basic)</span></span>
<span data-ttu-id="37049-103">Transfiere el control inmediatamente a la siguiente iteración de un bucle.</span><span class="sxs-lookup"><span data-stu-id="37049-103">Transfers control immediately to the next iteration of a loop.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37049-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="37049-104">Syntax</span></span>  
  
```vb  
Continue { Do | For | While }  
```  
  
## <a name="remarks"></a><span data-ttu-id="37049-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="37049-105">Remarks</span></span>  
 <span data-ttu-id="37049-106">Puede transferir desde dentro de un bucle `Do`, `For` o `While` a la siguiente iteración del bucle.</span><span class="sxs-lookup"><span data-stu-id="37049-106">You can transfer from inside a `Do`, `For`, or `While` loop to the next iteration of that loop.</span></span> <span data-ttu-id="37049-107">El control pasa inmediatamente a la prueba de la condición de bucle, que es equivalente a transferir a la instrucción `For` o `While`, o a la instrucción `Do` o `Loop` que contiene la cláusula `Until` o `While`.</span><span class="sxs-lookup"><span data-stu-id="37049-107">Control passes immediately to the loop condition test, which is equivalent to transferring to the `For` or `While` statement, or to the `Do` or `Loop` statement that contains the `Until` or `While` clause.</span></span>  
  
 <span data-ttu-id="37049-108">Puede usar `Continue` en cualquier ubicación del bucle que permita las transferencias.</span><span class="sxs-lookup"><span data-stu-id="37049-108">You can use `Continue` at any location in the loop that allows transfers.</span></span> <span data-ttu-id="37049-109">Las reglas que permiten la transferencia de control son las mismas que con la [instrucción Goto](../../../visual-basic/language-reference/statements/goto-statement.md).</span><span class="sxs-lookup"><span data-stu-id="37049-109">The rules allowing transfer of control are the same as with the [GoTo Statement](../../../visual-basic/language-reference/statements/goto-statement.md).</span></span>  
  
 <span data-ttu-id="37049-110">Por ejemplo, si un bucle está contenido completamente dentro de un bloque `Try`, un bloque `Catch` o un bloque `Finally`, puede usar `Continue` para transferir fuera del bucle.</span><span class="sxs-lookup"><span data-stu-id="37049-110">For example, if a loop is totally contained within a `Try` block, a `Catch` block, or a `Finally` block, you can use `Continue` to transfer out of the loop.</span></span> <span data-ttu-id="37049-111">Por otra parte, si la estructura `Try`... `End Try` está contenida en el bucle, no se puede usar `Continue` para transferir el control fuera del bloque `Finally`, y se puede usar para transferir fuera de un bloque `Try` o `Catch` solo si se transfiere completamente fuera del @no_ _ t-6... `End Try` (estructura).</span><span class="sxs-lookup"><span data-stu-id="37049-111">If, on the other hand, the `Try`...`End Try` structure is contained within the loop, you cannot use `Continue` to transfer control out of the `Finally` block, and you can use it to transfer out of a `Try` or `Catch` block only if you transfer completely out of the `Try`...`End Try` structure.</span></span>  
  
 <span data-ttu-id="37049-112">Si tiene bucles anidados del mismo tipo, por ejemplo, un bucle @no__t 0 dentro de otro bucle `Do`, una instrucción `Continue Do` omite la siguiente iteración del bucle `Do` más interno que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="37049-112">If you have nested loops of the same type, for example a `Do` loop within another `Do` loop, a `Continue Do` statement skips to the next iteration of the innermost `Do` loop that contains it.</span></span> <span data-ttu-id="37049-113">No se puede usar `Continue` para pasar a la siguiente iteración de un bucle contenedor del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="37049-113">You cannot use `Continue` to skip to the next iteration of a containing loop of the same type.</span></span>  
  
 <span data-ttu-id="37049-114">Si tiene bucles anidados de distintos tipos, por ejemplo, un bucle @no__t 0 dentro de un bucle `For`, puede ir directamente a la siguiente iteración de cualquier bucle mediante `Continue Do` o `Continue For`.</span><span class="sxs-lookup"><span data-stu-id="37049-114">If you have nested loops of different types, for example a `Do` loop within a `For` loop, you can skip to the next iteration of either loop by using either `Continue Do` or `Continue For`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37049-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="37049-115">Example</span></span>  
 <span data-ttu-id="37049-116">En el ejemplo de código siguiente se usa la instrucción `Continue While` para saltar a la columna siguiente de una matriz si un divisor es cero.</span><span class="sxs-lookup"><span data-stu-id="37049-116">The following code example uses the `Continue While` statement to skip to the next column of an array if a divisor is zero.</span></span> <span data-ttu-id="37049-117">El `Continue While` está dentro de un bucle `For`.</span><span class="sxs-lookup"><span data-stu-id="37049-117">The `Continue While` is inside a `For` loop.</span></span> <span data-ttu-id="37049-118">Se transfiere a la instrucción `While col < lastcol`, que es la siguiente iteración del bucle `While` más interno que contiene el bucle `For`.</span><span class="sxs-lookup"><span data-stu-id="37049-118">It transfers to the `While col < lastcol` statement, which is the next iteration of the innermost `While` loop that contains the `For` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="37049-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="37049-119">See also</span></span>

- [<span data-ttu-id="37049-120">Do...Loop (instrucción)</span><span class="sxs-lookup"><span data-stu-id="37049-120">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="37049-121">For...Next (instrucción)</span><span class="sxs-lookup"><span data-stu-id="37049-121">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="37049-122">While...End While (instrucción)</span><span class="sxs-lookup"><span data-stu-id="37049-122">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [<span data-ttu-id="37049-123">Try...Catch...Finally (instrucción)</span><span class="sxs-lookup"><span data-stu-id="37049-123">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
