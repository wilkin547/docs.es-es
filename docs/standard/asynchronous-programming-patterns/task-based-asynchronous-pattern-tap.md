---
title: Modelo asincrónico basado en tareas (TAP)
description: Descubra el modelo asincrónico basado en tareas (TAP). TAP es el modelo asincrónico de diseño recomendado para los nuevos desarrollos en .NET.
ms.date: 02/26/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- asynchronous design patterns, .NET
- TAP, .NET support for
- Task-based Asynchronous Pattern, .NET support for
- .NET, asynchronous design patterns
ms.assetid: 8cef1fcf-6f9f-417c-b21f-3fd8bac75007
ms.openlocfilehash: 2987e7baa52f627d1da41af21d05bfa22a247fbb
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "92889249"
---
# <a name="task-based-asynchronous-pattern"></a>Modelo asincrónico basado en tareas

El modelo asincrónico basado en tareas (TAP) se basa en los tipos <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> y <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> del espacio de nombres <xref:System.Threading.Tasks?displayProperty=nameWithType>, que se usan para representar operaciones asincrónicas arbitrarias. TAP es el patrón asincrónico de diseño recomendado para los nuevos desarrollos.  
  
## <a name="naming-parameters-and-return-types"></a>Nombres, parámetros y tipos de valores devueltos

