---
title: "Función &#39; &lt;nombreProcedimiento&gt;&#39; &#39; t devuelve un valor en todas las rutas de acceso de código"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42105
- vbc42105
helpviewer_keywords:
- BC42105
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5244d97a79f2450f44fe05f63510369914375912
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="function-39ltprocedurenamegt39-doesn39t-return-a-value-on-all-code-paths"></a><span data-ttu-id="99697-102">Función &#39; &lt;nombreProcedimiento&gt;&#39; &#39; t devuelve un valor en todas las rutas de acceso de código</span><span class="sxs-lookup"><span data-stu-id="99697-102">Function &#39;&lt;procedurename&gt;&#39; doesn&#39;t return a value on all code paths</span></span>
<span data-ttu-id="99697-103">Función '\<nombreProcedimiento >' no devuelve un valor en todas las rutas de código.</span><span class="sxs-lookup"><span data-stu-id="99697-103">Function '\<procedurename>' doesn't return a value on all code paths.</span></span> <span data-ttu-id="99697-104">¿Falta una instrucción 'Return'?</span><span class="sxs-lookup"><span data-stu-id="99697-104">Are you missing a 'Return' statement?</span></span>  
  
 <span data-ttu-id="99697-105">A `Function` procedimiento tiene al menos una ruta posible en el código que no devuelve un valor.</span><span class="sxs-lookup"><span data-stu-id="99697-105">A `Function` procedure has at least one possible path through its code that does not return a value.</span></span>  
  
 <span data-ttu-id="99697-106">Puede devolver un valor desde un `Function` procedimiento en cualquiera de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="99697-106">You can return a value from a `Function` procedure in any of the following ways:</span></span>  
  
-   <span data-ttu-id="99697-107">Incluya el valor en un [instrucción Return](../../../visual-basic/language-reference/statements/return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="99697-107">Include the value in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
-   <span data-ttu-id="99697-108">Asigne el valor para el `Function` procedimiento asigne un nombre y, a continuación, realizar un `Exit Function` instrucción.</span><span class="sxs-lookup"><span data-stu-id="99697-108">Assign the value to the `Function` procedure name and then perform an `Exit Function` statement.</span></span>  
  
-   <span data-ttu-id="99697-109">Asigne el valor para el `Function` procedimiento asigne un nombre y, a continuación, realizar la `End Function` instrucción.</span><span class="sxs-lookup"><span data-stu-id="99697-109">Assign the value to the `Function` procedure name and then perform the `End Function` statement.</span></span>  
  
 <span data-ttu-id="99697-110">Si el control se transfiere a `Exit Function` o `End Function` y no ha asignado ningún valor para el nombre del procedimiento, el procedimiento devuelve el valor predeterminado del tipo de datos devuelto.</span><span class="sxs-lookup"><span data-stu-id="99697-110">If control passes to `Exit Function` or `End Function` and you have not assigned any value to the procedure name, the procedure returns the default value of the return data type.</span></span> <span data-ttu-id="99697-111">Para obtener más información, vea "Comportamiento" en [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="99697-111">For more information, see "Behavior" in [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="99697-112">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="99697-112">By default, this message is a warning.</span></span> <span data-ttu-id="99697-113">Para obtener más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [configurar advertencias en Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="99697-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="99697-114">**Id. de error:** BC42105</span><span class="sxs-lookup"><span data-stu-id="99697-114">**Error ID:** BC42105</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="99697-115">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="99697-115">To correct this error</span></span>  
  
-   <span data-ttu-id="99697-116">Compruebe la lógica de flujo de control y asegúrese de que asignar un valor antes de cada instrucción que genera un valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="99697-116">Check your control flow logic and make sure you assign a value before every statement that causes a return.</span></span>  
  
     <span data-ttu-id="99697-117">Es más fácil garantizar que todos los valores devueltos desde el procedimiento devuelve un valor si siempre utiliza el `Return` instrucción.</span><span class="sxs-lookup"><span data-stu-id="99697-117">It is easier to guarantee that every return from the procedure returns a value if you always use the `Return` statement.</span></span> <span data-ttu-id="99697-118">Si lo hace, la última instrucción antes de `End Function` debe ser un `Return` instrucción.</span><span class="sxs-lookup"><span data-stu-id="99697-118">If you do this, the last statement before `End Function` should be a `Return` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99697-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="99697-119">See Also</span></span>  
 [<span data-ttu-id="99697-120">Procedimientos de función</span><span class="sxs-lookup"><span data-stu-id="99697-120">Function Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)  
 [<span data-ttu-id="99697-121">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="99697-121">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="99697-122">Página Compilación, Diseñador de proyectos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99697-122">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
