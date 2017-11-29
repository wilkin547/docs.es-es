---
title: "End &lt;palabra clave&gt; (instrucción, Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.EndDefinition
helpviewer_keywords: End keyword [Visual Basic]
ms.assetid: 42d6e088-ab0f-4cda-88e8-fdce3e5fcf4f
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cf0ac1221f8a85a8a43599d9c5ec210884205e5e
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="end-ltkeywordgt-statement-visual-basic"></a><span data-ttu-id="ae848-102">End &lt;palabra clave&gt; (instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ae848-102">End &lt;keyword&gt; Statement (Visual Basic)</span></span>
<span data-ttu-id="ae848-103">Cuando va seguido de una palabra clave adicional, termina la definición del bloque de instrucciones introducida por esa palabra clave.</span><span class="sxs-lookup"><span data-stu-id="ae848-103">When followed by an additional keyword, terminates the definition of the statement block introduced by that keyword.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae848-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ae848-104">Syntax</span></span>  
  
```  
End AddHandler  
End Class   
End Enum   
End Event   
End Function   
End Get   
End If   
End Interface   
End Module   
End Namespace   
End Operator   
End Property   
End RaiseEvent  
End RemoveHandler  
End Select   
End Set   
End Structure   
End Sub   
End SyncLock   
End Try   
End While   
End With  
```  
  
## <a name="parts"></a><span data-ttu-id="ae848-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="ae848-105">Parts</span></span>  
 `End`  
 <span data-ttu-id="ae848-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="ae848-106">Required.</span></span> <span data-ttu-id="ae848-107">Termina la definición del elemento de programación.</span><span class="sxs-lookup"><span data-stu-id="ae848-107">Terminates the definition of the programming element.</span></span>  
  
 `AddHandler`  
 <span data-ttu-id="ae848-108">Es obligatorio para terminar una `AddHandler` descriptor de acceso comenzada por una búsqueda de coincidencias `AddHandler` instrucción en un personalizado [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ae848-108">Required to terminate an `AddHandler` accessor begun by a matching `AddHandler` statement in a custom [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
 `Class`  
 <span data-ttu-id="ae848-109">Es obligatorio para terminar una definición de clase comenzada por una búsqueda de coincidencias [Class (instrucción)](../../../visual-basic/language-reference/statements/class-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ae848-109">Required to terminate a class definition begun by a matching [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md).</span></span>  
  
 `Enum`  
 <span data-ttu-id="ae848-110">Es obligatorio para terminar una definición de enumeración que comienza por una coincidencia [Enum (instrucción)](../../../visual-basic/language-reference/statements/enum-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ae848-110">Required to terminate an enumeration definition begun by a matching [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md).</span></span>  
  
 `Event`  
 <span data-ttu-id="ae848-111">Es obligatorio para terminar una `Custom` definición de evento comenzada por una búsqueda de coincidencias [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ae848-111">Required to terminate a `Custom` event definition begun by a matching [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
 `Function`  
 <span data-ttu-id="ae848-112">Es obligatorio para terminar una `Function` comenzada por una coincidencia de la definición del procedimiento [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ae848-112">Required to terminate a `Function` procedure definition begun by a matching [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span> <span data-ttu-id="ae848-113">Si la ejecución encuentra una `End``Function` instrucción, el control vuelve al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="ae848-113">If execution encounters an `End``Function` statement, control returns to the calling code.</span></span>  
  
 `Get`  
 <span data-ttu-id="ae848-114">Es obligatorio para terminar una `Property` comenzada por una coincidencia de la definición del procedimiento [instrucción Get](../../../visual-basic/language-reference/statements/get-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ae848-114">Required to terminate a `Property` procedure definition begun by a matching [Get Statement](../../../visual-basic/language-reference/statements/get-statement.md).</span></span> <span data-ttu-id="ae848-115">Si la ejecución encuentra una `End``Get` instrucción, el control vuelve a la instrucción que solicita el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="ae848-115">If execution encounters an `End``Get` statement, control returns to the statement requesting the property's value.</span></span>  
  
 `If`  
 <span data-ttu-id="ae848-116">Es obligatorio para terminar una `If`... `Then`... `Else` definición comenzada por una coincidencia del bloque `If` instrucción.</span><span class="sxs-lookup"><span data-stu-id="ae848-116">Required to terminate an `If`...`Then`...`Else` block definition begun by a matching `If` statement.</span></span> <span data-ttu-id="ae848-117">Consulte [si... Then... Else (instrucción)](../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ae848-117">See [If...Then...Else Statement](../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span></span>  
  
 `Interface`  
 <span data-ttu-id="ae848-118">Es obligatorio para terminar una definición de interfaz que comienza por una coincidencia [Interface (instrucción)](../../../visual-basic/language-reference/statements/interface-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ae848-118">Required to terminate an interface definition begun by a matching [Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md).</span></span>  
  
 `Module`  
 <span data-ttu-id="ae848-119">Es obligatorio para terminar una definición de módulo comenzada por una búsqueda de coincidencias [Module (instrucción)](../../../visual-basic/language-reference/statements/module-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ae848-119">Required to terminate a module definition begun by a matching [Module Statement](../../../visual-basic/language-reference/statements/module-statement.md).</span></span>  
  
 `Namespace`  
 <span data-ttu-id="ae848-120">Es obligatorio para terminar una definición de espacio de nombres que comienza por una búsqueda de coincidencias [instrucción Namespace](../../../visual-basic/language-reference/statements/namespace-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ae848-120">Required to terminate a namespace definition begun by a matching [Namespace Statement](../../../visual-basic/language-reference/statements/namespace-statement.md).</span></span>  
  
 `Operator`  
 <span data-ttu-id="ae848-121">Es obligatorio para terminar una definición de operador que comienza por una búsqueda de coincidencias [Operator (instrucción)](../../../visual-basic/language-reference/statements/operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ae848-121">Required to terminate an operator definition begun by a matching [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
 `Property`  
 <span data-ttu-id="ae848-122">Es obligatorio para terminar una definición de propiedad que comienza por una coincidencia [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ae848-122">Required to terminate a property definition begun by a matching [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md).</span></span>  
  
 `RaiseEvent`  
 <span data-ttu-id="ae848-123">Es obligatorio para terminar una `RaiseEvent` descriptor de acceso comenzada por una búsqueda de coincidencias `RaiseEvent` instrucción en un personalizado [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ae848-123">Required to terminate a `RaiseEvent` accessor begun by a matching `RaiseEvent` statement in a custom [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
 `RemoveHandler`  
 <span data-ttu-id="ae848-124">Es obligatorio para terminar una `RemoveHandler` descriptor de acceso comenzada por una búsqueda de coincidencias `RemoveHandler` instrucción en un personalizado [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ae848-124">Required to terminate a `RemoveHandler` accessor begun by a matching `RemoveHandler` statement in a custom [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
 `Select`  
 <span data-ttu-id="ae848-125">Es obligatorio para terminar una `Select`... `Case` definición comenzada por una coincidencia del bloque `Select` instrucción.</span><span class="sxs-lookup"><span data-stu-id="ae848-125">Required to terminate a `Select`...`Case` block definition begun by a matching `Select` statement.</span></span> <span data-ttu-id="ae848-126">Vea [seleccione... Caso instrucción](../../../visual-basic/language-reference/statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ae848-126">See [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
 `Set`  
 <span data-ttu-id="ae848-127">Es obligatorio para terminar una `Property` comenzada por una coincidencia de la definición del procedimiento [instrucción Set](../../../visual-basic/language-reference/statements/set-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ae848-127">Required to terminate a `Property` procedure definition begun by a matching [Set Statement](../../../visual-basic/language-reference/statements/set-statement.md).</span></span> <span data-ttu-id="ae848-128">Si la ejecución encuentra una `End``Set` instrucción, el control vuelve a la instrucción que establece el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="ae848-128">If execution encounters an `End``Set` statement, control returns to the statement setting the property's value.</span></span>  
  
 `Structure`  
 <span data-ttu-id="ae848-129">Es obligatorio para terminar una definición de estructura que comienza por una búsqueda de coincidencias [Structure (instrucción)](../../../visual-basic/language-reference/statements/structure-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ae848-129">Required to terminate a structure definition begun by a matching [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md).</span></span>  
  
 `Sub`  
 <span data-ttu-id="ae848-130">Es obligatorio para terminar una `Sub` comenzada por una coincidencia de la definición del procedimiento [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ae848-130">Required to terminate a `Sub` procedure definition begun by a matching [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md).</span></span> <span data-ttu-id="ae848-131">Si la ejecución encuentra una `End``Sub` instrucción, el control vuelve al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="ae848-131">If execution encounters an `End``Sub` statement, control returns to the calling code.</span></span>  
  
 `SyncLock`  
 <span data-ttu-id="ae848-132">Es obligatorio para terminar una `SyncLock` definición comenzada por una coincidencia del bloque `SyncLock` instrucción.</span><span class="sxs-lookup"><span data-stu-id="ae848-132">Required to terminate a `SyncLock` block definition begun by a matching `SyncLock` statement.</span></span> <span data-ttu-id="ae848-133">Vea [SyncLock (instrucción)](../../../visual-basic/language-reference/statements/synclock-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ae848-133">See [SyncLock Statement](../../../visual-basic/language-reference/statements/synclock-statement.md).</span></span>  
  
 `Try`  
 <span data-ttu-id="ae848-134">Es obligatorio para terminar una `Try`... `Catch`... `Finally` definición comenzada por una coincidencia del bloque `Try` instrucción.</span><span class="sxs-lookup"><span data-stu-id="ae848-134">Required to terminate a `Try`...`Catch`...`Finally` block definition begun by a matching `Try` statement.</span></span> <span data-ttu-id="ae848-135">Vea [intente... Catch... Finally (instrucción)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ae848-135">See [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
 `While`  
 <span data-ttu-id="ae848-136">Es obligatorio para terminar una `While` definición que comienza por una coincidencia de un bucle `While` instrucción.</span><span class="sxs-lookup"><span data-stu-id="ae848-136">Required to terminate a `While` loop definition begun by a matching `While` statement.</span></span> <span data-ttu-id="ae848-137">Vea [mientras... End While (instrucción)](../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ae848-137">See [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span></span>  
  
 `With`  
 <span data-ttu-id="ae848-138">Es obligatorio para terminar una `With` definición comenzada por una coincidencia del bloque `With` instrucción.</span><span class="sxs-lookup"><span data-stu-id="ae848-138">Required to terminate a `With` block definition begun by a matching `With` statement.</span></span> <span data-ttu-id="ae848-139">Consulte [con... Terminar con la instrucción](../../../visual-basic/language-reference/statements/with-end-with-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ae848-139">See [With...End With Statement](../../../visual-basic/language-reference/statements/with-end-with-statement.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae848-140">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ae848-140">Remarks</span></span>  
 <span data-ttu-id="ae848-141">El [End (instrucción)](../../../visual-basic/language-reference/statements/end-statement.md), sin una palabra clave adicional, termina la ejecución inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="ae848-141">The [End Statement](../../../visual-basic/language-reference/statements/end-statement.md), without an additional keyword, terminates execution immediately.</span></span>  
  
 <span data-ttu-id="ae848-142">Cuando está precedido por un signo de número (`#`), el `End` palabra clave finaliza un bloque de preprocesamiento introducido por la directiva correspondiente.</span><span class="sxs-lookup"><span data-stu-id="ae848-142">When preceded by a number sign (`#`), the `End` keyword terminates a preprocessing block introduced by the corresponding directive.</span></span>  
  
 `#End`  
 <span data-ttu-id="ae848-143">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="ae848-143">Required.</span></span> <span data-ttu-id="ae848-144">Termina la definición del bloque de preprocesamiento.</span><span class="sxs-lookup"><span data-stu-id="ae848-144">Terminates the definition of the preprocessing block.</span></span>  
  
 `#ExternalSource`  
 <span data-ttu-id="ae848-145">Es obligatorio para terminar un bloque de origen externo que comienza por una búsqueda de coincidencias [#ExternalSource (directiva)](../../../visual-basic/language-reference/directives/externalsource-directive.md).</span><span class="sxs-lookup"><span data-stu-id="ae848-145">Required to terminate an external source block begun by a matching [#ExternalSource Directive](../../../visual-basic/language-reference/directives/externalsource-directive.md).</span></span>  
  
 `#If`  
 <span data-ttu-id="ae848-146">Es obligatorio para terminar un bloque de compilación condicional que comienza por una búsqueda de coincidencias `#If` directiva.</span><span class="sxs-lookup"><span data-stu-id="ae848-146">Required to terminate a conditional compilation block begun by a matching `#If` directive.</span></span> <span data-ttu-id="ae848-147">Vea [#If... Then... #Else directivas](../../../visual-basic/language-reference/directives/if-then-else-directives.md).</span><span class="sxs-lookup"><span data-stu-id="ae848-147">See [#If...Then...#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md).</span></span>  
  
 `#Region`  
 <span data-ttu-id="ae848-148">Es obligatorio para terminar un bloque de regiones de origen que comienza por una búsqueda de coincidencias [#Region (directiva)](../../../visual-basic/language-reference/directives/region-directive.md).</span><span class="sxs-lookup"><span data-stu-id="ae848-148">Required to terminate a source region block begun by a matching [#Region Directive](../../../visual-basic/language-reference/directives/region-directive.md).</span></span>  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="ae848-149">Notas de desarrollador de Smart Device</span><span class="sxs-lookup"><span data-stu-id="ae848-149">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="ae848-150">El `End` instrucción sin una palabra clave adicional, no se admite.</span><span class="sxs-lookup"><span data-stu-id="ae848-150">The `End` statement, without an additional keyword, is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae848-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae848-151">See Also</span></span>  
 [<span data-ttu-id="ae848-152">End (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ae848-152">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)
