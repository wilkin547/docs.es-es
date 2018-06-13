---
title: Throw (Instrucción, Visual Basic)
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
ms.openlocfilehash: cfa53b3585846da25711739fb7af4bde21746b29
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33602858"
---
# <a name="throw-statement-visual-basic"></a><span data-ttu-id="4d7e8-102">Throw (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4d7e8-102">Throw Statement (Visual Basic)</span></span>
<span data-ttu-id="4d7e8-103">Produce una excepción dentro de un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="4d7e8-103">Throws an exception within a procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d7e8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4d7e8-104">Syntax</span></span>  
  
```  
Throw [ expression ]  
```  
  
## <a name="part"></a><span data-ttu-id="4d7e8-105">Parte</span><span class="sxs-lookup"><span data-stu-id="4d7e8-105">Part</span></span>  
 `expression`  
 <span data-ttu-id="4d7e8-106">Proporciona información sobre la excepción que se produzca.</span><span class="sxs-lookup"><span data-stu-id="4d7e8-106">Provides information about the exception to be thrown.</span></span> <span data-ttu-id="4d7e8-107">Opcional si se encuentra en un `Catch` instrucción, en caso contrario, se requiere.</span><span class="sxs-lookup"><span data-stu-id="4d7e8-107">Optional when residing in a `Catch` statement, otherwise required.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d7e8-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4d7e8-108">Remarks</span></span>  
 <span data-ttu-id="4d7e8-109">El `Throw` instrucción produce una excepción que se puede controlar con código de control de excepciones estructurado (`Try`... `Catch`... `Finally`) o código de control de excepciones no estructurado (`On Error GoTo`).</span><span class="sxs-lookup"><span data-stu-id="4d7e8-109">The `Throw` statement throws an exception that you can handle with structured exception-handling code (`Try`...`Catch`...`Finally`) or unstructured exception-handling code (`On Error GoTo`).</span></span> <span data-ttu-id="4d7e8-110">Puede usar el `Throw` instrucción para interceptar errores dentro del código porque Visual Basic asciende por la pila de llamadas hasta que encuentra el código de control de excepciones adecuado.</span><span class="sxs-lookup"><span data-stu-id="4d7e8-110">You can use the `Throw` statement to trap errors within your code because Visual Basic moves up the call stack until it finds the appropriate exception-handling code.</span></span>  
  
 <span data-ttu-id="4d7e8-111">A `Throw` instrucción sin expresión sólo puede utilizarse en una `Catch` (instrucción), en el que caso la instrucción, vuelve a producir la excepción se controla actualmente por el `Catch` instrucción.</span><span class="sxs-lookup"><span data-stu-id="4d7e8-111">A `Throw` statement with no expression can only be used in a `Catch` statement, in which case the statement rethrows the exception currently being handled by the `Catch` statement.</span></span>  
  
 <span data-ttu-id="4d7e8-112">El `Throw` instrucción restablece la pila de llamadas para el `expression` excepción.</span><span class="sxs-lookup"><span data-stu-id="4d7e8-112">The `Throw` statement resets the call stack for the `expression` exception.</span></span> <span data-ttu-id="4d7e8-113">Si `expression` no se proporciona, la pila de llamadas es permanecen sin cambios.</span><span class="sxs-lookup"><span data-stu-id="4d7e8-113">If `expression` is not provided, the call stack is left unchanged.</span></span> <span data-ttu-id="4d7e8-114">Puede tener acceso a la pila de llamadas para la excepción a través de la <xref:System.Exception.StackTrace%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="4d7e8-114">You can access the call stack for the exception through the <xref:System.Exception.StackTrace%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d7e8-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4d7e8-115">Example</span></span>  
 <span data-ttu-id="4d7e8-116">El siguiente código utiliza el `Throw` instrucción se producirá una excepción:</span><span class="sxs-lookup"><span data-stu-id="4d7e8-116">The following code uses the `Throw` statement to throw an exception:</span></span>  
  
 [!code-vb[VbVbalrStatements#84](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/throw-statement_1.vb)]  
  
## <a name="requirements"></a><span data-ttu-id="4d7e8-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4d7e8-117">Requirements</span></span>  
 <span data-ttu-id="4d7e8-118">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="4d7e8-118">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="4d7e8-119">**Módulo:** `Interaction`</span><span class="sxs-lookup"><span data-stu-id="4d7e8-119">**Module:** `Interaction`</span></span>  
  
 <span data-ttu-id="4d7e8-120">**Ensamblado:** biblioteca de tiempo de ejecución de Visual Basic (en Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="4d7e8-120">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d7e8-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d7e8-121">See Also</span></span>  
 [<span data-ttu-id="4d7e8-122">Try...Catch...Finally (instrucción)</span><span class="sxs-lookup"><span data-stu-id="4d7e8-122">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [<span data-ttu-id="4d7e8-123">On Error (instrucción)</span><span class="sxs-lookup"><span data-stu-id="4d7e8-123">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
