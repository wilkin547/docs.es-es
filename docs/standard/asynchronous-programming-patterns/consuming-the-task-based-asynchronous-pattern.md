---
title: "Consuming the Task-based Asynchronous Pattern | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - ".NET Framework, and TAP"
  - "asynchronous design patterns, .NET Framework"
  - "TAP, .NET Framework support for"
  - "Task-based Asynchronous Pattern, .NET Framework support for"
  - ".NET Framework, asynchronous design patterns"
ms.assetid: 033cf871-ae24-433d-8939-7a3793e547bf
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Consuming the Task-based Asynchronous Pattern
Cuando se utiliza el patrón asincrónico basado en tareas \(TAP\) para ejecutar operaciones asincrónicas, se pueden utilizar devoluciones de llamada para conseguir esperas sin bloqueos.  Para las tareas, esto se logra con métodos como <xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=fullName>.  La compatibilidad asincrónica basada en lenguajes oculta devoluciones de llamada al permitir que las operaciones asincrónicas sean esperadas dentro del flujo de control normal y el código generado por el compilador proporcione esta misma compatibilidad a nivel de API.  
  
## Suspender la ejecución con Await  
 Empezando con [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], se puede utilizar la palabra clave [await](../Topic/await%20\(C%23%20Reference\).md) en C\# y [Await \(Operador\)](../Topic/Await%20Operator%20\(Visual%20Basic\).md) en Visual Basic para esperar asincrónicamente a <xref:System.Threading.Tasks.Task> y a los objetos <xref:System.Threading.Tasks.Task%601>.  Cuando se está esperando una <xref:System.Threading.Tasks.Task>, la expresión `await` es de tipo `void`.  Cuando se está esperando una <xref:System.Threading.Tasks.Task%601>, la expresión `await` es de tipo `TResult`.  Una expresión `await` debe aparecer en el cuerpo de un método asincrónico.  Para obtener más información sobre la compatibilidad del lenguaje C\# y Visual Basic en [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], consulte las especificaciones del lenguaje C\# y Visual Basic.  
  
 Más en detalle, la función de espera instala una devolución de llamada en la tarea mediante una continuación.  Esta devolución de llamada reanuda el método asincrónico en el momento de suspensión.  Cuando se reanuda el método asincrónico, si la operación en espera se completa correctamente y fue <xref:System.Threading.Tasks.Task%601>, se devuelve su `TResult`.  Si <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> esperado terminó en el estado <xref:System.Threading.Tasks.TaskStatus>, se lanza una excepción <xref:System.OperationCanceledException>.  Si <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> esperado terminó en el estado <xref:System.Threading.Tasks.TaskStatus>, se lanza la excepción que produjo el error.  `Task` puede darse como resultado de varias excepciones, pero sólo una de estas excepciones se propaga.  Sin embargo, la propiedad <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=fullName> devuelve una excepción <xref:System.AggregateException> que contiene todos los errores.  
  
 Si un contexto de sincronización \(objeto<xref:System.Threading.SynchronizationContext>\) está asociado al subproceso que estaba ejecutando el método asincrónico en el momento de la suspensión \(por ejemplo, si la propiedad <xref:System.Threading.SynchronizationContext.Current%2A?displayProperty=fullName> no es `null`\), el método asincrónico se reanuda en el mismo contexto de sincronización utilizando el método <xref:System.Threading.SynchronizationContext.Post%2A> del contexto.  De lo contrario, se basa en el programador de tareas \(objeto<xref:System.Threading.Tasks.TaskScheduler>\) que estaba en curso en el momento de la suspensión.  Normalmente, éste es el programador de tareas predeterminado \(<xref:System.Threading.Tasks.TaskScheduler.Default%2A?displayProperty=fullName>\), que tiene como destino el grupo de subprocesos.  Este programador de tareas determina si la operación asincrónica esperada debe reanudarse donde se completó o si la reanudación debe programarse.  El programador predeterminado suele permitir que la continuación se ejecute en el subproceso que la operación en espera completó.  
  
 Cuando se invoca un método asincrónico, se ejecuta sincrónicamente el cuerpo de la función hasta la primera expresión en espera de una instancia esperable que aún no se ha completado, punto en el que la invocación vuelve al llamador.  Si el método asincrónico no devuelve `void`, se devuelve un objeto <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> para representar el cálculo en curso.  En un método asincrónico que no es void, si se encuentra una instrucción de retorno, o se alcanza el final del cuerpo del método, la tarea se completa en el estado final <xref:System.Threading.Tasks.TaskStatus>.  Si una excepción no controlada hace que el control deje el cuerpo del método asincrónico, la tarea termina en el estado <xref:System.Threading.Tasks.TaskStatus>.  Si la excepción es <xref:System.OperationCanceledException>, la tarea finaliza en el estado <xref:System.Threading.Tasks.TaskStatus>.  De esta manera, el resultado o la excepción se publican finalmente.  
  
 Hay muchas variaciones importantes de este comportamiento.  Por razones de rendimiento, si una tarea ya se ha completado cuando se espera, el control no se cede y la función sigue ejecutándose.  Además, volver al contexto original no siempre es el comportamiento deseado y se puede modificar; esto se describe con más detalle en la sección siguiente.  
  
