---
title: Utilizar el modelo asincrónico basado en tareas
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- .NET Framework, and TAP
- asynchronous design patterns, .NET Framework
- TAP, .NET Framework support for
- Task-based Asynchronous Pattern, .NET Framework support for
- .NET Framework, asynchronous design patterns
ms.assetid: 033cf871-ae24-433d-8939-7a3793e547bf
ms.openlocfilehash: f80e6ae520ab03c0f5f4edc30c0b7102193ee6c5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73139816"
---
# <a name="consuming-the-task-based-asynchronous-pattern"></a>Utilizar el modelo asincrónico basado en tareas

Cuando se utiliza el modelo asincrónico basado en tareas (TAP) para trabajar con operaciones asincrónicas, puede utilizar las devoluciones de llamada para conseguir esperas sin bloqueos.  Para las tareas, esto se consigue con métodos como <xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=nameWithType>. La compatibilidad asincrónica basada en lenguaje oculta las devoluciones de llamada al permitir que las operaciones asincrónicas se puedan esperar en el flujo de control normal y que el código generado por el compilador proporcione esta misma compatibilidad de nivel de API.

## <a name="suspending-execution-with-await"></a>Suspender la ejecución con Await
 A partir de .NET Framework 4.5, se puede utilizar la palabra clave [await](../../csharp/language-reference/operators/await.md) de C# y el [operador Await](../../visual-basic/language-reference/operators/await-operator.md) de Visual Basic para esperar asincrónicamente los objetos <xref:System.Threading.Tasks.Task> y <xref:System.Threading.Tasks.Task%601>. Cuando se espera una clase <xref:System.Threading.Tasks.Task>, la expresión `await` es de tipo `void`. Cuando se espera una clase <xref:System.Threading.Tasks.Task%601>, la expresión `await` es de tipo `TResult`. Debe producirse una expresión `await` dentro del cuerpo de un método asincrónico. Para obtener más información sobre la compatibilidad del lenguaje C# y Visual Basic en .NET Framework 4.5, consulte las especificaciones del lenguaje C# y Visual Basic.

 En realidad, la funcionalidad de await instala una devolución de llamada en la tarea mediante una continuación.  Esta devolución de llamada reanuda el método asincrónico en el punto de suspensión. Cuando se reanuda el método asincrónico, si la operación de espera finalizó correctamente y fue un objeto <xref:System.Threading.Tasks.Task%601>, se devuelve su `TResult`.  Si las clases <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> por la que esperaba finalizaron con el estado <xref:System.Threading.Tasks.TaskStatus.Canceled>, se produce una excepción <xref:System.OperationCanceledException>.  Si las clases <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> por la que esperaba finalizaron con el estado <xref:System.Threading.Tasks.TaskStatus.Faulted>, se produce la excepción que causó el error. Un objeto `Task` puede producir un error como resultado de múltiples excepciones, pero solo una de estas excepciones se propaga. Sin embargo, la propiedad <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> devuelve una excepción <xref:System.AggregateException> que contiene todos los errores.

 Si un contexto de sincronización (objeto <xref:System.Threading.SynchronizationContext>) está asociado con el subproceso que ejecutaba el método asincrónico en el momento de la suspensión (por ejemplo, si la propiedad <xref:System.Threading.SynchronizationContext.Current%2A?displayProperty=nameWithType> no es `null`), el método asincrónico se reanuda en ese mismo contexto de sincronización con el método <xref:System.Threading.SynchronizationContext.Post%2A> del contexto. De lo contrario, se basa en el programador de tareas (objeto <xref:System.Threading.Tasks.TaskScheduler>) que era actual en el momento de la suspensión. Normalmente, se trata del programador de tareas predeterminado (<xref:System.Threading.Tasks.TaskScheduler.Default%2A?displayProperty=nameWithType>), que tiene como destino el grupo de subprocesos. El programador de tareas determina si la operación asincrónica en espera debe reanudarse donde ha completado o si se debe programar la reanudación. Normalmente, el programador predeterminado permite que la continuación se ejecute en el subproceso que ha completado la operación de espera.

 Cuando se llama a un método asincrónico, ejecuta sincrónicamente el cuerpo de la función hasta que la primera expresión de espera en una instancia esperable que todavía no se ha completado, momento en el que la invocación se devuelve al llamador. Si el método asincrónico no devuelve `void`, se devuelve un objeto <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> para representar el cálculo en curso. En un método asincrónico distinto de void, si se encuentra una instrucción de devolución o se alcanza el final del cuerpo del método, la tarea se completa en el estado final <xref:System.Threading.Tasks.TaskStatus.RanToCompletion>. Si una excepción no controlada hace que el control abandone el cuerpo del método asincrónico, la tarea finaliza en el estado <xref:System.Threading.Tasks.TaskStatus.Faulted>. Si esa excepción es una clase <xref:System.OperationCanceledException>, en su lugar, la tarea finaliza con el estado <xref:System.Threading.Tasks.TaskStatus.Canceled>. De esta manera, el resultado o excepción se publica finalmente.

 Hay diversas variaciones importantes de este comportamiento.  Por motivos de rendimiento, si ya ha completado una tarea en el momento en que se esperaba, no se obtiene el control y la función continúa ejecutándose.  Además, volver al contexto original no siempre es el comportamiento deseado y se puede cambiar. Esto se describe con más detalle en la sección siguiente.

