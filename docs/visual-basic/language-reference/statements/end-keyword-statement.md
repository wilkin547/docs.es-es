---
description: 'Más información acerca de: <keyword> instrucción end (Visual Basic)'
title: Instrucción End <keyword>
ms.date: 07/20/2015
f1_keywords:
- vb.EndDefinition
helpviewer_keywords:
- End keyword [Visual Basic]
ms.assetid: 42d6e088-ab0f-4cda-88e8-fdce3e5fcf4f
ms.openlocfilehash: ba21d4ba68a054d77d4f29307d49ed8e82bb6b50
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99769200"
---
# <a name="end-keyword-statement-visual-basic"></a><span data-ttu-id="494b3-103">End \<keyword> (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="494b3-103">End \<keyword> Statement (Visual Basic)</span></span>

<span data-ttu-id="494b3-104">Cuando va seguido de una palabra clave adicional, finaliza la definición del bloque de instrucciones introducido por esa palabra clave.</span><span class="sxs-lookup"><span data-stu-id="494b3-104">When followed by an additional keyword, terminates the definition of the statement block introduced by that keyword.</span></span>

## <a name="syntax"></a><span data-ttu-id="494b3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="494b3-105">Syntax</span></span>

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
  
## <a name="parts"></a><span data-ttu-id="494b3-106">Partes</span><span class="sxs-lookup"><span data-stu-id="494b3-106">Parts</span></span>

