---
title: SyncLock (instrucción) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.SyncLock
- SyncLock
helpviewer_keywords:
- threading [Visual Basic], locks
- SyncLock statement [Visual Basic]
- locks, threads
ms.assetid: 14501703-298f-4d43-b139-c4b6366af176
ms.openlocfilehash: 6f5a89ebe359ca2fdae1d5545192dc2dcecca6a2
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43401380"
---
# <a name="synclock-statement"></a>SyncLock (Instrucción)
Adquiere un bloqueo exclusivo para un bloque de instrucciones antes de ejecutar el bloque.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
SyncLock lockobject  
    [ block ]  
End SyncLock  
```  
  
## <a name="parts"></a>Elementos  
 `lockobject`  
 Requerido. Expresión que se evalúa como una referencia de objeto.  
  
 `block`  
 Opcional. Bloque de instrucciones que se ejecuta cuando se adquiere el bloqueo.  
  
 `End SyncLock`  
 Finaliza un `SyncLock` bloque.  
  
## <a name="remarks"></a>Comentarios  
 El `SyncLock` instrucción garantiza que varios subprocesos no ejecuten el bloque de instrucciones al mismo tiempo. `SyncLock` impide que cada subproceso entra en el bloque hasta que no está ejecutando ningún otro subproceso.  
  
 El uso más común de `SyncLock` consiste en proteger los datos se actualice mediante varios subprocesos simultáneamente. Si las instrucciones que manipulan los datos deben ir hasta su finalización sin interrupción, colocarlos dentro un `SyncLock` bloque.  
  
 Un bloque de instrucciones protegido por un bloqueo exclusivo a veces se denomina un *sección crítica*.  
  
## <a name="rules"></a>Reglas  
  
-   La bifurcación. No puede bifurcarse en un `SyncLock` bloquear desde fuera del bloque.  
  
-   Valor de objeto de bloqueo. El valor de `lockobject` no puede ser `Nothing`. Debe crear el objeto de bloqueo antes de usarlo en un `SyncLock` instrucción.  
  
     No se puede cambiar el valor de `lockobject` mientras se ejecuta un `SyncLock` bloque. El mecanismo requiere que el objeto de bloqueo permanecen sin cambios.  
  
-   No puede usar el [Await](../../../visual-basic/language-reference/operators/await-operator.md) operador en un `SyncLock` bloque.  
  
## <a name="behavior"></a>Comportamiento  
  
-   Mecanismo. Cuando un subproceso llega la `SyncLock` instrucción, se evalúa como el `lockobject` expresión y suspende la ejecución hasta que adquiere un bloqueo exclusivo en el objeto devuelto por la expresión. Cuando se alcance otro subproceso el `SyncLock` instrucción, no podrá adquirir un bloqueo hasta que se ejecuta el primer subproceso el `End SyncLock` instrucción.  
  
-   Datos protegidos. Si `lockobject` es un `Shared` variable, el bloqueo exclusivo impide que un subproceso en cualquier instancia de la clase ejecutando el `SyncLock` bloquear mientras está ejecutando ningún otro subproceso. Esto protege los datos que se comparten entre todas las instancias.  
  
     Si `lockobject` es una variable de instancia (no `Shared`), el bloqueo impide que un subproceso que se ejecuta en la instancia actual de ejecutar el `SyncLock` bloque al mismo tiempo que otro subproceso en la misma instancia. Esto protege los datos mantenidos por la instancia individual.  
  
-   Adquisición y liberación. Un `SyncLock` bloque se comporta como un `Try...Finally` construcción en el que el `Try` bloque adquiere un bloqueo exclusivo en `lockobject` y `Finally` bloqueo lo libere. Por este motivo, la `SyncLock` bloque garantiza la liberación del bloqueo, independientemente de cómo salga el bloque. Esto es cierto incluso si se produce una excepción no controlada.  
  
-   Llamadas de Framework. El `SyncLock` bloque adquiere y libera el bloqueo exclusivo mediante una llamada a la `Enter` y `Exit` métodos de la `Monitor` clase en el <xref:System.Threading> espacio de nombres.  
  
## <a name="programming-practices"></a>Prácticas recomendadas de programación  
 El `lockobject` expresión siempre debe evaluarse como un objeto que pertenece exclusivamente a la clase. Se debe declarar un `Private` variable de objeto para proteger los datos que pertenecen a la instancia actual, o un `Private Shared` variable de objeto para proteger los datos comunes a todas las instancias.  
  
 No se debe usar el `Me` palabra clave para proporcionar un bloqueo de objeto por ejemplo datos. Si el código externo a la clase tiene una referencia a una instancia de la clase, podría usar esa referencia como un objeto de bloqueo para un `SyncLock` bloque totalmente distinto del suyo, protección de datos diferentes. De este modo, la clase y la otra clase podrían se bloquean entre sí de ejecutar sus no relacionadas `SyncLock` bloques. El bloqueo de forma similar en una cadena puede ser problemático, ya que cualquier otro código en el proceso con la misma cadena compartirá el mismo bloqueo.  
  
 No debe utilizar el `Me.GetType` método para proporcionar un objeto de bloqueo de datos compartidos. Esto es porque `GetType` siempre devuelve el mismo `Type` objeto para un nombre de clase determinada. Podría llamar código externo `GetType` en su clase y obtener el mismo objeto de bloqueo que se usa. Esto daría lugar a las dos clases de bloqueo entre sí desde sus `SyncLock` bloques.  
  
## <a name="examples"></a>Ejemplos  
  
### <a name="description"></a>Descripción  
 El ejemplo siguiente muestra una clase que mantiene una lista simple de mensajes. Contiene los mensajes en una matriz y el último elemento de la matriz utilizado en una variable. El `addAnotherMessage` procedimiento incrementa el último elemento y almacena el nuevo mensaje. Esas dos operaciones están protegidas por la `SyncLock` y `End SyncLock` instrucciones, ya que una vez que se ha incrementado el último elemento, se debe almacenar el nuevo mensaje antes de que ningún otro subproceso puede incrementar el último elemento nuevo.  
  
 Si el `simpleMessageList` comparte una lista de mensajes entre todas sus instancias, las variables de clase `messagesList` y `messagesLast` se declararía como `Shared`. En este caso, la variable `messagesLock` también debe ser `Shared`, de modo que sería un objeto único bloqueo utilizado por todas las instancias.  
  
### <a name="code"></a>Código  
 [!code-vb[VbVbalrThreading#1](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/synclock-statement_1.vb)]  
  
### <a name="description"></a>Descripción  
 En el ejemplo siguiente se usa subprocesos y `SyncLock`. Siempre y cuando la `SyncLock` instrucción está presente, el bloque de instrucciones es una sección crítica y `balance` nunca se convierte en un número negativo. Puede marcar como comentario el `SyncLock` y `End SyncLock` instrucciones para ver el efecto de omitir el `SyncLock` palabra clave.  
  
### <a name="code"></a>Código  
 [!code-vb[VbVbalrThreading#21](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/synclock-statement_2.vb)]  
  
### <a name="comments"></a>Comentarios  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Threading>  
 <xref:System.Threading.Monitor>  
 [Sincronización de subprocesos](../../programming-guide/concepts/threading/thread-synchronization.md)  
 [Subprocesamiento](../../programming-guide/concepts/threading/index.md)
