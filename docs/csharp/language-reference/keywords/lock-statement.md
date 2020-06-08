---
title: 'Instrucción lock: Referencia de C#'
description: Use la instrucción lock de C# para sincronizar el acceso de un subproceso al recurso compartido
ms.date: 04/02/2020
f1_keywords:
- lock_CSharpKeyword
- lock
helpviewer_keywords:
- lock keyword [C#]
ms.assetid: 656da1a4-707e-4ef6-9c6e-6d13b646af42
ms.openlocfilehash: 6e9a6975977588ba7692c925d7940cd2ec26671f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406695"
---
# <a name="lock-statement-c-reference"></a>Instrucción lock (Referencia de C#)

La instrucción `lock` adquiere el bloqueo de exclusión mutua de un objeto determinado, ejecuta un bloque de instrucciones y luego libera el bloqueo. Mientras se mantiene un bloqueo, el subproceso que lo mantiene puede volver a adquirir y liberar el bloqueo. Ningún otro subproceso puede adquirir el bloqueo y espera hasta que se libera.

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

No se puede usar el operador [await](../operators/await.md) en el cuerpo de una instrucción `lock`.

## <a name="guidelines"></a>Instrucciones

Al sincronizar el acceso del subproceso al recurso compartido, bloquee una instancia dedicada de objeto (por ejemplo, `private readonly object balanceLock = new object();`) u otra instancia cuyo empleo como objeto de bloqueo sea poco probable por parte de elementos no relacionados del código. Evite el uso de la misma instancia de objeto de bloqueo para distintos recursos compartidos, ya que se podría producir un interbloqueo o una contención de bloqueo. En particular, evite utilizar lo siguiente como objetos de bloqueo:

- `this`, porque los autores de llamadas podrían usarlo como un bloqueo.
- Instancias <xref:System.Type>, porque el operador o la reflexión [typeof](../operators/type-testing-and-cast.md#typeof-operator) podrían obtenerlas.
- Instancias de cadena, incluidos literales de cadena, porque podrían [internarse](/dotnet/api/system.string.intern#remarks).

Mantenga el bloqueo durante el menor tiempo posible para reducir la contención de bloqueo.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se define una clase `Account` que sincroniza el acceso a su campo privado `balance` mediante el bloqueo de una instancia dedicada `balanceLock`. El empleo de la misma instancia para bloquear garantiza que el campo `balance` no sea actualizado al mismo tiempo por dos subprocesos que intentan llamar a los métodos `Debit` o `Credit` simultáneamente.

[!code-csharp[lock-statement-example](snippets/LockStatementExample.cs)]

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, consulte la sección sobre la [instrucción lock](~/_csharplang/spec/statements.md#the-lock-statement) de la [especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Palabras clave de C#](index.md)
- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.SpinLock?displayProperty=nameWithType>
- <xref:System.Threading.Interlocked?displayProperty=nameWithType>
- [Información general sobre las primitivas de sincronización](../../../standard/threading/overview-of-synchronization-primitives.md)
