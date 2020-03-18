---
title: Modelo de programación asincrónica de tareas (TAP) con async y await (C#)
ms.date: 05/22/2017
ms.assetid: 9bcf896a-5826-4189-8c1a-3e35fa08243a
ms.openlocfilehash: 2700f5bfaa2746c1ea6f4862bee3af60cf83d693
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "78848991"
---
# <a name="task-asynchronous-programming-model"></a>Modelo de programación asincrónica de tareas

Puede evitar cuellos de botella de rendimiento y mejorar la capacidad de respuesta total de la aplicación mediante la programación asincrónica. Sin embargo, las técnicas tradicionales para escribir aplicaciones asincrónicas pueden resultar complicadas, haciéndolas difícil de escribir, depurar y mantener.

[C# 5](../../../whats-new/csharp-version-history.md#c-version-50) ha introducido un enfoque simplificado, la programación asincrónica, que aprovecha la compatibilidad asincrónica de .NET Framework 4.5 y versiones posteriores, NET Core y Windows Runtime. El compilador realiza el trabajo difícil que el desarrollador suele realizar y la aplicación conserva una estructura lógica similar al código sincrónico. Como resultado, se obtienen todas las ventajas de la programación asincrónica con una parte del trabajo.

Este tema proporciona información general sobre cuándo y cómo utilizar la programación asincrónica e incluye vínculos que admiten temas con detalles y ejemplos.

## <a name="BKMK_WhentoUseAsynchrony"></a> La asincronía mejora la capacidad de respuesta

La asincronía es esencial para actividades que pueden producir bloqueos, por ejemplo, el acceso a Internet. Tener acceso a un recurso web a veces es lento o va retrasado. Si tal actividad queda bloqueada en un proceso sincrónico, toda la aplicación deberá esperar. En un proceso asincrónico, la aplicación puede continuar con otro trabajo que no dependa del recurso web hasta que finaliza la tarea que puede producir bloqueos.

En la tabla siguiente se muestran las áreas típicas donde la programación asincrónica mejora su capacidad de respuesta. Las API enumeradas desde .NET y Windows Runtime contienen métodos que admiten la programación asincrónica.

| Área de aplicación    | Tipos de .NET con métodos asincrónicos     | Tipos de Windows Runtime con métodos asincrónicos  |
|---------------------|-----------------------------------|-------------------------------------------|
|Acceso web|<xref:System.Net.Http.HttpClient>|<xref:Windows.Web.Syndication.SyndicationClient>|
|Trabajar con archivos|<xref:System.IO.StreamWriter>, <xref:System.IO.StreamReader>, <xref:System.Xml.XmlReader>|<xref:Windows.Storage.StorageFile>|
|Trabajar con imágenes||<xref:Windows.Media.Capture.MediaCapture>, <xref:Windows.Graphics.Imaging.BitmapEncoder>, <xref:Windows.Graphics.Imaging.BitmapDecoder>|
|Programar WCF|[Operaciones sincrónicas y asincrónicas](../../../../framework/wcf/synchronous-and-asynchronous-operations.md)||

La asincronía es especialmente valiosa para aquellas aplicaciones que obtienen acceso al subproceso de interfaz de usuario, ya que todas las actividades relacionadas con la interfaz de usuario normalmente comparten un único subproceso. Si se bloquea un proceso en una aplicación sincrónica, se bloquean todos. La aplicación deja de responder y puede que se piense que se ha producido un error cuando en realidad la aplicación está esperando.

Cuando se usan métodos asincrónicos, la aplicación continúa respondiendo a la interfaz de usuario. Puede cambiar el tamaño o minimizar una ventana, por ejemplo, o puede cerrar la aplicación si no desea esperar a que finalice.

El enfoque basado en asincrónico agrega el equivalente de una transmisión automática a la lista de opciones entre las que puede elegir al diseñar operaciones asincrónicas. Es decir, obtiene todas las ventajas de la programación asincrónica tradicional pero con mucho menos trabajo de desarrollador.

## <a name="BKMK_HowtoWriteanAsyncMethod"></a> Los métodos asincrónicos son más fáciles de escribir

Las palabras clave [async](../../../language-reference/keywords/async.md) y [await](../../../language-reference/operators/await.md) en C# son fundamentales en la programación asincrónica. Con esas dos palabras clave, se pueden usar los recursos de .NET Framework, .NET Core o Windows Runtime para crear un método asincrónico casi tan fácilmente como se crea un método sincrónico. Los métodos asincrónicos que se definen mediante la palabra clave `async` se denominan *métodos asincrónicos*.

En el ejemplo siguiente se muestra un método asincrónico. Casi todo el código deberá ser totalmente familiar.

Puede encontrar el archivo de ejemplo completo de Windows Presentation Foundation (WPF) al final de este tema y puede descargar el [ejemplo Async: ejemplo de "programación asincrónica con Async y Await"](https://docs.microsoft.com/samples/dotnet/samples/async-and-await-cs/).

```csharp
async Task<int> AccessTheWebAsync()
{
    // You need to add a reference to System.Net.Http to declare client.
    var client = new HttpClient();

    // GetStringAsync returns a Task<string>. That means that when you await the
    // task you'll get a string (urlContents).
    Task<string> getStringTask = client.GetStringAsync("https://docs.microsoft.com/dotnet");

    // You can do work here that doesn't rely on the string from GetStringAsync.
    DoIndependentWork();

    // The await operator suspends AccessTheWebAsync.
    //  - AccessTheWebAsync can't continue until getStringTask is complete.
    //  - Meanwhile, control returns to the caller of AccessTheWebAsync.
    //  - Control resumes here when getStringTask is complete.
    //  - The await operator then retrieves the string result from getStringTask.
    string urlContents = await getStringTask;

    // The return statement specifies an integer result.
    // Any methods that are awaiting AccessTheWebAsync retrieve the length value.
    return urlContents.Length;
}
```

Del ejemplo anterior puede obtener información sobre varios procedimientos. Comience con la firma del método. Incluye el modificador `async`. El tipo de valor devuelto es `Task<int>` (vea la sección "Tipos de valor devuelto" para obtener más opciones). El nombre del método termina en `Async`. En el cuerpo del método, `GetStringAsync` devuelve un elemento `Task<string>`. Esto significa que, cuando se aplica `await` a la tarea, se obtiene un elemento `string` (`urlContents`).  Antes de la espera de la tarea, puede realizar otras acciones que no se basen en el elemento `string` de `GetStringAsync`.

Preste mucha atención al operador `await`. Suspende a `AccessTheWebAsync`;

- `AccessTheWebAsync` no puede continuar hasta que se complete `getStringTask`.
- Mientras tanto, el control vuelve al autor de la llamada de `AccessTheWebAsync`.
- Aquí se reanuda el control cuando se completa `getStringTask`.
- Después, el operador `await` recupera el resultado `string` de `getStringTask`.

La instrucción return especifica un resultado entero. Los métodos que están a la espera de `AccessTheWebAsync` recuperan el valor de longitud.

Si `AccessTheWebAsync` no hay ningún trabajo que se pueda hacer entre llamar a `GetStringAsync` y esperar a su finalización, se puede simplificar el código llamando y esperando en la siguiente instrucción única.

```csharp
string urlContents = await client.GetStringAsync("https://docs.microsoft.com/dotnet");
```

Las siguientes características resumen lo que hace que el ejemplo anterior sea un método asincrónico:

- Method Signature incluye un modificador `async`.
- El nombre de un método asincrónico, por convención, finaliza con un sufijo “Async”.
- El tipo de valor devuelto es uno de los tipos siguientes:

  - <xref:System.Threading.Tasks.Task%601> si el método tiene una instrucción return en la que el operando tiene el tipo `TResult`.
  - <xref:System.Threading.Tasks.Task> si el método no tiene ninguna instrucción return ni tiene una instrucción return sin operando.
  - `void` si está escribiendo un controlador de eventos asincrónicos.
  - Cualquier otro tipo que tenga un método `GetAwaiter` (a partir de C# 7.0).

  Para obtener más información, consulte la sección [Tipos de valor devuelto y parámetros](#BKMK_ReturnTypesandParameters).

- El método normalmente incluye al menos una expresión `await`, que marca un punto en el que el método no puede continuar hasta que se completa la operación asincrónica en espera. Mientras tanto, se suspende el método y el control vuelve al llamador del método. La sección siguiente de este tema muestra lo que sucede en el punto de suspensión.

En métodos asincrónicos, se utilizan las palabras clave y los tipos proporcionados para indicar lo que se desea hacer y el compilador realiza el resto, incluido el seguimiento de qué debe ocurrir cuando el control vuelve a un punto de espera en un método suspendido. Algunos procesos de rutina, tales como bucles y control de excepciones, pueden ser difíciles de controlar en código asincrónico tradicional. En un método asincrónico, se pueden escribir estos elementos como se haría en una solución sincrónica y se resuelve este problema.

Para obtener más información sobre la asincronía en versiones anteriores de .NET Framework, vea [TPL y la programación asincrónica tradicional de .NET Framework](../../../../standard/parallel-programming/tpl-and-traditional-async-programming.md).

## <a name="BKMK_WhatHappensUnderstandinganAsyncMethod"></a> Lo que ocurre en un método asincrónico

Lo más importante de entender en la programación asincrónica es cómo el flujo de control pasa de un método a otro. El diagrama siguiente lo guía en el proceso:

![Seguimiento de un programa asincrónico](./media/task-asynchronous-programming-model/navigation-trace-async-program.png "NavigationTrace")

Los números del diagrama se corresponden a los pasos siguientes, que se inician cuando el usuario hace clic en el botón de inicio.

1. Un controlador de eventos llama al método asincrónico `AccessTheWebAsync` y lo espera.

2. `AccessTheWebAsync` crea una instancia <xref:System.Net.Http.HttpClient> y llama al método asincrónico <xref:System.Net.Http.HttpClient.GetStringAsync%2A> para descargar el contenido de un sitio web como una cadena.

3. Sucede algo en `GetStringAsync` que suspende el progreso. Quizás debe esperar a un sitio web para realizar la descarga o alguna otra actividad de bloqueo. Para evitar el bloqueo de recursos, `GetStringAsync` genera un control a su llamador, `AccessTheWebAsync`.

     `GetStringAsync` devuelve un elemento <xref:System.Threading.Tasks.Task%601>, donde `TResult` es una cadena y `AccessTheWebAsync` asigna la tarea a la variable `getStringTask`. La tarea representa el proceso actual para la llamada a `GetStringAsync`, con el compromiso de generar un valor de cadena real cuando se completa el trabajo.

4. Debido a que `getStringTask` no se ha esperado, `AccessTheWebAsync` puede continuar con otro trabajo que no dependa del resultado final de `GetStringAsync`. Ese trabajo se representa mediante una llamada al método sincrónico `DoIndependentWork`.

5. `DoIndependentWork` es un método sincrónico que funciona y vuelve al llamador.

6. `AccessTheWebAsync` se ha quedado sin el trabajo que se puede realizar sin un resultado de `getStringTask`. Después, `AccessTheWebAsync` desea calcular y devolver la longitud de la cadena descargada, pero el método no puede calcular ese valor hasta que el método tiene la cadena.

     Por consiguiente, `AccessTheWebAsync` utiliza un operador await para suspender el progreso y producir el control al método que llamó `AccessTheWebAsync`. `AccessTheWebAsync` devuelve `Task<int>` al llamador. La tarea representa una sugerencia para generar un resultado entero que es la longitud de la cadena descargada.

    > [!NOTE]
    > Si `GetStringAsync` (y, por tanto, `getStringTask`) se completa antes de que `AccessTheWebAsync` lo espere, el control permanece en `AccessTheWebAsync`. El gasto de suspensión y después regresar a `AccessTheWebAsync` se desperdiciaría si el proceso denominado asincrónico (`getStringTask`) ya se ha completado y `AccessTheWebAsync` no tiene que esperar el resultado final.

     Dentro del llamador (el controlador de eventos en este ejemplo), el patrón de procesamiento continúa. El llamador puede hacer otro trabajo que no depende del resultado de `AccessTheWebAsync` antes de esperar ese resultado, o es posible que el llamador se espere inmediatamente.   El controlador de eventos está esperando `AccessTheWebAsync`, y `AccessTheWebAsync` está esperando `GetStringAsync`.

7. `GetStringAsync` completa y genera un resultado de la cadena. La llamada a `GetStringAsync` no devuelve el resultado de la cadena de la manera que cabría esperar. (Recuerde que el método ya devolvió una tarea en el paso 3.) En su lugar, el resultado de cadena se almacena en la tarea que representa la finalización del método, `getStringTask`. El operador await recupera el resultado de `getStringTask`. La instrucción de asignación asigna el resultado recuperado a `urlContents`.

8. Cuando `AccessTheWebAsync` tiene el resultado de la cadena, el método puede calcular la longitud de la cadena. El trabajo de `AccessTheWebAsync` también se completa y el controlador de eventos que espera se puede reanudar. En el ejemplo completo del final de este tema, puede comprobar que el controlador de eventos recupera e imprime el valor de resultado de longitud.
Si no está familiarizado con la programación asincrónica, reserve un minuto para ver la diferencia entre el comportamiento sincrónico y asincrónico. Un método sincrónico devuelve cuando se completa su trabajo (paso 5), pero un método asincrónico devuelve un valor de tarea cuando se suspende el trabajo (pasos 3 y 6). Cuando el método asincrónico completa finalmente el trabajo, se marca la tarea como completa y el resultado, si existe, se almacena en la tarea.

Para obtener más información sobre el flujo de control, vea [Controlar el flujo en los programas asincrónicos (C#)](control-flow-in-async-programs.md).

## <a name="BKMK_APIAsyncMethods"></a> Métodos asincrónicos de API

Tal vez se pregunte dónde encontrar métodos como `GetStringAsync` que sean compatibles con la programación asincrónica. .NET Framework 4.5 o versiones posteriores y .NET Core contienen muchos miembros que trabajan con `async` y `await`. Puede reconocerlos por el sufijo "Async" que se anexa al nombre del miembro y por su tipo de valor devuelto <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>. Por ejemplo, la clase `System.IO.Stream` contiene métodos como <xref:System.IO.Stream.CopyToAsync%2A>, <xref:System.IO.Stream.ReadAsync%2A> y <xref:System.IO.Stream.WriteAsync%2A> junto con los métodos sincrónicos <xref:System.IO.Stream.CopyTo%2A>, <xref:System.IO.Stream.Read%2A> y <xref:System.IO.Stream.Write%2A>.

Windows Runtime también contiene muchos métodos que puede utilizar con `async` y `await` en Aplicaciones Windows. Para obtener más información, vea [Subprocesamiento y programación asincrónica](/windows/uwp/threading-async/) para el desarrollo en UWP, así como [Programación asincrónica (aplicaciones de la Tienda Windows)](https://docs.microsoft.com/previous-versions/windows/apps/hh464924(v=win.10)) e [Inicio rápido: Llamar a API asincrónicas en C# o Visual Basic](https://docs.microsoft.com/previous-versions/windows/apps/hh452713(v=win.10)) si usa versiones anteriores de Windows Runtime.

## <a name="BKMK_Threads"></a> Subprocesos

La intención de los métodos Async es ser aplicaciones que no pueden producir bloqueos. Una expresión `await` en un método asincrónico no bloquea el subproceso actual mientras la tarea esperada se encuentra en ejecución. En vez de ello, la expresión declara el resto del método como una continuación y devuelve el control al llamador del método asincrónico.

Las palabras clave `async` y `await` no hacen que se creen subprocesos adicionales. Los métodos Async no requieren multithreading, ya que un método asincrónico no se ejecuta en su propio subproceso. El método se ejecuta en el contexto de sincronización actual y ocupa tiempo en el subproceso únicamente cuando el método está activo. Puede utilizar <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> para mover el trabajo enlazado a la CPU a un subproceso en segundo plano, pero un subproceso en segundo plano no ayuda con un proceso que solo está esperando a que los resultados estén disponibles.

El enfoque basado en asincrónico en la programación asincrónica es preferible a los enfoques existentes en casi todos los casos. En concreto, este enfoque es mejor que la clase <xref:System.ComponentModel.BackgroundWorker> para las operaciones enlazadas a E/S porque el código es más sencillo y no se tiene que proteger contra las condiciones de carrera. Junto con el método <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType>, la programación asincrónica es mejor que <xref:System.ComponentModel.BackgroundWorker> para las operaciones enlazadas a la CPU, ya que la programación asincrónica separa los detalles de coordinación en la ejecución del código del trabajo que `Task.Run` transfiere al grupo de subprocesos.

## <a name="BKMK_AsyncandAwait"></a> Async y Await

Si especifica que un método es un método asincrónico mediante el modificador [async](../../../language-reference/keywords/async.md), habilita las dos funciones siguientes.

- El método asincrónico marcado puede utilizar [await](../../../language-reference/operators/await.md) para designar puntos de suspensión. El operador `await` indica al compilador que el método asincrónico no puede continuar pasado ese punto hasta que se complete el proceso asincrónico aguardado. Mientras tanto, el control devuelve al llamador del método asincrónico.

     La suspensión de un método asincrónico en una expresión `await` no constituye una salida del método y los bloques `finally` no se ejecutan.

- El método asincrónico marcado sí se puede esperar por los métodos que lo llaman.

Un método asincrónico normalmente contiene una o más apariciones de un operador `await`, pero la ausencia de expresiones `await` no causa errores de compilación. Si un método asincrónico no usa un operador `await` para marcar el punto de suspensión, se ejecuta como un método sincrónico, a pesar del modificador `async`. El compilador detecta una advertencia para dichos métodos.

`async` y `await` son palabras clave contextuales. Para mayor información y ejemplos, vea los siguientes temas:

- [async](../../../language-reference/keywords/async.md)
- [await](../../../language-reference/operators/await.md)

## <a name="BKMK_ReturnTypesandParameters"></a> Tipos de valor devuelto y parámetros

Un método asincrónico suele devolver <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>. Dentro de un método asincrónico, se aplica un operador `await` a una tarea que devuelve una llamada a otro método asincrónico.

Puede especificar <xref:System.Threading.Tasks.Task%601> como el tipo de valor devuelto si el método contiene una instrucción [`return`](../../../language-reference/keywords/return.md) en la que se especifica un operando de tipo `TResult`.

Puede usar <xref:System.Threading.Tasks.Task> como tipo de valor devuelto si el método no tiene instrucción return o si tiene una instrucción return que no devuelve un operando.

A partir de C# 7.0, también puede especificar cualquier otro tipo de valor devuelto, siempre que dicho tipo incluya un método `GetAwaiter`. Un ejemplo de este tipo es <xref:System.Threading.Tasks.ValueTask%601>. Está disponible en el paquete NuGet [System.Threading.Tasks.Extension](https://www.nuget.org/packages/System.Threading.Tasks.Extensions/).

En el ejemplo siguiente se muestra cómo declarar y llamar a un método que devuelve <xref:System.Threading.Tasks.Task%601> o <xref:System.Threading.Tasks.Task>:

```csharp
// Signature specifies Task<TResult>
async Task<int> GetTaskOfTResultAsync()
{
    int hours = 0;
    await Task.Delay(0);
    // Return statement specifies an integer result.
    return hours;
}

// Calls to GetTaskOfTResultAsync
Task<int> returnedTaskTResult = GetTaskOfTResultAsync();
int intResult = await returnedTaskTResult;
// or, in a single statement
int intResult = await GetTaskOfTResultAsync();

// Signature specifies Task
async Task GetTaskAsync()
{
    await Task.Delay(0);
    // The method has no return statement.
}

// Calls to GetTaskAsync
Task returnedTask = GetTaskAsync();
await returnedTask;
// or, in a single statement
await GetTaskAsync();
```

Cada tarea devuelta representa el trabajo en curso. Una tarea encapsula la información sobre el estado del proceso asincrónico y, finalmente, el resultado final del proceso o la excepción que el proceso provoca si no tiene éxito.

Un método asincrónico también puede tener un tipo de valor devuelto `void`. Este tipo de valor devuelto se utiliza principalmente para definir controladores de eventos, donde se requiere un tipo de valor devuelto `void`. Los controladores de eventos asincrónicos sirven a menudo como punto de partida para programas asincrónicos.

No se puede esperar a un método asincrónico que tenga un tipo de valor devuelto `void` y el llamador de un método con tipo de valor devuelto void no puede capturar ninguna excepción producida por este.

Un método asincrónico no puede declarar ningún parámetro [in](../../../language-reference/keywords/in-parameter-modifier.md), [ref](../../../language-reference/keywords/ref.md) o [out](../../../language-reference/keywords/out-parameter-modifier.md), pero el método puede llamar a los métodos que tienen estos parámetros. De forma similar, un método asincrónico no puede devolver un valor por referencia, aunque puede llamar a métodos con valores devueltos ref.

Para más información y ejemplos, vea [Async Return Types (C#)](./async-return-types.md) (Tipos de valor devuelto asincrónicos [C#]). Para más información sobre cómo capturar excepciones en métodos asincrónicos, vea [try-catch](../../../language-reference/keywords/try-catch.md).

Las API asincrónicas en la programación de Windows Runtime tienen uno de los siguientes tipos de valor devuelto, que son similares a las tareas:

- <xref:Windows.Foundation.IAsyncOperation%601>, lo que equivale a <xref:System.Threading.Tasks.Task%601>
- <xref:Windows.Foundation.IAsyncAction>, lo que equivale a <xref:System.Threading.Tasks.Task>
- <xref:Windows.Foundation.IAsyncActionWithProgress%601>
- <xref:Windows.Foundation.IAsyncOperationWithProgress%602>

## <a name="BKMK_NamingConvention"></a> Convención de nomenclatura

Por convención, los nombres de los métodos que devuelven tipos que suelen admitir "await" (p. ej., `Task`, `Task<T>`, `ValueTask` y `ValueTask<T>`) deben terminar por "Async". Los nombres de los métodos que inician operaciones asincrónicas, pero que no devuelven un tipo que admite "await", no deben terminar en "Async", pero pueden empezar por "Begin", "Start" o cualquier otro verbo para sugerir que este método no devuelve ni genera el resultado de la operación.

Puede ignorar esta convención cuando un evento, clase base o contrato de interfaz sugieren un nombre diferente. Por ejemplo, no se debería cambiar el nombre de los controladores de eventos, tales como `Button1_Click`.

## <a name="BKMK_RelatedTopics"></a> Temas relacionados y ejemplos (Visual Studio)

|Título|Description|Ejemplo|
|-----------|-----------------|------------|
|[Walkthrough: Accessing the Web by Using async and await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md) (Tutorial: Acceso a web usando Async y Await [C#])|Muestra cómo convertir una solución WPF sincrónica en una solución WPF asincrónica. La aplicación descarga una serie de sitios web.|[Async Sample: Accessing the Web Walkthrough](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f) (Ejemplo Async: obtener acceso al tutorial web)|
|[Procedimiento para ampliar el tutorial de async usando Task.WhenAll (C#)](./how-to-extend-the-async-walkthrough-by-using-task-whenall.md)|Agrega <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> al tutorial anterior. El uso de `WhenAll` inicia todas las descargas al mismo tiempo.||
|[Procedimiento para realizar varias solicitudes web en paralelo con async y await (C#)](./how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md)|Demuestra cómo comenzar varias tareas al mismo tiempo.|[Async Sample: Make Multiple Web Requests in Parallel](https://code.msdn.microsoft.com/Async-Make-Multiple-Web-49adb82e) (Ejemplo Async: realización de varias solicitudes web en paralelo)|
|[Async Return Types (C#)](./async-return-types.md) (Tipos de valor devuelto de async [C#])|Muestra los tipos que los métodos asincrónicos pueden devolver y explica cuándo es apropiado cada uno de ellos.||
|[Control Flow in Async Programs (C#)](./control-flow-in-async-programs.md) (Flujo de control en programas asincrónicos [C#])|Rastrea en detalle el flujo de control a través de una sucesión de expresiones await en un programa asincrónico.|[Async Sample: Control Flow in Async Programs](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0) (Ejemplo Async: flujo de control en programas asincrónicos)|
|[Fine-Tuning Your Async Application (C#)](./fine-tuning-your-async-application.md) (Ajuste de la aplicación asincrónica [C#])|Muestra cómo agregar la siguiente funcionalidad a la solución asincrónica:<br /><br /> - [Cancel an Async Task or a List of Tasks (C#)](./cancel-an-async-task-or-a-list-of-tasks.md) (Cancelación de una tarea asincrónica o de una lista de tareas [C#])<br />- [Cancel Async Tasks after a Period of Time (C#)](./cancel-async-tasks-after-a-period-of-time.md) (Cancelación de tareas asincrónicas tras un período de tiempo [C#])<br />- [Cancel Remaining Async Tasks after One Is Complete (C#)](./cancel-remaining-async-tasks-after-one-is-complete.md) (Cancelación de tareas asincrónicas restantes cuando se completa una [C#])<br />- [Start Multiple Async Tasks and Process Them As They Complete (C#)](./start-multiple-async-tasks-and-process-them-as-they-complete.md) (Inicio de varias tareas asincrónicas y cómo procesarlas a medida que se completan [C#])|[Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Ejemplo asincrónico: Ajustar la aplicación)|
|[Handling Reentrancy in Async Apps (C#)](./handling-reentrancy-in-async-apps.md) (Control de la reentrada en aplicaciones asincrónicas [C#])|Muestra cómo controlar los casos en los que se reinicia una operación asincrónica activa mientras se ejecuta.||
|[WhenAny: Bridging between the .NET Framework and the Windows Runtime](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/jj635140(v=vs.120)) (WhenAny: Puente entre .NET Framework y Windows Runtime)|Muestra cómo unir entre tipos de tareas en .NET Framework e IAsyncOperations en Windows Runtime para poder usar <xref:System.Threading.Tasks.Task.WhenAny%2A> con un método de Windows Runtime.|[Async Sample: Bridging between .NET and Windows Runtime (AsTask and WhenAny)](https://code.msdn.microsoft.com/Async-Sample-Bridging-d6a2f739) (Ejemplo Async: puente entre .NET y Windows Runtime [AsTask y WhenAny])|
|Cancelación asincrónica: Puente entre .NET Framework y Windows Runtime|Muestra cómo unir entre tipos de tareas en .NET Framework e IAsyncOperations en Windows Runtime para poder usar <xref:System.Threading.CancellationTokenSource> con un método de Windows Runtime.|[Async Sample: Bridging between .NET and Windows Runtime (AsTask & Cancellation)](https://code.msdn.microsoft.com/Async-Sample-Bridging-9479eca3) (Ejemplo Async: puente entre .NET y Windows Runtime [AsTask & Cancellation])|
|[Using Async for File Access (C#)](./using-async-for-file-access.md) (Uso de Async en acceso a archivos [C#])|Enumera y demuestra los beneficios de usar async y await para obtener acceso a archivos.||
|[Modelo asincrónico basado en tareas [TAP]](../../../../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)|Describe un nuevo patrón de asincronía en .NET Framework. El patrón está basado en los tipos <xref:System.Threading.Tasks.Task> y <xref:System.Threading.Tasks.Task%601>.||
|[Vídeos de Async en Channel 9](https://channel9.msdn.com/search?term=async%20&type=All#pubDate=year&ch9Search&lang-en=en)|Proporciona vínculos a una serie de vídeos sobre programación asincrónica.||

## <a name="BKMK_CompleteExample"></a> Ejemplo completo

El código siguiente es el archivo *MainWindow.xaml.cs* de la aplicación de WPF que se explica en este artículo. Puede descargar el ejemplo de [Async Sample: Example from "Asynchronous Programming with Async and Await"](https://docs.microsoft.com/samples/dotnet/samples/async-and-await-cs/) (Ejemplo de Async: ejemplo de "programación asincrónica con Async y Await").

[!code-csharp[async](~/samples/snippets/standard/async/async-and-await/cs/MainWindow.xaml.cs)]

## <a name="see-also"></a>Vea también

- [async](../../../language-reference/keywords/async.md)
- [await](../../../language-reference/operators/await.md)
- [Programación asincrónica](../../../async.md)
- [Información general de Async](../../../../standard/async.md)
