---
title: Implementar el modelo asincrónico basado en tareas
ms.date: 06/14/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- .NET Framework, and TAP
- asynchronous design patterns, .NET Framework
- TAP, .NET Framework support for
- Task-based Asynchronous Pattern, .NET Framework support for
- .NET Framework, asynchronous design patterns
ms.assetid: fab6bd41-91bd-44ad-86f9-d8319988aa78
ms.openlocfilehash: 6218aa1a7b813601e9b718abf862e20a7cbcd313
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124297"
---
# <a name="implementing-the-task-based-asynchronous-pattern"></a>Implementar el modelo asincrónico basado en tareas
Puede implementar el patrón asincrónico basado en tareas (TAP) de tres maneras: mediante los compiladores de C# y Visual Basic en Visual Studio, manualmente o mediante una combinación del compilador y métodos manuales. En las siguientes secciones se describe cada método con detalle. Puede usar el modelo TAP para implementar operaciones asincrónicas enlazadas a cálculos y enlazadas a E/S. En la sección [Cargas de trabajo](#workloads) se trata cada tipo de operación.

## <a name="generating-tap-methods"></a>Generación de métodos TAP

### <a name="using-the-compilers"></a>Uso de compiladores
A partir de .NET Framework 4.5, cualquier método que tenga la palabra clave `async` (`Async` en Visual Basic) se considera un método asincrónico, y los compiladores de C# y Visual Basic realizan las transformaciones necesarias para implementar el método de forma asincrónica mediante TAP. Un método asincrónico debe devolver un objeto <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> o <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>. En el último caso, el cuerpo de la función debe devolver `TResult` y el compilador garantiza que este resultado está disponible a través del objeto de la tarea resultante. Del mismo modo, en la tarea de salida se calculan las referencias de cualquier excepción no controlada dentro del cuerpo del método y esto hace que la tarea resultante finalice en el estado <xref:System.Threading.Tasks.TaskStatus.Faulted?displayProperty=nameWithType>. La excepción es cuando un objeto <xref:System.OperationCanceledException> (o un tipo derivado) no está controlado, en cuyo caso la tarea resultante finaliza en el estado <xref:System.Threading.Tasks.TaskStatus.Canceled?displayProperty=nameWithType>.

### <a name="generating-tap-methods-manually"></a>Generar métodos de TAP manualmente
Puede implementar el patrón TAP manualmente para tener un mejor control sobre la implementación. El compilador se basa en el área de superficie pública expuesta del espacio de nombres <xref:System.Threading.Tasks?displayProperty=nameWithType> y los tipos auxiliares del espacio de nombres <xref:System.Runtime.CompilerServices?displayProperty=nameWithType>. Para implementar TAP, cree un objeto <xref:System.Threading.Tasks.TaskCompletionSource%601>, realice la operación asincrónica y, cuando se complete, llame al método <xref:System.Threading.Tasks.TaskCompletionSource%601.SetResult%2A>, <xref:System.Threading.Tasks.TaskCompletionSource%601.SetException%2A> o <xref:System.Threading.Tasks.TaskCompletionSource%601.SetCanceled%2A>, o a la versión `Try` de uno de estos métodos. Cuando implementa un método de TAP manualmente, debe completar la tarea resultante cuando la operación asincrónica representada se complete. Por ejemplo:

