---
title: "Utilizar el modelo asincrónico basado en tareas"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .NET Framework, and TAP
- asynchronous design patterns, .NET Framework
- TAP, .NET Framework support for
- Task-based Asynchronous Pattern, .NET Framework support for
- .NET Framework, asynchronous design patterns
ms.assetid: 033cf871-ae24-433d-8939-7a3793e547bf
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 90b2a36f0e6bf06b0fefe2191d5b17c9c07d1588
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="consuming-the-task-based-asynchronous-pattern"></a>Utilizar el modelo asincrónico basado en tareas
Cuando se utiliza el modelo asincrónico basado en tareas (TAP) para trabajar con operaciones asincrónicas, puede utilizar las devoluciones de llamada para conseguir esperas sin bloqueos.  Para las tareas, esto se logra a través de métodos como <xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=nameWithType>. La compatibilidad asincrónica basada en lenguaje oculta las devoluciones de llamada al permitir que las operaciones asincrónicas se puedan esperar en el flujo de control normal y que el código generado por el compilador proporcione esta misma compatibilidad de nivel de API.  
  
## <a name="suspending-execution-with-await"></a>Suspender la ejecución con Await  
 A partir de la [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], puede usar el [await](~/docs/csharp/language-reference/keywords/await.md) palabra clave de C# y la [operador Await](~/docs/visual-basic/language-reference/operators/await-operator.md) en Visual Basic para esperar de forma asincrónica <xref:System.Threading.Tasks.Task> y <xref:System.Threading.Tasks.Task%601> objetos. Cuando está esperando un <xref:System.Threading.Tasks.Task>, `await` expresión es del tipo `void`. Cuando está esperando un <xref:System.Threading.Tasks.Task%601>, `await` expresión es del tipo `TResult`. Debe producirse una expresión `await` dentro del cuerpo de un método asincrónico. Para más información sobre la compatibilidad del lenguaje C# y Visual Basic en [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], consulte las especificaciones del lenguaje C# y Visual Basic.  
  
 En realidad, la funcionalidad de await instala una devolución de llamada en la tarea mediante una continuación.  Esta devolución de llamada reanuda el método asincrónico en el punto de suspensión. Cuando se reanuda el método asincrónico, si la operación de espera se completó correctamente y fue un <xref:System.Threading.Tasks.Task%601>, sus `TResult` se devuelve.  Si el <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> que se esperó finalizó en el <xref:System.Threading.Tasks.TaskStatus.Canceled> estado, un <xref:System.OperationCanceledException> se produce la excepción.  Si el <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> que se esperó finalizó con el <xref:System.Threading.Tasks.TaskStatus.Faulted> de estado, se produce la excepción que provocó el error. Un objeto `Task` puede producir un error como resultado de múltiples excepciones, pero solo una de estas excepciones se propaga. Sin embargo, el <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> propiedad devuelve un <xref:System.AggregateException> la excepción que contiene todos los errores.  
  
 Si un contexto de sincronización (<xref:System.Threading.SynchronizationContext> objeto) está asociado con el subproceso que se estaba ejecutando el método asincrónico en el momento de suspensión (por ejemplo, si la <xref:System.Threading.SynchronizationContext.Current%2A?displayProperty=nameWithType> propiedad no es `null`), el método asincrónico se reanuda en el que mismo contexto de sincronización mediante el contexto <xref:System.Threading.SynchronizationContext.Post%2A> método. En caso contrario, se basa en el programador de tareas (<xref:System.Threading.Tasks.TaskScheduler> objeto) que era el actual en el momento de suspensión. Normalmente, esto es el programador de tareas predeterminado (<xref:System.Threading.Tasks.TaskScheduler.Default%2A?displayProperty=nameWithType>), que tiene como destino el grupo de subprocesos. El programador de tareas determina si la operación asincrónica en espera debe reanudarse donde ha completado o si se debe programar la reanudación. Normalmente, el programador predeterminado permite que la continuación se ejecute en el subproceso que ha completado la operación de espera.  
  
 Cuando se llama a un método asincrónico, ejecuta sincrónicamente el cuerpo de la función hasta que la primera expresión de espera en una instancia esperable que todavía no se ha completado, momento en el que la invocación se devuelve al llamador. Si el método asincrónico no devuelve `void`, <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> se devuelve el objeto para representar el cálculo en curso. En un método asincrónico no nulo, si se encuentra una instrucción return o se llega al final del cuerpo del método, la tarea se completa en el <xref:System.Threading.Tasks.TaskStatus.RanToCompletion> estado final. Si una excepción no controlada hace que el control a abandonar el cuerpo del método asincrónico, la tarea finaliza en el <xref:System.Threading.Tasks.TaskStatus.Faulted> estado. Si esa excepción es una <xref:System.OperationCanceledException>, en su lugar, la tarea finaliza en el <xref:System.Threading.Tasks.TaskStatus.Canceled> estado. De esta manera, el resultado o excepción se publica finalmente.  
  
 Hay diversas variaciones importantes de este comportamiento.  Por motivos de rendimiento, si ya ha completado una tarea en el momento en que se esperaba, no se obtiene el control y la función continúa ejecutándose.  Además, volver al contexto original no siempre es el comportamiento deseado y se puede cambiar. Esto se describe con más detalle en la sección siguiente.  
  
