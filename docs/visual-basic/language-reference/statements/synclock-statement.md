---
description: 'Más información acerca de: SyncLock (instrucción)'
title: SyncLock (Instrucción)
ms.date: 07/20/2015
f1_keywords:
- vb.SyncLock
- SyncLock
helpviewer_keywords:
- threading [Visual Basic], locks
- SyncLock statement [Visual Basic]
- locks, threads
ms.assetid: 14501703-298f-4d43-b139-c4b6366af176
ms.openlocfilehash: 206c10c8bca85a496345576d0d5f9ff260db82e3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99740982"
---
# <a name="synclock-statement"></a>SyncLock (Instrucción)

Adquiere un bloqueo exclusivo para un bloque de instrucciones antes de ejecutar el bloque.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
SyncLock lockobject  
    [ block ]  
End SyncLock  
```  
  
## <a name="parts"></a>Partes  

 `lockobject`  
 Necesario. Expresión que se evalúa como una referencia de objeto.  
  
 `block`  
 Opcional. Bloque de instrucciones que se ejecutan cuando se adquiere el bloqueo.  
  
 `End SyncLock`  
 Finaliza un `SyncLock` bloque.  
  
## <a name="remarks"></a>Observaciones  

 La `SyncLock` instrucción garantiza que varios subprocesos no ejecuten el bloque de instrucciones al mismo tiempo. `SyncLock` impide que cada subproceso entre en el bloque hasta que no lo ejecute ningún otro subproceso.  
  
 El uso más común de `SyncLock` es proteger los datos de la actualización por parte de más de un subproceso simultáneamente. Si las instrucciones que manipulan los datos deben ir a la finalización sin interrupción, colóquelos dentro de un `SyncLock` bloque.  
  
 Un bloque de instrucciones protegido por un bloqueo exclusivo a veces se denomina *sección crítica*.  
  
## <a name="rules"></a>Reglas  
  
- Bifurcación. No se puede crear una bifurcación en un `SyncLock` bloque desde fuera del bloque.  
  
- Valor de bloqueo de objeto. El valor de `lockobject` no puede ser `Nothing` . Debe crear el objeto de bloqueo antes de usarlo en una `SyncLock` instrucción.  
  
     No se puede cambiar el valor de `lockobject` mientras se ejecuta un `SyncLock` bloque. El mecanismo requiere que el objeto de bloqueo permanezca sin cambios.  
  
- No se puede usar el operador [Await](../operators/await-operator.md) en un `SyncLock` bloque.  
  
## <a name="behavior"></a>Comportamiento  
  
- Método. Cuando un subproceso alcanza la `SyncLock` instrucción, evalúa la `lockobject` expresión y suspende la ejecución hasta que adquiere un bloqueo exclusivo en el objeto devuelto por la expresión. Cuando otro subproceso alcanza la `SyncLock` instrucción, no adquiere un bloqueo hasta que el primer subproceso ejecuta la `End SyncLock` instrucción.  
  
- Datos protegidos. Si `lockobject` es una `Shared` variable, el bloqueo exclusivo impide que un subproceso de una instancia de la clase ejecute el `SyncLock` bloque mientras otro subproceso lo está ejecutando. Esto protege los datos que se comparten entre todas las instancias.  
  
     Si `lockobject` es una variable de instancia (no `Shared` ), el bloqueo impide que un subproceso que se ejecuta en la instancia actual ejecute el `SyncLock` bloque al mismo tiempo que otro subproceso de la misma instancia. Esto protege los datos mantenidos por la instancia individual.  
  
- Adquisición y lanzamiento. Un `SyncLock` bloque se comporta como una `Try...Finally` construcción en la que el `Try` bloque adquiere un bloqueo exclusivo en `lockobject` y el `Finally` bloque lo libera. Por este motivo, el `SyncLock` bloque garantiza la liberación del bloqueo, independientemente de cómo salga del bloque. Esto es así incluso en el caso de una excepción no controlada.  
  
- Llamadas de marco de trabajo. El `SyncLock` bloque adquiere y libera el bloqueo exclusivo mediante una llamada a `Enter` los `Exit` métodos y de la `Monitor` clase en el <xref:System.Threading> espacio de nombres.  
  
## <a name="programming-practices"></a>Prácticas de programación  

 La `lockobject` expresión siempre debe evaluarse como un objeto que pertenece exclusivamente a la clase. Debe declarar una `Private` variable de objeto para proteger los datos que pertenecen a la instancia actual o una `Private Shared` variable de objeto para proteger los datos comunes a todas las instancias.  
  
 No debe utilizar la `Me` palabra clave para proporcionar un objeto de bloqueo para los datos de instancia. Si el código externo a la clase tiene una referencia a una instancia de la clase, podría usar esa referencia como un objeto de bloqueo para un `SyncLock` bloque completamente diferente del suyo, protegiendo datos diferentes. De esta manera, la clase y la otra clase podrían bloquearse entre sí desde la ejecución de los `SyncLock` bloques no relacionados. Un bloqueo similar en una cadena puede ser problemático, ya que cualquier otro código del proceso que use la misma cadena compartirá el mismo bloqueo.  
  
 Tampoco debe utilizar el `Me.GetType` método para proporcionar un objeto de bloqueo para los datos compartidos. Esto se debe `GetType` a que siempre devuelve el mismo `Type` objeto para un nombre de clase determinado. El código externo podría llamar a `GetType` en su clase y obtener el mismo objeto de bloqueo que está utilizando. Esto daría lugar a que las dos clases se bloqueen entre sí desde sus `SyncLock` bloques.  
  
## <a name="examples"></a>Ejemplos  
  
### <a name="description"></a>Descripción  

 En el ejemplo siguiente se muestra una clase que mantiene una lista de mensajes simple. Contiene los mensajes de una matriz y el último elemento utilizado de esa matriz en una variable. El `addAnotherMessage` procedimiento incrementa el último elemento y almacena el nuevo mensaje. Estas dos operaciones están protegidas por las `SyncLock` `End SyncLock` instrucciones y, porque una vez que se ha incrementado el último elemento, el nuevo mensaje se debe almacenar antes de que cualquier otro subproceso pueda incrementar el último elemento de nuevo.  
  
 Si la `simpleMessageList` clase compartía una lista de mensajes entre todas sus instancias, las variables `messagesList` y `messagesLast` se declararían como `Shared` . En este caso, la variable `messagesLock` también debe ser `Shared` , de modo que haya un solo objeto de bloqueo utilizado por cada instancia.  
  
### <a name="code"></a>Código  

 [!code-vb[VbVbalrThreading#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrThreading/VB/Class1.vb#1)]  
  
### <a name="description"></a>Descripción  

 En el ejemplo siguiente se usan los subprocesos y `SyncLock` . Siempre y cuando la `SyncLock` instrucción esté presente, el bloque de instrucciones es una sección crítica y `balance` nunca se convierte en un número negativo. Puede comentar las `SyncLock` `End SyncLock` instrucciones y para ver el efecto de salir de la `SyncLock` palabra clave.  
  
### <a name="code"></a>Código  

 [!code-vb[VbVbalrThreading#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrThreading/VB/class2.vb#21)]  
  
### <a name="comments"></a>Comentarios  
  
## <a name="see-also"></a>Vea también

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.Interlocked?displayProperty=nameWithType>
- [Información general sobre las primitivas de sincronización](../../../standard/threading/overview-of-synchronization-primitives.md)
