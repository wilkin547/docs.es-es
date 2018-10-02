---
title: lock (Instrucción, Referencia de C#)
description: Use la instrucción lock de C# para sincronizar el acceso de un subproceso al recurso compartido
ms.date: 08/28/2018
f1_keywords:
- lock_CSharpKeyword
- lock
helpviewer_keywords:
- lock keyword [C#]
ms.assetid: 656da1a4-707e-4ef6-9c6e-6d13b646af42
ms.openlocfilehash: 2b6fbfb2f81d7745c4effb9ea0087f34cc872a6c
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43858361"
---
# <a name="lock-statement-c-reference"></a>lock (Instrucción, Referencia de C#)

La instrucción `lock` obtiene el bloqueo de exclusión mutua de un objeto determinado, ejecuta un bloque de instrucciones y luego libera el bloqueo. Mientras se mantiene un bloqueo, el subproceso que lo mantiene puede volver a obtener y liberar el bloqueo. Ningún otro subproceso puede obtener el bloqueo y espera hasta que se libera.

La instrucción `lock` tiene el formato

```csharp
lock (x)
{
    // Your code...
}
```

donde `x` es una expresión de un [tipo de referencia](reference-types.md). Es exactamente equivalente a

```csharp
object __lockObj = x;
bool __lockWasTaken = false;
try
{
    System.Threading.Monitor.Enter(__lockObj, ref __lockWasTaken);
    // Your code...
}
finally
{
    if (__lockWasTaken) System.Threading.Monitor.Exit(__lockObj);
}
```

Puesto que el código usa un bloque [try... finally](try-finally.md), el bloqueo se libera aunque se produzca una excepción dentro del cuerpo de una instrucción `lock`.

No se puede usar la palabra clave [await](await.md) en el cuerpo de una instrucción `lock`.

## <a name="remarks"></a>Comentarios

Al sincronizar el acceso del subproceso al recurso compartido, bloquee una instancia dedicada de objeto (por ejemplo, `private readonly object balanceLock = new object();`) u otra instancia cuyo empleo como objeto de bloqueo sea poco probable por parte de elementos no relacionados del código. Evite el uso de la misma instancia de objeto de bloqueo para distintos recursos compartidos, ya que se podría producir un interbloqueo o una contención de bloqueo. En particular, evite usar

- `this` (los autores de llamadas podrían usarlo como un bloqueo),
- instancias <xref:System.Type> (el operador o la reflexión [typeof](typeof.md) podrían obtenerlas),
- instancias de cadena, incluidos literales de cadena,

como objetos de bloqueo.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se define una clase `Account` que sincroniza el acceso a su campo privado `balance` mediante el bloqueo de una instancia dedicada `balanceLock`. El empleo de la misma instancia para bloquear garantiza que el campo `balance` no sea actualizado al mismo tiempo por dos subprocesos que intentan llamar a los métodos `Debit` o `Credit` simultáneamente.

[!code-csharp[lock-statement-example](~/samples/snippets/csharp/keywords/LockStatementExample.cs)]

## <a name="c-language-specification"></a>especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.SpinLock?displayProperty=nameWithType>
- <xref:System.Threading.Interlocked?displayProperty=nameWithType>
- [Referencia de C#](../index.md)
- [Palabras clave de C#](index.md)
- [Palabras clave de instrucciones](statement-keywords.md)
- [Operaciones de bloqueo](../../../standard/threading/interlocked-operations.md)
- [Información general sobre las primitivas de sincronización](../../../standard/threading/overview-of-synchronization-primitives.md)