---
title: Instrucción End <keyword>
ms.date: 07/20/2015
f1_keywords:
- vb.EndDefinition
helpviewer_keywords:
- End keyword [Visual Basic]
ms.assetid: 42d6e088-ab0f-4cda-88e8-fdce3e5fcf4f
ms.openlocfilehash: 87f4724cc036e6e0bdf0b558854a4034f45b9ab5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343736"
---
# <a name="end-keyword-statement-visual-basic"></a><span data-ttu-id="35ca1-102">End \<palabra clave > instrucción (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="35ca1-102">End \<keyword> Statement (Visual Basic)</span></span>

<span data-ttu-id="35ca1-103">Cuando va seguido de una palabra clave adicional, finaliza la definición del bloque de instrucciones introducido por esa palabra clave.</span><span class="sxs-lookup"><span data-stu-id="35ca1-103">When followed by an additional keyword, terminates the definition of the statement block introduced by that keyword.</span></span>

## <a name="syntax"></a><span data-ttu-id="35ca1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="35ca1-104">Syntax</span></span>

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
  
## <a name="parts"></a><span data-ttu-id="35ca1-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="35ca1-105">Parts</span></span>

|<span data-ttu-id="35ca1-106">Parte</span><span class="sxs-lookup"><span data-stu-id="35ca1-106">Part</span></span>|<span data-ttu-id="35ca1-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="35ca1-107">Description</span></span>|
|---|---|
|`End`|<span data-ttu-id="35ca1-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="35ca1-108">Required.</span></span> <span data-ttu-id="35ca1-109">Finaliza la definición del elemento de programación.</span><span class="sxs-lookup"><span data-stu-id="35ca1-109">Terminates the definition of the programming element.</span></span>|
|`AddHandler`|<span data-ttu-id="35ca1-110">Se requiere para terminar un descriptor de acceso `AddHandler` Iniciado por una instrucción `AddHandler` coincidente en una [instrucción de evento](event-statement.md)personalizada.</span><span class="sxs-lookup"><span data-stu-id="35ca1-110">Required to terminate an `AddHandler` accessor begun by a matching `AddHandler` statement in a custom [Event Statement](event-statement.md).</span></span>|
|`Class`|<span data-ttu-id="35ca1-111">Necesario para terminar una definición de clase que comienza por una [instrucción de clase](class-statement.md)coincidente.</span><span class="sxs-lookup"><span data-stu-id="35ca1-111">Required to terminate a class definition begun by a matching [Class Statement](class-statement.md).</span></span>|
|`Enum`|<span data-ttu-id="35ca1-112">Necesario para terminar una definición de enumeración iniciada por una [instrucción enum](enum-statement.md)coincidente.</span><span class="sxs-lookup"><span data-stu-id="35ca1-112">Required to terminate an enumeration definition begun by a matching [Enum Statement](enum-statement.md).</span></span>|
|`Event`|<span data-ttu-id="35ca1-113">Necesario para terminar una definición de evento `Custom` iniciada por una [instrucción de evento](event-statement.md)coincidente.</span><span class="sxs-lookup"><span data-stu-id="35ca1-113">Required to terminate a `Custom` event definition begun by a matching [Event Statement](event-statement.md).</span></span>|  
|`Function`|<span data-ttu-id="35ca1-114">Necesario para terminar una definición de procedimiento `Function` iniciada por una [instrucción de función](function-statement.md)coincidente.</span><span class="sxs-lookup"><span data-stu-id="35ca1-114">Required to terminate a `Function` procedure definition begun by a matching [Function Statement](function-statement.md).</span></span> <span data-ttu-id="35ca1-115">Si la ejecución encuentra una instrucción `End Function`, el control vuelve al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="35ca1-115">If execution encounters an `End Function` statement, control returns to the calling code.</span></span>|
|`Get`|<span data-ttu-id="35ca1-116">Necesario para terminar una definición de procedimiento `Property` iniciada por una [instrucción Get](get-statement.md)coincidente.</span><span class="sxs-lookup"><span data-stu-id="35ca1-116">Required to terminate a `Property` procedure definition begun by a matching [Get Statement](get-statement.md).</span></span> <span data-ttu-id="35ca1-117">Si la ejecución encuentra una instrucción `End Get`, el control vuelve a la instrucción que solicita el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="35ca1-117">If execution encounters an `End Get` statement, control returns to the statement requesting the property's value.</span></span>|
|`If`|<span data-ttu-id="35ca1-118">Necesario para terminar una definición de bloque `If`...`Then`...`Else` iniciada por una instrucción de `If` coincidente.</span><span class="sxs-lookup"><span data-stu-id="35ca1-118">Required to terminate an `If`...`Then`...`Else` block definition begun by a matching `If` statement.</span></span> <span data-ttu-id="35ca1-119">Vea [If... Después... Else (instrucción](if-then-else-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="35ca1-119">See [If...Then...Else Statement](if-then-else-statement.md).</span></span>|
|`Interface`|<span data-ttu-id="35ca1-120">Necesario para terminar una definición de interfaz iniciada por una [instrucción de interfaz](interface-statement.md)coincidente.</span><span class="sxs-lookup"><span data-stu-id="35ca1-120">Required to terminate an interface definition begun by a matching [Interface Statement](interface-statement.md).</span></span>|
|`Module`|<span data-ttu-id="35ca1-121">Necesario para terminar una definición de módulo iniciada por una [instrucción de módulo](module-statement.md)coincidente.</span><span class="sxs-lookup"><span data-stu-id="35ca1-121">Required to terminate a module definition begun by a matching [Module Statement](module-statement.md).</span></span>|
|`Namespace`|<span data-ttu-id="35ca1-122">Necesario para terminar una definición de espacio de nombres iniciada por una [instrucción de espacio de nombres](namespace-statement.md)coincidente.</span><span class="sxs-lookup"><span data-stu-id="35ca1-122">Required to terminate a namespace definition begun by a matching [Namespace Statement](namespace-statement.md).</span></span>|
|`Operator`|<span data-ttu-id="35ca1-123">Necesario para terminar una definición de operador iniciada por una [instrucción de operador](operator-statement.md)coincidente.</span><span class="sxs-lookup"><span data-stu-id="35ca1-123">Required to terminate an operator definition begun by a matching [Operator Statement](operator-statement.md).</span></span>|
|`Property`|<span data-ttu-id="35ca1-124">Necesario para terminar una definición de propiedad iniciada por una [instrucción de propiedad](property-statement.md)coincidente.</span><span class="sxs-lookup"><span data-stu-id="35ca1-124">Required to terminate a property definition begun by a matching [Property Statement](property-statement.md).</span></span>|
|`RaiseEvent`|<span data-ttu-id="35ca1-125">Se requiere para terminar un descriptor de acceso `RaiseEvent` Iniciado por una instrucción `RaiseEvent` coincidente en una [instrucción de evento](event-statement.md)personalizada.</span><span class="sxs-lookup"><span data-stu-id="35ca1-125">Required to terminate a `RaiseEvent` accessor begun by a matching `RaiseEvent` statement in a custom [Event Statement](event-statement.md).</span></span>|
|`RemoveHandler`|<span data-ttu-id="35ca1-126">Se requiere para terminar un descriptor de acceso `RemoveHandler` Iniciado por una instrucción `RemoveHandler` coincidente en una [instrucción de evento](event-statement.md)personalizada.</span><span class="sxs-lookup"><span data-stu-id="35ca1-126">Required to terminate a `RemoveHandler` accessor begun by a matching `RemoveHandler` statement in a custom [Event Statement](event-statement.md).</span></span>|
|`Select`|<span data-ttu-id="35ca1-127">Necesario para terminar una definición de bloque `Select`...`Case` iniciada por una instrucción `Select` coincidente.</span><span class="sxs-lookup"><span data-stu-id="35ca1-127">Required to terminate a `Select`...`Case` block definition begun by a matching `Select` statement.</span></span> <span data-ttu-id="35ca1-128">Vea [Select... Instrucción Case](select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="35ca1-128">See [Select...Case Statement](select-case-statement.md).</span></span>  
|`Set`|<span data-ttu-id="35ca1-129">Necesario para terminar una definición de procedimiento `Property` iniciada por una [instrucción set](set-statement.md)coincidente.</span><span class="sxs-lookup"><span data-stu-id="35ca1-129">Required to terminate a `Property` procedure definition begun by a matching [Set Statement](set-statement.md).</span></span> <span data-ttu-id="35ca1-130">Si la ejecución encuentra una instrucción `End Set`, el control vuelve a la instrucción que establece el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="35ca1-130">If execution encounters an `End Set` statement, control returns to the statement setting the property's value.</span></span>  
|`Structure`|<span data-ttu-id="35ca1-131">Necesario para terminar una definición de estructura que comienza por una [instrucción de estructura](structure-statement.md)coincidente.</span><span class="sxs-lookup"><span data-stu-id="35ca1-131">Required to terminate a structure definition begun by a matching [Structure Statement](structure-statement.md).</span></span>  
|`Sub`|<span data-ttu-id="35ca1-132">Necesario para terminar una definición de procedimiento `Sub` iniciada por una [instrucción Sub](sub-statement.md)coincidente.</span><span class="sxs-lookup"><span data-stu-id="35ca1-132">Required to terminate a `Sub` procedure definition begun by a matching [Sub Statement](sub-statement.md).</span></span> <span data-ttu-id="35ca1-133">Si la ejecución encuentra una instrucción `End Sub`, el control vuelve al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="35ca1-133">If execution encounters an `End Sub` statement, control returns to the calling code.</span></span>  
|`SyncLock`|<span data-ttu-id="35ca1-134">Necesario para terminar una definición de bloque `SyncLock` iniciada por una instrucción `SyncLock` coincidente.</span><span class="sxs-lookup"><span data-stu-id="35ca1-134">Required to terminate a `SyncLock` block definition begun by a matching `SyncLock` statement.</span></span> <span data-ttu-id="35ca1-135">Vea la [instrucción SyncLock](synclock-statement.md).</span><span class="sxs-lookup"><span data-stu-id="35ca1-135">See [SyncLock Statement](synclock-statement.md).</span></span>  
|`Try`|<span data-ttu-id="35ca1-136">Necesario para terminar una definición de bloque `Try`...`Catch`...`Finally` iniciada por una instrucción de `Try` coincidente.</span><span class="sxs-lookup"><span data-stu-id="35ca1-136">Required to terminate a `Try`...`Catch`...`Finally` block definition begun by a matching `Try` statement.</span></span> <span data-ttu-id="35ca1-137">Vea [try... Detectar... Finally](try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="35ca1-137">See [Try...Catch...Finally Statement](try-catch-finally-statement.md).</span></span>  
|`While`|<span data-ttu-id="35ca1-138">Necesario para terminar una definición de bucle `While` iniciada por una instrucción `While` coincidente.</span><span class="sxs-lookup"><span data-stu-id="35ca1-138">Required to terminate a `While` loop definition begun by a matching `While` statement.</span></span> <span data-ttu-id="35ca1-139">Vea [while... End while (instrucción](while-end-while-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="35ca1-139">See [While...End While Statement](while-end-while-statement.md).</span></span>  
|`With`| <span data-ttu-id="35ca1-140">Necesario para terminar una definición de bloque `With` iniciada por una instrucción `With` coincidente.</span><span class="sxs-lookup"><span data-stu-id="35ca1-140">Required to terminate a `With` block definition begun by a matching `With` statement.</span></span> <span data-ttu-id="35ca1-141">Vea [con... End with](with-end-with-statement.md).</span><span class="sxs-lookup"><span data-stu-id="35ca1-141">See [With...End With Statement](with-end-with-statement.md).</span></span>  
|||
  
## <a name="directives"></a><span data-ttu-id="35ca1-142">Directivas</span><span class="sxs-lookup"><span data-stu-id="35ca1-142">Directives</span></span>

<span data-ttu-id="35ca1-143">Cuando va precedido de un signo de número (`#`), la palabra clave `End` finaliza un bloque de preprocesamiento introducido por la directiva correspondiente.</span><span class="sxs-lookup"><span data-stu-id="35ca1-143">When preceded by a number sign (`#`), the `End` keyword terminates a preprocessing block introduced by the corresponding directive.</span></span>  

```vb
#End ExternalSource
#End If
#End Region
```

|<span data-ttu-id="35ca1-144">Parte</span><span class="sxs-lookup"><span data-stu-id="35ca1-144">Part</span></span>|<span data-ttu-id="35ca1-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="35ca1-145">Description</span></span>|
|---|---|
|`#End`|<span data-ttu-id="35ca1-146">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="35ca1-146">Required.</span></span> <span data-ttu-id="35ca1-147">Finaliza la definición del bloque de preprocesamiento.</span><span class="sxs-lookup"><span data-stu-id="35ca1-147">Terminates the definition of the preprocessing block.</span></span>|
|`ExternalSource`|<span data-ttu-id="35ca1-148">Obligatorio para finalizar un bloque de origen externo Iniciado por una [Directiva de #ExternalSource](../directives/externalsource-directive.md)coincidente.</span><span class="sxs-lookup"><span data-stu-id="35ca1-148">Required to terminate an external source block begun by a matching [#ExternalSource Directive](../directives/externalsource-directive.md).</span></span>|
|`If`|<span data-ttu-id="35ca1-149">Necesario para terminar un bloque de compilación condicional Iniciado por una directiva de `#If` coincidente.</span><span class="sxs-lookup"><span data-stu-id="35ca1-149">Required to terminate a conditional compilation block begun by a matching `#If` directive.</span></span> <span data-ttu-id="35ca1-150">Vea [#If... Then... #Else directivas](../directives/if-then-else-directives.md).</span><span class="sxs-lookup"><span data-stu-id="35ca1-150">See [#If...Then...#Else Directives](../directives/if-then-else-directives.md).</span></span>|
|`Region`|<span data-ttu-id="35ca1-151">Obligatorio para terminar un bloque de región de origen Iniciado por una [Directiva de #Region](../directives/region-directive.md)coincidente.</span><span class="sxs-lookup"><span data-stu-id="35ca1-151">Required to terminate a source region block begun by a matching [#Region Directive](../directives/region-directive.md).</span></span>|
|||

## <a name="remarks"></a><span data-ttu-id="35ca1-152">Comentarios</span><span class="sxs-lookup"><span data-stu-id="35ca1-152">Remarks</span></span>

<span data-ttu-id="35ca1-153">La [instrucción end](end-statement.md), sin una palabra clave adicional, finaliza la ejecución inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="35ca1-153">The [End Statement](end-statement.md), without an additional keyword, terminates execution immediately.</span></span>

## <a name="smart-device-developer-notes"></a><span data-ttu-id="35ca1-154">Notas para desarrolladores de Smart Device</span><span class="sxs-lookup"><span data-stu-id="35ca1-154">Smart Device Developer Notes</span></span>  

<span data-ttu-id="35ca1-155">No se admite la instrucción `End`, sin una palabra clave adicional.</span><span class="sxs-lookup"><span data-stu-id="35ca1-155">The `End` statement, without an additional keyword, is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35ca1-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="35ca1-156">See also</span></span>

- [<span data-ttu-id="35ca1-157">End (instrucción)</span><span class="sxs-lookup"><span data-stu-id="35ca1-157">End Statement</span></span>](end-statement.md)
