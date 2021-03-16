---
title: Uso de la inserción de dependencias en .NET
description: Obtenga información sobre cómo usar la inserción de dependencias en las aplicaciones .NET.
author: IEvangelist
ms.author: dapine
ms.date: 11/13/2020
ms.topic: tutorial
no-loc:
- Transient
- Scoped
- Singleton
- Example
ms.openlocfilehash: d6654d5d1c8f7959e96998c18a1790cce46ebf41
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102402212"
---
# <a name="tutorial-use-dependency-injection-in-net"></a>Tutorial: Uso de la inserción de dependencias en .NET

En este tutorial se muestra cómo usar la [inserción de dependencias (DI) en .NET](dependency-injection.md). Con las *extensiones de Microsoft*, DI es un ciudadano de primera clase donde se agregan y configuran los servicios en un <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>. La interfaz de <xref:Microsoft.Extensions.Hosting.IHost> expone la instancia de <xref:System.IServiceProvider>, que actúa como un contenedor de todos los servicios registrados.

En este tutorial aprenderá a:

> [!div class="checklist"]
>
> - Crear una aplicación de consola de .NET que use la inserción de dependencias.
> - Compilar y configurar un [host genérico](generic-host.md).
> - Escribir varias interfaces y las implementaciones correspondientes.
> - Usar la duración y el ámbito del servicio para DI.

## <a name="prerequisites"></a>Requisitos previos

- [SDK de .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet) o versiones posteriores.
- Familiaridad con la creación de nuevas aplicaciones .NET y la instalación de paquetes NuGet.

## <a name="create-a-new-console-application"></a>Creación de una nueva aplicación de consola

