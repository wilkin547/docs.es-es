---
title: Formato de registro de la consola
description: Aprenda a usar el formato de registro de la consola disponible o a implementar el formato de registro personalizado para las aplicaciones .NET.
author: IEvangelist
ms.author: dapine
ms.date: 12/17/2020
ms.openlocfilehash: 0ec8fc2018febe4273aa646d1682be197933f925
ms.sourcegitcommit: 3d6d6595a03915f617349781f455f838a44b0f44
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2020
ms.locfileid: "102402198"
---
# <a name="console-log-formatting"></a>Formato de registro de la consola

En .NET 5, se ha agregado compatibilidad con el formato personalizado a los registros de la consola en el espacio de nombres `Microsoft.Extensions.Logging.Console`. Hay tres opciones de formato predefinidas disponibles: [`Simple`](#simple), [`Systemd`](#systemd) y [`Json`](#json).

> [!IMPORTANT]
> Anteriormente, la enumeración <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat> permitía seleccionar el formato de registro deseado, como inteligible, que era `Default`, o como una sola línea, lo que también se conoce como `Systemd`. Sin embargo, **no** eran personalizables y ahora están en desuso.

En este artículo, obtendrá información sobre los formateadores de registros de la consola. En el código fuente de ejemplo se muestra cómo hacer lo siguiente:

- Registrar un formateador nuevo
- Seleccionar un formateador registrado para usarlo
  - Mediante código o [configuración](configuration.md)
- Implementar un formateador personalizado
  - Actualizar la configuración mediante <xref:Microsoft.Extensions.Options.IOptionsMonitor%601>
  - Habilitar el formato de color personalizado

## <a name="register-formatter"></a>Registro del formateador

El [proveedor de registros `Console`](logging-providers.md#console) tiene varios formateadores predefinidos y expone la capacidad de crear su propio formateador personalizado. Para registrar cualquiera de los formateadores disponibles, use el método de extensión `Add{Type}Console` correspondiente:

| Tipos disponibles | Método para registrar el tipo |
|--|--|
| <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Json?displayProperty=nameWithType> | <xref:Microsoft.Extensions.Logging.ConsoleLoggerExtensions.AddJsonConsole%2A?displayProperty=nameWithType> |
| <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Simple?displayProperty=nameWithType> | <xref:Microsoft.Extensions.Logging.ConsoleLoggerExtensions.AddSimpleConsole%2A?displayProperty=nameWithType> |
| <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Systemd?displayProperty=nameWithType> | <xref:Microsoft.Extensions.Logging.ConsoleLoggerExtensions.AddSystemdConsole%2A?displayProperty=nameWithType> |

### <a name="simple"></a>Simple

Para usar el formateador de consola `Simple`, regístrelo con `AddSimpleConsole`:

:::code language="csharp" source="snippets/logging/console-formatter-simple/Program.cs" highlight="11-16":::

En el código fuente de ejemplo anterior, se registró el formateador <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Simple?displayProperty=nameWithType>. Proporciona registros con la posibilidad de no solo ajustar información, como el tiempo y el nivel de registro de cada mensaje de registro, sino que también permite la inserción de color ANSI y la sangría de los mensajes.

### <a name="systemd"></a>Systemd

Registrador de la consola <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Systemd?displayProperty=nameWithType>:

- Usa el formato de nivel de registro "Syslog" y los niveles de gravedad.
- **No** da formato a los mensajes con colores.
- Siempre registra mensajes en una sola línea.

Esto suele ser útil para los contenedores, que a menudo usan el registro de la consola `Systemd`. Con .NET 5, el registrador de la consola `Simple` también habilita una versión compacta que registra en una sola línea y también permite deshabilitar colores como se muestra en un ejemplo anterior.

:::code language="csharp" source="snippets/logging/console-formatter-systemd/Program.cs" highlight="11-15":::

### <a name="json"></a>Json

Para escribir registros en formato JSON, se usa el formateador de la consola `Json`. El código fuente de ejemplo muestra cómo una aplicación ASP.NET Core podría realizar el registro. Con la plantilla `webapp`, cree una aplicación ASP.NET Core con el comando [dotnet new](../tools/dotnet-new.md):

```dotnetcli
dotnet new webapp -o Console.ExampleFormatters.Json
```

Al ejecutar la aplicación con el código de plantilla, obtiene el formato de registro predeterminado siguiente:

```
info: Microsoft.Hosting.Lifetime[0]
      Now listening on: https://localhost:5001
```

De forma predeterminada, se selecciona el formateador de registros de la consola `Simple` con la configuración predeterminada. Para cambiar esto, llame a `AddJsonConsole` en *Program.cs*:

:::code language="csharp" source="snippets/logging/console-formatter-json/Program.cs" highlight="17-26":::

Vuelva a ejecutar la aplicación, con el cambio anterior; ahora, el mensaje de registro adopta el formato JSON:

:::code language="json" source="snippets/logging/console-formatter-json/example-output.json":::

> [!TIP]
> De forma predeterminada, el formateador de la consola `Json` registra cada mensaje en una sola línea. Para mejorar la legibilidad mientras se configura el formateador, establezca <xref:System.Text.Json.JsonWriterOptions.Indented?displayProperty=nameWithType> en `true`.

## <a name="set-formatter-with-configuration"></a>Definición del formateador con configuración

En los ejemplos anteriores se ha mostrado cómo registrar un formateador mediante programación. Como alternativa, puede hacerlo con la [configuración](configuration.md). Considere el código fuente de ejemplo de aplicación web anterior; si actualiza el archivo *appsettings.json* en lugar de llamar a `ConfigureLogging` en el archivo *Program.cs*, podría obtener el mismo resultado. El archivo `appsettings.json` actualizado configuraría el formateador como sigue:

:::code language="json" source="snippets/logging/console-formatter-json/appsettings.json" highlight="14-23":::

Los dos valores de clave que se deben establecer son `"FormatterName"` y `"FormatterOptions"`. Si ya está registrado un formateador con el valor establecido para `"FormatterName"`, se selecciona ese formateador y se pueden configurar sus propiedades siempre que se proporcionen como una clave dentro del nodo `"FormatterOptions"`. Los nombres de formateador predefinidos se reservan en <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames>:

- <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Json?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Simple?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Systemd?displayProperty=nameWithType>

## <a name="implement-a-custom-formatter"></a>Implementar un formateador personalizado

Para implementar un formateador personalizado, debe hacer lo siguiente:

- Cree una subclase de <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatter>, que representa el formateador personalizado.
- Registre el formateador personalizado con:
  - <xref:Microsoft.Extensions.Logging.ConsoleLoggerExtensions.AddConsole%2A?displayProperty=nameWithType>
  - <xref:Microsoft.Extensions.Logging.ConsoleLoggerExtensions.AddConsoleFormatter%60%602(Microsoft.Extensions.Logging.ILoggingBuilder,System.Action{%60%601})?displayProperty=nameWithType>

Cree un método de extensión para administrar esto automáticamente:

:::code language="csharp" source="snippets/logging/console-formatter-custom/ConsoleLoggerExtensions.cs" highlight="11-12":::

Los elementos `CustomOptions` se definen de la manera siguiente:

:::code language="csharp" source="snippets/logging/console-formatter-custom/CustomOptions.cs":::

En el código anterior, las opciones son una subclase de <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterOptions>.

La API `AddConsoleFormatter` hace lo siguiente:

- Registra una subclase de `ConsoleFormatter`.
- Controla la configuración:
  - Usa un token de cambio para sincronizar las actualizaciones, según el [patrón de opciones](options.md), y la interfaz [IOptionsMonitor](xref:Microsoft.Extensions.Options.IOptionsMonitor%601).

:::code language="csharp" source="snippets/logging/console-formatter-custom/Program.cs" highlight="11-12":::

Defina una subclase `CustomerFormatter` de `ConsoleFormatter`:

:::code language="csharp" source="snippets/logging/console-formatter-custom/CustomFormatter.cs" highlight="24-45":::

La API `CustomFormatter.Write<TState>` anterior determina qué texto se ajusta alrededor de cada mensaje de registro. Un estándar `ConsoleFormatter` debe ser capaz de ajustar en torno a los ámbitos, las marcas de tiempo y el nivel de gravedad de los registros, como mínimo. Además, puede codificar los colores ANSI en los mensajes de registro y proporcionar también las sangrías deseadas. La implementación de `CustomFormatter.Write<TState>` carece de estas funcionalidades.

Para obtener información sobre cómo personalizar aún más el formato, vea las implementaciones existentes en el espacio de nombres `Microsoft.Extensions.Logging.Console`:

- [SimpleConsoleFormatter](https://github.com/dotnet/runtime/blob/master/src/libraries/Microsoft.Extensions.Logging.Console/src/SimpleConsoleFormatter.cs)
- [SystemdConsoleFormatter](https://github.com/dotnet/runtime/blob/master/src/libraries/Microsoft.Extensions.Logging.Console/src/SystemdConsoleFormatter.cs)
- [JsonConsoleFormatter](https://github.com/dotnet/runtime/blob/master/src/libraries/Microsoft.Extensions.Logging.Console/src/JsonConsoleFormatter.cs)

## <a name="implement-custom-color-formatting"></a>Implementación del formato de color personalizado

Con el fin de habilitar correctamente las funcionalidades de color en el formateador de registro personalizado, puede extender <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions>, ya que tiene una propiedad <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions.ColorBehavior?displayProperty=nameWithType> que puede ser útil para habilitar colores en los registros.

Cree un elemento `CustomColorOptions` derivado de `SimpleConsoleFormatterOptions`:

:::code language="csharp" source="snippets/logging/console-formatter-custom/CustomColorOptions.cs" highlight="5":::

A continuación, escriba algunos métodos de extensión en una clase `TextWriterExtensions` que permita la inserción conveniente de colores codificados con ANSI en los mensajes de registro con formato:

:::code language="csharp" source="snippets/logging/console-formatter-custom/TextWriterExtensions.cs":::

Un formateador de color personalizado que controla la aplicación de colores personalizados podría definirse de la siguiente manera:

:::code language="csharp" source="snippets/logging/console-formatter-custom/CustomColorFormatter.cs" highlight="15-18,52-65":::

Al ejecutar la aplicación, los registros mostrarán el mensaje `CustomPrefix` en color verde cuando `FormatterOptions.ColorBehavior` es `Enabled`.

> [!NOTE]
> Cuando <xref:Microsoft.Extensions.Logging.Console.LoggerColorBehavior> es `Disabled`, los mensajes de registro _no_ interpretan códigos de color ANSI insertados en los mensajes de registro. En su lugar, el resultado es un mensaje sin formato. Por ejemplo, considere lo siguiente:
>
> ```csharp
> logger.LogInformation("Random log \x1B[42mwith green background\x1B[49m message");
> ```
>
> Esto generaría la cadena textual _sin_ color.
>
> ```output
> Random log \x1B[42mwith green background\x1B[49m message
> ```

## <a name="see-also"></a>Vea también

- [Registro en .NET](logging.md)
- [Implementación de un proveedor de registro personalizado en .NET](custom-logging-provider.md)
- [Registro de alto rendimiento en .NET](high-performance-logging.md)
