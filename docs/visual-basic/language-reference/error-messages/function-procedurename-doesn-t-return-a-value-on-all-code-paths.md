---
title: La función '<procedurename>' no devuelve un valor en todas las rutas de acceso a código
ms.date: 07/20/2015
f1_keywords:
- bc42105
- vbc42105
helpviewer_keywords:
- BC42105
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
ms.openlocfilehash: 5564f95048f6b44a48229c7e5be9331839803439
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662104"
---
# <a name="function-procedurename-doesnt-return-a-value-on-all-code-paths"></a><span data-ttu-id="d3de6-102">Función '\<NombreDeProcedimiento >' no devuelve un valor en todas las rutas de código</span><span class="sxs-lookup"><span data-stu-id="d3de6-102">Function '\<procedurename>' doesn't return a value on all code paths</span></span>
<span data-ttu-id="d3de6-103">Función '\<NombreDeProcedimiento >' no devuelve un valor en todas las rutas de código.</span><span class="sxs-lookup"><span data-stu-id="d3de6-103">Function '\<procedurename>' doesn't return a value on all code paths.</span></span> <span data-ttu-id="d3de6-104">¿Falta alguna instrucción 'Return'?</span><span class="sxs-lookup"><span data-stu-id="d3de6-104">Are you missing a 'Return' statement?</span></span>  
  
 <span data-ttu-id="d3de6-105">Un `Function` procedimiento tiene al menos una ruta de acceso posibles a través de su código que no devuelve un valor.</span><span class="sxs-lookup"><span data-stu-id="d3de6-105">A `Function` procedure has at least one possible path through its code that does not return a value.</span></span>  
  
 <span data-ttu-id="d3de6-106">Puede devolver un valor desde un `Function` procedimiento en cualquiera de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="d3de6-106">You can return a value from a `Function` procedure in any of the following ways:</span></span>  
  
- <span data-ttu-id="d3de6-107">Incluya el valor en un [instrucción Return](../../../visual-basic/language-reference/statements/return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d3de6-107">Include the value in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
- <span data-ttu-id="d3de6-108">Asigne el valor para el `Function` procedimiento asigne un nombre y, a continuación, realizar un `Exit Function` instrucción.</span><span class="sxs-lookup"><span data-stu-id="d3de6-108">Assign the value to the `Function` procedure name and then perform an `Exit Function` statement.</span></span>  
  
- <span data-ttu-id="d3de6-109">Asigne el valor para el `Function` procedimiento asigne un nombre y, a continuación, realizar el `End Function` instrucción.</span><span class="sxs-lookup"><span data-stu-id="d3de6-109">Assign the value to the `Function` procedure name and then perform the `End Function` statement.</span></span>  
  
 <span data-ttu-id="d3de6-110">Si el control se transfiere a `Exit Function` o `End Function` y no ha asignado ningún valor para el nombre del procedimiento, el procedimiento devuelve el valor predeterminado del tipo de datos devuelto.</span><span class="sxs-lookup"><span data-stu-id="d3de6-110">If control passes to `Exit Function` or `End Function` and you have not assigned any value to the procedure name, the procedure returns the default value of the return data type.</span></span> <span data-ttu-id="d3de6-111">Para obtener más información, vea "Comportamiento" en [instrucción Function](../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d3de6-111">For more information, see "Behavior" in [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="d3de6-112">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="d3de6-112">By default, this message is a warning.</span></span> <span data-ttu-id="d3de6-113">Para obtener más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="d3de6-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="d3de6-114">**Identificador de error:** BC42105</span><span class="sxs-lookup"><span data-stu-id="d3de6-114">**Error ID:** BC42105</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d3de6-115">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="d3de6-115">To correct this error</span></span>  
  
- <span data-ttu-id="d3de6-116">Compruebe la lógica del flujo de control y asegúrese de que asignar un valor antes de cada instrucción que genera un valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="d3de6-116">Check your control flow logic and make sure you assign a value before every statement that causes a return.</span></span>  
  
     <span data-ttu-id="d3de6-117">Es más fácil garantizar que todos los valores devueltos desde el procedimiento devuelve un valor si siempre usa el `Return` instrucción.</span><span class="sxs-lookup"><span data-stu-id="d3de6-117">It is easier to guarantee that every return from the procedure returns a value if you always use the `Return` statement.</span></span> <span data-ttu-id="d3de6-118">Si lo hace, la última instrucción antes de `End Function` debe ser un `Return` instrucción.</span><span class="sxs-lookup"><span data-stu-id="d3de6-118">If you do this, the last statement before `End Function` should be a `Return` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3de6-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="d3de6-119">See also</span></span>

- [<span data-ttu-id="d3de6-120">Procedimientos de función</span><span class="sxs-lookup"><span data-stu-id="d3de6-120">Function Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)
- [<span data-ttu-id="d3de6-121">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="d3de6-121">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="d3de6-122">Página Compilación, Diseñador de proyectos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d3de6-122">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
