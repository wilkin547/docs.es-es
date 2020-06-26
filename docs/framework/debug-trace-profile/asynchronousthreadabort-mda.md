---
title: MDA de asynchronousThreadAbort
description: Revise cómo se activa el Asistente para la depuración administrada (MDA) asynchronousThreadAbort cuando un subproceso intenta colocar una anulación asincrónica en otro subproceso.
ms.date: 03/30/2017
helpviewer_keywords:
- asynchronous thread aborts
- AsynchronousThreadAbort MDA
- managed debugging assistants (MDAs), asynchronous thread aborts
- threading [.NET Framework], managed debugging assistants
- MDAs (managed debugging assistants), asynchronous thread aborts
ms.assetid: 9ebe40b2-d703-421e-8660-984acc42bfe0
ms.openlocfilehash: 469372d57d9c21198353d171fec16458691eb25d
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415672"
---
# <a name="asynchronousthreadabort-mda"></a>MDA de asynchronousThreadAbort
El Asistente para la depuración administrada (MDA) `asynchronousThreadAbort` se activa cuando un subproceso intenta incorporar una anulación asincrónica a otro subproceso. Las anulaciones de subproceso sincrónicas no activan el MDA `asynchronousThreadAbort`.

## <a name="symptoms"></a>Síntomas
 Una aplicación se bloquea con una <xref:System.Threading.ThreadAbortException> no controlada cuando se anula el subproceso de aplicación principal. Si la aplicación siguiera ejecutándose, las consecuencias podrían ser peores que el bloqueo, posiblemente más datos dañados.

 Las operaciones que debían ser atómicas es probable que se hayan interrumpido tras la finalización parcial, dejando los datos de la aplicación en un estado impredecible. Una <xref:System.Threading.ThreadAbortException> se puede generar desde puntos aparentemente aleatorios de la ejecución de código, a menudo en ubicaciones desde las que no se esperaba que se generara una excepción. El código podría no ser capaz de controlar este tipo de excepción, lo que daría lugar a un estado dañado.

 Los síntomas pueden variar enormemente debido a la aleatoriedad inherente al problema.

## <a name="cause"></a>Causa
 El código de un subproceso ha llamado al método <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> de un subproceso de destino para incorporar una anulación de subproceso asincrónica. La anulación de subproceso es asincrónica porque el código que realiza la llamada a <xref:System.Threading.Thread.Abort%2A> se ejecuta en un subproceso distinto al destino de la operación de anulación. Las anulaciones de subproceso sincrónicas no deberían causar problemas, ya que el subproceso que realiza la <xref:System.Threading.Thread.Abort%2A> debe haberla hecho únicamente en un punto de control seguro donde el estado de la aplicación es coherente.

 Las anulaciones de subproceso asincrónicas presentan un problema, ya que se procesan en puntos impredecibles de la ejecución del subproceso de destino. Para evitar esto, el código escrito para ejecutarse en un subproceso que se pueda anular de este modo tendría que controlar una <xref:System.Threading.ThreadAbortException> prácticamente en cada línea de código, teniendo cuidado de volver a poner los datos de la aplicación en un estado coherente. No es realista esperar que el código se escriba teniendo en cuenta este problema ni escribir código protegido frente a todas las circunstancias posibles.

 Las llamadas a código no administrado y bloques `finally` no se anulan asincrónicamente, sino inmediatamente al salir de una de estas categorías.

 La causa puede ser difícil de determinar debido a la aleatoriedad inherente al problema.

## <a name="resolution"></a>Solución
 Evite el diseño de código que necesite anulaciones de subproceso asincrónicas. Existen varios enfoques más adecuados para la interrupción de un subproceso de destino que no requieren una llamada a <xref:System.Threading.Thread.Abort%2A>. El más seguro consiste en incorporar un mecanismo, como una propiedad común, que indique al subproceso de destino que solicite una interrupción. El subproceso de destino comprueba la señal en determinados puntos de control seguros. Si observa que se ha solicitado una interrupción, puede cerrar correctamente.

## <a name="effect-on-the-runtime"></a>Efecto en el Runtime
 Este MDA no tiene ningún efecto en el CLR. Solo notifica datos sobre las anulaciones de subproceso asincrónicas.

## <a name="output"></a>Output
 El MDA notifica el identificador del subproceso que realiza la anulación y el identificador del subproceso que es el destino de ella. Nunca serán iguales, porque eso está limitado a las interrupciones asincrónicas.

## <a name="configuration"></a>Configuración

```xml
<mdaConfig>
  <assistants>
    <asynchronousThreadAbort />
  </assistants>
</mdaConfig>
```

## <a name="example"></a>Ejemplo
 La activación del MDA `asynchronousThreadAbort` solo exige una llamada a <xref:System.Threading.Thread.Abort%2A> en un subproceso independiente en ejecución. Tenga en cuenta las consecuencias si el contenido de la función de inicio del subproceso fuera un conjunto de operaciones más complejas que la anulación pudiera interrumpir en cualquier punto arbitrario.

```csharp
using System.Threading;
void FireMda()
{
    Thread t = new Thread(delegate() { Thread.Sleep(1000); });
    t.Start();
    // The following line activates the MDA.
    t.Abort();
    t.Join();
}
```

## <a name="see-also"></a>Consulte también

- <xref:System.Threading.Thread>
- [Diagnóstico de errores con asistentes de depuraciones administradas](diagnosing-errors-with-managed-debugging-assistants.md)
