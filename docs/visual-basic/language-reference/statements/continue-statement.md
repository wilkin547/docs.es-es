---
description: Más información acerca de la instrucción Continue (Visual Basic)
title: Instrucción Continue
ms.date: 07/20/2015
f1_keywords:
- vb.continue
helpviewer_keywords:
- Continue statement [Visual Basic]
- loops, transferring to next iteration
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
ms.openlocfilehash: c6d67e766b2551956795803076efe639ba3c8c99
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99673874"
---
# <a name="continue-statement-visual-basic"></a><span data-ttu-id="e5322-103">Continue (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e5322-103">Continue Statement (Visual Basic)</span></span>

<span data-ttu-id="e5322-104">Transfiere el control inmediatamente a la siguiente iteración de un bucle.</span><span class="sxs-lookup"><span data-stu-id="e5322-104">Transfers control immediately to the next iteration of a loop.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5322-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e5322-105">Syntax</span></span>  
  
```vb  
Continue { Do | For | While }  
```  
  
## <a name="remarks"></a><span data-ttu-id="e5322-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e5322-106">Remarks</span></span>  

 <span data-ttu-id="e5322-107">Puede transferir desde dentro de un `Do` `For` bucle, o `While` hasta la siguiente iteración del bucle.</span><span class="sxs-lookup"><span data-stu-id="e5322-107">You can transfer from inside a `Do`, `For`, or `While` loop to the next iteration of that loop.</span></span> <span data-ttu-id="e5322-108">El control pasa inmediatamente a la prueba de la condición de bucle, que es equivalente a transferir a la `For` `While` instrucción o, o a la `Do` `Loop` instrucción o que contiene la `Until` `While` cláusula o.</span><span class="sxs-lookup"><span data-stu-id="e5322-108">Control passes immediately to the loop condition test, which is equivalent to transferring to the `For` or `While` statement, or to the `Do` or `Loop` statement that contains the `Until` or `While` clause.</span></span>  
  
 <span data-ttu-id="e5322-109">Puede usar `Continue` en cualquier ubicación del bucle que permita las transferencias.</span><span class="sxs-lookup"><span data-stu-id="e5322-109">You can use `Continue` at any location in the loop that allows transfers.</span></span> <span data-ttu-id="e5322-110">Las reglas que permiten la transferencia de control son las mismas que con la [instrucción Goto](goto-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e5322-110">The rules allowing transfer of control are the same as with the [GoTo Statement](goto-statement.md).</span></span>  
  
 <span data-ttu-id="e5322-111">Por ejemplo, si un bucle está totalmente contenido dentro de un bloque, `Try` un `Catch` bloque o un `Finally` bloque, puede usar `Continue` para transferir fuera del bucle.</span><span class="sxs-lookup"><span data-stu-id="e5322-111">For example, if a loop is totally contained within a `Try` block, a `Catch` block, or a `Finally` block, you can use `Continue` to transfer out of the loop.</span></span> <span data-ttu-id="e5322-112">Por otro lado, si la `Try` estructura... `End Try` está contenida dentro del bucle, no se puede usar `Continue` para transferir el control fuera del `Finally` bloque, y se puede utilizar para transferir fuera de un `Try` bloque o `Catch` solo si se transfiere completamente de la `Try` estructura... `End Try` .</span><span class="sxs-lookup"><span data-stu-id="e5322-112">If, on the other hand, the `Try`...`End Try` structure is contained within the loop, you cannot use `Continue` to transfer control out of the `Finally` block, and you can use it to transfer out of a `Try` or `Catch` block only if you transfer completely out of the `Try`...`End Try` structure.</span></span>  
  
 <span data-ttu-id="e5322-113">Si tiene bucles anidados del mismo tipo, por ejemplo un `Do` bucle dentro de otro `Do` bucle, una `Continue Do` instrucción salta a la siguiente iteración del bucle más interno `Do` que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="e5322-113">If you have nested loops of the same type, for example a `Do` loop within another `Do` loop, a `Continue Do` statement skips to the next iteration of the innermost `Do` loop that contains it.</span></span> <span data-ttu-id="e5322-114">No se puede usar `Continue` para pasar a la siguiente iteración de un bucle contenedor del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="e5322-114">You cannot use `Continue` to skip to the next iteration of a containing loop of the same type.</span></span>  
  
 <span data-ttu-id="e5322-115">Si tiene bucles anidados de distintos tipos, por ejemplo un `Do` bucle dentro de un `For` bucle, puede ir directamente a la siguiente iteración de cualquier bucle mediante `Continue Do` o `Continue For` .</span><span class="sxs-lookup"><span data-stu-id="e5322-115">If you have nested loops of different types, for example a `Do` loop within a `For` loop, you can skip to the next iteration of either loop by using either `Continue Do` or `Continue For`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5322-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e5322-116">Example</span></span>  

 <span data-ttu-id="e5322-117">En el ejemplo de código siguiente `Continue While` se usa la instrucción para saltar a la columna siguiente de una matriz si un divisor es cero.</span><span class="sxs-lookup"><span data-stu-id="e5322-117">The following code example uses the `Continue While` statement to skip to the next column of an array if a divisor is zero.</span></span> <span data-ttu-id="e5322-118">`Continue While`Está dentro de un `For` bucle.</span><span class="sxs-lookup"><span data-stu-id="e5322-118">The `Continue While` is inside a `For` loop.</span></span> <span data-ttu-id="e5322-119">Se transfiere a la `While col < lastcol` instrucción, que es la siguiente iteración del bucle más interno `While` que contiene el `For` bucle.</span><span class="sxs-lookup"><span data-stu-id="e5322-119">It transfers to the `While col < lastcol` statement, which is the next iteration of the innermost `While` loop that contains the `For` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="e5322-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5322-120">See also</span></span>

- [<span data-ttu-id="e5322-121">Instrucción Do...Loop</span><span class="sxs-lookup"><span data-stu-id="e5322-121">Do...Loop Statement</span></span>](do-loop-statement.md)
- [<span data-ttu-id="e5322-122">Instrucción For...Next</span><span class="sxs-lookup"><span data-stu-id="e5322-122">For...Next Statement</span></span>](for-next-statement.md)
- [<span data-ttu-id="e5322-123">Instrucción While...End While</span><span class="sxs-lookup"><span data-stu-id="e5322-123">While...End While Statement</span></span>](while-end-while-statement.md)
- [<span data-ttu-id="e5322-124">Try...Catch...Finally (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e5322-124">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)
