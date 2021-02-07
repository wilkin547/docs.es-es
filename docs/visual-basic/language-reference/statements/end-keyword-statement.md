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
# <a name="end-keyword-statement-visual-basic"></a>End \<keyword> (Instrucción, Visual Basic)

Cuando va seguido de una palabra clave adicional, finaliza la definición del bloque de instrucciones introducido por esa palabra clave.

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
  
## <a name="parts"></a>Partes

|Parte|Descripción|
|---|---|
|`End`|Necesario. Finaliza la definición del elemento de programación.|
|`AddHandler`|Obligatorio para finalizar un `AddHandler` descriptor de acceso Iniciado por una `AddHandler` instrucción coincidente en una [instrucción de evento](event-statement.md)personalizada.|
|`Class`|Necesario para terminar una definición de clase que comienza por una [instrucción de clase](class-statement.md)coincidente.|
|`Enum`|Necesario para terminar una definición de enumeración iniciada por una [instrucción enum](enum-statement.md)coincidente.|
|`Event`|Necesario para terminar una `Custom` definición de evento iniciada por una [instrucción de evento](event-statement.md)coincidente.|  
|`Function`|Necesario para terminar una `Function` definición de procedimiento iniciada por una [instrucción de función](function-statement.md)coincidente. Si la ejecución encuentra una `End Function` instrucción, el control vuelve al código de llamada.|
|`Get`|Necesario para terminar una `Property` definición de procedimiento iniciada por una [instrucción Get](get-statement.md)coincidente. Si la ejecución encuentra una `End Get` instrucción, el control vuelve a la instrucción que solicita el valor de la propiedad.|
|`If`|Requerido para terminar una `If` ... `Then` ...`Else` definición de bloque iniciada por una `If` instrucción coincidente. Vea [If... Después... Else (instrucción](if-then-else-statement.md)).|
|`Interface`|Necesario para terminar una definición de interfaz iniciada por una [instrucción de interfaz](interface-statement.md)coincidente.|
|`Module`|Necesario para terminar una definición de módulo iniciada por una [instrucción de módulo](module-statement.md)coincidente.|
|`Namespace`|Necesario para terminar una definición de espacio de nombres iniciada por una [instrucción de espacio de nombres](namespace-statement.md)coincidente.|
|`Operator`|Necesario para terminar una definición de operador iniciada por una [instrucción de operador](operator-statement.md)coincidente.|
|`Property`|Necesario para terminar una definición de propiedad iniciada por una [instrucción de propiedad](property-statement.md)coincidente.|
|`RaiseEvent`|Necesario para terminar un `RaiseEvent` descriptor de acceso Iniciado por una `RaiseEvent` instrucción coincidente en una [instrucción de evento](event-statement.md)personalizada.|
|`RemoveHandler`|Necesario para terminar un `RemoveHandler` descriptor de acceso Iniciado por una `RemoveHandler` instrucción coincidente en una [instrucción de evento](event-statement.md)personalizada.|
|`Select`|Necesario para terminar una `Select` definición de bloque... que `Case` comienza por una `Select` instrucción coincidente. Vea [Select... Instrucción Case](select-case-statement.md).  
|`Set`|Necesario para terminar una `Property` definición de procedimiento que comienza por una [instrucción set](set-statement.md)coincidente. Si la ejecución encuentra una `End Set` instrucción, el control vuelve a la instrucción que establece el valor de la propiedad.  
|`Structure`|Necesario para terminar una definición de estructura que comienza por una [instrucción de estructura](structure-statement.md)coincidente.  
|`Sub`|Necesario para terminar una `Sub` definición de procedimiento que comienza por una [instrucción Sub](sub-statement.md)coincidente. Si la ejecución encuentra una `End Sub` instrucción, el control vuelve al código de llamada.  
|`SyncLock`|Necesario para terminar una `SyncLock` definición de bloque iniciada por una `SyncLock` instrucción coincidente. Vea la [instrucción SyncLock](synclock-statement.md).  
|`Try`|Requerido para terminar una `Try` ... `Catch` ...`Finally` definición de bloque iniciada por una `Try` instrucción coincidente. Vea [try... Detectar... Finally](try-catch-finally-statement.md).  
|`While`|Necesario para terminar una `While` definición de bucle iniciada por una `While` instrucción coincidente. Vea [while... End while (instrucción](while-end-while-statement.md)).  
|`With`| Necesario para terminar una `With` definición de bloque iniciada por una `With` instrucción coincidente. Vea [con... End with](with-end-with-statement.md).  
|||
  
## <a name="directives"></a>Directivas

Cuando va precedido de un signo de número ( `#` ), la `End` palabra clave finaliza un bloque de preprocesamiento introducido por la directiva correspondiente.  

```vb
#End ExternalSource
#End If
#End Region
```

|Parte|Descripción|
|---|---|
|`#End`|Necesario. Finaliza la definición del bloque de preprocesamiento.|
|`ExternalSource`|Obligatorio para finalizar un bloque de origen externo Iniciado por una [Directiva de #ExternalSource](../directives/externalsource-directive.md)coincidente.|
|`If`|Necesario para terminar un bloque de compilación condicional Iniciado por una `#If` Directiva coincidente. Vea [#If... Then... #Else directivas](../directives/if-then-else-directives.md).|
|`Region`|Obligatorio para terminar un bloque de región de origen Iniciado por una [Directiva de #Region](../directives/region-directive.md)coincidente.|
|||

## <a name="remarks"></a>Observaciones

La [instrucción end](end-statement.md), sin una palabra clave adicional, finaliza la ejecución inmediatamente.

## <a name="smart-device-developer-notes"></a>Notas para desarrolladores de Smart Device  

`End`No se admite la instrucción, sin una palabra clave adicional.  
  
## <a name="see-also"></a>Vea también

- [End (instrucción)](end-statement.md)
