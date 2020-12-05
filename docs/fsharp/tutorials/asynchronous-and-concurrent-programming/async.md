---
title: Programación asincrónica
description: 'Obtenga información sobre cómo F # proporciona compatibilidad limpia para asincronía basándose en un modelo de programación de nivel de lenguaje derivado de conceptos básicos de la programación funcional.'
ms.date: 08/15/2020
ms.openlocfilehash: 04b397ddbfb468aa3bc4ee245175d3ec9bdedb50
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "96739332"
---
# <a name="async-programming-in-f"></a>Programación asincrónica en F\#

La programación asincrónica es un mecanismo fundamental para las aplicaciones modernas por diversos motivos. Hay dos casos de uso principales en los que se encontrarán la mayoría de los desarrolladores:

- Presentar un proceso de servidor que pueda dar servicio a un número significativo de solicitudes entrantes simultáneas, al tiempo que se minimizan los recursos del sistema ocupados mientras el procesamiento de solicitudes espera entradas de sistemas o servicios externos a ese proceso.
- Mantener una interfaz de usuario con capacidad de respuesta o un subproceso principal mientras progresa simultáneamente el trabajo en segundo plano

Aunque el trabajo en segundo plano implica la utilización de varios subprocesos, es importante tener en cuenta los conceptos de asincronía y multithreading por separado. De hecho, son aspectos independientes y uno no implica el otro. En este artículo se describen los conceptos independientes con más detalle.

## <a name="asynchrony-defined"></a>Asincronía definido

El punto anterior, que asincronía es independiente del uso de varios subprocesos, merece la pena explicar un poco más. Hay tres conceptos que a veces están relacionados, pero estrictamente independientes entre sí:

- Simultaneidad Cuando se ejecutan varios cálculos en períodos de tiempo superpuestos.
- Paralelismo cuando varios cálculos o varias partes de un único cálculo se ejecutan exactamente al mismo tiempo.
- Asincronía Cuando uno o varios cálculos pueden ejecutarse por separado desde el flujo del programa principal.

Los tres son conceptos ortogonales, pero se pueden reagrupar fácilmente, especialmente cuando se usan juntos. Por ejemplo, puede que necesite ejecutar varios cálculos asincrónicos en paralelo. Esta relación no significa que el paralelismo o asincronía impliquen entre sí.

Si tiene en cuenta el etymology de la palabra "Asynchronous", hay dos partes implicadas:

- "a", que significa "no".
- "sincrónico", que significa "al mismo tiempo".

Al colocar estos dos términos juntos, verá que "asincrónico" significa "no al mismo tiempo". Eso es todo. No hay ninguna implicación de simultaneidad o paralelismo en esta definición. Esto también se aplica en la práctica.

En términos prácticos, los cálculos asincrónicos en F # están programados para ejecutarse independientemente del flujo principal del programa. Esta ejecución independiente no implica simultaneidad ni paralelismo, ni implica que un cálculo siempre se produce en segundo plano. De hecho, los cálculos asincrónicos pueden incluso ejecutarse sincrónicamente, dependiendo de la naturaleza del cálculo y del entorno en el que se ejecuta el cálculo.

La principal ventaja que debe tener es que los cálculos asincrónicos son independientes del flujo principal del programa. Aunque hay pocas garantías sobre cuándo o cómo se ejecuta un cálculo asincrónico, existen algunos enfoques para orquestarlos y programarlos. En el resto de este artículo se exploran los conceptos básicos de F # asincronía y cómo usar los tipos, las funciones y las expresiones integradas en F #.

## <a name="core-concepts"></a>Conceptos principales

En F #, la programación asincrónica se centra en torno a tres conceptos básicos:

- El `Async<'T>` tipo, que representa un cálculo asincrónico que admite composición.
- Las `Async` funciones del módulo, que permiten programar el trabajo asincrónico, componer los cálculos asincrónicos y transformar los resultados asincrónicos.
- `async { }` [Expresión de cálculo](../../language-reference/computation-expressions.md), que proporciona una sintaxis adecuada para compilar y controlar los cálculos asincrónicos.

Puede ver estos tres conceptos en el ejemplo siguiente:

```fsharp
open System
open System.IO

let printTotalFileBytes path =
    async {
        let! bytes = File.ReadAllBytesAsync(path) |> Async.AwaitTask
        let fileName = Path.GetFileName(path)
        printfn $"File {fileName} has %d{bytes.Length} bytes"
    }

[<EntryPoint>]
let main argv =
    printTotalFileBytes "path-to-file.txt"
    |> Async.RunSynchronously

    Console.Read() |> ignore
    0
```

En el ejemplo, la `printTotalFileBytes` función es de tipo `string -> Async<unit>` . La llamada a la función no ejecuta realmente el cálculo asincrónico. En su lugar, devuelve un `Async<unit>` que actúa como *especificación* del trabajo que se va a ejecutar de forma asincrónica. Llama `Async.AwaitTask` a en su cuerpo, que convierte el resultado de <xref:System.IO.File.ReadAllBytesAsync%2A> en un tipo adecuado.

Otra línea importante es la llamada a `Async.RunSynchronously` . Esta es una de las funciones de inicio del módulo Async que debe llamar si desea ejecutar realmente un cálculo asincrónico de F #.

Esta es una diferencia fundamental con el estilo C#/Visual Basic de `async` programación. En F #, los cálculos asincrónicos se pueden considerar como **tareas en frío**. Deben iniciarse explícitamente para ejecutarse realmente. Esto tiene algunas ventajas, ya que permite combinar y secuenciar el trabajo asincrónico de forma mucho más sencilla que en C# o Visual Basic.

## <a name="combine-asynchronous-computations"></a>Combinar cálculos asincrónicos

Este es un ejemplo que se basa en el anterior mediante la combinación de cálculos:

```fsharp
open System
open System.IO

let printTotalFileBytes path =
    async {
        let! bytes = File.ReadAllBytesAsync(path) |> Async.AwaitTask
        let fileName = Path.GetFileName(path)
        printfn $"File {fileName} has %d{bytes.Length} bytes"
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

Como puede ver, la `main` función tiene bastantes llamadas más. Conceptualmente, hace lo siguiente:

1. Transforme los argumentos de la línea de comandos en `Async<unit>` cálculos con `Array.map` .
2. Cree un `Async<'T[]>` que programe y ejecute los `printTotalFileBytes` cálculos en paralelo cuando se ejecute.
3. Cree un `Async<unit>` que ejecutará el cálculo en paralelo y omitirá su resultado.
4. Ejecute explícitamente el último cálculo con `Async.RunSynchronously` y bloquee hasta que se complete.

Cuando se ejecuta este programa, `printTotalFileBytes` se ejecuta en paralelo para cada argumento de la línea de comandos. Dado que los cálculos asincrónicos se ejecutan de forma independiente del flujo de programa, no hay ningún orden en el que impriman su información y terminen de ejecutarse. Los cálculos se programarán en paralelo, pero no se garantiza su orden de ejecución.

## <a name="sequence-asynchronous-computations"></a>Cálculos asincrónicos de secuencia

Dado `Async<'T>` que es una especificación de trabajo en lugar de una tarea que ya se está ejecutando, puede realizar fácilmente transformaciones más complejas. Este es un ejemplo que secuencia un conjunto de cálculos asincrónicos para que se ejecuten uno tras otro.

