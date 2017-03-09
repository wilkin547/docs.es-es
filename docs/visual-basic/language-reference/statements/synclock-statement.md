---
title: "SyncLock (Instrucci&#243;n) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.SyncLock"
  - "SyncLock"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "bloqueos, subprocesos"
  - "SyncLock (instrucción)"
  - "subprocesamiento [Visual Basic], bloqueos"
ms.assetid: 14501703-298f-4d43-b139-c4b6366af176
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# SyncLock (Instrucci&#243;n)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Adquiere un bloqueo exclusivo para un bloque de instrucciones antes de ejecutar el bloque.  
  
## Sintaxis  
  
```  
SyncLock lockobject  
    [ block ]  
End SyncLock  
```  
  
## Elementos  
 `lockobject`  
 Requerido.  Expresión que se evalúa como una referencia a objeto.  
  
 `block`  
 Opcional.  Bloque de instrucciones que se ejecuta cuando se adquiere el bloqueo.  
  
 `End SyncLock`  
 Termina un bloque `SyncLock`.  
  
## Comentarios  
 La instrucción `SyncLock` se asegura de que varios subprocesos no ejecutan el bloque de instrucciones al mismo tiempo.  `SyncLock` evita que cada subproceso entre en el bloque hasta que no haya otro subproceso ejecutándolo.  
  
 El uso más común de `SyncLock` es impedir que más de un subproceso actualice los datos simultáneamente.  Si las instrucciones que manipulan los datos deben completarse sin interrupciones, colóquelas dentro de un bloque `SyncLock`.  
  
 Un bloque de instrucciones protegido por un bloqueo exclusivo se denomina a veces una *sección crítica*.  
  
## Reglas  
  
-   Bifurcación.  No puede bifurcar en un bloque `SyncLock` desde fuera del bloque.  
  
-   Valor del objeto Lock.  El valor de `lockobject` no puede ser `Nothing`.  Debe crear el objeto de bloqueo antes de utilizarlo en una instrucción `SyncLock`.  
  
     No puede cambiar el valor de `lockobject` mientras ejecuta un bloque `SyncLock`.  El mecanismo requiere que el objeto de bloqueo permanezca inalterado.  
  
-   No puede utilizar el operador de [Espera](../../../visual-basic/language-reference/operators/await-operator.md) en un bloque de `SyncLock` .  
  
## Comportamiento  
  
-   Mecanismo.  Cuando un subproceso llega a la instrucción `SyncLock`, evalúa la expresión `lockobject` e interrumpe la ejecución hasta que adquiere un bloqueo exclusivo sobre el objeto devuelto por la expresión.  Cuando otro subproceso llega a la instrucción `SyncLock`, no adquiere un bloqueo hasta que el primer subproceso ejecute la instrucción `End SyncLock`  
  
-   Datos protegidos.  Si `lockobject` es una variable `Shared`, el bloqueo exclusivo impide que un subproceso de cualquier instancia de la clase ejecute el bloque `SyncLock` mientras lo ejecute otro subproceso.  Esto protege los datos compartidos entre todas las instancias.  
  
     Si `lockobject` es una variable de instancia \(no `Shared`\), el bloqueo impide que un subproceso que se ejecuta en la instancia actual ejecute el bloque `SyncLock` en la misma instancia a la vez que otro subproceso.  Esto protege los datos mantenidos por la instancia individual.  
  
-   Adquisición y liberación.  Un bloque `SyncLock` se comporta como otra construcción `Try...Finally` en la que el bloque `Try` adquiere un bloqueo exclusivo sobre `lockobject` y el bloque `Finally` lo libera.  Gracias a esto, el bloque `SyncLock` garantiza la liberación del bloqueo, independientemente de cómo salga del bloque.  Esto es verdad incluso en el caso de una excepción no controlada.  
  
-   Llamadas del marco de trabajo.  El bloque `SyncLock` adquiere y libera el bloqueo exclusivo llamando a los métodos `Enter` y `Exit` de la clase `Monitor` en el espacio de nombres <xref:System.Threading>.  
  
## Programar prácticas  
 La expresión `lockobject` se debe evaluar siempre como un objeto que pertenece exclusivamente a su clase.  Debe declarar una variable de objeto `Private` para proteger los datos que pertenecen a la instancia actual o una variable de objeto `Private Shared` para proteger los datos comunes a todas las instancias.  
  
 No debe utilizar la palabra clave `Me` para proporcionar un objeto de bloqueo para los datos de instancia.  Si existe un código ajeno a su clase con una referencia a una instancia de su clase, éste puede utilizar esta referencia como un objeto de bloqueo para un bloque `SyncLock` totalmente distinto del suyo y proteger datos distintos.  De esta manera, su clase y la otra clase podrían impedir que se ejecutaran sus bloques `SyncLock` no relacionados.  Bloquear de forma similar una cadena puede ser problemático ya que cualquier otro código del proceso, que utilice la misma cadena, compartirá el mismo bloqueo.  
  
 Asimismo, no debe utilizar el método `Me.GetType` para proporcionar un objeto de bloqueo para datos compartidos.  Esto se debe a que `GetType` devuelve siempre el mismo objeto `Type` para un nombre de clase determinado.  El código externo podría llamar a `GetType` en su clase y obtener el mismo objeto de bloqueo que está utilizando.  Esto provocaría el bloqueo de las dos clases entre sí desde sus bloques `SyncLock`.  
  
## Ejemplos  
  
### Descripción  
 El ejemplo siguiente muestra una clase que mantiene una lista simple de mensajes.  Contiene los mensajes en una matriz y el último elemento utilizado de esa matriz en una variable.  El procedimiento `addAnotherMessage` incrementa el último elemento y almacena el nuevo mensaje.  Estas dos operaciones están protegidas por las instrucciones `SyncLock` y `End SyncLock` porque una vez incrementado el último elemento, se debe almacenar el nuevo mensaje antes de que cualquier otro subproceso pueda incrementar de nuevo el último elemento.  
  
 Si la clase `simpleMessageList` compartiera una lista de mensajes entre todas sus instancias, las variables `messagesList` y `messagesLast` se declararían como `Shared`.  En este caso, la variable `messagesLock` también debería ser `Shared` para que hubiera un único objeto de bloqueo utilizado por todas las instancias.  
  
### Código  
 [!code-vb[VbVbalrThreading#1](../../../visual-basic/language-reference/statements/codesnippet/visualbasic/synclock-statement_1.vb)]  
  
### Descripción  
 El siguiente ejemplo utiliza subprocesos y `SyncLock`.  Con el uso de la instrucción `SyncLock`, el bloque de instrucciones se convierte en una sección crítica y `balance` nunca toma un valor negativo.  Puede marcar como comentario las instrucciones `SyncLock` y `End SyncLock` para ver el efecto de omitir la palabra clave `SyncLock`.  
  
### Código  
 [!code-vb[VbVbalrThreading#21](../../../visual-basic/language-reference/statements/codesnippet/visualbasic/synclock-statement_2.vb)]  
  
### Comentarios  
  
## Vea también  
 <xref:System.Threading>   
 <xref:System.Threading.Monitor>   
 [Sincronización de subprocesos](../Topic/Thread%20Synchronization%20\(C%23%20and%20Visual%20Basic\).md)   
 [Subprocesos](../Topic/Threading%20\(C%23%20and%20Visual%20Basic\).md)