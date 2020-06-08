---
title: Programación asincrónica en C#
description: Información general sobre la compatibilidad con el lenguaje C# para la programación asincrónica mediante async, await, Task y Task<T>
ms.date: 06/04/2020
ms.openlocfilehash: fbbd08f8c0e650c366ca1d283825e629fcb952d7
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2020
ms.locfileid: "84446459"
---
# <a name="asynchronous-programming-with-async-and-await"></a>Programación asincrónica con async y await

El [modelo de programación asincrónica de tareas (TAP)](task-asynchronous-programming-model.md) es una abstracción del código asincrónico. El código se escribe como una secuencia de instrucciones, como es habitual. Puede leerlo como si cada instrucción se completase antes de comenzar la siguiente. El compilador realiza una serie de transformaciones, debido a que algunas de estas instrucciones podrían empezar a funcionar y devolver una clase <xref:System.Threading.Tasks.Task> que representa el trabajo en curso.

Este es el objetivo de la sintaxis: habilitar código que se lea como una secuencia de instrucciones, pero que se ejecute siguiendo un orden mucho más complicado, en función de la asignación de recursos externos y del momento en el que se completen las tareas. Es similar a la manera en la que las personas dan instrucciones para los procesos que incluyen las tareas asincrónicas. En este artículo, usará un ejemplo con instrucciones para preparar el desayuno que le ayudará a comprender cómo las palabras clave `async` y `await` facilitan el proceso de razonar sobre el código, que incluye una serie de instrucciones asincrónicas. Para explicar cómo se prepara un desayuno, probablemente escribirá unas instrucciones parecidas a las que se recogen en la lista siguiente:

1. Sirva una taza de café.
1. Caliente una sartén y fría dos huevos.
1. Fría tres lonchas de beicon.
1. Tueste dos rebanadas de pan.
1. Unte el pan con mantequilla y mermelada.
1. Sirva un vaso de zumo de naranja.

Si tiene experiencia en la cocina, lo más probable es que ejecute estas instrucciones de forma **asincrónica**. Primero, calentará la sartén para los huevos e irá friendo el beicon. Después, pondrá el pan en la tostadora y empezará a freír los huevos. En cada paso del proceso, iniciará una tarea y volverá la atención a las tareas que tiene pendientes.

La preparación del desayuno es un buen ejemplo de un trabajo asincrónico que no es paralelo. Una persona (o un subproceso) puede controlar todas estas tareas. Siguiendo con la analogía del desayuno, una persona puede preparar el desayuno asincrónicamente si comienza la tarea siguiente antes de que finalice la anterior. Los alimentos se cocinan tanto si una persona supervisa el proceso como si no. En cuanto se empieza a calentar la sartén para los huevos, se puede comenzar a freír el beicon. Una vez que el beicon se esté haciendo, se puede poner el pan en la tostadora.

En el caso de un algoritmo paralelo, necesitaría varios cocineros (o subprocesos). Uno se encargaría de los huevos, otro del beicon, etc. Cada uno de ellos se centraría en una sola tarea. Un cocinero (o subproceso) se bloqueará al esperar asincrónicamente a que el beicon se dore para darle la vuelta, o al esperar a que las tostadas estén listas.

Piense ahora en estas mismas instrucciones escritas como instrucciones de C#:

:::code language="csharp" source="snippets/index/AsyncBreakfast-starter/Program.cs" highlight="8-27":::

:::image type="content" source="media/synchronous-breakfast.png" alt-text="Desayuno sincrónico":::

El desayuno preparado de forma sincrónica tardó unos 30 minutos porque el total es la suma de cada tarea individual.

> [!NOTE]
> Las clases `Coffee`, `Egg`, `Bacon`, `Toast` y `Juice` están vacías. Simplemente son clases de marcador creadas para la demostración; no contienen propiedades y no sirven para ningún otro propósito.

Los equipos no interpretan estas instrucciones de la misma manera que las personas. El equipo se bloqueará en cada instrucción hasta que el trabajo se complete antes de pasar a la instrucción siguiente. Podría decirse que esto da lugar a un desayuno poco satisfactorio. Las tareas posteriores no se pueden iniciar mientras no se completen las anteriores. Así pues, se tardará mucho más en preparar el desayuno y algunos alimentos se habrán enfriado incluso antes de servirse.

