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
# <a name="configuration-providers-in-net"></a>Proveedores de configuración en .NET

La configuración en .NET se realiza con proveedores de configuración. Hay varios tipos de proveedores que dependen de varios orígenes de configuración. En este artículo se detallan los distintos proveedores de configuración y sus orígenes correspondientes.

- [Proveedor de configuración de archivo](#file-configuration-provider)
- [Proveedor de configuración de variables de entorno](#environment-variable-configuration-provider)
- [Proveedor de configuración de línea de comandos](#command-line-configuration-provider)
- [Proveedor de configuración de clave por archivo](#key-per-file-configuration-provider)
- [Proveedor de configuración de memoria](#memory-configuration-provider)

## <a name="file-configuration-provider"></a>Proveedor de configuración de archivo

<xref:Microsoft.Extensions.Configuration.FileConfigurationProvider> es la clase base para cargar la configuración del sistema de archivos. Los siguientes proveedores de configuración se derivan de `FileConfigurationProvider`:

- [Proveedor de configuración JSON](#json-configuration-provider)
- [Proveedor de configuración XML](#xml-configuration-provider)
- [Proveedor de configuración INI](#ini-configuration-provider)

### <a name="json-configuration-provider"></a>Proveedor de configuración JSON

La clase <xref:Microsoft.Extensions.Configuration.Json.JsonConfigurationProvider> carga la configuración desde un archivo JSON. Instale el paquete NuGet [`Microsoft.Extensions.Configuration.Json`](https://www.nuget.org/packages/Microsoft.Extensions.Configuration.Json).

Las sobrecargas pueden especificar:

- Si el archivo es opcional.
- Si la configuración se recarga si el archivo cambia.

Observe el código siguiente:

:::code language="csharp" source="snippets/configuration/console-json/Program.cs" range="1-39,43-44" highlight="23-29":::

El código anterior:

- Borra todos los proveedores de configuración existentes que se agregaron de forma predeterminada en el método <xref:Microsoft.Extensions.Hosting.Host.CreateDefaultBuilder(System.String[])>.
- Configura el proveedor de configuración de JSON para cargar los archivos *appsettings.json* y *appsettings*.`Environment`.*json* con las siguientes opciones:
  - `optional: true`: el archivo es opcional.
  - `reloadOnChange: true`: el archivo se recarga cuando se guardan los cambios.

La configuración de JSON es reemplazada por la configuración del [proveedor de configuración de variables de entorno](#environment-variable-configuration-provider) y del [proveedor de configuración de línea de comandos](#command-line-configuration-provider).

A continuación se muestra un ejemplo de archivo *appsettings.json* con varios valores de configuración:

:::code language="json" source="snippets/configuration/console-json/appsettings.json":::

Desde la instancia de <xref:Microsoft.Extensions.Configuration.IConfigurationBuilder>, una vez agregados los proveedores de configuración, puede llamar a <xref:Microsoft.Extensions.Configuration.IConfigurationBuilder.Build?displayProperty=nameWithType> para obtener el objeto <xref:Microsoft.Extensions.Configuration.IConfigurationRoot>. La raíz de configuración representa la raíz de una jerarquía de configuración. Las secciones de la configuración se pueden enlazar a instancias de objetos .NET y, posteriormente, se pueden proporcionar como <xref:Microsoft.Extensions.Options.IOptions%601> mediante la inserción de dependencias.

Observe la clase `TransientFaultHandlingOptions` definida como se indica a continuación:

:::code language="csharp" source="snippets/configuration/console-json/TransientFaultHandlingOptions.cs":::

El código siguiente compila la raíz de la configuración, enlaza una sección al tipo de clase `TransientFaultHandlingOptions` e imprime los valores enlazados en la ventana de la consola:

:::code language="csharp" source="snippets/configuration/console-json/Program.cs" range="31-38":::

La aplicación escribiría la siguiente salida de ejemplo:

:::code language="csharp" source="snippets/configuration/console-json/Program.cs" range="40-42":::

### <a name="xml-configuration-provider"></a>Proveedor de configuración XML

La clase <xref:Microsoft.Extensions.Configuration.Xml.XmlConfigurationProvider> carga la configuración desde un archivo XML en tiempo de ejecución. Instale el paquete NuGet [`Microsoft.Extensions.Configuration.Xml`](https://www.nuget.org/packages/Microsoft.Extensions.Configuration.Xml).

En el código siguiente se muestra la configuración de archivos XML mediante el proveedor de configuración XML.

:::code language="csharp" source="snippets/configuration/console-xml/Program.cs" range="1-34,52,58-59" highlight="23-34":::

El código anterior:

- Borra todos los proveedores de configuración existentes que se agregaron de forma predeterminada en el método <xref:Microsoft.Extensions.Hosting.Host.CreateDefaultBuilder(System.String[])>.
- Configura el proveedor de configuración XML para cargar los archivos *appsettings.xml* y *repeating-example.xml* con las siguientes opciones:
  - `optional: true`: el archivo es opcional.
  - `reloadOnChange: true`: el archivo se recarga cuando se guardan los cambios.
- Configura el proveedor de configuración de variables de entorno.
- Configura el proveedor de configuración de línea de comandos si el valor `args` especificado contiene argumentos.

La configuración XML se reemplaza por la configuración del [proveedor de configuración de variables de entorno](#environment-variable-configuration-provider) y del [proveedor de configuración de línea de comandos](#command-line-configuration-provider).

A continuación se muestra un ejemplo de archivo *appsettings.xml* con varios valores de configuración:

:::code language="xml" source="snippets/configuration/console-xml/appsettings.xml":::

Los elementos de repetición que usan el mismo nombre de elemento funcionan si el atributo `name` se usa para distinguir los elementos:

:::code language="xml" source="snippets/configuration/console-xml/repeating-example.xml":::

El código siguiente lee el archivo de configuración anterior y muestra las claves y los valores:

:::code language="csharp" source="snippets/configuration/console-xml/Program.cs" range="36-51":::

La aplicación escribiría la siguiente salida de ejemplo:

:::code language="csharp" source="snippets/configuration/console-xml/Program.cs" range="53-57":::

Los atributos se pueden usar para suministrar valores:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<configuration>
  <key attribute="value" />
  <section>
    <key attribute="value" />
  </section>
</configuration>
```

El archivo de configuración anterior carga las siguientes claves con `value`:

- `key:attribute`
- `section:key:attribute`

### <a name="ini-configuration-provider"></a>Proveedor de configuración INI

La clase <xref:Microsoft.Extensions.Configuration.Ini.IniConfigurationProvider> carga la configuración desde un archivo INI en tiempo de ejecución. Instale el paquete NuGet [`Microsoft.Extensions.Configuration.Ini`](https://www.nuget.org/packages/Microsoft.Extensions.Configuration.Ini).

En el código siguiente se borran todos los proveedores de configuración y se agregan los `IniConfigurationProvider` con dos archivos INI como origen:

:::code language="csharp" source="snippets/configuration/console-ini/Program.cs" range="1-37,44-45" highlight="24-30":::

A continuación se muestra un ejemplo de archivo *appsettings.ini* con varios valores de configuración:

:::code language="ini" source="snippets/configuration/console-ini/appsettings.ini":::

En el código siguiente se muestran los valores de configuración anteriores escribiéndolo en la ventana de la consola:

:::code language="csharp" source="snippets/configuration/console-ini/Program.cs" range="32-36":::

La aplicación escribiría la siguiente salida de ejemplo:

:::code language="csharp" source="snippets/configuration/console-ini/Program.cs" range="38-43":::

## <a name="environment-variable-configuration-provider"></a>Proveedor de configuración de variables de entorno

Al usar la configuración predeterminada, <xref:Microsoft.Extensions.Configuration.EnvironmentVariables.EnvironmentVariablesConfigurationProvider> carga la configuración de los pares clave-valor de la variable de entorno después de leer *appsettings.json*, *appsettings.* `Environment` *.json* y el Administrador de secretos. Por lo tanto, los valores de clave que se leen del entorno reemplazan los valores que se leen de *appsettings.json*, *appsettings.* `Environment` *.json* y del administrador de secretos.

El separador `:` no funciona con claves jerárquicas de variables de entorno en todas las plataformas. Todas las plataformas admiten un carácter de subrayado doble (`__`), que se reemplaza automáticamente por un signo `:`. Por ejemplo, el separador `:` no es compatible con [Bash](https://linuxhint.com/bash-environment-variables), pero `__` sí.

Los siguientes comandos `set`:

- Establecen las claves de entorno y los valores del ejemplo anterior en Windows.
- Pruebe la configuración cambiando sus valores predeterminados. El comando `dotnet run` debe ejecutarse en el directorio del proyecto.

```dotnetcli
set SecretKey="Secret key from environment"
set TransientFaultHandlingOptions__Enabled="true"
set TransientFaultHandlingOptions__AutoRetryDelay="00:00:13"

dotnet run
```

Los ajustes de configuración del entorno anteriores:

- Solo se establecen en procesos iniciados desde la ventana de comandos en la que se establecieron.
- No los podrán leer las aplicaciones web que se inician con Visual Studio.

Los siguientes comandos [setx](/windows-server/administration/windows-commands/setx) se pueden usar para establecer las claves de entorno y los valores en Windows. A diferencia de `set`, la configuración de `setx` se conserva. `/M` establece la variable en el entorno del sistema. Si no se usa el modificador `/M`, se establece una variable de entorno de usuario.

```dotnetcli
setx SecretKey "Secret key from setx environment" /M
setx TransientFaultHandlingOptions__Enabled "true" /M
setx TransientFaultHandlingOptions__AutoRetryDelay "00:00:05" /M

dotnet run
```

Para comprobar que los comandos anteriores invalidan *appsettings.json* y *appsettings.* `Environment` *.json*:

- Con Visual Studio: salga y reinicie Visual Studio.
- Con la CLI: abra una nueva ventana de comandos y escriba `dotnet run`.

Llame a <xref:Microsoft.Extensions.Configuration.EnvironmentVariablesExtensions.AddEnvironmentVariables%2A> con una cadena para especificar un prefijo para las variables de entorno:

:::code language="csharp" source="snippets/configuration/console-env/Program.cs" highlight="21-22":::

En el código anterior:

- `config.AddEnvironmentVariables(prefix: "CustomPrefix_")` se agrega después de los proveedores de configuración predeterminados. Para obtener un ejemplo de ordenación de los proveedores de configuración, consulte [Proveedor de configuración XML](#xml-configuration-provider).
- Las variables de entorno establecidas con el prefijo `CustomPrefix_` invalidan los proveedores de configuración predeterminados. Esto incluye las variables de entorno sin el prefijo.

El prefijo se quita cuando se leen los pares clave-valor de configuración.

Los siguientes comandos prueban el prefijo personalizado:

```dotnetcli
set CustomPrefix__SecretKey="Secret key with CustomPrefix_ environment"
set CustomPrefix__TransientFaultHandlingOptions__Enabled=true
set CustomPrefix__TransientFaultHandlingOptions__AutoRetryDelay=00:00:21

dotnet run
```

La configuración predeterminada carga las variables de entorno y los argumentos de la línea de comandos con el prefijo `DOTNET_`. .NET usa el prefijo `DOTNET_` para la [configuración del host](generic-host.md#host-configuration) y la [configuración de la aplicación](generic-host.md#app-configuration), pero no para la del usuario.

Para obtener más información sobre la configuración del host y de la aplicación, consulte el artículo [Host genérico de .NET](generic-host.md).

En [Azure App Service](https://azure.microsoft.com/services/app-service), seleccione **Nueva configuración de la aplicación** en la página **Configuración > Configuración**. Los ajustes de configuración de Azure App Service:

- Se cifran en reposo y se transmiten a través de un canal cifrado.
- Se exponen como variables de entorno.

### <a name="connection-string-prefixes"></a>Prefijos de cadena de conexión

La API de configuración tiene reglas de procesamiento especiales para cuatro variables de entorno de cadena de conexión. Estas cadenas de conexión están implicadas en la configuración de las cadenas de conexión de Azure para el entorno de la aplicación. Las variables de entorno con los prefijos que se muestran en la tabla se cargan en la aplicación con la configuración predeterminada o cuando no se proporciona ningún prefijo a `AddEnvironmentVariables`.

| Prefijo de cadena de conexión | Proveedor                                                                |
|--------------------------|-------------------------------------------------------------------------|
| `CUSTOMCONNSTR_`         | Proveedor personalizado                                                         |
| `MYSQLCONNSTR_`          | [MySQL](https://www.mysql.com)                                          |
| `SQLAZURECONNSTR_`       | [Azure SQL Database](https://azure.microsoft.com/services/sql-database) |
| `SQLCONNSTR_`            | [SQL Server](https://www.microsoft.com/sql-server)                      |

Cuando una variable de entorno se detecta y carga en la configuración con cualquiera de los cuatro prefijos que se muestran en la tabla:

- La clave de configuración se crea al quitar el prefijo de la variable de entorno y al agregar una sección de clave de configuración (`ConnectionStrings`).
- Se crea un nuevo par clave-valor de configuración que representa el proveedor de conexión de base de datos (excepto para `CUSTOMCONNSTR_`, que no tiene ningún proveedor indicado).

| Clave de variable de entorno | Clave de configuración convertida | Entrada de configuración del proveedor                                                    |
|--------------------------|-----------------------------|---------------------------------------------------------------------------------|
| `CUSTOMCONNSTR_{KEY}`    | `ConnectionStrings:{KEY}`   | Entrada de configuración no creada.                                                |
| `MYSQLCONNSTR_{KEY}`     | `ConnectionStrings:{KEY}`   | Clave: `ConnectionStrings:{KEY}_ProviderName`:<br>Valor: `MySql.Data.MySqlClient` |
| `SQLAZURECONNSTR_{KEY}`  | `ConnectionStrings:{KEY}`   | Clave: `ConnectionStrings:{KEY}_ProviderName`:<br>Valor: `System.Data.SqlClient`  |
| `SQLCONNSTR_{KEY}`       | `ConnectionStrings:{KEY}`   | Clave: `ConnectionStrings:{KEY}_ProviderName`:<br>Valor: `System.Data.SqlClient`  |

### <a name="environment-variables-set-in-launchsettingsjson"></a>Variables de entorno configuradas en launchSettings.json

Las variables de entorno configuradas en *launchSettings.json* invalidan aquellas configuradas en el entorno del sistema.

## <a name="command-line-configuration-provider"></a>Proveedor de configuración de línea de comandos

Si se usa la configuración predeterminada, <xref:Microsoft.Extensions.Configuration.CommandLine.CommandLineConfigurationProvider> carga la configuración de los pares de clave-valor de argumento de la línea de comandos después de los siguientes orígenes de configuración:

- Archivos *appsettings.json* y *appsettings*.`Environment`.*json*.
- Secretos de aplicación (administrador de secretos) en el entorno `Development`.
- Variables de entorno.

De forma predeterminada, los valores de configuración establecidos en la línea de comandos reemplazan los valores de configuración establecidos con el resto de proveedores de configuración.

### <a name="command-line-arguments"></a>Argumentos de la línea de comandos

El comando siguiente establece las claves y los valores mediante `=`:

```dotnetcli
dotnet run SecretKey="Secret key from command line"
```

El comando siguiente establece las claves y los valores mediante `/`:

```dotnetcli
dotnet run /SecretKey "Secret key set from forward slash"
```

El comando siguiente establece las claves y los valores mediante `--`:

```dotnetcli
dotnet run --SecretKey "Secret key set from double hyphen"
```

El valor de la clave:

- Debe seguir a un signo `=`, o bien la clave debe tener un prefijo `--` o `/` cuando el valor sigue a un espacio.
- No es necesario si se usa `=`. Por ejemplo: `SomeKey=`.

Dentro del mismo comando, no mezcle pares clave-valor de argumento de la línea de comandos que usan `=` con pares de clave-valor que usan un espacio.

## <a name="key-per-file-configuration-provider"></a>Proveedor de configuración de clave por archivo

<xref:Microsoft.Extensions.Configuration.KeyPerFile.KeyPerFileConfigurationProvider> usa los archivos de un directorio como pares clave-valor de configuración. La clave es el nombre de archivo. El valor es el contenido del archivo. El proveedor de configuración de clave por archivo se usa en escenarios de hospedaje de Docker.

Para activar la configuración de clave por archivo, llame al método de extensión <xref:Microsoft.Extensions.Configuration.KeyPerFileConfigurationBuilderExtensions.AddKeyPerFile%2A> en una instancia de <xref:Microsoft.Extensions.Configuration.ConfigurationBuilder>. La ruta de acceso `directoryPath` a los archivos debe ser una ruta de acceso absoluta.

Las sobrecargas permiten especificar:

- Un delegado `Action<KeyPerFileConfigurationSource>` que configura el origen.
- Si el directorio es opcional y la ruta de acceso al directorio.

El carácter de subrayado doble (`__`) se usa como delimitador de claves de configuración en los nombres de archivo. Por ejemplo, el nombre de archivo `Logging__LogLevel__System` genera la clave de configuración `Logging:LogLevel:System`.

Llame a `ConfigureAppConfiguration` cuando cree el host para especificar la configuración de la aplicación:

```csharp
.ConfigureAppConfiguration((_, configuration) =>
{
    var path = Path.Combine(
        Directory.GetCurrentDirectory(), "path/to/files");

    configuration.AddKeyPerFile(directoryPath: path, optional: true);
})
```

## <a name="memory-configuration-provider"></a>Proveedor de configuración de memoria

<xref:Microsoft.Extensions.Configuration.Memory.MemoryConfigurationProvider> usa una colección en memoria como pares clave-valor de configuración.

El código siguiente agrega una colección en memoria al sistema de configuración:

:::code language="csharp" source="snippets/configuration/console-memory/Program.cs" highlight="22-29":::

En el código anterior, <xref:Microsoft.Extensions.Configuration.MemoryConfigurationBuilderExtensions.AddInMemoryCollection(Microsoft.Extensions.Configuration.IConfigurationBuilder,System.Collections.Generic.IEnumerable{System.Collections.Generic.KeyValuePair{System.String,System.String}})?displayProperty=nameWithType> agrega el proveedor de memoria después de los proveedores de configuración predeterminados. Para obtener un ejemplo de ordenación de los proveedores de configuración, consulte [Proveedor de configuración XML](#xml-configuration-provider).

## <a name="see-also"></a>Vea también

- [Configuración en .NET](configuration.md)
- [Host genérico de .NET](generic-host.md)
- [Implementación de un proveedor de configuración personalizado](custom-configuration-provider.md)
