---
title: "Propiedad &#39; &lt;propertyname&gt;&#39; &#39; t devuelve un valor en todas las rutas de acceso de código"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42107
- vbc42107
helpviewer_keywords: BC42107
ms.assetid: 06800966-9c3b-4844-9f13-83ac95607d32
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c9ef5b2ac62412f5684cbc78ab6bebf6bc7b6752
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="property-39ltpropertynamegt39-doesn39t-return-a-value-on-all-code-paths"></a><span data-ttu-id="ee12b-102">Propiedad &#39; &lt;propertyname&gt;&#39; &#39; t devuelve un valor en todas las rutas de acceso de código</span><span class="sxs-lookup"><span data-stu-id="ee12b-102">Property &#39;&lt;propertyname&gt;&#39; doesn&#39;t return a value on all code paths</span></span>
<span data-ttu-id="ee12b-103">Propiedad '\<propertyname >' no devuelve un valor en todas las rutas de código.</span><span class="sxs-lookup"><span data-stu-id="ee12b-103">Property '\<propertyname>' doesn't return a value on all code paths.</span></span> <span data-ttu-id="ee12b-104">Podría producirse una excepción de referencia nula en tiempo de ejecución al usar el resultado.</span><span class="sxs-lookup"><span data-stu-id="ee12b-104">A null reference exception could occur at run time when the result is used.</span></span>  
  
 <span data-ttu-id="ee12b-105">Una propiedad `Get` procedimiento tiene al menos una ruta posible en el código que no devuelve un valor.</span><span class="sxs-lookup"><span data-stu-id="ee12b-105">A property `Get` procedure has at least one possible path through its code that does not return a value.</span></span>  
  
 <span data-ttu-id="ee12b-106">Puede devolver un valor de una propiedad `Get` procedimiento en cualquiera de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="ee12b-106">You can return a value from a property `Get` procedure in any of the following ways:</span></span>  
  
-   <span data-ttu-id="ee12b-107">Asigne el valor al nombre de propiedad y, a continuación, realizar un `Exit Property` instrucción.</span><span class="sxs-lookup"><span data-stu-id="ee12b-107">Assign the value to the property name and then perform an `Exit Property` statement.</span></span>  
  
-   <span data-ttu-id="ee12b-108">Asigne el valor al nombre de propiedad y, a continuación, realizar la `End Get` instrucción.</span><span class="sxs-lookup"><span data-stu-id="ee12b-108">Assign the value to the property name and then perform the `End Get` statement.</span></span>  
  
-   <span data-ttu-id="ee12b-109">Incluya el valor en un [instrucción Return](../../../visual-basic/language-reference/statements/return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ee12b-109">Include the value in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
 <span data-ttu-id="ee12b-110">Si el control se transfiere a `Exit Property` o `End Get` y no ha asignado ningún valor al nombre de propiedad, el `Get` procedimiento devuelve el valor predeterminado del tipo de datos de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="ee12b-110">If control passes to `Exit Property` or `End Get` and you have not assigned any value to the property name, the `Get` procedure returns the default value of the property's data type.</span></span> <span data-ttu-id="ee12b-111">Para obtener más información, vea "Comportamiento" en [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ee12b-111">For more information, see "Behavior" in [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="ee12b-112">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="ee12b-112">By default, this message is a warning.</span></span> <span data-ttu-id="ee12b-113">Para obtener más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [configurar advertencias en Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="ee12b-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="ee12b-114">**Id. de error:** BC42107</span><span class="sxs-lookup"><span data-stu-id="ee12b-114">**Error ID:** BC42107</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ee12b-115">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="ee12b-115">To correct this error</span></span>  
  
-   <span data-ttu-id="ee12b-116">Compruebe la lógica de flujo de control y asegúrese de que asignar un valor antes de cada instrucción que genera un valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="ee12b-116">Check your control flow logic and make sure you assign a value before every statement that causes a return.</span></span>  
  
     <span data-ttu-id="ee12b-117">Es más fácil garantizar que todos los valores devueltos desde el procedimiento devuelve un valor si siempre utiliza el `Return` instrucción.</span><span class="sxs-lookup"><span data-stu-id="ee12b-117">It is easier to guarantee that every return from the procedure returns a value if you always use the `Return` statement.</span></span> <span data-ttu-id="ee12b-118">Si lo hace, la última instrucción antes de `End Get` debe ser un `Return` instrucción.</span><span class="sxs-lookup"><span data-stu-id="ee12b-118">If you do this, the last statement before `End Get` should be a `Return` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee12b-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="ee12b-119">See Also</span></span>  
 [<span data-ttu-id="ee12b-120">Procedimientos de propiedades</span><span class="sxs-lookup"><span data-stu-id="ee12b-120">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)  
 [<span data-ttu-id="ee12b-121">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ee12b-121">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="ee12b-122">Get (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ee12b-122">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
