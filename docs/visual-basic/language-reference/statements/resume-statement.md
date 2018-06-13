---
title: Resume (Instrucción)
ms.date: 07/20/2015
f1_keywords:
- vb.Resume
- vb.ResumeNext
helpviewer_keywords:
- Next statement [Visual Basic], Resume
- Resume Next statement [Visual Basic]
- execution [Visual Basic], resuming
- run-time errors [Visual Basic], resuming after
- Resume statement [Visual Basic], syntax
- errors [Visual Basic], resuming after
- Error statement [Visual Basic], and Resume statement
- execution
- Resume statement [Visual Basic]
ms.assetid: e24d058b-1a5c-4274-acb9-7d295d3ea537
ms.openlocfilehash: 1d03f631893be51529f29af824de0d684bf43804
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603787"
---
# <a name="resume-statement"></a><span data-ttu-id="52d91-102">Resume (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="52d91-102">Resume Statement</span></span>
<span data-ttu-id="52d91-103">Reanuda la ejecución una vez finalizada una rutina de control de errores.</span><span class="sxs-lookup"><span data-stu-id="52d91-103">Resumes execution after an error-handling routine is finished.</span></span>  
  
 <span data-ttu-id="52d91-104">Se recomienda que utilice el control de excepciones estructurado en el código siempre que sea posible, en lugar de utilizar el control estructurado de excepciones y el `On Error` y `Resume` las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="52d91-104">We suggest that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` and `Resume` statements.</span></span> <span data-ttu-id="52d91-105">Para obtener más información, vea [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) (Try...Catch...Finally [Instrucción, Visual Basic]).</span><span class="sxs-lookup"><span data-stu-id="52d91-105">For more information, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52d91-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="52d91-106">Syntax</span></span>  
  
```  
Resume [ Next | line ]  
```  
  
## <a name="parts"></a><span data-ttu-id="52d91-107">Elementos</span><span class="sxs-lookup"><span data-stu-id="52d91-107">Parts</span></span>  
 `Resume`  
 <span data-ttu-id="52d91-108">Requerido.</span><span class="sxs-lookup"><span data-stu-id="52d91-108">Required.</span></span> <span data-ttu-id="52d91-109">Si el error se produjo en el mismo procedimiento que el controlador de errores, se reanuda la ejecución con la instrucción que produjo el error.</span><span class="sxs-lookup"><span data-stu-id="52d91-109">If the error occurred in the same procedure as the error handler, execution resumes with the statement that caused the error.</span></span> <span data-ttu-id="52d91-110">Si el error se produjo en un procedimiento llamado, la ejecución se reanuda en la instrucción que llame por última vez fuera del procedimiento que contiene la rutina de control de errores.</span><span class="sxs-lookup"><span data-stu-id="52d91-110">If the error occurred in a called procedure, execution resumes at the statement that last called out of the procedure containing the error-handling routine.</span></span>  
  
 `Next`  
 <span data-ttu-id="52d91-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="52d91-111">Optional.</span></span> <span data-ttu-id="52d91-112">Si el error se produjo en el mismo procedimiento que el controlador de errores, se reanuda la ejecución con la instrucción inmediatamente posterior a la instrucción que produjo el error.</span><span class="sxs-lookup"><span data-stu-id="52d91-112">If the error occurred in the same procedure as the error handler, execution resumes with the statement immediately following the statement that caused the error.</span></span> <span data-ttu-id="52d91-113">Si el error se produjo en un procedimiento llamado, la ejecución continúa con la instrucción inmediatamente posterior a la instrucción que llame por última vez fuera del procedimiento que contiene la rutina de control de errores (o `On Error Resume Next` instrucción).</span><span class="sxs-lookup"><span data-stu-id="52d91-113">If the error occurred in a called procedure, execution resumes with the statement immediately following the statement that last called out of the procedure containing the error-handling routine (or `On Error Resume Next` statement).</span></span>  
  
 `line`  
 <span data-ttu-id="52d91-114">Opcional.</span><span class="sxs-lookup"><span data-stu-id="52d91-114">Optional.</span></span> <span data-ttu-id="52d91-115">La ejecución se reanuda en la línea especificada en la sección necesario `line` argumento.</span><span class="sxs-lookup"><span data-stu-id="52d91-115">Execution resumes at the line specified in the required `line` argument.</span></span> <span data-ttu-id="52d91-116">El `line` argumento es una etiqueta de línea o un número de línea y debe estar en el mismo procedimiento que el controlador de errores.</span><span class="sxs-lookup"><span data-stu-id="52d91-116">The `line` argument is a line label or line number and must be in the same procedure as the error handler.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52d91-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="52d91-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="52d91-118">Se recomienda que use el control de excepciones estructurado en el código siempre que sea posible, en lugar de utilizar el control estructurado de excepciones y el `On Error` y `Resume` las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="52d91-118">We recommend that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` and `Resume` statements.</span></span> <span data-ttu-id="52d91-119">Para obtener más información, vea [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) (Try...Catch...Finally [Instrucción, Visual Basic]).</span><span class="sxs-lookup"><span data-stu-id="52d91-119">For more information, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
 <span data-ttu-id="52d91-120">Si utiliza un `Resume` instrucción en cualquier lugar distinto en una rutina de control de errores, que se produce un error.</span><span class="sxs-lookup"><span data-stu-id="52d91-120">If you use a `Resume` statement anywhere other than in an error-handling routine, an error occurs.</span></span>  
  
 <span data-ttu-id="52d91-121">El `Resume` no se puede usar la instrucción en un procedimiento que contenga una `Try...Catch...Finally` instrucción.</span><span class="sxs-lookup"><span data-stu-id="52d91-121">The `Resume` statement cannot be used in any procedure that contains a `Try...Catch...Finally` statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="52d91-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="52d91-122">Example</span></span>  
 <span data-ttu-id="52d91-123">Este ejemplo se utiliza la `Resume` instrucción que se debe terminar en un procedimiento de control de errores y, a continuación, reanudar la ejecución con la instrucción que produjo el error.</span><span class="sxs-lookup"><span data-stu-id="52d91-123">This example uses the `Resume` statement to end error handling in a procedure and then resume execution with the statement that caused the error.</span></span> <span data-ttu-id="52d91-124">Se genera el error número 55 para ilustrar el uso de la `Resume` instrucción.</span><span class="sxs-lookup"><span data-stu-id="52d91-124">Error number 55 is generated to illustrate use of the `Resume` statement.</span></span>  
  
 [!code-vb[VbVbalrErrorHandling#16](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/resume-statement_1.vb)]  
  
## <a name="requirements"></a><span data-ttu-id="52d91-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="52d91-125">Requirements</span></span>  
 <span data-ttu-id="52d91-126">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="52d91-126">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="52d91-127">**Ensamblado:** biblioteca de tiempo de ejecución de Visual Basic (en Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="52d91-127">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52d91-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="52d91-128">See Also</span></span>  
 [<span data-ttu-id="52d91-129">Try...Catch...Finally (instrucción)</span><span class="sxs-lookup"><span data-stu-id="52d91-129">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [<span data-ttu-id="52d91-130">Error (instrucción)</span><span class="sxs-lookup"><span data-stu-id="52d91-130">Error Statement</span></span>](../../../visual-basic/language-reference/statements/error-statement.md)  
 [<span data-ttu-id="52d91-131">On Error (instrucción)</span><span class="sxs-lookup"><span data-stu-id="52d91-131">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