```fsharp
let printTotalFileBytes path =
    async {
        let! bytes = File.ReadAllBytesAsync(path) |> Async.AwaitTask
        let fileName = Path.GetFileName(path)
        printfn $"File {fileName} has %d{bytes.Length} bytes"
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

Esto programará `printTotalFileBytes` para que se ejecute en el orden de los elementos de en `argv` lugar de programarlos en paralelo. Dado que el siguiente elemento no se programará hasta que haya finalizado la ejecución del último cálculo, los cálculos se secuenciarán de modo que no se superpongan en su ejecución.

## <a name="important-async-module-functions"></a>Funciones importantes del módulo Async

Al escribir código asincrónico en F #, normalmente interactuará con un marco que controla la programación de los cálculos. Sin embargo, este no es siempre el caso, por lo que es conveniente conocer las distintas funciones de inicio para programar el trabajo asincrónico.

Dado que los cálculos asincrónicos de F # son una _especificación_ del trabajo en lugar de una representación del trabajo que ya se está ejecutando, deben iniciarse explícitamente con una función de inicio. Hay muchos [métodos de inicio asincrónico](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpasync.html#section0) que son útiles en contextos diferentes. En la siguiente sección se describen algunas de las funciones de inicio más comunes.

### <a name="asyncstartchild"></a>Async. Startchild (

Inicia un cálculo secundario dentro de un cálculo asincrónico. Esto permite ejecutar simultáneamente varios cálculos asincrónicos. El cálculo secundario comparte un token de cancelación con el cálculo primario. Si se cancela el cálculo primario, también se cancela el cálculo de los elementos secundarios.

Signature:

```fsharp
computation: Async<'T> * timeout: ?int -> Async<Async<'T>>
```

Cuándo usarlo:

- Cuando se desea ejecutar varios cálculos asincrónicos simultáneamente en lugar de uno en uno, pero no se programan en paralelo.
- Cuando desea asociar la duración de un cálculo secundario al de un cálculo primario.

Qué debe ver:

- Iniciar varios cálculos con `Async.StartChild` no es lo mismo que programarlos en paralelo. Si desea programar cálculos en paralelo, use `Async.Parallel` .
- Si se cancela un cálculo primario, se desencadenará la cancelación de todos los cálculos secundarios que se iniciaron.

### <a name="asyncstartimmediate"></a>Async. StartImmediate (

Ejecuta un cálculo asincrónico y comienza inmediatamente en el subproceso actual del sistema operativo. Esto resulta útil si necesita actualizar algo en el subproceso de llamada durante el cálculo. Por ejemplo, si un cálculo asincrónico debe actualizar una interfaz de usuario (por ejemplo, actualizar una barra de progreso), `Async.StartImmediate` debe usarse.

Signature:

```fsharp
computation: Async<unit> * cancellationToken: ?CancellationToken -> unit
```

Cuándo usarlo:

- Cuando es necesario actualizar algo en el subproceso que realiza la llamada en medio de un cálculo asincrónico.

Qué debe ver:

- El código del cálculo asincrónico se ejecutará en cualquier subproceso en el que se programe. Esto puede ser problemático si ese subproceso es sensiblemente confidencial, como un subproceso de la interfaz de usuario. En tales casos, `Async.StartImmediate` es probable que no sea apropiado usar.

### <a name="asyncstartastask"></a>Async. Startastask (

Ejecuta un cálculo en el grupo de subprocesos. Devuelve un <xref:System.Threading.Tasks.Task%601> que se completará en el estado correspondiente una vez finalizado el cálculo (genera el resultado, produce la excepción o se cancela). Si no se proporciona ningún token de cancelación, se usará el token de cancelación predeterminado.

Signature:

```fsharp
computation: Async<'T> * taskCreationOptions: ?TaskCreationOptions * cancellationToken: ?CancellationToken -> Task<'T>
```

Cuándo usarlo:

- Cuando necesita llamar a una API de .NET que espera que <xref:System.Threading.Tasks.Task%601> represente el resultado de un cálculo asincrónico.

Qué debe ver:

- Esta llamada asignará un `Task` objeto adicional, lo que puede aumentar la sobrecarga si se usa con frecuencia.

### <a name="asyncparallel"></a>Async. Parallel

Programa una secuencia de cálculos asincrónicos que se van a ejecutar en paralelo. El grado de paralelismo se puede optimizar o limitar opcionalmente especificando el `maxDegreesOfParallelism` parámetro.

Signature:

```fsharp
computations: seq<Async<'T>> * ?maxDegreesOfParallelism: int -> Async<'T[]>
```

Cuándo usarlo

- Si necesita ejecutar un conjunto de cálculos al mismo tiempo y no depende de su orden de ejecución.
- Si no necesita resultados de los cálculos programados en paralelo hasta que todos se hayan completado.

Qué debe ver:

- Solo se puede tener acceso a la matriz de valores resultante una vez finalizados todos los cálculos.
- Los cálculos se ejecutarán cuando acaben de programarse. Este comportamiento significa que no se puede confiar en su orden de ejecución.

### <a name="asyncsequential"></a>Async. Sequential

Programa una secuencia de cálculos asincrónicos que se van a ejecutar en el orden en que se pasan. Se ejecutará el primer cálculo, después el siguiente, y así sucesivamente. No se ejecutarán cálculos en paralelo.

Signature:

```fsharp
computations: seq<Async<'T>> -> Async<'T[]>
```

Cuándo usarlo

- Si tiene que ejecutar varios cálculos en orden.

Qué debe ver:

- Solo se puede tener acceso a la matriz de valores resultante una vez finalizados todos los cálculos.
- Los cálculos se ejecutarán en el orden en que se pasan a esta función, lo que puede significar que habrá más tiempo antes de que se devuelvan los resultados.

### <a name="asyncawaittask"></a>Async. Awaittask (

Devuelve un cálculo asincrónico que espera <xref:System.Threading.Tasks.Task%601> a que se complete el determinado y devuelve su resultado como un `Async<'T>`

