---
title: Programación asíncrona
description: Descubra cómo F- proporciona soporte limpio para la asincronía basada en un modelo de programación de nivel de lenguaje derivado de los conceptos básicos de programación funcional.
ms.date: 12/17/2018
ms.openlocfilehash: 0a7d400c9778e30d6b25798239f12b7b2b0e3d82
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021524"
---
# <a name="async-programming-in-f"></a>Programación asíncrona en F\#

La programación asincrónica es un mecanismo que es esencial para las aplicaciones modernas por diversas razones. Hay dos casos de uso principales que la mayoría de los desarrolladores encontrarán:

- Presentar un proceso de servidor que puede dar servicio a un número significativo de solicitudes entrantes simultáneas, al tiempo que se minimizan los recursos del sistema ocupados mientras el procesamiento de solicitudes espera entradas de sistemas o servicios externos a ese proceso
- Mantener una interfaz de usuario responsiva o un subproceso principal mientras se progresa simultáneamente en el trabajo en segundo plano

Aunque el trabajo en segundo plano a menudo implica la utilización de varios subprocesos, es importante tener en cuenta los conceptos de asincronía y multiproceso por separado. De hecho, son preocupaciones separadas, y una no implica la otra. En este artículo se describen los conceptos separados con más detalle.

## <a name="asynchrony-defined"></a>Asincronía definida

El punto anterior - que la asincronía es independiente de la utilización de varios subprocesos - vale la pena explicar un poco más. Hay tres conceptos que a veces están relacionados, pero estrictamente independientes entre sí:

- Simultaneidad; cuando se ejecutan varios cálculos en períodos de tiempo superpuestos.
- Paralelismo; cuando varios cálculos o varias partes de un solo cálculo se ejecutan exactamente al mismo tiempo.
- Asincronía; cuando uno o más cálculos se pueden ejecutar por separado del flujo principal del programa.

Los tres son conceptos ortogonales, pero se pueden confundenr fácilmente, especialmente cuando se utilizan juntos. Por ejemplo, es posible que deba ejecutar varios cálculos asincrónicos en paralelo. Esta relación no significa que el paralelismo o la asincronía impliquen unos a otros.

Si considera la etimología de la palabra "asincrónico", hay dos piezas involucradas:

- "a", que significa "no".
- "sincrónico", que significa "al mismo tiempo".

Cuando se juntan estos dos términos, verá que "asincrónico" significa "no al mismo tiempo". Eso es todo. No hay ninguna implicación de simultaneidad o paralelismo en esta definición. Esto también es cierto en la práctica.

En términos prácticos, los cálculos asincrónicos en F- están programados para ejecutarse independientemente del flujo principal del programa. Esta ejecución independiente no implica simultaneidad o paralelismo, ni implica que siempre se produce un cálculo en segundo plano. De hecho, los cálculos asincrónicos pueden incluso ejecutarse sincrónicamente, dependiendo de la naturaleza del cálculo y el entorno en el que se ejecuta el cálculo.

La principal toma que debe tener es que los cálculos asincrónicos son independientes del flujo del programa principal. Aunque hay pocas garantías sobre cuándo o cómo se ejecuta un cálculo asincrónico, hay algunos enfoques para orquestarlos y programarlos. En el resto de este artículo se exploran los conceptos básicos de la asincronía de F y cómo usar los tipos, funciones y expresiones integradas en F .

## <a name="core-concepts"></a>Conceptos principales

En F, la programación asincrónica se centra en tres conceptos básicos:

- El `Async<'T>` tipo, que representa un cálculo asincrónico componible.
- Las `Async` funciones del módulo, que permiten programar el trabajo asincrónico, componer cálculos asincrónicos y transformar resultados asincrónicos.
- La `async { }` [expresión de cálculo](../../language-reference/computation-expressions.md), que proporciona una sintaxis conveniente para crear y controlar cálculos asincrónicos.

Puede ver estos tres conceptos en el ejemplo siguiente:

```fsharp
open System
open System.IO

let printTotalFileBytes path =
    async {
        let! bytes = File.ReadAllBytesAsync(path) |> Async.AwaitTask
        let fileName = Path.GetFileName(path)
        printfn "File %s has %d bytes" fileName bytes.Length
    }

[<EntryPoint>]
let main argv =
    printTotalFileBytes "path-to-file.txt"
    |> Async.RunSynchronously

    Console.Read() |> ignore
    0
```

