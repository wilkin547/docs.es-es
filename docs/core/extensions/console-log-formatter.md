---
title: Formato de registro de la consola
description: Aprenda a usar el formato de registro de la consola disponible o a implementar el formato de registro personalizado para las aplicaciones .NET.
author: IEvangelist
ms.author: dapine
ms.date: 12/17/2020
ms.openlocfilehash: 178c66a99fac4d706156894cacffa5d902cb7901
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104872696"
---
# <a name="console-log-formatting"></a><span data-ttu-id="abad2-103">Formato de registro de la consola</span><span class="sxs-lookup"><span data-stu-id="abad2-103">Console log formatting</span></span>

<span data-ttu-id="abad2-104">En .NET 5, se ha agregado compatibilidad con el formato personalizado a los registros de la consola en el espacio de nombres `Microsoft.Extensions.Logging.Console`.</span><span class="sxs-lookup"><span data-stu-id="abad2-104">In .NET 5, support for custom formatting was added to console logs in the `Microsoft.Extensions.Logging.Console` namespace.</span></span> <span data-ttu-id="abad2-105">Hay tres opciones de formato predefinidas disponibles: [`Simple`](#simple), [`Systemd`](#systemd) y [`Json`](#json).</span><span class="sxs-lookup"><span data-stu-id="abad2-105">There are three predefined formatting options available: [`Simple`](#simple), [`Systemd`](#systemd), and [`Json`](#json).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="abad2-106">Anteriormente, la enumeración <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat> permitía seleccionar el formato de registro deseado, como inteligible, que era `Default`, o como una sola línea, lo que también se conoce como `Systemd`.</span><span class="sxs-lookup"><span data-stu-id="abad2-106">Previously, the <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat> enum allowed for selecting the desired log format, either human readable which was the `Default`, or single line which is also known as `Systemd`.</span></span> <span data-ttu-id="abad2-107">Sin embargo, **no** eran personalizables y ahora están en desuso.</span><span class="sxs-lookup"><span data-stu-id="abad2-107">However, these were **not** customizable, and are now deprecated.</span></span>

<span data-ttu-id="abad2-108">En este artículo, obtendrá información sobre los formateadores de registros de la consola.</span><span class="sxs-lookup"><span data-stu-id="abad2-108">In this article, you will learn about console log formatters.</span></span> <span data-ttu-id="abad2-109">En el código fuente de ejemplo se muestra cómo hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="abad2-109">The sample source code demonstrates how to:</span></span>

- <span data-ttu-id="abad2-110">Registrar un formateador nuevo</span><span class="sxs-lookup"><span data-stu-id="abad2-110">Register a new formatter</span></span>
- <span data-ttu-id="abad2-111">Seleccionar un formateador registrado para usarlo</span><span class="sxs-lookup"><span data-stu-id="abad2-111">Select a registered formatter to use</span></span>
  - <span data-ttu-id="abad2-112">Mediante código o [configuración](configuration.md)</span><span class="sxs-lookup"><span data-stu-id="abad2-112">Either through code, or [configuration](configuration.md)</span></span>
- <span data-ttu-id="abad2-113">Implementar un formateador personalizado</span><span class="sxs-lookup"><span data-stu-id="abad2-113">Implement a custom formatter</span></span>
  - <span data-ttu-id="abad2-114">Actualizar la configuración mediante <xref:Microsoft.Extensions.Options.IOptionsMonitor%601></span><span class="sxs-lookup"><span data-stu-id="abad2-114">Update configuration via <xref:Microsoft.Extensions.Options.IOptionsMonitor%601></span></span>
  - <span data-ttu-id="abad2-115">Habilitar el formato de color personalizado</span><span class="sxs-lookup"><span data-stu-id="abad2-115">Enable custom color formatting</span></span>

## <a name="register-formatter"></a><span data-ttu-id="abad2-116">Registro del formateador</span><span class="sxs-lookup"><span data-stu-id="abad2-116">Register formatter</span></span>

<span data-ttu-id="abad2-117">El [proveedor de registros `Console`](logging-providers.md#console) tiene varios formateadores predefinidos y expone la capacidad de crear su propio formateador personalizado.</span><span class="sxs-lookup"><span data-stu-id="abad2-117">The [`Console` logging provider](logging-providers.md#console) has several predefined formatters, and exposes the ability to author your own custom formatter.</span></span> <span data-ttu-id="abad2-118">Para registrar cualquiera de los formateadores disponibles, use el método de extensión `Add{Type}Console` correspondiente:</span><span class="sxs-lookup"><span data-stu-id="abad2-118">To register any of the available formatters, use the corresponding `Add{Type}Console` extension method:</span></span>

| <span data-ttu-id="abad2-119">Tipos disponibles</span><span class="sxs-lookup"><span data-stu-id="abad2-119">Available types</span></span> | <span data-ttu-id="abad2-120">Método para registrar el tipo</span><span class="sxs-lookup"><span data-stu-id="abad2-120">Method to register type</span></span> |
|--|--|
| <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Json?displayProperty=nameWithType> | <xref:Microsoft.Extensions.Logging.ConsoleLoggerExtensions.AddJsonConsole%2A?displayProperty=nameWithType> |
| <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Simple?displayProperty=nameWithType> | <xref:Microsoft.Extensions.Logging.ConsoleLoggerExtensions.AddSimpleConsole%2A?displayProperty=nameWithType> |
| <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Systemd?displayProperty=nameWithType> | <xref:Microsoft.Extensions.Logging.ConsoleLoggerExtensions.AddSystemdConsole%2A?displayProperty=nameWithType> |

### <a name="simple"></a><span data-ttu-id="abad2-121">Simple</span><span class="sxs-lookup"><span data-stu-id="abad2-121">Simple</span></span>

<span data-ttu-id="abad2-122">Para usar el formateador de consola `Simple`, regístrelo con `AddSimpleConsole`:</span><span class="sxs-lookup"><span data-stu-id="abad2-122">To use the `Simple` console formatter, register it with `AddSimpleConsole`:</span></span>

:::code language="csharp" source="snippets/logging/console-formatter-simple/Program.cs" highlight="11-16":::

<span data-ttu-id="abad2-123">En el código fuente de ejemplo anterior, se registró el formateador <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Simple?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="abad2-123">In the preceding sample source code, the <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Simple?displayProperty=nameWithType> formatter was registered.</span></span> <span data-ttu-id="abad2-124">Proporciona registros con la posibilidad de no solo ajustar información, como el tiempo y el nivel de registro de cada mensaje de registro, sino que también permite la inserción de color ANSI y la sangría de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="abad2-124">It provides logs with the ability to not only wrap information such as time and log level in each log message, but also allows for ANSI color embedding and indentation of messages.</span></span>

### <a name="systemd"></a><span data-ttu-id="abad2-125">Systemd</span><span class="sxs-lookup"><span data-stu-id="abad2-125">Systemd</span></span>

<span data-ttu-id="abad2-126">Registrador de la consola <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Systemd?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="abad2-126">The <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Systemd?displayProperty=nameWithType> console logger:</span></span>

- <span data-ttu-id="abad2-127">Usa el formato de nivel de registro "Syslog" y los niveles de gravedad.</span><span class="sxs-lookup"><span data-stu-id="abad2-127">Uses the "Syslog" log level format and severities</span></span>
- <span data-ttu-id="abad2-128">**No** da formato a los mensajes con colores.</span><span class="sxs-lookup"><span data-stu-id="abad2-128">Does **not** format messages with colors</span></span>
- <span data-ttu-id="abad2-129">Siempre registra mensajes en una sola línea.</span><span class="sxs-lookup"><span data-stu-id="abad2-129">Always logs messages in a single line</span></span>

<span data-ttu-id="abad2-130">Esto suele ser útil para los contenedores, que a menudo usan el registro de la consola `Systemd`.</span><span class="sxs-lookup"><span data-stu-id="abad2-130">This is commonly useful for containers, which often make use of `Systemd` console logging.</span></span> <span data-ttu-id="abad2-131">Con .NET 5, el registrador de la consola `Simple` también habilita una versión compacta que registra en una sola línea y también permite deshabilitar colores como se muestra en un ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="abad2-131">With .NET 5, the `Simple` console logger also enables a compact version that logs in a single line, and also allows for disabling colors as shown in an earlier sample.</span></span>

:::code language="csharp" source="snippets/logging/console-formatter-systemd/Program.cs" highlight="11-15":::

### <a name="json"></a><span data-ttu-id="abad2-132">Json</span><span class="sxs-lookup"><span data-stu-id="abad2-132">Json</span></span>

<span data-ttu-id="abad2-133">Para escribir registros en formato JSON, se usa el formateador de la consola `Json`.</span><span class="sxs-lookup"><span data-stu-id="abad2-133">To write logs in a JSON format, the `Json` console formatter is used.</span></span> <span data-ttu-id="abad2-134">El código fuente de ejemplo muestra cómo una aplicación ASP.NET Core podría realizar el registro.</span><span class="sxs-lookup"><span data-stu-id="abad2-134">The sample source code shows how an ASP.NET Core app might register it.</span></span> <span data-ttu-id="abad2-135">Con la plantilla `webapp`, cree una aplicación ASP.NET Core con el comando [dotnet new](../tools/dotnet-new.md):</span><span class="sxs-lookup"><span data-stu-id="abad2-135">Using the `webapp` template, create a new ASP.NET Core app with the [dotnet new](../tools/dotnet-new.md) command:</span></span>

```dotnetcli
dotnet new webapp -o Console.ExampleFormatters.Json
```

<span data-ttu-id="abad2-136">Al ejecutar la aplicación con el código de plantilla, obtiene el formato de registro predeterminado siguiente:</span><span class="sxs-lookup"><span data-stu-id="abad2-136">When running the app, using the template code, you get the default log format below:</span></span>

```
info: Microsoft.Hosting.Lifetime[0]
      Now listening on: https://localhost:5001
```

<span data-ttu-id="abad2-137">De forma predeterminada, se selecciona el formateador de registros de la consola `Simple` con la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="abad2-137">By default, the `Simple` console log formatter is selected with default configuration.</span></span> <span data-ttu-id="abad2-138">Para cambiar esto, llame a `AddJsonConsole` en *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="abad2-138">You change this by calling `AddJsonConsole` in the *Program.cs*:</span></span>

:::code language="csharp" source="snippets/logging/console-formatter-json/Program.cs" highlight="17-26":::

<span data-ttu-id="abad2-139">Vuelva a ejecutar la aplicación, con el cambio anterior; ahora, el mensaje de registro adopta el formato JSON:</span><span class="sxs-lookup"><span data-stu-id="abad2-139">Run the app again, with the above change, the log message is now formatted as JSON:</span></span>

:::code language="json" source="snippets/logging/console-formatter-json/example-output.json":::

> [!TIP]
> <span data-ttu-id="abad2-140">De forma predeterminada, el formateador de la consola `Json` registra cada mensaje en una sola línea.</span><span class="sxs-lookup"><span data-stu-id="abad2-140">The `Json` console formatter, by default, logs each message in a single line.</span></span> <span data-ttu-id="abad2-141">Para mejorar la legibilidad mientras se configura el formateador, establezca <xref:System.Text.Json.JsonWriterOptions.Indented?displayProperty=nameWithType> en `true`.</span><span class="sxs-lookup"><span data-stu-id="abad2-141">In order to make it more readable while configuring the formatter, set <xref:System.Text.Json.JsonWriterOptions.Indented?displayProperty=nameWithType> to `true`.</span></span>

## <a name="set-formatter-with-configuration"></a><span data-ttu-id="abad2-142">Definición del formateador con configuración</span><span class="sxs-lookup"><span data-stu-id="abad2-142">Set formatter with configuration</span></span>

<span data-ttu-id="abad2-143">En los ejemplos anteriores se ha mostrado cómo registrar un formateador mediante programación.</span><span class="sxs-lookup"><span data-stu-id="abad2-143">The previous samples have shown how to register a formatter programmatically.</span></span> <span data-ttu-id="abad2-144">Como alternativa, puede hacerlo con la [configuración](configuration.md).</span><span class="sxs-lookup"><span data-stu-id="abad2-144">Alternatively, this can be done with [configuration](configuration.md).</span></span> <span data-ttu-id="abad2-145">Considere el código fuente de ejemplo de aplicación web anterior; si actualiza el archivo *appsettings.json* en lugar de llamar a `ConfigureLogging` en el archivo *Program.cs*, podría obtener el mismo resultado.</span><span class="sxs-lookup"><span data-stu-id="abad2-145">Consider the previous web application sample source code, if you update the *appsettings.json* file rather than calling `ConfigureLogging` in the *Program.cs* file, you could get the same outcome.</span></span> <span data-ttu-id="abad2-146">El archivo `appsettings.json` actualizado configuraría el formateador como sigue:</span><span class="sxs-lookup"><span data-stu-id="abad2-146">The updated `appsettings.json` file would configure the formatter as follows:</span></span>

:::code language="json" source="snippets/logging/console-formatter-json/appsettings.json" highlight="14-23":::

<span data-ttu-id="abad2-147">Los dos valores de clave que se deben establecer son `"FormatterName"` y `"FormatterOptions"`.</span><span class="sxs-lookup"><span data-stu-id="abad2-147">The two key values that need to be set are `"FormatterName"` and `"FormatterOptions"`.</span></span> <span data-ttu-id="abad2-148">Si ya está registrado un formateador con el valor establecido para `"FormatterName"`, se selecciona ese formateador y se pueden configurar sus propiedades siempre que se proporcionen como una clave dentro del nodo `"FormatterOptions"`.</span><span class="sxs-lookup"><span data-stu-id="abad2-148">If a formatter with the value set for `"FormatterName"` is already registered, that formatter is selected, and its properties can be configured as long as they are provided as a key inside the `"FormatterOptions"` node.</span></span> <span data-ttu-id="abad2-149">Los nombres de formateador predefinidos se reservan en <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames>:</span><span class="sxs-lookup"><span data-stu-id="abad2-149">The predefined formatter names are reserved under <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames>:</span></span>

- <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Json?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Simple?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Systemd?displayProperty=nameWithType>

## <a name="implement-a-custom-formatter"></a><span data-ttu-id="abad2-150">Implementar un formateador personalizado</span><span class="sxs-lookup"><span data-stu-id="abad2-150">Implement a custom formatter</span></span>

<span data-ttu-id="abad2-151">Para implementar un formateador personalizado, debe hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="abad2-151">To implement a custom formatter, you need to:</span></span>

- <span data-ttu-id="abad2-152">Cree una subclase de <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatter>, que representa el formateador personalizado.</span><span class="sxs-lookup"><span data-stu-id="abad2-152">Create a subclass of <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatter>, this represents your custom formatter</span></span>
- <span data-ttu-id="abad2-153">Registre el formateador personalizado con:</span><span class="sxs-lookup"><span data-stu-id="abad2-153">Register your custom formatter with</span></span>
  - <xref:Microsoft.Extensions.Logging.ConsoleLoggerExtensions.AddConsole%2A?displayProperty=nameWithType>
  - <xref:Microsoft.Extensions.Logging.ConsoleLoggerExtensions.AddConsoleFormatter%60%602(Microsoft.Extensions.Logging.ILoggingBuilder,System.Action{%60%601})?displayProperty=nameWithType>

<span data-ttu-id="abad2-154">Cree un método de extensión para administrar esto automáticamente:</span><span class="sxs-lookup"><span data-stu-id="abad2-154">Create an extension method to handle this for you:</span></span>

:::code language="csharp" source="snippets/logging/console-formatter-custom/ConsoleLoggerExtensions.cs" highlight="11-12":::

<span data-ttu-id="abad2-155">Los elementos `CustomOptions` se definen de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="abad2-155">The `CustomOptions` are defined as follows:</span></span>

:::code language="csharp" source="snippets/logging/console-formatter-custom/CustomOptions.cs":::

<span data-ttu-id="abad2-156">En el código anterior, las opciones son una subclase de <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterOptions>.</span><span class="sxs-lookup"><span data-stu-id="abad2-156">In the preceding code, the options are a subclass of <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterOptions>.</span></span>

<span data-ttu-id="abad2-157">La API `AddConsoleFormatter` hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="abad2-157">The `AddConsoleFormatter` API:</span></span>

- <span data-ttu-id="abad2-158">Registra una subclase de `ConsoleFormatter`.</span><span class="sxs-lookup"><span data-stu-id="abad2-158">Registers a subclass of `ConsoleFormatter`</span></span>
- <span data-ttu-id="abad2-159">Controla la configuración:</span><span class="sxs-lookup"><span data-stu-id="abad2-159">Handles configuration:</span></span>
  - <span data-ttu-id="abad2-160">Usa un token de cambio para sincronizar las actualizaciones, según el [patrón de opciones](options.md), y la interfaz [IOptionsMonitor](xref:Microsoft.Extensions.Options.IOptionsMonitor%601).</span><span class="sxs-lookup"><span data-stu-id="abad2-160">Uses a change token to synchronize updates, based on the [options pattern](options.md), and the [IOptionsMonitor](xref:Microsoft.Extensions.Options.IOptionsMonitor%601) interface</span></span>

:::code language="csharp" source="snippets/logging/console-formatter-custom/Program.cs" highlight="11-12":::

<span data-ttu-id="abad2-161">Defina una subclase `CustomerFormatter` de `ConsoleFormatter`:</span><span class="sxs-lookup"><span data-stu-id="abad2-161">Define a `CustomerFormatter` subclass of `ConsoleFormatter`:</span></span>

:::code language="csharp" source="snippets/logging/console-formatter-custom/CustomFormatter.cs" highlight="24-45":::

<span data-ttu-id="abad2-162">La API `CustomFormatter.Write<TState>` anterior determina qué texto se ajusta alrededor de cada mensaje de registro.</span><span class="sxs-lookup"><span data-stu-id="abad2-162">The preceding `CustomFormatter.Write<TState>` API dictates what text gets wrapped around each log message.</span></span> <span data-ttu-id="abad2-163">Un estándar `ConsoleFormatter` debe ser capaz de ajustar en torno a los ámbitos, las marcas de tiempo y el nivel de gravedad de los registros, como mínimo.</span><span class="sxs-lookup"><span data-stu-id="abad2-163">A standard `ConsoleFormatter` should be able to wrap around scopes, time stamps, and severity level of logs at a minimum.</span></span> <span data-ttu-id="abad2-164">Además, puede codificar los colores ANSI en los mensajes de registro y proporcionar también las sangrías deseadas.</span><span class="sxs-lookup"><span data-stu-id="abad2-164">Additionally, you can encode ANSI colors in the log messages, and provide desired indentations as well.</span></span> <span data-ttu-id="abad2-165">La implementación de `CustomFormatter.Write<TState>` carece de estas funcionalidades.</span><span class="sxs-lookup"><span data-stu-id="abad2-165">The implementation of the `CustomFormatter.Write<TState>` lacks these capabilities.</span></span>

<span data-ttu-id="abad2-166">Para obtener información sobre cómo personalizar aún más el formato, vea las implementaciones existentes en el espacio de nombres `Microsoft.Extensions.Logging.Console`:</span><span class="sxs-lookup"><span data-stu-id="abad2-166">For inspiration on further customizing formatting, see the existing implementations in the `Microsoft.Extensions.Logging.Console` namespace:</span></span>

- <span data-ttu-id="abad2-167">[SimpleConsoleFormatter](https://github.com/dotnet/runtime/blob/main/src/libraries/Microsoft.Extensions.Logging.Console/src/SimpleConsoleFormatter.cs)</span><span class="sxs-lookup"><span data-stu-id="abad2-167">[SimpleConsoleFormatter](https://github.com/dotnet/runtime/blob/main/src/libraries/Microsoft.Extensions.Logging.Console/src/SimpleConsoleFormatter.cs).</span></span>
- [<span data-ttu-id="abad2-168">SystemdConsoleFormatter</span><span class="sxs-lookup"><span data-stu-id="abad2-168">SystemdConsoleFormatter</span></span>](https://github.com/dotnet/runtime/blob/main/src/libraries/Microsoft.Extensions.Logging.Console/src/SystemdConsoleFormatter.cs)
- [<span data-ttu-id="abad2-169">JsonConsoleFormatter</span><span class="sxs-lookup"><span data-stu-id="abad2-169">JsonConsoleFormatter</span></span>](https://github.com/dotnet/runtime/blob/main/src/libraries/Microsoft.Extensions.Logging.Console/src/JsonConsoleFormatter.cs)

## <a name="implement-custom-color-formatting"></a><span data-ttu-id="abad2-170">Implementación del formato de color personalizado</span><span class="sxs-lookup"><span data-stu-id="abad2-170">Implement custom color formatting</span></span>

<span data-ttu-id="abad2-171">Con el fin de habilitar correctamente las funcionalidades de color en el formateador de registro personalizado, puede extender <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions>, ya que tiene una propiedad <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions.ColorBehavior?displayProperty=nameWithType> que puede ser útil para habilitar colores en los registros.</span><span class="sxs-lookup"><span data-stu-id="abad2-171">In order to properly enable color capabilities in your custom logging formatter, you can extend the <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions> as it has a <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions.ColorBehavior?displayProperty=nameWithType> property that can be useful for enabling colors in logs.</span></span>

<span data-ttu-id="abad2-172">Cree un elemento `CustomColorOptions` derivado de `SimpleConsoleFormatterOptions`:</span><span class="sxs-lookup"><span data-stu-id="abad2-172">Create a `CustomColorOptions` that derives from `SimpleConsoleFormatterOptions`:</span></span>

:::code language="csharp" source="snippets/logging/console-formatter-custom/CustomColorOptions.cs" highlight="5":::

<span data-ttu-id="abad2-173">A continuación, escriba algunos métodos de extensión en una clase `TextWriterExtensions` que permita la inserción conveniente de colores codificados con ANSI en los mensajes de registro con formato:</span><span class="sxs-lookup"><span data-stu-id="abad2-173">Next, write some extension methods in a `TextWriterExtensions` class that allow for conveniently embedding ANSI coded colors within formatted log messages:</span></span>

:::code language="csharp" source="snippets/logging/console-formatter-custom/TextWriterExtensions.cs":::

<span data-ttu-id="abad2-174">Un formateador de color personalizado que controla la aplicación de colores personalizados podría definirse de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="abad2-174">A custom color formatter that handles applying custom colors could be defined as follows:</span></span>

:::code language="csharp" source="snippets/logging/console-formatter-custom/CustomColorFormatter.cs" highlight="15-18,52-65":::

<span data-ttu-id="abad2-175">Al ejecutar la aplicación, los registros mostrarán el mensaje `CustomPrefix` en color verde cuando `FormatterOptions.ColorBehavior` es `Enabled`.</span><span class="sxs-lookup"><span data-stu-id="abad2-175">When you run the application, the logs will show the `CustomPrefix` message in the color green when `FormatterOptions.ColorBehavior` is `Enabled`.</span></span>

> [!NOTE]
> <span data-ttu-id="abad2-176">Cuando <xref:Microsoft.Extensions.Logging.Console.LoggerColorBehavior> es `Disabled`, los mensajes de registro _no_ interpretan códigos de color ANSI insertados en los mensajes de registro.</span><span class="sxs-lookup"><span data-stu-id="abad2-176">When <xref:Microsoft.Extensions.Logging.Console.LoggerColorBehavior> is `Disabled`, log messages do _not_ interpret embedded ANSI color codes within log messages.</span></span> <span data-ttu-id="abad2-177">En su lugar, el resultado es un mensaje sin formato.</span><span class="sxs-lookup"><span data-stu-id="abad2-177">Instead, they output the raw message.</span></span> <span data-ttu-id="abad2-178">Por ejemplo, considere lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="abad2-178">For example, consider the following:</span></span>
>
> ```csharp
> logger.LogInformation("Random log \x1B[42mwith green background\x1B[49m message");
> ```
>
> <span data-ttu-id="abad2-179">Esto generaría la cadena textual _sin_ color.</span><span class="sxs-lookup"><span data-stu-id="abad2-179">This would output the verbatim string, and it is _not_ colorized.</span></span>
>
> ```output
> Random log \x1B[42mwith green background\x1B[49m message
> ```

## <a name="see-also"></a><span data-ttu-id="abad2-180">Vea también</span><span class="sxs-lookup"><span data-stu-id="abad2-180">See also</span></span>

- [<span data-ttu-id="abad2-181">Registro en .NET</span><span class="sxs-lookup"><span data-stu-id="abad2-181">Logging in .NET</span></span>](logging.md)
- [<span data-ttu-id="abad2-182">Implementación de un proveedor de registro personalizado en .NET</span><span class="sxs-lookup"><span data-stu-id="abad2-182">Implement a custom logging provider in .NET</span></span>](custom-logging-provider.md)
- [<span data-ttu-id="abad2-183">Registro de alto rendimiento en .NET</span><span class="sxs-lookup"><span data-stu-id="abad2-183">High-performance logging in .NET</span></span>](high-performance-logging.md)
