---
title: Encadenar tareas mediante tareas de continuación
ms.date: 02/11/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, continuations
ms.assetid: 0b45e9a2-de28-46ce-8212-1817280ed42d
ms.openlocfilehash: 7de8c4e44e1866e3df36c666c9ecc210dc6a7d83
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159369"
---
# <a name="chaining-tasks-by-using-continuation-tasks"></a>Encadenar tareas mediante tareas de continuación
En la programación asincrónica, es habitual que una operación asincrónica, al finalizar, invoque una segunda operación y le pase los datos. Tradicionalmente, las continuaciones se han realizado mediante métodos de devolución de llamada. En la biblioteca TPL (Task Parallel Library, biblioteca de procesamiento paralelo basado en tareas), se proporciona la misma funcionalidad mediante *tareas de continuación*. Una tarea de continuación (también conocida simplemente como una continuación) es una tarea asincrónica invocada por otra tarea, conocida como el *antecedente*, cuando esta finaliza.  
  
 A pesar de que las continuaciones son relativamente fáciles de usar, resultan eficaces y flexibles. Por ejemplo, se puede:  
  
- Pasar datos del antecedente a la continuación.  
  
- Especificar las condiciones precisas en las que se invoca o no se invoca la continuación.  
  
- Cancelar una continuación antes de que se inicie o de forma cooperativa mientras se ejecuta.  
  
- Proporcionar sugerencias sobre cómo debería programarse la continuación.  
  
- Invocar varias continuaciones desde el mismo antecedente.  
  
- Invocar una continuación cuando todos o alguno de los antecedentes finalicen.  
  
- Encadenar las continuaciones una tras otra hasta cualquier longitud arbitraria.  
  
- Usar una continuación para controlar las excepciones producidas por el antecedente.  
  
## <a name="about-continuations"></a>Sobre las continuaciones  
 Una continuación es una tarea que se crea en el estado <xref:System.Threading.Tasks.TaskStatus.WaitingForActivation> y que se activa automáticamente cuando su tarea (o tareas) antecedente finaliza. Llamar a <xref:System.Threading.Tasks.Task.Start%2A?displayProperty=nameWithType> en una continuación en código de usuario produce una excepción <xref:System.InvalidOperationException?displayProperty=nameWithType> .  
  
 Una continuación es en sí misma un <xref:System.Threading.Tasks.Task> y no bloquea el subproceso en el que se inicia. Para un bloqueo, llame al método <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> hasta que finalice la tarea de continuación.  
  
## <a name="creating-a-continuation-for-a-single-antecedent"></a>Crear una continuación para un antecedente único  
 Se puede crear una continuación que se ejecute una vez completado su antecedente mediante una llamada al método <xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=nameWithType> . En el ejemplo siguiente se muestra el patrón básico (para mayor claridad, se omite el control de excepciones). En él se ejecuta una tarea antecedente, `taskA`, que devuelve un objeto <xref:System.DayOfWeek> que indica el nombre del día actual de la semana. Cuando finaliza el antecedente, este se pasa a la tarea de continuación, `continuation`, y se muestra una cadena que incluye su resultado.