### Configurar la suspension y reanudación con Yield y ConfigureAwait  
 Varios son los métodos que proporcionan mayor control sobre la ejecución de un método asincrónico.  Por ejemplo, se puede utilizar el método <xref:System.Threading.Tasks.Task.Yield%2A?displayProperty=fullName> para incluir un punto de producción en el método asincrónico:  
  
```csharp  
public class Task : …  
{  
    public static YieldAwaitable Yield();  
    …  
}  
  
```  
  
 Esto es equivalente a enviar de forma asincrónica o a programar de nuevo el contexto actual.  
  
```csharp  
Task.Run(async  delegate  
{  
    for(int i=0; i<1000000; i++)  
    {  
        await Task.Yield(); // fork the continuation into a separate work item  
        ...  
    }  
});  
  
```  
  
 También se puede utilizar el método <xref:System.Threading.Tasks.Task.ConfigureAwait%2A?displayProperty=fullName> para un mejor control sobre la suspensión y la reanudación de un método asincrónico.  Como se mencionó anteriormente, de forma predeterminada, el contexto actual se capturan cuando se suspende un método asincrónico, y ese contexto capturado se utiliza para invocar la continuación del método asincrónico sobre la reanudación.  En muchos casos, éste es el comportamiento exacto que se desea.  En otros casos, puede no interesar saber el contexto de continuación y se puede mejorar el rendimiento si se evita que tales elementos vuelvan al contexto original.  Para habilitar esto, utilice el método <xref:System.Threading.Tasks.Task.ConfigureAwait%2A?displayProperty=fullName> para informar a la operación en espera de que no capture ni reanude el contexto, sino que continúe la ejecución siempre que la operación asincrónica en espera se complete:  
  
```csharp  
await someTask.ConfigureAwait(continueOnCapturedContext:false);  
  
```  
  
## Cancelar una operación asincrónica  
 Empezando con [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], los métodos TAP que admiten cancelación proporcionan al menos una sobrecarga que acepta un token de cancelación \(objeto<xref:System.Threading.CancellationToken> \).  
  
 El token de cancelación se crea desde el origen de tokens de cancelación \(objeto<xref:System.Threading.CancellationTokenSource> \).  La propiedad <xref:System.Threading.CancellationTokenSource.Token%2A> del origen devuelve el token de cancelación que se notificará cuando se llame al método <xref:System.Threading.CancellationTokenSource.Cancel%2A> del origen.  Por ejemplo, si se desea descargar una sola página web y poder cancelar la operación, se crea un objeto <xref:System.Threading.CancellationTokenSource>, se pasa el token al método TAP y después se llama al método <xref:System.Threading.CancellationTokenSource.Cancel%2A> cuando esté preparado para cancelar la operación:  
  
```csharp  
var cts = new CancellationTokenSource();  
string result = await DownloadStringAsync(url, cts.Token);  
… // at some point later, potentially on another thread  
cts.Cancel();  
  
```  
  
 Para cancelar llamadas asincrónicas múltiples, se puede pasar el mismo token a todas las invocaciones:  
  
```csharp  
var cts = new CancellationTokenSource();  
    IList<string> results = await Task.WhenAll(from url in urls select DownloadStringAsync(url, cts.Token));  
    // at some point later, potentially on another thread  
    …  
    cts.Cancel();  
  
```  
  
 O bien, se puede pasar el mismo token a un subconjunto selectivo de operaciones:  
  
