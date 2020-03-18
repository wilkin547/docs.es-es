---
title: 'Cómo: Escribir un bucle Parallel.For con variables locales de subproceso'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel for loops, how to use local state
ms.assetid: 68384064-7ee7-41e2-90e3-71f00bde01bb
ms.openlocfilehash: 14f4f1402f564d38bb508e893521a3951c1509f4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73139714"
---
# <a name="how-to-write-a-parallelfor-loop-with-thread-local-variables"></a>Cómo: Escribir un bucle Parallel.For con variables locales de subproceso
En este ejemplo se muestra la forma de usar variables locales para el subproceso para almacenar y recuperar el estado en cada una de las tareas independientes creadas por un bucle <xref:System.Threading.Tasks.Parallel.For%2A>. Mediante el uso de datos locales de subproceso, se puede evitar la sobrecarga que supone la sincronización de un gran número de accesos a un estado compartido. En vez de escribir en un recurso compartido en cada iteración, se calcula y se almacena el valor hasta que finalizan todas las iteraciones de la tarea. A continuación, se escribe una vez el resultado final en el recurso compartido o se pasa a otro método.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se llama al método <xref:System.Threading.Tasks.Parallel.For%60%601%28System.Int32%2CSystem.Int32%2CSystem.Func%7B%60%600%7D%2CSystem.Func%7BSystem.Int32%2CSystem.Threading.Tasks.ParallelLoopState%2C%60%600%2C%60%600%7D%2CSystem.Action%7B%60%600%7D%29> para calcular la suma de los valores de una matriz que contiene un millón de elementos. El valor de cada elemento es igual a su índice.  
  
 [!code-csharp[TPL_Parallel#05](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/forandforeach_simple.cs#05)]
 [!code-vb[TPL_Parallel#05](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/forwiththreadlocal.vb#05)]  
  
 Los dos primeros parámetros de cada método <xref:System.Threading.Tasks.Parallel.For%2A> especifican los valores de iteración inicial y final. En esta sobrecarga del método, el tercer parámetro es donde se inicializa el estado local. En este contexto, estado local significa una variable cuya duración se extiende desde justo antes de la primera iteración del bucle en el subproceso actual, hasta justo después de la última iteración.  
  
 El tipo del tercer parámetro es <xref:System.Func%601>, donde `TResult` es el tipo de la variable que almacenará el estado local de subproceso. Su tipo se define mediante el argumento de tipo genérico que se proporciona al llamar al método <xref:System.Threading.Tasks.Parallel.For%60%601%28System.Int32%2CSystem.Int32%2CSystem.Func%7B%60%600%7D%2CSystem.Func%7BSystem.Int32%2CSystem.Threading.Tasks.ParallelLoopState%2C%60%600%2C%60%600%7D%2CSystem.Action%7B%60%600%7D%29> genérico, que en este caso es <xref:System.Int64>. El argumento de tipo le indica al compilador el tipo de variable temporal que se usará para almacenar el estado local de subproceso. En este ejemplo, la expresión `() => 0` (o `Function() 0` en Visual Basic) inicializa la variable local de subproceso en cero. Si el argumento de tipo genérico es un tipo de referencia o un tipo de valor definido por el usuario, la expresión tendrá el aspecto siguiente:  
  
```csharp  
() => new MyClass()  
```  
  
```vb  
Function() new MyClass()  
```  
  
 El cuarto parámetro define la lógica del bucle y debe ser un delegado o una expresión lambda cuya firma sea `Func<int, ParallelLoopState, long, long>` en C# o `Func(Of Integer, ParallelLoopState, Long, Long)` en Visual Basic. El primer parámetro es el valor del contador de bucle correspondiente a esa iteración del bucle. El segundo es un objeto <xref:System.Threading.Tasks.ParallelLoopState> que se puede usar para desglosar el bucle; la clase <xref:System.Threading.Tasks.Parallel> proporciona este objeto a cada repetición del bucle. El tercer parámetro es la variable local de subproceso. El último parámetro es el tipo de valor devuelto. En este caso, el tipo es <xref:System.Int64> porque es el que se especificó en el argumento de tipo <xref:System.Threading.Tasks.Parallel.For%2A>. Esa variable se denomina `subtotal` y la devuelve la expresión lambda. El valor devuelto se usa para inicializar `subtotal` en todas las iteraciones posteriores del bucle. Este último parámetro también se puede considerar como un valor que se pasa a todas las iteraciones y que, cuando finaliza la última iteración, se pasa al delegado `localFinally`.  
  
 El quinto parámetro define el método que se llama una vez, después de que se hayan completado todas las iteraciones de un subproceso en particular. El tipo del argumento de entrada se corresponde de nuevo con el argumento de tipo del método <xref:System.Threading.Tasks.Parallel.For%60%601%28System.Int32%2CSystem.Int32%2CSystem.Func%7B%60%600%7D%2CSystem.Func%7BSystem.Int32%2CSystem.Threading.Tasks.ParallelLoopState%2C%60%600%2C%60%600%7D%2CSystem.Action%7B%60%600%7D%29> y el tipo devuelto por la expresión lambda del cuerpo. En este ejemplo, el valor se agrega a una variable en el ámbito de clase de un modo seguro para subprocesos mediante una llamada al método <xref:System.Threading.Interlocked.Add%2A?displayProperty=nameWithType>. Gracias a la variable local de subproceso, se ha evitado el tener que escribir en esta variable de clase en cada iteración del bucle.  
  
 Para obtener más información sobre cómo usar las expresiones lambda, vea [Expresiones lambda en PLINQ y TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).  
  
## <a name="see-also"></a>Vea también

- [Data Parallelism](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md) (Paralelismo de datos)
- [Programación en paralelo](../../../docs/standard/parallel-programming/index.md)
- [Biblioteca TPL](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)
- [Expresiones lambda en PLINQ y TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