> [!NOTE]
> En los ejemplos de C# de este artículo se usa el modificador `async` en el método `Main`. Esa característica está disponible en C# 7.1 y versiones posteriores. En las versiones anteriores se genera [`CS5001`](../../csharp/misc/cs5001.md) al compilar este código de ejemplo. Tendrá que establecer la versión del lenguaje en C# 7.1 o posterior. Puede obtener información sobre cómo configurar la versión del lenguaje en el artículo sobre [configuración de la versión del lenguaje](../../csharp/language-reference/configure-language-version.md).
  
 [!code-csharp[TPL_Continuations#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_continuations/cs/simple1.cs#1)]
 [!code-vb[TPL_Continuations#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/simple1.vb#1)]  
  
## <a name="creating-a-continuation-for-multiple-antecedents"></a>Crear una continuación para varios antecedentes  
 También puede crear una continuación que se ejecutará cuando se haya completado una tarea o un grupo de tareas. Para ejecutar una continuación cuando se hayan completado todas las tareas antecedentes, llame al método estático`Shared` ( <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> en Visual Basic) o al método de instancia <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A?displayProperty=nameWithType> . Para ejecutar una continuación cuando cualquiera de las tareas antecedentes se haya completado, llame al método estático`Shared` ( <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> en Visual Basic) o al método de instancia <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAny%2A?displayProperty=nameWithType> .  
  
 Tenga en cuenta que las llamadas a las sobrecargas <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> y <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> no bloquean el subproceso que realiza la llamada.  Sin embargo, se suele llamar a todos menos a los métodos <xref:System.Threading.Tasks.Task.WhenAll%28System.Collections.Generic.IEnumerable%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=nameWithType> y <xref:System.Threading.Tasks.Task.WhenAll%28System.Threading.Tasks.Task%5B%5D%29?displayProperty=nameWithType> para recuperar la propiedad <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType> devuelta, que bloquea el subproceso que realiza la llamada.  
  
 En el ejemplo siguiente se llama al método <xref:System.Threading.Tasks.Task.WhenAll%28System.Collections.Generic.IEnumerable%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=nameWithType> para crear una tarea de continuación que refleje los resultados de sus diez tareas antecedentes. Cada tarea antecedente eleva al cuadrado un valor de índice que varía entre uno y diez. Si los antecedentes se completan correctamente (su propiedad <xref:System.Threading.Tasks.Task.Status%2A?displayProperty=nameWithType> es <xref:System.Threading.Tasks.TaskStatus.RanToCompletion?displayProperty=nameWithType>), la propiedad <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType> de la continuación es una matriz de los valores <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType> devueltos por cada antecedente. En el ejemplo se suman para calcular el total de los cuadrados de todos los números entre uno y diez.  
  
 [!code-csharp[TPL_Continuations#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_continuations/cs/whenall1.cs#5)]
 [!code-vb[TPL_Continuations#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/whenall1.vb#5)]  
  
## <a name="continuation-options"></a>Opciones de continuación  
 Cuando se crea una continuación de tarea única, se puede usar una sobrecarga <xref:System.Threading.Tasks.Task.ContinueWith%2A> que toma un valor de enumeración <xref:System.Threading.Tasks.TaskContinuationOptions?displayProperty=nameWithType> para especificar las condiciones en las que se inicia la continuación. Por ejemplo, se puede especificar que la continuación únicamente se ejecute si el antecedente se completa correctamente, o solo si se completa en un estado de error. Si la condición no es true cuando el antecedente está listo para invocar la continuación, la continuación realiza la transición directamente al estado <xref:System.Threading.Tasks.TaskStatus.Canceled?displayProperty=nameWithType> y, por tanto, no se puede iniciar.  
  
 Hay distintos métodos de continuación de varias tareas, como las sobrecargas del método <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A?displayProperty=nameWithType> , que también incluyen un parámetro <xref:System.Threading.Tasks.TaskContinuationOptions?displayProperty=nameWithType> . Sin embargo, solo es válido un subconjunto de todos los miembros de enumeración de <xref:System.Threading.Tasks.TaskContinuationOptions?displayProperty=nameWithType> . Se pueden especificar valores <xref:System.Threading.Tasks.TaskContinuationOptions?displayProperty=nameWithType> que tengan equivalentes en la enumeración <xref:System.Threading.Tasks.TaskCreationOptions?displayProperty=nameWithType> , como <xref:System.Threading.Tasks.TaskContinuationOptions.AttachedToParent?displayProperty=nameWithType>, <xref:System.Threading.Tasks.TaskContinuationOptions.LongRunning?displayProperty=nameWithType>y <xref:System.Threading.Tasks.TaskContinuationOptions.PreferFairness?displayProperty=nameWithType>. Si se especifica cualquiera de las opciones `NotOn` o `OnlyOn` con una continuación de varias tareas, se producirá una excepción <xref:System.ArgumentOutOfRangeException> en tiempo de ejecución.  
  
 Para obtener más información sobre las opciones de continuación de tarea, consulte el tema <xref:System.Threading.Tasks.TaskContinuationOptions> .  
  
## <a name="passing-data-to-a-continuation"></a>Pasar datos a una continuación  
 El método <xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=nameWithType> pasa una referencia al antecedente al delegado de usuario de la continuación como argumento. Si el antecedente es un objeto <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> y la tarea se ejecutó hasta que se completó, la continuación puede luego tener acceso a la propiedad <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType> de la tarea.  
  
 La propiedad <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType> se bloquea hasta que se completa la tarea. Sin embargo, si la tarea se canceló o produjo errores y se intenta tener acceso a la propiedad <xref:System.Threading.Tasks.Task%601.Result%2A> , se producirá una excepción <xref:System.AggregateException> . Puede evitar este problema con la opción <xref:System.Threading.Tasks.TaskContinuationOptions.OnlyOnRanToCompletion> , tal como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[TPL_Continuations#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_continuations/cs/result1.cs#2)]
 [!code-vb[TPL_Continuations#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/result1.vb#2)]  
  
 Si desea que la continuación se ejecute aunque el antecedente no finalice correctamente, debe protegerse de la excepción. Un modo de hacerlo es probar la propiedad <xref:System.Threading.Tasks.Task.Status%2A?displayProperty=nameWithType> del antecedente y solo intentar el acceso a la propiedad <xref:System.Threading.Tasks.Task%601.Result%2A> si el estado no es <xref:System.Threading.Tasks.TaskStatus.Faulted> ni <xref:System.Threading.Tasks.TaskStatus.Canceled>. También puede examinar la propiedad <xref:System.Threading.Tasks.Task.Exception%2A> del antecedente. Para más información, consulte [Control de excepciones](../../../docs/standard/parallel-programming/exception-handling-task-parallel-library.md). En el ejemplo siguiente se modifica el ejemplo anterior para tener acceso a la propiedad <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType> del antecedente, pero solo si su estado es <xref:System.Threading.Tasks.TaskStatus.RanToCompletion?displayProperty=nameWithType>.  
  
 [!code-csharp[TPL_Continuations#7](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_continuations/cs/result2.cs#7)]
 [!code-vb[TPL_Continuations#7](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/result2.vb#7)]  
  
## <a name="canceling-a-continuation"></a>Cancelar una continuación  
 La propiedad <xref:System.Threading.Tasks.Task.Status%2A?displayProperty=nameWithType> de una continuación se establece en <xref:System.Threading.Tasks.TaskStatus.Canceled?displayProperty=nameWithType> en las situaciones siguientes:  
  
- Se produce un excepción <xref:System.OperationCanceledException> en respuesta a una solicitud de cancelación. Como sucede con cualquier tarea, si la excepción contiene el mismo token que se ha pasado a la continuación, se trata como una confirmación de cancelación cooperativa.  
  
- A la continuación se le pasa un <xref:System.Threading.CancellationToken?displayProperty=nameWithType> cuya propiedad <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> es `true`. En este caso, la continuación no se inicia y realiza la transición al estado <xref:System.Threading.Tasks.TaskStatus.Canceled?displayProperty=nameWithType> .  
  
- La continuación nunca se ejecuta porque la condición establecida por su argumento <xref:System.Threading.Tasks.TaskContinuationOptions> no se cumplió. Por ejemplo, si un antecedente entra en un estado <xref:System.Threading.Tasks.TaskStatus.Faulted?displayProperty=nameWithType> , su continuación —a la que se le pasó la opción <xref:System.Threading.Tasks.TaskContinuationOptions.NotOnFaulted?displayProperty=nameWithType> — no se ejecutará, pero realizará la transición al estado <xref:System.Threading.Tasks.TaskStatus.Canceled> .  
  
 Si una tarea y su continuación representan dos partes de la misma operación lógica, se puede pasar el mismo token de cancelación a ambas tareas, tal como se muestra en el ejemplo siguiente. Consta de un antecedente que genera una lista de enteros divisibles por 33 y que pasa a la continuación. La continuación a su vez muestra la lista. El antecedente y la continuación se ponen en pausa periódicamente durante intervalos aleatorios. Además, un objeto <xref:System.Threading.Timer?displayProperty=nameWithType> se usa para ejecutar el método `Elapsed` después de un intervalo de tiempo de espera de cinco segundos. Este ejemplo llama al método <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType>, que hace que la tarea que se ejecuta actualmente llame al método <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A?displayProperty=nameWithType>. Que el método <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> se invoque cuando se está ejecutando el antecedente o su continuación depende de la duración de las pausas generadas de forma aleatoria. Si se cancela el antecedente, la continuación no se iniciará. Si no se cancela el antecedente, el token aún puede usarse para cancelar la continuación.  
  
 [!code-csharp[TPL_Continuations#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_continuations/cs/cancellation1.cs#3)]
 [!code-vb[TPL_Continuations#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/cancellation1.vb#3)]  
  
 También se puede evitar que una continuación se ejecute si su antecedente se cancela sin proporcionar a la continuación un token de cancelación. Para ello, debe especificarse la opción <xref:System.Threading.Tasks.TaskContinuationOptions.NotOnCanceled?displayProperty=nameWithType> al crear la continuación. Este es un ejemplo sencillo.  
  
 [!code-csharp[TPL_Continuations#8](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_continuations/cs/cancellation2.cs#8)]
 [!code-vb[TPL_Continuations#8](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/cancellation2.vb#8)]  
  
 Cuando una continuación entra en el estado <xref:System.Threading.Tasks.TaskStatus.Canceled> puede afectar a las continuaciones posteriores, en función de los valores de <xref:System.Threading.Tasks.TaskContinuationOptions> que se especificaron para esas continuaciones.  
  
 Las continuaciones eliminadas no se iniciarán.  
  
## <a name="continuations-and-child-tasks"></a>Continuaciones y tareas secundarias  
 Una continuación no se ejecuta hasta que el antecedente y todas sus tareas secundarias asociadas no se completen. La continuación no espera a que las tareas secundarias desasociadas finalicen. En los dos ejemplos siguientes se ilustran tareas secundarias que se asocian y desasocian de un antecedente que crea una continuación. En el ejemplo siguiente la continuación solo se ejecuta después de que se completan todas las tareas secundarias. Si se ejecuta el ejemplo varias veces, se genera una salida idéntica cada vez. En el ejemplo se inicia el antecedente mediante una llamada al método <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType>, ya que de forma predeterminada el método <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> crea una tarea primaria cuya opción de creación de tarea predeterminada es <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType>.  
  
 [!code-csharp[TPL_Continuations#9](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_continuations/cs/attached1.cs#9)]
 [!code-vb[TPL_Continuations#9](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/attached1.vb#9)]  
  
 No obstante, si las tareas secundarias se desasocian del antecedente, la continuación se ejecuta en cuanto finaliza el antecedente y con independencia del estado de las tareas secundarias. Como resultado, varias ejecuciones del ejemplo siguiente pueden tener una salida distinta que depende de cómo el programador de tareas controla cada tarea secundaria.  
  
 [!code-csharp[TPL_Continuations#10](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_continuations/cs/detached1.cs#10)]
 [!code-vb[TPL_Continuations#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/detached1.vb#10)]  
  
 El estado final de la tarea antecedente depende del estado final de las tareas secundarias asociadas. El estado de las tareas secundarias desasociadas no afecta al elemento primario. Para más información, consulte [Tareas secundarias asociadas y desasociadas](../../../docs/standard/parallel-programming/attached-and-detached-child-tasks.md).  
  
## <a name="associating-state-with-continuations"></a>Asociación de estado con continuaciones  
 Un estado arbitrario se puede asociar con una continuación de tarea. El método <xref:System.Threading.Tasks.Task.ContinueWith%2A> proporciona versiones sobrecargadas, y cada una de ellas toma un valor <xref:System.Object> que representa el estado de la continuación. Más adelante se puede tener acceso a este objeto de estado mediante la propiedad <xref:System.Threading.Tasks.Task.AsyncState%2A?displayProperty=nameWithType> . Si no se proporciona un valor, este objeto de estado es `null` .  
  
 El estado de continuación es útil al convertir un código existente que use el [modelo de programación asincrónica (APM)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md) para utilizar la TPL. En el APM, normalmente se proporciona el estado del objeto en el método **Begin**_Método_ y el acceso posterior a ese estado mediante la propiedad <xref:System.IAsyncResult.AsyncState%2A?displayProperty=nameWithType>. Si se usa el método <xref:System.Threading.Tasks.Task.ContinueWith%2A> , se puede conservar este estado al convertir código que usa el APM para usar la TPL.  
  
 El estado de continuación también puede ser útil cuando se trabaja con objetos <xref:System.Threading.Tasks.Task> en el depurador de Visual Studio. Por ejemplo, en la ventana **Tareas paralelas** , la columna **Tarea** muestra la representación de cadena del objeto de estado de cada tarea. Para más información sobre la ventana **Tareas paralelas**, consulte el artículo [Usar la ventana Tareas](/visualstudio/debugger/using-the-tasks-window).  
  
 En el ejemplo siguiente se muestra cómo usar el estado de continuación. En él se crea una cadena de tareas de continuación. Cada tarea proporciona la hora actual —un objeto <xref:System.DateTime> — para el parámetro `state` del método <xref:System.Threading.Tasks.Task.ContinueWith%2A> . Cada objeto <xref:System.DateTime> representa la hora en que se creó la tarea de continuación. Cada tarea produce como resultado un segundo objeto <xref:System.DateTime> que representa la hora en que finaliza la tarea. Una vez que finalizan todas las tareas, se muestran la hora de creación y la hora de finalización de cada tarea de continuación.  
  
 [!code-csharp[TPL_ContinuationState#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_continuationstate/cs/continuationstate.cs#1)]
 [!code-vb[TPL_ContinuationState#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuationstate/vb/continuationstate.vb#1)]  
  
## <a name="handling-exceptions-thrown-from-continuations"></a>Control de excepciones producidas por continuaciones  
 Una relación antecedente-continuación no es una relación entre elementos primarios y secundarios. Las excepciones producidas por las continuaciones no se propagan al antecedente. Por lo tanto, las excepciones producidas por las continuaciones se deben controlar como en cualquier otra tarea, es decir:  
  
- Puede usar el método <xref:System.Threading.Tasks.Task.Wait%2A>, <xref:System.Threading.Tasks.Task.WaitAll%2A>o <xref:System.Threading.Tasks.Task.WaitAny%2A> , o su homólogo genérico, para esperar en la continuación. Puede esperar un antecedente y sus continuaciones en la misma instrucción `try` , tal como se muestra en el ejemplo siguiente.  
  
     [!code-csharp[TPL_Continuations#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_continuations/cs/exception1.cs#6)]
     [!code-vb[TPL_Continuations#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/exception1.vb#6)]  
  
- Puede usar una segunda continuación para observar la propiedad <xref:System.Threading.Tasks.Task.Exception%2A> de la primera continuación. En el siguiente ejemplo, una tarea intenta leer en un archivo inexistente. La continuación muestra entonces información sobre la excepción en la tarea antecedente.  
  
     [!code-csharp[TPL_Continuations#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_continuations/cs/exception2.cs#4)]
     [!code-vb[TPL_Continuations#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/exception2.vb#4)]  
  
     Dado que se ejecutó con la opción <xref:System.Threading.Tasks.TaskContinuationOptions.OnlyOnFaulted?displayProperty=nameWithType> , la continuación solo se ejecuta si se produce una excepción en el antecedente y, por lo tanto, puede asumir que la propiedad <xref:System.Threading.Tasks.Task.Exception%2A> del antecedente no es `null`. Si la continuación se ejecuta tanto si se produce una excepción en el antecedente como si no, habría que comprobar si la propiedad <xref:System.Threading.Tasks.Task.Exception%2A> del antecedente no es `null` antes de intentar controlar la excepción, como se muestra en el fragmento de código siguiente.  
  
     [!code-csharp[TPL_Continuations#11](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_continuations/cs/exception2.cs#11)]
     [!code-vb[TPL_Continuations#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/exception2.vb#11)]  
  
     Para más información, consulte [Control de excepciones](../../../docs/standard/parallel-programming/exception-handling-task-parallel-library.md).  
  
- Si la continuación es una tarea secundaria asociada que se creó mediante la opción <xref:System.Threading.Tasks.TaskContinuationOptions.AttachedToParent?displayProperty=nameWithType> , sus excepciones serán propagadas por el elemento primario hacia el subproceso de llamada, como sucede con cualquier otro elemento secundario asociado. Para más información, consulte [Tareas secundarias asociadas y desasociadas](../../../docs/standard/parallel-programming/attached-and-detached-child-tasks.md).  
  
## <a name="see-also"></a>Vea también

- [Biblioteca TPL](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)
