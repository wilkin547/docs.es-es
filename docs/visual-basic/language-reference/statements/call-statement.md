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
ms.openlocfilehash: af0b62d6cfacbcf94f527e049e07e51bf496a6cf
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "71392759"
---
# <a name="call-statement-visual-basic"></a><span data-ttu-id="ababb-102">Call (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ababb-102">Call Statement (Visual Basic)</span></span>

<span data-ttu-id="ababb-103">Transfiere el control a un procedimiento de biblioteca de vínculos dinámicos (DLL) `Function`, `Sub` o.</span><span class="sxs-lookup"><span data-stu-id="ababb-103">Transfers control to a `Function`, `Sub`, or dynamic-link library (DLL) procedure.</span></span>

## <a name="syntax"></a><span data-ttu-id="ababb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ababb-104">Syntax</span></span>

```vb
[ Call ] procedureName [ (argumentList) ]
```

## <a name="parts"></a><span data-ttu-id="ababb-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="ababb-105">Parts</span></span>

|||
|---|---|
|`procedureName`|<span data-ttu-id="ababb-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="ababb-106">Required.</span></span> <span data-ttu-id="ababb-107">Nombre del procedimiento al que se va a llamar.</span><span class="sxs-lookup"><span data-stu-id="ababb-107">Name of the procedure to call.</span></span>|
|`argumentList`|<span data-ttu-id="ababb-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="ababb-108">Optional.</span></span> <span data-ttu-id="ababb-109">Lista de variables o expresiones que representan los argumentos que se pasan al procedimiento cuando se llama.</span><span class="sxs-lookup"><span data-stu-id="ababb-109">List of variables or expressions representing arguments that are passed to the procedure when it is called.</span></span> <span data-ttu-id="ababb-110">Los argumentos múltiples se separan mediante comas.</span><span class="sxs-lookup"><span data-stu-id="ababb-110">Multiple arguments are separated by commas.</span></span> <span data-ttu-id="ababb-111">Si incluye `argumentList`, debe encerrarlo entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="ababb-111">If you include `argumentList`, you must enclose it in parentheses.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="ababb-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ababb-112">Remarks</span></span>

 <span data-ttu-id="ababb-113">Puede usar la palabra clave `Call` al llamar a un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="ababb-113">You can use the `Call` keyword when you call a procedure.</span></span> <span data-ttu-id="ababb-114">Para la mayoría de las llamadas a procedimientos, no es necesario usar esta palabra clave.</span><span class="sxs-lookup"><span data-stu-id="ababb-114">For most procedure calls, you aren’t required to use this  keyword.</span></span>

 <span data-ttu-id="ababb-115">Normalmente se usa la palabra clave `Call` cuando la expresión llamada no comienza por un identificador.</span><span class="sxs-lookup"><span data-stu-id="ababb-115">You typically use the `Call` keyword when the called expression doesn’t start with an identifier.</span></span> <span data-ttu-id="ababb-116">No se recomienda el uso de la palabra clave `Call` para otros usos.</span><span class="sxs-lookup"><span data-stu-id="ababb-116">Use of the `Call` keyword for other uses isn't recommended.</span></span>

 <span data-ttu-id="ababb-117">Si el procedimiento devuelve un valor, la instrucción `Call` lo descarta.</span><span class="sxs-lookup"><span data-stu-id="ababb-117">If the procedure returns a value, the `Call` statement discards it.</span></span>

## <a name="example"></a><span data-ttu-id="ababb-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ababb-118">Example</span></span>

 <span data-ttu-id="ababb-119">En el código siguiente se muestran dos ejemplos en los que la palabra clave `Call` es necesaria para llamar a un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="ababb-119">The following code shows two examples where the `Call` keyword is necessary to call a procedure.</span></span> <span data-ttu-id="ababb-120">En ambos ejemplos, la expresión llamada no comienza por un identificador.</span><span class="sxs-lookup"><span data-stu-id="ababb-120">In both examples, the called expression doesn't start with an identifier.</span></span>

 [!code-vb[VbVbalrStatements#97](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#97)]  
  
## <a name="see-also"></a><span data-ttu-id="ababb-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="ababb-121">See also</span></span>

- [<span data-ttu-id="ababb-122">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ababb-122">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="ababb-123">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ababb-123">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="ababb-124">Declare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ababb-124">Declare Statement</span></span>](declare-statement.md)
- [<span data-ttu-id="ababb-125">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="ababb-125">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
