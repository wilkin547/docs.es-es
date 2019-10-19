---
title: Instrucción resume (Visual Basic)
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
ms.openlocfilehash: 7b8c2e123c04ff9720d690507ee41a6b52f40c3f
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583272"
---
# <a name="resume-statement"></a><span data-ttu-id="14492-102">Resume (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="14492-102">Resume Statement</span></span>
<span data-ttu-id="14492-103">Reanuda la ejecución después de que haya finalizado una rutina de control de errores.</span><span class="sxs-lookup"><span data-stu-id="14492-103">Resumes execution after an error-handling routine is finished.</span></span>  
  
 <span data-ttu-id="14492-104">Se recomienda usar el control de excepciones estructurado en el código siempre que sea posible, en lugar de usar el control de excepciones no estructurado y las instrucciones `On Error` y `Resume`.</span><span class="sxs-lookup"><span data-stu-id="14492-104">We suggest that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` and `Resume` statements.</span></span> <span data-ttu-id="14492-105">Para obtener más información, vea [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) (Try...Catch...Finally [Instrucción, Visual Basic]).</span><span class="sxs-lookup"><span data-stu-id="14492-105">For more information, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14492-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="14492-106">Syntax</span></span>  
  
```vb  
Resume [ Next | line ]  
```  
  
## <a name="parts"></a><span data-ttu-id="14492-107">Elementos</span><span class="sxs-lookup"><span data-stu-id="14492-107">Parts</span></span>  
 `Resume`  
 <span data-ttu-id="14492-108">Requerido.</span><span class="sxs-lookup"><span data-stu-id="14492-108">Required.</span></span> <span data-ttu-id="14492-109">Si el error se produjo en el mismo procedimiento que el controlador de errores, la ejecución se reanuda con la instrucción que causó el error.</span><span class="sxs-lookup"><span data-stu-id="14492-109">If the error occurred in the same procedure as the error handler, execution resumes with the statement that caused the error.</span></span> <span data-ttu-id="14492-110">Si el error se produjo en un procedimiento llamado, la ejecución se reanuda en la instrucción que se ha llamado por última vez en el procedimiento que contiene la rutina de control de errores.</span><span class="sxs-lookup"><span data-stu-id="14492-110">If the error occurred in a called procedure, execution resumes at the statement that last called out of the procedure containing the error-handling routine.</span></span>  
  
 `Next`  
 <span data-ttu-id="14492-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="14492-111">Optional.</span></span> <span data-ttu-id="14492-112">Si el error se produjo en el mismo procedimiento que el controlador de errores, la ejecución se reanudará con la instrucción inmediatamente posterior a la instrucción que causó el error.</span><span class="sxs-lookup"><span data-stu-id="14492-112">If the error occurred in the same procedure as the error handler, execution resumes with the statement immediately following the statement that caused the error.</span></span> <span data-ttu-id="14492-113">Si el error se produjo en un procedimiento llamado, la ejecución se reanuda con la instrucción inmediatamente posterior a la instrucción que se ha llamado por última vez en el procedimiento que contiene la rutina de control de errores (o `On Error Resume Next` instrucción).</span><span class="sxs-lookup"><span data-stu-id="14492-113">If the error occurred in a called procedure, execution resumes with the statement immediately following the statement that last called out of the procedure containing the error-handling routine (or `On Error Resume Next` statement).</span></span>  
  
 `line`  
 <span data-ttu-id="14492-114">Opcional.</span><span class="sxs-lookup"><span data-stu-id="14492-114">Optional.</span></span> <span data-ttu-id="14492-115">La ejecución se reanuda en la línea especificada en el argumento `line` requerido.</span><span class="sxs-lookup"><span data-stu-id="14492-115">Execution resumes at the line specified in the required `line` argument.</span></span> <span data-ttu-id="14492-116">El `line` argumento es una etiqueta de línea o un número de línea y debe estar en el mismo procedimiento que el controlador de errores.</span><span class="sxs-lookup"><span data-stu-id="14492-116">The `line` argument is a line label or line number and must be in the same procedure as the error handler.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="14492-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="14492-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="14492-118">Se recomienda usar el control de excepciones estructurado en el código siempre que sea posible, en lugar de usar el control de excepciones no estructurado y las instrucciones `On Error` y `Resume`.</span><span class="sxs-lookup"><span data-stu-id="14492-118">We recommend that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` and `Resume` statements.</span></span> <span data-ttu-id="14492-119">Para obtener más información, vea [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) (Try...Catch...Finally [Instrucción, Visual Basic]).</span><span class="sxs-lookup"><span data-stu-id="14492-119">For more information, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
 <span data-ttu-id="14492-120">Si utiliza una instrucción `Resume` en cualquier lugar que no sea en una rutina de control de errores, se producirá un error.</span><span class="sxs-lookup"><span data-stu-id="14492-120">If you use a `Resume` statement anywhere other than in an error-handling routine, an error occurs.</span></span>  
  
 <span data-ttu-id="14492-121">No se puede usar la instrucción `Resume` en ningún procedimiento que contenga una instrucción `Try...Catch...Finally`.</span><span class="sxs-lookup"><span data-stu-id="14492-121">The `Resume` statement cannot be used in any procedure that contains a `Try...Catch...Finally` statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14492-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="14492-122">Example</span></span>  
 <span data-ttu-id="14492-123">En este ejemplo se utiliza la instrucción `Resume` para finalizar el control de errores en un procedimiento y, a continuación, reanudar la ejecución con la instrucción que causó el error.</span><span class="sxs-lookup"><span data-stu-id="14492-123">This example uses the `Resume` statement to end error handling in a procedure and then resume execution with the statement that caused the error.</span></span> <span data-ttu-id="14492-124">Se genera el número de error 55 para mostrar el uso de la instrucción `Resume`.</span><span class="sxs-lookup"><span data-stu-id="14492-124">Error number 55 is generated to illustrate use of the `Resume` statement.</span></span>  
  
 [!code-vb[VbVbalrErrorHandling#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#16)]  
  
## <a name="requirements"></a><span data-ttu-id="14492-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="14492-125">Requirements</span></span>  
 <span data-ttu-id="14492-126">**Espacio de nombres:** [Microsoft. VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="14492-126">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="14492-127">**Ensamblado:** Biblioteca en tiempo de ejecución de Visual Basic (en Microsoft. VisualBasic. dll)</span><span class="sxs-lookup"><span data-stu-id="14492-127">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14492-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="14492-128">See also</span></span>

- [<span data-ttu-id="14492-129">Try...Catch...Finally (instrucción)</span><span class="sxs-lookup"><span data-stu-id="14492-129">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="14492-130">Error (instrucción)</span><span class="sxs-lookup"><span data-stu-id="14492-130">Error Statement</span></span>](../../../visual-basic/language-reference/statements/error-statement.md)
- [<span data-ttu-id="14492-131">On Error (instrucción)</span><span class="sxs-lookup"><span data-stu-id="14492-131">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