### <a name="configuring-suspension-and-resumption-with-yield-and-configureawait"></a>Configurar la suspensión y reanudación con Yield y ConfigureAwait
 Varios métodos proporcionan más control sobre la ejecución de un método asincrónico. Por ejemplo, puede usar el método <xref:System.Threading.Tasks.Task.Yield%2A?displayProperty=nameWithType> para introducir un punto de rendimiento en el método asincrónico:

```csharp
public class Task : …
{
    public static YieldAwaitable Yield();
    …
}
```

 Esto es equivalente a volver a registrar o programar de manera asincrónica al contexto actual.

```csharp
Task.Run(async delegate
{
    for(int i=0; i<1000000; i++)
    {
        await Task.Yield(); // fork the continuation into a separate work item
        ...
    }
});
```

 También puede usar el método <xref:System.Threading.Tasks.Task.ConfigureAwait%2A?displayProperty=nameWithType> para controlar mejor la suspensión y reanudación de un método asincrónico.  Como se mencionó anteriormente, de forma predeterminada, se captura el contexto actual en el momento en que se suspende un método asincrónico, y ese contexto capturado se utiliza para invocar la continuación del método asincrónico tras la reanudación.  En muchos casos, este es el comportamiento exacto que desea.  En otros casos, es posible que no le preocupe el contexto de continuación y puede lograr un mejor rendimiento al evitar dichos registros en el contexto original.  Para habilitar esto, use el método <xref:System.Threading.Tasks.Task.ConfigureAwait%2A?displayProperty=nameWithType> para informar a la operación await que no capture ni se reanude en el contexto, pero que continúe la ejecución siempre que haya completado la operación asincrónica que se estaba esperando:

```csharp
await someTask.ConfigureAwait(continueOnCapturedContext:false);
```

## <a name="canceling-an-asynchronous-operation"></a>Cancelar una operación asincrónica
 A partir de .NET Framework 4, los métodos de TAP que admiten cancelación proporcionan al menos una sobrecarga que acepta un token de cancelación (objeto <xref:System.Threading.CancellationToken>).

 Se crea un token de cancelación a través de un origen de token de cancelación (objeto <xref:System.Threading.CancellationTokenSource>).  La propiedad <xref:System.Threading.CancellationTokenSource.Token%2A> del origen devuelve el token de cancelación que se señalará cuando se llame al método <xref:System.Threading.CancellationTokenSource.Cancel%2A> de origen.  Por ejemplo, si desea descargar una única página web y desea poder cancelar la operación, cree un objeto <xref:System.Threading.CancellationTokenSource>, pase su token para el método TAP y luego llame al método <xref:System.Threading.CancellationTokenSource.Cancel%2A> de origen cuando esté listo para cancelar la operación:

```csharp
var cts = new CancellationTokenSource();
string result = await DownloadStringAsync(url, cts.Token);
… // at some point later, potentially on another thread
cts.Cancel();
```

 Para cancelar varias invocaciones asincrónicas, puede pasar el mismo token para todas las llamadas:

```csharp
var cts = new CancellationTokenSource();
    IList<string> results = await Task.WhenAll(from url in urls select DownloadStringAsync(url, cts.Token));
    // at some point later, potentially on another thread
    …
    cts.Cancel();
```

 O bien, puede pasar el mismo token a un subconjunto de operaciones selectivo:

```csharp
var cts = new CancellationTokenSource();
    byte [] data = await DownloadDataAsync(url, cts.Token);
    await SaveToDiskAsync(outputPath, data, CancellationToken.None);
    … // at some point later, potentially on another thread
    cts.Cancel();
```

 Las solicitudes de cancelación se pueden iniciar desde cualquier subproceso.

 Puede pasar el valor <xref:System.Threading.CancellationToken.None%2A?displayProperty=nameWithType> a cualquier método que acepta un token de cancelación para indicar que nunca se le solicitó la cancelación.  Esto hace que la propiedad <xref:System.Threading.CancellationToken.CanBeCanceled%2A?displayProperty=nameWithType> devuelva `false`, y el método llamado puede optimizarse en consecuencia.  Con fines de prueba, también puede pasar un token de cancelación cancelado previamente cuyas instancias se crean mediante el constructor que acepta un valor booleano para indicar si el token debe iniciarse en un estado ya cancelado o que no se puede cancelar.

 Este enfoque de cancelación tiene varias ventajas:

- Puede pasar el mismo token de cancelación a cualquier número de operaciones sincrónicas y asincrónicas.

- La misma solicitud de cancelación puede extenderse a cualquier número de agentes de escucha.

- El desarrollador de la API asincrónica tiene todo el control de si se puede solicitar la cancelación y cuándo puede surtir efecto.

- El código que utiliza la API puede determinar de forma selectiva las llamadas asincrónicas que se propagarán las solicitudes de cancelación.

## <a name="monitoring-progress"></a>Supervisar el progreso
 Algunos métodos asincrónicos exponen progreso a través de una interfaz de progreso pasada al método asincrónico.  Por ejemplo, considere una función que se descarga de manera asincrónica una cadena de texto y que genera las actualizaciones de progreso que incluyen el porcentaje de descarga que se ha completado hasta el momento.  Este método se puede utilizar en una aplicación de Windows Presentation Foundation (WPF) como sigue:

```csharp
private async void btnDownload_Click(object sender, RoutedEventArgs e)
{
    btnDownload.IsEnabled = false;
    try
    {
        txtResult.Text = await DownloadStringAsync(txtUrl.Text,
            new Progress<int>(p => pbDownloadProgress.Value = p));
    }
    finally { btnDownload.IsEnabled = true; }
}
```

