---
title: Throw (Instrucción)
ms.date: 07/20/2015
f1_keywords:
- vb.Throw
helpviewer_keywords:
- structured exception handling, throw statements
- try-catch exception handling, throw statements
- throw statement [Visual Basic], about throw statements
- throwing exceptions, throw statement
- exception handling, throw statement
- On Error statement [Visual Basic], throwing exceptions
- throwing exceptions
- exception handling, unstructured
- throw statement [Visual Basic]
ms.assetid: a6e07406-5c8a-4498-87a2-8339f3651d62
ms.openlocfilehash: 95572b1739490e90f53da6b6ec283bfb532c46d3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404140"
---
# <a name="throw-statement-visual-basic"></a><span data-ttu-id="ba2b3-102">Throw (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ba2b3-102">Throw Statement (Visual Basic)</span></span>

<span data-ttu-id="ba2b3-103">Produce una excepción dentro de un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="ba2b3-103">Throws an exception within a procedure.</span></span>

## <a name="syntax"></a><span data-ttu-id="ba2b3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ba2b3-104">Syntax</span></span>

```vb
Throw [ expression ]
```

## <a name="part"></a><span data-ttu-id="ba2b3-105">Parte</span><span class="sxs-lookup"><span data-stu-id="ba2b3-105">Part</span></span>

`expression`\
<span data-ttu-id="ba2b3-106">Proporciona información sobre la excepción que se va a producir.</span><span class="sxs-lookup"><span data-stu-id="ba2b3-106">Provides information about the exception to be thrown.</span></span> <span data-ttu-id="ba2b3-107">Opcional cuando reside en una `Catch` instrucción; de lo contrario, es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="ba2b3-107">Optional when residing in a `Catch` statement, otherwise required.</span></span>

## <a name="remarks"></a><span data-ttu-id="ba2b3-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ba2b3-108">Remarks</span></span>

<span data-ttu-id="ba2b3-109">La `Throw` instrucción produce una excepción que se puede controlar con código estructurado de control de excepciones ( `Try` ... `Catch` ...`Finally`) código de control de excepciones no estructurado ( `On Error GoTo` ).</span><span class="sxs-lookup"><span data-stu-id="ba2b3-109">The `Throw` statement throws an exception that you can handle with structured exception-handling code (`Try`...`Catch`...`Finally`) or unstructured exception-handling code (`On Error GoTo`).</span></span> <span data-ttu-id="ba2b3-110">Puede usar la `Throw` instrucción para interceptar errores dentro del código porque Visual Basic sube la pila de llamadas hasta que encuentra el código de control de excepciones adecuado.</span><span class="sxs-lookup"><span data-stu-id="ba2b3-110">You can use the `Throw` statement to trap errors within your code because Visual Basic moves up the call stack until it finds the appropriate exception-handling code.</span></span>

<span data-ttu-id="ba2b3-111">Una `Throw` instrucción sin expresión solo se puede usar en una `Catch` instrucción, en cuyo caso la instrucción vuelve a iniciar la excepción que está controlando actualmente la `Catch` instrucción.</span><span class="sxs-lookup"><span data-stu-id="ba2b3-111">A `Throw` statement with no expression can only be used in a `Catch` statement, in which case the statement rethrows the exception currently being handled by the `Catch` statement.</span></span>

<span data-ttu-id="ba2b3-112">La `Throw` instrucción restablece la pila de llamadas de la `expression` excepción.</span><span class="sxs-lookup"><span data-stu-id="ba2b3-112">The `Throw` statement resets the call stack for the `expression` exception.</span></span> <span data-ttu-id="ba2b3-113">Si `expression` no se proporciona, la pila de llamadas permanece sin cambios.</span><span class="sxs-lookup"><span data-stu-id="ba2b3-113">If `expression` is not provided, the call stack is left unchanged.</span></span> <span data-ttu-id="ba2b3-114">Puede tener acceso a la pila de llamadas de la excepción a través de la <xref:System.Exception.StackTrace%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="ba2b3-114">You can access the call stack for the exception through the <xref:System.Exception.StackTrace%2A> property.</span></span>

## <a name="example"></a><span data-ttu-id="ba2b3-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ba2b3-115">Example</span></span>

<span data-ttu-id="ba2b3-116">En el código siguiente se usa la `Throw` instrucción para producir una excepción:</span><span class="sxs-lookup"><span data-stu-id="ba2b3-116">The following code uses the `Throw` statement to throw an exception:</span></span>

[!code-vb[VbVbalrStatements#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#84)]

## <a name="see-also"></a><span data-ttu-id="ba2b3-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ba2b3-117">See also</span></span>

- [<span data-ttu-id="ba2b3-118">Instrucción Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="ba2b3-118">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)
- [<span data-ttu-id="ba2b3-119">Instrucción On Error</span><span class="sxs-lookup"><span data-stu-id="ba2b3-119">On Error Statement</span></span>](on-error-statement.md)
