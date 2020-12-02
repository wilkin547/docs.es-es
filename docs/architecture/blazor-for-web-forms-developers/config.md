---
title: Configuración de la aplicación
description: Obtenga información sobre cómo configurar Blazor aplicaciones sin usar ConfigurationManager.
author: csharpfritz
ms.author: jefritz
no-loc:
- Blazor
ms.date: 11/20/2020
ms.openlocfilehash: 360d9077bc981a2e9875bb1f86b49c0029424d6e
ms.sourcegitcommit: 2f485e721f7f34b87856a51181b5b56624b31fd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2020
ms.locfileid: "96509798"
---
# <a name="app-configuration"></a>Configuración de la aplicación

La forma principal de cargar la configuración de la aplicación en formularios Web Forms es con entradas del archivo de *web.config* &mdash; en el servidor o en un archivo de configuración relacionado al que hace referencia *web.config*. Puede usar el objeto estático `ConfigurationManager` para interactuar con la configuración de la aplicación, las cadenas de conexión del repositorio de datos y otros proveedores de configuración extendidos que se agregan a la aplicación. Es habitual ver las interacciones con la configuración de la aplicación, tal como se muestra en el código siguiente:

```csharp
var configurationValue = ConfigurationManager.AppSettings["ConfigurationSettingName"];
var connectionString = ConfigurationManager.ConnectionStrings["MyDatabaseConnectionName"].ConnectionString;
```

Con ASP.NET Core y el lado servidor Blazor , el archivo de *web.config* puede estar presente si la aplicación se hospeda en un servidor IIS de Windows. Sin embargo, no hay ninguna `ConfigurationManager` interacción con esta configuración y puede recibir una configuración de aplicación más estructurada de otros orígenes. Echemos un vistazo a cómo se recopila la configuración y cómo puede seguir accediendo a la información de configuración desde un archivo de *web.config* .

## <a name="configuration-sources"></a>Orígenes de configuración

ASP.NET Core reconoce que hay muchos orígenes de configuración que puede usar para la aplicación. El marco de trabajo intenta ofrecerle lo mejor de estas características de forma predeterminada. La configuración se lee y se agrega desde estos diversos orígenes mediante ASP.NET Core. Los valores cargados posteriormente para la misma clave de configuración tienen prioridad sobre los valores anteriores.

ASP.NET Core se diseñó para ser compatible con la nube y para facilitar la configuración de las aplicaciones para operadores y desarrolladores. ASP.NET Core es compatible con el entorno y sabe si se está ejecutando en `Production` su `Development` entorno de o. El indicador de entorno se establece en la `ASPNETCORE_ENVIRONMENT` variable de entorno del sistema. Si no se configura ningún valor, el valor predeterminado de la aplicación es en ejecución en el `Production` entorno.

La aplicación puede desencadenar y agregar la configuración de varios orígenes según el nombre del entorno. De forma predeterminada, la configuración se carga de los siguientes recursos en el orden mostrado:

1. *appsettings.jsen* el archivo, si está presente
1. *appSettings. {ENVIRONMENT_NAME}. archivo JSON* , si está presente
1. Archivo de secretos de usuario en disco, si está presente
1. Variables de entorno
1. Argumentos de la línea de comandos

## <a name="appsettingsjson-format-and-access"></a>appsettings.jsen formato y acceso

El *appsettings.jsen* el archivo puede ser jerárquico con valores estructurados como el siguiente JSON:

```json
{
  "section0": {
    "key0": "value",
    "key1": "value"
  },
  "section1": {
    "key0": "value",
    "key1": "value"
  }
}
```

Cuando se presenta el JSON anterior, el sistema de configuración acopla los valores secundarios y hace referencia a sus rutas de acceso jerárquicas completas. Un carácter de dos puntos ( `:` ) separa cada propiedad de la jerarquía. Por ejemplo, la clave de configuración `section1:key0` tiene acceso al `section1` valor del literal de objeto `key0` .

