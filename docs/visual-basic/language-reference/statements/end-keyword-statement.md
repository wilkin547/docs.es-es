---
title: "End &lt;palabra clave&gt; (Instrucci&#243;n, Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.EndDefinition"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "End (palabra clave)"
ms.assetid: 42d6e088-ab0f-4cda-88e8-fdce3e5fcf4f
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# End &lt;palabra clave&gt; (Instrucci&#243;n, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Cuando está seguido de una palabra clave adicional, finaliza la definición del bloque de instrucciones introducida por esa palabra clave.  
  
## Sintaxis  
  
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
  
## Elementos  
 `End`  
 Obligatorio.  Finaliza la definición del elemento de programación.  
  
 `AddHandler`  
 Es obligatorio para finalizar un descriptor de acceso `AddHandler` que comienza por una instrucción `AddHandler` correspondiente en un [Event \(Instrucción\)](../../../visual-basic/language-reference/statements/event-statement.md) personalizado.  
  
 `Class`  
 Es obligatorio para terminar una definición de clase que comienza por una [Class \(Instrucción\)](../../../visual-basic/language-reference/statements/class-statement.md) correspondiente.  
  
 `Enum`  
 Es obligatorio para terminar una definición de enumeración que comienza por una [Enum \(Instrucción\)](../../../visual-basic/language-reference/statements/enum-statement.md) correspondiente.  
  
 `Event`  
 Es obligatorio para terminar una definición de evento `Custom` que comienza por un [Event \(Instrucción\)](../../../visual-basic/language-reference/statements/event-statement.md) correspondiente.  
  
 `Function`  
 Es obligatorio para terminar una definición de procedimiento `Function` que comienza por una [Function \(Instrucción\)](../../../visual-basic/language-reference/statements/function-statement.md) correspondiente.  Si en la ejecución se encuentra una instrucción `End` `Function`, el control vuelve al código de llamada.  
  
 `Get`  
 Es obligatorio para terminar una definición de procedimiento `Property` que comienza por un [Get \(Instrucción\)](../../../visual-basic/language-reference/statements/get-statement.md) correspondiente.  Si en la ejecución se encuentra una instrucción `End` `Get`, el control vuelve a la instrucción que solicita el valor de la propiedad.  
  
 `If`  
 Es obligatorio para terminar una definición de bloque `If`...`Then`...`Else` que comienza por una instrucción `If` correspondiente.  Vea [If...Then...Else \(Instrucción\)](../../../visual-basic/language-reference/statements/if-then-else-statement.md).  
  
 `Interface`  
 Es obligatorio para terminar una definición de interfaz que comienza por una [Interface \(Instrucción\)](../../../visual-basic/language-reference/statements/interface-statement.md) correspondiente.  
  
 `Module`  
 Es obligatorio para terminar una definición de módulo que comienza por un [Module \(Instrucción\)](../../../visual-basic/language-reference/statements/module-statement.md) correspondiente.  
  
 `Namespace`  
 Es obligatorio para terminar una definición de espacio de nombres que comienza por un [Namespace \(Instrucción\)](../../../visual-basic/language-reference/statements/namespace-statement.md) correspondiente.  
  
 `Operator`  
 Es obligatorio para terminar una definición de operador que comienza por una [Operator \(Instrucción\)](../../../visual-basic/language-reference/statements/operator-statement.md) correspondiente.  
  
 `Property`  
 Es obligatorio para terminar una definición de propiedad que comienza por una [Property \(Instrucción\)](../../../visual-basic/language-reference/statements/property-statement.md) correspondiente.  
  
 `RaiseEvent`  
 Es obligatorio para finalizar un descriptor de acceso `RaiseEvent` que comienza por una instrucción `RaiseEvent` correspondiente en un [Event \(Instrucción\)](../../../visual-basic/language-reference/statements/event-statement.md) personalizado.  
  
 `RemoveHandler`  
 Es obligatorio para finalizar un descriptor de acceso `RemoveHandler` que comienza por una instrucción `RemoveHandler` correspondiente en un [Event \(Instrucción\)](../../../visual-basic/language-reference/statements/event-statement.md) personalizado.  
  
 `Select`  
 Es obligatorio para terminar una definición de bloque `Select`...`Case` que comienza por una instrucción `Select` correspondiente.  Vea [Select...Case \(Instrucción\)](../../../visual-basic/language-reference/statements/select-case-statement.md).  
  
 `Set`  
 Es obligatorio para terminar una definición de procedimiento `Property` que comienza por un [Set \(Instrucción\)](../../../visual-basic/language-reference/statements/set-statement.md) correspondiente.  Si en la ejecución se encuentra una instrucción `End` `Set`, el control vuelve a la instrucción que establece el valor de la propiedad.  
  
 `Structure`  
 Es obligatorio para terminar una definición de estructura que comienza por una [Structure \(Instrucción\)](../../../visual-basic/language-reference/statements/structure-statement.md) correspondiente.  
  
 `Sub`  
 Es obligatorio para terminar una definición de procedimiento `Sub` que comienza por un [Sub \(Instrucción\)](../../../visual-basic/language-reference/statements/sub-statement.md) correspondiente.  Si en la ejecución se encuentra una instrucción `End` `Sub`, el control vuelve al código de llamada.  
  
 `SyncLock`  
 Es obligatorio para terminar una definición de bloque `SyncLock` que comienza por una instrucción `SyncLock` correspondiente.  Vea [SyncLock \(Instrucción\)](../../../visual-basic/language-reference/statements/synclock-statement.md).  
  
 `Try`  
 Es obligatorio para terminar una definición de bloque `Try`...`Catch`...`Finally` que comienza por una instrucción `Try` correspondiente.  Vea [Try...Catch...Finally \(Instrucción\)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
 `While`  
 Es obligatorio para terminar una definición de bucle `While` que comienza por una instrucción `While` correspondiente.  Vea [While...End While \(Instrucción\)](../../../visual-basic/language-reference/statements/while-end-while-statement.md).  
  
 `With`  
 Es obligatorio para terminar una definición de bloque `With` que comienza por una instrucción `With` correspondiente.  Vea [With...End With \(Instrucción\)](../../../visual-basic/language-reference/statements/with-end-with-statement.md).  
  
## Comentarios  
 [End \(Instrucción\)](../../../visual-basic/language-reference/statements/end-statement.md), sin una palabra clave adicional, termina la ejecución inmediatamente.  
  
 Cuando le precede un signo de número \(`#`\), la palabra clave `End` finaliza un bloque de preprocesamiento introducido por la directiva correspondiente.  
  
 `#End`  
 Obligatorio.  Termina la definición del bloque de preprocesamiento.  
  
 `#ExternalSource`  
 Es obligatorio para terminar un bloque de origen externo que comienza por un [\#ExternalSource \(Directiva\)](../../../visual-basic/language-reference/directives/externalsource-directive.md) correspondiente.  
  
 `#If`  
 Es obligatorio para terminar un bloque de compilación condicional que comienza por una directiva `#If` correspondiente.  Vea [\#If...Then...\#Else \(Directivas\)](../../../visual-basic/language-reference/directives/if-then-else-directives.md).  
  
 `#Region`  
 Es obligatorio para terminar un bloque de área de origen que comienza por un [\#Region \(Directiva\)](../../../visual-basic/language-reference/directives/region-directive.md) correspondiente.  
  
## Notas para desarrolladores de dispositivos Smart Device  
 No se admite la instrucción `End` si no va acompañada de una palabra clave adicional.  
  
## Vea también  
 [End \(Instrucción\)](../../../visual-basic/language-reference/statements/end-statement.md)