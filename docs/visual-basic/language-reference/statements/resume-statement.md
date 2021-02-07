---
description: 'Más información acerca de: resume (instrucción)'
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
ms.openlocfilehash: fd3a02fc2606355d7e3a34f5c0d69eef577809de
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99741190"
---
# <a name="resume-statement"></a><span data-ttu-id="e88ab-103">Resume (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="e88ab-103">Resume Statement</span></span>

<span data-ttu-id="e88ab-104">Reanuda la ejecución después de que haya finalizado una rutina de control de errores.</span><span class="sxs-lookup"><span data-stu-id="e88ab-104">Resumes execution after an error-handling routine is finished.</span></span>  
  
 <span data-ttu-id="e88ab-105">Se recomienda usar el control de excepciones estructurado en el código siempre que sea posible, en lugar de usar el control de excepciones no estructurado y las `On Error` `Resume` instrucciones y.</span><span class="sxs-lookup"><span data-stu-id="e88ab-105">We suggest that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` and `Resume` statements.</span></span> <span data-ttu-id="e88ab-106">Para obtener más información, vea [Instrucción Try...Catch...Finally (Visual Basic)](try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e88ab-106">For more information, see [Try...Catch...Finally Statement](try-catch-finally-statement.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e88ab-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e88ab-107">Syntax</span></span>  
  
```vb  
Resume [ Next | line ]  
```  
  
## <a name="parts"></a><span data-ttu-id="e88ab-108">Partes</span><span class="sxs-lookup"><span data-stu-id="e88ab-108">Parts</span></span>  

 `Resume`  
 <span data-ttu-id="e88ab-109">Necesario.</span><span class="sxs-lookup"><span data-stu-id="e88ab-109">Required.</span></span> <span data-ttu-id="e88ab-110">Si el error se produjo en el mismo procedimiento que el controlador de errores, la ejecución se reanuda con la instrucción que causó el error.</span><span class="sxs-lookup"><span data-stu-id="e88ab-110">If the error occurred in the same procedure as the error handler, execution resumes with the statement that caused the error.</span></span> <span data-ttu-id="e88ab-111">Si el error se produjo en un procedimiento llamado, la ejecución se reanuda en la instrucción que se ha llamado por última vez en el procedimiento que contiene la rutina de control de errores.</span><span class="sxs-lookup"><span data-stu-id="e88ab-111">If the error occurred in a called procedure, execution resumes at the statement that last called out of the procedure containing the error-handling routine.</span></span>  
  
 `Next`  
 <span data-ttu-id="e88ab-112">Opcional.</span><span class="sxs-lookup"><span data-stu-id="e88ab-112">Optional.</span></span> <span data-ttu-id="e88ab-113">Si el error se produjo en el mismo procedimiento que el controlador de errores, la ejecución se reanudará con la instrucción inmediatamente posterior a la instrucción que causó el error.</span><span class="sxs-lookup"><span data-stu-id="e88ab-113">If the error occurred in the same procedure as the error handler, execution resumes with the statement immediately following the statement that caused the error.</span></span> <span data-ttu-id="e88ab-114">Si el error se produjo en un procedimiento llamado, la ejecución se reanuda con la instrucción inmediatamente posterior a la instrucción que se ha llamado por última vez en el procedimiento que contiene la rutina de control de errores (o `On Error Resume Next` instrucción).</span><span class="sxs-lookup"><span data-stu-id="e88ab-114">If the error occurred in a called procedure, execution resumes with the statement immediately following the statement that last called out of the procedure containing the error-handling routine (or `On Error Resume Next` statement).</span></span>  
  
 `line`  
 <span data-ttu-id="e88ab-115">Opcional.</span><span class="sxs-lookup"><span data-stu-id="e88ab-115">Optional.</span></span> <span data-ttu-id="e88ab-116">La ejecución se reanuda en la línea especificada en el `line` argumento requerido.</span><span class="sxs-lookup"><span data-stu-id="e88ab-116">Execution resumes at the line specified in the required `line` argument.</span></span> <span data-ttu-id="e88ab-117">El `line` argumento es una etiqueta de línea o un número de línea y debe estar en el mismo procedimiento que el controlador de errores.</span><span class="sxs-lookup"><span data-stu-id="e88ab-117">The `line` argument is a line label or line number and must be in the same procedure as the error handler.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e88ab-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e88ab-118">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e88ab-119">Se recomienda usar el control de excepciones estructurado en el código siempre que sea posible, en lugar de usar el control de excepciones no estructurado y las `On Error` `Resume` instrucciones y.</span><span class="sxs-lookup"><span data-stu-id="e88ab-119">We recommend that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` and `Resume` statements.</span></span> <span data-ttu-id="e88ab-120">Para obtener más información, vea [Instrucción Try...Catch...Finally (Visual Basic)](try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e88ab-120">For more information, see [Try...Catch...Finally Statement](try-catch-finally-statement.md).</span></span>  
  
 <span data-ttu-id="e88ab-121">Si utiliza una `Resume` instrucción que no sea en una rutina de control de errores, se producirá un error.</span><span class="sxs-lookup"><span data-stu-id="e88ab-121">If you use a `Resume` statement anywhere other than in an error-handling routine, an error occurs.</span></span>  
  
 <span data-ttu-id="e88ab-122">La `Resume` instrucción no se puede usar en ningún procedimiento que contenga una `Try...Catch...Finally` instrucción.</span><span class="sxs-lookup"><span data-stu-id="e88ab-122">The `Resume` statement cannot be used in any procedure that contains a `Try...Catch...Finally` statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e88ab-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e88ab-123">Example</span></span>  

 <span data-ttu-id="e88ab-124">En este ejemplo se utiliza la `Resume` instrucción para finalizar el control de errores en un procedimiento y, a continuación, reanudar la ejecución con la instrucción que causó el error.</span><span class="sxs-lookup"><span data-stu-id="e88ab-124">This example uses the `Resume` statement to end error handling in a procedure and then resume execution with the statement that caused the error.</span></span> <span data-ttu-id="e88ab-125">Se genera el número de error 55 para mostrar el uso de la `Resume` instrucción.</span><span class="sxs-lookup"><span data-stu-id="e88ab-125">Error number 55 is generated to illustrate use of the `Resume` statement.</span></span>  
  
 [!code-vb[VbVbalrErrorHandling#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#16)]  
  
## <a name="requirements"></a><span data-ttu-id="e88ab-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e88ab-126">Requirements</span></span>  

 <span data-ttu-id="e88ab-127">**Espacio de nombres:** [Microsoft. VisualBasic](../runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="e88ab-127">**Namespace:** [Microsoft.VisualBasic](../runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="e88ab-128">**Ensamblado:** Biblioteca en tiempo de ejecución de Visual Basic (en Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="e88ab-128">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e88ab-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="e88ab-129">See also</span></span>

- [<span data-ttu-id="e88ab-130">Try...Catch...Finally (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e88ab-130">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)
- [<span data-ttu-id="e88ab-131">Error (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="e88ab-131">Error Statement</span></span>](error-statement.md)
- [<span data-ttu-id="e88ab-132">Instrucción On Error</span><span class="sxs-lookup"><span data-stu-id="e88ab-132">On Error Statement</span></span>](on-error-statement.md)