## <a name="user-secrets"></a>Secretos de usuario

Los secretos de usuario son:

* Valores de configuración que se almacenan en un archivo JSON en la estación de trabajo del desarrollador, fuera de la carpeta de desarrollo de la aplicación.
* Solo se carga cuando se ejecuta en el `Development` entorno.
* Asociado a una aplicación específica.
* Administrado con el comando de la CLI de .NET `user-secrets` .

Configure la aplicación para el almacenamiento de secretos ejecutando el `user-secrets` comando:

```dotnetcli
dotnet user-secrets init
```

El comando anterior agrega un `UserSecretsId` elemento al archivo de proyecto. El elemento contiene un GUID, que se usa para asociar secretos con la aplicación. Después, puede definir un secreto con el `set` comando. Por ejemplo:

```dotnetcli
dotnet user-secrets set "Parent:ApiKey" "12345"
```

El comando anterior hace que la `Parent:ApiKey` clave de configuración esté disponible en la estación de trabajo de un desarrollador con el valor `12345` .

Para obtener más información sobre cómo crear, almacenar y administrar secretos de usuario, consulte el documento sobre el [almacenamiento seguro de secretos de aplicación en el desarrollo en ASP.net Core](/aspnet/core/security/app-secrets) .

## <a name="environment-variables"></a>Variables de entorno

El siguiente conjunto de valores cargados en la configuración de la aplicación son las variables de entorno del sistema. Ahora se puede tener acceso a toda la configuración de las variables de entorno del sistema a través de la API de configuración. Los valores jerárquicos se acoplan y separan con caracteres de dos puntos cuando se leen dentro de la aplicación. Sin embargo, algunos sistemas operativos no admiten los nombres de las variables de entorno de caracteres de dos puntos. ASP.NET Core aborda esta limitación mediante la conversión de valores que tienen un carácter de subrayado doble ( `__` ) en un signo de dos puntos cuando se tiene acceso a ellos. El `Parent:ApiKey` valor de la sección de secretos de usuario anterior se puede invalidar con la variable de entorno `Parent__ApiKey` .

## <a name="command-line-arguments"></a>Argumentos de la línea de comandos

La configuración también se puede proporcionar como argumentos de la línea de comandos cuando se inicia la aplicación. Use la notación de doble guión ( `--` ) o barra diagonal ( `/` ) para indicar el nombre del valor de configuración que se va a establecer y el valor que se va a configurar. La sintaxis es similar a la de los siguientes comandos:

```dotnetcli
dotnet run CommandLineKey1=value1 --CommandLineKey2=value2 /CommandLineKey3=value3
dotnet run --CommandLineKey1 value1 /CommandLineKey2 value2
dotnet run Parent:ApiKey=67890
```

## <a name="the-return-of-webconfig"></a>El valor devuelto de web.config

Si ha implementado la aplicación en Windows en IIS, el archivo *web.config* aún configura IIS para administrar la aplicación. De forma predeterminada, IIS agrega una referencia al módulo de ASP.NET Core (ANCM). ANCM es un módulo de IIS nativo que hospeda la aplicación en lugar del servidor Web Kestrel. Esta *web.config* sección es similar al siguiente marcado XML:

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <location path="." inheritInChildApplications="false">
    <system.webServer>
      <handlers>
        <add name="aspNetCore" path="*" verb="*" modules="AspNetCoreModuleV2" resourceType="Unspecified" />
      </handlers>
      <aspNetCore processPath=".\MyApp.exe"
                  stdoutLogEnabled="false"
                  stdoutLogFile=".\logs\stdout"
                  hostingModel="inprocess" />
    </system.webServer>
  </location>