<a name="combinators"></a>
## <a name="using-the-built-in-task-based-combinators"></a>Usar los combinadores integrados basados en tareas
 El espacio de nombres <xref:System.Threading.Tasks> incluye varios métodos para crear tareas y trabajar con ellas.

### <a name="taskrun"></a>Task.Run
 La clase <xref:System.Threading.Tasks.Task> incluye varios métodos <xref:System.Threading.Tasks.Task.Run%2A> que le permiten descargar trabajo con facilidad como las clases <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> en el grupo de subprocesos; por ejemplo:

```csharp
public async void button1_Click(object sender, EventArgs e)
{
    textBox1.Text = await Task.Run(() =>
    {
        // … do compute-bound work here
        return answer;
    });
}
```

 Algunos de estos métodos <xref:System.Threading.Tasks.Task.Run%2A>, como la sobrecarga <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=nameWithType>, existen como forma abreviada del método <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType>.  Otras sobrecargas, como <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=nameWithType>, habilitan el uso de await en el trabajo descargado; por ejemplo:

```csharp
public async void button1_Click(object sender, EventArgs e)
{
    pictureBox1.Image = await Task.Run(async() =>
    {
        using(Bitmap bmp1 = await DownloadFirstImageAsync())
        using(Bitmap bmp2 = await DownloadSecondImageAsync())
        return Mashup(bmp1, bmp2);
    });
}
```

 Tales sobrecargas, lógicamente, son equivalentes al uso del método <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType> junto con el método de extensión <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> en la biblioteca TPL.

### <a name="taskfromresult"></a>Task.FromResult
 Utilice el método <xref:System.Threading.Tasks.Task.FromResult%2A> en escenarios donde los datos estén disponibles y solo debe devolverse desde un método de devolución de tarea de elevación en un método <xref:System.Threading.Tasks.Task%601>:

```csharp
public Task<int> GetValueAsync(string key)
{
    int cachedValue;
    return TryGetCachedValue(out cachedValue) ?
        Task.FromResult(cachedValue) :
        GetValueAsyncInternal();
}

private async Task<int> GetValueAsyncInternal(string key)
{
    …
}
```

### <a name="taskwhenall"></a>Task.WhenAll
 Utilice el método <xref:System.Threading.Tasks.Task.WhenAll%2A> para esperar asincrónicamente en varias operaciones asincrónicas que se representan como tareas.  El método tiene varias sobrecargas que admiten un conjunto de tareas no genéricas o un conjunto no uniforme de tareas genéricas (por ejemplo, esperando de forma asincrónica varias operaciones que devuelven void o esperando de forma asincrónica varios métodos que devuelven valores, donde cada valor puede tener un tipo diferente) y para admitir un conjunto uniforme de tareas genéricas (como esperar de forma asincrónica para varios métodos que devuelven `TResult`).

 Supongamos que desea enviar mensajes de correo electrónico a varios clientes. Puede superponer el envío de los mensajes, para que no esté esperando que se complete un mensaje antes de enviar el siguiente. También puede averiguar cuando se completan las operaciones de envío y si se ha producido algún error:

```csharp
IEnumerable<Task> asyncOps = from addr in addrs select SendMailAsync(addr);
await Task.WhenAll(asyncOps);
```

 Este código no controla explícitamente las excepciones que pueden aparecer, pero permite que las excepciones se propaguen fuera de `await` en la tarea resultante de <xref:System.Threading.Tasks.Task.WhenAll%2A>.  Para controlar las excepciones, puede utilizar código como el siguiente:

```csharp
IEnumerable<Task> asyncOps = from addr in addrs select SendMailAsync(addr);
try
{
    await Task.WhenAll(asyncOps);
}
catch(Exception exc)
{
    ...
}
```

 En este caso, si se produce un error en cualquier operación asincrónica, todas las excepciones se consolidarán en una excepción <xref:System.AggregateException>, que se almacena en la clase <xref:System.Threading.Tasks.Task> devuelta por el método <xref:System.Threading.Tasks.Task.WhenAll%2A>.  Sin embargo, solo una de esas excepciones se propaga por la palabra clave `await`.  Si desea examinar todas las excepciones, puede volver a escribir el código anterior como sigue:

```csharp
Task [] asyncOps = (from addr in addrs select SendMailAsync(addr)).ToArray();
try
{
    await Task.WhenAll(asyncOps);
}
catch(Exception exc)
{
    foreach(Task faulted in asyncOps.Where(t => t.IsFaulted))
    {
        … // work with faulted and faulted.Exception
    }
}
```

 Veamos un ejemplo de descarga de varios archivos desde la web de forma asincrónica.  En este caso, todas las operaciones asincrónicas tienen tipos de resultado homogéneos, y es fácil acceder a los resultados:

```csharp
string [] pages = await Task.WhenAll(
    from url in urls select DownloadStringAsync(url));
```

 Puede utilizar las mismas técnicas de control de excepciones que se explicaron en el escenario anterior que devuelve void:

```csharp
Task [] asyncOps =
    (from url in urls select DownloadStringAsync(url)).ToArray();
try
{
    string [] pages = await Task.WhenAll(asyncOps);
    ...
}
catch(Exception exc)
{
    foreach(Task<string> faulted in asyncOps.Where(t => t.IsFaulted))
    {
        … // work with faulted and faulted.Exception
    }
}
```