TAP usa un solo método para representar el inicio y la finalización de una operación asincrónica. Esto contrasta con el modelo de programación asincrónico (APM o `IAsyncResult`) y con el modelo asincrónico basado en eventos (EAP). APM requiere los métodos `Begin` y `End`. EPA requiere un método con el sufijo `Async` y también requiere uno o más eventos, tipos de delegado de controlador de eventos y tipos derivados de `EventArg`. Los métodos asincrónicos en TAP incluyen el sufijo `Async` después del nombre de la operación para los métodos que devuelven tipos que admiten await, como <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.ValueTask> y <xref:System.Threading.Tasks.ValueTask%601>. Por ejemplo, una operación `Get` asincrónica que devuelve un `Task<String>` se puede denominar `GetAsync`. Si va a agregar un método de TAP a una clase que ya contiene un nombre de método EAP con el sufijo `Async`, use el sufijo `TaskAsync` en su lugar. Por ejemplo, si la clase ya tiene un método `GetAsync`, use el nombre `GetTaskAsync`. Si un método inicia una operación asincrónica pero no devuelve un tipo que admite await, su nombre debe comenzar por `Begin`, `Start` u otro verbo que sugiera que este método no devuelve ni genera el resultado de la operación.  
  
 Un método de TAP devuelve <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> o <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>, en función de si el método sincrónico correspondiente devuelve void o un tipo `TResult`.  
  
 Los parámetros de un método de TAP deben coincidir con los parámetros de su homólogo sincrónico y se deben proporcionar en el mismo orden.  Sin embargo, los parámetros `out` y `ref` están exentos de esta regla y se deben evitar completamente. En su lugar, los datos que se hubieran devuelto con un parámetro `out` o `ref` se deben devolver como parte del tipo `TResult` devuelto por <xref:System.Threading.Tasks.Task%601> y deben usar una tupla o una estructura de datos personalizada para incluir varios valores. También debería plantearse la posibilidad de agregar un parámetro <xref:System.Threading.CancellationToken> aunque el homólogo sincrónico del método TAP no ofrezca ninguno.

 Los métodos que están dedicados exclusivamente a la creación, manipulación o combinación de tareas (donde el intento asincrónico del método está claro en el nombre del método o en el nombre del tipo al que el método pertenece) no necesitan seguir este modelo de nomenclatura; esos métodos se conocen a menudo como *combinadores* (también denominados elementos de combinación). Los ejemplos de combinadores incluyen <xref:System.Threading.Tasks.Task.WhenAll%2A> y <xref:System.Threading.Tasks.Task.WhenAny%2A>, y se describen en la sección que describe los combinadores integrados basados en tareas titulada [Usar los combinadores integrados basados en tareas](consuming-the-task-based-asynchronous-pattern.md#combinators) del artículo [Utilizar el modelo asincrónico basado en tareas](consuming-the-task-based-asynchronous-pattern.md).  
  
 Para obtener ejemplos de cómo la sintaxis de TAP difiere de la sintaxis empleada en patrones heredados de programación asincrónica como el modelo de programación asincrónica (APM) y el patrón asincrónico basado en eventos (EAP), vea [Modelos para la programación asincrónica](index.md).  
  
## <a name="initiating-an-asynchronous-operation"></a>Inicio de una operación asincrónica  
 Un método asincrónico basado en TAP puede hacer una pequeña cantidad de trabajo sincrónicamente, como validar argumentos e iniciar la operación asincrónica, antes de que devuelva la tarea resultante. El trabajo sincrónico debe reducirse al mínimo de modo que el método asincrónico pueda volver rápidamente. Entre las razones para un retorno rápido se incluyen las siguientes:  
  
- Los métodos asincrónicos se pueden invocar desde subprocesos de la interfaz de usuario (UI) y cualquier trabajo sincrónico de ejecución prolongada puede dañar la capacidad de respuesta de la aplicación.  
  
- Se pueden iniciar varios métodos asincrónicos simultáneamente. Por tanto, cualquier trabajo de ejecución prolongada en la parte sincrónica de un método asincrónico puede retrasar el inicio de otras operaciones asincrónicas, lo que reduce las ventajas de la simultaneidad.  
  
 En algunos casos, la cantidad de trabajo necesario para completar la operación es menor que la cantidad de trabajo necesario para iniciar la operación de forma asincrónica. La lectura de una secuencia donde la operación de lectura se puede satisfacer mediante datos que ya están almacenados en búfer en la memoria es un ejemplo de este escenario. En casos como este, la operación puede completarse sincrónicamente y puede devolver una tarea que ya se ha completado.  
  
## <a name="exceptions"></a>Excepciones  
 Un método asincrónico debe generar una excepción fuera de la llamada de método asincrónico solo como respuesta a un error de uso. Los errores de uso nunca deben producirse en código de producción. Por ejemplo, si al pasar una referencia nula (`Nothing` en Visual Basic) como uno de los argumentos del método se produce un estado de error (representado normalmente por una excepción <xref:System.ArgumentNullException>), puede modificar el código de llamada para asegurarse de que nunca se pase una referencia nula. Para todos los demás errores, las excepciones que se producen cuando se ejecuta un método asincrónico deben asignarse a la tarea devuelta, aunque el método asincrónico se complete sincrónicamente antes de que se devuelva la tarea. Normalmente, una tarea contiene como máximo una excepción. Sin embargo, si la tarea representa varias operaciones (por ejemplo, <xref:System.Threading.Tasks.Task.WhenAll%2A>), se pueden asociar varias excepciones a una única tarea.  
  
## <a name="target-environment"></a>Entorno de destino  
 Cuando implementa un método de TAP, puede determinar dónde se produce la ejecución asincrónica. Puede optar por ejecutar la carga de trabajo en el grupo de subprocesos, implementarla mediante E/S asincrónica (sin enlazarse a un subproceso durante la mayor parte de la ejecución de la operación), ejecutarla en un subproceso concreto (como el subproceso de la interfaz de usuario) o usar cualquier número de contextos posibles. Un método de TAP incluso puede no tener nada que ejecutar y puede devolver simplemente una clase <xref:System.Threading.Tasks.Task> que representa la ocurrencia de una condición en otra ubicación en el sistema (por ejemplo, una tarea que representa datos que llegan a una estructura de datos en cola).

 El autor de la llamada al método TAP puede bloquear la espera para que el método de TAP se complete mediante la espera sincrónica en la tarea resultante, o bien puede ejecutar código (de continuación) adicional cuando la operación asincrónica se completa. El creador del código de continuación tiene control sobre lo que ese código ejecuta. Puede crear el código de continuación explícitamente, mediante métodos de la clase <xref:System.Threading.Tasks.Task> (por ejemplo, <xref:System.Threading.Tasks.Task.ContinueWith%2A>) o implícitamente, usando la compatibilidad con lenguaje sobre las continuaciones (por ejemplo, `await` en C#, `Await` en Visual Basic, `AwaitValue` en F#).  
  
## <a name="task-status"></a>Estado de la tarea  
 La clase <xref:System.Threading.Tasks.Task> proporciona un ciclo de vida para las operaciones asincrónicas y ese ciclo se representa mediante la enumeración <xref:System.Threading.Tasks.TaskStatus>. Para admitir los casos extremos de tipos que se derivan de <xref:System.Threading.Tasks.Task> y <xref:System.Threading.Tasks.Task%601>, y para admitir la separación de la construcción de la programación, la clase <xref:System.Threading.Tasks.Task> expone un método <xref:System.Threading.Tasks.Task.Start%2A>. Las tareas creadas por los constructores públicos <xref:System.Threading.Tasks.Task> se denominan *tareas en frío* , porque inician su ciclo de vida en el estado <xref:System.Threading.Tasks.TaskStatus.Created> no programado y solo se programan cuando se llama a <xref:System.Threading.Tasks.Task.Start%2A> en estas instancias.

 Todas las demás tareas inician su ciclo de vida en un estado activo, lo que significa que las operaciones asincrónicas que representan ya se han iniciado y su estado de la tarea es un valor de enumeración distinto de <xref:System.Threading.Tasks.TaskStatus.Created?displayProperty=nameWithType>. Todas las tareas que se devuelven de métodos de TAP deben estar activas. **Si un método de TAP usa internamente el constructor de una tarea para crear instancias de la tarea que se va a devolver, el método de TAP debe llamar a <xref:System.Threading.Tasks.Task.Start%2A> en el objeto <xref:System.Threading.Tasks.Task> antes de devolverlo.** Los consumidores de un método de TAP pueden suponer con seguridad que la tarea devuelta está activa y no deben intentar llamar a <xref:System.Threading.Tasks.Task.Start%2A> en ningún <xref:System.Threading.Tasks.Task> que se devuelve de un método de TAP. La llamada a <xref:System.Threading.Tasks.Task.Start%2A> en una tarea activa produce una excepción <xref:System.InvalidOperationException>.  
  
## <a name="cancellation-optional"></a>Cancelación (opcional)  
 En TAP, la cancelación es opcional tanto para los implementadores de método asincrónico como para los consumidores de este método. Si una operación permite la cancelación, expone una sobrecarga del método asincrónico que acepta un token de cancelación (instancia de <xref:System.Threading.CancellationToken>). Por convención, el parámetro se denomina `cancellationToken`.  
  
 [!code-csharp[Conceptual.TAP#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.tap/cs/examples1.cs#1)]
 [!code-vb[Conceptual.TAP#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.tap/vb/examples1.vb#1)]  
  
 La operación asincrónica supervisa este token para las solicitudes de cancelación. Si recibe una solicitud de cancelación, puede elegir admitir esa solicitud y cancelar la operación. Si la solicitud de cancelación hace que el trabajo finalice prematuramente, el método de TAP devuelve una tarea que finaliza en el estado <xref:System.Threading.Tasks.TaskStatus.Canceled>; no hay ningún resultado disponible y no se produce ninguna excepción.  El estado <xref:System.Threading.Tasks.TaskStatus.Canceled> se considera un estado final (completado) para una tarea, junto con los estados <xref:System.Threading.Tasks.TaskStatus.Faulted> y <xref:System.Threading.Tasks.TaskStatus.RanToCompletion>. Por tanto, si una tarea está en el estado <xref:System.Threading.Tasks.TaskStatus.Canceled>, su propiedad <xref:System.Threading.Tasks.Task.IsCompleted%2A> devuelve `true`. Cuando una tarea se completa en el estado <xref:System.Threading.Tasks.TaskStatus.Canceled>, cualquier continuación registrada con la tarea se programa o se ejecuta, a menos que se especificara una opción de continuación como <xref:System.Threading.Tasks.TaskContinuationOptions.NotOnCanceled> para rechazar la continuación. Cualquier código que espera de forma asincrónica una tarea cancelada mediante el uso de características del lenguaje sigue ejecutándose pero recibe un objeto <xref:System.OperationCanceledException> o una excepción derivada del mismo. El código que se bloquea sincrónicamente en espera de la tarea mediante métodos como <xref:System.Threading.Tasks.Task.Wait%2A> y <xref:System.Threading.Tasks.Task.WaitAll%2A> también continúa ejecutándose con una excepción.  
  
 Si un token de cancelación ha solicitado la cancelación antes de que se llame al método de TAP que acepta ese token, el método de TAP debe devolver una tarea <xref:System.Threading.Tasks.TaskStatus.Canceled>.  Sin embargo, si se solicita la cancelación mientras la operación asincrónica se ejecuta, la operación asincrónica no necesita aceptar la solicitud de cancelación.  La tarea devuelta debe finalizar en el estado <xref:System.Threading.Tasks.TaskStatus.Canceled> solo si la operación termina como resultado de la solicitud de cancelación. Si se solicita la cancelación pero aún se produce un resultado o una excepción, la tarea debe finalizar en el estado <xref:System.Threading.Tasks.TaskStatus.RanToCompletion> o <xref:System.Threading.Tasks.TaskStatus.Faulted>.

 En el caso de los métodos asincrónicos que quieren exponer la capacidad de cancelarse ante todo, no tiene que proporcionar una sobrecarga que no acepte un token de cancelación. Para los métodos que no pueden cancelarse, no proporcione sobrecargas que acepten un token de cancelación; esto ayuda a indicar al llamador si el método de destino es realmente cancelable.  El código de consumidor que no desea la cancelación puede llamar a un método que acepta un objeto <xref:System.Threading.CancellationToken> y proporciona <xref:System.Threading.CancellationToken.None%2A> como valor del argumento. <xref:System.Threading.CancellationToken.None%2A> es funcionalmente equivalente al objeto <xref:System.Threading.CancellationToken> predeterminado.  
  
## <a name="progress-reporting-optional"></a>Informe de progreso (opcional)  
 Algunas operaciones asincrónicas se benefician de proporcionar notificaciones de progreso; se suelen usar para actualizar una interfaz de usuario con información sobre el progreso de la operación asincrónica.

 En TAP, el progreso se controla a través de una interfaz <xref:System.IProgress%601>, la cual se pasa al método asincrónico como un parámetro normalmente denominado `progress`.  Proporcionar la interfaz de progreso cuando se llama al método asincrónico ayuda a eliminar condiciones de carrera resultantes de un uso incorrecto (es decir, cuando los controladores de eventos registrados incorrectamente después del inicio de la operación pueden perder actualizaciones).  Lo que es más importante, la interfaz de progreso admite implementaciones diferentes de progreso, según determina el código usado.  Por ejemplo, el código usado puede que desee encargarse solo de la última actualización de progreso, almacenar en búfer todas las actualizaciones, invocar una acción para cada actualización o controlar si se serializa la invocación en un subproceso determinado. Todas estas opciones se pueden conseguir mediante otra implementación de la interfaz, personalizada según las necesidades particulares del consumidor.  Como ocurre con la cancelación, las implementaciones de TAP deben proporcionar un parámetro <xref:System.IProgress%601> solo si la API admite notificaciones de progreso.

 Por ejemplo, si el método `ReadAsync` anteriormente mencionado en este artículo puede informar del progreso intermedio en forma de número de bytes leídos hasta el momento, la devolución de llamada de progreso puede ser una interfaz <xref:System.IProgress%601>:  
  
 [!code-csharp[Conceptual.TAP#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.tap/cs/examples1.cs#2)]
 [!code-vb[Conceptual.TAP#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.tap/vb/examples1.vb#2)]  
  
 Si un método `FindFilesAsync` devuelve una lista de todos los archivos que satisfacen un patrón particular de búsqueda, la devolución de progreso puede proporcionar una estimación del porcentaje de trabajo completado y el conjunto actual de resultados parciales. Podría proporcionar esta información con una tupla:  
  
 [!code-csharp[Conceptual.TAP#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.tap/cs/examples1.cs#3)]
 [!code-vb[Conceptual.TAP#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.tap/vb/examples1.vb#3)]  
  
 o con un tipo de datos que sea específico de la API:  
  
 [!code-csharp[Conceptual.TAP#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.tap/cs/examples1.cs#4)]
 [!code-vb[Conceptual.TAP#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.tap/vb/examples1.vb#4)]  
  
 En este último caso, el tipo de datos especial suele tener el sufijo `ProgressInfo`.  
  
 Si las implementaciones de TAP proporcionan sobrecargas que aceptan un parámetro `progress`, deben permitir que el argumento sea `null`, en cuyo caso no se notificará ningún progreso. Las implementaciones de TAP deben notificar sincrónicamente el progreso al objeto <xref:System.Progress%601>, lo que permite que el método asincrónico proporcione rápidamente el progreso. También permite al consumidor del progreso determinar cómo y dónde es mejor controlar la información. Por ejemplo, la instancia de progreso puede optar por hacerse con las devoluciones de llamada y generar eventos en un contexto capturado de sincronización.  
  
## <a name="iprogresst-implementations"></a>Implementaciones\<T> de IProgress  
.NET proporciona la clase <xref:System.Progress%601>, que implementa <xref:System.IProgress%601>. La clase <xref:System.Progress%601> se declara de la forma siguiente:  
  
```csharp  
public class Progress<T> : IProgress<T>  
{  
    public Progress();  
    public Progress(Action<T> handler);  
    protected virtual void OnReport(T value);  
    public event EventHandler<T>? ProgressChanged;  
}  
```
  
 Una instancia de <xref:System.Progress%601> expone un evento <xref:System.Progress%601.ProgressChanged>, que se provoca cada vez que la operación asincrónica informe de una actualización de progreso. El evento <xref:System.Progress%601.ProgressChanged> se genera en el objeto <xref:System.Threading.SynchronizationContext> que se capturó cuando se creó la instancia de <xref:System.Progress%601>. Si no había ningún contexto de sincronización disponible, se usa un contexto predeterminado destinado al grupo de subprocesos. Los controladores pueden registrarse con este evento. También se puede proporcionar un único controlador al constructor <xref:System.Progress%601> por comodidad, y se comportará como un controlador de eventos para el evento <xref:System.Progress%601.ProgressChanged>. Las actualizaciones de progreso se generan de forma asincrónica para evitar retrasar la operación asincrónica mientras los controladores de eventos se ejecutan. Otra implementación <xref:System.IProgress%601> podría elegir aplicar semánticas diferentes.  
  
## <a name="choosing-the-overloads-to-provide"></a>Elección de las sobrecargas que se van a proporcionar  
 Si una implementación TAP usa la propiedad <xref:System.Threading.Tasks.TaskFactory.CancellationToken%2A> y los parámetros <xref:System.IProgress%601> opcionales, podría requerir hasta cuatro sobrecargas:  
  
```csharp  
public Task MethodNameAsync(…);  
public Task MethodNameAsync(…, CancellationToken cancellationToken);  
public Task MethodNameAsync(…, IProgress<T> progress);
public Task MethodNameAsync(…,
    CancellationToken cancellationToken, IProgress<T> progress);  
```  
  
```vb  
Public MethodNameAsync(…) As Task  
Public MethodNameAsync(…, cancellationToken As CancellationToken cancellationToken) As Task  
Public MethodNameAsync(…, progress As IProgress(Of T)) As Task
Public MethodNameAsync(…, cancellationToken As CancellationToken,
                       progress As IProgress(Of T)) As Task  
```  
  
 Aunque muchas implementaciones de TAP no ofrecen funcionalidades de cancelación o progreso, por lo que requieren un único método:  
  
```csharp  
public Task MethodNameAsync(…);  
```  
  
```vb  
Public MethodNameAsync(…) As Task  
```  
  
 Si una implementación de TAP admite la cancelación o el progreso pero no ambos, puede proporcionar dos sobrecargas:  
  
```csharp  
public Task MethodNameAsync(…);  
public Task MethodNameAsync(…, CancellationToken cancellationToken);  
  
// … or …  
  
public Task MethodNameAsync(…);  
public Task MethodNameAsync(…, IProgress<T> progress);  
```  
  
```vb  
Public MethodNameAsync(…) As Task  
Public MethodNameAsync(…, cancellationToken As CancellationToken) As Task  
  
' … or …  
  
Public MethodNameAsync(…) As Task  
Public MethodNameAsync(…, progress As IProgress(Of T)) As Task  
```  
  
 Si una implementación TAP admite la cancelación y el progreso, puede exponer las cuatro sobrecargas. Sin embargo, puede proporcionar solo las dos siguientes:  
  
```csharp  
public Task MethodNameAsync(…);  
public Task MethodNameAsync(…,
    CancellationToken cancellationToken, IProgress<T> progress);  
```  
  
```vb  
Public MethodNameAsync(…) As Task  
Public MethodNameAsync(…, cancellationToken As CancellationToken,
                       progress As IProgress(Of T)) As Task  
```  
  
 Para compensar las dos combinaciones intermedias que faltan, los desarrolladores pueden pasar la propiedad <xref:System.Threading.CancellationToken.None%2A> o un objeto <xref:System.Threading.CancellationToken> predeterminado para el parámetro `cancellationToken` y `null` para el parámetro `progress`.  
  
 Si se espera que cada uso del método TAP admita cancelación o progreso, puede omitir las sobrecargas que no acepten el parámetro pertinente.  
  
 Si se decide exponer varias sobrecargas para conseguir que la cancelación o el progreso sean opcionales, las sobrecargas que no admitan cancelación o progreso deben comportarse como si pasaran <xref:System.Threading.CancellationToken.None%2A> para la cancelación o `null` para el progreso en la sobrecarga que admite ambas.  
  
## <a name="related-articles"></a>Artículos relacionados
  
|Title|Descripción|  
|-----------|-----------------|  
|[Patrones para la programación asincrónica](index.md)|Presenta los tres patrones para realizar las operaciones asincrónicas: el patrón asincrónico basado en tareas (TAP), el modelo de programación asincrónica (APM) y el patrón asincrónico basado en eventos (EAP).|  
|[Implementar el modelo asincrónico basado en tareas](implementing-the-task-based-asynchronous-pattern.md)|Describe cómo implementar el patrón asincrónico basado en tareas (TAP) de tres maneras: mediante los compiladores de C# y Visual Basic de Visual Studio, manualmente o a través de una combinación del compilador y de métodos manuales.|  
|[Modelo asincrónico basado en tareas (TAP)](consuming-the-task-based-asynchronous-pattern.md)|Describe cómo se pueden utilizar las tareas y las devoluciones de llamada para conseguir esperas sin bloqueos.|  
|[Interoperabilidad con otros tipos y patrones asincrónicos](interop-with-other-asynchronous-patterns-and-types.md)|Describe cómo usar el patrón asincrónico basado en tareas (TAP) para implementar el modelo de programación asincrónica (APM) y el patrón asincrónico basado en eventos (EAP).|
