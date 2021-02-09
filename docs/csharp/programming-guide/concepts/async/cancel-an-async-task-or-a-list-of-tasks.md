---
title: Cancelación de una lista de tareas (C#)
description: Aprenda a usar tokens de cancelación para indicar una solicitud de cancelación a una lista de tareas.
ms.date: 02/03/2021
ms.topic: tutorial
ms.assetid: eec32dbb-70ea-4c88-bd27-fa2e34546914
ms.openlocfilehash: 532c61ab6499583620ba2ee5c710c58f7886f89d
ms.sourcegitcommit: 65af0f0ad316858882845391d60ef7e303b756e8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "99585746"
---
# <a name="cancel-a-list-of-tasks-c"></a>Cancelación de una lista de tareas (C#)

Puede cancelar una aplicación de consola asincrónica si no quiere esperar a que termine. Mediante el ejemplo de este tema, puede agregar una cancelación a una aplicación que descargue el contenido de una lista de sitios web. Puede cancelar muchas tareas asociando la instancia de <xref:System.Threading.CancellationTokenSource> a cada tarea. Si se presiona la tecla <kbd>Entrar</kbd>, se cancelan todas las tareas que aún no se han completado.

Esta tutorial abarca lo siguiente:

> [!div class="checklist"]
>
> - Creación de una aplicación de consola de .NET
> - Escritura de una aplicación asincrónica que admite la cancelación
> - Demostración de la señalización de una cancelación

## <a name="prerequisites"></a>Requisitos previos

Este tutorial requiere lo siguiente:

- [.NET 5.0 o un SDK posterior](https://dotnet.microsoft.com/download/dotnet/5.0)
- Entorno de desarrollo integrado (IDE)
  - [Se recomienda usar Visual Studio, Visual Studio Code o Visual Studio para Mac](https://visualstudio.microsoft.com).

### <a name="create-example-application"></a>Creación de una aplicación de ejemplo

Cree una nueva aplicación de consola de .NET Core. Puede crear una mediante el comando [`dotnet new console`](../../../../core/tools/dotnet-new.md#console) o desde [Visual Studio](/visualstudio/install/install-visual-studio). Abra el archivo *Program.cs* en su editor de código favorito.

### <a name="replace-using-statements"></a>Reemplazo de instrucciones using

Reemplace las instrucciones using existentes por estas declaraciones:

```csharp
using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using System.Threading;
using System.Threading.Tasks;
```

## <a name="add-fields"></a>Adición de campos

Dentro de la definición de la clase `Program`, agregue estos tres campos:

```csharp
static readonly CancellationTokenSource s_cts = new CancellationTokenSource();

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

<xref:System.Threading.CancellationTokenSource> se usa para indicar una cancelación solicitada a un token de cancelación (<xref:System.Threading.CancellationToken>). `HttpClient` expone la capacidad de enviar solicitudes HTTP y de recibir respuestas HTTP. `s_urlList` contiene todas las direcciones URL que planea procesar la aplicación.

## <a name="update-application-entry-point"></a>Actualización del punto de entrada de la aplicación

El punto de entrada principal de la aplicación de consola es el método `Main`. Reemplace el método existente por lo siguiente:

```csharp
static async Task Main()
{
    Console.WriteLine("Application started.");
    Console.WriteLine("Press the ENTER key to cancel...\n");

    Task cancelTask = Task.Run(() =>
    {
        while (Console.ReadKey().Key != ConsoleKey.Enter)
        {
            Console.WriteLine("Press the ENTER key to cancel...");
        }

        Console.WriteLine("\nENTER key pressed: cancelling downloads.\n");
        s_cts.Cancel();
    });

    Task sumPageSizesTask = SumPageSizesAsync();

    await Task.WhenAny(new[] { cancelTask, sumPageSizesTask });

    Console.WriteLine("Application ending.");
}
```

El método `Main` actualizado ahora se considera un método [Async main](../../../whats-new/csharp-7.md#async-main), el cual permite un punto de entrada asincrónico en el archivo ejecutable. Escribe algunos mensajes informativos en la consola y, luego, declara una instancia de <xref:System.Threading.Tasks.Task> denominada `cancelTask`, la cual leerá las pulsaciones de teclas de la consola. Si se presiona la tecla <kbd>Entrar</kbd>, se realiza una llamada a <xref:System.Threading.CancellationTokenSource.Cancel?displayProperty=nameWithType>. Esto indicará la cancelación. Después, se asigna la variable `sumPageSizesTask` desde el método `SumPageSizesAsync` y ambas tareas se pasan a <xref:System.Threading.Tasks.Task.WhenAny(System.Threading.Tasks.Task[])?displayProperty=nameWithType>, que continuará cuando se complete cualquiera de las dos tareas.

## <a name="create-the-asynchronous-sum-page-sizes-method"></a>Creación de un método SumPageSizes asincrónico

Agregue el método `SumPageSizesAsync` después del método `Main`:

```csharp
static async Task SumPageSizesAsync()
{
    var stopwatch = Stopwatch.StartNew();

    int total = 0;
    foreach (string url in s_urlList)
    {
        int contentLength = await ProcessUrlAsync(url, s_client, s_cts.Token);
        total += contentLength;
    }

    stopwatch.Stop();

    Console.WriteLine($"\nTotal bytes returned:  {total:#,#}");
    Console.WriteLine($"Elapsed time:          {stopwatch.Elapsed}\n");
}
```

El método comienza creando una instancia e iniciando una clase <xref:System.Diagnostics.Stopwatch>. Luego, recorre en bucle cada dirección URL en `s_urlList` y llama a `ProcessUrlAsync`. Con cada iteración, se pasa el token `s_cts.Token` al método `ProcessUrlAsync` y el código devuelve una clase <xref:System.Threading.Tasks.Task%601>, donde `TResult` es un entero:

```csharp
int total = 0;
foreach (string url in s_urlList)
{
    int contentLength = await ProcessUrlAsync(url, s_client, s_cts.Token);
    total += contentLength;
}
```

## <a name="add-process-method"></a>Adición de un método de proceso

Agregue el siguiente método `ProcessUrlAsync` después del método `SumPageSizesAsync`:

```csharp
static async Task<int> ProcessUrlAsync(string url, HttpClient client, CancellationToken token)
{
    HttpResponseMessage response = await client.GetAsync(url, token);
    byte[] content = await response.Content.ReadAsByteArrayAsync(token);
    Console.WriteLine($"{url,-60} {content.Length,10:#,#}");

    return content.Length;
}
```

Para cualquier dirección URL, el método usará la instancia de `client` proporcionada para obtener la respuesta como `byte[]`. La instancia de <xref:System.Threading.CancellationToken> se pasa a los métodos <xref:System.Net.Http.HttpClient.GetAsync(System.String,System.Threading.CancellationToken)?displayProperty=nameWithType> y <xref:System.Net.Http.HttpContent.ReadAsByteArrayAsync?displayProperty=nameWithType>. El token (`token`) se usa para registrar la cancelación solicitada. La longitud se devuelve después de que la dirección URL y la longitud se escriban en la consola.

### <a name="example-application-output"></a>Ejemplo de resultado de la aplicación

```console
Application started.
Press the ENTER key to cancel...

https://docs.microsoft.com                                       37,357
https://docs.microsoft.com/aspnet/core                           85,589
https://docs.microsoft.com/azure                                398,939
https://docs.microsoft.com/azure/devops                          73,663
https://docs.microsoft.com/dotnet                                67,452
https://docs.microsoft.com/dynamics365                           48,582
https://docs.microsoft.com/education                             22,924

ENTER key pressed: cancelling downloads.

Application ending.
```

## <a name="complete-example"></a>Ejemplo completo

El código siguiente es el texto completo del archivo *Program.cs* para el ejemplo.

:::code language="csharp" source="snippets/cancel-tasks/cancel-tasks/Program.cs":::

## <a name="see-also"></a>Vea también

- <xref:System.Threading.CancellationToken>
- <xref:System.Threading.CancellationTokenSource>
- [Programación asincrónica con async y await (C#)](index.md)

## <a name="next-steps"></a>Pasos siguientes

> [!div class="nextstepaction"]
> [Cancelar tareas asincrónicas tras un período de tiempo (C#)](cancel-async-tasks-after-a-period-of-time.md)