```csharp  
var cts = new CancellationTokenSource();  
    byte [] data = await DownloadDataAsync(url, cts.Token);  
    await SaveToDiskAsync(outputPath, data, CancellationToken.None);  
    … // at some point later, potentially on another thread  
    cts.Cancel();  
  
```  
  
 Las solicitudes de cancelación se pueden iniciar desde cualquier subproceso.  
  
 Se puede pasar el valor <xref:System.Threading.CancellationToken.None%2A?displayProperty=fullName> a cualquier método que acepte un token de cancelación para indicar que la cancelación nunca se solicitará.  Esto hace que la propiedad <xref:System.Threading.CancellationToken.CanBeCanceled%2A?displayProperty=fullName> devuelva `false` y consiguientemente el método llamado pueda optimizarse.  Con fines de prueba, también se puede pasar un token precancelado de cancelación del que se creen instancias utilizando el constructor que acepta un valor booleano para indicar si el token debería comenzar en un estado ya cancelado o no cancelable.  
  
 Este tratamiento de la cancelación tiene varias ventajas:  
  
-   Se puede pasar el mismo token de cancelación a cualquier número de operaciones asincrónicas o sincrónicas.  
  
-   La misma solicitud de cancelación puede extenderse a cualquier número de oyentes.  
  
-   El desarrollador de la API asincrónica tiene completo control de si la cancelación puede ser solicitada y cuándo puede tener lugar.  
  
-   El consumidor de la API puede determinar selectivamente las llamadas asincrónicas a las que las solicitudes de cancelación se propagarán.  
  
## Supervisar el progreso  
 Algunos métodos asincrónicos presentan su progreso a través de una interfaz de progreso que pasa por el método asincrónico.  Por ejemplo, piense en una función que de forma asincrónica descarga una cadena de texto y en el camino provoca actualizaciones de progreso que incluyen el porcentaje de descarga que se ha completado hasta el momento.  Este método se puede utilizar en una aplicación de Windows Presentation Foundation \(WPF\) como se indica a continuación:  
  
```csharp  
private async  void btnDownload_Click(object sender, RoutedEventArgs e)    
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
## Utilizar los elementos de combinación basados en tareas integradas  
 El espacio de nombres <xref:System.Threading.Tasks> incluye varios métodos para componer y trabajar con tareas.  
  
### Task.Run  
 La clase <xref:System.Threading.Tasks.Task> incluye varios métodos <xref:System.Threading.Tasks.Task.Run%2A> que permiten con facilidad librarse de trabajo como un <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> al grupo de subprocesos, por ejemplo:  
  
```csharp  
public async  void button1_Click(object sender, EventArgs e)  
{  
    textBox1.Text = await Task.Run(() =>  
    {  
        // … do compute-bound work here  
        return answer;  
    });  
}  
  
```  
  
 Algunos de estos métodos <xref:System.Threading.Tasks.Task.Run%2A> tales como la sobrecarga de <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=fullName> existen como una versión reducida del método <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=fullName>.  Otras sobrecargas, como <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=fullName>, permiten que la espera se utilice dentro del trabajo descargado, por ejemplo:  
  
```csharp  
public async  void button1_Click(object sender, EventArgs e)  
{  
    pictureBox1.Image = await Task.Run(async() =>  
    {  
        using(Bitmap bmp1 = await DownloadFirstImageAsync())  
        using(Bitmap bmp2 = await DownloadSecondImageAsync())  
        return Mashup(bmp1, bmp2);  
    });  
}  
```  
  
 Dichas sobrecargas son lógicamente equivalentes a utilizar el método <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=fullName> en conjunción con el método de extensión <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> en la biblioteca de tareas paralelas.  
  
### Task.FromResult  
 Para esos escenarios en los que los datos pueden estar ya disponibles y simplemente necesitan ser devueltos desde un método que devuelve tareas subido en un <xref:System.Threading.Tasks.Task.FromResult%2A>, el método <xref:System.Threading.Tasks.Task%601> puede ser utilizado:  
  
```csharp  
public Task<int> GetValueAsync(string key)  
{  
    int cachedValue;  
    return TryGetCachedValue(out cachedValue) ?  
        Task.FromResult(cachedValue) :  
        GetValueAsyncInternal();  
}  
  
private async  Task<int> GetValueAsyncInternal(string key)  
{  
    …  
}  
  