### <a name="configuring-suspension-and-resumption-with-yield-and-configureawait"></a>Configurar la suspensión y reanudación con Yield y ConfigureAwait  
 Varios métodos proporcionan más control sobre la ejecución de un método asincrónico. Por ejemplo, puede usar el <xref:System.Threading.Tasks.Task.Yield%2A?displayProperty=nameWithType> método introducir un punto de rendimiento en el método asincrónico:  
  
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
  
 También puede usar el <xref:System.Threading.Tasks.Task.ConfigureAwait%2A?displayProperty=nameWithType> método para un mejor control sobre la suspensión y reanudación de un método asincrónico.  Como se mencionó anteriormente, de forma predeterminada, se captura el contexto actual en el momento en que se suspende un método asincrónico, y ese contexto capturado se utiliza para invocar la continuación del método asincrónico tras la reanudación.  En muchos casos, este es el comportamiento exacto que desea.  En otros casos, es posible que no le preocupe el contexto de continuación y puede lograr un mejor rendimiento al evitar dichos registros en el contexto original.  Para habilitar esto, use el <xref:System.Threading.Tasks.Task.ConfigureAwait%2A?displayProperty=nameWithType> método para informar a la operación await no para capturar y reanudar en el contexto, pero continuar ejecución siempre que completar la operación asincrónica que se está esperó:  
  
```csharp  
await someTask.ConfigureAwait(continueOnCapturedContext:false);  
```  
  
## <a name="canceling-an-asynchronous-operation"></a>Cancelar una operación asincrónica  
 A partir de la [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], métodos de TAP que admiten la cancelación proporcionan al menos una sobrecarga que acepta un token de cancelación (<xref:System.Threading.CancellationToken> objeto).  
  
 Se crea un token de cancelación a través de un origen de token de cancelación (<xref:System.Threading.CancellationTokenSource> objeto).  El origen <xref:System.Threading.CancellationTokenSource.Token%2A> propiedad devuelve el token de cancelación se señalará cuando el origen <xref:System.Threading.CancellationTokenSource.Cancel%2A> se llama al método.  Por ejemplo, si desea descargar una única página Web y desea poder cancelar la operación, cree un <xref:System.Threading.CancellationTokenSource> de objetos, pasar su token para el método de TAP y, a continuación, llame a la fuente <xref:System.Threading.CancellationTokenSource.Cancel%2A> método cuando esté listo para cancelar la operación:  
  
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
  
 Puede pasar el <xref:System.Threading.CancellationToken.None%2A?displayProperty=nameWithType> valor a cualquier método que acepta un token de cancelación para indicar que nunca se le solicitó la cancelación.  Esto hace que la <xref:System.Threading.CancellationToken.CanBeCanceled%2A?displayProperty=nameWithType> propiedad para devolver `false`, y el método llamado pueda optimizar en consecuencia.  Con fines de prueba, también puede pasar un token de cancelación cancelado previamente cuyas instancias se crean mediante el constructor que acepta un valor booleano para indicar si el token debe iniciarse en un estado ya cancelado o que no se puede cancelar.  
  
 Este enfoque de cancelación tiene varias ventajas:  
  
-   Puede pasar el mismo token de cancelación a cualquier número de operaciones sincrónicas y asincrónicas.  
  
