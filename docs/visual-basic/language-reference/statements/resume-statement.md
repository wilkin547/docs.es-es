---
title: Resume (instrucción) (Visual Basic)
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
ms.openlocfilehash: ef6a2e22c1394065ba6127aa3dd388b47238dea8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54624800"
---
# <a name="resume-statement"></a><span data-ttu-id="cbdb2-102">Resume (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="cbdb2-102">Resume Statement</span></span>
<span data-ttu-id="cbdb2-103">Reanuda la ejecución una vez finalizada una rutina de control de errores.</span><span class="sxs-lookup"><span data-stu-id="cbdb2-103">Resumes execution after an error-handling routine is finished.</span></span>  
  
 <span data-ttu-id="cbdb2-104">Se recomienda que utilice control de excepciones estructurado en el código siempre que sea posible, en lugar de utilizar el control no estructurado de excepciones y la `On Error` y `Resume` instrucciones.</span><span class="sxs-lookup"><span data-stu-id="cbdb2-104">We suggest that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` and `Resume` statements.</span></span> <span data-ttu-id="cbdb2-105">Para obtener más información, vea [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) (Try...Catch...Finally [Instrucción, Visual Basic]).</span><span class="sxs-lookup"><span data-stu-id="cbdb2-105">For more information, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbdb2-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cbdb2-106">Syntax</span></span>  
  
```  
Resume [ Next | line ]  
```  
  
## <a name="parts"></a><span data-ttu-id="cbdb2-107">Elementos</span><span class="sxs-lookup"><span data-stu-id="cbdb2-107">Parts</span></span>  
 `Resume`  
 <span data-ttu-id="cbdb2-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="cbdb2-108">Required.</span></span> <span data-ttu-id="cbdb2-109">Si se produjo el error en el mismo procedimiento que el controlador de errores, se reanuda la ejecución con la instrucción que produjo el error.</span><span class="sxs-lookup"><span data-stu-id="cbdb2-109">If the error occurred in the same procedure as the error handler, execution resumes with the statement that caused the error.</span></span> <span data-ttu-id="cbdb2-110">Si se produjo el error en un procedimiento llamado, se reanuda la ejecución en la instrucción que llame por última vez fuera del procedimiento que contiene la rutina de control de errores.</span><span class="sxs-lookup"><span data-stu-id="cbdb2-110">If the error occurred in a called procedure, execution resumes at the statement that last called out of the procedure containing the error-handling routine.</span></span>  
  
 `Next`  
 <span data-ttu-id="cbdb2-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="cbdb2-111">Optional.</span></span> <span data-ttu-id="cbdb2-112">Si se produjo el error en el mismo procedimiento que el controlador de errores, se reanuda la ejecución con la instrucción inmediatamente posterior a la instrucción que produjo el error.</span><span class="sxs-lookup"><span data-stu-id="cbdb2-112">If the error occurred in the same procedure as the error handler, execution resumes with the statement immediately following the statement that caused the error.</span></span> <span data-ttu-id="cbdb2-113">Si se produjo el error en un procedimiento llamado, se reanuda la ejecución con la instrucción inmediatamente posterior a la instrucción que llame por última vez fuera del procedimiento que contiene la rutina de control de errores (o `On Error Resume Next` instrucción).</span><span class="sxs-lookup"><span data-stu-id="cbdb2-113">If the error occurred in a called procedure, execution resumes with the statement immediately following the statement that last called out of the procedure containing the error-handling routine (or `On Error Resume Next` statement).</span></span>  
  
 `line`  
 <span data-ttu-id="cbdb2-114">Opcional.</span><span class="sxs-lookup"><span data-stu-id="cbdb2-114">Optional.</span></span> <span data-ttu-id="cbdb2-115">Reanuda la ejecución en la línea especificada en la sección necesario `line` argumento.</span><span class="sxs-lookup"><span data-stu-id="cbdb2-115">Execution resumes at the line specified in the required `line` argument.</span></span> <span data-ttu-id="cbdb2-116">El `line` argumento es una etiqueta de línea o un número de línea y debe estar en el mismo procedimiento que el controlador de errores.</span><span class="sxs-lookup"><span data-stu-id="cbdb2-116">The `line` argument is a line label or line number and must be in the same procedure as the error handler.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cbdb2-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cbdb2-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cbdb2-118">Le recomendamos que use el control de excepciones estructurado en el código siempre que sea posible, en lugar de utilizar el control no estructurado de excepciones y la `On Error` y `Resume` instrucciones.</span><span class="sxs-lookup"><span data-stu-id="cbdb2-118">We recommend that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` and `Resume` statements.</span></span> <span data-ttu-id="cbdb2-119">Para obtener más información, vea [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) (Try...Catch...Finally [Instrucción, Visual Basic]).</span><span class="sxs-lookup"><span data-stu-id="cbdb2-119">For more information, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
 <span data-ttu-id="cbdb2-120">Si usa un `Resume` instrucción en cualquier lugar distinto en una rutina de control de errores, que se produce un error.</span><span class="sxs-lookup"><span data-stu-id="cbdb2-120">If you use a `Resume` statement anywhere other than in an error-handling routine, an error occurs.</span></span>  
  
 <span data-ttu-id="cbdb2-121">El `Resume` instrucción no se puede usar en cualquier procedimiento que contiene un `Try...Catch...Finally` instrucción.</span><span class="sxs-lookup"><span data-stu-id="cbdb2-121">The `Resume` statement cannot be used in any procedure that contains a `Try...Catch...Finally` statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cbdb2-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cbdb2-122">Example</span></span>  
 <span data-ttu-id="cbdb2-123">Este ejemplo se usa el `Resume` instrucción a fin de control de errores en un procedimiento y, a continuación, reanudar la ejecución con la instrucción que produjo el error.</span><span class="sxs-lookup"><span data-stu-id="cbdb2-123">This example uses the `Resume` statement to end error handling in a procedure and then resume execution with the statement that caused the error.</span></span> <span data-ttu-id="cbdb2-124">Se genera el error número 55 para ilustrar el uso de la `Resume` instrucción.</span><span class="sxs-lookup"><span data-stu-id="cbdb2-124">Error number 55 is generated to illustrate use of the `Resume` statement.</span></span>  
  
 [!code-vb[VbVbalrErrorHandling#16](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/resume-statement_1.vb)]  
  
## <a name="requirements"></a><span data-ttu-id="cbdb2-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cbdb2-125">Requirements</span></span>  
 <span data-ttu-id="cbdb2-126">**Espacio de nombres**: [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="cbdb2-126">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="cbdb2-127">**Ensamblado:** Biblioteca en tiempo de ejecución de Visual Basic (en Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="cbdb2-127">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbdb2-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="cbdb2-128">See also</span></span>
- [<span data-ttu-id="cbdb2-129">Try...Catch...Finally (instrucción)</span><span class="sxs-lookup"><span data-stu-id="cbdb2-129">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="cbdb2-130">Error (instrucción)</span><span class="sxs-lookup"><span data-stu-id="cbdb2-130">Error Statement</span></span>](../../../visual-basic/language-reference/statements/error-statement.md)
- [<span data-ttu-id="cbdb2-131">On Error (instrucción)</span><span class="sxs-lookup"><span data-stu-id="cbdb2-131">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
