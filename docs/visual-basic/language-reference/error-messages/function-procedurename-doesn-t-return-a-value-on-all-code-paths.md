---
title: La función '<procedurename>' no devuelve un valor en todas las rutas de acceso a código
ms.date: 07/20/2015
f1_keywords:
- bc42105
- vbc42105
helpviewer_keywords:
- BC42105
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
ms.openlocfilehash: 19b305e337767dfb34718aed7b665f142851bd36
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163368"
---
# <a name="bc42105-function-procedurename-doesnt-return-a-value-on-all-code-paths"></a><span data-ttu-id="91aef-102">BC42105: la función ' \<procedurename> ' no devuelve un valor en todas las rutas de código</span><span class="sxs-lookup"><span data-stu-id="91aef-102">BC42105: Function '\<procedurename>' doesn't return a value on all code paths</span></span>

<span data-ttu-id="91aef-103">La función ' \<procedurename> ' no devuelve un valor en todas las rutas de acceso de código.</span><span class="sxs-lookup"><span data-stu-id="91aef-103">Function '\<procedurename>' doesn't return a value on all code paths.</span></span> <span data-ttu-id="91aef-104">¿Falta una instrucción ' Return '?</span><span class="sxs-lookup"><span data-stu-id="91aef-104">Are you missing a 'Return' statement?</span></span>

 <span data-ttu-id="91aef-105">Un `Function` procedimiento tiene al menos una ruta de acceso posible a través de su código que no devuelve un valor.</span><span class="sxs-lookup"><span data-stu-id="91aef-105">A `Function` procedure has at least one possible path through its code that does not return a value.</span></span>

 <span data-ttu-id="91aef-106">Puede devolver un valor de un `Function` procedimiento de cualquiera de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="91aef-106">You can return a value from a `Function` procedure in any of the following ways:</span></span>

- <span data-ttu-id="91aef-107">Incluya el valor en una [instrucción return](../statements/return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="91aef-107">Include the value in a [Return Statement](../statements/return-statement.md).</span></span>

- <span data-ttu-id="91aef-108">Asigne el valor al `Function` nombre del procedimiento y, a continuación, realice una `Exit Function` instrucción.</span><span class="sxs-lookup"><span data-stu-id="91aef-108">Assign the value to the `Function` procedure name and then perform an `Exit Function` statement.</span></span>

- <span data-ttu-id="91aef-109">Asigne el valor al `Function` nombre del procedimiento y, a continuación, realice la `End Function` instrucción.</span><span class="sxs-lookup"><span data-stu-id="91aef-109">Assign the value to the `Function` procedure name and then perform the `End Function` statement.</span></span>

 <span data-ttu-id="91aef-110">Si el control pasa a `Exit Function` o `End Function` y no ha asignado ningún valor al nombre del procedimiento, el procedimiento devuelve el valor predeterminado del tipo de datos devuelto.</span><span class="sxs-lookup"><span data-stu-id="91aef-110">If control passes to `Exit Function` or `End Function` and you have not assigned any value to the procedure name, the procedure returns the default value of the return data type.</span></span> <span data-ttu-id="91aef-111">Para obtener más información, vea el tema sobre el comportamiento en la [instrucción function](../statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="91aef-111">For more information, see "Behavior" in [Function Statement](../statements/function-statement.md).</span></span>

 <span data-ttu-id="91aef-112">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="91aef-112">By default, this message is a warning.</span></span> <span data-ttu-id="91aef-113">Para obtener más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="91aef-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="91aef-114">**Identificador de error:** BC42105</span><span class="sxs-lookup"><span data-stu-id="91aef-114">**Error ID:** BC42105</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="91aef-115">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="91aef-115">To correct this error</span></span>

- <span data-ttu-id="91aef-116">Compruebe la lógica del flujo de control y asegúrese de asignar un valor antes de cada instrucción que produce una devolución.</span><span class="sxs-lookup"><span data-stu-id="91aef-116">Check your control flow logic and make sure you assign a value before every statement that causes a return.</span></span>

     <span data-ttu-id="91aef-117">Es más fácil garantizar que todas las devoluciones del procedimiento devuelvan un valor si siempre se usa la `Return` instrucción.</span><span class="sxs-lookup"><span data-stu-id="91aef-117">It is easier to guarantee that every return from the procedure returns a value if you always use the `Return` statement.</span></span> <span data-ttu-id="91aef-118">Si lo hace, la última instrucción antes de `End Function` debe ser una `Return` instrucción.</span><span class="sxs-lookup"><span data-stu-id="91aef-118">If you do this, the last statement before `End Function` should be a `Return` statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="91aef-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="91aef-119">See also</span></span>

- [<span data-ttu-id="91aef-120">Procedimientos de función</span><span class="sxs-lookup"><span data-stu-id="91aef-120">Function Procedures</span></span>](../../programming-guide/language-features/procedures/function-procedures.md)
- [<span data-ttu-id="91aef-121">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="91aef-121">Function Statement</span></span>](../statements/function-statement.md)
- [<span data-ttu-id="91aef-122">Página Compilación, Diseñador de proyectos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="91aef-122">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
