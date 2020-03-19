---
title: Generación y consumo de secuencias asincrónicas
description: En este tutorial avanzado se muestran escenarios donde la generación y utilización de secuencias asincrónicas proporciona una manera más natural de trabajar con secuencias de datos que pueden generarse de forma asincrónica.
ms.date: 02/10/2019
ms.technology: csharp-async
ms.custom: mvc
ms.openlocfilehash: de090eb9cc1e8b511956313ab5169ee4d07a492f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79156745"
---
# <a name="tutorial-generate-and-consume-async-streams-using-c-80-and-net-core-30"></a>Tutorial: Generación y uso de secuencias asincrónicas con C# 8.0 y .NET Core 3.0

C#8.0 presenta **secuencias asincrónicas**, que modelan un origen de datos en secuencias cuando los elementos de la secuencia de datos se pueden recuperar o generar de forma asincrónica. Las secuencias asincrónicas se basan en las nuevas interfaces presentadas en .NET Standard 2.1 e implementadas en .NET Core 3.0 para proporcionar un modelo de programación natural para orígenes de datos de secuencias asincrónicas.

En este tutorial aprenderá lo siguiente:

> [!div class="checklist"]
>
> - Crear un origen de datos que genera una secuencia de elementos de datos de forma asincrónica.
> - Utilizar ese origen de datos de forma asincrónica.
> - Reconocer cuándo la interfaz y el origen de datos nuevos son preferibles a las secuencias de datos sincrónicas anteriores.

## <a name="prerequisites"></a>Requisitos previos

Deberá configurar la máquina para ejecutar .NET Core, incluido el compilador de C# 8.0. El compilador de C# 8 está disponible a partir de la [versión 16.3 de Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) o del [SDK de .NET Core 3.0](https://dotnet.microsoft.com/download).

