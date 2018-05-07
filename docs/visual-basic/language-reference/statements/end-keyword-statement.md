---
title: End &lt;palabra clave&gt; (instrucción, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.EndDefinition
helpviewer_keywords:
- End keyword [Visual Basic]
ms.assetid: 42d6e088-ab0f-4cda-88e8-fdce3e5fcf4f
ms.openlocfilehash: 8137434bfd8c26144d78b1761b784cdba4894eaf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="end-ltkeywordgt-statement-visual-basic"></a>End &lt;palabra clave&gt; (instrucción, Visual Basic)
Cuando va seguido de una palabra clave adicional, termina la definición del bloque de instrucciones introducida por esa palabra clave.  
  
## <a name="syntax"></a>Sintaxis  
  
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
  
## <a name="parts"></a>Elementos  
 `End`  
 Requerido. Termina la definición del elemento de programación.  
  
 `AddHandler`  
 Es obligatorio para terminar una `AddHandler` descriptor de acceso comenzada por una búsqueda de coincidencias `AddHandler` instrucción en un personalizado [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md).  
  
 `Class`  
 Es obligatorio para terminar una definición de clase comenzada por una búsqueda de coincidencias [Class (instrucción)](../../../visual-basic/language-reference/statements/class-statement.md).  
  
 `Enum`  
 Es obligatorio para terminar una definición de enumeración que comienza por una coincidencia [Enum (instrucción)](../../../visual-basic/language-reference/statements/enum-statement.md).  
  
 `Event`  
 Es obligatorio para terminar una `Custom` definición de evento comenzada por una búsqueda de coincidencias [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md).  
  
 `Function`  
 Es obligatorio para terminar una `Function` comenzada por una coincidencia de la definición del procedimiento [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md). Si la ejecución encuentra una `End``Function` instrucción, el control vuelve al código de llamada.  
  
 `Get`  
 Es obligatorio para terminar una `Property` comenzada por una coincidencia de la definición del procedimiento [instrucción Get](../../../visual-basic/language-reference/statements/get-statement.md). Si la ejecución encuentra una `End``Get` instrucción, el control vuelve a la instrucción que solicita el valor de la propiedad.  
  
 `If`  
 Es obligatorio para terminar una `If`... `Then`... `Else` definición comenzada por una coincidencia del bloque `If` instrucción. Consulte [si... Then... Else (instrucción)](../../../visual-basic/language-reference/statements/if-then-else-statement.md).  
  
 `Interface`  
 Es obligatorio para terminar una definición de interfaz que comienza por una coincidencia [Interface (instrucción)](../../../visual-basic/language-reference/statements/interface-statement.md).  
  
 `Module`  
 Es obligatorio para terminar una definición de módulo comenzada por una búsqueda de coincidencias [Module (instrucción)](../../../visual-basic/language-reference/statements/module-statement.md).  
  
 `Namespace`  
 Es obligatorio para terminar una definición de espacio de nombres que comienza por una búsqueda de coincidencias [instrucción Namespace](../../../visual-basic/language-reference/statements/namespace-statement.md).  
  
 `Operator`  
 Es obligatorio para terminar una definición de operador que comienza por una búsqueda de coincidencias [Operator (instrucción)](../../../visual-basic/language-reference/statements/operator-statement.md).  
  
 `Property`  
 Es obligatorio para terminar una definición de propiedad que comienza por una coincidencia [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md).  
  
 `RaiseEvent`  
 Es obligatorio para terminar una `RaiseEvent` descriptor de acceso comenzada por una búsqueda de coincidencias `RaiseEvent` instrucción en un personalizado [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md).  
  
 `RemoveHandler`  
 Es obligatorio para terminar una `RemoveHandler` descriptor de acceso comenzada por una búsqueda de coincidencias `RemoveHandler` instrucción en un personalizado [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md).  
  
 `Select`  
 Es obligatorio para terminar una `Select`... `Case` definición comenzada por una coincidencia del bloque `Select` instrucción. Vea [seleccione... Caso instrucción](../../../visual-basic/language-reference/statements/select-case-statement.md).  
  
 `Set`  
 Es obligatorio para terminar una `Property` comenzada por una coincidencia de la definición del procedimiento [instrucción Set](../../../visual-basic/language-reference/statements/set-statement.md). Si la ejecución encuentra una `End``Set` instrucción, el control vuelve a la instrucción que establece el valor de la propiedad.  
  
 `Structure`  
 Es obligatorio para terminar una definición de estructura que comienza por una búsqueda de coincidencias [Structure (instrucción)](../../../visual-basic/language-reference/statements/structure-statement.md).  
  
 `Sub`  
 Es obligatorio para terminar una `Sub` comenzada por una coincidencia de la definición del procedimiento [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md). Si la ejecución encuentra una `End``Sub` instrucción, el control vuelve al código de llamada.  
  
 `SyncLock`  
 Es obligatorio para terminar una `SyncLock` definición comenzada por una coincidencia del bloque `SyncLock` instrucción. Vea [SyncLock (instrucción)](../../../visual-basic/language-reference/statements/synclock-statement.md).  
  
 `Try`  
 Es obligatorio para terminar una `Try`... `Catch`... `Finally` definición comenzada por una coincidencia del bloque `Try` instrucción. Vea [intente... Catch... Finally (instrucción)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
 `While`  
 Es obligatorio para terminar una `While` definición que comienza por una coincidencia de un bucle `While` instrucción. Vea [mientras... End While (instrucción)](../../../visual-basic/language-reference/statements/while-end-while-statement.md).  
  
 `With`  
 Es obligatorio para terminar una `With` definición comenzada por una coincidencia del bloque `With` instrucción. Consulte [con... Terminar con la instrucción](../../../visual-basic/language-reference/statements/with-end-with-statement.md).  
  
## <a name="remarks"></a>Comentarios  
 El [End (instrucción)](../../../visual-basic/language-reference/statements/end-statement.md), sin una palabra clave adicional, termina la ejecución inmediatamente.  
  
 Cuando está precedido por un signo de número (`#`), el `End` palabra clave finaliza un bloque de preprocesamiento introducido por la directiva correspondiente.  
  
 `#End`  
 Requerido. Termina la definición del bloque de preprocesamiento.  
  
 `#ExternalSource`  
 Es obligatorio para terminar un bloque de origen externo que comienza por una búsqueda de coincidencias [#ExternalSource (directiva)](../../../visual-basic/language-reference/directives/externalsource-directive.md).  
  
 `#If`  
 Es obligatorio para terminar un bloque de compilación condicional que comienza por una búsqueda de coincidencias `#If` directiva. Vea [#If... Then... #Else directivas](../../../visual-basic/language-reference/directives/if-then-else-directives.md).  
  
 `#Region`  
 Es obligatorio para terminar un bloque de regiones de origen que comienza por una búsqueda de coincidencias [#Region (directiva)](../../../visual-basic/language-reference/directives/region-directive.md).  
  
## <a name="smart-device-developer-notes"></a>Notas de desarrollador de Smart Device  
 El `End` instrucción sin una palabra clave adicional, no se admite.  
  
## <a name="see-also"></a>Vea también  
 [End (instrucción)](../../../visual-basic/language-reference/statements/end-statement.md)
