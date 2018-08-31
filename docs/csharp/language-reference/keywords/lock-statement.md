---
title: lock (Instrucción, Referencia de C#)
description: 'La palabra clave lock se usa en el subprocesamiento '
ms.date: 07/20/2015
f1_keywords:
- lock_CSharpKeyword
- lock
helpviewer_keywords:
- lock keyword [C#]
ms.assetid: 656da1a4-707e-4ef6-9c6e-6d13b646af42
ms.openlocfilehash: 6ed46837482642dfd7e1a96cd120fc18023c5e9f
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2018
ms.locfileid: "42931198"
---
# <a name="lock-statement-c-reference"></a>lock (Instrucción, Referencia de C#)

La palabra clave `lock` marca un bloque de instrucciones como una sección crítica. Para ello, obtiene el bloqueo de exclusión mutua para un objeto determinado, ejecuta una instrucción y, después, libera el bloqueo. En el ejemplo siguiente se incluye una instrucción `lock`.

```csharp
class Account
{
    decimal balance;
    private Object thisLock = new Object();

    public void Withdraw(decimal amount)
    {
        lock (thisLock)
        {
            if (amount > balance)
            {
                throw new Exception("Insufficient funds");
            }
            balance -= amount;
        }
    }
}
```

Para obtener más información, vea [Sincronización de subprocesos](../../programming-guide/concepts/threading/thread-synchronization.md).

## <a name="remarks"></a>Comentarios

La palabra clave `lock` garantiza que un subproceso no entra en una sección crítica de código mientras otro subproceso se encuentra en la sección crítica. Si otro subproceso intenta entrar en un código bloqueado, esperará hasta que se libere el objeto.

En la sección [Subprocesamiento](../../programming-guide/concepts/threading/index.md) se describen los subprocesos.

La palabra clave `lock` llama a <xref:System.Threading.Monitor.Enter%2A> al comienzo del bloque y a <xref:System.Threading.Monitor.Exit%2A> al final de este. Se genera <xref:System.Threading.ThreadInterruptedException> si <xref:System.Threading.Thread.Interrupt%2A> interrumpe un subproceso que está esperando para especificar una instrucción `lock`.

En general, evite el bloqueo en un tipo `public` o en instancias que estén fuera del control de su código. Las construcciones comunes `lock (this)`, `lock (typeof (MyType))` y `lock ("myLock")` incumplen esta instrucción:

- `lock (this)` es un problema si la instancia es accesible públicamente.

- `lock (typeof (MyType))` es un problema si `MyType` es accesible públicamente.

- `lock("myLock")` es un problema porque cualquier otro código del proceso que use la misma cadena compartirá el bloqueo.

Se recomienda definir un objeto `private` para bloquear, o una variable de objeto `private static` para proteger los datos comunes a todas las instancias.

No se puede usar la palabra clave [await](await.md) en el cuerpo de una instrucción `lock`.

## <a name="example---threads-without-locking"></a>Ejemplo: subprocesos sin bloquear

En el ejemplo siguiente se muestra un uso simple de los subprocesos sin bloquear en C#:

[!code-csharp[csrefKeywordsFixedLock#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsFixedLock/CS/csrefKeywordsFixedLock.cs#5)]

## <a name="example---threads-using-locking"></a>Ejemplo: subprocesos con bloqueo

En el ejemplo siguiente se usan subprocesos y `lock`. Siempre que la instrucción `lock` esté presente, el bloque de instrucciones será una sección crítica y `balance` nunca se convertirá en un número negativo:

[!code-csharp[csrefKeywordsFixedLock#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsFixedLock/CS/csrefKeywordsFixedLock.cs#6)]

## <a name="c-language-specification"></a>especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

- <xref:System.Reflection.MethodImplAttributes>
- <xref:System.Threading.Mutex>
- <xref:System.Threading.Monitor>
- [Referencia de C#](../../language-reference/index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Subprocesamiento](../../programming-guide/concepts/threading/index.md)
- [Palabras clave de C#](index.md)
- [Palabras clave de instrucciones](statement-keywords.md)
- [Interlocked Operations](../../../standard/threading/interlocked-operations.md) (Operaciones Interlocked)
- [AutoResetEvent](../../../standard/threading/autoresetevent.md)
- [Sincronización de subprocesos](../../programming-guide/concepts/threading/thread-synchronization.md)