Si quiere que el equipo ejecute las instrucciones anteriores de forma asincrónica, debe escribir código asincrónico.

Estas cuestiones son importantes para los programas que se escriben hoy en día. Al escribir programas cliente, le interesa que la interfaz de usuario responda a la entrada del usuario. La aplicación no debería hacer que un teléfono parezca congelado mientras descarga datos de la Web. Al escribir programas de servidor, no le conviene que los subprocesos se bloqueen. La intención es que puedan atender también otras solicitudes. El uso de código sincrónico cuando existen alternativas asincrónicas va en detrimento de la capacidad de escalar horizontalmente a un menor coste. Al final, los subprocesos bloqueados pasarán factura.

Las aplicaciones modernas de más éxito requieren código asincrónico. Sin la compatibilidad con los lenguajes, la escritura de código asincrónico requería devoluciones de llamada, eventos de finalización u otros medios que impedían ver claramente la intención original del código. La ventaja del código sincrónico es que resulta fácil de entender. Las acciones detalladas hacen que sea fácil examinar el código y comprenderlo. Los modelos asincrónicos tradicionales obligaban a centrarse en la naturaleza asincrónica del código, no en las acciones fundamentales.

## <a name="dont-block-await-instead"></a>Uso de await para evitar los bloqueos

El código anterior muestra una práctica incorrecta, que consiste en construir código sincrónico para llevar a cabo operaciones asincrónicas. Tal como está escrito, este código bloquea el subproceso que lo ejecuta y le impide realizar cualquier otro trabajo. Nada lo interrumpirá mientras alguna de las tareas esté en curso. Es como si usted se quedara mirando la tostadora después de meter el pan y no pudiera oír a nadie que le dirigiera la palabra hasta que las tostadas estuvieran listas.

Empecemos por actualizar este código para que el subproceso no se bloquee mientras se ejecutan las tareas. La palabra clave `await` proporciona un modo sin bloqueo para iniciar una tarea y, después, proseguir la ejecución cuando dicha tarea se complete. Una versión asincrónica sencilla del código para preparar el desayuno tendría un aspecto parecido al del fragmento siguiente:

:::code language="csharp" source="snippets/index/AsyncBreakfast-V2/Program.cs" id="SnippetMain":::

> [!IMPORTANT]
> El tiempo total transcurrido es aproximadamente el mismo que el de la versión inicial sincrónica. El código todavía tiene que aprovechar algunas de las características clave de programación asincrónica.