### <a name="taskwhenany"></a>Task.WhenAny
 Puede usar el método <xref:System.Threading.Tasks.Task.WhenAny%2A> para esperar de manera asincrónica solo una de varias operaciones asincrónicas que se representan como tareas para completar.  Este método actúa en cuatro casos de uso principales:

- Redundancia: realizar una operación varias veces y seleccionar la que se complete primero (por ejemplo, ponerse en contacto con varios servicios web de cotización bursátil que va a generar un único resultado y seleccionar la que se completa con más rapidez).

- Intercalación: iniciar varias operaciones y esperar que se completen todas, pero procesarlas a medida que se completan.

- Limitación: permitir que operaciones adicionales comiencen a medida que otras se completan.  Esto es una extensión del escenario de intercalación.

- Recursividad temprana: por ejemplo, una operación representada por la tarea t1 puede agruparse en una tarea <xref:System.Threading.Tasks.Task.WhenAny%2A> con otra tarea t2, y puede esperar a la tarea <xref:System.Threading.Tasks.Task.WhenAny%2A>. La tarea t2 podría representar un tiempo de espera o cancelación, o alguna otra señal que hace que la tarea <xref:System.Threading.Tasks.Task.WhenAny%2A> se complete antes de que finalice t1.

#### <a name="redundancy"></a>Redundancia
 Considere un caso en el que quiera tomar la decisión de comprar o no una acción.  Hay varios servicios web de recomendación bursátil en los que confía, pero según la carga diaria, cada servicio puede acabar ralentizándose en momentos diferentes.  Puede usar el método <xref:System.Threading.Tasks.Task.WhenAny%2A> para recibir una notificación cuando se complete cualquier operación:

```csharp
var recommendations = new List<Task<bool>>()
{
    GetBuyRecommendation1Async(symbol),
    GetBuyRecommendation2Async(symbol),
    GetBuyRecommendation3Async(symbol)
};
Task<bool> recommendation = await Task.WhenAny(recommendations);
if (await recommendation) BuyStock(symbol);
```

 A diferencia de <xref:System.Threading.Tasks.Task.WhenAll%2A>, que devuelve los resultados desajustados de todas las tareas que se han completado correctamente, <xref:System.Threading.Tasks.Task.WhenAny%2A> devuelve la tarea completada. Si se produce un error en una tarea, es importante saber que se produjo un error y, si una tarea se realiza correctamente, es importante saber con qué tarea está asociado el valor devuelto.  Por lo tanto, necesitará acceder al resultado de la tarea devuelta o esperarla aún más, tal como se muestra en este ejemplo.

 Al igual que con <xref:System.Threading.Tasks.Task.WhenAll%2A>, tendrá que ser capaz de alojar las excepciones.  Dado que recibe de vuelta la tarea de completa, puede esperar que se hayan propagado los errores en la tarea devuelta y `try/catch` adecuadamente; por ejemplo:

```csharp
Task<bool> [] recommendations = …;
while(recommendations.Count > 0)
{
    Task<bool> recommendation = await Task.WhenAny(recommendations);
    try
    {
        if (await recommendation) BuyStock(symbol);
        break;
    }
    catch(WebException exc)
    {
        recommendations.Remove(recommendation);
    }
}
```

 Además, aunque una primera tarea se complete correctamente, las tareas subsiguientes pueden producir un error.  En este punto, tiene varias opciones para tratar las excepciones: puede esperar hasta que han completado todas las tareas iniciadas, en cuyo caso puede utilizar el método <xref:System.Threading.Tasks.Task.WhenAll%2A>, o bien puede decidir que todas las excepciones son importantes y se deben registrar.  Para ello, puede usar las continuaciones para recibir una notificación cuando se hayan completado las tareas de forma asincrónica:

```csharp
foreach(Task recommendation in recommendations)
{
    var ignored = recommendation.ContinueWith(
        t => { if (t.IsFaulted) Log(t.Exception); });
}
```

 O bien

```csharp
foreach(Task recommendation in recommendations)
{
    var ignored = recommendation.ContinueWith(
        t => Log(t.Exception), TaskContinuationOptions.OnlyOnFaulted);
}
```

 o incluso:

```csharp
private static async void LogCompletionIfFailed(IEnumerable<Task> tasks)
{
    foreach(var task in tasks)
    {
        try { await task; }
        catch(Exception exc) { Log(exc); }
    }
}
…
LogCompletionIfFailed(recommendations);
```

 Por último, puede querer cancelar todas las operaciones restantes:

```csharp
var cts = new CancellationTokenSource();
var recommendations = new List<Task<bool>>()
{
    GetBuyRecommendation1Async(symbol, cts.Token),
    GetBuyRecommendation2Async(symbol, cts.Token),
    GetBuyRecommendation3Async(symbol, cts.Token)
};

Task<bool> recommendation = await Task.WhenAny(recommendations);
cts.Cancel();
if (await recommendation) BuyStock(symbol);
```

#### <a name="interleaving"></a>Intercalación
 Considere un caso donde descarga imágenes de la web y procesa cada imagen (por ejemplo, agregando la imagen a un control de interfaz de usuario).  Tendrá que realizar el procesamiento secuencialmente en el subproceso de interfaz de usuario, pero quiere descargar las imágenes lo más simultáneamente como sea posible. Además, no desea mantener la adición de las imágenes en la interfaz de usuario hasta que todas se hayan descargado, sino que desea agregarlas a medida que se realizan:

```csharp
List<Task<Bitmap>> imageTasks =
    (from imageUrl in urls select GetBitmapAsync(imageUrl)).ToList();
while(imageTasks.Count > 0)
{
    try
    {
        Task<Bitmap> imageTask = await Task.WhenAny(imageTasks);
        imageTasks.Remove(imageTask);

        Bitmap image = await imageTask;
        panel.AddImage(image);
    }
    catch{}
}
```

 También puede aplicar la intercalación en un escenario que implica el procesamiento de cálculo intensivo en la clase <xref:System.Threading.ThreadPool> de las imágenes descargadas; por ejemplo:

```csharp
List<Task<Bitmap>> imageTasks =
    (from imageUrl in urls select GetBitmapAsync(imageUrl)
         .ContinueWith(t => ConvertImage(t.Result)).ToList();
while(imageTasks.Count > 0)
{
    try
    {
        Task<Bitmap> imageTask = await Task.WhenAny(imageTasks);
        imageTasks.Remove(imageTask);

        Bitmap image = await imageTask;
        panel.AddImage(image);
    }
    catch{}
}
```

#### <a name="throttling"></a>Limitación de peticiones
 Considere el ejemplo de intercalación, excepto en que el usuario descarga tantas imágenes que las descargas tienen que limitarse; por ejemplo, desea que solo un número específico de descargas ocurra al mismo tiempo. Para lograr esto, puede iniciar un subconjunto de operaciones asincrónicas.  Cuando se completen las operaciones, puede iniciar operaciones adicionales que ocupen su lugar:

```csharp
const int CONCURRENCY_LEVEL = 15;
Uri [] urls = …;
int nextIndex = 0;
var imageTasks = new List<Task<Bitmap>>();
while(nextIndex < CONCURRENCY_LEVEL && nextIndex < urls.Length)
{
    imageTasks.Add(GetBitmapAsync(urls[nextIndex]));
    nextIndex++;
}

while(imageTasks.Count > 0)
{
    try
    {
        Task<Bitmap> imageTask = await Task.WhenAny(imageTasks);
        imageTasks.Remove(imageTask);

        Bitmap image = await imageTask;
        panel.AddImage(image);
    }
    catch(Exception exc) { Log(exc); }

    if (nextIndex < urls.Length)
    {
        imageTasks.Add(GetBitmapAsync(urls[nextIndex]));
        nextIndex++;
    }
}
```

#### <a name="early-bailout"></a>Salida anticipada
 Considere que está esperando asincrónicamente que una operación se complete mientras se responde simultáneamente a la solicitud de cancelación de un usuario (por ejemplo, el usuario hace clic en un botón Cancelar). El código siguiente muestra este escenario:

```csharp
private CancellationTokenSource m_cts;

public void btnCancel_Click(object sender, EventArgs e)
{
    if (m_cts != null) m_cts.Cancel();
}

public async void btnRun_Click(object sender, EventArgs e)
{
    m_cts = new CancellationTokenSource();
    btnRun.Enabled = false;
    try
    {
        Task<Bitmap> imageDownload = GetBitmapAsync(txtUrl.Text);
        await UntilCompletionOrCancellation(imageDownload, m_cts.Token);
        if (imageDownload.IsCompleted)
        {
            Bitmap image = await imageDownload;
            panel.AddImage(image);
        }
        else imageDownload.ContinueWith(t => Log(t));
    }
    finally { btnRun.Enabled = true; }
}

private static async Task UntilCompletionOrCancellation(
    Task asyncOp, CancellationToken ct)
{
    var tcs = new TaskCompletionSource<bool>();
    using(ct.Register(() => tcs.TrySetResult(true)))
        await Task.WhenAny(asyncOp, tcs.Task);
    return asyncOp;
}
```

 Esta implementación permite volver a la interfaz de usuario en cuanto decide abandonar la operación, pero no se cancelan las operaciones asincrónicas subyacentes.  Otra alternativa sería cancelar las operaciones pendientes cuando decide abandone la operación, pero no se restablece la interfaz de usuario hasta que las operaciones se hayan finalizado, posiblemente debido a una finalización anticipada debido a la solicitud de cancelación:

```csharp
private CancellationTokenSource m_cts;

public async void btnRun_Click(object sender, EventArgs e)
{
    m_cts = new CancellationTokenSource();

    btnRun.Enabled = false;
    try
    {
        Task<Bitmap> imageDownload = GetBitmapAsync(txtUrl.Text, m_cts.Token);
        await UntilCompletionOrCancellation(imageDownload, m_cts.Token);
        Bitmap image = await imageDownload;
        panel.AddImage(image);
    }
    catch(OperationCanceledException) {}
    finally { btnRun.Enabled = true; }
}
```

 Otro ejemplo de recursividad temprana conlleva usar el método <xref:System.Threading.Tasks.Task.WhenAny%2A> junto con el método <xref:System.Threading.Tasks.Task.Delay%2A>, como se describe en la sección siguiente.

