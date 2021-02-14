---
title: 'Cambio importante: Propiedades obsoletas en ConsoleLoggerOptions'
description: Obtenga información sobre el cambio importante de .NET 5.0 en las bibliotecas básicas de .NET, donde el tipo ConsoleLoggerFormat y algunas propiedades de ConsoleLoggerOptions ahora están obsoletos.
ms.date: 11/01/2020
ms.openlocfilehash: bd039dfa84ae3399d7fb36f992010a9a3c9f6ddf
ms.sourcegitcommit: 4df8e005c074ceb1f978f007b222fe253be2baf3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2021
ms.locfileid: "99548388"
---
# <a name="obsolete-properties-on-consoleloggeroptions"></a><span data-ttu-id="d0bbf-103">Propiedades obsoletas en ConsoleLoggerOptions</span><span class="sxs-lookup"><span data-stu-id="d0bbf-103">Obsolete properties on ConsoleLoggerOptions</span></span>

<span data-ttu-id="d0bbf-104">El tipo <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat?displayProperty=nameWithType> y algunas propiedades de <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> ahora están obsoletos.</span><span class="sxs-lookup"><span data-stu-id="d0bbf-104">The <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat?displayProperty=nameWithType> type and some properties on <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> are now obsolete.</span></span>

## <a name="change-description"></a><span data-ttu-id="d0bbf-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="d0bbf-105">Change description</span></span>

<span data-ttu-id="d0bbf-106">A partir de .NET 5.0, el tipo <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat?displayProperty=nameWithType> y varias propiedades de <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> están obsoletos.</span><span class="sxs-lookup"><span data-stu-id="d0bbf-106">Starting in .NET 5.0, the <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat?displayProperty=nameWithType> type and several properties on <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> are obsolete.</span></span> <span data-ttu-id="d0bbf-107">Las propiedades obsoletas son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="d0bbf-107">The obsolete properties are:</span></span>

- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.IncludeScopes?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.TimestampFormat?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.UseUtcTimestamp?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format?displayProperty=nameWithType>

<span data-ttu-id="d0bbf-108">Con la introducción de nuevos formateadores, estas propiedades ahora están disponibles en los formateadores individuales.</span><span class="sxs-lookup"><span data-stu-id="d0bbf-108">With the introduction of new formatters, these properties are now available on the individual formatters.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="d0bbf-109">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="d0bbf-109">Reason for change</span></span>

<span data-ttu-id="d0bbf-110">La propiedad <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format> es un tipo de enumeración, que no puede representar un formateador personalizado.</span><span class="sxs-lookup"><span data-stu-id="d0bbf-110">The <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format> property is an enumeration type, which cannot represent a custom formatter.</span></span>

<span data-ttu-id="d0bbf-111">Las propiedades restantes se han establecido en <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> y se han aplicado a los formatos integrados para los registros de la consola.</span><span class="sxs-lookup"><span data-stu-id="d0bbf-111">The remaining properties were set on <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> and applied to both of the built-in formats for console logs.</span></span> <span data-ttu-id="d0bbf-112">Pero con la introducción de una nueva API de formateador, tiene más sentido representar el formato en las opciones específicas del formateador.</span><span class="sxs-lookup"><span data-stu-id="d0bbf-112">However, with the introduction of a new formatter API, it makes more sense for formatting to be represented on the formatter-specific options.</span></span> <span data-ttu-id="d0bbf-113">Este cambio proporciona una mejor separación entre los formateadores de registrador y el registrador.</span><span class="sxs-lookup"><span data-stu-id="d0bbf-113">This change provides better separation between the logger and logger formatters.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="d0bbf-114">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="d0bbf-114">Version introduced</span></span>

<span data-ttu-id="d0bbf-115">5.0</span><span class="sxs-lookup"><span data-stu-id="d0bbf-115">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="d0bbf-116">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="d0bbf-116">Recommended action</span></span>