> [!TIP]
> Los cuerpos del método de `FryEggsAsync`, `FryBaconAsync` y `ToastBreadAsync` se han actualizado para devolver `Task<Egg>`, `Task<Bacon>` y `Task<Toast>`, respectivamente. Se cambia el nombre de los métodos de su versión original para incluir el sufijo "Async". Sus implementaciones se muestran como parte de la [versión final](#final-version) más adelante en este artículo.

Este código no produce un bloqueo mientras se cocinan los huevos o el beicon, pero tampoco inicia otras tareas. Es decir, pondría el pan en la tostadora y se quedaría esperando a que estuviera listo, pero, por lo menos, si alguien reclamara su atención, le haría caso. En un restaurante en el que se atienden varios pedidos, el cocinero empezaría a preparar otro desayuno mientras se hace el primero.

El subproceso que se encarga del desayuno ya no se bloquearía mientras espera por las tareas iniciadas que aún no han terminado. En algunas aplicaciones, lo único que se necesita es este cambio. Una aplicación de interfaz gráfica de usuario seguirá respondiendo al usuario con este único cambio. Aun así, para este escenario, necesita algo más. No le interesa que todas las tareas de componente se ejecuten secuencialmente. Es mejor iniciar cada una de estas tareas sin esperar a que la tarea anterior se complete.

## <a name="start-tasks-concurrently"></a>Inicio simultáneo de tareas

En muchos escenarios, necesita iniciar varias tareas independientes de inmediato. Después, a medida que finalice cada tarea, podrá seguir con el trabajo que esté listo. Siguiendo con la analogía del desayuno, esta es la manera más rápida de prepararlo. Además, de este modo, todo estará listo aproximadamente en el mismo momento. Así podrá disfrutar de un desayuno caliente.

La clase <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> y los tipos relacionados se pueden usar para razonar sobre las tareas que están en curso. Esto le permite escribir código que se asemeje más a la manera en que realmente se prepara el desayuno. Para ello, cocinará los huevos, el beicon y las tostadas al mismo tiempo. Como cada uno de estos elementos requiere una acción, se ocupará de esa tarea, se encargará de la acción siguiente y esperará por todo lo que necesite su atención.

Comenzará una tarea y conservará el objeto <xref:System.Threading.Tasks.Task> que representa el trabajo. Llevará a cabo una instrucción `await` para esperar por cada tarea antes de trabajar con su resultado.

Realicemos estos cambios en el código del desayuno. El primer paso consiste en almacenar las tareas de las operaciones cuando se inician, en lugar de esperar por ellas:

```csharp
Coffee cup = PourCoffee();
Console.WriteLine("coffee is ready");

Task<Egg> eggsTask = FryEggsAsync(2);
Egg eggs = await eggsTask;
Console.WriteLine("eggs are ready");

Task<Bacon> baconTask = FryBaconAsync(3);
Bacon bacon = await baconTask;
Console.WriteLine("bacon is ready");

Task<Toast> toastTask = ToastBreadAsync(2);
Toast toast = await toastTask;
ApplyButter(toast);
ApplyJam(toast);
Console.WriteLine("toast is ready");

Juice oj = PourOJ();
Console.WriteLine("oj is ready");
Console.WriteLine("Breakfast is ready!");
```

Después, puede mover las instrucciones `await` del beicon y los huevos al final del método, antes de servir el desayuno:

```csharp
Coffee cup = PourCoffee();
Console.WriteLine("coffee is ready");

Task<Egg> eggsTask = FryEggsAsync(2);
Task<Bacon> baconTask = FryBaconAsync(3);
Task<Toast> toastTask = ToastBreadAsync(2);

Toast toast = await toastTask;
ApplyButter(toast);
ApplyJam(toast);
Console.WriteLine("toast is ready");
Juice oj = PourOJ();
Console.WriteLine("oj is ready");

Egg eggs = await eggsTask;
Console.WriteLine("eggs are ready");
Bacon bacon = await baconTask;
Console.WriteLine("bacon is ready");

Console.WriteLine("Breakfast is ready!");
```

:::image type="content" source="media/asynchronous-breakfast.png" alt-text="Desayuno asincrónico":::

El desayuno preparado de forma asincrónica tardó unos 20 minutos porque algunas tareas pudieron efectuarse simultáneamente.

El código anterior funciona mejor. Iniciará todas las tareas asincrónicas a la vez y esperará por una tarea solo cuando necesite los resultados. El código anterior se parece al código de una aplicación web que realiza solicitudes a diferentes microservicios y, después, combina los resultados en una sola página. Podrá realizar todas las solicitudes de inmediato y, luego, llevará a cabo una instrucción `await` para esperar por todas esas tareas y componer la página web.

## <a name="composition-with-tasks"></a>Composición con tareas

 Ya tiene todo listo al mismo tiempo para el desayuno, excepto las tostadas. La preparación de las tostadas es la composición de una operación asincrónica (tostar el pan) y varias operaciones sincrónicas (untar la mantequilla y la mermelada). La actualización de este código ilustra un concepto importante:

> [!IMPORTANT]
> La composición de una operación asincrónica seguida de un trabajo sincrónico es una operación asincrónica. Dicho de otra manera, si una parte cualquiera de una operación es asincrónica, toda la operación es asincrónica.

En el código anterior se muestra que se puede usar un objeto <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> para conservar tareas en ejecución. Lleva a cabo una instrucción `await` para esperar por una tarea a fin de poder usar su resultado. El siguiente paso consiste en crear métodos que representan la combinación de otro trabajo. Antes de servir el desayuno, quiere esperar por la tarea que representa tostar el pan antes de untar la mantequilla y la mermelada. Puede representar este trabajo con el código siguiente:

:::code language="csharp" source="snippets/index/AsyncBreakfast-V3/Program.cs" id="SnippetComposeToastTask":::

El método anterior tiene el modificador `async` en su firma, lo que indica al compilador que este método incluye una instrucción `await`, es decir, que contiene operaciones asincrónicas. Este método representa la tarea que tuesta el pan y, después, agrega la mantequilla y la mermelada. El método devuelve un objeto <xref:System.Threading.Tasks.Task%601> que representa la composición de estas tres operaciones. El bloque principal de código se convierte en lo siguiente:

:::code language="csharp" source="snippets/index/AsyncBreakfast-V3/Program.cs" id="SnippetMain":::

El cambio anterior ilustra una técnica importante para trabajar con código asincrónico. Para componer tareas, las operaciones se separan en un método nuevo que devuelve una tarea. Usted puede elegir cuándo se debe esperar por esta tarea y puede iniciar otras tareas simultáneamente.

## <a name="await-tasks-efficiently"></a>Espera de la finalización de las tareas de forma eficaz

La serie de instrucciones `await` al final del código anterior se puede mejorar mediante el uso de métodos de la clase `Task`. Una de estas API es <xref:System.Threading.Tasks.Task.WhenAll%2A>, que devuelve un objeto <xref:System.Threading.Tasks.Task> que se completa cuando finalizan todas las tareas de la lista de argumentos, como se muestra en el código siguiente:

```csharp
await Task.WhenAll(eggsTask, baconTask, toastTask);
Console.WriteLine("eggs are ready");
Console.WriteLine("bacon is ready");
Console.WriteLine("toast is ready");
Console.WriteLine("Breakfast is ready!");
```

Otra opción consiste en usar <xref:System.Threading.Tasks.Task.WhenAny%2A>, que devuelve un objeto `Task<Task>` que se completa cuando finaliza cualquiera de sus argumentos. Puede esperar por la tarea devuelta, con la certeza de saber que ya ha terminado. En el código siguiente se muestra cómo se puede usar <xref:System.Threading.Tasks.Task.WhenAny%2A> para esperar a que la primera tarea finalice y, después, procesar su resultado. Después de procesar el resultado de la tarea completada, quítela de la lista de tareas que se pasan a `WhenAny`.

```csharp
var breakfastTasks = new List<Task> { eggsTask, baconTask, toastTask };
while (breakfastTasks.Count > 0)
{
    Task finishedTask = await Task.WhenAny(breakfastTasks);
    if (finishedTask == eggsTask)
    {
        Console.WriteLine("eggs are ready");
    }
    else if (finishedTask == baconTask)
    {
        Console.WriteLine("bacon is ready");
    }
    else if (finishedTask == toastTask)
    {
        Console.WriteLine("toast is ready");
    }
    breakfastTasks.Remove(finishedTask);
}
```

Después de todos estos cambios, la versión final del código tiene un aspecto similar al siguiente: <a id="final-version"></a>.
:::code language="csharp" source="snippets/index/AsyncBreakfast-final/Program.cs" highlight="9-40":::

:::image type="content" source="media/whenany-async-breakfast.png" alt-text="Cualquier desayuno asincrónico":::

La versión final del desayuno preparado de forma asincrónica tardó aproximadamente 15 minutes porque algunas tareas pudieron efectuarse simultáneamente y el código pudo supervisar varias tareas a la vez, tomando medidas solo en caso necesario.

Este código final es asincrónico. Refleja con más precisión la manera en que una persona prepara un desayuno. Compare el código anterior con el primer ejemplo de código del artículo. Las acciones principales siguen siendo claras cuando se lee el código. De hecho, puede leerlo como si se tratara de las instrucciones para preparar el desayuno que se indican al principio del artículo. Las características del lenguaje para `async` y `await` proporcionan la traducción que cualquier persona haría para seguir las instrucciones escritas, a saber: las tareas deben iniciarse a medida que sea posible y debe evitarse el bloqueo por esperar a que se completen las tareas.

## <a name="next-steps"></a>Pasos siguientes

> [!div class="nextstepaction"]
> [Información sobre el modelo de programación asincrónica de tareas](task-asynchronous-programming-model.md)
