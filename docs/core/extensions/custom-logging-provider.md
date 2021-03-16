---
title: Implementación de un proveedor de registro personalizado en .NET
description: Obtenga información sobre cómo implementar un proveedor de registro personalizado en las aplicaciones .NET.
author: IEvangelist
ms.author: dapine
ms.date: 09/25/2020
ms.topic: how-to
ms.openlocfilehash: 3a0af6296c2ade15ff1b75dce5a5f99bfe235ebf
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "102402072"
---
# <a name="implement-a-custom-logging-provider-in-net"></a>Implementación de un proveedor de registro personalizado en .NET

Hay muchos [proveedores de registro](logging-providers.md) disponibles para las necesidades de registro habituales. Puede que tenga que implementar un <xref:Microsoft.Extensions.Logging.ILoggerProvider> personalizado cuando uno de los proveedores disponibles no se ajuste a las necesidades de su aplicación. En este artículo, aprenderá a implementar un proveedor de registro personalizado que se puede usar para colorear los registros en la consola.

### <a name="sample-custom-logger-configuration"></a>Configuración de registrador personalizado de ejemplo

En el ejemplo se crean diferentes entradas de consola de color por nivel de registro e identificador de evento con el siguiente tipo de configuración:

:::code language="csharp" source="snippets/configuration/console-custom-logging/ColorConsoleLoggerConfiguration.cs":::

El código anterior establece el nivel predeterminado en `Information`, el color en `Green` y el `EventId` en `0` de forma implícita.

### <a name="create-the-custom-logger"></a>Creación del registrador personalizado

El nombre de la categoría de implementación `ILogger` es normalmente el origen del registro. Por ejemplo, el tipo en el que se crea el registrador:

:::code language="csharp" source="snippets/configuration/console-custom-logging/ColorConsoleLogger.cs":::

El código anterior:

- Crea una instancia del registrador por nombre de categoría.
- Comprueba `logLevel == _config.LogLevel` en `IsEnabled`, por lo que cada `logLevel` tiene un registrador único. Los registradores también se deben habilitar para todos los niveles de registro superiores:

:::code language="csharp" source="snippets/configuration/console-custom-logging/ColorConsoleLogger.cs" range="16-17":::

## <a name="custom-logger-provider"></a>Proveedor de registrador personalizado

El objeto `ILoggerProvider` es responsable de crear las instancias de registrador. Tal vez no sea necesario crear una instancia del registrador por categoría, pero esto tiene sentido para algunos registradores, como NLog o log4net. Al hacerlo, también se podrán elegir diferentes destinos de salida de registro por categoría, en caso necesario:

:::code language="csharp" source="snippets/configuration/console-custom-logging/ColorConsoleLoggerProvider.cs":::

En el código anterior, <xref:Microsoft.Build.Logging.LoggerDescription.CreateLogger%2A> crea una única instancia de `ColorConsoleLogger` por nombre de categoría y la almacena en [`ConcurrentDictionary<TKey,TValue>`](/dotnet/api/system.collections.concurrent.concurrentdictionary-2).

## <a name="usage-and-registration-of-the-custom-logger"></a>Uso y registro del registrador personalizado

Para agregar el proveedor de registro personalizado y el registrador correspondiente, agregue un <xref:Microsoft.Extensions.Logging.ILoggerProvider> con <xref:Microsoft.Extensions.Logging.ILoggingBuilder> desde <xref:Microsoft.Extensions.Hosting.HostingHostBuilderExtensions.ConfigureLogging(Microsoft.Extensions.Hosting.IHostBuilder,System.Action{Microsoft.Extensions.Logging.ILoggingBuilder})?displayProperty=nameWithType>:

:::code language="csharp" source="snippets/configuration/console-custom-logging/Program.cs" range="23-39":::

`ILoggingBuilder` crea una o más instancias de `ILogger`. El marco de trabajo usa las instancias de `ILogger` para registrar la información.

Para el código anterior, proporcione al menos un método de extensión para `ILoggerFactory`:

:::code language="csharp" source="snippets/configuration/console-custom-logging/Extensions/ColorConsoleLoggerExtensions.cs":::

La ejecución de esta aplicación simple se representará de forma similar a la siguiente ventana de la consola:

:::image type="content" source="media/color-console-logger.png" alt-text="Salida de ejemplo del registrador de la consola de color":::

## <a name="see-also"></a>Vea también

- [Registro en .NET](logging.md).
- [Proveedores de registro en .NET](logging-providers.md).
- [Registro de alto rendimiento en .NET](high-performance-logging.md).
