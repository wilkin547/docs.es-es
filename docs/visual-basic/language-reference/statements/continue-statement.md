---
title: Continue (Instrucción, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.continue
helpviewer_keywords:
- Continue statement [Visual Basic]
- loops, transferring to next iteration
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
ms.openlocfilehash: eb8596c43bf6232eec4bcb844e6202c5de373404
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33602728"
---
# <a name="continue-statement-visual-basic"></a><span data-ttu-id="27f15-102">Continue (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="27f15-102">Continue Statement (Visual Basic)</span></span>
<span data-ttu-id="27f15-103">Transfiere el control inmediatamente a la siguiente iteración de un bucle.</span><span class="sxs-lookup"><span data-stu-id="27f15-103">Transfers control immediately to the next iteration of a loop.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27f15-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="27f15-104">Syntax</span></span>  
  
```  
Continue { Do | For | While }  
```  
  
## <a name="remarks"></a><span data-ttu-id="27f15-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="27f15-105">Remarks</span></span>  
 <span data-ttu-id="27f15-106">Puede transferir desde dentro de un `Do`, `For`, o `While` loop a la siguiente iteración del bucle.</span><span class="sxs-lookup"><span data-stu-id="27f15-106">You can transfer from inside a `Do`, `For`, or `While` loop to the next iteration of that loop.</span></span> <span data-ttu-id="27f15-107">Control pasa inmediatamente a la comprobación de condición del bucle, que es equivalente a transferir a la `For` o `While` (instrucción), o a la `Do` o `Loop` instrucción que contiene el `Until` o `While` cláusula.</span><span class="sxs-lookup"><span data-stu-id="27f15-107">Control passes immediately to the loop condition test, which is equivalent to transferring to the `For` or `While` statement, or to the `Do` or `Loop` statement that contains the `Until` or `While` clause.</span></span>  
  
 <span data-ttu-id="27f15-108">Puede usar `Continue` en cualquier ubicación en el bucle que permite las transferencias.</span><span class="sxs-lookup"><span data-stu-id="27f15-108">You can use `Continue` at any location in the loop that allows transfers.</span></span> <span data-ttu-id="27f15-109">Las reglas que permiten la transferencia del control son los mismos que con la [instrucción GoTo](../../../visual-basic/language-reference/statements/goto-statement.md).</span><span class="sxs-lookup"><span data-stu-id="27f15-109">The rules allowing transfer of control are the same as with the [GoTo Statement](../../../visual-basic/language-reference/statements/goto-statement.md).</span></span>  
  
 <span data-ttu-id="27f15-110">Por ejemplo, si un bucle es totalmente independiente dentro de un `Try` bloque, un `Catch` bloque, o un `Finally` bloque, puede usar `Continue` para transferir fuera del bucle.</span><span class="sxs-lookup"><span data-stu-id="27f15-110">For example, if a loop is totally contained within a `Try` block, a `Catch` block, or a `Finally` block, you can use `Continue` to transfer out of the loop.</span></span> <span data-ttu-id="27f15-111">Si es, por otro lado, la `Try`... `End Try` estructura está dentro del bucle, no se puede usar `Continue` para transferir el control fuera de la `Finally` bloque y se puede usar para transferir fuera de un `Try` o `Catch` sólo se bloquea si transfirió completamente fuera de la `Try`... `End Try` estructura.</span><span class="sxs-lookup"><span data-stu-id="27f15-111">If, on the other hand, the `Try`...`End Try` structure is contained within the loop, you cannot use `Continue` to transfer control out of the `Finally` block, and you can use it to transfer out of a `Try` or `Catch` block only if you transfer completely out of the `Try`...`End Try` structure.</span></span>  
  
 <span data-ttu-id="27f15-112">Si tiene bucles anidados del mismo tipo, por ejemplo un `Do` bucle dentro de otro `Do` bucles, un `Continue Do` omite la instrucción a la siguiente iteración de la más interna `Do` bucle que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="27f15-112">If you have nested loops of the same type, for example a `Do` loop within another `Do` loop, a `Continue Do` statement skips to the next iteration of the innermost `Do` loop that contains it.</span></span> <span data-ttu-id="27f15-113">No se puede utilizar `Continue` para ir directamente a la siguiente iteración de un bucle que contiene el mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="27f15-113">You cannot use `Continue` to skip to the next iteration of a containing loop of the same type.</span></span>  
  
 <span data-ttu-id="27f15-114">Si tiene bucles anidados de tipos diferentes, por ejemplo un `Do` bucle dentro de un `For` bucle, puede omitir a la siguiente iteración de cualquiera de esos bucles utilizando `Continue Do` o `Continue For`.</span><span class="sxs-lookup"><span data-stu-id="27f15-114">If you have nested loops of different types, for example a `Do` loop within a `For` loop, you can skip to the next iteration of either loop by using either `Continue Do` or `Continue For`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="27f15-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="27f15-115">Example</span></span>  
 <span data-ttu-id="27f15-116">El siguiente ejemplo de código utiliza el `Continue While` instrucción para pasar a la siguiente columna de una matriz si un divisor es cero.</span><span class="sxs-lookup"><span data-stu-id="27f15-116">The following code example uses the `Continue While` statement to skip to the next column of an array if a divisor is zero.</span></span> <span data-ttu-id="27f15-117">El `Continue While` está dentro de un `For` bucle.</span><span class="sxs-lookup"><span data-stu-id="27f15-117">The `Continue While` is inside a `For` loop.</span></span> <span data-ttu-id="27f15-118">Transfiere a la `While col < lastcol` instrucción, que es la siguiente iteración de la más interna `While` bucle que contiene el `For` bucle.</span><span class="sxs-lookup"><span data-stu-id="27f15-118">It transfers to the `While col < lastcol` statement, which is the next iteration of the innermost `While` loop that contains the `For` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#14](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/continue-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="27f15-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="27f15-119">See Also</span></span>  
 [<span data-ttu-id="27f15-120">Do...Loop (instrucción)</span><span class="sxs-lookup"><span data-stu-id="27f15-120">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [<span data-ttu-id="27f15-121">For...Next (instrucción)</span><span class="sxs-lookup"><span data-stu-id="27f15-121">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [<span data-ttu-id="27f15-122">While...End While (instrucción)</span><span class="sxs-lookup"><span data-stu-id="27f15-122">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)  
 [<span data-ttu-id="27f15-123">Try...Catch...Finally (instrucción)</span><span class="sxs-lookup"><span data-stu-id="27f15-123">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
