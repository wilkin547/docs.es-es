---
title: Registro en .NET
author: IEvangelist
description: Obtenga información sobre cómo usar la plataforma de registro proporcionada por el paquete NuGet Microsoft.Extensions.Logging.
ms.author: dapine
ms.date: 02/19/2021
ms.openlocfilehash: 834331b9e103138012bbe91586d0d5a7c08654ce
ms.sourcegitcommit: bdbf6472de867a0a11aaa5b9384a2506c24f27d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2021
ms.locfileid: "102402215"
---
# <a name="logging-in-net"></a><span data-ttu-id="5f3ff-103">Registro en .NET</span><span class="sxs-lookup"><span data-stu-id="5f3ff-103">Logging in .NET</span></span>

<span data-ttu-id="5f3ff-104">.NET es compatible con una API de registro que funciona con una gran variedad de proveedores de registro integrados y de terceros.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-104">.NET supports a logging API that works with a variety of built-in and third-party logging providers.</span></span> <span data-ttu-id="5f3ff-105">En este artículo se muestra cómo usar las API de registro con proveedores integrados.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-105">This article shows how to use the logging API with built-in providers.</span></span> <span data-ttu-id="5f3ff-106">La mayoría de los ejemplos de código que se muestran en este artículo se aplican a cualquier aplicación .NET que use el [host genérico](generic-host.md).</span><span class="sxs-lookup"><span data-stu-id="5f3ff-106">Most of the code examples shown in this article apply to any .NET app that uses the [Generic Host](generic-host.md).</span></span> <span data-ttu-id="5f3ff-107">En el caso de las aplicaciones que no usan el host genérico, vea [Aplicación de consola que no es de host](#non-host-console-app).</span><span class="sxs-lookup"><span data-stu-id="5f3ff-107">For apps that don't use the Generic Host, see [Non-host console app](#non-host-console-app).</span></span>

## <a name="create-logs"></a><span data-ttu-id="5f3ff-108">Creación de registros</span><span class="sxs-lookup"><span data-stu-id="5f3ff-108">Create logs</span></span>

<span data-ttu-id="5f3ff-109">Para crear registros, use un objeto <xref:Microsoft.Extensions.Logging.ILogger%601> desde la [inserción de dependencias (DI)](dependency-injection.md).</span><span class="sxs-lookup"><span data-stu-id="5f3ff-109">To create logs, use an <xref:Microsoft.Extensions.Logging.ILogger%601> object from [dependency injection (DI)](dependency-injection.md).</span></span>

<span data-ttu-id="5f3ff-110">En el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5f3ff-110">The following example:</span></span>

- <span data-ttu-id="5f3ff-111">Crea un registrador, `ILogger<Worker>`, que utiliza una *categoría* de registro del nombre completo del tipo `Worker`.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-111">Creates a logger, `ILogger<Worker>`, which uses a log *category* of the fully qualified name of the type `Worker`.</span></span> <span data-ttu-id="5f3ff-112">La categoría de registro es una cadena que está asociada con cada registro.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-112">The log category is a string that is associated with each log.</span></span>
- <span data-ttu-id="5f3ff-113">Llama a <xref:Microsoft.Extensions.Logging.LoggerExtensions.LogInformation%2A> para realizar el registro en el nivel de `Information`.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-113">Calls <xref:Microsoft.Extensions.Logging.LoggerExtensions.LogInformation%2A> to log at the `Information` level.</span></span> <span data-ttu-id="5f3ff-114">El *nivel* de registro indica la gravedad del evento registrado.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-114">The Log *level* indicates the severity of the logged event.</span></span>

:::code language="csharp" source="snippets/configuration/worker-service/Worker.cs" range="9-24" highlight="12":::

<span data-ttu-id="5f3ff-115">Los [niveles](#log-level) y las [categorías](#log-category) se explican detalladamente más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-115">[Levels](#log-level) and [categories](#log-category) are explained in more detail later in this article.</span></span>

## <a name="configure-logging"></a><span data-ttu-id="5f3ff-116">registro</span><span class="sxs-lookup"><span data-stu-id="5f3ff-116">Configure logging</span></span>

<span data-ttu-id="5f3ff-117">La configuración de registros suele proporcionarla la sección `Logging` de los archivos *appsettings*.`{Environment}` *.json*.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-117">Logging configuration is commonly provided by the `Logging` section of *appsettings*.`{Environment}`*.json* files.</span></span> <span data-ttu-id="5f3ff-118">El siguiente archivo *appsettings.Development.json* se genera mediante las plantillas de servicio de trabajo de .NET:</span><span class="sxs-lookup"><span data-stu-id="5f3ff-118">The following *appsettings.Development.json* file is generated by the .NET Worker service templates:</span></span>

:::code language="json" source="snippets/configuration/worker-service/appsettings.Development.json":::

<span data-ttu-id="5f3ff-119">En el código JSON anterior:</span><span class="sxs-lookup"><span data-stu-id="5f3ff-119">In the preceding JSON:</span></span>

- <span data-ttu-id="5f3ff-120">Se especifican las categorías `"Default"`, `"Microsoft"` y `"Microsoft.Hosting.Lifetime"`.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-120">The `"Default"`, `"Microsoft"`, and `"Microsoft.Hosting.Lifetime"` categories are specified.</span></span>
- <span data-ttu-id="5f3ff-121">La categoría `"Microsoft"` se aplica a todas las categorías que comienzan por `"Microsoft"`.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-121">The `"Microsoft"` category applies to all categories that start with `"Microsoft"`.</span></span>
- <span data-ttu-id="5f3ff-122">La categoría `"Microsoft"` registra en el nivel de registro `Warning` y superiores.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-122">The `"Microsoft"` category logs at log level `Warning` and higher.</span></span>
- <span data-ttu-id="5f3ff-123">La categoría `"Microsoft.Hosting.Lifetime"` es más específica que la categoría `"Microsoft"`, por lo que la categoría `"Microsoft.Hosting.Lifetime"` registra en el nivel de registro "Information" y superiores.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-123">The `"Microsoft.Hosting.Lifetime"` category is more specific than the `"Microsoft"` category, so the `"Microsoft.Hosting.Lifetime"` category logs at log level "Information" and higher.</span></span>
- <span data-ttu-id="5f3ff-124">No se especifica un proveedor de registro específico, por lo que `LogLevel` se aplica a todos los proveedores de registro habilitados, excepto [Windows EventLog](logging-providers.md#windows-eventlog).</span><span class="sxs-lookup"><span data-stu-id="5f3ff-124">A specific log provider is not specified, so `LogLevel` applies to all the enabled logging providers except for the [Windows EventLog](logging-providers.md#windows-eventlog).</span></span>

<span data-ttu-id="5f3ff-125">La propiedad `Logging` puede tener <xref:Microsoft.Extensions.Logging.LogLevel> y registrar propiedades del proveedor de registro.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-125">The `Logging` property can have <xref:Microsoft.Extensions.Logging.LogLevel> and log provider properties.</span></span> <span data-ttu-id="5f3ff-126">`LogLevel` especifica el [nivel](#log-level) mínimo que se va a registrar para las categorías seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-126">The `LogLevel` specifies the minimum [level](#log-level) to log for selected categories.</span></span> <span data-ttu-id="5f3ff-127">En el código JSON anterior, se especifican los niveles de registro `Information` y `Warning`.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-127">In the preceding JSON, `Information` and `Warning` log levels are specified.</span></span> <span data-ttu-id="5f3ff-128">`LogLevel` indica la gravedad del registro y los valores están entre 0 y 6:</span><span class="sxs-lookup"><span data-stu-id="5f3ff-128">`LogLevel` indicates the severity of the log and ranges from 0 to 6:</span></span>

<span data-ttu-id="5f3ff-129">`Trace` = 0, `Debug` = 1, `Information` = 2, `Warning` = 3, `Error` = 4, `Critical` = 5 y `None` = 6.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-129">`Trace` = 0, `Debug` = 1, `Information` = 2, `Warning` = 3, `Error` = 4, `Critical` = 5, and `None` = 6.</span></span>

<span data-ttu-id="5f3ff-130">Cuando se especifica `LogLevel`, el registro está habilitado para los mensajes tanto en el nivel especificado como en los superiores.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-130">When a `LogLevel` is specified, logging is enabled for messages at the specified level and higher.</span></span> <span data-ttu-id="5f3ff-131">En el código JSON anterior, se registra la categoría `Default` para `Information` y los niveles posteriores.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-131">In the preceding JSON, the `Default` category is logged for `Information` and higher.</span></span> <span data-ttu-id="5f3ff-132">Por ejemplo, se registran los mensajes `Information`, `Warning`, `Error` y `Critical`.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-132">For example, `Information`, `Warning`, `Error`, and `Critical` messages are logged.</span></span> <span data-ttu-id="5f3ff-133">Si no se especifica `LogLevel`, el nivel predeterminado del registro es `Information`.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-133">If no `LogLevel` is specified, logging defaults to the `Information` level.</span></span> <span data-ttu-id="5f3ff-134">Para obtener más información, consulte [Niveles de registro](#log-level).</span><span class="sxs-lookup"><span data-stu-id="5f3ff-134">For more information, see [Log levels](#log-level).</span></span>

<span data-ttu-id="5f3ff-135">Una propiedad de proveedor puede especificar una propiedad de `LogLevel`.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-135">A provider property can specify a `LogLevel` property.</span></span> <span data-ttu-id="5f3ff-136">`LogLevel` en un proveedor especifica los niveles que se van a registrar para ese proveedor, e invalida la configuración de registro que no es de proveedor.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-136">`LogLevel` under a provider specifies levels to log for that provider, and overrides the non-provider log settings.</span></span> <span data-ttu-id="5f3ff-137">Fíjese en el siguiente archivo *appsettings.json*:</span><span class="sxs-lookup"><span data-stu-id="5f3ff-137">Consider the following *appsettings.json* file:</span></span>

:::code language="json" source="snippets/configuration/worker-service/appsettings.Staging.json":::

<span data-ttu-id="5f3ff-138">La configuración de `Logging.{ProviderName}.LogLevel` invalida la configuración de `Logging.LogLevel`.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-138">Settings in `Logging.{ProviderName}.LogLevel` override settings in `Logging.LogLevel`.</span></span> <span data-ttu-id="5f3ff-139">En el código JSON anterior, el nivel de registro predeterminado del proveedor `Debug` se establece en `Information`:</span><span class="sxs-lookup"><span data-stu-id="5f3ff-139">In the preceding JSON, the `Debug` provider's default log level is set to `Information`:</span></span>

`Logging:Debug:LogLevel:Default:Information`

<span data-ttu-id="5f3ff-140">La configuración anterior especifica el nivel de registro `Information` para cada categoría de `Logging:Debug:`, excepto `Microsoft.Hosting`.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-140">The preceding setting specifies the `Information` log level for every `Logging:Debug:` category except `Microsoft.Hosting`.</span></span> <span data-ttu-id="5f3ff-141">Cuando se muestra una categoría específica, esa categoría invalida la categoría predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-141">When a specific category is listed, the specific category overrides the default category.</span></span> <span data-ttu-id="5f3ff-142">En el JSON anterior, las categorías de `Logging:Debug:LogLevel` `"Microsoft.Hosting"` y `"Default"` invalidan la configuración de `Logging:LogLevel`</span><span class="sxs-lookup"><span data-stu-id="5f3ff-142">In the preceding JSON, the `Logging:Debug:LogLevel` categories `"Microsoft.Hosting"` and `"Default"` override the settings in `Logging:LogLevel`</span></span>

<span data-ttu-id="5f3ff-143">Se puede especificar el nivel de registro mínimo para:</span><span class="sxs-lookup"><span data-stu-id="5f3ff-143">The minimum log level can be specified for any of:</span></span>

- <span data-ttu-id="5f3ff-144">Proveedores específicos:  Por ejemplo, `Logging:EventSource:LogLevel:Default:Information`.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-144">Specific providers:  For example, `Logging:EventSource:LogLevel:Default:Information`</span></span>
- <span data-ttu-id="5f3ff-145">Categorías específicas: Por ejemplo, `Logging:LogLevel:Microsoft:Warning`.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-145">Specific categories: For example, `Logging:LogLevel:Microsoft:Warning`</span></span>
- <span data-ttu-id="5f3ff-146">Todos los proveedores y todas las categorías: `Logging:LogLevel:Default:Warning`</span><span class="sxs-lookup"><span data-stu-id="5f3ff-146">All providers and all categories: `Logging:LogLevel:Default:Warning`</span></span>

<span data-ttu-id="5f3ff-147">Los registros situados por debajo del nivel mínimo:</span><span class="sxs-lookup"><span data-stu-id="5f3ff-147">Any logs below the minimum level are ***not***:</span></span>

- <span data-ttu-id="5f3ff-148">no se pasan proveedor;</span><span class="sxs-lookup"><span data-stu-id="5f3ff-148">Passed to the provider.</span></span>
- <span data-ttu-id="5f3ff-149">no se registran ni se muestran.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-149">Logged or displayed.</span></span>

<span data-ttu-id="5f3ff-150">Para suprimir todos los registros, especifique [LogLevel.None](xref:Microsoft.Extensions.Logging.LogLevel).</span><span class="sxs-lookup"><span data-stu-id="5f3ff-150">To suppress all logs, specify [LogLevel.None](xref:Microsoft.Extensions.Logging.LogLevel).</span></span> <span data-ttu-id="5f3ff-151">`LogLevel.None` tiene un valor de 6, que es mayor que `LogLevel.Critical` (5).</span><span class="sxs-lookup"><span data-stu-id="5f3ff-151">`LogLevel.None` has a value of 6, which is higher than `LogLevel.Critical` (5).</span></span>

<span data-ttu-id="5f3ff-152">Si un proveedor admite [ámbitos de registro](#log-scopes), `IncludeScopes` indica si están habilitados.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-152">If a provider supports [log scopes](#log-scopes), `IncludeScopes` indicates whether they're enabled.</span></span> <span data-ttu-id="5f3ff-153">Para obtener más información, consulte [Ámbitos de registro](#log-scopes).</span><span class="sxs-lookup"><span data-stu-id="5f3ff-153">For more information, see [log scopes](#log-scopes)</span></span>

<span data-ttu-id="5f3ff-154">El siguiente archivo *appsettings.json* contiene la configuración de todos los proveedores integrados:</span><span class="sxs-lookup"><span data-stu-id="5f3ff-154">The following *appsettings.json* file contains settings for all of the built-in providers:</span></span>

:::code language="json" source="snippets/configuration/worker-service/appsettings.Production.json":::

<span data-ttu-id="5f3ff-155">En el ejemplo anterior:</span><span class="sxs-lookup"><span data-stu-id="5f3ff-155">In the preceding sample:</span></span>

- <span data-ttu-id="5f3ff-156">Las categorías y los niveles no son valores sugeridos.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-156">The categories and levels are not suggested values.</span></span> <span data-ttu-id="5f3ff-157">El objetivo del ejemplo es mostrar todos los proveedores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-157">The sample is provided to show all the default providers.</span></span>
- <span data-ttu-id="5f3ff-158">La configuración de `Logging.{ProviderName}.LogLevel` invalida la configuración de `Logging.LogLevel`.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-158">Settings in `Logging.{ProviderName}.LogLevel` override settings in `Logging.LogLevel`.</span></span> <span data-ttu-id="5f3ff-159">Por ejemplo, el nivel de `Debug.LogLevel.Default` invalida el nivel de `LogLevel.Default`.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-159">For example, the level in `Debug.LogLevel.Default` overrides the level in `LogLevel.Default`.</span></span>
- <span data-ttu-id="5f3ff-160">Se usa cada *alias* de proveedor.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-160">Each provider's *alias* is used.</span></span> <span data-ttu-id="5f3ff-161">Cada proveedor define un *alias* que se puede utilizar en la configuración en lugar del nombre de tipo completo.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-161">Each provider defines an *alias* that can be used in configuration in place of the fully qualified type name.</span></span> <span data-ttu-id="5f3ff-162">Los alias de proveedores integrados son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="5f3ff-162">The built-in providers' aliases are:</span></span>
  - <span data-ttu-id="5f3ff-163">Consola</span><span class="sxs-lookup"><span data-stu-id="5f3ff-163">Console</span></span>
  - <span data-ttu-id="5f3ff-164">Depuración</span><span class="sxs-lookup"><span data-stu-id="5f3ff-164">Debug</span></span>
  - <span data-ttu-id="5f3ff-165">EventSource</span><span class="sxs-lookup"><span data-stu-id="5f3ff-165">EventSource</span></span>
  - <span data-ttu-id="5f3ff-166">EventLog</span><span class="sxs-lookup"><span data-stu-id="5f3ff-166">EventLog</span></span>
  - <span data-ttu-id="5f3ff-167">AzureAppServicesFile</span><span class="sxs-lookup"><span data-stu-id="5f3ff-167">AzureAppServicesFile</span></span>
  - <span data-ttu-id="5f3ff-168">AzureAppServicesBlob</span><span class="sxs-lookup"><span data-stu-id="5f3ff-168">AzureAppServicesBlob</span></span>
  - <span data-ttu-id="5f3ff-169">ApplicationInsights</span><span class="sxs-lookup"><span data-stu-id="5f3ff-169">ApplicationInsights</span></span>

### <a name="set-log-level-by-command-line-environment-variables-and-other-configuration"></a><span data-ttu-id="5f3ff-170">Establecimiento del nivel de registro mediante la línea de comandos, las variables de entorno y otra configuración</span><span class="sxs-lookup"><span data-stu-id="5f3ff-170">Set log level by command line, environment variables, and other configuration</span></span>

<span data-ttu-id="5f3ff-171">El nivel de registro se puede establecer con cualquiera de los [proveedores de configuración](configuration-providers.md).</span><span class="sxs-lookup"><span data-stu-id="5f3ff-171">Log level can be set by any of the [configuration providers](configuration-providers.md).</span></span> <span data-ttu-id="5f3ff-172">Por ejemplo, puede crear una variable de entorno persistente denominada `Logging:LogLevel:Microsoft` con un valor de `Information`.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-172">For example, you can create a persisted environment variable named `Logging:LogLevel:Microsoft` with a value of `Information`.</span></span>

## <a name="command-line"></a>[<span data-ttu-id="5f3ff-173">Línea de comandos</span><span class="sxs-lookup"><span data-stu-id="5f3ff-173">Command Line</span></span>](#tab/command-line)

<span data-ttu-id="5f3ff-174">Cree y asigne una variable de entorno persistente según el valor de nivel de registro.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-174">Create and assign persisted environment variable, given the log level value.</span></span>

```CMD
:: Assigns the env var to the value
setx "Logging__LogLevel__Microsoft" "Information" /M
```

<span data-ttu-id="5f3ff-175">En una *nueva* instancia del **símbolo del sistema**, lea la variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-175">In a *new* instance of the **Command Prompt**, read the environment variable.</span></span>

```CMD
:: Prints the env var value
echo %Logging__LogLevel__Microsoft%
```

## <a name="powershell"></a>[<span data-ttu-id="5f3ff-176">PowerShell</span><span class="sxs-lookup"><span data-stu-id="5f3ff-176">PowerShell</span></span>](#tab/powershell)

<span data-ttu-id="5f3ff-177">Cree y asigne una variable de entorno persistente según el valor de nivel de registro.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-177">Create and assign persisted environment variable, given the log level value.</span></span>

```powershell
# Assigns the env var to the value
[System.Environment]::SetEnvironmentVariable(
    "Logging__LogLevel__Microsoft", "Information", "Machine")
```

<span data-ttu-id="5f3ff-178">En una *nueva* instancia de **PowerShell**, lea la variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-178">In a *new* instance of the **PowerShell**, read the environment variable.</span></span>

```powershell
# Prints the env var value
[System.Environment]::GetEnvironmentVariable(
    "Logging__LogLevel__Microsoft", "Machine")
```

## <a name="bash"></a>[<span data-ttu-id="5f3ff-179">Bash</span><span class="sxs-lookup"><span data-stu-id="5f3ff-179">Bash</span></span>](#tab/bash)

<span data-ttu-id="5f3ff-180">Cree y asigne una variable de entorno persistente según el valor de nivel de registro.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-180">Create and assign persisted environment variable, given the log level value.</span></span>

```Bash
# Assigns the env var to the value, persists it across sessions
echo export Logging__LogLevel__Microsoft="Information" >> ~/.bashrc && source ~/.bashrc
```

<span data-ttu-id="5f3ff-181">Para leer la variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-181">To read the environment variable.</span></span>

```Bash
# Prints the env var value
echo $Logging__LogLevel__Microsoft

# Or use printenv:
# printenv Logging__LogLevel__Microsoft
```

> [!NOTE]
> <span data-ttu-id="5f3ff-182">Al configurar variables de entorno con nombres que contienen `.` (puntos), considere la posibilidad de "Exportar una variable con un punto (.) en ella" en **Stack Exchange** y su [respuesta aceptada](https://unix.stackexchange.com/a/93533) correspondiente.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-182">When configuring environment variables with names that contain `.` (periods), consider the "Exporting a variable with a dot (.) in it" question on **Stack Exchange** and its corresponding [accepted answer](https://unix.stackexchange.com/a/93533).</span></span>

---

<span data-ttu-id="5f3ff-183">La configuración del entorno anterior se conserva en el entorno.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-183">The preceding environment setting is persisted in the environment.</span></span> <span data-ttu-id="5f3ff-184">Para probar la configuración cuando se usa una aplicación creada con las plantillas de servicio de trabajo de .NET, use el comando `dotnet run` en el directorio del proyecto después de asignar la variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-184">To test the settings when using an app created with the .NET Worker service templates, use the `dotnet run` command in the project directory after the environment variable is assigned.</span></span>

```dotnetcli
dotnet run
```

> [!TIP]
> <span data-ttu-id="5f3ff-185">Después de establecer una variable de entorno, reinicie su entorno de desarrollo integrado (IDE) para asegurarse de que las variables de entorno recién agregadas están disponibles.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-185">After setting an environment variable, restart your integrated development environment (IDE) to ensure that newly added environment variables are available.</span></span>

<span data-ttu-id="5f3ff-186">En [Azure App Service](https://azure.microsoft.com/services/app-service/), seleccione **Nueva configuración de la aplicación** en la página **Configuración > Configuración**.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-186">On [Azure App Service](https://azure.microsoft.com/services/app-service/), select **New application setting** on the **Settings > Configuration** page.</span></span> <span data-ttu-id="5f3ff-187">Los ajustes de configuración de Azure App Service:</span><span class="sxs-lookup"><span data-stu-id="5f3ff-187">Azure App Service application settings are:</span></span>

- <span data-ttu-id="5f3ff-188">Se cifran en reposo y se transmiten a través de un canal cifrado.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-188">Encrypted at rest and transmitted over an encrypted channel.</span></span>
- <span data-ttu-id="5f3ff-189">Se exponen como variables de entorno.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-189">Exposed as environment variables.</span></span>

<span data-ttu-id="5f3ff-190">Para más información sobre cómo establecer los valores de configuración de .NET mediante variables de entorno, vea [Variables de entorno](configuration-providers.md#environment-variable-configuration-provider).</span><span class="sxs-lookup"><span data-stu-id="5f3ff-190">For more information on setting .NET configuration values using environment variables, see [environment variables](configuration-providers.md#environment-variable-configuration-provider).</span></span>

## <a name="how-filtering-rules-are-applied"></a><span data-ttu-id="5f3ff-191">Cómo se aplican las reglas de filtro</span><span class="sxs-lookup"><span data-stu-id="5f3ff-191">How filtering rules are applied</span></span>

<span data-ttu-id="5f3ff-192">Cuando se crea un objeto <xref:Microsoft.Extensions.Logging.ILogger%601>, el objeto <xref:Microsoft.Extensions.Logging.ILoggerFactory> selecciona una sola regla por proveedor para aplicar a ese registrador.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-192">When an <xref:Microsoft.Extensions.Logging.ILogger%601> object is created, the <xref:Microsoft.Extensions.Logging.ILoggerFactory> object selects a single rule per provider to apply to that logger.</span></span> <span data-ttu-id="5f3ff-193">Todos los mensajes escritos por una instancia `ILogger` se filtran según las reglas seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-193">All messages written by an `ILogger` instance are filtered based on the selected rules.</span></span> <span data-ttu-id="5f3ff-194">De las reglas disponibles, se selecciona la más específica para cada par de categoría y proveedor.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-194">The most specific rule for each provider and category pair is selected from the available rules.</span></span>

<span data-ttu-id="5f3ff-195">Cuando se crea un `ILogger` para una categoría determinada, se usa el algoritmo siguiente para cada proveedor:</span><span class="sxs-lookup"><span data-stu-id="5f3ff-195">The following algorithm is used for each provider when an `ILogger` is created for a given category:</span></span>

- <span data-ttu-id="5f3ff-196">Se seleccionan todas las reglas que coinciden con el proveedor o su alias.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-196">Select all rules that match the provider or its alias.</span></span> <span data-ttu-id="5f3ff-197">Si no se encuentra ninguna coincidencia, se seleccionan todas las reglas con un proveedor vacío.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-197">If no match is found, select all rules with an empty provider.</span></span>
- <span data-ttu-id="5f3ff-198">Del resultado del paso anterior, se seleccionan las reglas con el prefijo de categoría coincidente más largo.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-198">From the result of the preceding step, select rules with longest matching category prefix.</span></span> <span data-ttu-id="5f3ff-199">Si no se encuentra ninguna coincidencia, se seleccionan todas las reglas que no especifican una categoría.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-199">If no match is found, select all rules that don't specify a category.</span></span>
- <span data-ttu-id="5f3ff-200">Si se seleccionan varias reglas, se toma la **última**.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-200">If multiple rules are selected, take the **last** one.</span></span>
- <span data-ttu-id="5f3ff-201">Si no hay ninguna regla seleccionada, use <xref:Microsoft.Extensions.Logging.LoggingBuilderExtensions.SetMinimumLevel(Microsoft.Extensions.Logging.ILoggingBuilder,Microsoft.Extensions.Logging.LogLevel)?displayProperty=nameWithType> para especificar el nivel de registro mínimo.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-201">If no rules are selected, use <xref:Microsoft.Extensions.Logging.LoggingBuilderExtensions.SetMinimumLevel(Microsoft.Extensions.Logging.ILoggingBuilder,Microsoft.Extensions.Logging.LogLevel)?displayProperty=nameWithType> to specify the minimum logging level.</span></span>

## <a name="log-category"></a><span data-ttu-id="5f3ff-202">Categoría de registro</span><span class="sxs-lookup"><span data-stu-id="5f3ff-202">Log category</span></span>

<span data-ttu-id="5f3ff-203">Cuando se crea un objeto `ILogger`, se especifica una *categoría*.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-203">When an `ILogger` object is created, a *category* is specified.</span></span> <span data-ttu-id="5f3ff-204">Esa categoría se incluye con cada mensaje de registro creado por esa instancia de `ILogger`.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-204">That category is included with each log message created by that instance of `ILogger`.</span></span> <span data-ttu-id="5f3ff-205">La cadena de categoría es arbitraria, pero la convención es usar el nombre de clase.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-205">The category string is arbitrary, but the convention is to use the class name.</span></span> <span data-ttu-id="5f3ff-206">Por ejemplo, en una aplicación con un servicio definido como el siguiente objeto, la categoría podría ser `"Example.DefaultService"`:</span><span class="sxs-lookup"><span data-stu-id="5f3ff-206">For example, in an application with a service define like the following object, the category might be `"Example.DefaultService"`:</span></span>

```csharp
namespace Example
{
    public class DefaultService : IService
    {
        private readonly ILogger<DefaultService> _logger;

        public DefaultService(ILogger<DefaultService> logger) =>
            _logger = logger;

        // ...
    }
}
```

<span data-ttu-id="5f3ff-207">Para especificar explícitamente la categoría, llame a <xref:Microsoft.Extensions.Logging.LoggerFactory.CreateLogger%2A?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="5f3ff-207">To explicitly specify the category, call <xref:Microsoft.Extensions.Logging.LoggerFactory.CreateLogger%2A?displayProperty=nameWithType>:</span></span>

```csharp
namespace Example
{
    public class DefaultService : IService
    {
        private readonly ILogger _logger;

        public DefaultService(ILoggerFactory loggerFactory) =>
            _logger = loggerFactory.CreateLogger("CustomCategory");

        // ...
    }
}
```

<span data-ttu-id="5f3ff-208">La llamada a `CreateLogger` con un nombre fijo puede ser útil cuando se usa en varias clases o tipos, por lo que los eventos se pueden organizar por categoría.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-208">Calling `CreateLogger` with a fixed name can be useful when used in multiple classes/types so the events can be organized by category.</span></span>

<span data-ttu-id="5f3ff-209">`ILogger<T>` es equivale a llamar a `CreateLogger` con el nombre de tipo completo de `T`.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-209">`ILogger<T>` is equivalent to calling `CreateLogger` with the fully qualified type name of `T`.</span></span>

## <a name="log-level"></a><span data-ttu-id="5f3ff-210">Nivel de registro</span><span class="sxs-lookup"><span data-stu-id="5f3ff-210">Log level</span></span>

<span data-ttu-id="5f3ff-211">En la tabla siguiente se enumeran los valores de <xref:Microsoft.Extensions.Logging.LogLevel>, el método de extensión `Log{LogLevel}` oportuno y el uso sugerido:</span><span class="sxs-lookup"><span data-stu-id="5f3ff-211">The following table lists the <xref:Microsoft.Extensions.Logging.LogLevel> values, the convenience `Log{LogLevel}` extension method, and the suggested usage:</span></span>

| <span data-ttu-id="5f3ff-212">LogLevel</span><span class="sxs-lookup"><span data-stu-id="5f3ff-212">LogLevel</span></span> | <span data-ttu-id="5f3ff-213">Valor</span><span class="sxs-lookup"><span data-stu-id="5f3ff-213">Value</span></span> | <span data-ttu-id="5f3ff-214">Método</span><span class="sxs-lookup"><span data-stu-id="5f3ff-214">Method</span></span> | <span data-ttu-id="5f3ff-215">Descripción</span><span class="sxs-lookup"><span data-stu-id="5f3ff-215">Description</span></span> |
|--|--|--|--|
| [<span data-ttu-id="5f3ff-216">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="5f3ff-216">Trace</span></span>](xref:Microsoft.Extensions.Logging.LogLevel) | <span data-ttu-id="5f3ff-217">0</span><span class="sxs-lookup"><span data-stu-id="5f3ff-217">0</span></span> | <xref:Microsoft.Extensions.Logging.LoggerExtensions.LogTrace%2A> | <span data-ttu-id="5f3ff-218">Contienen los mensajes más detallados.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-218">Contain the most detailed messages.</span></span> <span data-ttu-id="5f3ff-219">Estos mensajes pueden contener datos confidenciales de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-219">These messages may contain sensitive app data.</span></span> <span data-ttu-id="5f3ff-220">Están deshabilitados de forma predeterminada y ***no*** se deben habilitar en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-220">These messages are disabled by default and should ***not*** be enabled in production.</span></span> |
| [<span data-ttu-id="5f3ff-221">Depurar</span><span class="sxs-lookup"><span data-stu-id="5f3ff-221">Debug</span></span>](xref:Microsoft.Extensions.Logging.LogLevel) | <span data-ttu-id="5f3ff-222">1</span><span class="sxs-lookup"><span data-stu-id="5f3ff-222">1</span></span> | <xref:Microsoft.Extensions.Logging.LoggerExtensions.LogDebug%2A> | <span data-ttu-id="5f3ff-223">Para depuración y desarrollo.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-223">For debugging and development.</span></span> <span data-ttu-id="5f3ff-224">Debido al elevado volumen, tenga precaución cuando lo use en producción.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-224">Use with caution in production due to the high volume.</span></span> |
| [<span data-ttu-id="5f3ff-225">Información</span><span class="sxs-lookup"><span data-stu-id="5f3ff-225">Information</span></span>](xref:Microsoft.Extensions.Logging.LogLevel) | <span data-ttu-id="5f3ff-226">2</span><span class="sxs-lookup"><span data-stu-id="5f3ff-226">2</span></span> | <xref:Microsoft.Extensions.Logging.LoggerExtensions.LogInformation%2A> | <span data-ttu-id="5f3ff-227">Realiza el seguimiento del flujo general de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-227">Tracks the general flow of the app.</span></span> <span data-ttu-id="5f3ff-228">Puede tener un valor a largo plazo.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-228">May have long-term value.</span></span> |
| [<span data-ttu-id="5f3ff-229">Advertencia</span><span class="sxs-lookup"><span data-stu-id="5f3ff-229">Warning</span></span>](xref:Microsoft.Extensions.Logging.LogLevel) | <span data-ttu-id="5f3ff-230">3</span><span class="sxs-lookup"><span data-stu-id="5f3ff-230">3</span></span> | <xref:Microsoft.Extensions.Logging.LoggerExtensions.LogWarning%2A> | <span data-ttu-id="5f3ff-231">Para eventos anómalos o inesperados.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-231">For abnormal or unexpected events.</span></span> <span data-ttu-id="5f3ff-232">Normalmente incluye errores o estados que no provocan un error en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-232">Typically includes errors or conditions that don't cause the app to fail.</span></span> |
| [<span data-ttu-id="5f3ff-233">Error</span><span class="sxs-lookup"><span data-stu-id="5f3ff-233">Error</span></span>](xref:Microsoft.Extensions.Logging.LogLevel) | <span data-ttu-id="5f3ff-234">4</span><span class="sxs-lookup"><span data-stu-id="5f3ff-234">4</span></span> | <xref:Microsoft.Extensions.Logging.LoggerExtensions.LogError%2A> | <span data-ttu-id="5f3ff-235">Para los errores y excepciones que no se pueden controlar.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-235">For errors and exceptions that cannot be handled.</span></span> <span data-ttu-id="5f3ff-236">Estos mensajes indican un error en la operación o solicitud actual, no un error de toda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-236">These messages indicate a failure in the current operation or request, not an app-wide failure.</span></span> |
| <span data-ttu-id="5f3ff-237">[Critical)](xref:Microsoft.Extensions.Logging.LogLevel) (Crítico)</span><span class="sxs-lookup"><span data-stu-id="5f3ff-237">[Critical](xref:Microsoft.Extensions.Logging.LogLevel)</span></span> | <span data-ttu-id="5f3ff-238">5</span><span class="sxs-lookup"><span data-stu-id="5f3ff-238">5</span></span> | <xref:Microsoft.Extensions.Logging.LoggerExtensions.LogCritical%2A> | <span data-ttu-id="5f3ff-239">Para los errores que requieren atención inmediata.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-239">For failures that require immediate attention.</span></span> <span data-ttu-id="5f3ff-240">Ejemplos: escenarios de pérdida de datos, espacio en disco insuficiente.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-240">Examples: data loss scenarios, out of disk space.</span></span> |
| [<span data-ttu-id="5f3ff-241">Ninguno</span><span class="sxs-lookup"><span data-stu-id="5f3ff-241">None</span></span>](xref:Microsoft.Extensions.Logging.LogLevel) | <span data-ttu-id="5f3ff-242">6</span><span class="sxs-lookup"><span data-stu-id="5f3ff-242">6</span></span> |  | <span data-ttu-id="5f3ff-243">Especifica que no se debe escribir ningún mensaje.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-243">Specifies that no messages should be written.</span></span> |

<span data-ttu-id="5f3ff-244">En la tabla anterior, `LogLevel` aparece de menor a mayor gravedad.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-244">In the previous table, the `LogLevel` is listed from lowest to highest severity.</span></span>

<span data-ttu-id="5f3ff-245">El primer parámetro del método [Log](xref:Microsoft.Extensions.Logging.LoggerExtensions), <xref:Microsoft.Extensions.Logging.LogLevel>, indica la gravedad del registro.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-245">The [Log](xref:Microsoft.Extensions.Logging.LoggerExtensions) method's first parameter, <xref:Microsoft.Extensions.Logging.LogLevel>, indicates the severity of the log.</span></span> <span data-ttu-id="5f3ff-246">En lugar de llamar a `Log(LogLevel, ...)`, la mayoría de los desarrolladores llaman a los métodos de extensión [Log{LogLevel}](xref:Microsoft.Extensions.Logging.LoggerExtensions).</span><span class="sxs-lookup"><span data-stu-id="5f3ff-246">Rather than calling `Log(LogLevel, ...)`, most developers call the [Log{LogLevel}](xref:Microsoft.Extensions.Logging.LoggerExtensions) extension methods.</span></span> <span data-ttu-id="5f3ff-247">Los métodos de extensión `Log{LogLevel}` [llaman al método Log y especifican el LogLevel](https://github.com/dotnet/extensions/blob/release/3.1/src/Logging/Logging.Abstractions/src/LoggerExtensions.cs).</span><span class="sxs-lookup"><span data-stu-id="5f3ff-247">The `Log{LogLevel}` extension methods [call the Log method and specify the LogLevel](https://github.com/dotnet/extensions/blob/release/3.1/src/Logging/Logging.Abstractions/src/LoggerExtensions.cs).</span></span> <span data-ttu-id="5f3ff-248">Por ejemplo, las dos llamadas de registro siguientes son funcionalmente equivalentes y generan el mismo registro:</span><span class="sxs-lookup"><span data-stu-id="5f3ff-248">For example, the following two logging calls are functionally equivalent and produce the same log:</span></span>

```csharp
public void LogDetails()
{
    var logMessage = "Details for log.";

    _logger.Log(LogLevel.Information, AppLogEvents.Details, logMessage);
    _logger.LogInformation(AppLogEvents.Details, logMessage);
}
```

<span data-ttu-id="5f3ff-249">`AppLogEvents.Details` es el identificador del evento y se representa implícitamente mediante un valor <xref:System.Int32> de constante.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-249">`AppLogEvents.Details` is the event ID, and is implicitly represented by a constant <xref:System.Int32> value.</span></span> <span data-ttu-id="5f3ff-250">`AppLogEvents` es una clase que expone varias constantes de identificador con nombre y se muestra en la sección [Id. de evento del registro](#log-event-id).</span><span class="sxs-lookup"><span data-stu-id="5f3ff-250">`AppLogEvents` is a class that exposes various named identifier constants and is displayed in the [Log event ID](#log-event-id) section.</span></span>

<span data-ttu-id="5f3ff-251">El siguiente código crea los registros `Information` y `Warning`:</span><span class="sxs-lookup"><span data-stu-id="5f3ff-251">The following code creates `Information` and `Warning` logs:</span></span>

```csharp
public async Task<T> GetAsync<T>(string id)
{
    _logger.LogInformation(AppLogEvents.Read, "Reading value for {Id}", id);

    var result = await _repository.GetAsync(id);
    if (result is null)
    {
        _logger.LogWarning(AppLogEvents.ReadNotFound, "GetAsync({Id}) not found", id);
    }

    return result;
}
```

<span data-ttu-id="5f3ff-252">En el código anterior, el primer parámetro de `Log{LogLevel}`, `AppLogEvents.Read`, es el [identificador de evento de registro](#log-event-id).</span><span class="sxs-lookup"><span data-stu-id="5f3ff-252">In the preceding code, the first `Log{LogLevel}` parameter,`AppLogEvents.Read`, is the [Log event ID](#log-event-id).</span></span> <span data-ttu-id="5f3ff-253">El segundo parámetro es una plantilla de mensaje con marcadores de posición para los valores de argumento proporcionados por el resto de parámetros de método.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-253">The second parameter is a message template with placeholders for argument values provided by the remaining method parameters.</span></span> <span data-ttu-id="5f3ff-254">Los parámetros de método se explican detalladamente en la sección de la [plantilla de mensaje](#log-message-template) más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-254">The method parameters are explained in the [message template](#log-message-template) section later in this article.</span></span>

<span data-ttu-id="5f3ff-255">Configure el nivel de registro adecuado y llame a los métodos `Log{LogLevel}` correctos para controlar el volumen de resultados del registro que se escriben en un soporte de almacenamiento determinado.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-255">Configure the appropriate log level and call the correct `Log{LogLevel}` methods to control how much log output is written to a particular storage medium.</span></span> <span data-ttu-id="5f3ff-256">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5f3ff-256">For example:</span></span>

- <span data-ttu-id="5f3ff-257">En producción:</span><span class="sxs-lookup"><span data-stu-id="5f3ff-257">In production:</span></span>
  - <span data-ttu-id="5f3ff-258">El registro en los niveles `Trace` o `Information` genera un gran volumen de mensajes de registro detallados.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-258">Logging at the `Trace` or `Information` levels produces a high-volume of detailed log messages.</span></span> <span data-ttu-id="5f3ff-259">Para controlar los costos y no superar los límites de almacenamiento de datos, registre los mensajes de nivel `Trace` a `Information` en un almacén de datos de alto volumen y bajo costo.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-259">To control costs and not exceed data storage limits, log `Trace` and `Information` level messages to a high-volume, low-cost data store.</span></span> <span data-ttu-id="5f3ff-260">Considere la posibilidad de limitar `Trace` y `Information` a categorías específicas.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-260">Consider limiting `Trace` and `Information` to specific categories.</span></span>
  - <span data-ttu-id="5f3ff-261">El registro entre los niveles `Warning` y `Critical` debe generar pocos mensajes de registro.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-261">Logging at `Warning` through `Critical` levels should produce few log messages.</span></span>
    - <span data-ttu-id="5f3ff-262">Los costos y los límites de almacenamiento no suelen ser un problema.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-262">Costs and storage limits usually aren't a concern.</span></span>
    - <span data-ttu-id="5f3ff-263">Cuantos menos registros haya, mayor será la flexibilidad a la hora de elegir el almacén de datos.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-263">Few logs allow more flexibility in data store choices.</span></span>
- <span data-ttu-id="5f3ff-264">En desarrollo:</span><span class="sxs-lookup"><span data-stu-id="5f3ff-264">In development:</span></span>
  - <span data-ttu-id="5f3ff-265">Establézcalo en `Warning`.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-265">Set to `Warning`.</span></span>
  - <span data-ttu-id="5f3ff-266">Agregue los mensajes `Trace` o`Information` al solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-266">Add `Trace` or `Information` messages when troubleshooting.</span></span> <span data-ttu-id="5f3ff-267">Para limitar la salida, establezca `Trace` o `Information` solo para las categorías que se están investigando.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-267">To limit output, set `Trace` or `Information` only for the categories under investigation.</span></span>

<span data-ttu-id="5f3ff-268">El siguiente JSON establece `Logging:Console:LogLevel:Microsoft:Information`:</span><span class="sxs-lookup"><span data-stu-id="5f3ff-268">The following JSON sets `Logging:Console:LogLevel:Microsoft:Information`:</span></span>

:::code language="json" source="snippets/configuration/worker-service/appsettings.MSFT.json":::

## <a name="log-event-id"></a><span data-ttu-id="5f3ff-269">Id. de evento del registro</span><span class="sxs-lookup"><span data-stu-id="5f3ff-269">Log event ID</span></span>

<span data-ttu-id="5f3ff-270">Cada registro puede especificar un *identificador de evento*; <xref:Microsoft.Extensions.Logging.EventId> es una estructura con `Id` y propiedades opcionales `Name` de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-270">Each log can specify an *event identifer*, the <xref:Microsoft.Extensions.Logging.EventId> is a structure with an `Id` and optional `Name` readonly properties.</span></span> <span data-ttu-id="5f3ff-271">El código fuente de ejemplo usa la clase `AppLogEvents` para definir los identificadores de evento:</span><span class="sxs-lookup"><span data-stu-id="5f3ff-271">The sample source code uses the `AppLogEvents` class to define event IDs:</span></span>

```csharp
internal static class AppLogEvents
{
    internal const int Create = 1000;
    internal const int Read = 1001;
    internal const int Update = 1002;
    internal const int Delete = 1003;

    internal const int Details = 3000;
    internal const int Error = 3001;

    internal const int ReadNotFound = 4000;
    internal const int UpdateNotFound = 4001;

    // ...
}
```

<span data-ttu-id="5f3ff-272">Un id. de evento asocia un conjunto de eventos.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-272">An event ID associates a set of events.</span></span> <span data-ttu-id="5f3ff-273">Por ejemplo, todos los registros relacionados con la lectura de valores de un repositorio pueden ser `1001`.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-273">For example, all logs related to reading values from a repository might be `1001`.</span></span>

<span data-ttu-id="5f3ff-274">El proveedor de registro puede registrar el id. de evento en un campo de identificador, en el mensaje de registro o no almacenarlo.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-274">The logging provider may log the event ID in an ID field, in the logging message, or not at all.</span></span> <span data-ttu-id="5f3ff-275">El proveedor de depuración no muestra los identificadores de evento.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-275">The Debug provider doesn't show event IDs.</span></span> <span data-ttu-id="5f3ff-276">El proveedor de consola muestra los identificadores de evento entre corchetes después de la categoría:</span><span class="sxs-lookup"><span data-stu-id="5f3ff-276">The console provider shows event IDs in brackets after the category:</span></span>

```console
info: Example.DefaultService.GetAsync[1001]
      Reading value for a1b2c3
warn: Example.DefaultService.GetAsync[4000]
      GetAsync(a1b2c3) not found
```

<span data-ttu-id="5f3ff-277">Algunos proveedores de registro almacenan el identificador de evento en un campo, lo que permite filtrar por el id.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-277">Some logging providers store the event ID in a field, which allows for filtering on the ID.</span></span>

## <a name="log-message-template"></a><span data-ttu-id="5f3ff-278">Plantilla de mensaje de registro</span><span class="sxs-lookup"><span data-stu-id="5f3ff-278">Log message template</span></span>

<span data-ttu-id="5f3ff-279">Cada API de registro usa una plantilla de mensaje.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-279">Each log API uses a message template.</span></span> <span data-ttu-id="5f3ff-280">La plantilla de mensaje puede contener marcadores de posición para los que se proporcionan argumentos.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-280">The message template can contain placeholders for which arguments are provided.</span></span> <span data-ttu-id="5f3ff-281">Use los nombres de los marcadores de posición, no números.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-281">Use names for the placeholders, not numbers.</span></span> <span data-ttu-id="5f3ff-282">El orden de los marcadores de posición, no sus nombres, determina qué parámetros se usan para proporcionar sus valores.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-282">The order of placeholders, not their names, determines which parameters are used to provide their values.</span></span> <span data-ttu-id="5f3ff-283">En el código siguiente, los nombres de parámetro están fuera de la secuencia en la plantilla de mensaje:</span><span class="sxs-lookup"><span data-stu-id="5f3ff-283">In the following code, the parameter names are out of sequence in the message template:</span></span>

```csharp
string p1 = "param1";
string p2 = "param2";
_logger.LogInformation("Parameter values: {p2}, {p1}", p1, p2);
```

<span data-ttu-id="5f3ff-284">El código anterior crea un mensaje de registro con los valores de parámetro en secuencia:</span><span class="sxs-lookup"><span data-stu-id="5f3ff-284">The preceding code creates a log message with the parameter values in sequence:</span></span>

```text
Parameter values: param1, param2
```

<span data-ttu-id="5f3ff-285">Este enfoque permite a los proveedores de registro implementar [registro semántico o estructurado](https://github.com/NLog/NLog/wiki/How-to-use-structured-logging).</span><span class="sxs-lookup"><span data-stu-id="5f3ff-285">This approach allows logging providers to implement [semantic or structured logging](https://github.com/NLog/NLog/wiki/How-to-use-structured-logging).</span></span> <span data-ttu-id="5f3ff-286">Los propios argumentos se pasan al sistema de registro, no solo a la plantilla de mensaje con formato.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-286">The arguments themselves are passed to the logging system, not just the formatted message template.</span></span> <span data-ttu-id="5f3ff-287">Esto permite a los proveedores de registro almacenar los valores de parámetro como campos.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-287">This enables logging providers to store the parameter values as fields.</span></span> <span data-ttu-id="5f3ff-288">Observe el siguiente método de registrador:</span><span class="sxs-lookup"><span data-stu-id="5f3ff-288">Consider the following logger method:</span></span>

```csharp
_logger.LogInformation("Getting item {Id} at {RunTime}", id, DateTime.Now);
```

<span data-ttu-id="5f3ff-289">Por ejemplo, al registrar en Azure Table Storage:</span><span class="sxs-lookup"><span data-stu-id="5f3ff-289">For example, when logging to Azure Table Storage:</span></span>

- <span data-ttu-id="5f3ff-290">Cada entidad de Azure Table puede tener propiedades `ID` y `RunTime`.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-290">Each Azure Table entity can have `ID` and `RunTime` properties.</span></span>
- <span data-ttu-id="5f3ff-291">Las tablas con propiedades simplifican las consultas en los datos registrados.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-291">Tables with properties simplify queries on logged data.</span></span> <span data-ttu-id="5f3ff-292">Por ejemplo, una consulta puede buscar todos los registros dentro de un intervalo `RunTime` determinado sin necesidad de analizar el tiempo de espera del mensaje de texto.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-292">For example, a query can find all logs within a particular `RunTime` range without having to parse the time out of the text message.</span></span>

## <a name="log-exceptions"></a><span data-ttu-id="5f3ff-293">Registro de excepciones</span><span class="sxs-lookup"><span data-stu-id="5f3ff-293">Log exceptions</span></span>

<span data-ttu-id="5f3ff-294">Los métodos de registrador tienen sobrecargas que toman un parámetro de excepción:</span><span class="sxs-lookup"><span data-stu-id="5f3ff-294">The logger methods have overloads that take an exception parameter:</span></span>

```csharp
public void Test(string id)
{
    try
    {
        if (id == "none")
        {
            throw new Exception("Default Id detected.");
        }
    }
    catch (Exception ex)
    {
        _logger.LogWarning(
            AppLogEvents.Error, ex,
            "Failed to process iteration: {Id}", id)
    }
}
```

<span data-ttu-id="5f3ff-295">El registro de excepciones es específico del proveedor.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-295">Exception logging is provider-specific.</span></span>

### <a name="default-log-level"></a><span data-ttu-id="5f3ff-296">Nivel de registro predeterminado</span><span class="sxs-lookup"><span data-stu-id="5f3ff-296">Default log level</span></span>

<span data-ttu-id="5f3ff-297">Si no se establece el nivel de registro predeterminado, su valor será `Information`.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-297">If the default log level is not set, the default log level value is `Information`.</span></span>

<span data-ttu-id="5f3ff-298">Por ejemplo, observe la siguiente aplicación de servicio de trabajo:</span><span class="sxs-lookup"><span data-stu-id="5f3ff-298">For example, consider the following worker service app:</span></span>

- <span data-ttu-id="5f3ff-299">Creada con las plantillas de trabajo de .NET.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-299">Created with the .NET Worker templates.</span></span>
- <span data-ttu-id="5f3ff-300">*appsettings.json* y *appsettings.Development.json* eliminados o con el nombre cambiado.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-300">*appsettings.json* and *appsettings.Development.json* deleted or renamed.</span></span>

<span data-ttu-id="5f3ff-301">Con la configuración anterior, al navegar a la página de privacidad o de inicio, se generan muchos mensajes de `Trace`, `Debug` y `Information` con `Microsoft` en el nombre de la categoría.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-301">With the preceding setup, navigating to the privacy or home page produces many `Trace`, `Debug`, and `Information`  messages with `Microsoft` in the category name.</span></span>

<span data-ttu-id="5f3ff-302">El código siguiente establece el nivel de registro predeterminado cuando este no se establece en la configuración:</span><span class="sxs-lookup"><span data-stu-id="5f3ff-302">The following code sets the default log level when the default log level is not set in configuration:</span></span>

```csharp
class Program
{
    static Task Main(string[] args) =>
        CreateHostBuilder(args).Build().RunAsync();

    static IHostBuilder CreateHostBuilder(string[] args) =>
        Host.CreateDefaultBuilder(args)
            .ConfigureLogging(logging => logging.SetMinimumLevel(LogLevel.Warning));
}
```

### <a name="filter-function"></a><span data-ttu-id="5f3ff-303">Función de filtro</span><span class="sxs-lookup"><span data-stu-id="5f3ff-303">Filter function</span></span>

<span data-ttu-id="5f3ff-304">Se invoca una función de filtro para todos los proveedores y las categorías que no tienen reglas asignadas mediante configuración o código:</span><span class="sxs-lookup"><span data-stu-id="5f3ff-304">A filter function is invoked for all providers and categories that don't have rules assigned to them by configuration or code:</span></span>

```csharp
class Program
{
    static Task Main(string[] args) =>
        CreateHostBuilder(args).Build().RunAsync();

    static IHostBuilder CreateHostBuilder(string[] args) =>
        Host.CreateDefaultBuilder(args)
            .ConfigureLogging(logging =>
                logging.AddFilter((provider, category, logLevel) =>
                {
                    return provider.Contains("ConsoleLoggerProvider")
                        && (category.Contains("Example") || category.Contains("Microsoft"))
                        && logLevel >= LogLevel.Information;
                }));
}
```

<span data-ttu-id="5f3ff-305">El código anterior muestra los registros de la consola cuando la categoría contiene `Example` o `Microsoft` y el nivel de registro es `Information` o superior.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-305">The preceding code displays console logs when the category contains `Example` or `Microsoft` and the log level is `Information` or higher.</span></span>

## <a name="log-scopes"></a><span data-ttu-id="5f3ff-306">Ámbitos de registro</span><span class="sxs-lookup"><span data-stu-id="5f3ff-306">Log scopes</span></span>

 <span data-ttu-id="5f3ff-307">Un *ámbito* puede agrupar un conjunto de operaciones lógicas.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-307">A *scope* can group a set of logical operations.</span></span> <span data-ttu-id="5f3ff-308">Esta agrupación se puede utilizar para adjuntar los mismos datos para cada registro que se crea como parte de un conjunto.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-308">This grouping can be used to attach the same data to each log that's created as part of a set.</span></span> <span data-ttu-id="5f3ff-309">Por ejemplo, cada registro creado como parte del procesamiento de una transacción puede incluir el identificador de dicha transacción.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-309">For example, every log created as part of processing a transaction can include the transaction ID.</span></span>

<span data-ttu-id="5f3ff-310">Un ámbito:</span><span class="sxs-lookup"><span data-stu-id="5f3ff-310">A scope:</span></span>

- <span data-ttu-id="5f3ff-311">es un tipo <xref:System.IDisposable> devuelto por el método <xref:Microsoft.Extensions.Logging.ILogger.BeginScope%2A>;</span><span class="sxs-lookup"><span data-stu-id="5f3ff-311">Is an <xref:System.IDisposable> type that's returned by the <xref:Microsoft.Extensions.Logging.ILogger.BeginScope%2A> method.</span></span>
- <span data-ttu-id="5f3ff-312">se mantiene hasta que se elimina.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-312">Lasts until it's disposed.</span></span>

<span data-ttu-id="5f3ff-313">Los siguientes proveedores admiten ámbitos:</span><span class="sxs-lookup"><span data-stu-id="5f3ff-313">The following providers support scopes:</span></span>

- `Console`
- [<span data-ttu-id="5f3ff-314">AzureAppServicesFile y AzureAppServicesBlob</span><span class="sxs-lookup"><span data-stu-id="5f3ff-314">AzureAppServicesFile and AzureAppServicesBlob</span></span>](xref:Microsoft.Extensions.Logging.AzureAppServices.BatchingLoggerOptions.IncludeScopes)

<span data-ttu-id="5f3ff-315">Use un ámbito encapsulando las llamadas de registrador en un bloque `using`:</span><span class="sxs-lookup"><span data-stu-id="5f3ff-315">Use a scope by wrapping logger calls in a `using` block:</span></span>

```csharp
public async Task<T> GetAsync<T>(string id)
{
    T result;

    using (_logger.BeginScope("using block message"))
    {
        _logger.LogInformation(
            AppLogEvents.Read, "Reading value for {Id}", id);

        var result = await _repository.GetAsync(id);
        if (result is null)
        {
            _logger.LogWarning(
                AppLogEvents.ReadNotFound, "GetAsync({Id}) not found", id);
        }
    }

    return result;
}
```

<span data-ttu-id="5f3ff-316">El JSON siguiente habilita ámbitos para el proveedor de la consola:</span><span class="sxs-lookup"><span data-stu-id="5f3ff-316">The following JSON enables scopes for the console provider:</span></span>

:::code language="json" source="snippets/configuration/worker-service/appsettings.IncludeScopes.json" highlight="9":::

<span data-ttu-id="5f3ff-317">El código siguiente permite ámbitos para el proveedor de la consola:</span><span class="sxs-lookup"><span data-stu-id="5f3ff-317">The following code enables scopes for the console provider:</span></span>

```csharp
class Program
{
    static Task Main(string[] args) =>
        CreateHostBuilder(args).Build().RunAsync();

    static IHostBuilder CreateHostBuilder(string[] args) =>
        Host.CreateDefaultBuilder(args)
            .ConfigureLogging((_, logging) =>
                logging.ClearProviders()
                    .AddConsole(options => options.IncludeScopes = true));
}
```

## <a name="non-host-console-app"></a><span data-ttu-id="5f3ff-318">Aplicación de consola que no es de host</span><span class="sxs-lookup"><span data-stu-id="5f3ff-318">Non-host console app</span></span>

<span data-ttu-id="5f3ff-319">El código de registro para las aplicaciones sin un [host genérico](generic-host.md) es distinto en la forma en que [se agregan los proveedores](logging-providers.md#built-in-logging-providers) y [se crean los registradores](#create-logs).</span><span class="sxs-lookup"><span data-stu-id="5f3ff-319">Logging code for apps without a [Generic Host](generic-host.md) differs in the way [providers are added](logging-providers.md#built-in-logging-providers) and [loggers are created](#create-logs).</span></span> <span data-ttu-id="5f3ff-320">En una aplicación de consola que no sea de host, llame al método de extensión `Add{provider name}` del proveedor al crear un elemento `LoggerFactory`:</span><span class="sxs-lookup"><span data-stu-id="5f3ff-320">In a non-host console app, call the provider's `Add{provider name}` extension method while creating a `LoggerFactory`:</span></span>

```csharp
class Program
{
    static void Main(string[] args)
    {
        using var loggerFactory = LoggerFactory.Create(builder =>
        {
            builder
                .AddFilter("Microsoft", LogLevel.Warning)
                .AddFilter("System", LogLevel.Warning)
                .AddFilter("LoggingConsoleApp.Program", LogLevel.Debug)
                .AddConsole();
        });

        ILogger logger = loggerFactory.CreateLogger<Program>();
        logger.LogInformation("Example log message");
    }
}
```

<span data-ttu-id="5f3ff-321">El objeto `loggerFactory` se usa para crear una instancia de <xref:Microsoft.Extensions.Logging.ILogger>.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-321">The `loggerFactory` object is used to create an <xref:Microsoft.Extensions.Logging.ILogger> instance.</span></span>

## <a name="create-logs-in-main"></a><span data-ttu-id="5f3ff-322">Creación de registros en Main</span><span class="sxs-lookup"><span data-stu-id="5f3ff-322">Create logs in Main</span></span>

<span data-ttu-id="5f3ff-323">El código siguiente registra en `Main` mediante la obtención de una instancia de `ILogger` de inserción de dependencias después de compilar el host:</span><span class="sxs-lookup"><span data-stu-id="5f3ff-323">The following code logs in `Main` by getting an `ILogger` instance from DI after building the host:</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Extensions.DependencyInjection;
using Microsoft.Extensions.Hosting;
using Microsoft.Extensions.Logging;

class Program
{
    static Task Main(string[] args)
    {
        IHost host = Host.CreateDefaultBuilder(args).Build();

        var logger = host.Services.GetRequiredService<ILogger<Program>>();
        logger.LogInformation("Host created.");

        return host.RunAsync();
    }
}
```

### <a name="no-asynchronous-logger-methods"></a><span data-ttu-id="5f3ff-324">No hay métodos de registrador asincrónicos</span><span class="sxs-lookup"><span data-stu-id="5f3ff-324">No asynchronous logger methods</span></span>

<span data-ttu-id="5f3ff-325">El registro debe ser tan rápido que no merezca la pena el costo de rendimiento del código asincrónico.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-325">Logging should be so fast that it isn't worth the performance cost of asynchronous code.</span></span> <span data-ttu-id="5f3ff-326">Si el almacén de datos de registro es lento, no escriba directamente en él.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-326">If a logging data store is slow, don't write to it directly.</span></span> <span data-ttu-id="5f3ff-327">Considere la posibilidad de escribir primero los mensajes de registro en un almacén rápido y, después, moverlos al almacén lento.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-327">Consider writing the log messages to a fast store initially, then moving them to the slow store later.</span></span> <span data-ttu-id="5f3ff-328">Por ejemplo, al iniciar sesión en SQL Server, no lo haga directamente en un método `Log`, ya que los métodos `Log` son sincrónicos.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-328">For example, when logging to SQL Server, don't do so directly in a `Log` method, since the `Log` methods are synchronous.</span></span> <span data-ttu-id="5f3ff-329">En su lugar, agregue sincrónicamente mensajes de registro a una cola en memoria y haga que un trabajo en segundo plano extraiga los mensajes de la cola para realizar el trabajo asincrónico de insertar datos en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-329">Instead, synchronously add log messages to an in-memory queue and have a background worker pull the messages out of the queue to do the asynchronous work of pushing data to SQL Server.</span></span>

## <a name="change-log-levels-in-a-running-app"></a><span data-ttu-id="5f3ff-330">Cambio de los niveles de registro en una aplicación en ejecución</span><span class="sxs-lookup"><span data-stu-id="5f3ff-330">Change log levels in a running app</span></span>

<span data-ttu-id="5f3ff-331">La API de registro no incluye un escenario que permita cambiar los niveles de registro mientras se ejecuta una aplicación.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-331">The Logging API doesn't include a scenario to change log levels while an app is running.</span></span> <span data-ttu-id="5f3ff-332">No obstante, algunos proveedores de configuración pueden volver a cargar la configuración, lo que tiene efecto inmediato en la configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-332">However, some configuration providers are capable of reloading configuration, which takes immediate effect on logging configuration.</span></span> <span data-ttu-id="5f3ff-333">Por ejemplo, el [Proveedor de configuración de archivo](configuration-providers.md#file-configuration-provider) vuelve a cargar la configuración de registro de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-333">For example, the [File Configuration Provider](configuration-providers.md#file-configuration-provider) reloads logging configuration by default.</span></span> <span data-ttu-id="5f3ff-334">Si se cambia la configuración en el código mientras se ejecuta una aplicación, la aplicación puede llamar a [IConfigurationRoot.Reload](xref:Microsoft.Extensions.Configuration.IConfigurationRoot.Reload%2A) para actualizar la configuración de registro de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-334">If configuration is changed in code while an app is running, the app can call [IConfigurationRoot.Reload](xref:Microsoft.Extensions.Configuration.IConfigurationRoot.Reload%2A) to update the app's logging configuration.</span></span>

## <a name="nuget-packages"></a><span data-ttu-id="5f3ff-335">Paquetes NuGet</span><span class="sxs-lookup"><span data-stu-id="5f3ff-335">NuGet packages</span></span>

<span data-ttu-id="5f3ff-336">Las implementaciones y las interfaces de <xref:Microsoft.Extensions.Logging.ILogger%601> y <xref:Microsoft.Extensions.Logging.ILoggerFactory> se incluyen en el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-336">The <xref:Microsoft.Extensions.Logging.ILogger%601> and <xref:Microsoft.Extensions.Logging.ILoggerFactory> interfaces and implementations are included in the .NET Core SDK.</span></span> <span data-ttu-id="5f3ff-337">También están disponibles en los siguientes paquetes NuGet:</span><span class="sxs-lookup"><span data-stu-id="5f3ff-337">They are also available in the following NuGet packages:</span></span>

- <span data-ttu-id="5f3ff-338">Las interfaces están en [Microsoft.Extensions.Logging.Abstractions](https://www.nuget.org/packages/Microsoft.Extensions.Logging.Abstractions).</span><span class="sxs-lookup"><span data-stu-id="5f3ff-338">The interfaces are in [Microsoft.Extensions.Logging.Abstractions](https://www.nuget.org/packages/Microsoft.Extensions.Logging.Abstractions).</span></span>
- <span data-ttu-id="5f3ff-339">Las implementaciones predeterminadas se encuentran en [Microsoft.Extensions.Logging](https://www.nuget.org/packages/microsoft.extensions.logging).</span><span class="sxs-lookup"><span data-stu-id="5f3ff-339">The default implementations are in [Microsoft.Extensions.Logging](https://www.nuget.org/packages/microsoft.extensions.logging).</span></span>

## <a name="apply-log-filter-rules-in-code"></a><span data-ttu-id="5f3ff-340">Aplicación de reglas de filtro en el código</span><span class="sxs-lookup"><span data-stu-id="5f3ff-340">Apply log filter rules in code</span></span>

<span data-ttu-id="5f3ff-341">El método preferido para establecer las reglas de filtro de registro es mediante la [Configuración](configuration.md).</span><span class="sxs-lookup"><span data-stu-id="5f3ff-341">The preferred approach for setting log filter rules is by using [Configuration](configuration.md).</span></span>

<span data-ttu-id="5f3ff-342">En el siguiente ejemplo se muestra cómo registrar reglas de filtro en el código:</span><span class="sxs-lookup"><span data-stu-id="5f3ff-342">The following example shows how to register filter rules in code:</span></span>

```csharp
class Program
{
    static Task Main(string[] args) =>
        CreateHostBuilder(args).Build().RunAsync();

    static IHostBuilder CreateHostBuilder(string[] args) =>
        Host.CreateDefaultBuilder(args)
            .ConfigureLogging(logging =>
               logging.AddFilter("System", LogLevel.Debug)
                  .AddFilter<DebugLoggerProvider>("Microsoft", LogLevel.Information)
                  .AddFilter<ConsoleLoggerProvider>("Microsoft", LogLevel.Trace));
}
```

<span data-ttu-id="5f3ff-343">`logging.AddFilter("System", LogLevel.Debug)` especifica la categoría `System` y el nivel de registro `Debug`.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-343">`logging.AddFilter("System", LogLevel.Debug)` specifies the `System` category and log level `Debug`.</span></span> <span data-ttu-id="5f3ff-344">El filtro se aplica a todos los proveedores porque no se ha configurado un proveedor específico.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-344">The filter is applied to all providers because a specific provider was not configured.</span></span>

<span data-ttu-id="5f3ff-345">`AddFilter<DebugLoggerProvider>("Microsoft", LogLevel.Information)` especifica:</span><span class="sxs-lookup"><span data-stu-id="5f3ff-345">`AddFilter<DebugLoggerProvider>("Microsoft", LogLevel.Information)` specifies:</span></span>

- <span data-ttu-id="5f3ff-346">El proveedor de registro `Debug`.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-346">The `Debug` logging provider.</span></span>
- <span data-ttu-id="5f3ff-347">Nivel de registro `Information` y superiores.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-347">Log level `Information` and higher.</span></span>
- <span data-ttu-id="5f3ff-348">Todas las categorías que empiezan con `"Microsoft"`.</span><span class="sxs-lookup"><span data-stu-id="5f3ff-348">All categories starting with `"Microsoft"`.</span></span>

## <a name="see-also"></a><span data-ttu-id="5f3ff-349">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f3ff-349">See also</span></span>

- [<span data-ttu-id="5f3ff-350">Proveedores de registro en .NET</span><span class="sxs-lookup"><span data-stu-id="5f3ff-350">Logging providers in .NET</span></span>](logging-providers.md)
- [<span data-ttu-id="5f3ff-351">Implementación de un proveedor de registro personalizado en .NET</span><span class="sxs-lookup"><span data-stu-id="5f3ff-351">Implement a custom logging provider in .NET</span></span>](custom-logging-provider.md)
- [<span data-ttu-id="5f3ff-352">Formato de registro de la consola</span><span class="sxs-lookup"><span data-stu-id="5f3ff-352">Console log formatting</span></span>](console-log-formatter.md)
- [<span data-ttu-id="5f3ff-353">Registro de alto rendimiento en .NET</span><span class="sxs-lookup"><span data-stu-id="5f3ff-353">High-performance logging in .NET</span></span>](high-performance-logging.md)
- <span data-ttu-id="5f3ff-354">Los errores de registro deben crearse en el repositorio [github.com/dotnet/extensions](https://github.com/dotnet/extensions/issues).</span><span class="sxs-lookup"><span data-stu-id="5f3ff-354">Logging bugs should be created in the [github.com/dotnet/extensions](https://github.com/dotnet/extensions/issues) repo</span></span>