```  
  
### Task.WhenAll  
 Utilice el método <xref:System.Threading.Tasks.Task.WhenAll%2A> de forma asincrónica para atender varias operaciones asincrónicas que se representan como tareas.  El método tiene múltiples sobrecargas que admiten un conjunto de tareas no genéricas o un conjunto no uniforme de tareas genéricas \(por ejemplo, tareas que esperan asincrónicamente varias operaciones de retorno tipo void, o tareas que esperan asincrónicamente múltiples métodos de valores de retorno en los que cada valor puede ser de diferente tipo\) así como también admiten un conjunto uniforme de tareas genéricas \(tales como esperar asincrónicamente varios métodos de retorno `TResult`\).  
  
 Digamos que se desea enviar un correo electrónico a varios clientes  Se puede solapar el envío de mensajes para que no se tenga que esperar a que un mensaje se complete antes de enviar el siguiente.  También se puede averiguar qué operaciones de envío se han completado y si se ha producido algún error.  
  
```csharp  
IEnumerable<Task> asyncOps = from addr in addrs select SendMailAsync(addr);  
await Task.WhenAll(asyncOps);  
  
```  
  
 Este código no controla explícitamente las excepciones que se pueden producir, sino que permite que las excepciones se propaguen fuera de `await` en la tarea resultante de <xref:System.Threading.Tasks.Task.WhenAll%2A>.  Para controlar las excepciones, se puede usar el siguiente código:  
  
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
  
 En este caso, si una operación asincrónica da error, todas las excepciones se consolidarán en una excepción <xref:System.AggregateException>, que se almacena en <xref:System.Threading.Tasks.Task> que se devuelve desde el método <xref:System.Threading.Tasks.Task.WhenAll%2A>.  Sin embargo, sólo una de esas excepciones se propaga por la palabra clave `await` .  Si se desean examinar todas las excepciones, se puede volver a escribir el código anterior como sigue:  
  
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
  
 Considere el caso de cómo descargar varios archivos de la web de forma asincrónica.  En este caso, todas las operaciones asincrónicas tienen tipos de resultado homogéneos y el acceso a los resultados es simple:  
  
```csharp  
string [] pages = await Task.WhenAll(  
    from url in urls select DownloadStringAsync(url));  
