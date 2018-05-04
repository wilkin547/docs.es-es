---
title: Tipos de valor devueltos asincrónicos (C#)
ms.custom: ''
ms.date: 05/29/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.topic: article
ms.assetid: ddb2539c-c898-48c1-ad92-245e4a996df8
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4927d6324b6bda5a897ce81928fc13cae303a99a
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="async-return-types-c"></a>Tipos de valor devueltos asincrónicos (C#)
Los métodos asincrónicos pueden tener los siguientes tipos de valor devuelto:

- <xref:System.Threading.Tasks.Task%601>, para un método asincrónico que devuelve un valor. 
 
-  <xref:System.Threading.Tasks.Task>, para un método asincrónico que realiza una operación pero no devuelve ningún valor.

- `void`, para un controlador de eventos. 

- A partir de C# 7.0, cualquier tipo que tenga un método `GetAwaiter` accesible. El objeto devuelto por el método `GetAwaiter` debe implementar la interfaz <xref:System.Runtime.CompilerServices.ICriticalNotifyCompletion?displayProperty=nameWithType>.
  
Para más información sobre los métodos async, vea [Programación asincrónica con async y await 8C#)](../../../../csharp/programming-guide/concepts/async/index.md).  
  
Cada tipo de valor devuelto se examina en una de las siguientes secciones, y puede encontrar un ejemplo completo que usa los tres tipos al final del tema.  
  
##  <a name="BKMK_TaskTReturnType"></a> Tipo de valor devuelto Task(T)  
El tipo de valor devuelto <xref:System.Threading.Tasks.Task%601> se usa para un método asincrónico que contiene una instrucción [return](../../../../csharp/language-reference/keywords/return.md) (C#) en la que el operando tiene el tipo `TResult`.  
  
En el ejemplo siguiente, el método asincrónico `GetLeisureHours` contiene una instrucción `return` que devuelve un entero. Por tanto, la declaración del método debe tener un tipo de valor devuelto de `Task<int>`.  El método asincrónico <xref:System.Threading.Tasks.Task.FromResult%2A> es un marcador de posición para una operación que devuelve una cadena.
  
[!code-csharp[return-value](../../../../../samples/snippets/csharp/programming-guide/async/async-returns1.cs)]

Cuando se llama a `GetLeisureHours` desde una expresión await en el método `ShowTodaysInfo`, esta recupera el valor entero (el valor de `leisureHours`) que está almacenado en la tarea que devuelve el método `GetLeisureHours`. Para más información sobre las expresiones await, vea [await](../../../../csharp/language-reference/keywords/await.md).  
  
Comprenderá mejor cómo sucede esto separando la llamada a `GetLeisureHours` de la aplicación de `await`, como se muestra en el código siguiente. Una llamada al método `TaskOfT_MethodAsync` que no se espera inmediatamente devuelve `Task<int>`, como se podría esperar de la declaración del método. La tarea se asigna a la variable `integerTask` en el ejemplo. Dado que `integerTask` es <xref:System.Threading.Tasks.Task%601>, contiene una propiedad <xref:System.Threading.Tasks.Task%601.Result> de tipo `TResult`. En este caso, TResult representa un tipo entero. Cuando `await` se aplica a `integerTask`, la expresión await se evalúa en el contenido de la propiedad <xref:System.Threading.Tasks.Task%601.Result%2A> de `integerTask`. El valor se asigna a la variable `result2`.  
  
> [!IMPORTANT]
>  La propiedad <xref:System.Threading.Tasks.Task%601.Result%2A> es una propiedad de bloqueo. Si se intenta acceder a ella antes de que termine su tarea, se bloquea el subproceso que está activo actualmente hasta que finaliza la tarea y el valor está disponible. En la mayoría de los casos, se debe tener acceso al valor usando `await` en lugar de tener acceso directamente a la propiedad. <br/> En el ejemplo anterior se ha recuperado el valor de la propiedad <xref:System.Threading.Tasks.Task%601.Result%2A> para bloquear el subproceso principal de manera que el método `ShowTodaysInfo` pueda terminar la ejecución antes de que finalice la aplicación.  

[!code-csharp[return-value](../../../../../samples/snippets/csharp/programming-guide/async/async-returns1a.cs#1)]
  
##  <a name="BKMK_TaskReturnType"></a> Tipo de valor devuelto Task  
Los métodos asincrónicos que no contienen una instrucción `return` o que contienen una instrucción `return` que no devuelve un operando tienen normalmente un tipo de valor devuelto de <xref:System.Threading.Tasks.Task>. Dichos métodos devuelven `void` si se ejecutan de manera sincrónica. Si se usa un tipo de valor devuelto <xref:System.Threading.Tasks.Task> para un método asincrónico, un método de llamada puede usar un operador `await` para suspender la finalización del llamador hasta que finalice el método asincrónico llamado.  
  
En el ejemplo siguiente, el método asincrónico `WaitAndApologize` no contiene una instrucción `return`, de manera que el método devuelve un objeto <xref:System.Threading.Tasks.Task>. Esto permite que se espere a `WaitAndApologize`. Tenga en cuenta que el tipo <xref:System.Threading.Tasks.Task> no incluye una propiedad `Result` porque no tiene ningún valor devuelto.  

[!code-csharp[return-value](../../../../../samples/snippets/csharp/programming-guide/async/async-returns2.cs)]  
  
Se espera a `WaitAndApologize` mediante una instrucción await en lugar de una expresión await, similar a la instrucción de llamada para un método sincrónico que devuelve void. En este caso, la aplicación de un operador await no genera un valor.  
  
Igual que en el ejemplo <xref:System.Threading.Tasks.Task%601> anterior, puede separar la llamada a `Task_MethodAsync` desde la aplicación de un operador await, como muestra el código siguiente. Pero recuerde que una `Task` no tiene una propiedad `Result` y que no se genera ningún valor cuando se aplica un operador await a una `Task`.  
  
El código siguiente separa la llamada del método `WaitAndApologize` de la espera de la tarea que el método devuelve.  
 
[!code-csharp[return-value](../../../../../samples/snippets/csharp/programming-guide/async/async-returns2a.cs#1)]  
 
##  <a name="BKMK_VoidReturnType"></a> Tipo de valor devuelto Void  
Usa el tipo de valor devuelto `void` en controladores de eventos asincrónicos, que necesitan un tipo de valor devuelto `void`. Para métodos distintos en los que los controladores de eventos no devuelven un valor, debe devolver <xref:System.Threading.Tasks.Task> en su lugar, porque no se espera a un método asincrónico que devuelve `void`. Cualquier llamador de este método debe poder continuar hasta completarse sin esperar a que finalice el método asincrónico llamado y el llamador debe ser independiente de los valores o las excepciones que genera el método asincrónico.  
  
El llamador de un método asincrónico que devuelve void no puede capturar las excepciones emitidas desde el método y dichas excepciones no controladas pueden provocar un error de la aplicación. Si se produce una excepción en un método asincrónico que devuelve <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>, la excepción se almacena en la tarea devuelta y se vuelve a emitir cuando se espera la tarea. Por tanto, asegúrese de que cualquier método asincrónico que puede producir una excepción tiene un tipo de valor devuelto de <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> y que se esperan llamadas al método.  
  
Para más información sobre cómo capturar excepciones en métodos asincrónicos, vea [try-catch](../../../../csharp/language-reference/keywords/try-catch.md).  
  
El ejemplo siguiente define un controlador de eventos asincrónico.  
 
[!code-csharp[return-value](../../../../../samples/snippets/csharp/programming-guide/async/async-returns3.cs)]  
 
## <a name="generalized-async-return-types-and-valuetaskt"></a>Tipos de valor devueltos asincrónicos generalizados y ValueTask<T>

A partir de C# 7.0, un método asincrónico puede devolver cualquier tipo que tenga un método `GetAwaiter` accesible.
 
Como <xref:System.Threading.Tasks.Task> y <xref:System.Threading.Tasks.Task%601> son tipos de referencia, la asignación de memoria en las rutas críticas para el rendimiento, especialmente cuando las asignaciones se producen en ajustados bucles, puede afectar negativamente al rendimiento. La compatibilidad para los tipos de valor devuelto generalizados significa que puede devolver un tipo de valor ligero en lugar de un tipo de referencia para evitar asignaciones de memoria adicionales. 

.NET proporciona la estructura <xref:System.Threading.Tasks.ValueTask%601?displayProperty=nameWithType> como una implementación ligera de un valor de devolución de tareas generalizado. Para usar el tipo <xref:System.Threading.Tasks.ValueTask%601?displayProperty=nameWithType>, debe agregar el paquete NuGet de `System.Threading.Tasks.Extensions` a su proyecto. En el ejemplo siguiente se usa la estructura <xref:System.Threading.Tasks.ValueTask%601> para recuperar el valor de dos tiradas de dado. 
  
[!code-csharp[return-value](../../../../../samples/snippets/csharp/programming-guide/async/async-valuetask.cs)]

## <a name="see-also"></a>Vea también  
<xref:System.Threading.Tasks.Task.FromResult%2A>   
[Walkthrough: Accessing the Web by Using async and await (C#)](../../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)  (Tutorial: Acceso a la web usando async y await (C#))  
[Controlar el flujo en los programas asincrónicos (C#)](../../../../csharp/programming-guide/concepts/async/control-flow-in-async-programs.md)   
[async](../../../../csharp/language-reference/keywords/async.md)   
[await](../../../../csharp/language-reference/keywords/await.md)