|<span data-ttu-id="494b3-107">Parte</span><span class="sxs-lookup"><span data-stu-id="494b3-107">Part</span></span>|<span data-ttu-id="494b3-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="494b3-108">Description</span></span>|
|---|---|
|`End`|<span data-ttu-id="494b3-109">Necesario.</span><span class="sxs-lookup"><span data-stu-id="494b3-109">Required.</span></span> <span data-ttu-id="494b3-110">Finaliza la definición del elemento de programación.</span><span class="sxs-lookup"><span data-stu-id="494b3-110">Terminates the definition of the programming element.</span></span>|
|`AddHandler`|<span data-ttu-id="494b3-111">Obligatorio para finalizar un `AddHandler` descriptor de acceso Iniciado por una `AddHandler` instrucción coincidente en una [instrucción de evento](event-statement.md)personalizada.</span><span class="sxs-lookup"><span data-stu-id="494b3-111">Required to terminate an `AddHandler` accessor begun by a matching `AddHandler` statement in a custom [Event Statement](event-statement.md).</span></span>|
|`Class`|<span data-ttu-id="494b3-112">Necesario para terminar una definición de clase que comienza por una [instrucción de clase](class-statement.md)coincidente.</span><span class="sxs-lookup"><span data-stu-id="494b3-112">Required to terminate a class definition begun by a matching [Class Statement](class-statement.md).</span></span>|
|`Enum`|<span data-ttu-id="494b3-113">Necesario para terminar una definición de enumeración iniciada por una [instrucción enum](enum-statement.md)coincidente.</span><span class="sxs-lookup"><span data-stu-id="494b3-113">Required to terminate an enumeration definition begun by a matching [Enum Statement](enum-statement.md).</span></span>|
|`Event`|<span data-ttu-id="494b3-114">Necesario para terminar una `Custom` definición de evento iniciada por una [instrucción de evento](event-statement.md)coincidente.</span><span class="sxs-lookup"><span data-stu-id="494b3-114">Required to terminate a `Custom` event definition begun by a matching [Event Statement](event-statement.md).</span></span>|  
|`Function`|<span data-ttu-id="494b3-115">Necesario para terminar una `Function` definición de procedimiento iniciada por una [instrucción de función](function-statement.md)coincidente.</span><span class="sxs-lookup"><span data-stu-id="494b3-115">Required to terminate a `Function` procedure definition begun by a matching [Function Statement](function-statement.md).</span></span> <span data-ttu-id="494b3-116">Si la ejecución encuentra una `End Function` instrucción, el control vuelve al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="494b3-116">If execution encounters an `End Function` statement, control returns to the calling code.</span></span>|
|`Get`|<span data-ttu-id="494b3-117">Necesario para terminar una `Property` definición de procedimiento iniciada por una [instrucción Get](get-statement.md)coincidente.</span><span class="sxs-lookup"><span data-stu-id="494b3-117">Required to terminate a `Property` procedure definition begun by a matching [Get Statement](get-statement.md).</span></span> <span data-ttu-id="494b3-118">Si la ejecución encuentra una `End Get` instrucción, el control vuelve a la instrucción que solicita el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="494b3-118">If execution encounters an `End Get` statement, control returns to the statement requesting the property's value.</span></span>|
|`If`|<span data-ttu-id="494b3-119">Requerido para terminar una `If` ... `Then` ...`Else` definición de bloque iniciada por una `If` instrucción coincidente.</span><span class="sxs-lookup"><span data-stu-id="494b3-119">Required to terminate an `If`...`Then`...`Else` block definition begun by a matching `If` statement.</span></span> <span data-ttu-id="494b3-120">Vea [If... Después... Else (instrucción](if-then-else-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="494b3-120">See [If...Then...Else Statement](if-then-else-statement.md).</span></span>|
|`Interface`|<span data-ttu-id="494b3-121">Necesario para terminar una definición de interfaz iniciada por una [instrucción de interfaz](interface-statement.md)coincidente.</span><span class="sxs-lookup"><span data-stu-id="494b3-121">Required to terminate an interface definition begun by a matching [Interface Statement](interface-statement.md).</span></span>|
|`Module`|<span data-ttu-id="494b3-122">Necesario para terminar una definición de módulo iniciada por una [instrucción de módulo](module-statement.md)coincidente.</span><span class="sxs-lookup"><span data-stu-id="494b3-122">Required to terminate a module definition begun by a matching [Module Statement](module-statement.md).</span></span>|
|`Namespace`|<span data-ttu-id="494b3-123">Necesario para terminar una definición de espacio de nombres iniciada por una [instrucción de espacio de nombres](namespace-statement.md)coincidente.</span><span class="sxs-lookup"><span data-stu-id="494b3-123">Required to terminate a namespace definition begun by a matching [Namespace Statement](namespace-statement.md).</span></span>|
|`Operator`|<span data-ttu-id="494b3-124">Necesario para terminar una definición de operador iniciada por una [instrucción de operador](operator-statement.md)coincidente.</span><span class="sxs-lookup"><span data-stu-id="494b3-124">Required to terminate an operator definition begun by a matching [Operator Statement](operator-statement.md).</span></span>|
|`Property`|<span data-ttu-id="494b3-125">Necesario para terminar una definición de propiedad iniciada por una [instrucción de propiedad](property-statement.md)coincidente.</span><span class="sxs-lookup"><span data-stu-id="494b3-125">Required to terminate a property definition begun by a matching [Property Statement](property-statement.md).</span></span>|
|`RaiseEvent`|<span data-ttu-id="494b3-126">Necesario para terminar un `RaiseEvent` descriptor de acceso Iniciado por una `RaiseEvent` instrucción coincidente en una [instrucción de evento](event-statement.md)personalizada.</span><span class="sxs-lookup"><span data-stu-id="494b3-126">Required to terminate a `RaiseEvent` accessor begun by a matching `RaiseEvent` statement in a custom [Event Statement](event-statement.md).</span></span>|
|`RemoveHandler`|<span data-ttu-id="494b3-127">Necesario para terminar un `RemoveHandler` descriptor de acceso Iniciado por una `RemoveHandler` instrucción coincidente en una [instrucción de evento](event-statement.md)personalizada.</span><span class="sxs-lookup"><span data-stu-id="494b3-127">Required to terminate a `RemoveHandler` accessor begun by a matching `RemoveHandler` statement in a custom [Event Statement](event-statement.md).</span></span>|
|`Select`|<span data-ttu-id="494b3-128">Necesario para terminar una `Select` definición de bloque... que `Case` comienza por una `Select` instrucción coincidente.</span><span class="sxs-lookup"><span data-stu-id="494b3-128">Required to terminate a `Select`...`Case` block definition begun by a matching `Select` statement.</span></span> <span data-ttu-id="494b3-129">Vea [Select... Instrucción Case](select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="494b3-129">See [Select...Case Statement](select-case-statement.md).</span></span>  
|`Set`|<span data-ttu-id="494b3-130">Necesario para terminar una `Property` definición de procedimiento que comienza por una [instrucción set](set-statement.md)coincidente.</span><span class="sxs-lookup"><span data-stu-id="494b3-130">Required to terminate a `Property` procedure definition begun by a matching [Set Statement](set-statement.md).</span></span> <span data-ttu-id="494b3-131">Si la ejecución encuentra una `End Set` instrucción, el control vuelve a la instrucción que establece el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="494b3-131">If execution encounters an `End Set` statement, control returns to the statement setting the property's value.</span></span>  
|`Structure`|<span data-ttu-id="494b3-132">Necesario para terminar una definición de estructura que comienza por una [instrucción de estructura](structure-statement.md)coincidente.</span><span class="sxs-lookup"><span data-stu-id="494b3-132">Required to terminate a structure definition begun by a matching [Structure Statement](structure-statement.md).</span></span>  
|`Sub`|<span data-ttu-id="494b3-133">Necesario para terminar una `Sub` definición de procedimiento que comienza por una [instrucción Sub](sub-statement.md)coincidente.</span><span class="sxs-lookup"><span data-stu-id="494b3-133">Required to terminate a `Sub` procedure definition begun by a matching [Sub Statement](sub-statement.md).</span></span> <span data-ttu-id="494b3-134">Si la ejecución encuentra una `End Sub` instrucción, el control vuelve al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="494b3-134">If execution encounters an `End Sub` statement, control returns to the calling code.</span></span>  
|`SyncLock`|<span data-ttu-id="494b3-135">Necesario para terminar una `SyncLock` definición de bloque iniciada por una `SyncLock` instrucción coincidente.</span><span class="sxs-lookup"><span data-stu-id="494b3-135">Required to terminate a `SyncLock` block definition begun by a matching `SyncLock` statement.</span></span> <span data-ttu-id="494b3-136">Vea la [instrucción SyncLock](synclock-statement.md).</span><span class="sxs-lookup"><span data-stu-id="494b3-136">See [SyncLock Statement](synclock-statement.md).</span></span>  
|`Try`|<span data-ttu-id="494b3-137">Requerido para terminar una `Try` ... `Catch` ...`Finally` definición de bloque iniciada por una `Try` instrucción coincidente.</span><span class="sxs-lookup"><span data-stu-id="494b3-137">Required to terminate a `Try`...`Catch`...`Finally` block definition begun by a matching `Try` statement.</span></span> <span data-ttu-id="494b3-138">Vea [try... Detectar... Finally](try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="494b3-138">See [Try...Catch...Finally Statement](try-catch-finally-statement.md).</span></span>  
|`While`|<span data-ttu-id="494b3-139">Necesario para terminar una `While` definición de bucle iniciada por una `While` instrucción coincidente.</span><span class="sxs-lookup"><span data-stu-id="494b3-139">Required to terminate a `While` loop definition begun by a matching `While` statement.</span></span> <span data-ttu-id="494b3-140">Vea [while... End while (instrucción](while-end-while-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="494b3-140">See [While...End While Statement](while-end-while-statement.md).</span></span>  
|`With`| <span data-ttu-id="494b3-141">Necesario para terminar una `With` definición de bloque iniciada por una `With` instrucción coincidente.</span><span class="sxs-lookup"><span data-stu-id="494b3-141">Required to terminate a `With` block definition begun by a matching `With` statement.</span></span> <span data-ttu-id="494b3-142">Vea [con... End with](with-end-with-statement.md).</span><span class="sxs-lookup"><span data-stu-id="494b3-142">See [With...End With Statement](with-end-with-statement.md).</span></span>  
|||
  
## <a name="directives"></a><span data-ttu-id="494b3-143">Directivas</span><span class="sxs-lookup"><span data-stu-id="494b3-143">Directives</span></span>

<span data-ttu-id="494b3-144">Cuando va precedido de un signo de número ( `#` ), la `End` palabra clave finaliza un bloque de preprocesamiento introducido por la directiva correspondiente.</span><span class="sxs-lookup"><span data-stu-id="494b3-144">When preceded by a number sign (`#`), the `End` keyword terminates a preprocessing block introduced by the corresponding directive.</span></span>  

```vb
#End ExternalSource
#End If
#End Region
```

|<span data-ttu-id="494b3-145">Parte</span><span class="sxs-lookup"><span data-stu-id="494b3-145">Part</span></span>|<span data-ttu-id="494b3-146">Descripción</span><span class="sxs-lookup"><span data-stu-id="494b3-146">Description</span></span>|
|---|---|
|`#End`|<span data-ttu-id="494b3-147">Necesario.</span><span class="sxs-lookup"><span data-stu-id="494b3-147">Required.</span></span> <span data-ttu-id="494b3-148">Finaliza la definición del bloque de preprocesamiento.</span><span class="sxs-lookup"><span data-stu-id="494b3-148">Terminates the definition of the preprocessing block.</span></span>|
|`ExternalSource`|<span data-ttu-id="494b3-149">Obligatorio para finalizar un bloque de origen externo Iniciado por una [Directiva de #ExternalSource](../directives/externalsource-directive.md)coincidente.</span><span class="sxs-lookup"><span data-stu-id="494b3-149">Required to terminate an external source block begun by a matching [#ExternalSource Directive](../directives/externalsource-directive.md).</span></span>|
|`If`|<span data-ttu-id="494b3-150">Necesario para terminar un bloque de compilación condicional Iniciado por una `#If` Directiva coincidente.</span><span class="sxs-lookup"><span data-stu-id="494b3-150">Required to terminate a conditional compilation block begun by a matching `#If` directive.</span></span> <span data-ttu-id="494b3-151">Vea [#If... Then... #Else directivas](../directives/if-then-else-directives.md).</span><span class="sxs-lookup"><span data-stu-id="494b3-151">See [#If...Then...#Else Directives](../directives/if-then-else-directives.md).</span></span>|
|`Region`|<span data-ttu-id="494b3-152">Obligatorio para terminar un bloque de región de origen Iniciado por una [Directiva de #Region](../directives/region-directive.md)coincidente.</span><span class="sxs-lookup"><span data-stu-id="494b3-152">Required to terminate a source region block begun by a matching [#Region Directive](../directives/region-directive.md).</span></span>|
|||

## <a name="remarks"></a><span data-ttu-id="494b3-153">Observaciones</span><span class="sxs-lookup"><span data-stu-id="494b3-153">Remarks</span></span>

<span data-ttu-id="494b3-154">La [instrucción end](end-statement.md), sin una palabra clave adicional, finaliza la ejecución inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="494b3-154">The [End Statement](end-statement.md), without an additional keyword, terminates execution immediately.</span></span>

## <a name="smart-device-developer-notes"></a><span data-ttu-id="494b3-155">Notas para desarrolladores de Smart Device</span><span class="sxs-lookup"><span data-stu-id="494b3-155">Smart Device Developer Notes</span></span>  

<span data-ttu-id="494b3-156">`End`No se admite la instrucción, sin una palabra clave adicional.</span><span class="sxs-lookup"><span data-stu-id="494b3-156">The `End` statement, without an additional keyword, is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="494b3-157">Vea también</span><span class="sxs-lookup"><span data-stu-id="494b3-157">See also</span></span>

- [<span data-ttu-id="494b3-158">End (instrucción)</span><span class="sxs-lookup"><span data-stu-id="494b3-158">End Statement</span></span>](end-statement.md)