```  
  
 Como en el caso anterior que se devuelve void, las mismas técnicas de control de excepciones se pueden utilizar aquí:  
  
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
  
### Task.WhenAny  
 Se puede usar el método <xref:System.Threading.Tasks.Task.WhenAny%2A> para esperar de forma asincrónica a una de las múltiples operaciones asincrónicas representadas como tareas a completar.  Este método tiene cuatro usos principales:  
  
-   Redundancia:  Realizando varias veces una operación y seleccionando el que complete primero \(por ejemplo, contactando servicios web varias de cita común que generarán un solo resultado y la selección de que completa el más rápido\).  
  
-   El intercalación:  Iniciar varias operaciones y esperar todos de completar, pero procesarlos como completa.  
  
-   La restricción:  Permitir que las operaciones adicionales comienzan con otras completadas.  Esto es una extensión del escenario de intercalado.  
  
-   Desalojo urgente a:  Por ejemplo, una operación representada por T1 de la tarea se puede agrupar en una tarea de <xref:System.Threading.Tasks.Task.WhenAny%2A> con otro t2 de tarea, y puede esperar a la tarea de <xref:System.Threading.Tasks.Task.WhenAny%2A> .  La tarea t2 podría representar un tiempo de espera, o cancelación, o alguna otra señal que haga que la tarea <xref:System.Threading.Tasks.Task.WhenAny%2A> se complete antes de completarse t1.  
  
#### Redundancia  
 Considere un caso en el que se desea tomar una decisión sobre si adquirir un valor o no.  Hay varios servicios web de recomendación de valores en los que se confía, pero dependiendo de la carga diaria, cada uno de los servicios puede resultar bastante lento en momentos diferentes.  Se puede usar el método <xref:System.Threading.Tasks.Task.WhenAny%2A> para recibir una notificación cuando cualquier operación se complete:  
  
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
  
 A diferencia de <xref:System.Threading.Tasks.Task.WhenAll%2A>, que devuelve los resultados empaquetados de todas las tareas que se completan correctamente, <xref:System.Threading.Tasks.Task.WhenAny%2A> devuelve la tarea que se completó.  Si una tarea da error, es importante saber dónde está el error, y si acaba correctamente, es importante saber a qué tarea está asociada el valor devuelto.  Por consiguiente, necesita tener acceso al resultado de la tarea devuelta, o la espera aún más, como en este ejemplo.  
  
 Al igual que con <xref:System.Threading.Tasks.Task.WhenAll%2A>, se necesita poder alojar excepciones.  Debido a que se recibe de vuelta la tarea completada, se puede esperar que la tarea devuelta tenga los errores propagados, y hacer `try/catch` sobre estos correctamente; por ejemplo:  
  
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
  
 Además, aún en el caso de que una primera tarea se complete correctamente, las tareas posteriores pueden producir errores.  En este punto, tiene varias opciones para trabajar con excepciones:  Puede esperar hasta que todas las tareas iniciadas han completado, en cuyo caso puede utilizar el método de <xref:System.Threading.Tasks.Task.WhenAll%2A> , o puede decidir que todas las excepciones son importantes y debe registrarse.  Para ello, se pueden utilizar directamente las continuaciones para recibir una notificación cuando las tareas estén completadas de forma asincrónica:  
  
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
private static async  void LogCompletionIfFailed(IEnumerable<Task> tasks)  
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
  
 Finalmente, se puede desear cancelar todas las operaciones restantes.  
  
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
  
#### Intercalado  
 Considere el caso en el que se descarguen imágenes de la web y se procese cada imagen \(por ejemplo, agregar la imagen a un control de UI\).  Se tiene que hacer el procesado secuencialmente en el subproceso de UI, pero se desea que las imágenes se descarguen de forma simultánea en la medida de lo posible.  Además, no se desea esperar a agregar las imágenes a la UI hasta que se hayan descargado todas \(se desean agregar a medida que se completan\):  
  
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
  
 El mismo intercalado también se puede aplicar a un escenario que implica procesamiento de cómputo intensivo en el <xref:System.Threading.ThreadPool> de imágenes descargadas; por ejemplo:  
  
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
  
#### Limitación de peticiones  
 Piense en el ejemplo de intercalado, excepto que el usuario ahora está descargando tantas imágenes que las descargas necesitan que se limiten explícitamente; por ejemplo, sólo se desea realizar un número específico de descargas simultáneamente.  Para lograr esto, se puede iniciar un subconjunto de las operaciones asincrónicas.  A medida que las operaciones se completan, se pueden iniciar operaciones adicionales para reemplazarlas:  
  
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
  
#### Rescate temprano  
 Considere que se está esperando asincrónicamente que una operación se complete mientras simultáneamente se responde a la solicitud de cancelación de un usuario \(por ejemplo, un usuario hace clic en el botón de cancelación\).  En el siguiente código se muestra este escenario:  
  
```csharp  
private CancellationTokenSource m_cts;   
  
public void btnCancel_Click(object sender, EventArgs e)  
{  
    if (m_cts != null) m_cts.Cancel();  
}  
  
public async  void btnRun_Click(object sender, EventArgs e)  
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
  
private static async  Task UntilCompletionOrCancellation(  
    Task asyncOp, CancellationToken ct)  
{  
    var tcs = new TaskCompletionSource<bool>();  
    using(ct.Register(() => tcs.TrySetResult(true)))  
        await Task.WhenAny(asyncOp, tcs.Task);  
    return asyncOp;  
}  
  
```  
  
 Esta implementación vuelve a habilitar la interfaz de usuario en cuanto decidamos salir pero no cancela las operaciones asincrónicas subyacentes.  Otra alternativa sería cancelar las operaciones pendientes cuando decidamos salir, aunque no se restaure la interfaz de usuario hasta que las operaciones se completen efectivamente, posiblemente por una finalización temprana debido a una solicitud de cancelación:  
  
```csharp  
private CancellationTokenSource m_cts;  
  
public async  void btnRun_Click(object sender, EventArgs e)  
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
  
 Otro ejemplo de rescate temprano implica usar el método <xref:System.Threading.Tasks.Task.WhenAny%2A> junto con el método <xref:System.Threading.Tasks.Task.Delay%2A> como se discute en la siguiente sección.  
  