En el ejemplo, la `printTotalFileBytes` `string -> Async<unit>`función es de tipo . Llamar a la función no ejecuta realmente el cálculo asincrónico. En su lugar, devuelve un `Async<unit>` que actúa como una *especificación* del trabajo que se ejecuta de forma asincrónica. Llama `Async.AwaitTask` a su cuerpo, que convierte <xref:System.IO.File.ReadAllBytesAsync%2A> el resultado de un tipo adecuado.

Otra línea importante es `Async.RunSynchronously`la llamada a . Esta es una de las funciones de inicio del módulo async a las que tendrá que llamar si desea ejecutar realmente un cálculo asincrónico de F.

Esta es una diferencia fundamental con el `async` estilo de programación de C/Visual Basic. En F, los cálculos asincrónicos se pueden considerar como **tareas frías**. Deben iniciarse explícitamente para ejecutarse. Esto tiene algunas ventajas, ya que le permite combinar y secuenciar el trabajo asincrónico mucho más fácilmente que en C o Visual Basic.

## <a name="combine-asynchronous-computations"></a>Combinar cálculos asincrónicos

Este es un ejemplo que se basa en el anterior mediante la combinación de cálculos:

```fsharp
open System
open System.IO

let printTotalFileBytes path =
    async {
        let! bytes = File.ReadAllBytesAsync(path) |> Async.AwaitTask
        let fileName = Path.GetFileName(path)
        printfn "File %s has %d bytes" fileName bytes.Length
    }

[<EntryPoint>]
let main argv =
    argv
    |> Array.map printTotalFileBytes
    |> Async.Parallel
    |> Async.Ignore
    |> Async.RunSynchronously

    0
```

Como puede ver, `main` la función tiene bastantes llamadas más realizadas. Conceptualmente, hace lo siguiente:

1. Transforme los argumentos `Async<unit>` de línea `Array.map`de comandos en cálculos con .
2. Cree `Async<'T[]>` un que programe `printTotalFileBytes` y ejecute los cálculos en paralelo cuando se ejecute.
3. Cree `Async<unit>` un que ejecute el cálculo paralelo e ignore su resultado.
4. Ejecute explícitamente el `Async.RunSynchronously` último cálculo con y bloquee hasta que se complete.

Cuando se ejecuta `printTotalFileBytes` este programa, se ejecuta en paralelo para cada argumento de línea de comandos. Dado que los cálculos asincrónicos se ejecutan independientemente del flujo del programa, no hay ningún orden en el que impriman su información y terminen de ejecutarse. Los cálculos se programarán en paralelo, pero su orden de ejecución no está garantizado.

## <a name="sequence-asynchronous-computations"></a>Secuenciar cálculos asincrónicos

Dado `Async<'T>` que es una especificación de trabajo en lugar de una tarea que ya se está ejecutando, puede realizar transformaciones más complejas fácilmente. Este es un ejemplo que secuencia un conjunto de cálculos asincrónicos para que se ejecuten uno tras otro.

```fsharp
let printTotalFileBytes path =
    async {
        let! bytes = File.ReadAllBytesAsync(path) |> Async.AwaitTask
        let fileName = Path.GetFileName(path)
        printfn "File %s has %d bytes" fileName bytes.Length
    }

[<EntryPoint>]
let main argv =
    argv
    |> Array.map printTotalFileBytes
    |> Async.Sequential
    |> Async.Ignore
    |> Async.RunSynchronously
    |> ignore
```

Esto se `printTotalFileBytes` programará para ejecutar en `argv` el orden de los elementos de en lugar de programarlos en paralelo. Dado que el siguiente elemento no se programará hasta que el último cálculo haya terminado de ejecutarse, los cálculos se secuencian de forma que no haya superposición en su ejecución.

## <a name="important-async-module-functions"></a>Funciones importantes del módulo asincrónico

Cuando se escribe código asincrónico en F, normalmente interactuará con un marco de trabajo que controla la programación de cálculos automáticamente. Sin embargo, este no siempre es el caso, por lo que es bueno aprender las diversas funciones de inicio para programar el trabajo asincrónico.

