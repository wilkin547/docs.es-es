---
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
ms.openlocfilehash: 0f430edce99513b0de9ef437d70648a128b336b8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352816"
---
# <a name="synclock-statement"></a>SyncLock (Instrucción)
Adquiere un bloqueo exclusivo para un bloque de instrucciones antes de ejecutar el bloque.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
SyncLock lockobject  
    [ block ]  
End SyncLock  
```  
  
## <a name="parts"></a>Elementos  
 `lockobject`  
 Obligatorio. Expresión que se evalúa como una referencia de objeto.  
  
 `block`  
 Opcional. Bloque de instrucciones que se ejecutan cuando se adquiere el bloqueo.  
  
 `End SyncLock`  
 Finaliza un bloque de `SyncLock`.  
  
## <a name="remarks"></a>Comentarios  
 La instrucción `SyncLock` garantiza que varios subprocesos no ejecuten el bloque de instrucciones al mismo tiempo. `SyncLock` impide que cada subproceso entre en el bloque hasta que no lo ejecute ningún otro subproceso.  
  
 El uso más común de `SyncLock` consiste en proteger los datos de la actualización a más de un subproceso simultáneamente. Si las instrucciones que manipulan los datos deben ir a la finalización sin interrupción, colóquelos dentro de un bloque `SyncLock`.  
  
 Un bloque de instrucciones protegido por un bloqueo exclusivo a veces se denomina *sección crítica*.  
  
## <a name="rules"></a>Reglas  
  
- Bifurcación. No se puede crear una bifurcación en un bloque `SyncLock` desde fuera del bloque.  
  
- Valor de bloqueo de objeto. No se puede `Nothing`el valor de `lockobject`. Debe crear el objeto de bloqueo antes de usarlo en una instrucción `SyncLock`.  
  
     No se puede cambiar el valor de `lockobject` mientras se ejecuta un bloque de `SyncLock`. El mecanismo requiere que el objeto de bloqueo permanezca sin cambios.  
  
- No se puede usar el operador [Await](../../../visual-basic/language-reference/operators/await-operator.md) en un bloque `SyncLock`.  
  
## <a name="behavior"></a>Comportamiento  
  
- Método. Cuando un subproceso alcanza la instrucción `SyncLock`, evalúa la expresión `lockobject` y suspende la ejecución hasta que adquiere un bloqueo exclusivo en el objeto devuelto por la expresión. Cuando otro subproceso alcanza la instrucción `SyncLock`, no adquiere un bloqueo hasta que el primer subproceso ejecuta la instrucción `End SyncLock`.  
  
- Datos protegidos. Si `lockobject` es una variable de `Shared`, el bloqueo exclusivo impide que un subproceso de una instancia de la clase ejecute el bloque de `SyncLock` mientras otro subproceso lo está ejecutando. Esto protege los datos que se comparten entre todas las instancias.  
  
     Si `lockobject` es una variable de instancia (no `Shared`), el bloqueo impide que un subproceso que se ejecuta en la instancia actual ejecute el bloque de `SyncLock` al mismo tiempo que otro subproceso de la misma instancia. Esto protege los datos mantenidos por la instancia individual.  
  
- Adquisición y lanzamiento. Un bloque `SyncLock` se comporta como una construcción `Try...Finally` en la que el bloque `Try` adquiere un bloqueo exclusivo en `lockobject` y el bloque `Finally` lo libera. Por este motivo, el bloque `SyncLock` garantiza la liberación del bloqueo, independientemente de cómo salga del bloque. Esto es así incluso en el caso de una excepción no controlada.  
  
- Llamadas de marco de trabajo. El bloque `SyncLock` adquiere y libera el bloqueo exclusivo mediante una llamada a los métodos `Enter` y `Exit` de la clase `Monitor` en el espacio de nombres <xref:System.Threading>.  
  
## <a name="programming-practices"></a>Prácticas de programación  
 La expresión `lockobject` siempre debe evaluarse como un objeto que pertenezca exclusivamente a la clase. Debe declarar un `Private` variable de objeto para proteger los datos que pertenecen a la instancia actual o una variable de objeto `Private Shared` para proteger los datos comunes a todas las instancias.  
  
 No debe utilizar la palabra clave `Me` para proporcionar un objeto de bloqueo para los datos de instancia. Si el código externo a la clase tiene una referencia a una instancia de la clase, podría usar esa referencia como un objeto de bloqueo para un bloque `SyncLock` completamente diferente del suyo, protegiendo los datos diferentes. De esta manera, la clase y la otra clase podrían bloquearse entre sí desde la ejecución de los bloques de `SyncLock` no relacionados. Un bloqueo similar en una cadena puede ser problemático, ya que cualquier otro código del proceso que use la misma cadena compartirá el mismo bloqueo.  
  
 Tampoco debe utilizar el método `Me.GetType` para proporcionar un objeto de bloqueo para los datos compartidos. Esto se debe a que `GetType` siempre devuelve el mismo objeto `Type` para un nombre de clase determinado. El código externo podría llamar a `GetType` en la clase y obtener el mismo objeto de bloqueo que está utilizando. Esto daría lugar a que las dos clases se bloqueen entre sí desde sus bloques `SyncLock`.  
  
## <a name="examples"></a>Ejemplos  
  
### <a name="description"></a>Descripción  
 En el ejemplo siguiente se muestra una clase que mantiene una lista de mensajes simple. Contiene los mensajes de una matriz y el último elemento utilizado de esa matriz en una variable. En el procedimiento `addAnotherMessage` se incrementa el último elemento y se almacena el mensaje nuevo. Estas dos operaciones están protegidas por las instrucciones `SyncLock` y `End SyncLock`, porque una vez que se ha incrementado el último elemento, el nuevo mensaje se debe almacenar antes de que cualquier otro subproceso pueda incrementar el último elemento de nuevo.  
  
 Si la clase `simpleMessageList` compartió una lista de mensajes entre todas sus instancias, las variables `messagesList` y `messagesLast` se declararían como `Shared`. En este caso, la variable `messagesLock` también debe ser `Shared`, de modo que haya un único objeto de bloqueo utilizado por cada instancia.  
  
### <a name="code"></a>Código  
 [!code-vb[VbVbalrThreading#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrThreading/VB/Class1.vb#1)]  
  
### <a name="description"></a>Descripción  
 En el ejemplo siguiente se usan subprocesos y `SyncLock`. Siempre y cuando la instrucción `SyncLock` esté presente, el bloque de instrucciones es una sección crítica y `balance` nunca se convierte en un número negativo. Puede comentar las instrucciones `SyncLock` y `End SyncLock` para ver el efecto de salir de la palabra clave `SyncLock`.  
  
### <a name="code"></a>Código  
 [!code-vb[VbVbalrThreading#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrThreading/VB/class2.vb#21)]  
  
### <a name="comments"></a>Comentarios  
  
## <a name="see-also"></a>Vea también

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.Interlocked?displayProperty=nameWithType>
- [Información general sobre las primitivas de sincronización](../../../standard/threading/overview-of-synchronization-primitives.md)
