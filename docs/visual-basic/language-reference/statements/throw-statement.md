---
description: 'Más información acerca de: Throw (instrucción) (Visual Basic)'
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
ms.openlocfilehash: b7fa4183b5997e5dac8045502a8eed1afe66fc0d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99740943"
---
# <a name="throw-statement-visual-basic"></a><span data-ttu-id="b6e3a-103">Throw (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b6e3a-103">Throw Statement (Visual Basic)</span></span>

<span data-ttu-id="b6e3a-104">Produce una excepción dentro de un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="b6e3a-104">Throws an exception within a procedure.</span></span>

## <a name="syntax"></a><span data-ttu-id="b6e3a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b6e3a-105">Syntax</span></span>

```vb
Throw [ expression ]
```

## <a name="part"></a><span data-ttu-id="b6e3a-106">Parte</span><span class="sxs-lookup"><span data-stu-id="b6e3a-106">Part</span></span>

`expression`\
<span data-ttu-id="b6e3a-107">Proporciona información sobre la excepción que se va a producir.</span><span class="sxs-lookup"><span data-stu-id="b6e3a-107">Provides information about the exception to be thrown.</span></span> <span data-ttu-id="b6e3a-108">Opcional cuando reside en una `Catch` instrucción; de lo contrario, es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="b6e3a-108">Optional when residing in a `Catch` statement, otherwise required.</span></span>

## <a name="remarks"></a><span data-ttu-id="b6e3a-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b6e3a-109">Remarks</span></span>

<span data-ttu-id="b6e3a-110">La `Throw` instrucción produce una excepción que se puede controlar con código estructurado de control de excepciones ( `Try` ... `Catch` ...`Finally`) código de control de excepciones no estructurado ( `On Error GoTo` ).</span><span class="sxs-lookup"><span data-stu-id="b6e3a-110">The `Throw` statement throws an exception that you can handle with structured exception-handling code (`Try`...`Catch`...`Finally`) or unstructured exception-handling code (`On Error GoTo`).</span></span> <span data-ttu-id="b6e3a-111">Puede usar la `Throw` instrucción para interceptar errores dentro del código porque Visual Basic sube la pila de llamadas hasta que encuentra el código de control de excepciones adecuado.</span><span class="sxs-lookup"><span data-stu-id="b6e3a-111">You can use the `Throw` statement to trap errors within your code because Visual Basic moves up the call stack until it finds the appropriate exception-handling code.</span></span>

<span data-ttu-id="b6e3a-112">Una `Throw` instrucción sin expresión solo se puede usar en una `Catch` instrucción, en cuyo caso la instrucción vuelve a iniciar la excepción que está controlando actualmente la `Catch` instrucción.</span><span class="sxs-lookup"><span data-stu-id="b6e3a-112">A `Throw` statement with no expression can only be used in a `Catch` statement, in which case the statement rethrows the exception currently being handled by the `Catch` statement.</span></span>

<span data-ttu-id="b6e3a-113">La `Throw` instrucción restablece la pila de llamadas de la `expression` excepción.</span><span class="sxs-lookup"><span data-stu-id="b6e3a-113">The `Throw` statement resets the call stack for the `expression` exception.</span></span> <span data-ttu-id="b6e3a-114">Si `expression` no se proporciona, la pila de llamadas permanece sin cambios.</span><span class="sxs-lookup"><span data-stu-id="b6e3a-114">If `expression` is not provided, the call stack is left unchanged.</span></span> <span data-ttu-id="b6e3a-115">Puede tener acceso a la pila de llamadas de la excepción a través de la <xref:System.Exception.StackTrace%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="b6e3a-115">You can access the call stack for the exception through the <xref:System.Exception.StackTrace%2A> property.</span></span>

## <a name="example"></a><span data-ttu-id="b6e3a-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b6e3a-116">Example</span></span>

<span data-ttu-id="b6e3a-117">En el código siguiente se usa la `Throw` instrucción para producir una excepción:</span><span class="sxs-lookup"><span data-stu-id="b6e3a-117">The following code uses the `Throw` statement to throw an exception:</span></span>

[!code-vb[VbVbalrStatements#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#84)]

## <a name="see-also"></a><span data-ttu-id="b6e3a-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="b6e3a-118">See also</span></span>

- [<span data-ttu-id="b6e3a-119">Try...Catch...Finally (instrucción)</span><span class="sxs-lookup"><span data-stu-id="b6e3a-119">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)
- [<span data-ttu-id="b6e3a-120">Instrucción On Error</span><span class="sxs-lookup"><span data-stu-id="b6e3a-120">On Error Statement</span></span>](on-error-statement.md)
