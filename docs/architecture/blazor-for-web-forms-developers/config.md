---
title: Configuración de la aplicación
description: Aprenda a configurar aplicaciones Blazor sin usar ConfigurationManager.
author: csharpfritz
ms.author: jefritz
ms.date: 04/01/2020
ms.openlocfilehash: c780a395f72e2520af86c20c7f6618953a528ff7
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "80588248"
---
# <a name="app-configuration"></a>Configuración de la aplicación

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

La forma principal de cargar la configuración de la aplicación&mdash;en formularios Web Forms es con entradas en el archivo *web.config* en el servidor o un archivo de configuración relacionado al que hace referencia *web.config*. Puede usar el `ConfigurationManager` objeto estático para interactuar con la configuración de la aplicación, las cadenas de conexión del repositorio de datos y otros proveedores de configuración extendida que se agregan a la aplicación. Es típico ver las interacciones con la configuración de la aplicación como se ve en el código siguiente:

```csharp
var configurationValue = ConfigurationManager.AppSettings["ConfigurationSettingName"];
var connectionString = ConfigurationManager.ConnectionStrings["MyDatabaseConnectionName"].ConnectionString;
```

Con ASP.NET Core y Blazor del lado servidor, el archivo *web.config* PUEDE estar presente si la aplicación está hospedada en un servidor IIS de Windows. Sin embargo, `ConfigurationManager` no hay interacción con esta configuración y puede recibir una configuración de aplicación más estructurada de otros orígenes. Echemos un vistazo a cómo se recopila la configuración y cómo puede seguir accediendo a la información de configuración desde un archivo *web.config.*

## <a name="configuration-sources"></a>Orígenes de configuración

ASP.NET Core reconoce que hay muchos orígenes de configuración que puede que desee usar para la aplicación. El marco de trabajo intenta ofrecerle la mejor de estas características de forma predeterminada. La configuración se lee y se agrega de estos diversos orígenes por ASP.NET Core. Los valores cargados posteriormente para la misma clave de configuración tienen prioridad sobre los valores anteriores.

ASP.NET Core se diseñó para ser conscientes de la nube y para facilitar la configuración de aplicaciones tanto para los operadores como para los desarrolladores. ASP.NET Core es compatible con el entorno y `Production` sabe `Development` si se está ejecutando en su entorno o en su entorno. El indicador de entorno `ASPNETCORE_ENVIRONMENT` se establece en la variable de entorno del sistema. Si no se configura ningún valor, el `Production` valor predeterminado de la aplicación se ejecuta en el entorno.

La aplicación puede desencadenar y agregar la configuración de varios orígenes en función del nombre del entorno. De forma predeterminada, la configuración se carga desde los siguientes recursos en el orden indicado:

1. *appsettings.json,* si está presente
1. *appsettings. ENVIRONMENT_NAME Si* está presente, si está presente.
1. Archivo de secretos de usuario en el disco, si está presente
1. Variables de entorno
1. Argumentos de la línea de comandos

## <a name="appsettingsjson-format-and-access"></a>appsettings.json formato y acceso

El archivo *appsettings.json* puede ser jerárquico con valores estructurados como el siguiente JSON:

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

Cuando se presenta con el JSON anterior, el sistema de configuración aplana los valores secundarios y hace referencia a sus rutas jerárquicas completas. Un carácter de dos puntos (`:`) separa cada propiedad de la jerarquía. Por ejemplo, la `section1:key0` clave `section1` de configuración `key0` tiene acceso al valor del literal de objeto.

## <a name="user-secrets"></a>Secretos de usuario

Los secretos de usuario son:

* Valores de configuración que se almacenan en un archivo JSON en la estación de trabajo del desarrollador, fuera de la carpeta de desarrollo de aplicaciones.
* Solo se carga `Development` cuando se ejecuta en el entorno.
* Asociado a una aplicación específica.
* Administrado con el comando de `user-secrets` la CLI de .NET Core.

Configure la aplicación para el `user-secrets` almacenamiento de secretos ejecutando el comando:

```dotnetcli
dotnet user-secrets init
```

El comando anterior agrega `UserSecretsId` un elemento al archivo de proyecto. El elemento contiene un GUID, que se usa para asociar secretos con la aplicación. A continuación, puede definir `set` un secreto con el comando. Por ejemplo:

```dotnetcli
dotnet user-secrets set "Parent:ApiKey" "12345"
```

El comando anterior `Parent:ApiKey` hace que la clave de configuración `12345`esté disponible en la estación de trabajo de un desarrollador con el valor .

Para obtener más información acerca de cómo crear, almacenar y administrar secretos de usuario, vea el [almacenamiento seguro de secretos de aplicación en desarrollo en ASP.NET documento principal.](/aspnet/core/security/app-secrets)

## <a name="environment-variables"></a>Variables de entorno