Signature:

```fsharp
task: Task<'T> -> Async<'T>
```

Cuándo usarlo:

- Cuando se utiliza una API de .NET que devuelve un <xref:System.Threading.Tasks.Task%601> en un cálculo asincrónico de F #.

Qué debe ver:

- Las excepciones se incluyen en <xref:System.AggregateException> la siguiente Convención de la biblioteca de Parallel Task y este comportamiento es diferente de la forma en que F # Async normalmente muestra excepciones.

### <a name="asynccatch"></a>Async. Catch

Crea un cálculo asincrónico que ejecuta un determinado `Async<'T>` y devuelve un `Async<Choice<'T, exn>>` . Si el especificado `Async<'T>` se completa correctamente, `Choice1Of2` se devuelve un con el valor resultante. Si se produce una excepción antes de que se complete, `Choice2of2` se devuelve un con la excepción generada. Si se usa en un cálculo asincrónico que se compone de muchos cálculos y uno de esos cálculos produce una excepción, el cálculo de la englobación se detendrá por completo en su totalidad.

Signature:

```fsharp
computation: Async<'T> -> Async<Choice<'T, exn>>
```

Cuándo usarlo:

- Cuando se realiza el trabajo asincrónico que puede producir un error con una excepción y se desea controlar esa excepción en el llamador.

Qué debe ver:

- Cuando se usan cálculos asincrónicos combinados o secuenciados, el cálculo de la englobación se detendrá por completo si uno de sus cálculos "internos" produce una excepción.

### <a name="asyncignore"></a>Async. ignore

Crea un cálculo asincrónico que ejecuta el cálculo especificado y omite su resultado.

Signature:

```fsharp
computation: Async<'T> -> Async<unit>
```

Cuándo usarlo:

- Cuando tiene un cálculo asincrónico cuyo resultado no es necesario. Esto es análogo al `ignore` código para el código no asincrónico.

Qué debe ver:

- Si debe usar `Async.Ignore` porque desea utilizar `Async.Start` u otra función que requiera `Async<unit>` , considere la posibilidad de descartar el resultado. Evite descartar los resultados solo para ajustarse a una firma de tipo.

### <a name="asyncrunsynchronously"></a>Async. RunSynchronously

Ejecuta un cálculo asincrónico y espera su resultado en el subproceso que realiza la llamada. Esta llamada está bloqueando.

Signature:

```fsharp
computation: Async<'T> * timeout: ?int * cancellationToken: ?CancellationToken -> 'T
```

Cuándo usarlo

- Si lo necesita, úselo solo una vez en una aplicación: en el punto de entrada de un archivo ejecutable.
- Cuando no le interesa el rendimiento y desea ejecutar un conjunto de otras operaciones asincrónicas a la vez.

Qué debe ver:

- La llamada a `Async.RunSynchronously` bloquea el subproceso que realiza la llamada hasta que se completa la ejecución.

### <a name="asyncstart"></a>Async. Start

Inicia un cálculo asincrónico en el grupo de subprocesos que devuelve `unit` . No espera el resultado. Los cálculos anidados iniciados con `Async.Start` se inician independientemente del cálculo primario que los llamó. Su duración no está asociada a ningún cálculo primario. Si se cancela el cálculo primario, no se cancelan los cálculos secundarios.

Signature:

```fsharp
computation: Async<unit> * cancellationToken: ?CancellationToken -> unit
```

Use solo cuando:

- Tiene un cálculo asincrónico que no produce un resultado ni requiere procesamiento de uno.
- No es necesario saber cuándo se completa un cálculo asincrónico.
- No le importa en qué subproceso se ejecuta un cálculo asincrónico.
- No es necesario tener en cuenta ni notificar las excepciones resultantes de la tarea.

