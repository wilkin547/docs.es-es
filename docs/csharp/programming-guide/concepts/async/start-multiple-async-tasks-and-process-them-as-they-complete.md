---
title: Procesamiento de tareas asincrónicas a medida que se completan
description: En este ejemplo se muestra cómo usar Task.WhenAny en C# para iniciar varias tareas y procesar los resultados a medida que finalizan, en lugar de procesarlos en el orden en que se inician.
ms.date: 08/19/2020
ms.assetid: 25331850-35a7-43b3-ab76-3908e4346b9d
ms.openlocfilehash: 860e94a9c3973ce56e7321741a1136f752aa3d18
ms.sourcegitcommit: 636af37170ae75a11c4f7d1ecd770820e7dfe7bd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2020
ms.locfileid: "91805244"
---
# <a name="process-asynchronous-tasks-as-they-complete-c"></a>Iniciar varias tareas asincrónicas y procesarlas a medida que se completan (C#)

Si usa <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>, puede iniciar varias tareas a la vez y procesarlas una por una a medida que se completen, en lugar de procesarlas en el orden en el que se han iniciado.

En el siguiente ejemplo se usa una consulta para crear una colección de tareas. Cada tarea descarga el contenido de un sitio web especificado. En cada iteración de un bucle while, una llamada awaited a <xref:System.Threading.Tasks.Task.WhenAny%2A> devuelve la tarea en la colección de tareas que termine primero su descarga. Esa tarea se quita de la colección y se procesa. El bucle se repite hasta que la colección no contiene más tareas.

## <a name="create-example-application"></a>Creación de una aplicación de ejemplo

