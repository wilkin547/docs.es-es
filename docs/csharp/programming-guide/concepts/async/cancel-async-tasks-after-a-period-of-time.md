---
title: Cancelación de tareas asincrónicas tras un período de tiempo (C#)
description: Obtenga información sobre cómo programar la cancelación de cualquier tarea asociada que no se complete en un período de tiempo determinado.
ms.date: 08/19/2020
ms.topic: tutorial
ms.assetid: 194282c2-399f-46da-a7a6-96674e00b0b3
ms.openlocfilehash: ad9064f8f45a737982ffc35ab4ea2395ddae9016
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811423"
---
# <a name="cancel-async-tasks-after-a-period-of-time-c"></a>Cancelar tareas asincrónicas tras un período de tiempo (C#)

Puede cancelar una operación asincrónica después de un período de tiempo con el método <xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=nameWithType> si no quiere esperar a que finalice la operación. Este método programa la cancelación de las tareas asociadas que no se completen en el período de tiempo designado por la expresión `CancelAfter`.

Este ejemplo se agrega al código que se desarrolla en el tutorial [Cancelación de una lista de tareas (C#)](cancel-an-async-task-or-a-list-of-tasks.md) para descargar una lista de sitios web y mostrar la longitud del contenido de cada uno de ellos.

Esta tutorial abarca lo siguiente:

> [!div class="checklist"]
>
> - Actualización de una aplicación de consola .NET existente
> - Programación de una cancelación

## <a name="prerequisites"></a>Requisitos previos

Este tutorial requiere lo siguiente:

- Que haya creado una aplicación en el tutorial [Cancelación de una lista de tareas (C#)](cancel-an-async-task-or-a-list-of-tasks.md)
- [.NET 5.0 o un SDK posterior](https://dotnet.microsoft.com/download/dotnet/5.0)
- Entorno de desarrollo integrado (IDE)
  - [Se recomienda usar Visual Studio, Visual Studio Code o Visual Studio para Mac](https://visualstudio.microsoft.com).

## <a name="update-application-entry-point"></a>Actualización del punto de entrada de la aplicación

Reemplace el método `Main` existente por lo siguiente:

```csharp
static async Task Main()
{
    Console.WriteLine("Application started.");

    try
    {
        s_cts.CancelAfter(3500);

        await SumPageSizesAsync();
    }
    catch (TaskCanceledException)
    {
        Console.WriteLine("\nTasks cancelled: timed out.\n");
    }

    Console.WriteLine("Application ending.");
}
```

El método actualizado `Main` escribe algunos mensajes informativos en la consola. En la instrucción [try catch](../../../language-reference/keywords/try-catch.md), hace una llamada a <xref:System.Threading.CancellationTokenSource.CancelAfter(System.Int32)?displayProperty=nameWithType> para programar una cancelación. Esto indicará la cancelación pasado un período de tiempo.

Después, se espera al método `SumPageSizesAsync`. Si el procesamiento de todas las direcciones URL se produce más rápido que la cancelación programada, la aplicación finaliza. Pero si la cancelación programada se desencadena antes de que se procesen todas las direcciones URL, se produce una excepción <xref:System.Threading.Tasks.TaskCanceledException>.

### <a name="example-application-output"></a>Ejemplo de resultado de la aplicación

```console
Application started.

https://docs.microsoft.com                                       37,357
https://docs.microsoft.com/aspnet/core                           85,589
https://docs.microsoft.com/azure                                398,939
https://docs.microsoft.com/azure/devops                          73,663

Tasks cancelled: timed out.

Application ending.
```

## <a name="complete-example"></a>Ejemplo completo

El código siguiente es el texto completo del archivo *Program.cs* para el ejemplo.

:::code language="csharp" source="snippets/cancel-tasks/cancel-task-after-period-of-time/Program.cs":::

## <a name="see-also"></a>Vea también

- <xref:System.Threading.CancellationToken>
- <xref:System.Threading.CancellationTokenSource>
- [Programación asincrónica con async y await (C#)](index.md)
- [Cancelación de una lista de tareas (C#)](cancel-an-async-task-or-a-list-of-tasks.md)