Mediante el comando [dotnet new](../tools/dotnet-new.md) o un asistente para nuevo proyecto IDE, cree una nueva aplicación de consola .NET denominada **ConsoleDIExample** . Agregue el paquete NuGet [Microsoft.Extensions.Hosting](https://www.nuget.org/packages/Microsoft.Extensions.Hosting) al proyecto.

## <a name="add-interfaces"></a>Adición de interfaces

Agregue las siguientes interfaces al directorio raíz del proyecto:

*IOperation.cs*

:::code language="csharp" source="snippets/configuration/console-di/IOperation.cs":::

La interfaz `IOperation` define una única propiedad `OperationId`.

*ITransientOperation.cs*

:::code language="csharp" source="snippets/configuration/console-di/ITransientOperation.cs":::

*IScopedOperation.cs*

:::code language="csharp" source="snippets/configuration/console-di/IScopedOperation.cs":::

*ISingletonOperation.cs*

:::code language="csharp" source="snippets/configuration/console-di/ISingletonOperation.cs":::

Todas las subinterfaces de `IOperation` denominan su duración de servicio prevista. Por ejemplo, "Transient" o "Singleton".

## <a name="add-default-implementation"></a>Adición de la implementación predeterminada

Agregue la siguiente implementación predeterminada para las distintas operaciones:

*DefaultOperation.cs*

:::code language="csharp" source="snippets/configuration/console-di/DefaultOperation.cs":::

`DefaultOperation` implementa todas las interfaces de marcador con nombre e inicializa la propiedad `OperationId` en los cuatro últimos caracteres de un nuevo identificador único global (GUID).

## <a name="add-service-that-requires-di"></a>Adición de un servicio que requiera DI

Agregue el siguiente objeto de registrador de operaciones, que actúa como un servicio para la aplicación de consola:

*OperationLogger.cs*

:::code language="csharp" source="snippets/configuration/console-di/OperationLogger.cs":::

`OperationLogger` define un constructor que requiere cada una de las interfaces de marcador mencionadas anteriormente, es decir `ITransientOperation`, `IScopedOperation` y `ISingletonOperation`. El objeto expone un método único que permite al consumidor registrar las operaciones con un parámetro `scope` determinado. Cuando se invoca, el método `LogOperations` registra el identificador único de cada operación con la cadena de ámbito y el mensaje.

## <a name="register-services-for-di"></a>Registro de servicios para DI

Actualice *Program.cs* con el siguiente código:

:::code language="csharp" source="snippets/configuration/console-di/Program.cs" range="1-18,35-60" highlight="22-26":::

> Cada método de extensión `services.Add{SERVICE_NAME}` agrega servicios y potencialmente los configura. Se recomienda que las aplicaciones sigan esta convención. Coloque los métodos de extensión en el espacio de nombres <xref:Microsoft.Extensions.DependencyInjection?displayProperty=fullName> para encapsular grupos de registros del servicio. La inclusión de la parte del espacio de nombres `Microsoft.Extensions.DependencyInjection` para los métodos de extensión DI también:
>
> - Permite que se muestren en [IntelliSense](/visualstudio/ide/using-intellisense) sin agregar bloques `using` adicionales.
> - Evita demasiadas instrucciones `using` en las clases `Program` o `Startup`, donde se llama normalmente a estos métodos de extensión.

La aplicación:

- Crea una instancia <xref:Microsoft.Extensions.Hosting.IHostBuilder> con la [configuración de enlazador predeterminada](generic-host.md#default-builder-settings).
- Configura los servicios y los agrega con su duración de servicio correspondiente.
- Llama a <xref:Microsoft.Extensions.Hosting.IHostBuilder.Build> y asigna una instancia de <xref:Microsoft.Extensions.Hosting.IHost>.
- Llama a `ExemplifyScoping`, pasando el <xref:Microsoft.Extensions.Hosting.IHost.Services?displayProperty=nameWithType>.

## <a name="conclusion"></a>Conclusión

La aplicación muestra una salida similar a la del ejemplo siguiente:

```console
Scope 1-Call 1 .GetRequiredService<OperationLogger>(): ITransientOperation [ 80f4...Always different        ]
Scope 1-Call 1 .GetRequiredService<OperationLogger>(): IScopedOperation    [ c878...Changes only with scope ]
Scope 1-Call 1 .GetRequiredService<OperationLogger>(): ISingletonOperation [ 1586...Always the same         ]
...
Scope 1-Call 2 .GetRequiredService<OperationLogger>(): ITransientOperation [ f3c0...Always different        ]
Scope 1-Call 2 .GetRequiredService<OperationLogger>(): IScopedOperation    [ c878...Changes only with scope ]
Scope 1-Call 2 .GetRequiredService<OperationLogger>(): ISingletonOperation [ 1586...Always the same         ]

Scope 2-Call 1 .GetRequiredService<OperationLogger>(): ITransientOperation [ f9af...Always different        ]
Scope 2-Call 1 .GetRequiredService<OperationLogger>(): IScopedOperation    [ 2bd0...Changes only with scope ]
Scope 2-Call 1 .GetRequiredService<OperationLogger>(): ISingletonOperation [ 1586...Always the same         ]
...
Scope 2-Call 2 .GetRequiredService<OperationLogger>(): ITransientOperation [ fa65...Always different        ]
Scope 2-Call 2 .GetRequiredService<OperationLogger>(): IScopedOperation    [ 2bd0...Changes only with scope ]
Scope 2-Call 2 .GetRequiredService<OperationLogger>(): ISingletonOperation [ 1586...Always the same         ]
```

En la salida de la aplicación, puede ver lo siguiente:

- Las operaciones Transient siempre son diferentes y se crea una nueva instancia con cada recuperación del servicio.
- Las operaciones Scoped solo cambian con un nuevo ámbito pero son la misma instancia dentro de un ámbito.
- Las operaciones Singleton siempre son las mismas y una instancia nueva solo se crea una vez.

## <a name="see-also"></a>Vea también

* [Instrucciones para la inserción de dependencias](dependency-injection-guidelines.md)
* [Inserción de dependencias en ASP.NET Core](/aspnet/core/fundamentals/dependency-injection)