- <span data-ttu-id="d0bbf-117">Use la nueva propiedad <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName?displayProperty=nameWithType> en lugar de la propiedad <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d0bbf-117">Use the new <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName?displayProperty=nameWithType> property in place of the <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="d0bbf-118">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d0bbf-118">For example:</span></span>

  ```csharp
  loggingBuilder.AddConsole(options =>
  {
    options.FormatterName = ConsoleFormatterNames.Systemd;
  });
  ```

  <span data-ttu-id="d0bbf-119">Hay varias diferencias entre <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName> y <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format>:</span><span class="sxs-lookup"><span data-stu-id="d0bbf-119">There are several differences between <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName> and <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format>:</span></span>

  - <span data-ttu-id="d0bbf-120"><xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format> solo tiene dos opciones posibles: `Default` y `Systemd`.</span><span class="sxs-lookup"><span data-stu-id="d0bbf-120"><xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format> has only two possible options: `Default` and `Systemd`.</span></span>
  - <span data-ttu-id="d0bbf-121"><xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName> no distingue mayúsculas de minúsculas y puede ser cualquier cadena.</span><span class="sxs-lookup"><span data-stu-id="d0bbf-121"><xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName> is case insensitive and can be any string.</span></span> <span data-ttu-id="d0bbf-122">Los nombres integrados reservados son `Simple`, `Systemd` y `Json` (.NET 5.0 y versiones posteriores).</span><span class="sxs-lookup"><span data-stu-id="d0bbf-122">The reserved, built-in names are `Simple`, `Systemd`, and `Json` (.NET 5.0 and later).</span></span>
  - <span data-ttu-id="d0bbf-123">`"Format": "Systemd"` se asigna a `"FormatterName": "Systemd"`.</span><span class="sxs-lookup"><span data-stu-id="d0bbf-123">`"Format": "Systemd"` maps to `"FormatterName": "Systemd"`.</span></span>
  - <span data-ttu-id="d0bbf-124">`"Format": "Default"` se asigna a `"FormatterName": "Simple"`.</span><span class="sxs-lookup"><span data-stu-id="d0bbf-124">`"Format": "Default"` maps to `"FormatterName": "Simple"`.</span></span>

- <span data-ttu-id="d0bbf-125">En el caso de las propiedades <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors>, <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.IncludeScopes>, <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.TimestampFormat> y <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.UseUtcTimestamp>, use en su lugar la propiedad correspondiente en los nuevos tipos <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterOptions>, <xref:Microsoft.Extensions.Logging.Console.JsonConsoleFormatterOptions>o <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions>.</span><span class="sxs-lookup"><span data-stu-id="d0bbf-125">For the <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors>, <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.IncludeScopes>, <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.TimestampFormat>, and <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.UseUtcTimestamp> properties, use the corresponding property on the new <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterOptions>, <xref:Microsoft.Extensions.Logging.Console.JsonConsoleFormatterOptions>, or <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions> types instead.</span></span> <span data-ttu-id="d0bbf-126">Por ejemplo, la configuración correspondiente para <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors?displayProperty=nameWithType> es <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions.ColorBehavior?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d0bbf-126">For example, the corresponding setting for <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors?displayProperty=nameWithType> is <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions.ColorBehavior?displayProperty=nameWithType>.</span></span>

  <span data-ttu-id="d0bbf-127">Código anterior:</span><span class="sxs-lookup"><span data-stu-id="d0bbf-127">Previous code:</span></span>

  ```csharp
  loggingBuilder.AddConsole(options =>
  {
      options.DisableColors = true;
  });
  ```

  <span data-ttu-id="d0bbf-128">Nuevo código:</span><span class="sxs-lookup"><span data-stu-id="d0bbf-128">New code:</span></span>

  ```csharp
  loggingBuilder.AddSimpleConsole(options =>
  {
      options.ColorBehavior = LoggerColorBehavior.Disabled;
  });
  ```

<span data-ttu-id="d0bbf-129">En los dos fragmentos de código JSON siguientes se muestra cómo cambia el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="d0bbf-129">The following two JSON snippets show how the configuration file changes.</span></span> <span data-ttu-id="d0bbf-130">Archivo de configuración anterior:</span><span class="sxs-lookup"><span data-stu-id="d0bbf-130">Old configuration file:</span></span>

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

<span data-ttu-id="d0bbf-131">Archivo de configuración nuevo:</span><span class="sxs-lookup"><span data-stu-id="d0bbf-131">New configuration file:</span></span>

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

## <a name="affected-apis"></a><span data-ttu-id="d0bbf-132">API afectadas</span><span class="sxs-lookup"><span data-stu-id="d0bbf-132">Affected APIs</span></span>

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
