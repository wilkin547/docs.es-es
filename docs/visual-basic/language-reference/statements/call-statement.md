---
title: Call (Instrucción, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Call
helpviewer_keywords:
- procedures [Visual Basic], Call statement
- Call statement [Visual Basic]
- procedures [Visual Basic], calling
ms.assetid: e5b31571-6867-406f-b8e7-a3f9aae4723a
ms.openlocfilehash: 755443a99a1ad8b0430a76d2dba1ff27472d4c9d
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58832650"
---
# <a name="call-statement-visual-basic"></a><span data-ttu-id="f1760-102">Call (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f1760-102">Call Statement (Visual Basic)</span></span>
<span data-ttu-id="f1760-103">Transfiere el control a un `Function`, `Sub`, o el procedimiento de la biblioteca de vínculos dinámicos (DLL).</span><span class="sxs-lookup"><span data-stu-id="f1760-103">Transfers control to a `Function`, `Sub`, or dynamic-link library (DLL) procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1760-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f1760-104">Syntax</span></span>  
  
```  
[ Call ] procedureName [ (argumentList) ]  
```  
  
## <a name="parts"></a><span data-ttu-id="f1760-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="f1760-105">Parts</span></span>  
|||
|---|---|
|`procedureName`|<span data-ttu-id="f1760-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="f1760-106">Required.</span></span> <span data-ttu-id="f1760-107">Nombre del procedimiento para llamar a.</span><span class="sxs-lookup"><span data-stu-id="f1760-107">Name of the procedure to call.</span></span>|
|`argumentList`|<span data-ttu-id="f1760-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="f1760-108">Optional.</span></span> <span data-ttu-id="f1760-109">Lista de variables o expresiones que representan los argumentos que se pasan al procedimiento cuando se llama.</span><span class="sxs-lookup"><span data-stu-id="f1760-109">List of variables or expressions representing arguments that are passed to the procedure when it is called.</span></span> <span data-ttu-id="f1760-110">Varios argumentos están separados por comas.</span><span class="sxs-lookup"><span data-stu-id="f1760-110">Multiple arguments are separated by commas.</span></span> <span data-ttu-id="f1760-111">Si incluye `argumentList`, debe encerrarlo entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="f1760-111">If you include `argumentList`, you must enclose it in parentheses.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="f1760-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f1760-112">Remarks</span></span>  
 <span data-ttu-id="f1760-113">Puede usar el `Call` palabra clave cuando se llama a un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f1760-113">You can use the `Call` keyword when you call a procedure.</span></span> <span data-ttu-id="f1760-114">Para la mayoría de las llamadas de procedimiento, no es necesario usar esta palabra clave.</span><span class="sxs-lookup"><span data-stu-id="f1760-114">For most procedure calls, you aren’t required to use this  keyword.</span></span>  
  
 <span data-ttu-id="f1760-115">Normalmente, se utiliza el `Call` palabra clave cuando la expresión llamada no se inicia con un identificador.</span><span class="sxs-lookup"><span data-stu-id="f1760-115">You typically use the `Call` keyword when the called expression doesn’t start with an identifier.</span></span> <span data-ttu-id="f1760-116">El uso de la `Call` no se recomienda la palabra clave para otros usos.</span><span class="sxs-lookup"><span data-stu-id="f1760-116">Use of the `Call` keyword for other uses isn’t recommended.</span></span>  
  
 <span data-ttu-id="f1760-117">Si el procedimiento devuelve un valor, el `Call` instrucción lo descarta.</span><span class="sxs-lookup"><span data-stu-id="f1760-117">If the procedure returns a value, the `Call` statement discards it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1760-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f1760-118">Example</span></span>  
 <span data-ttu-id="f1760-119">El código siguiente muestra dos ejemplos donde el `Call` palabra clave es necesario llamar a un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f1760-119">The following code shows two examples where the `Call` keyword is necessary to call a procedure.</span></span> <span data-ttu-id="f1760-120">En ambos ejemplos, la expresión llamada no se inicia con un identificador.</span><span class="sxs-lookup"><span data-stu-id="f1760-120">In both examples, the called expression doesn't start with an identifier.</span></span>  
  
 [!code-vb[VbVbalrStatements#97](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#97)]  
  
## <a name="see-also"></a><span data-ttu-id="f1760-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="f1760-121">See also</span></span>

- [<span data-ttu-id="f1760-122">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f1760-122">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="f1760-123">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f1760-123">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="f1760-124">Declare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f1760-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="f1760-125">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="f1760-125">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
