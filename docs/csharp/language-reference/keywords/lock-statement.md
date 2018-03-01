---
title: "lock (Instrucción, Referencia de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- lock_CSharpKeyword
- lock
helpviewer_keywords:
- lock keyword [C#]
ms.assetid: 656da1a4-707e-4ef6-9c6e-6d13b646af42
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: eb48c2b1554ad2817406eaef42b4cb336ea46862
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
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
  
-   `lock (this)` es un problema si la instancia es accesible públicamente.  
  
-   `lock (typeof (MyType))` es un problema si `MyType` es accesible públicamente.  
  
-   `lock("myLock")` es un problema porque cualquier otro código del proceso que use la misma cadena compartirá el bloqueo.  
  
 Se recomienda definir un objeto `private` para bloquear, o una variable de objeto `private static` para proteger los datos comunes a todas las instancias.  
  
 No se puede usar la palabra clave [await](../../../csharp/language-reference/keywords/await.md) en el cuerpo de una instrucción `lock`.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra un uso simple de subprocesos sin bloquear en C#.  
  
 [!code-csharp[csrefKeywordsFixedLock#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_1.cs)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usan subprocesos y `lock`. Siempre que la instrucción `lock` esté presente, el bloque de instrucciones será una sección crítica y `balance` nunca se convertirá en un número negativo.  
  
 [!code-csharp[csrefKeywordsFixedLock#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_2.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Reflection.MethodImplAttributes>  
 <xref:System.Threading.Mutex>  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Subprocesamiento](../../programming-guide/concepts/threading/index.md)  
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)  
 [Palabras clave de instrucciones](../../../csharp/language-reference/keywords/statement-keywords.md)  
 <xref:System.Threading.Monitor>  
 [Interlocked Operations](../../../standard/threading/interlocked-operations.md) (Operaciones Interlocked)  
 [AutoResetEvent](../../../standard/threading/autoresetevent.md)  
 [Sincronización de subprocesos](../../programming-guide/concepts/threading/thread-synchronization.md)