### Task.Delay  
 Se puede usar el método <xref:System.Threading.Tasks.Task.Delay%2A> para introducir pausas en una ejecución asincrónica del método.  Esto es útil para muchos tipos de funcionalidad, como compilar los bucles de sondeo y retrasar el control de datos proporcionados por el usuario durante un período de tiempo predeterminado.  El método <xref:System.Threading.Tasks.Task.Delay%2A> puede también resultar útil junto con <xref:System.Threading.Tasks.Task.WhenAny%2A> para implementar tiempos de espera.  
  
 Si una tarea que forma parte de una operación asincrónica mayor \(por ejemplo, un servicio web ASP.NET\) tarda demasiado tiempo en completarse, la operación global podría sufrir, especialmente si no llega a completarse nunca.  Por esta razón, es importante poder tener tiempos muertos cuando se espera en una operación asincrónica.  Los métodos sincrónicos <xref:System.Threading.Tasks.Task.Wait%2A>, <xref:System.Threading.Tasks.Task.%2A> WaitAll?qualifyHint=False&autoUpgrade=True y <xref:System.Threading.Tasks.Task.%2A> WaitAny?qualifyHint=False&autoUpgrade=True aceptan valores de tiempo de espera, pero los métodos <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A>\/<xref:System.Threading.Tasks.Task.WhenAny%2A> y el mencionado previamente <xref:System.Threading.Tasks.Task.WhenAll%2A>\/<xref:System.Threading.Tasks.Task.WhenAny%2A> correspondientes no.  En su lugar, se puede usar <xref:System.Threading.Tasks.Task.Delay%2A> y <xref:System.Threading.Tasks.Task.WhenAny%2A> en conjunto para implementar un tiempo de espera.  
  
 Por ejemplo, en la aplicación de interfaz de usuario, digamos que se desea descargar una imagen y deshabilitar la interfaz de usuario mientras se descarga dicha imagen.  Sin embargo, si la descarga lleva mucho tiempo, se desea rehabilitar la interfaz de usuario y la descarga debe descartarse:  
  
```csharp  
public async  void btnDownload_Click(object sender, EventArgs e)  
{  
    btnDownload.Enabled = false;  
    try  
    {  
        Task<Bitmap> download = GetBitmapAsync(url);  
        if (download == await Task.WhenAny(download, Task.Delay(3000)))  
        {  
            Bitmap bmp = await download;  
            pictureBox.Image = bmp;  
            status.Text = “Downloaded”;  
        }  
        else  
        {  
            pictureBox.Image = null;  
            status.Text = “Timed out”;  
            var ignored = download.ContinueWith(  
                t => Trace(“Task finally completed”));  
        }  
    }  
    finally { btnDownload.Enabled = true; }  
}  
  
```  
  
 Lo mismo ocurre con las descargas múltiples, puesto que <xref:System.Threading.Tasks.Task.WhenAll%2A> devuelve una tarea:  
  
```csharp  
public async  void btnDownload_Click(object sender, RoutedEventArgs e)  
{  
    btnDownload.Enabled = false;  
    try  
    {  
        Task<Bitmap[]> downloads =   
            Task.WhenAll(from url in urls select GetBitmapAsync(url));  
        if (downloads == await Task.WhenAny(downloads, Task.Delay(3000)))  
        {  
            foreach(var bmp in downloads) panel.AddImage(bmp);  
            status.Text = “Downloaded”;  
        }  
        else  
        {  
            status.Text = “Timed out”;  
            downloads.ContinueWith(t => Log(t));  
        }  
    }  
    finally { btnDownload.Enabled = true; }  
}  
  
```  
  
## Compilar elementos de combinación basados en tareas  
 Dado que una tarea es capaz de representar completamente una operación asincrónica y proporcionar funciones sincrónicas y asincrónicas para combinar con la operación, recuperar los resultados, etc., es posible compilar las bibliotecas útiles de los combinadores que constituyen las tareas para compilar modelos más grandes.  Como se ha visto en la sección anterior, .NET Framework incluye varios combinadores integrados, pero también se pueden compilar los propios.  Las siguientes secciones ofrecen varios ejemplos de posibles métodos de elementos de combinación.  
  
### RetryOnFault  
 En muchas situaciones, se puede desear reintentar una operación si un intento previo da error.  Para el código sincrónico, se podría compilar un método auxiliar como `RetryOnFault` en el siguiente ejemplo para lograrlo:  
  
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
  
 Se puede compilar un método auxiliar casi idéntico para las operaciones asincrónicas implementadas con el TAP y que devuelvan tareas:  
  
```csharp  
public static async  Task<T> RetryOnFault<T>(  
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
  
 Se puede usar este combinador para encapsular reintentos en la lógica de la aplicación; por ejemplo:  
  
```csharp  
// Download the URL, trying up to three times in case of failure  
string pageContents = await RetryOnFault(  
    () => DownloadStringAsync(url), 3);  
  