Cree una nueva aplicación de consola de .NET Core. Puede crear una mediante el comando [dotnet new console](../../../../core/tools/dotnet-new.md#console) o desde [Visual Studio](/visualstudio/install/install-visual-studio). Abra el archivo *Program.cs* en su editor de código favorito.

### <a name="replace-using-statements"></a>Reemplazo de instrucciones using

Reemplace las instrucciones using existentes por estas declaraciones:

```csharp
using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.Linq;
using System.Net.Http;
using System.Threading.Tasks;
```

## <a name="add-fields"></a>Adición de campos

Dentro de la definición de la clase `Program`, agregue los dos campos siguientes:

```csharp
static readonly HttpClient s_client = new HttpClient
{
    MaxResponseContentBufferSize = 1_000_000
};

static readonly IEnumerable<string> s_urlList = new string[]
{
    "https://docs.microsoft.com",
    "https://docs.microsoft.com/aspnet/core",
    "https://docs.microsoft.com/azure",
    "https://docs.microsoft.com/azure/devops",
    "https://docs.microsoft.com/dotnet",
    "https://docs.microsoft.com/dynamics365",
    "https://docs.microsoft.com/education",
    "https://docs.microsoft.com/enterprise-mobility-security",
    "https://docs.microsoft.com/gaming",
    "https://docs.microsoft.com/graph",
    "https://docs.microsoft.com/microsoft-365",
    "https://docs.microsoft.com/office",
    "https://docs.microsoft.com/powershell",
    "https://docs.microsoft.com/sql",
    "https://docs.microsoft.com/surface",
    "https://docs.microsoft.com/system-center",
    "https://docs.microsoft.com/visualstudio",
    "https://docs.microsoft.com/windows",
    "https://docs.microsoft.com/xamarin"
};
```

`HttpClient` expone la capacidad de enviar solicitudes HTTP y de recibir respuestas HTTP. `s_urlList` contiene todas las direcciones URL que planea procesar la aplicación.

## <a name="update-application-entry-point"></a>Actualización del punto de entrada de la aplicación

El punto de entrada principal de la aplicación de consola es el método `Main`. Reemplace el método existente por lo siguiente:

```csharp
static Task Main() => SumPageSizesAsync();
```

El método `Main` actualizado ahora se considera un método [Async main](../../../whats-new/csharp-7.md#async-main), el cual permite un punto de entrada asincrónico en el archivo ejecutable. Se trata de una llamada a `SumPageSizesAsync`.

## <a name="create-the-asynchronous-sum-page-sizes-method"></a>Creación de un método SumPageSizes asincrónico

Agregue el método `SumPageSizesAsync` después del método `Main`:

```csharp
static async Task SumPageSizesAsync()
{
    var stopwatch = Stopwatch.StartNew();

    IEnumerable<Task<int>> downloadTasksQuery =
        from url in s_urlList
        select ProcessUrlAsync(url, s_client);

    List<Task<int>> downloadTasks = downloadTasksQuery.ToList();

    int total = 0;
    while (downloadTasks.Any())
    {
        Task<int> finishedTask = await Task.WhenAny(downloadTasks);
        downloadTasks.Remove(finishedTask);
        total += await finishedTask;
    }

    stopwatch.Stop();

    Console.WriteLine($"\nTotal bytes returned:  {total:#,#}");
    Console.WriteLine($"Elapsed time:          {stopwatch.Elapsed}\n");
}
```

El método comienza creando una instancia e iniciando una clase <xref:System.Diagnostics.Stopwatch>. Después, incluye una consulta que, cuando se ejecuta, crea una colección de tareas. Cada llamada a `ProcessUrlAsync` en el siguiente código devuelve un objeto <xref:System.Threading.Tasks.Task%601>, donde `TResult` es un entero:

```csharp
IEnumerable<Task<int>> downloadTasksQuery =
    from url in s_urlList
    select ProcessUrlAsync(url, s_client);
```

Debido a la [ejecución diferida](../../../../standard/linq/deferred-execution-example.md) con LINQ, se llama a <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> para iniciar cada tarea.

```csharp
List<Task<int>> downloadTasks = downloadTasksQuery.ToList();
```

El bucle `while` realiza los pasos siguientes para cada tarea de la colección:

1. Espera una llamada a `WhenAny` para identificar la primera tarea de la colección que ha finalizado su descarga.

    ```csharp
    Task<int> firstFinishedTask = await Task.WhenAny(downloadTasks);
    ```

1. Quita la tarea de la colección.

    ```csharp
    downloadTasks.Remove(firstFinishedTask);
    ```

1. Espera `finishedTask`, que se devuelve mediante una llamada a `ProcessUrlAsync`. La variable `finishedTask` es un <xref:System.Threading.Tasks.Task%601> donde `TResult` es un entero. La tarea ya está completa, pero la espera para recuperar la longitud del sitio web descargado, como se muestra en el ejemplo siguiente. Si se produce un error en la tarea, `await` iniciará la primera excepción secundaria almacenada en `AggregateException`, en lugar de leer la propiedad <xref:System.Threading.Tasks.Task%601.Result?displayProperty=nameWithType> que iniciaría la excepción `AggregateException`.

    ```csharp
    total += await finishedTask;
    ```

## <a name="add-process-method"></a>Adición de un método de proceso

Agregue el siguiente método `ProcessUrlAsync` después del método `SumPageSizesAsync`:

```csharp
static async Task<int> ProcessUrlAsync(string url, HttpClient client)
{
    byte[] content = await client.GetByteArrayAsync(url);
    Console.WriteLine($"{url,-60} {content.Length,10:#,#}");

    return content.Length;
}
```

Para cualquier dirección URL, el método usará la instancia de `client` proporcionada para obtener la respuesta como `byte[]`. La longitud se devuelve después de que la dirección URL y la longitud se escriban en la consola.

Ejecute el programa varias veces para comprobar que las longitudes que se han descargado no aparecen siempre en el mismo orden.

> [!CAUTION]
> Puede usar `WhenAny` en un bucle, como se describe en el ejemplo, para solucionar problemas que implican un número reducido de tareas. Sin embargo, otros enfoques son más eficaces si hay que procesar un gran número de tareas. Para más información y ejemplos, vea [Processing Tasks as they complete](https://devblogs.microsoft.com/pfxteam/processing-tasks-as-they-complete) (Procesar tareas a medida que se completan).

## <a name="complete-example"></a>Ejemplo completo

El código siguiente es el texto completo del archivo *Program.cs* para el ejemplo.

:::code language="csharp" source="snippets/multiple-tasks/Program.cs":::

## <a name="see-also"></a>Vea también

- <xref:System.Threading.Tasks.Task.WhenAny%2A>
- [Programación asincrónica con async y await (C#)](index.md)
