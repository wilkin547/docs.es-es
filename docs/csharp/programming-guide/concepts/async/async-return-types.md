---
title: Tipos de valor devueltos asincrónicos (C#)
ms.date: 05/29/2017
ms.assetid: ddb2539c-c898-48c1-ad92-245e4a996df8
ms.openlocfilehash: 9926fea5308f9088ad924bcc98d8deed319c6300
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79170044"
---
# <a name="async-return-types-c"></a>Tipos de valor devueltos asincrónicos (C#)
Los métodos asincrónicos pueden tener los siguientes tipos de valor devuelto:

- <xref:System.Threading.Tasks.Task%601>, para un método asincrónico que devuelve un valor.

- <xref:System.Threading.Tasks.Task>, para un método asincrónico que realiza una operación pero no devuelve ningún valor.

- `void`, para un controlador de eventos.

- A partir de C# 7.0, cualquier tipo que tenga un método `GetAwaiter` accesible. El objeto devuelto por el método `GetAwaiter` debe implementar la interfaz <xref:System.Runtime.CompilerServices.ICriticalNotifyCompletion?displayProperty=nameWithType>.
  
Para más información sobre los métodos async, vea [Programación asincrónica con async y await 8C#)](./index.md).  
  
Cada tipo de valor devuelto se examina en una de las siguientes secciones, y puede encontrar un ejemplo completo que usa los tres tipos al final del tema.  
  
## Tipo de valor devuelto<a name="BKMK_TaskTReturnType"></a> Task\<TResult\>  
El tipo de valor devuelto <xref:System.Threading.Tasks.Task%601> se usa para un método asincrónico que contiene una instrucción [return](../../../language-reference/keywords/return.md) (C#) en la que el operando tiene el tipo `TResult`.  
  
En el ejemplo siguiente, el método asincrónico `GetLeisureHours` contiene una instrucción `return` que devuelve un entero. Por tanto, la declaración del método debe tener un tipo de valor devuelto de `Task<int>`.  El método asincrónico <xref:System.Threading.Tasks.Task.FromResult%2A> es un marcador de posición para una operación que devuelve una cadena.
  
[!code-csharp[return-value](../../../../../samples/snippets/csharp/programming-guide/async/async-returns1.cs)]

Cuando se llama a `GetLeisureHours` desde una expresión await en el método `ShowTodaysInfo`, esta recupera el valor entero (el valor de `leisureHours`) que está almacenado en la tarea que devuelve el método `GetLeisureHours`. Para más información sobre las expresiones await, vea [await](../../../language-reference/operators/await.md).  
  
Comprenderá mejor cómo sucede esto separando la llamada a `GetLeisureHours` de la aplicación de `await`, como se muestra en el código siguiente. Una llamada al método `GetLeisureHours` que no se espera inmediatamente devuelve `Task<int>`, como se podría esperar de la declaración del método. La tarea se asigna a la variable `integerTask` en el ejemplo. Dado que `integerTask` es <xref:System.Threading.Tasks.Task%601>, contiene una propiedad <xref:System.Threading.Tasks.Task%601.Result> de tipo `TResult`. En este caso, `TResult` representa un tipo entero. Cuando `await` se aplica a `integerTask`, la expresión await se evalúa en el contenido de la propiedad <xref:System.Threading.Tasks.Task%601.Result%2A> de `integerTask`. El valor se asigna a la variable `ret`.  
  
> [!IMPORTANT]
> La propiedad <xref:System.Threading.Tasks.Task%601.Result%2A> es una propiedad de bloqueo. Si se intenta acceder a ella antes de que termine su tarea, se bloquea el subproceso que está activo actualmente hasta que finaliza la tarea y el valor está disponible. En la mayoría de los casos, se debe tener acceso al valor usando `await` en lugar de tener acceso directamente a la propiedad. <br/> En el ejemplo anterior se ha recuperado el valor de la propiedad <xref:System.Threading.Tasks.Task%601.Result%2A> para bloquear el subproceso principal de manera que el método `ShowTodaysInfo` pueda terminar la ejecución antes de que finalice la aplicación.  

[!code-csharp[return-value](../../../../../samples/snippets/csharp/programming-guide/async/async-returns1a.cs#1)]
  
## <a name="BKMK_TaskReturnType"></a> Tipo de valor devuelto Task  
Los métodos asincrónicos que no contienen una instrucción `return` o que contienen una instrucción `return` que no devuelve un operando tienen normalmente un tipo de valor devuelto de <xref:System.Threading.Tasks.Task>. Dichos métodos devuelven `void` si se ejecutan de manera sincrónica. Si se usa un tipo de valor devuelto <xref:System.Threading.Tasks.Task> para un método asincrónico, un método de llamada puede usar un operador `await` para suspender la finalización del llamador hasta que finalice el método asincrónico llamado.  
  
En el ejemplo siguiente, el método asincrónico `WaitAndApologize` no contiene una instrucción `return`, de manera que el método devuelve un objeto <xref:System.Threading.Tasks.Task>. Esto permite que se espere a `WaitAndApologize`. Tenga en cuenta que el tipo <xref:System.Threading.Tasks.Task> no incluye una propiedad `Result` porque no tiene ningún valor devuelto.  

[!code-csharp[return-value](../../../../../samples/snippets/csharp/programming-guide/async/async-returns2.cs)]  
  
Se espera a `WaitAndApologize` mediante una instrucción await en lugar de una expresión await, similar a la instrucción de llamada para un método sincrónico que devuelve void. En este caso, la aplicación de un operador await no genera un valor.  
  
Igual que en el ejemplo <xref:System.Threading.Tasks.Task%601> anterior, puede separar la llamada a `WaitAndApologize` desde la aplicación de un operador await, como muestra el código siguiente. Pero recuerde que una `Task` no tiene una propiedad `Result` y que no se genera ningún valor cuando se aplica un operador await a una `Task`.  
  
El código siguiente separa la llamada del método `WaitAndApologize` de la espera de la tarea que el método devuelve.  

[!code-csharp[return-value](../../../../../samples/snippets/csharp/programming-guide/async/async-returns2a.cs#1)]  

## <a name="BKMK_VoidReturnType"></a> Tipo de valor devuelto Void

Usa el tipo de valor devuelto `void` en controladores de eventos asincrónicos, que necesitan un tipo de valor devuelto `void`. Para métodos que no sean controladores de eventos que no devuelven un valor, debe devolver <xref:System.Threading.Tasks.Task> en su lugar, porque no se espera a un método asincrónico que devuelva `void`. Cualquier llamador de este método debe poder continuar hasta completarse sin esperar a que finalice el método asincrónico llamado y el llamador debe ser independiente de los valores o las excepciones que genera el método asincrónico.  
  
El llamador de un método asincrónico que devuelve void no puede capturar las excepciones emitidas desde el método y dichas excepciones no controladas pueden provocar un error de la aplicación. Si se produce una excepción en un método asincrónico que devuelve <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>, la excepción se almacena en la tarea devuelta y se vuelve a emitir cuando se espera la tarea. Por tanto, asegúrese de que cualquier método asincrónico que puede producir una excepción tiene un tipo de valor devuelto de <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> y que se esperan llamadas al método.  
  
Para obtener más información sobre cómo capturar excepciones en métodos asincrónicos, vea la sección [Excepciones en métodos asincrónicos](../../../language-reference/keywords/try-catch.md#exceptions-in-async-methods) del tema [try-catch](../../../language-reference/keywords/try-catch.md).  
  
En el ejemplo siguiente se muestra el comportamiento de un controlador de eventos asincrónicos. Tenga en cuenta que en el código de ejemplo, un controlador de eventos asincrónicos debe informar de que ha terminado al subproceso principal. Después, el subproceso principal puede esperar a que un controlador de eventos asincrónicos finalice antes de salir del programa.

[!code-csharp[return-value](../../../../../samples/snippets/csharp/programming-guide/async/async-returns3.cs)]  

## <a name="generalized-async-return-types-and-valuetasktresult"></a>Tipos de valor devueltos asincrónicos generalizados y ValueTask\<TResult\>

A partir de C# 7.0, un método asincrónico puede devolver cualquier tipo que tenga un método `GetAwaiter` accesible.

Como <xref:System.Threading.Tasks.Task> y <xref:System.Threading.Tasks.Task%601> son tipos de referencia, la asignación de memoria en las rutas críticas para el rendimiento, especialmente cuando las asignaciones se producen en ajustados bucles, puede afectar negativamente al rendimiento. La compatibilidad para los tipos de valor devuelto generalizados significa que puede devolver un tipo de valor ligero en lugar de un tipo de referencia para evitar asignaciones de memoria adicionales.

.NET proporciona la estructura <xref:System.Threading.Tasks.ValueTask%601?displayProperty=nameWithType> como una implementación ligera de un valor de devolución de tareas generalizado. Para usar el tipo <xref:System.Threading.Tasks.ValueTask%601?displayProperty=nameWithType>, debe agregar el paquete NuGet de `System.Threading.Tasks.Extensions` a su proyecto. En el ejemplo siguiente se usa la estructura <xref:System.Threading.Tasks.ValueTask%601> para recuperar el valor de dos tiradas de dado.
  
[!code-csharp[return-value](../../../../../samples/snippets/csharp/programming-guide/async/async-valuetask.cs)]

## <a name="see-also"></a>Vea también

- <xref:System.Threading.Tasks.Task.FromResult%2A>
- [Walkthrough: Accessing the Web by Using async and await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md) (Tutorial: Acceso a web usando Async y Await [C#])
- [Control Flow in Async Programs (C#)](./control-flow-in-async-programs.md) (Flujo de control en programas asincrónicos [C#])
- [async](../../../language-reference/keywords/async.md)
- [await](../../../language-reference/operators/await.md)
