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
# <a name="end-keyword-statement-visual-basic"></a>End \<palabra clave > instrucción (Visual Basic)

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
  
## <a name="parts"></a>Elementos

|Parte|Descripción|
|---|---|
|`End`|Obligatorio. Finaliza la definición del elemento de programación.|
|`AddHandler`|Se requiere para terminar un descriptor de acceso `AddHandler` Iniciado por una instrucción `AddHandler` coincidente en una [instrucción de evento](event-statement.md)personalizada.|
|`Class`|Necesario para terminar una definición de clase que comienza por una [instrucción de clase](class-statement.md)coincidente.|
|`Enum`|Necesario para terminar una definición de enumeración iniciada por una [instrucción enum](enum-statement.md)coincidente.|
|`Event`|Necesario para terminar una definición de evento `Custom` iniciada por una [instrucción de evento](event-statement.md)coincidente.|  
|`Function`|Necesario para terminar una definición de procedimiento `Function` iniciada por una [instrucción de función](function-statement.md)coincidente. Si la ejecución encuentra una instrucción `End Function`, el control vuelve al código de llamada.|
|`Get`|Necesario para terminar una definición de procedimiento `Property` iniciada por una [instrucción Get](get-statement.md)coincidente. Si la ejecución encuentra una instrucción `End Get`, el control vuelve a la instrucción que solicita el valor de la propiedad.|
|`If`|Necesario para terminar una definición de bloque `If`...`Then`...`Else` iniciada por una instrucción de `If` coincidente. Vea [If... Después... Else (instrucción](if-then-else-statement.md)).|
|`Interface`|Necesario para terminar una definición de interfaz iniciada por una [instrucción de interfaz](interface-statement.md)coincidente.|
|`Module`|Necesario para terminar una definición de módulo iniciada por una [instrucción de módulo](module-statement.md)coincidente.|
|`Namespace`|Necesario para terminar una definición de espacio de nombres iniciada por una [instrucción de espacio de nombres](namespace-statement.md)coincidente.|
|`Operator`|Necesario para terminar una definición de operador iniciada por una [instrucción de operador](operator-statement.md)coincidente.|
|`Property`|Necesario para terminar una definición de propiedad iniciada por una [instrucción de propiedad](property-statement.md)coincidente.|
|`RaiseEvent`|Se requiere para terminar un descriptor de acceso `RaiseEvent` Iniciado por una instrucción `RaiseEvent` coincidente en una [instrucción de evento](event-statement.md)personalizada.|
|`RemoveHandler`|Se requiere para terminar un descriptor de acceso `RemoveHandler` Iniciado por una instrucción `RemoveHandler` coincidente en una [instrucción de evento](event-statement.md)personalizada.|
|`Select`|Necesario para terminar una definición de bloque `Select`...`Case` iniciada por una instrucción `Select` coincidente. Vea [Select... Instrucción Case](select-case-statement.md).  
|`Set`|Necesario para terminar una definición de procedimiento `Property` iniciada por una [instrucción set](set-statement.md)coincidente. Si la ejecución encuentra una instrucción `End Set`, el control vuelve a la instrucción que establece el valor de la propiedad.  
|`Structure`|Necesario para terminar una definición de estructura que comienza por una [instrucción de estructura](structure-statement.md)coincidente.  
|`Sub`|Necesario para terminar una definición de procedimiento `Sub` iniciada por una [instrucción Sub](sub-statement.md)coincidente. Si la ejecución encuentra una instrucción `End Sub`, el control vuelve al código de llamada.  
|`SyncLock`|Necesario para terminar una definición de bloque `SyncLock` iniciada por una instrucción `SyncLock` coincidente. Vea la [instrucción SyncLock](synclock-statement.md).  
|`Try`|Necesario para terminar una definición de bloque `Try`...`Catch`...`Finally` iniciada por una instrucción de `Try` coincidente. Vea [try... Detectar... Finally](try-catch-finally-statement.md).  
|`While`|Necesario para terminar una definición de bucle `While` iniciada por una instrucción `While` coincidente. Vea [while... End while (instrucción](while-end-while-statement.md)).  
|`With`| Necesario para terminar una definición de bloque `With` iniciada por una instrucción `With` coincidente. Vea [con... End with](with-end-with-statement.md).  
|||
  
## <a name="directives"></a>Directivas

Cuando va precedido de un signo de número (`#`), la palabra clave `End` finaliza un bloque de preprocesamiento introducido por la directiva correspondiente.  

```vb
#End ExternalSource
#End If
#End Region
```

|Parte|Descripción|
|---|---|
|`#End`|Obligatorio. Finaliza la definición del bloque de preprocesamiento.|
|`ExternalSource`|Obligatorio para finalizar un bloque de origen externo Iniciado por una [Directiva de #ExternalSource](../directives/externalsource-directive.md)coincidente.|
|`If`|Necesario para terminar un bloque de compilación condicional Iniciado por una directiva de `#If` coincidente. Vea [#If... Then... #Else directivas](../directives/if-then-else-directives.md).|
|`Region`|Obligatorio para terminar un bloque de región de origen Iniciado por una [Directiva de #Region](../directives/region-directive.md)coincidente.|
|||

## <a name="remarks"></a>Comentarios

La [instrucción end](end-statement.md), sin una palabra clave adicional, finaliza la ejecución inmediatamente.

## <a name="smart-device-developer-notes"></a>Notas para desarrolladores de Smart Device  

No se admite la instrucción `End`, sin una palabra clave adicional.  
  
## <a name="see-also"></a>Vea también

- [End (instrucción)](end-statement.md)