Deberá crear un [token de acceso de GitHub](https://help.github.com/articles/creating-a-personal-access-token-for-the-command-line/#creating-a-token) para poder tener acceso al punto de conexión de GraphQL de GitHub. Seleccione los siguientes permisos para el token de acceso de GitHub:

- repo:status
- public_repo

Guarde el token de acceso en un lugar seguro para usarlo a fin de obtener acceso al punto de conexión de API de GitHub.

> [!WARNING]
> Mantenga seguro su token de acceso personal. Cualquier software con su token de acceso personal podría realizar llamadas de API de GitHub con sus derechos de acceso.

En este tutorial se da por supuesto que está familiarizado con C# y. NET, incluidos Visual Studio o la CLI de .NET Core.

## <a name="run-the-starter-application"></a>Ejecución de la aplicación de inicio

Puede obtener el código para la aplicación de inicio utilizada en este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples) de la carpeta [csharp/tutoriales/AsyncStreams](https://github.com/dotnet/samples/tree/master/csharp/tutorials/AsyncStreams/start).

La aplicación de inicio es una aplicación de consola que usa la interfaz [GraphQL de GitHub](https://developer.github.com/v4/) para recuperar las incidencias recientes escritas en el repositorio [dotnet/docs](https://github.com/dotnet/docs). Comience por mirar el código siguiente para el método `Main` de la aplicación de inicio:

[!code-csharp[StarterAppMain](~/samples/snippets/csharp/tutorials/AsyncStreams/start/IssuePRreport/IssuePRreport/Program.cs#StarterAppMain)]

Puede establecer una variable de entorno `GitHubKey` para el token de acceso personal, o bien puede reemplazar el último argumento en la llamada a `GenEnvVariable` por el token de acceso personal. No incluya el código de acceso en el código fuente si va a guardar el origen con otras personas o va a ponerlo en un repositorio de código fuente compartido.

Después de crear el cliente de GitHub, el código de `Main` crea un objeto de informe de progreso y un token de cancelación. Una vez que se crean esos objetos, `Main` llama a `runPagedQueryAsync` para recuperar las 250 incidencias creadas más recientemente. Una vez finalizada esa tarea, se muestran los resultados.

Al ejecutar la aplicación inicial, puede realizar algunas observaciones importantes acerca de cómo se ejecuta esta aplicación.  Verá el progreso notificado para cada página devuelta desde GitHub. Puede observar una pausa marcada antes de que GitHub devuelva cada nueva página de incidencias. Por último, se muestran las incidencias solo después de que se hayan recuperado 10 páginas de GitHub.

## <a name="examine-the-implementation"></a>Examen de la implementación

La implementación revela por qué observó el comportamiento descrito en la sección anterior. Examine el código de `runPagedQueryAsync`:

[!code-csharp[RunPagedQueryStarter](~/samples/snippets/csharp/tutorials/AsyncStreams/start/IssuePRreport/IssuePRreport/Program.cs#RunPagedQuery)]

Vamos a concentrarnos en el algoritmo de paginación y la estructura asincrónica del código anterior. (Puede consultar la [documentación de GraphQL de GitHub](https://developer.github.com/v4/guides/) para obtener más información sobre la API de GraphQL de GitHub). El método `runPagedQueryAsync` enumera las incidencias desde la más reciente hasta la más antigua. Solicita 25 incidencias por página y examina la estructura `pageInfo` de la respuesta para continuar con la página anterior. Eso sigue al soporte de paginación estándar de GraphQL para respuestas de varias páginas. La respuesta incluye un objeto `pageInfo` que incluye a su vez un valor `hasPreviousPages` y un valor `startCursor` usado para solicitar la página anterior. Las incidencias se encuentran en la matriz `nodes`. El método `runPagedQueryAsync` anexa estos nodos a una matriz que contiene todos los resultados de todas las páginas.

Después de recuperar y restaurar una página de resultados, `runPagedQueryAsync` informa del progreso y comprueba la cancelación. Si se ha solicitado la cancelación, `runPagedQueryAsync` lanza un <xref:System.OperationCanceledException>.

Hay varios elementos en este código que se pueden mejorar. Lo más importante, `runPagedQueryAsync` debe asignar el almacenamiento para todas las incidencias devueltas. Este ejemplo se detiene en 250 incidencias porque la recuperación de todas las incidencias abiertas requeriría mucha más memoria para almacenar todas las incidencias recuperadas. Además, los protocolos para admitir el progreso y la cancelación hacen que el algoritmo sea más difícil de comprender en su primera lectura. Debe buscar la clase de progreso para saber dónde se notifica el progreso. También tiene que realizar un seguimiento de las comunicaciones a través de <xref:System.Threading.CancellationTokenSource> y su <xref:System.Threading.CancellationToken> asociado para comprender dónde se solicita la cancelación y dónde se concede.

## <a name="async-streams-provide-a-better-way"></a>Las secuencias asincrónicas ofrecen una manera mejor

Las secuencias asincrónicas y el lenguaje asociado abordan todas estas cuestiones. El código que genera la secuencia ahora puede usar `yield return` para devolver los elementos en un método que se declaró con el modificador `async`. Puede usar una secuencia asincrónica utilizando un bucle `await foreach` igual que puede usar una secuencia mediante un bucle `foreach`.

Estas nuevas características del lenguaje dependen de tres nuevas interfaces agregadas a .NET Standard 2.1 e implementadas en .NET Core 3.0:

```csharp
namespace System.Collections.Generic
{
    public interface IAsyncEnumerable<out T>
    {
        IAsyncEnumerator<T> GetAsyncEnumerator(CancellationToken cancellationToken = default);
    }

    public interface IAsyncEnumerator<out T> : IAsyncDisposable
    {
        T Current { get; }

        ValueTask<bool> MoveNextAsync();
    }
}

namespace System
{
    public interface IAsyncDisposable
    {
        ValueTask DisposeAsync();
    }
}
```

Estas tres interfaces deben resultar familiares a la mayoría de desarrolladores de C#. Se comportan de manera similar con sus contrapartes sincrónicas:

- <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.IEnumerator%601?displayProperty=nameWithType>
- <xref:System.IDisposable?displayProperty=nameWithType>

Un tipo que podría ser desconocido es <xref:System.Threading.Tasks.ValueTask?displayProperty=nameWithType>. La estructura `ValueTask` proporciona una API similar a la clase <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>. `ValueTask` se usa en estas interfaces por motivos de rendimiento.

## <a name="convert-to-async-streams"></a>Conversión en secuencias asincrónicas

A continuación, convierta el método `runPagedQueryAsync` para generar una secuencia asincrónica. En primer lugar, cambie la signatura de `runPagedQueryAsync` para que devuelva un `IAsyncEnumerable<JToken>`y quite el token de cancelación y los objetos de progreso de la lista de parámetros como se muestra en el código siguiente:

[!code-csharp[FinishedSignature](~/samples/snippets/csharp/tutorials/AsyncStreams/finished/IssuePRreport/IssuePRreport/Program.cs#UpdateSignature)]

El código de inicio procesa cada página a medida que se recupera, tal como se muestra en el código siguiente:

[!code-csharp[StarterPaging](~/samples/snippets/csharp/tutorials/AsyncStreams/start/IssuePRreport/IssuePRreport/Program.cs#ProcessPage)]

Reemplace esas tres líneas por el código siguiente:

[!code-csharp[FinishedPaging](~/samples/snippets/csharp/tutorials/AsyncStreams/finished/IssuePRreport/IssuePRreport/Program.cs#YieldReturnPage)]

También puede quitar la declaración de `finalResults` anteriormente en este método y la instrucción `return` que sigue al bucle modificado.

Ha terminado los cambios para generar una secuencia asincrónica. El método finalizado debe ser similar al siguiente código:

[!code-csharp[FinishedGenerate](~/samples/snippets/csharp/tutorials/AsyncStreams/finished/IssuePRreport/IssuePRreport/Program.cs#GenerateAsyncStream)]

A continuación, cambie el código que utiliza la colección para usar la secuencia asincrónica. Busque el código siguiente en `Main` que procesa la colección de incidencias:

[!code-csharp[EnumerateOldStyle](~/samples/snippets/csharp/tutorials/AsyncStreams/start/IssuePRreport/IssuePRreport/Program.cs#EnumerateOldStyle)]

Reemplace el código por el siguiente bucle `await foreach`:

[!code-csharp[FinishedEnumerateAsyncStream](~/samples/snippets/csharp/tutorials/AsyncStreams/finished/IssuePRreport/IssuePRreport/Program.cs#EnumerateAsyncStream)]

Los elementos de secuencia se procesan de forma predeterminada en el contexto capturado. Si quiere deshabilitar la captura del contexto, use el método de extensión <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType>. Para obtener más información sobre los contextos de sincronización y la captura del contexto actual, vea el artículo sobre el [consumo del patrón asincrónico basado en tareas](../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md).

Puede obtener el código para el tutorial finalizado en el repositorio [dotnet/samples](https://github.com/dotnet/samples) de la carpeta [csharp/tutoriales/AsyncStreams](https://github.com/dotnet/samples/tree/master/csharp/tutorials/AsyncStreams/finished).

## <a name="run-the-finished-application"></a>Ejecución de la aplicación finalizada

Vuelva a ejecutar la aplicación. Compare su comportamiento con el comportamiento de la aplicación de inicio. La primera página de resultados se enumera en cuanto está disponible. Hay una pausa marcada cada vez que se solicita y se recupera una página nueva; a continuación, se enumeran rápidamente los resultados de la página siguiente. El bloque `try` / `catch` no es necesario para controlar la cancelación: el autor de la llamada puede detener la enumeración de la colección. El progreso se notifica claramente porque la secuencia asincrónica genera resultados a medida que se descarga cada página. El estado de cada problema devuelto se incluye sin problemas en el bucle `await foreach`. No necesita un objeto de devolución de llamada para hacer un seguimiento del progreso.

Puede ver mejoras en el uso de la memoria examinando el código. Ya no tiene que asignar una colección para almacenar todos los resultados antes de que se enumeren. El autor de la llamada puede determinar cómo consumir los resultados y si se necesita una colección de almacenamiento.

Ejecute las aplicaciones de inicio y finalizada y podrá ver las diferencias entre las implementaciones personalmente. Puede eliminar el token de acceso de GitHub que creó cuando inició este tutorial cuando haya terminado. Si un atacante obtuviera acceso a dicho token, podría tener acceso a sus API de GitHub con sus credenciales.
