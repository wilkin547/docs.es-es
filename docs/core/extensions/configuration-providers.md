---
title: Proveedores de configuración en .NET
description: Obtenga información sobre cómo se usa la API de proveedores de configuración para configurar aplicaciones .NET.
author: IEvangelist
ms.author: dapine
ms.date: 03/08/2021
ms.openlocfilehash: 5f248c93de1773a8bbe8209f002806fb196bb260
ms.sourcegitcommit: 46cfed35d79d70e08c313b9c664c7e76babab39e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/10/2021
ms.locfileid: "102605014"
---
# <a name="configuration-providers-in-net"></a><span data-ttu-id="798bc-103">Proveedores de configuración en .NET</span><span class="sxs-lookup"><span data-stu-id="798bc-103">Configuration providers in .NET</span></span>

<span data-ttu-id="798bc-104">La configuración en .NET se realiza con proveedores de configuración.</span><span class="sxs-lookup"><span data-stu-id="798bc-104">Configuration in .NET is possible with configuration providers.</span></span> <span data-ttu-id="798bc-105">Hay varios tipos de proveedores que dependen de varios orígenes de configuración.</span><span class="sxs-lookup"><span data-stu-id="798bc-105">There are several types of providers that rely on various configuration sources.</span></span> <span data-ttu-id="798bc-106">En este artículo se detallan los distintos proveedores de configuración y sus orígenes correspondientes.</span><span class="sxs-lookup"><span data-stu-id="798bc-106">This article details all of the different configuration providers and their corresponding sources.</span></span>

