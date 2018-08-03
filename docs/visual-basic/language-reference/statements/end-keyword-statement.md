---
title: End &lt;palabra clave&gt; (instrucción, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.EndDefinition
helpviewer_keywords:
- End keyword [Visual Basic]
ms.assetid: 42d6e088-ab0f-4cda-88e8-fdce3e5fcf4f
ms.openlocfilehash: 8137434bfd8c26144d78b1761b784cdba4894eaf
ms.sourcegitcommit: 7fe772c6c05a982153655d618c826e9839d39cac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/03/2018
ms.locfileid: "33605269"
---
# <a name="end-ltkeywordgt-statement-visual-basic"></a><span data-ttu-id="a9b87-102">End &lt;palabra clave&gt; (instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a9b87-102">End &lt;keyword&gt; Statement (Visual Basic)</span></span>

<span data-ttu-id="a9b87-103">Cuando va seguido de una palabra clave adicional, termina la definición del bloque de instrucción introducido por esa palabra clave.</span><span class="sxs-lookup"><span data-stu-id="a9b87-103">When followed by an additional keyword, terminates the definition of the statement block introduced by that keyword.</span></span>

## <a name="syntax"></a><span data-ttu-id="a9b87-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a9b87-104">Syntax</span></span>

```vb
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
  
## <a name="parts"></a><span data-ttu-id="a9b87-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="a9b87-105">Parts</span></span>

|<span data-ttu-id="a9b87-106">Parte</span><span class="sxs-lookup"><span data-stu-id="a9b87-106">Part</span></span>|<span data-ttu-id="a9b87-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a9b87-107">Description</span></span>|
|---|---|
|`End`|<span data-ttu-id="a9b87-108">Requerido.</span><span class="sxs-lookup"><span data-stu-id="a9b87-108">Required.</span></span> <span data-ttu-id="a9b87-109">Termina la definición del elemento de programación.</span><span class="sxs-lookup"><span data-stu-id="a9b87-109">Terminates the definition of the programming element.</span></span>|
|`AddHandler`|<span data-ttu-id="a9b87-110">Es obligatorio para terminar una `AddHandler` comenzada por un descriptor de acceso `AddHandler` instrucción personalizada [Event (instrucción)](event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a9b87-110">Required to terminate an `AddHandler` accessor begun by a matching `AddHandler` statement in a custom [Event Statement](event-statement.md).</span></span>|
|`Class`|<span data-ttu-id="a9b87-111">Es obligatorio para terminar una definición de clase comenzada por un [Class (instrucción)](class-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a9b87-111">Required to terminate a class definition begun by a matching [Class Statement](class-statement.md).</span></span>|
|`Enum`|<span data-ttu-id="a9b87-112">Es obligatorio para terminar una definición de enumeración que comienza por una coincidencia [Enum (instrucción)](enum-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a9b87-112">Required to terminate an enumeration definition begun by a matching [Enum Statement](enum-statement.md).</span></span>|
|`Event`|<span data-ttu-id="a9b87-113">Es obligatorio para terminar una `Custom` definición de evento comenzada por un [Event (instrucción)](event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a9b87-113">Required to terminate a `Custom` event definition begun by a matching [Event Statement](event-statement.md).</span></span>|  
|`Function`|<span data-ttu-id="a9b87-114">Es obligatorio para terminar una `Function` definición del procedimiento comenzada por un [instrucción Function](function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a9b87-114">Required to terminate a `Function` procedure definition begun by a matching [Function Statement](function-statement.md).</span></span> <span data-ttu-id="a9b87-115">Si la ejecución se encuentra una `End Function` instrucción, el control vuelve al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="a9b87-115">If execution encounters an `End Function` statement, control returns to the calling code.</span></span>|
|`Get`|<span data-ttu-id="a9b87-116">Es obligatorio para terminar una `Property` definición del procedimiento comenzada por un [Get Statement](get-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a9b87-116">Required to terminate a `Property` procedure definition begun by a matching [Get Statement](get-statement.md).</span></span> <span data-ttu-id="a9b87-117">Si la ejecución se encuentra una `End Get` instrucción, el control vuelve a la instrucción que solicita el valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="a9b87-117">If execution encounters an `End Get` statement, control returns to the statement requesting the property's value.</span></span>|
|`If`|<span data-ttu-id="a9b87-118">Es obligatorio para terminar una `If`... `Then`... `Else` bloquear definición comenzada por una coincidencia `If` instrucción.</span><span class="sxs-lookup"><span data-stu-id="a9b87-118">Required to terminate an `If`...`Then`...`Else` block definition begun by a matching `If` statement.</span></span> <span data-ttu-id="a9b87-119">Consulte [si... Entonces... Else (instrucción)](if-then-else-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a9b87-119">See [If...Then...Else Statement](if-then-else-statement.md).</span></span>|
|`Interface`|<span data-ttu-id="a9b87-120">Es obligatorio para terminar una definición de interfaz que comienza por un [Interface (instrucción)](interface-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a9b87-120">Required to terminate an interface definition begun by a matching [Interface Statement](interface-statement.md).</span></span>|
|`Module`|<span data-ttu-id="a9b87-121">Es obligatorio para terminar una definición de módulo comenzada por una coincidencia [Module (instrucción)](module-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a9b87-121">Required to terminate a module definition begun by a matching [Module Statement](module-statement.md).</span></span>|
|`Namespace`|<span data-ttu-id="a9b87-122">Es obligatorio para terminar una definición de espacio de nombres que comienza por una coincidencia [instrucción Namespace](namespace-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a9b87-122">Required to terminate a namespace definition begun by a matching [Namespace Statement](namespace-statement.md).</span></span>|
|`Operator`|<span data-ttu-id="a9b87-123">Es obligatorio para terminar una definición de operador comenzada por un [Operator (instrucción)](operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a9b87-123">Required to terminate an operator definition begun by a matching [Operator Statement](operator-statement.md).</span></span>|
|`Property`|<span data-ttu-id="a9b87-124">Es obligatorio para terminar una definición de propiedad comenzada por un [Property Statement](property-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a9b87-124">Required to terminate a property definition begun by a matching [Property Statement](property-statement.md).</span></span>|
|`RaiseEvent`|<span data-ttu-id="a9b87-125">Es obligatorio para terminar una `RaiseEvent` comenzada por un descriptor de acceso `RaiseEvent` instrucción personalizada [Event (instrucción)](event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a9b87-125">Required to terminate a `RaiseEvent` accessor begun by a matching `RaiseEvent` statement in a custom [Event Statement](event-statement.md).</span></span>|
|`RemoveHandler`|<span data-ttu-id="a9b87-126">Es obligatorio para terminar una `RemoveHandler` comenzada por un descriptor de acceso `RemoveHandler` instrucción personalizada [Event (instrucción)](event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a9b87-126">Required to terminate a `RemoveHandler` accessor begun by a matching `RemoveHandler` statement in a custom [Event Statement](event-statement.md).</span></span>|
|`Select`|<span data-ttu-id="a9b87-127">Es obligatorio para terminar una `Select`... `Case` bloquear definición comenzada por una coincidencia `Select` instrucción.</span><span class="sxs-lookup"><span data-stu-id="a9b87-127">Required to terminate a `Select`...`Case` block definition begun by a matching `Select` statement.</span></span> <span data-ttu-id="a9b87-128">Consulte [seleccione... Instrucción de caso](select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a9b87-128">See [Select...Case Statement](select-case-statement.md).</span></span>  
|`Set`|<span data-ttu-id="a9b87-129">Es obligatorio para terminar una `Property` definición del procedimiento comenzada por un [instrucción Set](set-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a9b87-129">Required to terminate a `Property` procedure definition begun by a matching [Set Statement](set-statement.md).</span></span> <span data-ttu-id="a9b87-130">Si la ejecución se encuentra una `End Set` instrucción, el control vuelve a la instrucción que establece el valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="a9b87-130">If execution encounters an `End Set` statement, control returns to the statement setting the property's value.</span></span>  
|`Structure`|<span data-ttu-id="a9b87-131">Es obligatorio para terminar una definición de estructura que comienza por una coincidencia [Structure (instrucción)](structure-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a9b87-131">Required to terminate a structure definition begun by a matching [Structure Statement](structure-statement.md).</span></span>  
|`Sub`|<span data-ttu-id="a9b87-132">Es obligatorio para terminar una `Sub` definición del procedimiento comenzada por un [Sub (instrucción)](sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a9b87-132">Required to terminate a `Sub` procedure definition begun by a matching [Sub Statement](sub-statement.md).</span></span> <span data-ttu-id="a9b87-133">Si la ejecución se encuentra una `End Sub` instrucción, el control vuelve al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="a9b87-133">If execution encounters an `End Sub` statement, control returns to the calling code.</span></span>  
|`SyncLock`|<span data-ttu-id="a9b87-134">Es obligatorio para terminar una `SyncLock` bloquear definición comenzada por una coincidencia `SyncLock` instrucción.</span><span class="sxs-lookup"><span data-stu-id="a9b87-134">Required to terminate a `SyncLock` block definition begun by a matching `SyncLock` statement.</span></span> <span data-ttu-id="a9b87-135">Consulte [instrucción SyncLock](synclock-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a9b87-135">See [SyncLock Statement](synclock-statement.md).</span></span>  
|`Try`|<span data-ttu-id="a9b87-136">Es obligatorio para terminar una `Try`... `Catch`... `Finally` bloquear definición comenzada por una coincidencia `Try` instrucción.</span><span class="sxs-lookup"><span data-stu-id="a9b87-136">Required to terminate a `Try`...`Catch`...`Finally` block definition begun by a matching `Try` statement.</span></span> <span data-ttu-id="a9b87-137">Consulte [intente... Catch... Finally (instrucción)](try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a9b87-137">See [Try...Catch...Finally Statement](try-catch-finally-statement.md).</span></span>  
|`While`|<span data-ttu-id="a9b87-138">Es obligatorio para terminar una `While` definición comenzada por una coincidencia de bucle `While` instrucción.</span><span class="sxs-lookup"><span data-stu-id="a9b87-138">Required to terminate a `While` loop definition begun by a matching `While` statement.</span></span> <span data-ttu-id="a9b87-139">Consulte [mientras... End While (instrucción)](while-end-while-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a9b87-139">See [While...End While Statement](while-end-while-statement.md).</span></span>  
|`With`| <span data-ttu-id="a9b87-140">Es obligatorio para terminar una `With` bloquear definición comenzada por una coincidencia `With` instrucción.</span><span class="sxs-lookup"><span data-stu-id="a9b87-140">Required to terminate a `With` block definition begun by a matching `With` statement.</span></span> <span data-ttu-id="a9b87-141">Consulte [con... Terminar con la instrucción](with-end-with-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a9b87-141">See [With...End With Statement](with-end-with-statement.md).</span></span>  
|||
  
## <a name="directives"></a><span data-ttu-id="a9b87-142">Directivas</span><span class="sxs-lookup"><span data-stu-id="a9b87-142">Directives</span></span>

<span data-ttu-id="a9b87-143">Cuando está precedido por un signo de número (`#`), el `End` palabra clave finaliza un bloque de preprocesamiento introducido por la directiva correspondiente.</span><span class="sxs-lookup"><span data-stu-id="a9b87-143">When preceded by a number sign (`#`), the `End` keyword terminates a preprocessing block introduced by the corresponding directive.</span></span>  

```vb
#End ExternalSource
#End If
#End Region
```

|<span data-ttu-id="a9b87-144">Parte</span><span class="sxs-lookup"><span data-stu-id="a9b87-144">Part</span></span>|<span data-ttu-id="a9b87-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="a9b87-145">Description</span></span>|
|---|---|
|`#End`|<span data-ttu-id="a9b87-146">Requerido.</span><span class="sxs-lookup"><span data-stu-id="a9b87-146">Required.</span></span> <span data-ttu-id="a9b87-147">Termina la definición del bloque de preprocesamiento.</span><span class="sxs-lookup"><span data-stu-id="a9b87-147">Terminates the definition of the preprocessing block.</span></span>|
|`ExternalSource`|<span data-ttu-id="a9b87-148">Es obligatorio para terminar un bloque de origen externo que comienza por un [#ExternalSource (directiva)](../directives/externalsource-directive.md).</span><span class="sxs-lookup"><span data-stu-id="a9b87-148">Required to terminate an external source block begun by a matching [#ExternalSource Directive](../directives/externalsource-directive.md).</span></span>|
|`If`|<span data-ttu-id="a9b87-149">Es obligatorio para terminar un bloque de compilación condicional comenzado por una coincidencia `#If` directiva.</span><span class="sxs-lookup"><span data-stu-id="a9b87-149">Required to terminate a conditional compilation block begun by a matching `#If` directive.</span></span> <span data-ttu-id="a9b87-150">Consulte [#If... Then... #Else directivas](../directives/if-then-else-directives.md).</span><span class="sxs-lookup"><span data-stu-id="a9b87-150">See [#If...Then...#Else Directives](../directives/if-then-else-directives.md).</span></span>|
|`Region`|<span data-ttu-id="a9b87-151">Es obligatorio para terminar un bloque de regiones de origen que comienza por un [#Region (directiva)](../directives/region-directive.md).</span><span class="sxs-lookup"><span data-stu-id="a9b87-151">Required to terminate a source region block begun by a matching [#Region Directive](../directives/region-directive.md).</span></span>|
|||

## <a name="remarks"></a><span data-ttu-id="a9b87-152">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a9b87-152">Remarks</span></span>

<span data-ttu-id="a9b87-153">El [instrucción End](end-statement.md), sin una palabra clave adicional, termina la ejecución inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="a9b87-153">The [End Statement](end-statement.md), without an additional keyword, terminates execution immediately.</span></span>

## <a name="smart-device-developer-notes"></a><span data-ttu-id="a9b87-154">Notas de desarrollador de dispositivos inteligentes</span><span class="sxs-lookup"><span data-stu-id="a9b87-154">Smart Device Developer Notes</span></span>  

<span data-ttu-id="a9b87-155">El `End` instrucción sin una palabra clave adicional, no se admite.</span><span class="sxs-lookup"><span data-stu-id="a9b87-155">The `End` statement, without an additional keyword, is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9b87-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9b87-156">See also</span></span>

[<span data-ttu-id="a9b87-157">End (instrucción)</span><span class="sxs-lookup"><span data-stu-id="a9b87-157">End Statement</span></span>](end-statement.md)