Qué debe ver:

- Las excepciones producidas por los cálculos iniciados con `Async.Start` no se propagan al autor de la llamada. La pila de llamadas se desenredará por completo.
- Cualquier trabajo (como llamar a `printfn` ) iniciado con `Async.Start` no hará que el efecto se produzca en el subproceso principal de la ejecución de un programa.

## <a name="interoperate-with-net"></a>Interoperar con .NET

Puede estar trabajando con una biblioteca de .NET o código base de C# que utiliza la programación asincrónica de estilo [Async/Await](../../../standard/async.md). Dado que C# y la mayoría de las bibliotecas de .NET usan los <xref:System.Threading.Tasks.Task%601> <xref:System.Threading.Tasks.Task> tipos y como abstracciones principales en lugar de `Async<'T>` , debe cruzar un límite entre estos dos enfoques a asincronía.

### <a name="how-to-work-with-net-async-and-taskt"></a>Cómo trabajar con .NET Async y `Task<T>`

Trabajar con las bibliotecas asincrónicas .NET y códigos base que usan <xref:System.Threading.Tasks.Task%601> (es decir, los cálculos asincrónicos que tienen valores devueltos) es sencillo y tiene compatibilidad integrada con F #.

Puede usar la `Async.AwaitTask` función para esperar un cálculo asincrónico de .net:

```fsharp
let getValueFromLibrary param =
    async {
        let! value = DotNetLibrary.GetValueAsync param |> Async.AwaitTask
        return value
    }
```

Puede usar la `Async.StartAsTask` función para pasar un cálculo asincrónico a un llamador de .net:

```fsharp
let computationForCaller param =
    async {
        let! result = getAsyncResult param
        return result
    } |> Async.StartAsTask
```

### <a name="how-to-work-with-net-async-and-task"></a>Cómo trabajar con .NET Async y `Task`

Para trabajar con las API que usan <xref:System.Threading.Tasks.Task> (es decir, los cálculos asincrónicos de .net que no devuelven un valor), puede que necesite agregar una función adicional que convierta un `Async<'T>` en un <xref:System.Threading.Tasks.Task> :

```fsharp
module Async =
    // Async<unit> -> Task
    let startTaskFromAsyncUnit (comp: Async<unit>) =
        Async.StartAsTask comp :> Task
```

Ya existe una `Async.AwaitTask` que acepta <xref:System.Threading.Tasks.Task> como entrada. Con esta y la función definida anteriormente `startTaskFromAsyncUnit` , puede iniciar y esperar <xref:System.Threading.Tasks.Task> tipos de un cálculo asincrónico de F #.

## <a name="relationship-to-multi-threading"></a>Relación con Multi-Threading

Aunque los subprocesos se mencionan en este artículo, hay dos aspectos importantes que hay que recordar:

1. No hay ninguna afinidad entre un cálculo asincrónico y un subproceso, a menos que se inicie explícitamente en el subproceso actual.
1. La programación asincrónica en F # no es una abstracción para multithreading.

Por ejemplo, un cálculo puede ejecutarse realmente en el subproceso del llamador, dependiendo de la naturaleza del trabajo. Un cálculo también podría "saltar" entre subprocesos, por lo que se le prestará una pequeña cantidad de tiempo para realizar un trabajo útil entre los períodos de "en espera" (por ejemplo, cuando una llamada de red está en tránsito).

Aunque F # proporciona algunas funciones para iniciar un cálculo asincrónico en el subproceso actual (o explícitamente no en el subproceso actual), asincronía generalmente no está asociado a una estrategia de subprocesos determinada.

## <a name="see-also"></a>Consulte también

- [Modelo de programación asincrónica de F #](https://www.microsoft.com/research/publication/the-f-asynchronous-programming-model)
- [Guía de F # Async de jet. com](https://medium.com/jettech/f-async-guide-eb3c8a2d180a)
- [Guía de programación asincrónica de F # para diversión y beneficios](https://fsharpforfunandprofit.com/posts/concurrency-async-and-parallel/)
- [Async en C# y F #: problemas asincrónicos en C #](http://tomasp.net/blog/csharp-async-gotchas.aspx/)