</configuration>
```

La configuración específica de la aplicación se puede definir anidando un `environmentVariables` elemento en el `aspNetCore` elemento. Los valores definidos en esta sección se presentan a la aplicación ASP.NET Core como variables de entorno. Las variables de entorno se cargan adecuadamente durante ese segmento de inicio de la aplicación.

```xml
<aspNetCore processPath="dotnet"
      arguments=".\MyApp.dll"
      stdoutLogEnabled="false"
      stdoutLogFile=".\logs\stdout"
      hostingModel="inprocess">
  <environmentVariables>
    <environmentVariable name="ASPNETCORE_ENVIRONMENT" value="Development" />
    <environmentVariable name="Parent:ApiKey" value="67890" />
  </environmentVariables>
</aspNetCore>
```

## <a name="read-configuration-in-the-app"></a>Lectura de la configuración en la aplicación

ASP.NET Core proporciona la configuración de la aplicación a través de la <xref:Microsoft.Extensions.Configuration.IConfiguration> interfaz. Los Blazor componentes, Blazor las páginas y cualquier otra clase administrada por el ASP.net Core que necesite tener acceso a la configuración deben solicitar esta interfaz de configuración. El marco de ASP.NET Core rellenará automáticamente esta interfaz con la configuración resuelta configurada anteriormente. En una Blazor página o en el marcado de Razor de un componente, puede insertar el `IConfiguration` objeto con una `@inject` Directiva en la parte superior del archivo *. Razor* de la siguiente manera:

```razor
@inject IConfiguration Configuration
```

Esta instrucción anterior hace `IConfiguration` que el objeto esté disponible como la `Configuration` variable a lo largo del resto de la plantilla de Razor.

Se pueden leer los valores de configuración individuales si se especifica la jerarquía de valores de configuración que se busca como parámetro de indexador:

```csharp
var mySetting = Configuration["section1:key0"];
```

Puede capturar secciones de configuración completas mediante el <xref:Microsoft.Extensions.Configuration.IConfiguration.GetSection%2A> método para recuperar una colección de claves en una ubicación concreta con una sintaxis similar a `GetSection("section1")` para recuperar la configuración de section1 del ejemplo anterior.

## <a name="strongly-typed-configuration"></a>Configuración fuertemente tipada

Con los formularios Web Forms, es posible crear un tipo de configuración fuertemente tipado que se hereda del <xref:System.Configuration.ConfigurationSection> tipo y los tipos asociados. `ConfigurationSection`Permite configurar algunas reglas de negocios y el procesamiento de esos valores de configuración.

En ASP.NET Core, puede especificar una jerarquía de clases que recibirá los valores de configuración. Estas clases:

* No es necesario heredar de una clase primaria.
* Debe incluir `public` propiedades que coincidan con las propiedades y las referencias de tipo de la estructura de configuración que desea capturar.

Para el *appsettings.jsanterior en* el ejemplo, puede definir las siguientes clases para capturar los valores:

```csharp
public class MyConfig
{
    public MyConfigSection section0 { get; set;}

    public MyConfigSection section1 { get; set;}
}

public class MyConfigSection
{
    public string key0 { get; set; }

    public string key1 { get; set; }
}
```

Esta jerarquía de clases se puede rellenar agregando la siguiente línea al `Startup.ConfigureServices` método:

```csharp
services.Configure<MyConfig>(Configuration);
```

En el resto de la aplicación, puede Agregar un parámetro de entrada a las clases o una `@inject` Directiva en las plantillas de Razor de tipo `IOptions<MyConfig>` para recibir los valores de configuración fuertemente tipados. La `IOptions<MyConfig>.Value` propiedad dará como resultado el `MyConfig` valor rellenado de los valores de configuración.

```razor
@inject IOptions<MyConfig> options
@code {
    var MyConfiguration = options.Value;
    var theSetting = MyConfiguration.section1.key0;
}
```

Puede encontrar más información sobre la característica de opciones en el [patrón de opciones de ASP.net Core](/aspnet/core/fundamentals/configuration/options#options-interfaces) documento.

>[!div class="step-by-step"]
>[Anterior](middleware.md)
>[Siguiente](security-authentication-authorization.md)