-   La misma solicitud de cancelación puede extenderse a cualquier número de agentes de escucha.  
  
-   El desarrollador de la API asincrónica tiene todo el control de si se puede solicitar la cancelación y cuándo puede surtir efecto.  
  
-   El código que utiliza la API puede determinar de forma selectiva las llamadas asincrónicas que se propagarán las solicitudes de cancelación.  
  
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
 El <xref:System.Threading.Tasks> espacio de nombres incluye varios métodos para crear y trabajar con tareas.  
  
### <a name="taskrun"></a>Task.Run  
 El <xref:System.Threading.Tasks.Task> clase incluye varios <xref:System.Threading.Tasks.Task.Run%2A> métodos que le permiten descargar de trabajo como un <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> al grupo de subprocesos, por ejemplo:  
  
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
  
 Algunas de estas <xref:System.Threading.Tasks.Task.Run%2A> métodos, como el <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=nameWithType> sobrecarga, existen como método abreviado para el <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType> método.  Otras sobrecargas, como <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=nameWithType>, habilitar usar await dentro del trabajo descargado, por ejemplo:  
  
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
  
 Estas sobrecargas están lógicamente equivalentes a de la <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType> método junto con el <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> método de extensión en Task Parallel Library.  
  
### <a name="taskfromresult"></a>Task.FromResult  
 Use la <xref:System.Threading.Tasks.Task.FromResult%2A> método en escenarios donde los datos pueden resultar ya está disponible y sólo debe devolverse desde un método de devolución de tarea que se soluciona en un <xref:System.Threading.Tasks.Task%601>:  
  
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
 Use la <xref:System.Threading.Tasks.Task.WhenAll%2A> método para esperar en varias operaciones asincrónicas que se representan como tareas de forma asincrónica.  El método tiene varias sobrecargas que admiten un conjunto de tareas no genéricas o un conjunto no uniforme de tareas genéricas (por ejemplo, esperando de forma asincrónica varias operaciones que devuelven void o esperando de forma asincrónica varios métodos que devuelven valores, donde cada valor puede tener un tipo diferente) y para admitir un conjunto uniforme de tareas genéricas (como esperar de forma asincrónica para varios métodos que devuelven `TResult`).  
  
 Supongamos que desea enviar mensajes de correo electrónico a varios clientes. Puede superponer el envío de los mensajes, para que no esté esperando que se complete un mensaje antes de enviar el siguiente. También puede averiguar cuando se completan las operaciones de envío y si se ha producido algún error:  
  
```csharp  
IEnumerable<Task> asyncOps = from addr in addrs select SendMailAsync(addr);  
await Task.WhenAll(asyncOps);  
```  
  
 Este código no controla explícitamente las excepciones que pueden aparecer, pero permite que las excepciones se propagan fuera de la `await` en la tarea resultante de <xref:System.Threading.Tasks.Task.WhenAll%2A>.  Para controlar las excepciones, puede utilizar código como el siguiente:  
  
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
  
 En este caso, si se produce un error en cualquier operación asincrónica, todas las excepciones se consolidará en un <xref:System.AggregateException> excepción, que se almacena en la <xref:System.Threading.Tasks.Task> que se devuelve desde el <xref:System.Threading.Tasks.Task.WhenAll%2A> método.  Sin embargo, solo una de esas excepciones se propaga por la palabra clave `await`.  Si desea examinar todas las excepciones, puede volver a escribir el código anterior como sigue:  
  
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
 Puede usar el <xref:System.Threading.Tasks.Task.WhenAny%2A> método para esperar de forma asincrónica con una sola de varias operaciones asincrónicas se representa como tareas en completarse.  Este método actúa en cuatro casos de uso principales:  
  
-   Redundancia: realizar una operación varias veces y seleccionar la que se complete primero (por ejemplo, ponerse en contacto con varios servicios web de cotización bursátil que va a generar un único resultado y seleccionar la que se completa con más rapidez).  
  
-   Intercalación: iniciar varias operaciones y esperar que se completen todas, pero procesarlas a medida que se completan.  
  
-   Limitación: permitir que operaciones adicionales comiencen a medida que otras se completan.  Esto es una extensión del escenario de intercalación.  
  
