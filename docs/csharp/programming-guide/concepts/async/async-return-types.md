---
title: Tipos de valor devueltos asincrónicos (C#)
description: Obtenga información sobre los tipos de valor devueltos que los métodos asincrónicos pueden tener en C# con ejemplos de código para cada tipo y recursos adicionales.
ms.date: 08/19/2020
ms.assetid: ddb2539c-c898-48c1-ad92-245e4a996df8
ms.openlocfilehash: 71e560ed8ee0cae14da396e5ea2f3ab29611ebab
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811501"
---
# <a name="async-return-types-c"></a>Tipos de valor devueltos asincrónicos (C#)

Los métodos asincrónicos pueden tener los siguientes tipos de valor devuelto:

- <xref:System.Threading.Tasks.Task>, para un método asincrónico que realiza una operación pero no devuelve ningún valor.
- <xref:System.Threading.Tasks.Task%601>, para un método asincrónico que devuelve un valor.
- `void`, para un controlador de eventos.
- A partir de C# 7.0, cualquier tipo que tenga un método `GetAwaiter` accesible. El objeto devuelto por el método `GetAwaiter` debe implementar la interfaz <xref:System.Runtime.CompilerServices.ICriticalNotifyCompletion?displayProperty=nameWithType>.
- A partir C# 8.0, <xref:System.Collections.Generic.IAsyncEnumerable%601>, para un método asincrónico que devuelve una *secuencia asincrónica*.

Para obtener más información sobre los métodos asincrónicos, vea [Programación asincrónica con async y await (C#)](./index.md).

También existen varios tipos que son específicos de las cargas de trabajo de Windows:

- <xref:System.Windows.Threading.DispatcherOperation>: para las operaciones asincrónicas limitadas a Windows.
- <xref:Windows.Foundation.IAsyncAction>: para las acciones asincrónicas en UWP que no devuelven un valor.
- <xref:Windows.Foundation.IAsyncActionWithProgress%601>: para las acciones asincrónicas en UWP que informan del progreso, pero no devuelven un valor.
- <xref:Windows.Foundation.IAsyncOperation%601>: para las operaciones asincrónicas en UWP que devuelven un valor.
- <xref:Windows.Foundation.IAsyncOperationWithProgress%602>: para las operaciones asincrónicas en UWP que informan del progreso y devuelven un valor.

## <a name="task-return-type"></a>Tipo de valor devuelto Task

Los métodos asincrónicos que no contienen una instrucción `return` o que contienen una instrucción `return` que no devuelve un operando tienen normalmente un tipo de valor devuelto de <xref:System.Threading.Tasks.Task>. Dichos métodos devuelven `void` si se ejecutan de manera sincrónica. Si se usa un tipo de valor devuelto <xref:System.Threading.Tasks.Task> para un método asincrónico, un método de llamada puede usar un operador `await` para suspender la finalización del llamador hasta que finalice el método asincrónico llamado.

En el ejemplo siguiente, el método `WaitAndApologizeAsync` no contiene una instrucción `return`, de manera que el método devuelve un objeto <xref:System.Threading.Tasks.Task>. La devolución de `Task` permite que se espere a `WaitAndApologizeAsync`. El tipo <xref:System.Threading.Tasks.Task> no incluye una propiedad `Result` porque no tiene ningún valor devuelto.

:::code language="csharp" source="snippets/async-return-types/async-returns2.cs" id="TaskReturn":::

Se espera a `WaitAndApologizeAsync` mediante una instrucción await en lugar de una expresión await, similar a la instrucción de llamada para un método sincrónico que devuelve void. En este caso, la aplicación de un operador await no genera un valor. Para aclarar la instrucción y la expresión de los términos, consulte la tabla siguiente:

| Tipo de operador await | Ejemplo                                      | Tipo                                   |
|------------|----------------------------------------------|----------------------------------------|
| .  | `await SomeTaskMethodAsync()`                | <xref:System.Threading.Tasks.Task>     |
| Expression | `T result = await SomeTaskMethodAsync<T>();` | <xref:System.Threading.Tasks.Task%601> |

Puede separar la llamada a `WaitAndApologizeAsync` desde la aplicación de un operador await, como muestra el código siguiente. Pero recuerde que una `Task` no tiene una propiedad `Result` y que no se genera ningún valor cuando se aplica un operador await a una `Task`.

El código siguiente separa la llamada del método `WaitAndApologizeAsync` de la espera de la tarea que el método devuelve.

:::code language="csharp" source="snippets/async-return-types/async-returns2a.cs" id="AwaitTask":::

## <a name="tasktresult-return-type"></a>Tipo de valor devuelto Task\<TResult\>

El tipo de valor devuelto <xref:System.Threading.Tasks.Task%601> se usa para un método asincrónico que contiene una instrucción [return](../../../language-reference/keywords/return.md) en la que el operando es `TResult`.

En el ejemplo siguiente, el método `GetLeisureHoursAsync` contiene una instrucción `return` que devuelve un entero. Por tanto, la declaración del método debe tener un tipo de valor devuelto de `Task<int>`. El método asincrónico <xref:System.Threading.Tasks.Task.FromResult%2A> es un marcador de posición para una operación que devuelve una propiedad <xref:System.DateTime.DayOfWeek>.

:::code language="csharp" source="snippets/async-return-types/async-returns1.cs" id="LeisureHours":::

Cuando se llama a `GetLeisureHoursAsync` desde una expresión await en el método `ShowTodaysInfo`, esta recupera el valor entero (el valor de `leisureHours`) que está almacenado en la tarea que devuelve el método `GetLeisureHours`. Para más información sobre las expresiones await, vea [await](../../../language-reference/operators/await.md).

Puede comprender mejor cómo `await` recupera el resultado de `Task<T>` si separa la llamada a `GetLeisureHoursAsync` de la aplicación de `await`, como se muestra en el código siguiente. Una llamada al método `GetLeisureHoursAsync` que no se espera inmediatamente devuelve `Task<int>`, como se podría esperar de la declaración del método. La tarea se asigna a la variable `getLeisureHoursTask` en el ejemplo. Dado que `getLeisureHoursTask` es <xref:System.Threading.Tasks.Task%601>, contiene una propiedad <xref:System.Threading.Tasks.Task%601.Result> de tipo `TResult`. En este caso, `TResult` representa un tipo entero. Cuando `await` se aplica a `getLeisureHoursTask`, la expresión await se evalúa en el contenido de la propiedad <xref:System.Threading.Tasks.Task%601.Result%2A> de `getLeisureHoursTask`. El valor se asigna a la variable `ret`.

> [!IMPORTANT]
> La propiedad <xref:System.Threading.Tasks.Task%601.Result%2A> es una propiedad de bloqueo. Si se intenta acceder a ella antes de que termine su tarea, se bloquea el subproceso que está activo actualmente hasta que finaliza la tarea y el valor está disponible. En la mayoría de los casos, se debe tener acceso al valor usando `await` en lugar de tener acceso directamente a la propiedad.
>
> En el ejemplo anterior se ha recuperado el valor de la propiedad <xref:System.Threading.Tasks.Task%601.Result%2A> para bloquear el subproceso principal de manera que el método `Main` pueda imprimir el mensaje (`message`) en la consola antes de que finalice la aplicación.

:::code language="csharp" source="snippets/async-return-types/async-returns1a.cs" id="StoreTask":::

## <a name="void-return-type"></a>Tipo de valor devuelto Void

Usa el tipo de valor devuelto `void` en controladores de eventos asincrónicos, que necesitan un tipo de valor devuelto `void`. Para métodos que no sean controladores de eventos que no devuelven un valor, debe devolver <xref:System.Threading.Tasks.Task> en su lugar, porque no se espera a un método asincrónico que devuelva `void`. Cualquiera que realice la llamada a este método debe continuar hasta completarse sin esperar a que finalice el método asincrónico que se haya llamado. El autor de la llamada debe ser independiente de los valores o las excepciones que genere el método asincrónico.

El autor de la llamada de un método asincrónico que devuelve void no puede capturar las excepciones iniciadas desde el método y es probable que esas excepciones sin controlar provoquen un error de la aplicación. Si un método que devuelve un valor <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> inicia una excepción, la excepción se almacena en la tarea devuelta. La excepción se vuelve a iniciar cuando se espera a la tarea. Por tanto, asegúrese de que cualquier método asincrónico que puede producir una excepción tiene un tipo de valor devuelto de <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> y que se esperan llamadas al método.

Para obtener más información sobre cómo capturar excepciones en métodos asincrónicos, vea la sección [Excepciones en métodos asincrónicos](../../../language-reference/keywords/try-catch.md#exceptions-in-async-methods) del artículo [try-catch](../../../language-reference/keywords/try-catch.md).

En el ejemplo siguiente se muestra el comportamiento de un controlador de eventos asincrónicos. En el código de ejemplo, un controlador de eventos asincrónicos debe informar al subproceso principal de que ha terminado. Después, el subproceso principal puede esperar a que un controlador de eventos asincrónicos finalice antes de salir del programa.

:::code language="csharp" source="snippets/async-return-types/async-returns3.cs":::

## <a name="generalized-async-return-types-and-valuetasktresult"></a>Tipos de valor devueltos asincrónicos generalizados y ValueTask\<TResult\>

A partir de C# 7.0, un método asincrónico puede devolver cualquier tipo que tenga un método `GetAwaiter` accesible.

Como <xref:System.Threading.Tasks.Task> y <xref:System.Threading.Tasks.Task%601> son tipos de referencia, la asignación de memoria en las rutas críticas para el rendimiento, especialmente cuando las asignaciones se producen en ajustados bucles, puede afectar negativamente al rendimiento. La compatibilidad para los tipos de valor devuelto generalizados significa que puede devolver un tipo de valor ligero en lugar de un tipo de referencia para evitar asignaciones de memoria adicionales.

.NET proporciona la estructura <xref:System.Threading.Tasks.ValueTask%601?displayProperty=nameWithType> como una implementación ligera de un valor de devolución de tareas generalizado. Para usar el tipo <xref:System.Threading.Tasks.ValueTask%601?displayProperty=nameWithType>, debe agregar el paquete NuGet de `System.Threading.Tasks.Extensions` a su proyecto. En el ejemplo siguiente se usa la estructura <xref:System.Threading.Tasks.ValueTask%601> para recuperar el valor de dos tiradas de dado.

:::code language="csharp" source="snippets/async-return-types/async-valuetask.cs":::

## <a name="async-streams-with-iasyncenumerablet"></a>Secuencias asincrónicas con IAsyncEnumerable\<T\>

A partir de C# 8.0, un método asincrónico puede devolver una *secuencia asincrónica*, representada por <xref:System.Collections.Generic.IAsyncEnumerable%601>. Una secuencia asincrónica proporciona una manera de enumerar los elementos leídos de una secuencia cuando se generan elementos en fragmentos con llamadas asincrónicas repetidas. En el ejemplo siguiente se muestra un método asincrónico que genera una secuencia asincrónica:

:::code language="csharp" source="snippets/async-return-types/AsyncStreams.cs" id="GenerateAsyncStream":::

En el ejemplo anterior, las líneas de una cadena se leen de forma asincrónica. Una vez que se ha leído cada línea, el código enumera cada palabra de la cadena. Los autores de la llamada enumerarían cada palabra mediante la instrucción `await foreach`. El método espera cuando necesita leer de forma asincrónica la línea siguiente de la cadena de origen.

## <a name="see-also"></a>Vea también

- <xref:System.Threading.Tasks.Task.FromResult%2A>
- [Procesamiento de tareas asincrónicas a medida que se completan](start-multiple-async-tasks-and-process-them-as-they-complete.md)
- [Programación asincrónica con async y await (C#)](index.md)
- [async](../../../language-reference/keywords/async.md)
- [await](../../../language-reference/operators/await.md)
