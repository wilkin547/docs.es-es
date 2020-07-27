---
title: 'Programación asincrónica: C#'
description: Obtenga información sobre el modelo de programación asincrónico de nivel de lenguaje de C# que proporciona .NET Core.
author: cartermp
ms.date: 05/20/2020
ms.technology: csharp-async
ms.assetid: b878c34c-a78f-419e-a594-a2b44fa521a4
ms.openlocfilehash: 35ba90f978b1993f80451a28a4cd08129afddd85
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864506"
---
# <a name="asynchronous-programming"></a>Programación asincrónica

Si tiene cualquier necesidad enlazada a E/S (por ejemplo, solicitar datos de una red, acceder a una base de datos o leer y escribir un sistema de archivos), deberá usar la programación asincrónica. También podría tener código enlazado a la CPU, como realizar un cálculo costoso, que también es un buen escenario para escribir código asincrónico.

C# tiene un modelo de programación asincrónico de nivel de lenguaje que permite escribir fácilmente código asincrónico sin tener que hacer malabares con las devoluciones de llamada o ajustarse a una biblioteca que admita la asincronía. Sigue lo que se conoce como el [modelo asincrónico basado en tareas (TAP)](../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).

## <a name="overview-of-the-asynchronous-model"></a>Información general del modelo asincrónico

El núcleo de la programación asincrónica son los objetos `Task` y `Task<T>`, que modelan las operaciones asincrónicas. Son compatibles con las palabras clave `async` y `await`. El modelo es bastante sencillo en la mayoría de los casos:

- Para el código enlazado a E/S, espera una operación que devuelva `Task` o `Task<T>` dentro de un método `async`.
- Para el código enlazado a la CPU, espera una operación que se inicia en un subproceso en segundo plano con el método <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType>.

La palabra clave `await` es donde ocurre la magia. Genera control para el autor de la llamada del método que ha realizado `await`, y permite en última instancia una interfaz de usuario con capacidad de respuesta o un servicio flexible. Aunque [existen maneras](../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) de abordar el código asincrónico diferentes de `async` y `await`, este artículo se centra en las construcciones de nivel de lenguaje.

### <a name="io-bound-example-download-data-from-a-web-service"></a>Ejemplo enlazado a E/S: descarga de datos de un servicio web

Puede que necesite descargar algunos datos de un servicio web cuando se presione un botón, pero no quiere bloquear el subproceso de interfaz de usuario. Puede conseguirlo de la siguiente forma:

```csharp
private readonly HttpClient _httpClient = new HttpClient();

downloadButton.Clicked += async (o, e) =>
{
    // This line will yield control to the UI as the request
    // from the web service is happening.
    //
    // The UI thread is now free to perform other work.
    var stringData = await _httpClient.GetStringAsync(URL);
    DoSomethingWithData(stringData);
};
```

El código expresa la intención (descargar datos de forma asincrónica) sin verse obstaculizado en la interacción con objetos `Task`.

### <a name="cpu-bound-example-perform-a-calculation-for-a-game"></a>Ejemplo enlazado a la CPU: realizar un cálculo para un juego

Supongamos que está escribiendo un juego para móviles en el que se pueden infligir daños a muchos enemigos en la pantalla pulsando un botón. Realizar el cálculo del daño puede resultar costoso y hacerlo en el subproceso de interfaz de usuario haría que pareciera que el juego se pone en pausa mientras se lleva a cabo el cálculo.

La mejor manera de abordar esta situación consiste en iniciar un subproceso en segundo plano que realice la tarea mediante `Task.Run` y esperar su resultado mediante `await`. Esto permite que la interfaz de usuario funcione de manera fluida mientras se lleva a cabo la tarea.

```csharp
private DamageResult CalculateDamageDone()
{
    // Code omitted:
    //
    // Does an expensive calculation and returns
    // the result of that calculation.
}

calculateButton.Clicked += async (o, e) =>
{
    // This line will yield control to the UI while CalculateDamageDone()
    // performs its work. The UI thread is free to perform other work.
    var damageResult = await Task.Run(() => CalculateDamageDone());
    DisplayDamage(damageResult);
};
```

Este código expresa claramente la intención del evento de clic del botón, no requiere la administración manual de un subproceso en segundo plano y lo hace en un modo sin bloqueo.

### <a name="what-happens-under-the-covers"></a>Qué sucede en segundo plano

