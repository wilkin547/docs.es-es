---
description: 'Más información acerca de: instrucción call (Visual Basic)'
title: Instrucción Call
ms.date: 07/20/2015
f1_keywords:
- vb.Call
helpviewer_keywords:
- procedures [Visual Basic], Call statement
- Call statement [Visual Basic]
- procedures [Visual Basic], calling
ms.assetid: e5b31571-6867-406f-b8e7-a3f9aae4723a
ms.openlocfilehash: 70e6c109621c3710ad9476a952e9c384a142ba3d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99674017"
---
# <a name="call-statement-visual-basic"></a><span data-ttu-id="3265e-103">Call (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3265e-103">Call Statement (Visual Basic)</span></span>

<span data-ttu-id="3265e-104">Transfiere el control a `Function` un `Sub` procedimiento de biblioteca de vínculos dinámicos (dll), o.</span><span class="sxs-lookup"><span data-stu-id="3265e-104">Transfers control to a `Function`, `Sub`, or dynamic-link library (DLL) procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3265e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3265e-105">Syntax</span></span>  
  
```vb  
[ Call ] procedureName [ (argumentList) ]  
```  
  
## <a name="parts"></a><span data-ttu-id="3265e-106">Partes</span><span class="sxs-lookup"><span data-stu-id="3265e-106">Parts</span></span>  

|||
|---|---|
|`procedureName`|<span data-ttu-id="3265e-107">Necesario.</span><span class="sxs-lookup"><span data-stu-id="3265e-107">Required.</span></span> <span data-ttu-id="3265e-108">Nombre del procedimiento al que se va a llamar.</span><span class="sxs-lookup"><span data-stu-id="3265e-108">Name of the procedure to call.</span></span>|
|`argumentList`|<span data-ttu-id="3265e-109">Opcional.</span><span class="sxs-lookup"><span data-stu-id="3265e-109">Optional.</span></span> <span data-ttu-id="3265e-110">Lista de variables o expresiones que representan los argumentos que se pasan al procedimiento cuando se llama.</span><span class="sxs-lookup"><span data-stu-id="3265e-110">List of variables or expressions representing arguments that are passed to the procedure when it is called.</span></span> <span data-ttu-id="3265e-111">Los argumentos múltiples se separan mediante comas.</span><span class="sxs-lookup"><span data-stu-id="3265e-111">Multiple arguments are separated by commas.</span></span> <span data-ttu-id="3265e-112">Si incluye `argumentList` , debe encerrarlo entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="3265e-112">If you include `argumentList`, you must enclose it in parentheses.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="3265e-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3265e-113">Remarks</span></span>

 <span data-ttu-id="3265e-114">Puede usar la `Call` palabra clave al llamar a un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="3265e-114">You can use the `Call` keyword when you call a procedure.</span></span> <span data-ttu-id="3265e-115">Para la mayoría de las llamadas a procedimientos, no es necesario usar esta palabra clave.</span><span class="sxs-lookup"><span data-stu-id="3265e-115">For most procedure calls, you aren’t required to use this  keyword.</span></span>

 <span data-ttu-id="3265e-116">Normalmente, se usa la `Call` palabra clave cuando la expresión llamada no comienza por un identificador.</span><span class="sxs-lookup"><span data-stu-id="3265e-116">You typically use the `Call` keyword when the called expression doesn’t start with an identifier.</span></span> <span data-ttu-id="3265e-117">No se recomienda el uso de la `Call` palabra clave para otros usos.</span><span class="sxs-lookup"><span data-stu-id="3265e-117">Use of the `Call` keyword for other uses isn't recommended.</span></span>

 <span data-ttu-id="3265e-118">Si el procedimiento devuelve un valor, la `Call` instrucción lo descarta.</span><span class="sxs-lookup"><span data-stu-id="3265e-118">If the procedure returns a value, the `Call` statement discards it.</span></span>

## <a name="example"></a><span data-ttu-id="3265e-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3265e-119">Example</span></span>

 <span data-ttu-id="3265e-120">En el código siguiente se muestran dos ejemplos en los que la `Call` palabra clave es necesaria para llamar a un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="3265e-120">The following code shows two examples where the `Call` keyword is necessary to call a procedure.</span></span> <span data-ttu-id="3265e-121">En ambos ejemplos, la expresión llamada no comienza por un identificador.</span><span class="sxs-lookup"><span data-stu-id="3265e-121">In both examples, the called expression doesn't start with an identifier.</span></span>

 [!code-vb[VbVbalrStatements#97](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#97)]  
  
## <a name="see-also"></a><span data-ttu-id="3265e-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="3265e-122">See also</span></span>

- [<span data-ttu-id="3265e-123">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="3265e-123">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="3265e-124">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="3265e-124">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="3265e-125">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="3265e-125">Declare Statement</span></span>](declare-statement.md)
- [<span data-ttu-id="3265e-126">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="3265e-126">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