```  
  
 Se podría extender la función `RetryOnFault` más adelante:  Por ejemplo, la función podría aceptar otro `Func<Task>` que se invocará entre reintentos para determinar cuándo probar la operación otra vez; por ejemplo:  
  
```csharp  
public static async  Task<T> RetryOnFault<T>(  
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
  
 Se podría usar la función como se muestra para esperar un segundo antes de reintentar la operación:  
  
```csharp  
// Download the URL, trying up to three times in case of failure,  
// and delaying for a second between retries  
string pageContents = await RetryOnFault(  
    () => DownloadStringAsync(url), 3, () => Task.Delay(1000));  
  
```  
  
### NeedOnlyOne  
 A veces, se puede aprovechar la redundancia para mejorar la latencia y las posibilidades de éxito de una operación.  Piense en los múltiples servicios web que proporcionan cotizaciones, pero que, durante varias horas del día cada uno de los servicios puede proporcionar diferentes niveles de calidad y de tiempos de respuesta.  Para tratar con estas fluctuaciones, se pueden mandar solicitudes a todos los servicios web y tan pronto como se reciba una respuesta de una, cancelar las solicitudes restantes.  Se puede implementar una función auxiliar para facilitar la implementación de este patrón común para iniciar múltiples operaciones, esperar alguna y después de cancelar el resto:  La función `NeedOnlyOne` en el siguiente ejemplo muestra este escenario:  
  
```csharp  
public static async  Task<T> NeedOnlyOne(  
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
  
 Esta función se puede utilizar como se indica a continuación:  
  
```csharp  
double currentPrice = await NeedOnlyOne(  
    ct => GetCurrentPriceFromServer1Async(“msft”, ct),  
    ct => GetCurrentPriceFromServer2Async(“msft”, ct),  
    ct => GetCurrentPriceFromServer3Async(“msft”, ct));  
```  
  
### Operaciones de intercalado  
 Existe un potencial problema de rendimiento si se usa el método <xref:System.Threading.Tasks.Task.WhenAny%2A> para admitir un escenario de intercalado cuando se utilizan conjuntos de tareas muy grandes.  Cada llamada a <xref:System.Threading.Tasks.Task.WhenAny%2A> da como resultado una continuación que se registra con cada tarea.  Para un número N de tareas, esto da como resultado O\(N2\) continuaciones creadas sobre el tiempo de vida de la operación de intercalado.  Si está trabajando con un amplio conjunto de tareas, puede utilizar un combinator \(`Interleaved` en el ejemplo siguiente\) para resolver el problema de rendimiento:  
  
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
  
 Se podría utilizar el combinador para procesar los resultados de tareas a medida que éstas se completan; por ejemplo:  
  
```csharp  
IEnumerable<Task<int>> tasks = ...;  
foreach(var task in Interleaved(tasks))  
{  
    int result = await task;  
    …  
}  
```  
  
### WhenAllOrFirstException  
 En ciertos escenarios de dispersión\/recolección, quizás se desee esperar a todas las tareas de un conjunto, a menos que una de ellas dé error, en cuyo caso se desee detener la espera tan pronto se produzca la excepción.  Se puede conseguir esto con un método combinador como `WhenAllOrFirstException` en el siguiente ejemplo:  
  
```csharp  
public static Task<T[]> WhenAllOrFirstException<T>(IEnumerable<Task<T>> tasks)  
{  
    var inputs = tasks.ToList();  
    var ce = new CountdownEvent(inputs.Count);  
    var tcs = new TaskCompletionSource<T[]>();  
  
    Action<Task> onCompleted = (Task completed) =>  
    {  
        if (completed.IsFaulted)   
            tcs.TrySetException(completed.Exception.InnerExceptions);  
        if (ce.Signal() && !tcs.Task.IsCompleted)  
            tcs.TrySetResult(inputs.Select(t => t.Result).ToArray());  
    };  
  
    foreach (var t in inputs) t.ContinueWith(onCompleted);  
    return tcs.Task;  
}  
  
```  
  
## Compilando estructuras de datos basadas en tareas  
 Además de la capacidad de compilar elementos de combinación basados en tareas personalizadas, el hecho de tener una estructura de datos en <xref:System.Threading.Tasks.Task> y <xref:System.Threading.Tasks.Task%601> que representa tanto los resultados de una operación asincrónica y la sincronización necesaria para unirlo hace que sea un tipo muy eficaz para compilar las estructuras de datos personalizadas que se utilizarán en escenarios asincrónicos.  
  
### AsyncCache  
 Un aspecto importante de una tarea es que se puede distribuir a todos los consumidores que la esperan, que registran continuaciones con ella, que obtienen su resultado o excepciones \(en el caso de <xref:System.Threading.Tasks.Task%601>\), etc.  Esto hace que <xref:System.Threading.Tasks.Task> y <xref:System.Threading.Tasks.Task%601> sean perfectamente aptos para su uso en una infraestructura de almacenamiento en caché asincrónica.  He aquí un ejemplo de una pequeña pero eficaz memoria caché asincrónica compilada sobre <xref:System.Threading.Tasks.Task%601>:  
  
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
  
 [AsyncCache\<TKey, TValue\>](http://go.microsoft.com/fwlink/p/?LinkId=251941) La clase acepta como un delegado a su constructor una función que toma `TKey` y devuelve <xref:System.Threading.Tasks.Task%601>.  Cualquier valor al que se ha obtenido acceso previamente desde la memoria caché se almacena en el diccionario interno y `AsyncCache` asegura que sólo una tarea se genera por clave, aun cuando se obtenga acceso a la memoria caché simultáneamente.  
  
 Por ejemplo, se puede construir una memoria caché para páginas web descargadas:  
  
```csharp  
private AsyncCache<string,string> m_webPages =   
    new AsyncCache<string,string>(DownloadStringAsync);  
  
```  
  
 Se puede usar esta memoria caché en métodos asincrónicos siempre que se necesiten los contenidos de una página web.  La clase `AsyncCache` garantiza que se estén descargando tan pocas páginas como sea posible y guarda en memoria caché los resultados.  
  
```csharp  
private async  void btnDownload_Click(object sender, RoutedEventArgs e)   
{  
    btnDownload.IsEnabled = false;  
    try  
    {  
        txtContents.Text = await m_webPages["http://www.microsoft.com"];  
    }  
    finally { btnDownload.IsEnabled = true; }  
}  
  
```  
  
### AsyncProducerConsumerCollection  
 También se pueden utilizar tareas para compilar las estructuras de datos con el fin de coordinar las actividades asincrónicas entre sí.  Piense en uno de los patrones paralelos clásicos de diseño: productor\/consumidor.  En este patrón, los productores generan datos que los consumidores adquieren y los productores y consumidores pueden ejecutarlos en paralelo.  Por ejemplo, el consumidor procesa el punto 1, que fue generado previamente por un productor que ahora está generando el punto 2.  Para el modelo de productor y consumidor, necesita invariable de alguna estructura de datos para almacenar el trabajo creado por los productores de forma que los consumidores puedan ser notificados de datos nuevos y encontrarlo cuando están disponibles.  
  
 A continuación se muestra una simple estructura de datos compilada sobre una tarea que habilita los métodos asincrónicos que se utilizarán como productores y consumidores:  
  
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
  
 Con esa estructura de datos en su lugar, se puede escribir código como el siguiente:  
  
```csharp  
private static AsyncProducerConsumerCollection<int> m_data = …;  
…  
private static async  Task ConsumerAsync()  
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
  
 El espacio de nombres <xref:System.Threading.Tasks.Dataflow> incluye el tipo <xref:System.Threading.Tasks.Dataflow.BufferBlock%601>, que se puede usar de una manera similar, pero sin tener que construir un tipo de colecciones personalizado:  
  
```csharp  
private static BufferBlock<int> m_data = …;  
…  
private static async  Task ConsumerAsync()  
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
>  El espacio de nombres <xref:System.Threading.Tasks.Dataflow> está disponible en el [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] por medio de **NuGet**.  Para instalar el ensamblado que contiene el espacio de nombres <xref:System.Threading.Tasks.Dataflow> , abra su proyecto en [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], elija **Administrar paquetes NuGet** desde el menú del proyecto y busque en línea el paquete Microsoft.Tpl.Dataflow.  
  
## Vea también  
 [Task\-based Asynchronous Pattern \(TAP\)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)   
 [Implementing the Task\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/implementing-the-task-based-asynchronous-pattern.md)   
 [Interop with Other Asynchronous Patterns and Types](../../../docs/standard/asynchronous-programming-patterns/interop-with-other-asynchronous-patterns-and-types.md)