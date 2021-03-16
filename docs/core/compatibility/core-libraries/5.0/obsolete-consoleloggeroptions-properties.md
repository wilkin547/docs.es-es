---
title: 'Cambio importante: Propiedades obsoletas en ConsoleLoggerOptions'
description: Obtenga información sobre el cambio importante de .NET 5 en las bibliotecas básicas de .NET, donde el tipo ConsoleLoggerFormat y algunas propiedades de ConsoleLoggerOptions ahora están obsoletos.
ms.date: 11/01/2020
ms.openlocfilehash: c6ee294f90e304cebd517bd0139c58a6c7a41e0c
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257315"
---
# <a name="obsolete-properties-on-consoleloggeroptions"></a>Propiedades obsoletas en ConsoleLoggerOptions

El tipo <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat?displayProperty=nameWithType> y algunas propiedades de <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> ahora están obsoletos.

## <a name="change-description"></a>Descripción del cambio

A partir de .NET 5, el tipo <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat?displayProperty=nameWithType> y varias propiedades de <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> están obsoletos. Las propiedades obsoletas son las siguientes:

- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.IncludeScopes?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.TimestampFormat?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.UseUtcTimestamp?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format?displayProperty=nameWithType>

Con la introducción de nuevos formateadores, estas propiedades ahora están disponibles en los formateadores individuales.

## <a name="reason-for-change"></a>Motivo del cambio

La propiedad <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format> es un tipo de enumeración, que no puede representar un formateador personalizado.

Las propiedades restantes se han establecido en <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> y se han aplicado a los formatos integrados para los registros de la consola. Pero con la introducción de una nueva API de formateador, tiene más sentido representar el formato en las opciones específicas del formateador. Este cambio proporciona una mejor separación entre los formateadores de registrador y el registrador.

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="recommended-action"></a>Acción recomendada

- Use la nueva propiedad <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName?displayProperty=nameWithType> en lugar de la propiedad <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format?displayProperty=nameWithType>. Por ejemplo:

  ```csharp
  loggingBuilder.AddConsole(options =>
  {
    options.FormatterName = ConsoleFormatterNames.Systemd;
  });
  ```

  Hay varias diferencias entre <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName> y <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format>:

  - <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format> solo tiene dos opciones posibles: `Default` y `Systemd`.
  - <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName> no distingue mayúsculas de minúsculas y puede ser cualquier cadena. Los nombres integrados reservados son `Simple`, `Systemd` y `Json` (.NET 5 y versiones posteriores).
  - `"Format": "Systemd"` se asigna a `"FormatterName": "Systemd"`.
  - `"Format": "Default"` se asigna a `"FormatterName": "Simple"`.

- En el caso de las propiedades <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors>, <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.IncludeScopes>, <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.TimestampFormat> y <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.UseUtcTimestamp>, use en su lugar la propiedad correspondiente en los nuevos tipos <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterOptions>, <xref:Microsoft.Extensions.Logging.Console.JsonConsoleFormatterOptions>o <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions>. Por ejemplo, la configuración correspondiente para <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors?displayProperty=nameWithType> es <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions.ColorBehavior?displayProperty=nameWithType>.

  Código anterior:

  ```csharp
  loggingBuilder.AddConsole(options =>
  {
      options.DisableColors = true;
  });
  ```

  Nuevo código:

  ```csharp
  loggingBuilder.AddSimpleConsole(options =>
  {
      options.ColorBehavior = LoggerColorBehavior.Disabled;
  });
  ```

En los dos fragmentos de código JSON siguientes se muestra cómo cambia el archivo de configuración. Archivo de configuración anterior:

```json
{
  "Logging": {
    "LogLevel": {
      "Default": "None",
      "Microsoft": "Warning",
      "Microsoft.Hosting.Lifetime": "Information"
    },

    "Console": {
      "LogLevel": {
        "Default": "Information"
      },
      "Format": "Systemd",
      "IncludeScopes": true,
      "TimestampFormat": "HH:mm:ss",
      "UseUtcTimestamp": true
    }
  },
  "AllowedHosts": "*"
}
```

Archivo de configuración nuevo:

```json
{
  "Logging": {
    "LogLevel": {
      "Default": "None",
      "Microsoft": "Warning",
      "Microsoft.Hosting.Lifetime": "Information"
    },

    "Console": {
      "LogLevel": {
        "Default": "Information"
      },
      "FormatterName": "Systemd",
      "FormatterOptions": {
        "IncludeScopes": true,
        "TimestampFormat": "HH:mm:ss",
        "UseUtcTimestamp": true
      }
    }
  },
  "AllowedHosts": "*"
}
```

## <a name="affected-apis"></a>API afectadas

- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors?displayProperty=fullName>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.IncludeScopes?displayProperty=fullName>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.TimestampFormat?displayProperty=fullName>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.UseUtcTimestamp?displayProperty=fullName>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format?displayProperty=fullName>

<!--

#### Category

- Core .NET libraries
- ASP.NET

### Affected APIs

- `P:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors`
- `P:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.IncludeScopes`
- `P:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.TimestampFormat`
- `P:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.UseUtcTimestamp`
- `P:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format`

-->
