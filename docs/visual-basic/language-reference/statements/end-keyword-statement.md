---
title: End <keyword> (Instrucción, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.EndDefinition
helpviewer_keywords:
- End keyword [Visual Basic]
ms.assetid: 42d6e088-ab0f-4cda-88e8-fdce3e5fcf4f
ms.openlocfilehash: 96dc8ce6b0d3b7545f5caeef43358936e426f566
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638160"
---
# <a name="end-keyword-statement-visual-basic"></a>End \<palabra clave > (instrucción, Visual Basic)

Cuando va seguido de una palabra clave adicional, termina la definición del bloque de instrucción introducido por esa palabra clave.

## <a name="syntax"></a>Sintaxis

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
  
## <a name="parts"></a>Elementos

|Parte|Descripción|
|---|---|
|`End`|Obligatorio. Termina la definición del elemento de programación.|
|`AddHandler`|Es obligatorio para terminar una `AddHandler` comenzada por un descriptor de acceso `AddHandler` instrucción personalizada [Event (instrucción)](event-statement.md).|
|`Class`|Es obligatorio para terminar una definición de clase comenzada por un [Class (instrucción)](class-statement.md).|
|`Enum`|Es obligatorio para terminar una definición de enumeración que comienza por una coincidencia [Enum (instrucción)](enum-statement.md).|
|`Event`|Es obligatorio para terminar una `Custom` definición de evento comenzada por un [Event (instrucción)](event-statement.md).|  
|`Function`|Es obligatorio para terminar una `Function` definición del procedimiento comenzada por un [instrucción Function](function-statement.md). Si la ejecución se encuentra una `End Function` instrucción, el control vuelve al código de llamada.|
|`Get`|Es obligatorio para terminar una `Property` definición del procedimiento comenzada por un [Get Statement](get-statement.md). Si la ejecución se encuentra una `End Get` instrucción, el control vuelve a la instrucción que solicita el valor de propiedad.|
|`If`|Es obligatorio para terminar una `If`... `Then`... `Else` bloquear definición comenzada por una coincidencia `If` instrucción. Consulte [si... Entonces... Else (instrucción)](if-then-else-statement.md).|
|`Interface`|Es obligatorio para terminar una definición de interfaz que comienza por un [Interface (instrucción)](interface-statement.md).|
|`Module`|Es obligatorio para terminar una definición de módulo comenzada por una coincidencia [Module (instrucción)](module-statement.md).|
|`Namespace`|Es obligatorio para terminar una definición de espacio de nombres que comienza por una coincidencia [instrucción Namespace](namespace-statement.md).|
|`Operator`|Es obligatorio para terminar una definición de operador comenzada por un [Operator (instrucción)](operator-statement.md).|
|`Property`|Es obligatorio para terminar una definición de propiedad comenzada por un [Property Statement](property-statement.md).|
|`RaiseEvent`|Es obligatorio para terminar una `RaiseEvent` comenzada por un descriptor de acceso `RaiseEvent` instrucción personalizada [Event (instrucción)](event-statement.md).|
|`RemoveHandler`|Es obligatorio para terminar una `RemoveHandler` comenzada por un descriptor de acceso `RemoveHandler` instrucción personalizada [Event (instrucción)](event-statement.md).|
|`Select`|Es obligatorio para terminar una `Select`... `Case` bloquear definición comenzada por una coincidencia `Select` instrucción. Consulte [seleccione... Instrucción de caso](select-case-statement.md).  
|`Set`|Es obligatorio para terminar una `Property` definición del procedimiento comenzada por un [instrucción Set](set-statement.md). Si la ejecución se encuentra una `End Set` instrucción, el control vuelve a la instrucción que establece el valor de propiedad.  
|`Structure`|Es obligatorio para terminar una definición de estructura que comienza por una coincidencia [Structure (instrucción)](structure-statement.md).  
|`Sub`|Es obligatorio para terminar una `Sub` definición del procedimiento comenzada por un [Sub (instrucción)](sub-statement.md). Si la ejecución se encuentra una `End Sub` instrucción, el control vuelve al código de llamada.  
|`SyncLock`|Es obligatorio para terminar una `SyncLock` bloquear definición comenzada por una coincidencia `SyncLock` instrucción. Consulte [instrucción SyncLock](synclock-statement.md).  
|`Try`|Es obligatorio para terminar una `Try`... `Catch`... `Finally` bloquear definición comenzada por una coincidencia `Try` instrucción. Consulte [intente... Catch... Finally (instrucción)](try-catch-finally-statement.md).  
|`While`|Es obligatorio para terminar una `While` definición comenzada por una coincidencia de bucle `While` instrucción. Consulte [mientras... End While (instrucción)](while-end-while-statement.md).  
|`With`| Es obligatorio para terminar una `With` bloquear definición comenzada por una coincidencia `With` instrucción. Consulte [con... Terminar con la instrucción](with-end-with-statement.md).  
|||
  
## <a name="directives"></a>Directivas

Cuando está precedido por un signo de número (`#`), el `End` palabra clave finaliza un bloque de preprocesamiento introducido por la directiva correspondiente.  

```vb
#End ExternalSource
#End If
#End Region
```

|Parte|Descripción|
|---|---|
|`#End`|Obligatorio. Termina la definición del bloque de preprocesamiento.|
|`ExternalSource`|Es obligatorio para terminar un bloque de origen externo que comienza por un [#ExternalSource (directiva)](../directives/externalsource-directive.md).|
|`If`|Es obligatorio para terminar un bloque de compilación condicional comenzado por una coincidencia `#If` directiva. Consulte [#If... Then... #Else directivas](../directives/if-then-else-directives.md).|
|`Region`|Es obligatorio para terminar un bloque de regiones de origen que comienza por un [#Region (directiva)](../directives/region-directive.md).|
|||

## <a name="remarks"></a>Comentarios

El [instrucción End](end-statement.md), sin una palabra clave adicional, termina la ejecución inmediatamente.

## <a name="smart-device-developer-notes"></a>Notas de desarrollador de dispositivos inteligentes  

El `End` instrucción sin una palabra clave adicional, no se admite.  
  
## <a name="see-also"></a>Vea también

- [End (instrucción)](end-statement.md)