- [<span data-ttu-id="798bc-107">Proveedor de configuración de archivo</span><span class="sxs-lookup"><span data-stu-id="798bc-107">File configuration provider</span></span>](#file-configuration-provider)
- [<span data-ttu-id="798bc-108">Proveedor de configuración de variables de entorno</span><span class="sxs-lookup"><span data-stu-id="798bc-108">Environment variable configuration provider</span></span>](#environment-variable-configuration-provider)
- [<span data-ttu-id="798bc-109">Proveedor de configuración de línea de comandos</span><span class="sxs-lookup"><span data-stu-id="798bc-109">Command-line configuration provider</span></span>](#command-line-configuration-provider)
- [<span data-ttu-id="798bc-110">Proveedor de configuración de clave por archivo</span><span class="sxs-lookup"><span data-stu-id="798bc-110">Key-per-file configuration provider</span></span>](#key-per-file-configuration-provider)
- [<span data-ttu-id="798bc-111">Proveedor de configuración de memoria</span><span class="sxs-lookup"><span data-stu-id="798bc-111">Memory configuration provider</span></span>](#memory-configuration-provider)

## <a name="file-configuration-provider"></a><span data-ttu-id="798bc-112">Proveedor de configuración de archivo</span><span class="sxs-lookup"><span data-stu-id="798bc-112">File configuration provider</span></span>

<span data-ttu-id="798bc-113"><xref:Microsoft.Extensions.Configuration.FileConfigurationProvider> es la clase base para cargar la configuración del sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="798bc-113"><xref:Microsoft.Extensions.Configuration.FileConfigurationProvider> is the base class for loading configuration from the file system.</span></span> <span data-ttu-id="798bc-114">Los siguientes proveedores de configuración se derivan de `FileConfigurationProvider`:</span><span class="sxs-lookup"><span data-stu-id="798bc-114">The following configuration providers derive from `FileConfigurationProvider`:</span></span>

- [<span data-ttu-id="798bc-115">Proveedor de configuración JSON</span><span class="sxs-lookup"><span data-stu-id="798bc-115">JSON configuration provider</span></span>](#json-configuration-provider)
- [<span data-ttu-id="798bc-116">Proveedor de configuración XML</span><span class="sxs-lookup"><span data-stu-id="798bc-116">XML configuration provider</span></span>](#xml-configuration-provider)
- [<span data-ttu-id="798bc-117">Proveedor de configuración INI</span><span class="sxs-lookup"><span data-stu-id="798bc-117">INI configuration provider</span></span>](#ini-configuration-provider)

### <a name="json-configuration-provider"></a><span data-ttu-id="798bc-118">Proveedor de configuración JSON</span><span class="sxs-lookup"><span data-stu-id="798bc-118">JSON configuration provider</span></span>

<span data-ttu-id="798bc-119">La clase <xref:Microsoft.Extensions.Configuration.Json.JsonConfigurationProvider> carga la configuración desde un archivo JSON.</span><span class="sxs-lookup"><span data-stu-id="798bc-119">The <xref:Microsoft.Extensions.Configuration.Json.JsonConfigurationProvider> class loads configuration from a JSON file.</span></span> <span data-ttu-id="798bc-120">Instale el paquete NuGet [`Microsoft.Extensions.Configuration.Json`](https://www.nuget.org/packages/Microsoft.Extensions.Configuration.Json).</span><span class="sxs-lookup"><span data-stu-id="798bc-120">Install the [`Microsoft.Extensions.Configuration.Json`](https://www.nuget.org/packages/Microsoft.Extensions.Configuration.Json) NuGet package.</span></span>

<span data-ttu-id="798bc-121">Las sobrecargas pueden especificar:</span><span class="sxs-lookup"><span data-stu-id="798bc-121">Overloads can specify:</span></span>

- <span data-ttu-id="798bc-122">Si el archivo es opcional.</span><span class="sxs-lookup"><span data-stu-id="798bc-122">Whether the file is optional</span></span>
- <span data-ttu-id="798bc-123">Si la configuración se recarga si el archivo cambia.</span><span class="sxs-lookup"><span data-stu-id="798bc-123">Whether the configuration is reloaded if the file changes</span></span>

<span data-ttu-id="798bc-124">Observe el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="798bc-124">Consider the following code:</span></span>

:::code language="csharp" source="snippets/configuration/console-json/Program.cs" range="1-39,43-44" highlight="23-29":::

<span data-ttu-id="798bc-125">El código anterior:</span><span class="sxs-lookup"><span data-stu-id="798bc-125">The preceding code:</span></span>

- <span data-ttu-id="798bc-126">Borra todos los proveedores de configuración existentes que se agregaron de forma predeterminada en el método <xref:Microsoft.Extensions.Hosting.Host.CreateDefaultBuilder(System.String[])>.</span><span class="sxs-lookup"><span data-stu-id="798bc-126">Clears all existing configuration providers that were added by default in the <xref:Microsoft.Extensions.Hosting.Host.CreateDefaultBuilder(System.String[])> method.</span></span>
- <span data-ttu-id="798bc-127">Configura el proveedor de configuración de JSON para cargar los archivos *appsettings.json* y *appsettings*.`Environment`.*json* con las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="798bc-127">Configures the JSON configuration provider to load the *appsettings.json* and  *appsettings*.`Environment`.*json* files with the following options:</span></span>
  - <span data-ttu-id="798bc-128">`optional: true`: el archivo es opcional.</span><span class="sxs-lookup"><span data-stu-id="798bc-128">`optional: true`: The file is optional.</span></span>
  - <span data-ttu-id="798bc-129">`reloadOnChange: true`: el archivo se recarga cuando se guardan los cambios.</span><span class="sxs-lookup"><span data-stu-id="798bc-129">`reloadOnChange: true` : The file is reloaded when changes are saved.</span></span>

<span data-ttu-id="798bc-130">La configuración de JSON es reemplazada por la configuración del [proveedor de configuración de variables de entorno](#environment-variable-configuration-provider) y del [proveedor de configuración de línea de comandos](#command-line-configuration-provider).</span><span class="sxs-lookup"><span data-stu-id="798bc-130">The JSON settings are overridden by settings in the [Environment variables configuration provider](#environment-variable-configuration-provider) and the [Command-line configuration provider](#command-line-configuration-provider).</span></span>

<span data-ttu-id="798bc-131">A continuación se muestra un ejemplo de archivo *appsettings.json* con varios valores de configuración:</span><span class="sxs-lookup"><span data-stu-id="798bc-131">An example *appsettings.json* file with various configuration settings follows:</span></span>

:::code language="json" source="snippets/configuration/console-json/appsettings.json":::

<span data-ttu-id="798bc-132">Desde la instancia de <xref:Microsoft.Extensions.Configuration.IConfigurationBuilder>, una vez agregados los proveedores de configuración, puede llamar a <xref:Microsoft.Extensions.Configuration.IConfigurationBuilder.Build?displayProperty=nameWithType> para obtener el objeto <xref:Microsoft.Extensions.Configuration.IConfigurationRoot>.</span><span class="sxs-lookup"><span data-stu-id="798bc-132">From the <xref:Microsoft.Extensions.Configuration.IConfigurationBuilder> instance, after configuration providers have been added you can call <xref:Microsoft.Extensions.Configuration.IConfigurationBuilder.Build?displayProperty=nameWithType> to get the <xref:Microsoft.Extensions.Configuration.IConfigurationRoot> object.</span></span> <span data-ttu-id="798bc-133">La raíz de configuración representa la raíz de una jerarquía de configuración.</span><span class="sxs-lookup"><span data-stu-id="798bc-133">The configuration root represents the root of a configuration hierarchy.</span></span> <span data-ttu-id="798bc-134">Las secciones de la configuración se pueden enlazar a instancias de objetos .NET y, posteriormente, se pueden proporcionar como <xref:Microsoft.Extensions.Options.IOptions%601> mediante la inserción de dependencias.</span><span class="sxs-lookup"><span data-stu-id="798bc-134">Sections from the configuration can be bound to instances of .NET objects, and later provided as <xref:Microsoft.Extensions.Options.IOptions%601> through dependency injection.</span></span>

<span data-ttu-id="798bc-135">Observe la clase `TransientFaultHandlingOptions` definida como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="798bc-135">Consider the `TransientFaultHandlingOptions` class defined as follows:</span></span>

:::code language="csharp" source="snippets/configuration/console-json/TransientFaultHandlingOptions.cs":::

<span data-ttu-id="798bc-136">El código siguiente compila la raíz de la configuración, enlaza una sección al tipo de clase `TransientFaultHandlingOptions` e imprime los valores enlazados en la ventana de la consola:</span><span class="sxs-lookup"><span data-stu-id="798bc-136">The following code builds the configuration root, binds a section to the `TransientFaultHandlingOptions` class type, and prints the bound values to the console window:</span></span>

:::code language="csharp" source="snippets/configuration/console-json/Program.cs" range="31-38":::

<span data-ttu-id="798bc-137">La aplicación escribiría la siguiente salida de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="798bc-137">The application would write the following sample output:</span></span>

:::code language="csharp" source="snippets/configuration/console-json/Program.cs" range="40-42":::

### <a name="xml-configuration-provider"></a><span data-ttu-id="798bc-138">Proveedor de configuración XML</span><span class="sxs-lookup"><span data-stu-id="798bc-138">XML configuration provider</span></span>

<span data-ttu-id="798bc-139">La clase <xref:Microsoft.Extensions.Configuration.Xml.XmlConfigurationProvider> carga la configuración desde un archivo XML en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="798bc-139">The <xref:Microsoft.Extensions.Configuration.Xml.XmlConfigurationProvider> class loads configuration from an XML file at runtime.</span></span> <span data-ttu-id="798bc-140">Instale el paquete NuGet [`Microsoft.Extensions.Configuration.Xml`](https://www.nuget.org/packages/Microsoft.Extensions.Configuration.Xml).</span><span class="sxs-lookup"><span data-stu-id="798bc-140">Install the [`Microsoft.Extensions.Configuration.Xml`](https://www.nuget.org/packages/Microsoft.Extensions.Configuration.Xml) NuGet package.</span></span>

<span data-ttu-id="798bc-141">En el código siguiente se muestra la configuración de archivos XML mediante el proveedor de configuración XML.</span><span class="sxs-lookup"><span data-stu-id="798bc-141">The following code demonstrates configuration of XML files using the XML configuration provider.</span></span>

:::code language="csharp" source="snippets/configuration/console-xml/Program.cs" range="1-34,52,58-59" highlight="23-34":::

<span data-ttu-id="798bc-142">El código anterior:</span><span class="sxs-lookup"><span data-stu-id="798bc-142">The preceding code:</span></span>

- <span data-ttu-id="798bc-143">Borra todos los proveedores de configuración existentes que se agregaron de forma predeterminada en el método <xref:Microsoft.Extensions.Hosting.Host.CreateDefaultBuilder(System.String[])>.</span><span class="sxs-lookup"><span data-stu-id="798bc-143">Clears all existing configuration providers that were added by default in the <xref:Microsoft.Extensions.Hosting.Host.CreateDefaultBuilder(System.String[])> method.</span></span>
- <span data-ttu-id="798bc-144">Configura el proveedor de configuración XML para cargar los archivos *appsettings.xml* y *repeating-example.xml* con las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="798bc-144">Configures the XML configuration provider to load the *appsettings.xml* and *repeating-example.xml* files with the following options:</span></span>
  - <span data-ttu-id="798bc-145">`optional: true`: el archivo es opcional.</span><span class="sxs-lookup"><span data-stu-id="798bc-145">`optional: true`: The file is optional.</span></span>
  - <span data-ttu-id="798bc-146">`reloadOnChange: true`: el archivo se recarga cuando se guardan los cambios.</span><span class="sxs-lookup"><span data-stu-id="798bc-146">`reloadOnChange: true` : The file is reloaded when changes are saved.</span></span>
- <span data-ttu-id="798bc-147">Configura el proveedor de configuración de variables de entorno.</span><span class="sxs-lookup"><span data-stu-id="798bc-147">Configures the environment variables configuration provider.</span></span>
- <span data-ttu-id="798bc-148">Configura el proveedor de configuración de línea de comandos si el valor `args` especificado contiene argumentos.</span><span class="sxs-lookup"><span data-stu-id="798bc-148">Configures the command-line configuration provider if the given `args` contains arguments.</span></span>

<span data-ttu-id="798bc-149">La configuración XML se reemplaza por la configuración del [proveedor de configuración de variables de entorno](#environment-variable-configuration-provider) y del [proveedor de configuración de línea de comandos](#command-line-configuration-provider).</span><span class="sxs-lookup"><span data-stu-id="798bc-149">The XML settings are overridden by settings in the [Environment variables configuration provider](#environment-variable-configuration-provider) and the [Command-line configuration provider](#command-line-configuration-provider).</span></span>

<span data-ttu-id="798bc-150">A continuación se muestra un ejemplo de archivo *appsettings.xml* con varios valores de configuración:</span><span class="sxs-lookup"><span data-stu-id="798bc-150">An example *appsettings.xml* file with various configuration settings follows:</span></span>

:::code language="xml" source="snippets/configuration/console-xml/appsettings.xml":::

<span data-ttu-id="798bc-151">Los elementos de repetición que usan el mismo nombre de elemento funcionan si el atributo `name` se usa para distinguir los elementos:</span><span class="sxs-lookup"><span data-stu-id="798bc-151">Repeating elements that use the same element name work if the `name` attribute is used to distinguish the elements:</span></span>

:::code language="xml" source="snippets/configuration/console-xml/repeating-example.xml":::

<span data-ttu-id="798bc-152">El código siguiente lee el archivo de configuración anterior y muestra las claves y los valores:</span><span class="sxs-lookup"><span data-stu-id="798bc-152">The following code reads the previous configuration file and displays the keys and values:</span></span>

:::code language="csharp" source="snippets/configuration/console-xml/Program.cs" range="36-51":::

<span data-ttu-id="798bc-153">La aplicación escribiría la siguiente salida de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="798bc-153">The application would write the following sample output:</span></span>

:::code language="csharp" source="snippets/configuration/console-xml/Program.cs" range="53-57":::

<span data-ttu-id="798bc-154">Los atributos se pueden usar para suministrar valores:</span><span class="sxs-lookup"><span data-stu-id="798bc-154">Attributes can be used to supply values:</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?>
<configuration>
  <key attribute="value" />
  <section>
    <key attribute="value" />
  </section>
</configuration>
```

<span data-ttu-id="798bc-155">El archivo de configuración anterior carga las siguientes claves con `value`:</span><span class="sxs-lookup"><span data-stu-id="798bc-155">The previous configuration file loads the following keys with `value`:</span></span>

- `key:attribute`
- `section:key:attribute`

### <a name="ini-configuration-provider"></a><span data-ttu-id="798bc-156">Proveedor de configuración INI</span><span class="sxs-lookup"><span data-stu-id="798bc-156">INI configuration provider</span></span>

<span data-ttu-id="798bc-157">La clase <xref:Microsoft.Extensions.Configuration.Ini.IniConfigurationProvider> carga la configuración desde un archivo INI en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="798bc-157">The <xref:Microsoft.Extensions.Configuration.Ini.IniConfigurationProvider> class loads configuration from an INI file at runtime.</span></span> <span data-ttu-id="798bc-158">Instale el paquete NuGet [`Microsoft.Extensions.Configuration.Ini`](https://www.nuget.org/packages/Microsoft.Extensions.Configuration.Ini).</span><span class="sxs-lookup"><span data-stu-id="798bc-158">Install the [`Microsoft.Extensions.Configuration.Ini`](https://www.nuget.org/packages/Microsoft.Extensions.Configuration.Ini)  NuGet package.</span></span>

<span data-ttu-id="798bc-159">En el código siguiente se borran todos los proveedores de configuración y se agregan los `IniConfigurationProvider` con dos archivos INI como origen:</span><span class="sxs-lookup"><span data-stu-id="798bc-159">The following code clears all the configuration providers and adds the `IniConfigurationProvider` with two INI files as the source:</span></span>

:::code language="csharp" source="snippets/configuration/console-ini/Program.cs" range="1-37,44-45" highlight="24-30":::

<span data-ttu-id="798bc-160">A continuación se muestra un ejemplo de archivo *appsettings.ini* con varios valores de configuración:</span><span class="sxs-lookup"><span data-stu-id="798bc-160">An example *appsettings.ini* file with various configuration settings follows:</span></span>

:::code language="ini" source="snippets/configuration/console-ini/appsettings.ini":::

<span data-ttu-id="798bc-161">En el código siguiente se muestran los valores de configuración anteriores escribiéndolo en la ventana de la consola:</span><span class="sxs-lookup"><span data-stu-id="798bc-161">The following code displays the preceding configuration settings by writing them to the console window:</span></span>

:::code language="csharp" source="snippets/configuration/console-ini/Program.cs" range="32-36":::

<span data-ttu-id="798bc-162">La aplicación escribiría la siguiente salida de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="798bc-162">The application would write the following sample output:</span></span>

:::code language="csharp" source="snippets/configuration/console-ini/Program.cs" range="38-43":::

## <a name="environment-variable-configuration-provider"></a><span data-ttu-id="798bc-163">Proveedor de configuración de variables de entorno</span><span class="sxs-lookup"><span data-stu-id="798bc-163">Environment variable configuration provider</span></span>

<span data-ttu-id="798bc-164">Al usar la configuración predeterminada, <xref:Microsoft.Extensions.Configuration.EnvironmentVariables.EnvironmentVariablesConfigurationProvider> carga la configuración de los pares clave-valor de la variable de entorno después de leer *appsettings.json*, *appsettings.* `Environment` *.json* y el Administrador de secretos.</span><span class="sxs-lookup"><span data-stu-id="798bc-164">Using the default configuration, the <xref:Microsoft.Extensions.Configuration.EnvironmentVariables.EnvironmentVariablesConfigurationProvider> loads configuration from environment variable key-value pairs after reading *appsettings.json*, *appsettings.*`Environment`*.json*, and Secret manager.</span></span> <span data-ttu-id="798bc-165">Por lo tanto, los valores de clave que se leen del entorno reemplazan los valores que se leen de *appsettings.json*, *appsettings.* `Environment` *.json* y del administrador de secretos.</span><span class="sxs-lookup"><span data-stu-id="798bc-165">Therefore, key values read from the environment override values read from *appsettings.json*, *appsettings.*`Environment`*.json*, and Secret manager.</span></span>

<span data-ttu-id="798bc-166">El separador `:` no funciona con claves jerárquicas de variables de entorno en todas las plataformas.</span><span class="sxs-lookup"><span data-stu-id="798bc-166">The `:` separator doesn't work with environment variable hierarchical keys on all platforms.</span></span> <span data-ttu-id="798bc-167">Todas las plataformas admiten un carácter de subrayado doble (`__`), que se reemplaza automáticamente por un signo `:`.</span><span class="sxs-lookup"><span data-stu-id="798bc-167">The double underscore (`__`) is automatically replaced by a `:` and is supported by all platforms.</span></span> <span data-ttu-id="798bc-168">Por ejemplo, el separador `:` no es compatible con [Bash](https://linuxhint.com/bash-environment-variables), pero `__` sí.</span><span class="sxs-lookup"><span data-stu-id="798bc-168">For example, the `:` separator is not supported by [Bash](https://linuxhint.com/bash-environment-variables), but `__` is.</span></span>

<span data-ttu-id="798bc-169">Los siguientes comandos `set`:</span><span class="sxs-lookup"><span data-stu-id="798bc-169">The following `set` commands:</span></span>

- <span data-ttu-id="798bc-170">Establecen las claves de entorno y los valores del ejemplo anterior en Windows.</span><span class="sxs-lookup"><span data-stu-id="798bc-170">Set the environment keys and values of the preceding example on Windows.</span></span>
- <span data-ttu-id="798bc-171">Pruebe la configuración cambiando sus valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="798bc-171">Test the settings by changing them from their default values.</span></span> <span data-ttu-id="798bc-172">El comando `dotnet run` debe ejecutarse en el directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="798bc-172">The `dotnet run` command must be run in the project directory.</span></span>

```dotnetcli
set SecretKey="Secret key from environment"
set TransientFaultHandlingOptions__Enabled="true"
set TransientFaultHandlingOptions__AutoRetryDelay="00:00:13"

dotnet run
```

<span data-ttu-id="798bc-173">Los ajustes de configuración del entorno anteriores:</span><span class="sxs-lookup"><span data-stu-id="798bc-173">The preceding environment settings:</span></span>

- <span data-ttu-id="798bc-174">Solo se establecen en procesos iniciados desde la ventana de comandos en la que se establecieron.</span><span class="sxs-lookup"><span data-stu-id="798bc-174">Are only set in processes launched from the command window they were set in.</span></span>
- <span data-ttu-id="798bc-175">No los podrán leer las aplicaciones web que se inician con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="798bc-175">Won't be read by web apps launched with Visual Studio.</span></span>

<span data-ttu-id="798bc-176">Los siguientes comandos [setx](/windows-server/administration/windows-commands/setx) se pueden usar para establecer las claves de entorno y los valores en Windows.</span><span class="sxs-lookup"><span data-stu-id="798bc-176">The following [setx](/windows-server/administration/windows-commands/setx) commands can be used to set the environment keys and values on Windows.</span></span> <span data-ttu-id="798bc-177">A diferencia de `set`, la configuración de `setx` se conserva.</span><span class="sxs-lookup"><span data-stu-id="798bc-177">Unlike `set`, `setx` settings are persisted.</span></span> <span data-ttu-id="798bc-178">`/M` establece la variable en el entorno del sistema.</span><span class="sxs-lookup"><span data-stu-id="798bc-178">`/M` sets the variable in the system environment.</span></span> <span data-ttu-id="798bc-179">Si no se usa el modificador `/M`, se establece una variable de entorno de usuario.</span><span class="sxs-lookup"><span data-stu-id="798bc-179">If the `/M` switch isn't used, a user environment variable is set.</span></span>

```dotnetcli
setx SecretKey "Secret key from setx environment" /M
setx TransientFaultHandlingOptions__Enabled "true" /M
setx TransientFaultHandlingOptions__AutoRetryDelay "00:00:05" /M

dotnet run
```

<span data-ttu-id="798bc-180">Para comprobar que los comandos anteriores invalidan *appsettings.json* y *appsettings.* `Environment` *.json*:</span><span class="sxs-lookup"><span data-stu-id="798bc-180">To test that the preceding commands override *appsettings.json* and *appsettings.*`Environment`*.json*:</span></span>

- <span data-ttu-id="798bc-181">Con Visual Studio: salga y reinicie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="798bc-181">With Visual Studio: Exit and restart Visual Studio.</span></span>
- <span data-ttu-id="798bc-182">Con la CLI: abra una nueva ventana de comandos y escriba `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="798bc-182">With the CLI: Start a new command window and enter `dotnet run`.</span></span>

<span data-ttu-id="798bc-183">Llame a <xref:Microsoft.Extensions.Configuration.EnvironmentVariablesExtensions.AddEnvironmentVariables%2A> con una cadena para especificar un prefijo para las variables de entorno:</span><span class="sxs-lookup"><span data-stu-id="798bc-183">Call <xref:Microsoft.Extensions.Configuration.EnvironmentVariablesExtensions.AddEnvironmentVariables%2A> with a string to specify a prefix for environment variables:</span></span>

:::code language="csharp" source="snippets/configuration/console-env/Program.cs" highlight="21-22":::

<span data-ttu-id="798bc-184">En el código anterior:</span><span class="sxs-lookup"><span data-stu-id="798bc-184">In the preceding code:</span></span>

- <span data-ttu-id="798bc-185">`config.AddEnvironmentVariables(prefix: "CustomPrefix_")` se agrega después de los proveedores de configuración predeterminados.</span><span class="sxs-lookup"><span data-stu-id="798bc-185">`config.AddEnvironmentVariables(prefix: "CustomPrefix_")` is added after the default configuration providers.</span></span> <span data-ttu-id="798bc-186">Para obtener un ejemplo de ordenación de los proveedores de configuración, consulte [Proveedor de configuración XML](#xml-configuration-provider).</span><span class="sxs-lookup"><span data-stu-id="798bc-186">For an example of ordering the configuration providers, see [XML configuration provider](#xml-configuration-provider).</span></span>
- <span data-ttu-id="798bc-187">Las variables de entorno establecidas con el prefijo `CustomPrefix_` invalidan los proveedores de configuración predeterminados.</span><span class="sxs-lookup"><span data-stu-id="798bc-187">Environment variables set with the `CustomPrefix_` prefix override the default configuration providers.</span></span> <span data-ttu-id="798bc-188">Esto incluye las variables de entorno sin el prefijo.</span><span class="sxs-lookup"><span data-stu-id="798bc-188">This includes environment variables without the prefix.</span></span>

<span data-ttu-id="798bc-189">El prefijo se quita cuando se leen los pares clave-valor de configuración.</span><span class="sxs-lookup"><span data-stu-id="798bc-189">The prefix is stripped off when the configuration key-value pairs are read.</span></span>

<span data-ttu-id="798bc-190">Los siguientes comandos prueban el prefijo personalizado:</span><span class="sxs-lookup"><span data-stu-id="798bc-190">The following commands test the custom prefix:</span></span>

```dotnetcli
set CustomPrefix__SecretKey="Secret key with CustomPrefix_ environment"
set CustomPrefix__TransientFaultHandlingOptions__Enabled=true
set CustomPrefix__TransientFaultHandlingOptions__AutoRetryDelay=00:00:21

dotnet run
```

<span data-ttu-id="798bc-191">La configuración predeterminada carga las variables de entorno y los argumentos de la línea de comandos con el prefijo `DOTNET_`.</span><span class="sxs-lookup"><span data-stu-id="798bc-191">The default configuration loads environment variables and command-line arguments prefixed with `DOTNET_`.</span></span> <span data-ttu-id="798bc-192">.NET usa el prefijo `DOTNET_` para la [configuración del host](generic-host.md#host-configuration) y la [configuración de la aplicación](generic-host.md#app-configuration), pero no para la del usuario.</span><span class="sxs-lookup"><span data-stu-id="798bc-192">The `DOTNET_` prefix is used by .NET for [host](generic-host.md#host-configuration) and [app configuration](generic-host.md#app-configuration), but not for user configuration.</span></span>

<span data-ttu-id="798bc-193">Para obtener más información sobre la configuración del host y de la aplicación, consulte el artículo [Host genérico de .NET](generic-host.md).</span><span class="sxs-lookup"><span data-stu-id="798bc-193">For more information on host and app configuration, see [.NET Generic Host](generic-host.md).</span></span>

<span data-ttu-id="798bc-194">En [Azure App Service](https://azure.microsoft.com/services/app-service), seleccione **Nueva configuración de la aplicación** en la página **Configuración > Configuración**.</span><span class="sxs-lookup"><span data-stu-id="798bc-194">On [Azure App Service](https://azure.microsoft.com/services/app-service), select **New application setting** on the **Settings > Configuration** page.</span></span> <span data-ttu-id="798bc-195">Los ajustes de configuración de Azure App Service:</span><span class="sxs-lookup"><span data-stu-id="798bc-195">Azure App Service application settings are:</span></span>

- <span data-ttu-id="798bc-196">Se cifran en reposo y se transmiten a través de un canal cifrado.</span><span class="sxs-lookup"><span data-stu-id="798bc-196">Encrypted at rest and transmitted over an encrypted channel.</span></span>
- <span data-ttu-id="798bc-197">Se exponen como variables de entorno.</span><span class="sxs-lookup"><span data-stu-id="798bc-197">Exposed as environment variables.</span></span>

### <a name="connection-string-prefixes"></a><span data-ttu-id="798bc-198">Prefijos de cadena de conexión</span><span class="sxs-lookup"><span data-stu-id="798bc-198">Connection string prefixes</span></span>

<span data-ttu-id="798bc-199">La API de configuración tiene reglas de procesamiento especiales para cuatro variables de entorno de cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="798bc-199">The Configuration API has special processing rules for four connection string environment variables.</span></span> <span data-ttu-id="798bc-200">Estas cadenas de conexión están implicadas en la configuración de las cadenas de conexión de Azure para el entorno de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="798bc-200">These connection strings are involved in configuring Azure connection strings for the app environment.</span></span> <span data-ttu-id="798bc-201">Las variables de entorno con los prefijos que se muestran en la tabla se cargan en la aplicación con la configuración predeterminada o cuando no se proporciona ningún prefijo a `AddEnvironmentVariables`.</span><span class="sxs-lookup"><span data-stu-id="798bc-201">Environment variables with the prefixes shown in the table are loaded into the app with the default configuration or when no prefix is supplied to `AddEnvironmentVariables`.</span></span>

| <span data-ttu-id="798bc-202">Prefijo de cadena de conexión</span><span class="sxs-lookup"><span data-stu-id="798bc-202">Connection string prefix</span></span> | <span data-ttu-id="798bc-203">Proveedor</span><span class="sxs-lookup"><span data-stu-id="798bc-203">Provider</span></span>                                                                |
|--------------------------|-------------------------------------------------------------------------|
| `CUSTOMCONNSTR_`         | <span data-ttu-id="798bc-204">Proveedor personalizado</span><span class="sxs-lookup"><span data-stu-id="798bc-204">Custom provider</span></span>                                                         |
| `MYSQLCONNSTR_`          | [<span data-ttu-id="798bc-205">MySQL</span><span class="sxs-lookup"><span data-stu-id="798bc-205">MySQL</span></span>](https://www.mysql.com)                                          |
| `SQLAZURECONNSTR_`       | [<span data-ttu-id="798bc-206">Azure SQL Database</span><span class="sxs-lookup"><span data-stu-id="798bc-206">Azure SQL Database</span></span>](https://azure.microsoft.com/services/sql-database) |
| `SQLCONNSTR_`            | [<span data-ttu-id="798bc-207">SQL Server</span><span class="sxs-lookup"><span data-stu-id="798bc-207">SQL Server</span></span>](https://www.microsoft.com/sql-server)                      |

<span data-ttu-id="798bc-208">Cuando una variable de entorno se detecta y carga en la configuración con cualquiera de los cuatro prefijos que se muestran en la tabla:</span><span class="sxs-lookup"><span data-stu-id="798bc-208">When an environment variable is discovered and loaded into configuration with any of the four prefixes shown in the table:</span></span>

- <span data-ttu-id="798bc-209">La clave de configuración se crea al quitar el prefijo de la variable de entorno y al agregar una sección de clave de configuración (`ConnectionStrings`).</span><span class="sxs-lookup"><span data-stu-id="798bc-209">The configuration key is created by removing the environment variable prefix and adding a configuration key section (`ConnectionStrings`).</span></span>
- <span data-ttu-id="798bc-210">Se crea un nuevo par clave-valor de configuración que representa el proveedor de conexión de base de datos (excepto para `CUSTOMCONNSTR_`, que no tiene ningún proveedor indicado).</span><span class="sxs-lookup"><span data-stu-id="798bc-210">A new configuration key-value pair is created that represents the database connection provider (except for `CUSTOMCONNSTR_`, which has no stated provider).</span></span>

| <span data-ttu-id="798bc-211">Clave de variable de entorno</span><span class="sxs-lookup"><span data-stu-id="798bc-211">Environment variable key</span></span> | <span data-ttu-id="798bc-212">Clave de configuración convertida</span><span class="sxs-lookup"><span data-stu-id="798bc-212">Converted configuration key</span></span> | <span data-ttu-id="798bc-213">Entrada de configuración del proveedor</span><span class="sxs-lookup"><span data-stu-id="798bc-213">Provider configuration entry</span></span>                                                    |
|--------------------------|-----------------------------|---------------------------------------------------------------------------------|
| `CUSTOMCONNSTR_{KEY}`    | `ConnectionStrings:{KEY}`   | <span data-ttu-id="798bc-214">Entrada de configuración no creada.</span><span class="sxs-lookup"><span data-stu-id="798bc-214">Configuration entry not created.</span></span>                                                |
| `MYSQLCONNSTR_{KEY}`     | `ConnectionStrings:{KEY}`   | <span data-ttu-id="798bc-215">Clave: `ConnectionStrings:{KEY}_ProviderName`:</span><span class="sxs-lookup"><span data-stu-id="798bc-215">Key: `ConnectionStrings:{KEY}_ProviderName`:</span></span><br><span data-ttu-id="798bc-216">Valor: `MySql.Data.MySqlClient`</span><span class="sxs-lookup"><span data-stu-id="798bc-216">Value: `MySql.Data.MySqlClient`</span></span> |
| `SQLAZURECONNSTR_{KEY}`  | `ConnectionStrings:{KEY}`   | <span data-ttu-id="798bc-217">Clave: `ConnectionStrings:{KEY}_ProviderName`:</span><span class="sxs-lookup"><span data-stu-id="798bc-217">Key: `ConnectionStrings:{KEY}_ProviderName`:</span></span><br><span data-ttu-id="798bc-218">Valor: `System.Data.SqlClient`</span><span class="sxs-lookup"><span data-stu-id="798bc-218">Value: `System.Data.SqlClient`</span></span>  |
| `SQLCONNSTR_{KEY}`       | `ConnectionStrings:{KEY}`   | <span data-ttu-id="798bc-219">Clave: `ConnectionStrings:{KEY}_ProviderName`:</span><span class="sxs-lookup"><span data-stu-id="798bc-219">Key: `ConnectionStrings:{KEY}_ProviderName`:</span></span><br><span data-ttu-id="798bc-220">Valor: `System.Data.SqlClient`</span><span class="sxs-lookup"><span data-stu-id="798bc-220">Value: `System.Data.SqlClient`</span></span>  |

### <a name="environment-variables-set-in-launchsettingsjson"></a><span data-ttu-id="798bc-221">Variables de entorno configuradas en launchSettings.json</span><span class="sxs-lookup"><span data-stu-id="798bc-221">Environment variables set in launchSettings.json</span></span>

<span data-ttu-id="798bc-222">Las variables de entorno configuradas en *launchSettings.json* invalidan aquellas configuradas en el entorno del sistema.</span><span class="sxs-lookup"><span data-stu-id="798bc-222">Environment variables set in *launchSettings.json* override those set in the system environment.</span></span>

## <a name="command-line-configuration-provider"></a><span data-ttu-id="798bc-223">Proveedor de configuración de línea de comandos</span><span class="sxs-lookup"><span data-stu-id="798bc-223">Command-line configuration provider</span></span>

<span data-ttu-id="798bc-224">Si se usa la configuración predeterminada, <xref:Microsoft.Extensions.Configuration.CommandLine.CommandLineConfigurationProvider> carga la configuración de los pares de clave-valor de argumento de la línea de comandos después de los siguientes orígenes de configuración:</span><span class="sxs-lookup"><span data-stu-id="798bc-224">Using the default configuration, the <xref:Microsoft.Extensions.Configuration.CommandLine.CommandLineConfigurationProvider> loads configuration from command-line argument key-value pairs after the following configuration sources:</span></span>

- <span data-ttu-id="798bc-225">Archivos *appsettings.json* y *appsettings*.`Environment`.*json*.</span><span class="sxs-lookup"><span data-stu-id="798bc-225">*appsettings.json* and *appsettings*.`Environment`.*json* files.</span></span>
- <span data-ttu-id="798bc-226">Secretos de aplicación (administrador de secretos) en el entorno `Development`.</span><span class="sxs-lookup"><span data-stu-id="798bc-226">App secrets (Secret Manager) in the `Development` environment.</span></span>
- <span data-ttu-id="798bc-227">Variables de entorno.</span><span class="sxs-lookup"><span data-stu-id="798bc-227">Environment variables.</span></span>

<span data-ttu-id="798bc-228">De forma predeterminada, los valores de configuración establecidos en la línea de comandos reemplazan los valores de configuración establecidos con el resto de proveedores de configuración.</span><span class="sxs-lookup"><span data-stu-id="798bc-228">By default, configuration values set on the command line override configuration values set with all the other configuration providers.</span></span>

### <a name="command-line-arguments"></a><span data-ttu-id="798bc-229">Argumentos de la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="798bc-229">Command-line arguments</span></span>

<span data-ttu-id="798bc-230">El comando siguiente establece las claves y los valores mediante `=`:</span><span class="sxs-lookup"><span data-stu-id="798bc-230">The following command sets keys and values using `=`:</span></span>

```dotnetcli
dotnet run SecretKey="Secret key from command line"
```

<span data-ttu-id="798bc-231">El comando siguiente establece las claves y los valores mediante `/`:</span><span class="sxs-lookup"><span data-stu-id="798bc-231">The following command sets keys and values using `/`:</span></span>

```dotnetcli
dotnet run /SecretKey "Secret key set from forward slash"
```

<span data-ttu-id="798bc-232">El comando siguiente establece las claves y los valores mediante `--`:</span><span class="sxs-lookup"><span data-stu-id="798bc-232">The following command sets keys and values using `--`:</span></span>

```dotnetcli
dotnet run --SecretKey "Secret key set from double hyphen"
```

<span data-ttu-id="798bc-233">El valor de la clave:</span><span class="sxs-lookup"><span data-stu-id="798bc-233">The key value:</span></span>

- <span data-ttu-id="798bc-234">Debe seguir a un signo `=`, o bien la clave debe tener un prefijo `--` o `/` cuando el valor sigue a un espacio.</span><span class="sxs-lookup"><span data-stu-id="798bc-234">Must follow `=`, or the key must have a prefix of `--` or `/` when the value follows a space.</span></span>
- <span data-ttu-id="798bc-235">No es necesario si se usa `=`.</span><span class="sxs-lookup"><span data-stu-id="798bc-235">Isn't required if `=` is used.</span></span> <span data-ttu-id="798bc-236">Por ejemplo: `SomeKey=`.</span><span class="sxs-lookup"><span data-stu-id="798bc-236">For example, `SomeKey=`.</span></span>

<span data-ttu-id="798bc-237">Dentro del mismo comando, no mezcle pares clave-valor de argumento de la línea de comandos que usan `=` con pares de clave-valor que usan un espacio.</span><span class="sxs-lookup"><span data-stu-id="798bc-237">Within the same command, don't mix command-line argument key-value pairs that use `=` with key-value pairs that use a space.</span></span>

## <a name="key-per-file-configuration-provider"></a><span data-ttu-id="798bc-238">Proveedor de configuración de clave por archivo</span><span class="sxs-lookup"><span data-stu-id="798bc-238">Key-per-file configuration provider</span></span>

<span data-ttu-id="798bc-239"><xref:Microsoft.Extensions.Configuration.KeyPerFile.KeyPerFileConfigurationProvider> usa los archivos de un directorio como pares clave-valor de configuración.</span><span class="sxs-lookup"><span data-stu-id="798bc-239">The <xref:Microsoft.Extensions.Configuration.KeyPerFile.KeyPerFileConfigurationProvider> uses a directory's files as configuration key-value pairs.</span></span> <span data-ttu-id="798bc-240">La clave es el nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="798bc-240">The key is the file name.</span></span> <span data-ttu-id="798bc-241">El valor es el contenido del archivo.</span><span class="sxs-lookup"><span data-stu-id="798bc-241">The value is the file's contents.</span></span> <span data-ttu-id="798bc-242">El proveedor de configuración de clave por archivo se usa en escenarios de hospedaje de Docker.</span><span class="sxs-lookup"><span data-stu-id="798bc-242">The Key-per-file configuration provider is used in Docker hosting scenarios.</span></span>

<span data-ttu-id="798bc-243">Para activar la configuración de clave por archivo, llame al método de extensión <xref:Microsoft.Extensions.Configuration.KeyPerFileConfigurationBuilderExtensions.AddKeyPerFile%2A> en una instancia de <xref:Microsoft.Extensions.Configuration.ConfigurationBuilder>.</span><span class="sxs-lookup"><span data-stu-id="798bc-243">To activate key-per-file configuration, call the <xref:Microsoft.Extensions.Configuration.KeyPerFileConfigurationBuilderExtensions.AddKeyPerFile%2A> extension method on an instance of <xref:Microsoft.Extensions.Configuration.ConfigurationBuilder>.</span></span> <span data-ttu-id="798bc-244">La ruta de acceso `directoryPath` a los archivos debe ser una ruta de acceso absoluta.</span><span class="sxs-lookup"><span data-stu-id="798bc-244">The `directoryPath` to the files must be an absolute path.</span></span>

<span data-ttu-id="798bc-245">Las sobrecargas permiten especificar:</span><span class="sxs-lookup"><span data-stu-id="798bc-245">Overloads permit specifying:</span></span>

- <span data-ttu-id="798bc-246">Un delegado `Action<KeyPerFileConfigurationSource>` que configura el origen.</span><span class="sxs-lookup"><span data-stu-id="798bc-246">An `Action<KeyPerFileConfigurationSource>` delegate that configures the source.</span></span>
- <span data-ttu-id="798bc-247">Si el directorio es opcional y la ruta de acceso al directorio.</span><span class="sxs-lookup"><span data-stu-id="798bc-247">Whether the directory is optional and the path to the directory.</span></span>

<span data-ttu-id="798bc-248">El carácter de subrayado doble (`__`) se usa como delimitador de claves de configuración en los nombres de archivo.</span><span class="sxs-lookup"><span data-stu-id="798bc-248">The double-underscore (`__`) is used as a configuration key delimiter in file names.</span></span> <span data-ttu-id="798bc-249">Por ejemplo, el nombre de archivo `Logging__LogLevel__System` genera la clave de configuración `Logging:LogLevel:System`.</span><span class="sxs-lookup"><span data-stu-id="798bc-249">For example, the file name `Logging__LogLevel__System` produces the configuration key `Logging:LogLevel:System`.</span></span>

<span data-ttu-id="798bc-250">Llame a `ConfigureAppConfiguration` cuando cree el host para especificar la configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="798bc-250">Call `ConfigureAppConfiguration` when building the host to specify the app's configuration:</span></span>

```csharp
.ConfigureAppConfiguration((_, configuration) =>
{
    var path = Path.Combine(
        Directory.GetCurrentDirectory(), "path/to/files");

    configuration.AddKeyPerFile(directoryPath: path, optional: true);
})
```

## <a name="memory-configuration-provider"></a><span data-ttu-id="798bc-251">Proveedor de configuración de memoria</span><span class="sxs-lookup"><span data-stu-id="798bc-251">Memory configuration provider</span></span>

<span data-ttu-id="798bc-252"><xref:Microsoft.Extensions.Configuration.Memory.MemoryConfigurationProvider> usa una colección en memoria como pares clave-valor de configuración.</span><span class="sxs-lookup"><span data-stu-id="798bc-252">The <xref:Microsoft.Extensions.Configuration.Memory.MemoryConfigurationProvider> uses an in-memory collection as configuration key-value pairs.</span></span>

<span data-ttu-id="798bc-253">El código siguiente agrega una colección en memoria al sistema de configuración:</span><span class="sxs-lookup"><span data-stu-id="798bc-253">The following code adds a memory collection to the configuration system:</span></span>

:::code language="csharp" source="snippets/configuration/console-memory/Program.cs" highlight="22-29":::

<span data-ttu-id="798bc-254">En el código anterior, <xref:Microsoft.Extensions.Configuration.MemoryConfigurationBuilderExtensions.AddInMemoryCollection(Microsoft.Extensions.Configuration.IConfigurationBuilder,System.Collections.Generic.IEnumerable{System.Collections.Generic.KeyValuePair{System.String,System.String}})?displayProperty=nameWithType> agrega el proveedor de memoria después de los proveedores de configuración predeterminados.</span><span class="sxs-lookup"><span data-stu-id="798bc-254">In the preceding code, <xref:Microsoft.Extensions.Configuration.MemoryConfigurationBuilderExtensions.AddInMemoryCollection(Microsoft.Extensions.Configuration.IConfigurationBuilder,System.Collections.Generic.IEnumerable{System.Collections.Generic.KeyValuePair{System.String,System.String}})?displayProperty=nameWithType> adds the memory provider after the default configuration providers.</span></span> <span data-ttu-id="798bc-255">Para obtener un ejemplo de ordenación de los proveedores de configuración, consulte [Proveedor de configuración XML](#xml-configuration-provider).</span><span class="sxs-lookup"><span data-stu-id="798bc-255">For an example of ordering the configuration providers, see [XML configuration provider](#xml-configuration-provider).</span></span>

## <a name="see-also"></a><span data-ttu-id="798bc-256">Vea también</span><span class="sxs-lookup"><span data-stu-id="798bc-256">See also</span></span>

- [<span data-ttu-id="798bc-257">Configuración en .NET</span><span class="sxs-lookup"><span data-stu-id="798bc-257">Configuration in .NET</span></span>](configuration.md)
- [<span data-ttu-id="798bc-258">Host genérico de .NET</span><span class="sxs-lookup"><span data-stu-id="798bc-258">.NET Generic Host</span></span>](generic-host.md)
- [<span data-ttu-id="798bc-259">Implementación de un proveedor de configuración personalizado</span><span class="sxs-lookup"><span data-stu-id="798bc-259">Implement a custom configuration provider</span></span>](custom-configuration-provider.md)
