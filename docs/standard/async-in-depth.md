---
title: Async en profundidad
description: Obtenga información sobre cómo es sencillo escribir código asincrónico enlazado a E/S y CPU al usar el modelo asincrónico basado en tareas de .NET.
author: cartermp
ms.author: wiwagn
ms.date: 06/20/2016
ms.assetid: 1e38f9d9-8f84-46ee-a15f-199aec4f2e34
ms.openlocfilehash: 7fcc41c4ea5037d643402fc722e8f16f28d560ee
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94823334"
---
# <a name="async-in-depth"></a>Async en profundidad

La escritura de código asincrónico enlazado a E/S y CPU es sencilla al usar el modelo asincrónico basado en tareas de .NET. El modelo se expone mediante los tipos `Task` y `Task<T>` y las palabras claves `async` y `await` en C# y Visual Basic. (Los recursos específicos del idioma se encuentran en la sección [Vea también](#see-also)). En este artículo, se explica cómo usar Async de .NET y se proporciona información sobre el marco de trabajo de Async usado en segundo plano.

## <a name="task-and-taskt"></a>Task y Task\<T>

Las tareas son construcciones que se usan para implementar lo que se conoce como el [modelo de promesa de simultaneidad](https://en.wikipedia.org/wiki/Futures_and_promises).  En resumen, le ofrecen una "promesa" de que el trabajo se completará en un momento posterior, lo que le permite coordinarse con la promesa con una API limpia.

- `Task` representa una única operación que no devuelve un valor.
- `Task<T>` representa una única operación que devuelve un valor de tipo `T`.

Es importante razonar sobre las tareas como abstracciones de trabajo que se producen de forma asincrónica y *no* una abstracción sobre subprocesos. De manera predeterminada, las tareas se ejecutan en el trabajo de subproceso y delegado actual del sistema operativo, según corresponda. De forma opcional, se puede solicitar de forma explícita que se ejecuten las tareas en un subproceso independiente mediante la API `Task.Run`.

Las tareas exponen un protocolo de API para supervisar, esperar y acceder al valor del resultado (en el caso de `Task<T>`) de una tarea. La integración de lenguajes, con la palabra clave `await`, proporciona una abstracción de alto nivel para usar tareas.

Mediante `await`, su aplicación o servicio puede realizar trabajo útil mientras se ejecuta una tarea al ceder el control a su llamador hasta que se realiza la tarea. El código no tiene que depender de las devoluciones de llamada ni eventos para seguir ejecutándose una vez completada la tarea. La integración de la API de tareas y lenguajes se encarga de ello. Si está usando `Task<T>`, la palabra clave `await` "desencapsulará" también el valor devuelto cuando se completa la tarea.  Más adelante se explican los detalles sobre cómo funciona esto.

Puede obtener más información sobre las tareas y las distintas formas de interactuar con ellas en el tema [Modelo asincrónico basado en tareas (TAP)](./asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).

## <a name="deeper-dive-into-tasks-for-an-io-bound-operation"></a>Tareas para una operación enlazada a E/S en profundidad

En la siguiente sección, se describe una vista general de lo que sucede con una llamada de E/S asincrónica normal. Comencemos con un par de ejemplos.

En el primer ejemplo, se llama a un método asincrónico y se devuelve una tarea activa que, probablemente, aún esté sin completar.

```csharp
public Task<string> GetHtmlAsync()
{
    // Execution is synchronous here
    var client = new HttpClient();

    return client.GetStringAsync("https://www.dotnetfoundation.org");
}
```

En el segundo ejemplo, se agrega el uso de las palabras clave `async` y `await` para que funcionen en la tarea.

```csharp
public async Task<string> GetFirstCharactersCountAsync(string url, int count)
{
    // Execution is synchronous here
    var client = new HttpClient();

    // Execution of GetFirstCharactersCountAsync() is yielded to the caller here
    // GetStringAsync returns a Task<string>, which is *awaited*
    var page = await client.GetStringAsync("https://www.dotnetfoundation.org");

    // Execution resumes when the client.GetStringAsync task completes,
    // becoming synchronous again.

    if (count > page.Length)
    {
        return page;
    }
    else
    {
        return page.Substring(0, count);
    }
}
```

La llamada a `GetStringAsync()` se realiza a través de bibliotecas de .NET de nivel inferior (es posible que se llame a otros métodos asincrónicos) hasta que se alcanza una llamada de interoperabilidad de P/Invoke en una biblioteca de red nativa. La biblioteca nativa puede realizar posteriormente una llamada API del sistema (como `write()` a un socket en Linux). Se creará un objeto de tarea en el límite nativo o administrado, posiblemente mediante [TaskCompletionSource](xref:System.Threading.Tasks.TaskCompletionSource%601.SetResult(%600)). El objeto de tarea se pasará por las capas, funcionará en ellas o se devolverá directamente y, finalmente, se devuelve al llamador inicial.

En este segundo ejemplo, se devolverá un objeto `Task<T>` de `GetStringAsync`. El uso de la palabra clave `await` hace que el método devuelva un objeto de tarea recién creado. El control vuelve al llamador de esta ubicación en el método `GetFirstCharactersCountAsync`. Los métodos y propiedades del objeto [Task&lt;T&gt;](xref:System.Threading.Tasks.Task%601) permiten que los llamadores supervisen el progreso de la tarea, que se completará cuando se haya ejecutado el código restante en GetFirstCharactersCountAsync.

Después de la llamada API del sistema, la solicitud ahora está en el espacio del kernel, que avanza hacia el subsistema de red del sistema operativo (como `/net` en Linux Kernel).  Aquí, el sistema operativo controlará la solicitud de red *de forma asincrónica*.  Los detalles pueden ser diferentes según el sistema operativo usado (la llamada al controlador de dispositivo puede programarse como una señal devuelta al tiempo de ejecución o una llamada al controlador de dispositivo puede realizarse y *después* se devuelve una señal), pero, finalmente, el tiempo de ejecución recibirá la información de que la solicitud de red está en curso.  En este momento, el trabajo del controlador de dispositivo estará programado, en curso o ya estará terminado (la solicitud ya estará "en la conexión"), pero como esto se produce de forma asincrónica, el controlador de dispositivo es capaz de controlar otra cosa de forma inmediata.

Por ejemplo, en Windows, un subproceso de sistema operativo realiza una llamada al controlador de dispositivo de red y le pide que realice la operación de red a través de un paquete de petición de interrupción (IRP) que representa la operación.  El controlador de dispositivo recibe el IRP, realiza la llamada a la red, marca el IRP como "pendiente" y vuelve al sistema operativo.  Ya que el subproceso de sistema operativo ahora sabe que el IRP está "pendiente", no tiene nada más que hacer en este trabajo y "vuelve", de modo que se puede usar para realizar otro trabajo.

Cuando se haya realizado la solicitud y regresen los datos a través del controlador de dispositivo, notifica a la CPU que se han recibido nuevos datos mediante una interrupción.  La forma en que se controla esta interrupción varía según el sistema operativo, pero, finalmente, los datos pasarán a través del sistema operativo hasta que lleguen a una llamada de interoperabilidad del sistema (por ejemplo, en Linux un controlador de interrupciones programará la mitad inferior de la IRQ para pasar los datos a través del sistema operativo de forma asincrónica).  Tenga en cuenta que esto *también* se produce de manera asincrónica.  El resultado se pone en cola hasta que el siguiente subproceso disponible puede ejecutar el método asincrónico y "desencapsular" el resultado de la tarea completada.

A lo largo de todo este proceso, un punto clave es que **ningún subproceso se dedica a ejecutar la tarea**.  Aunque el trabajo se ejecuta en algún contexto (es decir, el sistema operativo tiene que pasar datos a un controlador de dispositivo y responder a una interrupción), no hay ningún subproceso dedicado a *esperar* a que vuelvan los datos de la solicitud.  Esto permite al sistema controlar un volumen de trabajo mucho mayor en lugar de esperar a que finalicen algunas llamadas de E/S.

Aunque lo anterior puede parecer mucho trabajo que realizar, al medirlo en términos de tiempo de reloj, es ínfimo en comparación con el tiempo necesario para realizar el trabajo de E/S real. Aunque no es exacta, una escala de tiempo posible para una llamada de este estilo tendría este aspecto:

0-1————————————————————————————————————————————————–2-3

- El tiempo empleado de los puntos `0` a `1` es todo hasta que un método asincrónico cede el control a su llamador.
- El tiempo empleado de los puntos `1` a `2` es el tiempo transcurrido en E/S, sin ningún costo de CPU.
- Por último, el tiempo empleado de los puntos `2` a `3` es durante el que se pasa el control (y posiblemente un valor) de nuevo al método asincrónico, momento en que se vuelve a ejecutar.

### <a name="what-does-this-mean-for-a-server-scenario"></a>¿Qué significa esto en un escenario de servidor?

Este modelo funciona bien con una carga de trabajo de escenario de servidor típica.  Ya que no hay ningún subproceso dedicado al bloqueo de tareas incompletas, el grupo de subprocesos de servidor puede atender a un mayor volumen de solicitudes web.

Considere dos servidores: uno que ejecute código asincrónico y otro que no lo haga.  Para este ejemplo, cada servidor tiene solo 5 subprocesos disponibles para las solicitudes de servicio.  Tenga en cuenta que estos números son pequeños y sirven solo en un contexto demostrativo.

Suponga que ambos servidores reciben seis solicitudes simultáneas. Cada solicitud realiza una operación de E/S.  El servidor *sin* código asincrónico tiene que poner en cola la solicitud 6 hasta que uno de los 5 subprocesos haya finalizado el trabajo enlazado a E/S y escrito una respuesta. En el momento en que entre la solicitud 20, el servidor puede comenzar a ralentizarse, porque la cola se extiende demasiado.

El servidor *con* código asincrónico en ejecución también pone en cola la solicitud 6, pero ya que usa `async` y `await`, cada uno de los subprocesos se libera cuando se inicia el trabajo enlazado a E/S, en lugar de cuando finaliza.  Cuando llega la solicitud 20, la cola de solicitudes entrantes será mucho más pequeña (en caso de que haya algo) y no se ralentiza el servidor.

Aunque se trata de un ejemplo inventado, ocurre de forma muy similar en el mundo real.  De hecho, puede esperar que un servidor pueda controlar más solicitudes mediante `async` y `await` que si se dedicaba a un subproceso para cada solicitud que recibe.

### <a name="what-does-this-mean-for-client-scenario"></a>¿Qué significa esto en un escenario de cliente?

El mayor beneficio al usar `async` y `await` para una aplicación cliente es un aumento en la capacidad de respuesta.  Aunque puede crear una aplicación dinámica al generar subprocesos de forma manual, el hecho de generar un subproceso es una operación costosa en comparación a usar solo `async` y `await`.  Especialmente en el caso de juegos para móviles, es fundamental afectar lo mínimo posible al subproceso de interfaz de usuario en lo que a E/S se refiere.

Sobre todo, ya que el trabajo enlazado a E/S no invierte prácticamente ningún tiempo en la CPU, dedicar un subproceso de CPU completo a realizar prácticamente ningún trabajo útil sería un mal uso de recursos.

Además, es muy sencillo enviar trabajo al subproceso de interfaz de usuario (como actualizar una interfaz de usuario) con métodos `async` y no requiere trabajo adicional (como llamar a un delegado seguro para subprocesos).

## <a name="deeper-dive-into-task-and-taskt-for-a-cpu-bound-operation"></a>Task y Task\<T> para una operación enlazada a la CPU en profundidad

El código `async` enlazado a la CPU es un poco diferente del código `async` enlazado a E/S.  Ya que el trabajo se realiza en la CPU, no hay ninguna forma de evitar dedicar un subproceso al cálculo.  El uso de `async` y `await` le proporciona una manera clara de interactuar con subprocesos en segundo plano y mantener al llamador del método asincrónico dinámico.  Tenga en cuenta que esto no proporciona ninguna protección para datos compartidos.  Si usa datos compartidos, aún tendrá que aplicar una estrategia de sincronización adecuada.

Esta es una vista general de una llamada asincrónica enlazada a la CPU:

```csharp
public async Task<int> CalculateResult(InputData data)
{
    // This queues up the work on the threadpool.
    var expensiveResultTask = Task.Run(() => DoExpensiveCalculation(data));

    // Note that at this point, you can do some other work concurrently,
    // as CalculateResult() is still executing!

    // Execution of CalculateResult is yielded here!
    var result = await expensiveResultTask;

    return result;
}
```

`CalculateResult()` se ejecuta en el subproceso en que se ha llamado.  Cuando llama a `Task.Run`, pone en cola la operación costosa enlazada a la CPU, `DoExpensiveCalculation()`, en el grupo de subprocesos y recibe un controlador `Task<int>`.  `DoExpensiveCalculation()` se ejecuta finalmente de forma simultánea en el siguiente subproceso disponible, probablemente en otro núcleo de CPU.  Es posible realizar trabajo simultáneo mientras `DoExpensiveCalculation()` está ocupado en otro subproceso, ya que el subproceso que llama a `CalculateResult()` aún se está ejecutando.

Una vez se encuentra `await`, la ejecución de `CalculateResult()` se cede a su llamador, lo que permite que se realice otro trabajo con el subproceso actual mientras `DoExpensiveCalculation()` genera un resultado.  Una vez que haya finalizado, el resultado se pone en la cola para ejecutarse en el subproceso principal.  Finalmente, el subproceso principal volverá a ejecutar `CalculateResult()`, momento en que tendrá el resultado de `DoExpensiveCalculation()`.

### <a name="why-does-async-help-here"></a>¿Por qué ayuda Async en este caso?

`async` y `await` son el procedimiento recomendado para administrar el trabajo enlazado a la CPU si necesita capacidad de respuesta. Hay varios patrones para usar Async con trabajo enlazado a la CPU. Es importante tener en cuenta que hay un pequeño costo al usar Async y no se recomienda para bucles de pequeñas dimensiones.  Depende de usted determinar cómo escribe el código en torno a esta nueva funcionalidad.

## <a name="see-also"></a>Vea también

- [Programación asincrónica en C#](../csharp/async.md)
- [Programación asincrónica con async y await (C#)](../csharp/programming-guide/concepts/async/index.md)
- [Programación asincrónica en F#](../fsharp/tutorials/asynchronous-and-concurrent-programming/async.md)
- [Programación asincrónica con Async y Await (Visual Basic)](../visual-basic/programming-guide/concepts/async/index.md)