-   Cese de hash temprano: por ejemplo, una operación representada por la tarea t1 se puede agrupar en un <xref:System.Threading.Tasks.Task.WhenAny%2A> tarea con otra tarea t2 así puede esperar en la <xref:System.Threading.Tasks.Task.WhenAny%2A> tarea. La tarea t2 puede representar un tiempo de espera, o cancelación o algunos otros tipos de señales que provoca la <xref:System.Threading.Tasks.Task.WhenAny%2A> tarea se complete antes de que finalice de t1.  
  
#### <a name="redundancy"></a>Redundancia  
 Considere un caso en el que quiera tomar la decisión de comprar o no una acción.  Hay varios servicios web de recomendación bursátil en los que confía, pero según la carga diaria, cada servicio puede acabar ralentizándose en momentos diferentes.  Puede usar el <xref:System.Threading.Tasks.Task.WhenAny%2A> método para recibir una notificación cuando se complete cualquier operación:  
  
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
  
 A diferencia de <xref:System.Threading.Tasks.Task.WhenAll%2A>, que devuelve los resultados de todas las tareas que ha realizado correctamente, sin ajustar <xref:System.Threading.Tasks.Task.WhenAny%2A> devuelve la tarea completada. Si se produce un error en una tarea, es importante saber que se produjo un error y, si una tarea se realiza correctamente, es importante saber con qué tarea está asociado el valor devuelto.  Por lo tanto, necesitará acceder al resultado de la tarea devuelta o esperarla aún más, tal como se muestra en este ejemplo.  
  
 Al igual que con <xref:System.Threading.Tasks.Task.WhenAll%2A>, tendrá que ser capaz de dar cabida a excepciones.  Dado que recibe de vuelta la tarea de completa, puede esperar que se hayan propagado los errores en la tarea devuelta y `try/catch` adecuadamente; por ejemplo:  
  
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
  
 Además, aunque una primera tarea se complete correctamente, las tareas subsiguientes pueden producir un error.  En este punto, tiene varias opciones para controlar las excepciones: puede esperar a que se han completado todas las tareas iniciadas, en cuyo caso puede utilizar el <xref:System.Threading.Tasks.Task.WhenAll%2A> método, también puede decidir que todas las excepciones son importantes y deben haber iniciado sesión.  Para ello, puede usar las continuaciones para recibir una notificación cuando se hayan completado las tareas de forma asincrónica:  
  
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
  