### <a name="taskdelay"></a>Task.Delay
 Puede usar el método <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> para introducir pausas en una ejecución del método asincrónico.  Esto es útil para muchos tipos de funcionalidad, incluida la generación de bucles de sondeo y el retraso del control de entrada de usuario durante un período predeterminado.  El método <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> también puede resultar útil junto con <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> para implementar tiempos de espera con awaits.

 Si una tarea que forma parte de una operación asincrónica mayor (por ejemplo, un servicio web ASP.NET) tarda demasiado tiempo en completarse, la operación global podría verse afectada, especialmente si no se puede completar.  Por este motivo, es importante poder agotar el tiempo de espera al esperar a una operación asincrónica.  Los métodos <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Task.WaitAll%2A?displayProperty=nameWithType> y <xref:System.Threading.Tasks.Task.WaitAny%2A?displayProperty=nameWithType> sincrónicos aceptan valores de tiempo de espera, pero <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A?displayProperty=nameWithType>/<xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> y los métodos <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>/<xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> mencionados anteriormente no los aceptan.  En su lugar, puede usar <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> y <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> en combinación con la implementación de un tiempo de espera.

 Por ejemplo, en la aplicación de la interfaz de usuario, supongamos que desea descargar una imagen y deshabilitar la interfaz de usuario mientras se descarga la imagen. Sin embargo, si la descarga tarda mucho tiempo, quiere volver a habilitar la interfaz de usuario y descartar la descarga:

```csharp
public async void btnDownload_Click(object sender, EventArgs e)
{
    btnDownload.Enabled = false;
    try
    {
        Task<Bitmap> download = GetBitmapAsync(url);
        if (download == await Task.WhenAny(download, Task.Delay(3000)))
        {
            Bitmap bmp = await download;
            pictureBox.Image = bmp;
            status.Text = "Downloaded";
        }
        else
        {
            pictureBox.Image = null;
            status.Text = "Timed out";
            var ignored = download.ContinueWith(
                t => Trace("Task finally completed"));
        }
    }
    finally { btnDownload.Enabled = true; }
}
```

 Lo mismo se aplica a varias descargas, porque <xref:System.Threading.Tasks.Task.WhenAll%2A> devuelve una tarea:

```csharp
public async void btnDownload_Click(object sender, RoutedEventArgs e)
{
    btnDownload.Enabled = false;
    try
    {
        Task<Bitmap[]> downloads =
            Task.WhenAll(from url in urls select GetBitmapAsync(url));
        if (downloads == await Task.WhenAny(downloads, Task.Delay(3000)))
        {
            foreach(var bmp in downloads) panel.AddImage(bmp);
            status.Text = "Downloaded";
        }
        else
        {
            status.Text = "Timed out";
            downloads.ContinueWith(t => Log(t));
        }
    }
    finally { btnDownload.Enabled = true; }
}
```

## <a name="building-task-based-combinators"></a>Crear combinadores basados en tareas
 Como una tarea se puede representar completamente una operación asincrónica y proporciona funcionalidades sincrónicas y asincrónicas para combinarse con la operación y recuperar sus resultados, entre otros, puede crear bibliotecas útiles de combinadores que componen tareas para crear patrones más grandes.  Como se describe en la sección anterior, .NET Framework incluye varios combinadores integrados, pero también puede crear los suyos propios. Las secciones siguientes proporcionan varios ejemplos de tipos y métodos de combinadores posibles.

### <a name="retryonfault"></a>RetryOnFault
 En muchas situaciones, puede querer reintentar la operación si se produce un error en un intento anterior.  Para el código sincrónico, podría crear un método del asistente como `RetryOnFault` en el ejemplo siguiente para lograr esto:

```csharp
public static T RetryOnFault<T>(
    Func<T> function, int maxTries)
{
    for(int i=0; i<maxTries; i++)
    {
        try { return function(); }
        catch { if (i == maxTries-1) throw; }
    }
    return default(T);
}
```

 Puede crear un método del asistente prácticamente idéntico para las operaciones asincrónicas que se implementan con TAP y, por tanto, devolver las tareas:

```csharp
public static async Task<T> RetryOnFault<T>(
    Func<Task<T>> function, int maxTries)
{
    for(int i=0; i<maxTries; i++)
    {
        try { return await function().ConfigureAwait(false); }
        catch { if (i == maxTries-1) throw; }
    }
    return default(T);
}
```

 Después puede usar este combinador para codificar los reintentos en la lógica de la aplicación; por ejemplo:

```csharp
// Download the URL, trying up to three times in case of failure
string pageContents = await RetryOnFault(
    () => DownloadStringAsync(url), 3);
```

 Puede ampliar aún más la función `RetryOnFault`. Por ejemplo, la función puede aceptar otro `Func<Task>` que se invocará entre reintentos para determinar cuándo volver a intentar la operación, por ejemplo:

```csharp
public static async Task<T> RetryOnFault<T>(
    Func<Task<T>> function, int maxTries, Func<Task> retryWhen)
{
    for(int i=0; i<maxTries; i++)
    {
        try { return await function().ConfigureAwait(false); }
        catch { if (i == maxTries-1) throw; }
        await retryWhen().ConfigureAwait(false);
    }
    return default(T);
}
```

 Después, puede utilizar la función siguiente para esperar un segundo antes de reintentar la operación:

```csharp
// Download the URL, trying up to three times in case of failure,
// and delaying for a second between retries
string pageContents = await RetryOnFault(
    () => DownloadStringAsync(url), 3, () => Task.Delay(1000));
```

### <a name="needonlyone"></a>NeedOnlyOne
 A veces, puede sacar partido de la redundancia para mejorar la latencia y las posibilidades de éxito de una operación.  Considere la posibilidad de varios servicios web que proporcionan cotizaciones bursátiles, pero a lo largo del día cada servicio puede proporcionar diferentes niveles de calidad y tiempos de respuesta.  Para tratar estas fluctuaciones, pueden emitir solicitudes a todos los servicios web y tan pronto como obtiene una respuesta de uno, cancelar las solicitudes restantes.  Puede implementar una función del asistente para que resulte más fácil de implementar este patrón común de iniciar varias operaciones, esperar alguna y, después, cancelar el resto. La función `NeedOnlyOne` del ejemplo siguiente muestra este escenario:

```csharp
public static async Task<T> NeedOnlyOne(
    params Func<CancellationToken,Task<T>> [] functions)
{
    var cts = new CancellationTokenSource();
    var tasks = (from function in functions
                 select function(cts.Token)).ToArray();
    var completed = await Task.WhenAny(tasks).ConfigureAwait(false);
    cts.Cancel();
    foreach(var task in tasks)
    {
        var ignored = task.ContinueWith(
            t => Log(t), TaskContinuationOptions.OnlyOnFaulted);
    }
    return completed;
}
```

 Después puede utilizar esta función como sigue:

```csharp
double currentPrice = await NeedOnlyOne(
    ct => GetCurrentPriceFromServer1Async("msft", ct),
    ct => GetCurrentPriceFromServer2Async("msft", ct),
    ct => GetCurrentPriceFromServer3Async("msft", ct));
```

### <a name="interleaved-operations"></a>Operaciones intercaladas
 Hay un posible problema de rendimiento con el uso del método <xref:System.Threading.Tasks.Task.WhenAny%2A> para admitir un escenario de intercalación cuando se trabaja con conjuntos de tareas muy grandes. Todas las llamadas a <xref:System.Threading.Tasks.Task.WhenAny%2A> resultan en el registro de una continuación con cada tarea. Para un número N de tareas, el resultado son O(N<sup>2</sup>) continuaciones creadas durante la vigencia de la operación de intercalación. Si trabaja con un conjunto de tareas grande, puede usar un combinador (`Interleaved` en el ejemplo siguiente) para solucionar el problema de rendimiento:

```csharp
static IEnumerable<Task<T>> Interleaved<T>(IEnumerable<Task<T>> tasks)
{
    var inputTasks = tasks.ToList();
    var sources = (from _ in Enumerable.Range(0, inputTasks.Count)
                   select new TaskCompletionSource<T>()).ToList();
    int nextTaskIndex = -1;
    foreach (var inputTask in inputTasks)
    {
        inputTask.ContinueWith(completed =>
        {
            var source = sources[Interlocked.Increment(ref nextTaskIndex)];
            if (completed.IsFaulted)
                source.TrySetException(completed.Exception.InnerExceptions);
            else if (completed.IsCanceled)
                source.TrySetCanceled();
            else
                source.TrySetResult(completed.Result);
        }, CancellationToken.None,
           TaskContinuationOptions.ExecuteSynchronously,
           TaskScheduler.Default);
    }
    return from source in sources
           select source.Task;
}
```

 Después puede usar el combinador para procesar los resultados de las tareas a medida que se completan; por ejemplo:

```csharp
IEnumerable<Task<int>> tasks = ...;
foreach(var task in Interleaved(tasks))
{
    int result = await task;
    …
}
```

### <a name="whenallorfirstexception"></a>WhenAllOrFirstException
 En ciertos escenarios de dispersión y recopilación, puede querer esperar a todas las tareas de un conjunto, a menos que una de ellas falle, en cuyo caso deseará detener la espera en cuanto se produzca la excepción.  Puede conseguirlo con un método de combinador como `WhenAllOrFirstException` en el ejemplo siguiente:

```csharp
public static Task<T[]> WhenAllOrFirstException<T>(IEnumerable<Task<T>> tasks)
{
    var inputs = tasks.ToList();
    var ce = new CountdownEvent(inputs.Count);
    var tcs = new TaskCompletionSource<T[]>();

    Action<Task> onCompleted = (Task completed) =>
    {
        if (completed.IsFaulted)
            tcs.TrySetException(completed.Exception.InnerExceptions);
        if (ce.Signal() && !tcs.Task.IsCompleted)
            tcs.TrySetResult(inputs.Select(t => t.Result).ToArray());
    };

    foreach (var t in inputs) t.ContinueWith(onCompleted);
    return tcs.Task;
}
```

## <a name="building-task-based-data-structures"></a>Crear estructuras de datos basadas en tareas
 Además de la capacidad de generar combinadores basados en tareas personalizadas, disponer de una estructura de datos de <xref:System.Threading.Tasks.Task> y <xref:System.Threading.Tasks.Task%601> que representa tanto los resultados de una operación asincrónica y la sincronización necesaria para unirse a ella la convierte en un tipo muy eficaz para crear estructuras de datos personalizadas para usarse en escenarios asincrónicos.

### <a name="asynccache"></a>AsyncCache
 Un aspecto importante de una tarea es que se puede entregar a varios consumidores, todos ellos pueden esperar a que finalice, registrar las continuaciones con ella, obtener sus resultados o excepciones (en el caso de <xref:System.Threading.Tasks.Task%601>), y así sucesivamente.  Esto hace que <xref:System.Threading.Tasks.Task> y <xref:System.Threading.Tasks.Task%601> sean perfectos para usarse en una infraestructura de almacenamiento en caché asincrónica.  Este es un ejemplo de una caché asincrónica pequeña pero muy eficaz creada a partir del objeto <xref:System.Threading.Tasks.Task%601>:

```csharp
public class AsyncCache<TKey, TValue>
{
    private readonly Func<TKey, Task<TValue>> _valueFactory;
    private readonly ConcurrentDictionary<TKey, Lazy<Task<TValue>>> _map;

    public AsyncCache(Func<TKey, Task<TValue>> valueFactory)
    {
        if (valueFactory == null) throw new ArgumentNullException("loader");
        _valueFactory = valueFactory;
        _map = new ConcurrentDictionary<TKey, Lazy<Task<TValue>>>();
    }

    public Task<TValue> this[TKey key]
    {
        get
        {
            if (key == null) throw new ArgumentNullException("key");
            return _map.GetOrAdd(key, toAdd =>
                new Lazy<Task<TValue>>(() => _valueFactory(toAdd))).Value;
        }
    }
}
```

 La clase [AsyncCache\<TKey, TValue >](https://devblogs.microsoft.com/pfxteam/parallelextensionsextras-tour-12-asynccache/) acepta como un delegado a su constructor una función que adopta `TKey` y devuelve una clase <xref:System.Threading.Tasks.Task%601>.  Todos los valores a los que se accedió previamente desde la memoria caché se almacenan en el diccionario interno y `AsyncCache` asegura que solo una tarea se genera por clave, incluso si se tiene acceso a la memoria caché al mismo tiempo.

 Por ejemplo, puede crear una caché de páginas web descargadas:

```csharp
private AsyncCache<string,string> m_webPages =
    new AsyncCache<string,string>(DownloadStringAsync);
```

 Después puede utilizar esta caché en métodos asincrónicos siempre que necesite el contenido de una página web. La clase `AsyncCache` garantiza que está descargando el menor número de páginas posible y almacena en caché los resultados.

```csharp
private async void btnDownload_Click(object sender, RoutedEventArgs e)
{
    btnDownload.IsEnabled = false;
    try
    {
        txtContents.Text = await m_webPages["https://www.microsoft.com"];
    }
    finally { btnDownload.IsEnabled = true; }
}
```

### <a name="asyncproducerconsumercollection"></a>AsyncProducerConsumerCollection
 También puede usar tareas para crear estructuras de datos para la coordinación de actividades asincrónicas.  Considere uno de los patrones de diseño paralelo clásico: productor-consumidor.  En este patrón, los productores generan datos consumidos por los consumidores, y los productores y los consumidores pueden ejecutarlos en paralelo. Por ejemplo, el consumidor procesa el elemento 1, que fue generado previamente por un productor que ahora está produciendo el elemento 2.  Para el modelo productor-consumidor, necesita invariablemente alguna estructura de datos para almacenar los trabajos creados por los productores, para que los consumidores puedan recibir notificaciones de nuevos datos y encontrarlos si están disponibles.

 A continuación se muestra una estructura de datos simple creada sobre las tareas, que permite el uso de métodos asincrónicos como productores y consumidores:

```csharp
public class AsyncProducerConsumerCollection<T>
{
    private readonly Queue<T> m_collection = new Queue<T>();
    private readonly Queue<TaskCompletionSource<T>> m_waiting =
        new Queue<TaskCompletionSource<T>>();

    public void Add(T item)
    {
        TaskCompletionSource<T> tcs = null;
        lock (m_collection)
        {
            if (m_waiting.Count > 0) tcs = m_waiting.Dequeue();
            else m_collection.Enqueue(item);
        }
        if (tcs != null) tcs.TrySetResult(item);
    }

    public Task<T> Take()
    {
        lock (m_collection)
        {
            if (m_collection.Count > 0)
            {
                return Task.FromResult(m_collection.Dequeue());
            }
            else
            {
                var tcs = new TaskCompletionSource<T>();
                m_waiting.Enqueue(tcs);
                return tcs.Task;
            }
        }
    }
}
```

 Con esta estructura de datos en su lugar, puede escribir código como el siguiente:

```csharp
private static AsyncProducerConsumerCollection<int> m_data = …;
…
private static async Task ConsumerAsync()
{
    while(true)
    {
        int nextItem = await m_data.Take();
        ProcessNextItem(nextItem);
    }
}
…
private static void Produce(int data)
{
    m_data.Add(data);
}
```

El espacio de nombres <xref:System.Threading.Tasks.Dataflow> incluye el tipo <xref:System.Threading.Tasks.Dataflow.BufferBlock%601>, que se puede usar de forma similar, pero sin tener que crear un tipo de colección personalizado:

```csharp
private static BufferBlock<int> m_data = …;
…
private static async Task ConsumerAsync()
{
    while(true)
    {
        int nextItem = await m_data.ReceiveAsync();
        ProcessNextItem(nextItem);
    }
}
…
private static void Produce(int data)
{
    m_data.Post(data);
}
```

> [!NOTE]
> El espacio de nombres <xref:System.Threading.Tasks.Dataflow> está disponible en .NET Framework 4.5 mediante **NuGet**. Para instalar el ensamblado que contiene el espacio de nombres <xref:System.Threading.Tasks.Dataflow>, abra el proyecto en Visual Studio, elija **Administrar paquetes NuGet** en el menú Proyecto y busque en línea el paquete Microsoft.Tpl.Dataflow.

## <a name="see-also"></a>Vea también

- [Modelo asincrónico basado en tareas [TAP]](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)
- [Implementar el modelo asincrónico basado en tareas](../../../docs/standard/asynchronous-programming-patterns/implementing-the-task-based-asynchronous-pattern.md)
- [Interoperabilidad con otros tipos y patrones asincrónicos](../../../docs/standard/asynchronous-programming-patterns/interop-with-other-asynchronous-patterns-and-types.md)