[!code-csharp[Conceptual.TAP_Patterns#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.tap_patterns/cs/patterns1.cs#1)]
[!code-vb[Conceptual.TAP_Patterns#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.tap_patterns/vb/patterns1.vb#1)]

### <a name="hybrid-approach"></a>Enfoque híbrido
 Puede resultar útil implementar el patrón TAP manualmente pero delegar la lógica básica de la implementación en el compilador. Por ejemplo, quizás desee usar el enfoque híbrido para comprobar argumentos fuera de un método asincrónico generado por el compilador de forma que las excepciones puedan salir del llamador directo del método en lugar de exponerse a través del objeto <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>:

 [!code-csharp[Conceptual.TAP_Patterns#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.tap_patterns/cs/patterns1.cs#2)]
 [!code-vb[Conceptual.TAP_Patterns#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.tap_patterns/vb/patterns1.vb#2)]

 Otro caso donde es útil esa delegación es cuando implementa la optimización de acceso rápido y desea devolver una tarea almacenada en memoria caché.

## <a name="workloads"></a>Cargas de trabajo
Puede implementar operaciones asincrónicas enlazadas a cálculos y enlazadas a E/S como métodos de TAP. Sin embargo, cuando los métodos de TAP se exponen públicamente desde una biblioteca, solo se deben suministrar para cargas de trabajo que impliquen operaciones enlazadas a E/S (también pueden implicar cálculos, pero no deben ser estrictamente de cálculo). Si un método está totalmente enlazado a cálculos, se debe exponer solo como una implementación sincrónica. El código que lo usa puede elegir si ajustar una invocación de ese método sincrónico en una tarea para descargar el trabajo en otro subproceso o para lograr el paralelismo. Si un método está enlazado a E/S, se debe exponer solo como una implementación asincrónica.

### <a name="compute-bound-tasks"></a>Tareas enlazadas a cálculos
La clase <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> es idónea para representar operaciones de cálculo intensivas. De forma predeterminada, se beneficia de la compatibilidad especial dentro de la clase <xref:System.Threading.ThreadPool> para proporcionar una ejecución eficaz, y también proporciona un buen control sobre cuándo, dónde y cómo se ejecutan los cálculos asincrónicos.

Puede generar tareas enlazadas a cálculos de las maneras siguientes:

- En .NET Framework 4, use el método <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType>, que acepta un delegado (normalmente <xref:System.Action%601> o <xref:System.Func%601>) que se va a ejecutar de forma asincrónica. Si proporciona un delegado de <xref:System.Action%601>, el método devuelve un objeto <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> que representa la ejecución asincrónica de ese delegado. Si proporciona un delegado de <xref:System.Func%601>, el método devuelve un objeto <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>. Las sobrecargas del método <xref:System.Threading.Tasks.TaskFactory.StartNew%2A> aceptan un token de cancelación (<xref:System.Threading.CancellationToken>), las opciones de creación de la tarea (<xref:System.Threading.Tasks.TaskCreationOptions>) y un programador de tareas (<xref:System.Threading.Tasks.TaskScheduler>), todo lo cual proporciona un control específico sobre la programación y la ejecución de la tarea. Una instancia de generador que tiene como destino el programador de tareas actual está disponible como una propiedad estática (<xref:System.Threading.Tasks.Task.Factory%2A>) de la clase <xref:System.Threading.Tasks.Task>; por ejemplo: `Task.Factory.StartNew(…)`.

- En .NET Framework 4.5 y versiones posteriores (incluidos .NET Core y .NET Standard), use el método <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> estático como un acceso directo a <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType>. Puede usar <xref:System.Threading.Tasks.Task.Run%2A> para iniciar fácilmente una tarea enlazada a cálculos destinada al grupo de subprocesos. En .NET Framework 4.5 y versiones posteriores, este es el mecanismo preferido para iniciar una tarea enlazada a procesos. Use `StartNew` directamente solo cuando desee un mayor control sobre la tarea.

- Use los constructores del tipo `Task` o el método `Start` si desea generar y programar la tarea por separado. Los métodos públicos solo deben devolver tareas que ya se han iniciado.

- Use las sobrecargas del método <xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=nameWithType>. Este método crea una nueva tarea que se programa cuando se completa otra tarea. Algunas de las sobrecargas de <xref:System.Threading.Tasks.Task.ContinueWith%2A> aceptan un token de cancelación, opciones de continuación y un programador de tareas para tener un mejor control sobre la programación y la ejecución de la tarea de continuación.

- Use los métodos <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A?displayProperty=nameWithType> y <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAny%2A?displayProperty=nameWithType>. Estos métodos crean una nueva tarea que se programa cuando se completa una parte o la totalidad del conjunto de tareas proporcionado. Estos métodos también proporcionan sobrecargas para controlar la programación y la ejecución de estas tareas.

En las tareas enlazadas a cálculos, el sistema puede evitar la ejecución de una tarea programada si recibe una solicitud de cancelación antes de que comience la ejecución de la tarea. Por tanto, si proporciona un token de cancelación (objeto <xref:System.Threading.CancellationToken>), puede pasar ese token al código asincrónico que lo supervisa. También puede proporcionar el token a uno de los métodos mencionados previamente, como `StartNew` o `Run`, para que el runtime de `Task` también supervise el token.

Por ejemplo, considere un método asincrónico que presenta una imagen. El cuerpo de la tarea puede sondear el token de cancelación para que el código pueda salir pronto si llega una solicitud de cancelación durante la representación. Además, si la solicitud de cancelación llega antes de que se inicie la representación, deseará evitar la operación de representación:

[!code-csharp[Conceptual.TAP_Patterns#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.tap_patterns/cs/patterns1.cs#3)]
[!code-vb[Conceptual.TAP_Patterns#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.tap_patterns/vb/patterns1.vb#3)]

Las tareas enlazadas a cálculos finalizan en un estado <xref:System.Threading.Tasks.TaskStatus.Canceled> si se cumple al menos una de las condiciones siguientes:

- Llega una solicitud de cancelación a través del objeto <xref:System.Threading.CancellationToken>, que se proporciona como argumento al método de creación (por ejemplo, `StartNew` o `Run`) antes de que la tarea cambie al estado <xref:System.Threading.Tasks.TaskStatus.Running>.

- Una excepción <xref:System.OperationCanceledException> no está controlada dentro del cuerpo de esta tarea, esa excepción contiene el mismo objeto <xref:System.Threading.CancellationToken> que se pasa a la tarea y ese token muestra que se solicitó la cancelación.

Si hay otra excepción no controlada en el cuerpo de la tarea, la tarea finaliza en el estado <xref:System.Threading.Tasks.TaskStatus.Faulted> y cualquier intento de esperar en la tarea u obtener acceso a su resultado produce una excepción.

### <a name="io-bound-tasks"></a>Tareas enlazadas a E/S
Para crear una tarea a la que no deba respaldar directamente un subproceso durante toda su ejecución, use el tipo <xref:System.Threading.Tasks.TaskCompletionSource%601>. Este tipo expone una propiedad <xref:System.Threading.Tasks.TaskCompletionSource%601.Task%2A> que devuelve una instancia asociada de <xref:System.Threading.Tasks.Task%601>. El ciclo de vida de esta tarea se controla mediante métodos <xref:System.Threading.Tasks.TaskCompletionSource%601> como <xref:System.Threading.Tasks.TaskCompletionSource%601.SetResult%2A>, <xref:System.Threading.Tasks.TaskCompletionSource%601.SetException%2A>, <xref:System.Threading.Tasks.TaskCompletionSource%601.SetCanceled%2A> y sus variantes de `TrySet`.

Suponga que desea crear una tarea que se completará después de un período de tiempo especificado. Por ejemplo, puede que desee retrasar una actividad en la interfaz de usuario. La clase <xref:System.Threading.Timer?displayProperty=nameWithType> ya proporciona la capacidad de invocar de forma asincrónica un delegado después de un período de tiempo especificado, y <xref:System.Threading.Tasks.TaskCompletionSource%601> le permite colocar un objeto <xref:System.Threading.Tasks.Task%601> delante del temporizador, por ejemplo:

[!code-csharp[Conceptual.TAP_Patterns#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.tap_patterns/cs/patterns1.cs#4)]
[!code-vb[Conceptual.TAP_Patterns#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.tap_patterns/vb/patterns1.vb#4)]

A partir de .NET Framework 4.5, el método <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> se proporciona con este propósito y puede usarlo dentro de otro método asincrónico, por ejemplo, para implementar un bucle asincrónico de sondeo:

[!code-csharp[Conceptual.TAP_Patterns#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.tap_patterns/cs/patterns1.cs#5)]
[!code-vb[Conceptual.TAP_Patterns#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.tap_patterns/vb/patterns1.vb#5)]

La clase <xref:System.Threading.Tasks.TaskCompletionSource%601> no tiene ningún homólogo no genérico. Sin embargo, <xref:System.Threading.Tasks.Task%601> deriva de <xref:System.Threading.Tasks.Task>, por lo que puede usar el objeto genérico <xref:System.Threading.Tasks.TaskCompletionSource%601> para los métodos enlazados a E/S que simplemente devuelven una tarea. Para ello, puede usar un origen con un `TResult` ficticio (<xref:System.Boolean> es una buena opción predeterminada, pero si le preocupa que el usuario de <xref:System.Threading.Tasks.Task> lo convierta en tipos inferiores a un objeto <xref:System.Threading.Tasks.Task%601>, puede usar un tipo `TResult` privado en su lugar). Por ejemplo, el método `Delay` del ejemplo anterior devuelve la hora actual junto con el desplazamiento resultante (`Task<DateTimeOffset>`). Si este valor de resultado es innecesario, el método podría codificarse como sigue (observe el cambio del tipo de valor devuelto y el cambio del argumento a <xref:System.Threading.Tasks.TaskCompletionSource%601.TrySetResult%2A>):

[!code-csharp[Conceptual.TAP_Patterns#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.tap_patterns/cs/patterns1.cs#6)]
[!code-vb[Conceptual.TAP_Patterns#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.tap_patterns/vb/patterns1.vb#6)]

### <a name="mixed-compute-bound-and-io-bound-tasks"></a>Tareas enlazadas a cálculos y enlazadas a E/S mixtas
Los métodos asincrónicos no se limitan solo a operaciones enlazadas a cálculos o enlazadas a E/S, sino que pueden representar una combinación de ambas. De hecho, se suelen combinar varias operaciones asincrónicas en operaciones mixtas mayores. Por ejemplo, el método `RenderAsync` de un ejemplo anterior realizaba una operación de cálculo intensiva para presentar una imagen basada en `imageData` de entrada. Este `imageData` podría proceder de un servicio Web al que tiene acceso de forma asincrónica:

[!code-csharp[Conceptual.TAP_Patterns#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.tap_patterns/cs/patterns1.cs#7)]
[!code-vb[Conceptual.TAP_Patterns#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.tap_patterns/vb/patterns1.vb#7)]

En este ejemplo también se muestra cómo se puede incluir en un subproceso un único token de cancelación mediante varias operaciones asincrónicas. Para más información, vea la sección de uso de la cancelación en [Utilizar el modelo asincrónico basado en tareas](../../../docs/standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md).

## <a name="see-also"></a>Vea también

- [Modelo asincrónico basado en tareas (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)
- [Modelo asincrónico basado en tareas (TAP)](../../../docs/standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md)
- [Interoperabilidad con otros tipos y patrones asincrónicos](../../../docs/standard/asynchronous-programming-patterns/interop-with-other-asynchronous-patterns-and-types.md)