```  
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
  
 También puede aplicar una intercalación a un escenario que implica un procesamiento muy intenso computacional en el <xref:System.Threading.ThreadPool> de las imágenes descargadas; por ejemplo:  
  
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
  
 Otro ejemplo de cese de hash temprano implica el uso de la <xref:System.Threading.Tasks.Task.WhenAny%2A> método junto con el <xref:System.Threading.Tasks.Task.Delay%2A> método, como se describe en la sección siguiente.  
  
### <a name="taskdelay"></a>Task.Delay  
 Puede usar el <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> método para presentar a los que se hace una pausa en la ejecución de un método asincrónico.  Esto es útil para muchos tipos de funcionalidad, incluida la generación de bucles de sondeo y el retraso del control de entrada de usuario durante un período predeterminado.  El <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> método también puede ser útil en combinación con <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> para implementar los tiempos de espera en espera.  
  
 Si una tarea que forma parte de una operación asincrónica mayor (por ejemplo, un servicio web ASP.NET) tarda demasiado tiempo en completarse, la operación global podría verse afectada, especialmente si no se puede completar.  Por este motivo, es importante poder agotar el tiempo de espera al esperar a una operación asincrónica.  Sincrónico <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Task.WaitAll%2A?displayProperty=nameWithType>, y <xref:System.Threading.Tasks.Task.WaitAny%2A?displayProperty=nameWithType> métodos aceptan valores de tiempo de espera, pero la correspondiente <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A?displayProperty=nameWithType> / <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> y mencionados anteriormente <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> / <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>métodos no lo hace.  En su lugar, puede usar <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> y <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> en combinación para implementar un tiempo de espera.  
  
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
 En muchas situaciones, puede querer reintentar la operación si se produce un error en un intento anterior.  Para el código sincrónico, podría crear un método auxiliar como `RetryOnFault` en el ejemplo siguiente para lograr esto:  
  
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
  
 Puede crear un método auxiliar prácticamente idéntico para las operaciones asincrónicas que se implementan con TAP y, por tanto, devolver las tareas:  
  
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
 A veces, puede sacar partido de la redundancia para mejorar la latencia y las posibilidades de éxito de una operación.  Considere la posibilidad de varios servicios web que proporcionan cotizaciones bursátiles, pero a lo largo del día cada servicio puede proporcionar diferentes niveles de calidad y tiempos de respuesta.  Para tratar estas fluctuaciones, pueden emitir solicitudes a todos los servicios web y tan pronto como obtiene una respuesta de uno, cancelar las solicitudes restantes.  Puede implementar una función auxiliar para que resulte más fácil de implementar este patrón común de iniciar varias operaciones, esperar alguna y, después, cancelar el resto. La función `NeedOnlyOne` del ejemplo siguiente muestra este escenario:  
  
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
 Hay un posible problema de rendimiento con el uso de la <xref:System.Threading.Tasks.Task.WhenAny%2A> método para admitir un escenario de intercalación cuando se trabaja con grandes conjuntos de tareas.  Todas las llamadas a <xref:System.Threading.Tasks.Task.WhenAny%2A> da como resultado una continuación que se va a registrar con cada tarea. Para el número N de tareas, el resultado de O(N2) continuaciones creadas durante la vigencia de la operación de intercalación.  Si está trabajando con un gran conjunto de tareas, puede utilizar un combinador (`Interleaved` en el ejemplo siguiente) para solucionar el problema de rendimiento:  
  
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
 Además de la capacidad para generar combinadores basado en tareas personalizadas, que tienen una estructura de datos en <xref:System.Threading.Tasks.Task> y <xref:System.Threading.Tasks.Task%601> que representa tanto los resultados de una operación asincrónica y la sincronización necesaria para unirse a él resulta muy eficaz Escriba en el que se va a crear estructuras de datos personalizadas para su uso en escenarios asincrónicos.  
  
### <a name="asynccache"></a>AsyncCache  
 Un aspecto importante de una tarea es que se puede transferir a varios consumidores, todos los cuales pueden esperar a que finalice, las continuaciones de registro con él, obtener su resultado o excepciones (en el caso de <xref:System.Threading.Tasks.Task%601>), y así sucesivamente.  Esto hace que <xref:System.Threading.Tasks.Task> y <xref:System.Threading.Tasks.Task%601> perfectamente adecuado para su uso en una infraestructura de almacenamiento en caché asincrónica.  Este es un ejemplo de una pequeña pero eficaz caché asincrónica construidos sobre <xref:System.Threading.Tasks.Task%601>:  
  
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
  
 El [AsyncCache\<TKey, TValue >](http://go.microsoft.com/fwlink/p/?LinkId=251941) clase acepta como un delegado a su constructor una función que toma un `TKey` y devuelve un <xref:System.Threading.Tasks.Task%601>.  Todos los valores a los que se accedió previamente desde la memoria caché se almacenan en el diccionario interno y `AsyncCache` asegura que solo una tarea se genera por clave, incluso si se tiene acceso a la memoria caché al mismo tiempo.  
  
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
        txtContents.Text = await m_webPages["http://www.microsoft.com"];  
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
  
 El <xref:System.Threading.Tasks.Dataflow> espacio de nombres incluye las <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> tipo, que puede usar de forma similar, pero sin tener que crear un tipo de colección personalizado:  
  
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
>  El <xref:System.Threading.Tasks.Dataflow> espacio de nombres está disponible en la [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] a través de **NuGet**. Para instalar el ensamblado que contiene el <xref:System.Threading.Tasks.Dataflow> espacio de nombres, abra el proyecto en [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], elija **administrar paquetes de NuGet** en el menú proyecto y busque en línea el paquete Microsoft.Tpl.Dataflow.  
  
## <a name="see-also"></a>Vea también  
 [Task-based Asynchronous Pattern (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) (Modelo asincrónico basado en tareas [TAP])  
 [Implementar el modelo asincrónico basado en tareas](../../../docs/standard/asynchronous-programming-patterns/implementing-the-task-based-asynchronous-pattern.md)  
 [Interoperabilidad con otros tipos y patrones asincrónicos](../../../docs/standard/asynchronous-programming-patterns/interop-with-other-asynchronous-patterns-and-types.md)