Debido a que los cálculos asincrónicos de F son una _especificación_ de trabajo en lugar de una representación del trabajo que ya se está ejecutando, deben iniciarse explícitamente con una función de inicio. Hay muchas [funciones de inicio async](https://msdn.microsoft.com/library/ee370232.aspx) que son útiles en diferentes contextos. En la siguiente sección se describen algunas de las funciones de inicio más comunes.

### <a name="asyncstartchild"></a>Async.StartChild

Inicia un cálculo secundario dentro de un cálculo asincrónico. Esto permite que varios cálculos asincrónicos se ejecuten simultáneamente. El cálculo secundario comparte un token de cancelación con el cálculo primario. Si se cancela el cálculo primario, también se cancela el cálculo secundario.

Signature:

```fsharp
computation: Async<'T> * timeout: ?int -> Async<Async<'T>>
```

Cuándo usarlo:

- Si desea ejecutar varios cálculos asincrónicos simultáneamente en lugar de uno a la vez, pero no tenerlos programados en paralelo.
- Cuando desea vincular la duración de un cálculo secundario a la de un cálculo primario.

Qué tener en cuenta:

- Iniciar varios cálculos con `Async.StartChild` no es lo mismo que programarlos en paralelo. Si desea programar cálculos en `Async.Parallel`paralelo, utilice .
- La cancelación de un cálculo primario desencadenará la cancelación de todos los cálculos secundarios que inició.

### <a name="asyncstartimmediate"></a>Async.StartImmediate

Ejecuta un cálculo asincrónico y comienza inmediatamente en el subproceso actual del sistema operativo. Esto es útil si necesita actualizar algo en el subproceso que realiza la llamada durante el cálculo. Por ejemplo, si un cálculo asincrónico debe actualizar una `Async.StartImmediate` interfaz de usuario (por ejemplo, actualizar una barra de progreso), debe usarse.

Signature:

```fsharp
computation: Async<unit> * cancellationToken: ?CancellationToken -> unit
```

Cuándo usarlo:

- Cuando necesite actualizar algo en el subproceso que realiza la llamada en medio de un cálculo asincrónico.

Qué tener en cuenta:

- El código del cálculo asincrónico se ejecutará en cualquier subproceso en el que se programe. Esto puede ser problemático si ese subproceso es de alguna manera sensible, como un subproceso de interfaz de usuario. En tales `Async.StartImmediate` casos, es probable que no sea apropiado de usar.

### <a name="asyncstartastask"></a>Async.StartAsTask

Ejecuta un cálculo en el grupo de subprocesos. Devuelve <xref:System.Threading.Tasks.Task%601> un que se completará en el estado correspondiente una vez que finalice el cálculo (produce el resultado, produce una excepción o se cancela). Si no se proporciona ningún token de cancelación, se usa el token de cancelación predeterminado.

Signature:

```fsharp
computation: Async<'T> * taskCreationOptions: ?TaskCreationOptions * cancellationToken: ?CancellationToken -> Task<'T>
```

Cuándo usarlo:

- Cuando necesite llamar a una API de <xref:System.Threading.Tasks.Task%601> .NET que espera que represente el resultado de un cálculo asincrónico.

Qué tener en cuenta:

- Esta llamada asignará `Task` un objeto adicional, que puede aumentar la sobrecarga si se utiliza con frecuencia.

### <a name="asyncparallel"></a>Async.Parallel

Programa una secuencia de cálculos asincrónicos que se ejecutarán en paralelo. El grado de paralelismo se puede ajustar/limitar `maxDegreesOfParallelism` opcionalmente especificando el parámetro.

Signature:

```fsharp
computations: seq<Async<'T>> * ?maxDegreesOfParallelism: int -> Async<'T[]>
```

Cuándo usarlo

- Si necesita ejecutar un conjunto de cálculos al mismo tiempo y no depende de su orden de ejecución.
- Si no necesita resultados de cálculos programados en paralelo hasta que se hayan completado todos.

Qué tener en cuenta:

- Solo puede acceder a la matriz resultante de valores una vez que todos los cálculos han finalizado.
- Los cálculos se ejecutarán siempre que terminen programados. Este comportamiento significa que no puede confiar en su orden de ejecución.

### <a name="asyncsequential"></a>Async.Sequential

Programa una secuencia de cálculos asincrónicos que se ejecutarán en el orden en que se pasan. Se ejecutará el primer cálculo, luego el siguiente, y así sucesivamente. No se ejecutarán cálculos en paralelo.

Signature:

```fsharp
computations: seq<Async<'T>> -> Async<'T[]>
```

Cuándo usarlo

- Si necesita ejecutar varios cálculos en orden.

Qué tener en cuenta:

- Solo puede acceder a la matriz resultante de valores una vez que todos los cálculos han finalizado.
- Los cálculos se ejecutarán en el orden en que se pasan a esta función, lo que puede significar que transcurrirá más tiempo antes de que se devuelvan los resultados.

### <a name="asyncawaittask"></a>Async.AwaitTask

Devuelve un cálculo asincrónico <xref:System.Threading.Tasks.Task%601> que espera a que se complete el dado y devuelve su resultado como un`Async<'T>`

Signature:

```fsharp
task: Task<'T> -> Async<'T>
```

Cuándo usarlo:

- Cuando se consume una API de <xref:System.Threading.Tasks.Task%601> .NET que devuelve un cálculo asincrónico dentro de F .

Qué tener en cuenta:

- Las excepciones se <xref:System.AggregateException> ajustan siguiendo la convención de la biblioteca de tareas paralelas y este comportamiento es diferente de cómo se asincrónico de F - generalmente expone excepciones.

### <a name="asynccatch"></a>Async.Catch

Crea un cálculo asincrónico `Async<'T>`que ejecuta `Async<Choice<'T, exn>>`un determinado , devolviendo un archivo . Si el `Async<'T>` especificado se completa `Choice1Of2` correctamente, se devuelve a con el valor resultante. Si se produce una excepción antes `Choice2of2` de que se complete, se devuelve a a con la excepción provocada. Si se utiliza en un cálculo asincrónico que se compone de muchos cálculos y uno de esos cálculos produce una excepción, el cálculo que abarca se detendrá por completo.

Signature:

```fsharp
computation: Async<'T> -> Async<Choice<'T, exn>>
```

Cuándo usarlo:

- Al realizar un trabajo asincrónico que puede producir un error con una excepción y desea controlar esa excepción en el llamador.

Qué tener en cuenta:

- Cuando se utilizan cálculos asincrónicos combinados o secuenciados, el cálculo que abarca se detendrá por completo si uno de sus cálculos "internos" produce una excepción.

### <a name="asyncignore"></a>Async.Ignore

Crea un cálculo asincrónico que ejecuta el cálculo especificado y omite su resultado.

Signature:

```fsharp
computation: Async<'T> -> Async<unit>
```

Cuándo usarlo:

- Cuando tiene un cálculo asincrónico cuyo resultado no es necesario. Esto es análogo `ignore` al código para el código no asincrónico.

Qué tener en cuenta:

- Si debe `Async.Ignore` utilizar porque desea `Async.Start` utilizar u otra `Async<unit>`función que requiera, considere si descartar el resultado está bien. Evite descartar los resultados solo para ajustarse a una firma de tipo.

### <a name="asyncrunsynchronously"></a>Async.RunSynchronously

Ejecuta un cálculo asincrónico y espera su resultado en el subproceso que realiza la llamada. Esta llamada está bloqueando.

Signature:

```fsharp
computation: Async<'T> * timeout: ?int * cancellationToken: ?CancellationToken -> 'T
```

Cuándo usarlo

- Si lo necesita, úselo solo una vez en una aplicación - en el punto de entrada para un ejecutable.
- Cuando no le importa el rendimiento y desea ejecutar un conjunto de otras operaciones asincrónicas a la vez.

Qué tener en cuenta:

- Al `Async.RunSynchronously` llamar, se bloquea el subproceso que realiza la llamada hasta que se completa la ejecución.

### <a name="asyncstart"></a>Async.Start

Inicia un cálculo asincrónico `unit`en el grupo de subprocesos que devuelve . No espera su resultado. Los cálculos `Async.Start` anidados iniciados con se inician independientemente del cálculo primario que los llamó. Su vida útil no está vinculada a ningún cálculo principal. Si se cancela el cálculo primario, no se cancela ningún cálculo secundario.

Signature:

```fsharp
computation: Async<unit> * cancellationToken: ?CancellationToken -> unit
```

Utilícelo solo cuando:

- Tiene un cálculo asincrónico que no produce un resultado y/o requiere el procesamiento de uno.
- No es necesario saber cuándo se completa un cálculo asincrónico.
- No le importa en qué subproceso se ejecute un cálculo asincrónico.
- No es necesario tener en cuenta o notificar excepciones resultantes de la tarea.

Qué tener en cuenta:

- Las excepciones provocadas por `Async.Start` los cálculos iniciados con no se propagan al autor de la llamada. La pila de llamadas será completamente desenrollada.
- Cualquier trabajo (como `printfn`la `Async.Start` llamada) iniciado con no hará que el efecto ocurra en el subproceso principal de la ejecución de un programa.

## <a name="interoperate-with-net"></a>Interoperar con .NET

Es posible que esté trabajando con una biblioteca de .NET o un código base de código que use programación asincrónica [async/await](../../../standard/async.md)-style. Debido a que la mayoría de las <xref:System.Threading.Tasks.Task%601> <xref:System.Threading.Tasks.Task> bibliotecas de .NET usan `Async<'T>`los tipos y como sus abstracciones principales en lugar de , debe cruzar un límite entre estos dos enfoques de asincronía.

### <a name="how-to-work-with-net-async-and-taskt"></a>Cómo trabajar con .NET async y`Task<T>`

Trabajar con bibliotecas asincrónicas de <xref:System.Threading.Tasks.Task%601> .NET y bases de código que usan (es decir, cálculos asincrónicos que tienen valores devueltos) es sencillo y tiene compatibilidad integrada con F .

Puede utilizar `Async.AwaitTask` la función para esperar un cálculo asincrónico de .NET:

```fsharp
let getValueFromLibrary param =
    async {
        let! value = DotNetLibrary.GetValueAsync param |> Async.AwaitTask
        return value
    }
```

Puede utilizar `Async.StartAsTask` la función para pasar un cálculo asincrónico a un llamador de .NET:

```fsharp
let computationForCaller param =
    async {
        let! result = getAsyncResult param
        return result
    } |> Async.StartAsTask
```

### <a name="how-to-work-with-net-async-and-task"></a>Cómo trabajar con .NET async y`Task`

Para trabajar con las <xref:System.Threading.Tasks.Task> API que usan (es decir, cálculos asincrónicos de .NET que `Async<'T>` no <xref:System.Threading.Tasks.Task>devuelven un valor), es posible que deba agregar una función adicional que convierta un valor en :

```fsharp
module Async =
    // Async<unit> -> Task
    let startTaskFromAsyncUnit (comp: Async<unit>) =
        Async.StartAsTask comp :> Task
```

Ya hay `Async.AwaitTask` un que <xref:System.Threading.Tasks.Task> acepta un como entrada. Con esta y `startTaskFromAsyncUnit` la función definida <xref:System.Threading.Tasks.Task> anteriormente, puede iniciar y esperar tipos desde un cálculo asincrónico de F .

## <a name="relationship-to-multi-threading"></a>Relación con el multi-threading

Aunque el enhebrado se menciona a lo largo de este artículo, hay dos cosas importantes que debe recordar:

1. No hay afinidad entre un cálculo asincrónico y un subproceso, a menos que se inicie explícitamente en el subproceso actual.
1. La programación asincrónica en F no es una abstracción para multiproceso.

Por ejemplo, un cálculo puede ejecutarse realmente en el subproceso de su llamador, dependiendo de la naturaleza del trabajo. Un cálculo también podría "saltar" entre subprocesos, tomándolos prestados durante una pequeña cantidad de tiempo para realizar un trabajo útil entre períodos de "espera" (por ejemplo, cuando una llamada de red está en tránsito).

Aunque F- proporciona algunas capacidades para iniciar un cálculo asincrónico en el subproceso actual (o explícitamente no en el subproceso actual), la asincronía generalmente no está asociada a una estrategia de subprocesos determinada.

## <a name="see-also"></a>Vea también

- [El modelo de programación asincrónica de F](https://www.microsoft.com/research/publication/the-f-asynchronous-programming-model)
- [Guía asincrona de F'com](https://medium.com/jettech/f-async-guide-eb3c8a2d180a)
- [Para la diversión y la guía de programación asincrónica de beneficios](https://fsharpforfunandprofit.com/posts/concurrency-async-and-parallel/)
- [Asincrónico en C- y F-: gotchas asincrónicos en C #](http://tomasp.net/blog/csharp-async-gotchas.aspx/)