En las operaciones asincrónicas existen numerosos aspectos dinámicos. Si siente curiosidad sobre lo que ocurre en el segundo plano de `Task` y `Task<T>`, eche un vistazo al artículo [Async en profundidad](../standard/async-in-depth.md) para obtener más información.

En lo que respecta a C#, el compilador transforma el código en una máquina de estados que realiza el seguimiento de acciones como la retención de la ejecución cuando se alcanza `await` y la reanudación de la ejecución cuando se ha finalizado un trabajo en segundo plano.

Para los más interesados en la teoría, se trata de una implementación del [modelo de promesas de asincronía](https://en.wikipedia.org/wiki/Futures_and_promises).

## <a name="key-pieces-to-understand"></a>Piezas clave que debe comprender

* El código asincrónico puede usarse para código tanto enlazado a E/S como enlazado a la CPU, pero de forma distinta en cada escenario.
* El código asincrónico usa `Task<T>` y `Task`, que son construcciones que se usan para modelar el trabajo que se realiza en segundo plano.
* La palabra clave `async` convierte un método en un método asincrónico, lo que permite usar la palabra clave `await` en su cuerpo.
* Cuando se aplica la palabra clave `await`, se suspende el método de llamada y se cede el control al autor de la llamada hasta que se completa la tarea esperada.
* `await` solo puede usarse dentro de un método asincrónico.

## <a name="recognize-cpu-bound-and-io-bound-work"></a>Reconocer el trabajo enlazado a la CPU y el enlazado a E/S

En los dos primeros ejemplos de esta guía se ha explicado cómo se puede usar `async` y `await` para trabajos enlazados a E/S y a la CPU. Resulta fundamental que pueda identificar si el trabajo que debe realizar está enlazado a E/S o a la CPU, ya que esto puede afectar en gran medida al rendimiento del código y podría dar lugar al uso inadecuado de ciertas construcciones.

A continuación, se indican dos preguntas que debe hacerse antes de escribir el código:

1. ¿Estará su código "esperando" algo, como datos de una base de datos?

   Si la respuesta es "sí", su trabajo está **enlazado a E/S**.

1. ¿Realizará el código un cálculo costoso?

   Si la respuesta es "sí", su trabajo está **enlazado a la CPU**.

Si el trabajo que tiene está **enlazado a E/S**, use `async` y `await` *sin* `Task.Run`. *No debe* usar la Biblioteca TPL. Esto se explica en [Async en profundidad](../standard/async-in-depth.md).

Si el trabajo que tiene está **enlazado a la CPU** y le interesa la capacidad de respuesta, use `async` y `await`, pero genere el trabajo en otro subproceso *con* `Task.Run`. Si el trabajo es adecuado para la simultaneidad y el paralelismo, también debe plantearse el uso de la [biblioteca TPL](../standard/parallel-programming/task-parallel-library-tpl.md).

Además, siempre debe medir la ejecución del código. Por ejemplo, puede verse en una situación en la que el trabajo enlazado a la CPU no sea suficientemente costoso en comparación con la sobrecarga de cambios de contexto cuando realice multithreading. Cada opción tiene su compensación y debe elegir el equilibrio correcto para su situación.

## <a name="more-examples"></a>Más ejemplos

En los ejemplos siguientes se muestran distintas maneras en las que puede escribir código asincrónico en C#. Abarcan algunos escenarios diferentes con los que puede encontrarse.

### <a name="extract-data-from-a-network"></a>Extracción de datos de una red

Este fragmento de código descarga el HTML desde la página principal en <https://dotnetfoundation.org> y cuenta el número de veces que aparece la cadena ".NET" en el código HTML. Usa ASP.NET para definir un método de controlador Web API que realiza esta tarea y devuelve el número.

> [!NOTE]
> Si tiene previsto realizar un análisis HTML en el código de producción, no use expresiones regulares. Use una biblioteca de análisis en su lugar.

```csharp
private readonly HttpClient _httpClient = new HttpClient();

[HttpGet, Route("DotNetCount")]
public async Task<int> GetDotNetCount()
{
    // Suspends GetDotNetCount() to allow the caller (the web server)
    // to accept another request, rather than blocking on this one.
    var html = await _httpClient.GetStringAsync("https://dotnetfoundation.org");

    return Regex.Matches(html, @"\.NET").Count;
}
```

Este es el mismo escenario escrito para una aplicación Windows Universal, que realiza la misma tarea cuando se presiona un botón:

```csharp
private readonly HttpClient _httpClient = new HttpClient();

private async void OnSeeTheDotNetsButtonClick(object sender, RoutedEventArgs e)
{
    // Capture the task handle here so we can await the background task later.
    var getDotNetFoundationHtmlTask = _httpClient.GetStringAsync("https://dotnetfoundation.org");

    // Any other work on the UI thread can be done here, such as enabling a Progress Bar.
    // This is important to do here, before the "await" call, so that the user
    // sees the progress bar before execution of this method is yielded.
    NetworkProgressBar.IsEnabled = true;
    NetworkProgressBar.Visibility = Visibility.Visible;

    // The await operator suspends OnSeeTheDotNetsButtonClick(), returning control to its caller.
    // This is what allows the app to be responsive and not block the UI thread.
    var html = await getDotNetFoundationHtmlTask;
    int count = Regex.Matches(html, @"\.NET").Count;

    DotNetCountLabel.Text = $"Number of .NETs on dotnetfoundation.org: {count}";

    NetworkProgressBar.IsEnabled = false;
    NetworkProgressBar.Visibility = Visibility.Collapsed;
}
```

### <a name="wait-for-multiple-tasks-to-complete"></a>Esperar a que se completen varias tareas

Es posible que se vea en una situación en la que necesite recuperar varios fragmentos de datos al mismo tiempo. La API `Task` contiene dos métodos, <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> y <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>, que permiten escribir código asincrónico que realiza una espera sin bloqueo en varios trabajos en segundo plano.

En este ejemplo se muestra cómo podría captar datos `User` de un conjunto de elementos `userId`.

```csharp
public async Task<User> GetUserAsync(int userId)
{
    // Code omitted:
    //
    // Given a user Id {userId}, retrieves a User object corresponding
    // to the entry in the database with {userId} as its Id.
}

public static async Task<IEnumerable<User>> GetUsersAsync(IEnumerable<int> userIds)
{
    var getUserTasks = new List<Task<User>>();
    foreach (int userId in userIds)
    {
        getUserTasks.Add(GetUserAsync(userId));
    }

    return await Task.WhenAll(getUserTasks);
}
```

Aquí tiene otra manera de escribir lo mismo de una forma más sucinta, con LINQ:

```csharp
public async Task<User> GetUserAsync(int userId)
{
    // Code omitted:
    //
    // Given a user Id {userId}, retrieves a User object corresponding
    // to the entry in the database with {userId} as its Id.
}

public static async Task<User[]> GetUsersAsync(IEnumerable<int> userIds)
{
    var getUserTasks = userIds.Select(id => GetUserAsync(id));
    return await Task.WhenAll(getUserTasks);
}
```

Aunque es menos código, tenga cuidado al combinar LINQ con código asincrónico. Dado que LINQ usa la ejecución diferida, las llamadas asincrónicas no se realizarán inmediatamente, como lo hacen en un bucle `foreach`, a menos que fuerce la secuencia generada a procesar una iteración con una llamada a `.ToList()` o `.ToArray()`.

## <a name="important-info-and-advice"></a>Consejos e información importante

Con la programación asincrónica, hay algunos detalles que debe tener en cuenta para evitar un comportamiento inesperado.

* Los métodos `async` **deben tener una palabra clave** `await` **en el cuerpo o nunca proporcionarán resultados**.

  Es importante que tenga esto en cuenta. Si no se usa `await` en el cuerpo de un método `async`, el compilador de C# genera una advertencia, pero el código se compila y se ejecuta como si se tratara de un método normal. Esto sería muy ineficaz, ya que la máquina de estados generada por el compilador de C# para el método asincrónico no realiza nada.

* **Debe agregar "Async" como el sufijo de todos los métodos asincrónicos que escriba.**

Se trata de la convención que se usa en .NET para distinguir más fácilmente los métodos sincrónicos de los asincrónicos. No se aplican necesariamente ciertos métodos a los que el código no llame explícitamente (como controladores de eventos o métodos de controlador web). Puesto que el código no los llama explícitamente, resulta importante explicitar sus nombres.

* `async void` **solo se debe usar para controladores de eventos.**

`async void` es la única manera de permitir a los controladores de eventos asincrónicos trabajar, ya que los eventos no tienen tipos de valor devuelto (por lo tanto, no pueden hacer uso de `Task` y `Task<T>`). Cualquier otro uso de `async void` no sigue el modelo de TAP y puede resultar difícil de usar, como:

* Las excepciones producidas en un método `async void` no se pueden detectar fuera de ese método.
* Los métodos `async void` resultan muy difíciles de probar.
* Los métodos `async void` pueden provocar efectos secundarios negativos si el autor de la llamada no espera que sean asincrónicos.

* **Tenga cuidado al usar lambdas asincrónicas en las expresiones de LINQ.**

Las expresiones lambda de LINQ usan la ejecución aplazada, lo que implica que el código podría acabar ejecutándose en un momento en que no se lo espere. La introducción de las tareas de bloqueo puede dar lugar a un interbloqueo si no se han escrito correctamente. Además, el anidamiento de código asincrónico de esta manera también puede hacer que resulte más difícil razonar sobre la ejecución del código. Async y LINQ son eficaces, pero deben usarse conjuntamente con el mayor cuidado y claridad posible.

* **Escriba código que espere las tareas sin bloqueo.**

Bloquear el subproceso actual como un medio para esperar que se complete `Task` puede dar lugar a interbloqueos y subprocesos de contexto bloqueados, y puede requerir un control de errores más complejo. En la tabla siguiente se ofrece orientación sobre cómo abordar la espera de las tareas de una manera que no produzca un bloqueo:

| Use esto...          | En vez de esto...           | Cuando quiera hacer esto...                 |
|----------------------|------------------------------|--------------------------------------------|
| `await`              | `Task.Wait` o `Task.Result` | Recuperar el resultado de una tarea en segundo plano |
| `await Task.WhenAny` | `Task.WaitAny`               | Esperar que finalice cualquier tarea           |
| `await Task.WhenAll` | `Task.WaitAll`               | Esperar que finalicen todas las tareas          |
| `await Task.Delay`   | `Thread.Sleep`               | Esperar un período de tiempo               |

* **Considere la posibilidad de usar** `ValueTask` **cuando sea posible**

La devolución de un objeto `Task` desde métodos asincrónicos puede presentar cuellos de botella de rendimiento en determinadas rutas de acceso. `Task` es un tipo de referencia, por lo que su uso implica la asignación de un objeto. En los casos en los que un método declarado con el modificador `async` devuelva un resultado en caché o se complete sincrónicamente, las asignaciones adicionales pueden suponer un costo considerable de tiempo en secciones críticas para el rendimiento del código. Esas asignaciones pueden resultar costosas si se producen en bucles ajustados. Para obtener más información, consulte [Tipos de valor devueltos asincrónicos generalizados](whats-new/csharp-7.md#generalized-async-return-types).

* **Considere la posibilidad de utilizar** `ConfigureAwait(false)`

Una pregunta habitual es "¿Cuándo debo usar el método <xref:System.Threading.Tasks.Task.ConfigureAwait(System.Boolean)?displayProperty=nameWithType>?". El método permite a una instancia de `Task` configurar su elemento awaiter. Este es un aspecto importante que debe tenerse en cuenta, y su configuración incorrecta podría tener implicaciones de rendimiento e incluso interbloqueos. Para obtener más información sobre `ConfigureAwait`, consulte las [preguntas más frecuentes sobre ConfigureAwait](https://devblogs.microsoft.com/dotnet/configureawait-faq).

* **Escriba código con menos estados.**

No dependa del estado de los objetos globales o la ejecución de ciertos métodos. En su lugar, dependa únicamente de los valores devueltos de los métodos. ¿Por qué?

* Le resultará más fácil razonar sobre el código.
* Le resultará más fácil probar el código.
* Resulta mucho más sencillo mezclar código asincrónico y sincrónico.
* Normalmente se pueden evitar por completo las condiciones de carrera.
* Depender de los valores devueltos facilita la coordinación de código asincrónico.
* (Extra) Funciona muy bien con la inserción de dependencias.

Un objetivo recomendado es lograr una [transparencia referencial](https://en.wikipedia.org/wiki/Referential_transparency_%28computer_science%29) completa o casi completa en el código. Esto se traducirá en un código base extremadamente predecible, que se puede probar y es fácil de mantener.

## <a name="other-resources"></a>Otros recursos

* En el artículo [Async en profundidad](../standard/async-in-depth.md) se proporciona más información sobre cómo funcionan las tareas.
* [Programación asincrónica con async y await (C#)](./programming-guide/concepts/async/index.md)
* Los vídeos [Six Essential Tips for Async](https://channel9.msdn.com/Series/Three-Essential-Tips-for-Async) (Seis consejos esenciales para la programación asincrónica) de Lucian Wischik son un recurso fantástico para este tipo de programación.