El siguiente conjunto de valores cargados en la configuración de la aplicación son las variables de entorno del sistema. Todas las opciones de entorno del sistema ahora son accesibles para usted a través de la API de configuración. Los valores jerárquicos se acoplan y se separan por caracteres de dos puntos cuando se leen dentro de la aplicación. Sin embargo, algunos sistemas operativos no permiten los nombres de variables de entorno de caracteres de dos puntos. ASP.NET Core aborda esta limitación convirtiendo valores`__`que tienen guiones dobles ( ) en dos puntos cuando se accede a ellos. El `Parent:ApiKey` valor de la sección de secretos de `Parent__ApiKey`usuario anterior se puede invalidar con la variable de entorno .

## <a name="command-line-arguments"></a>Argumentos de la línea de comandos

La configuración también se puede proporcionar como argumentos de línea de comandos cuando se inicia la aplicación. Utilice la notación`--`de doble guión ( ) o de barra diagonal (`/`) para indicar el nombre del valor de configuración que se va a establecer y el valor que se va a configurar. La sintaxis es similar a los siguientes comandos:

```dotnetcli
dotnet run CommandLineKey1=value1 --CommandLineKey2=value2 /CommandLineKey3=value3
dotnet run --CommandLineKey1 value1 /CommandLineKey2 value2
dotnet run Parent:ApiKey=67890
```

## <a name="the-return-of-webconfig"></a>El retorno de web.config

Si ha implementado la aplicación en Windows en IIS, el archivo *web.config* sigue configurando IIS para administrar la aplicación. De forma predeterminada, IIS agrega una referencia al módulo de núcleo de ASP.NET (ANCM). ANCM es un módulo IIS nativo que hospeda la aplicación en lugar del servidor web de Kestrel. Esta sección *web.config* es similar al siguiente marcado XML:

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

La configuración específica de la aplicación `environmentVariables` se `aspNetCore` puede definir anidando un elemento en el elemento. Los valores definidos en esta sección se presentan a la aplicación ASP.NET Core como variables de entorno. Las variables de entorno se cargan correctamente durante ese segmento de inicio de la aplicación.

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

## <a name="read-configuration-in-the-app"></a>Leer la configuración en la aplicación

ASP.NET Core proporciona la <xref:Microsoft.Extensions.Configuration.IConfiguration> configuración de la aplicación a través de la interfaz. Esta interfaz de configuración debe ser solicitada por los componentes de Blazor, las páginas de Blazor y cualquier otra clase administrada por Core ASP.NET que necesite acceso a la configuración. El marco de trabajo de ASP.NET Core rellenará automáticamente esta interfaz con la configuración resuelta configurada anteriormente. En una página Blazor o en el marcado `IConfiguration` Razor de `@inject` un componente, puede insertar el objeto con una directiva en la parte superior del archivo *.razor* como esta:

```razor
@inject IConfiguration Configuration
```

Esta instrucción anterior `IConfiguration` hace que `Configuration` el objeto esté disponible como variable en el resto de la plantilla razor.

Los valores de configuración individuales se pueden leer especificando la jerarquía de valores de configuración buscada como parámetro de indexador:

```csharp
var mySetting = Configuration["section1:key0"];
```

Puede capturar secciones de <xref:Microsoft.Extensions.Configuration.IConfiguration.GetSection%2A> configuración completas mediante el método para recuperar una `GetSection("section1")` colección de claves en una ubicación específica con una sintaxis similar a la de recuperar la configuración de section1 del ejemplo anterior.

## <a name="strongly-typed-configuration"></a>Configuración fuertemente tipada

Con formularios Web Forms, era posible crear un tipo <xref:System.Configuration.ConfigurationSection> de configuración fuertemente tipado que se heredó del tipo y los tipos asociados. Un `ConfigurationSection` permite configurar algunas reglas de negocio y procesamiento para esos valores de configuración.

En ASP.NET Core, puede especificar una jerarquía de clases que recibirá los valores de configuración. Estas clases:

* No es necesario heredar de una clase primaria.
* Debe `public` incluir propiedades que coincidan con las propiedades y referencias de tipo para la estructura de configuración que desea capturar.

Para el ejemplo *appsettings.json* anterior, podría definir las siguientes clases para capturar los valores:

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

Esta jerarquía de clases se puede rellenar `Startup.ConfigureServices` agregando la siguiente línea al método:

```csharp
services.Configure<MyConfig>(Configuration);
```

En el resto de la aplicación, puede agregar `@inject` un parámetro de `IOptions<MyConfig>` entrada a las clases o una directiva en plantillas de tipo Razor para recibir los valores de configuración fuertemente tipados. La `IOptions<MyConfig>.Value` propiedad producirá `MyConfig` el valor rellenado a partir de los valores de configuración.

```razor
@inject IOptions<MyConfig> options
@code {
    var MyConfiguration = options.Value;
    var theSetting = MyConfiguration.section1.key0;
}
```

Puede encontrar más información sobre la función Opciones en el [patrón Opciones del](/aspnet/core/fundamentals/configuration/options#options-interfaces) documento ASP.NET Core.

>[!div class="step-by-step"]
>[Anterior](middleware.md)
>[Siguiente](security-authentication-authorization.md)
