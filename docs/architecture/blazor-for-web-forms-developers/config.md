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
# <a name="app-configuration"></a><span data-ttu-id="d5c5a-103">Configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="d5c5a-103">App configuration</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="d5c5a-104">La forma principal de cargar la configuración de la aplicación&mdash;en formularios Web Forms es con entradas en el archivo *web.config* en el servidor o un archivo de configuración relacionado al que hace referencia *web.config*. Puede usar el `ConfigurationManager` objeto estático para interactuar con la configuración de la aplicación, las cadenas de conexión del repositorio de datos y otros proveedores de configuración extendida que se agregan a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-104">The primary way to load app configuration in Web Forms is with entries in the *web.config* file&mdash;either on the server or a related configuration file referenced by *web.config*. You can use the static `ConfigurationManager` object to interact with app settings, data repository connection strings, and other extended configuration providers that are added into the app.</span></span> <span data-ttu-id="d5c5a-105">Es típico ver las interacciones con la configuración de la aplicación como se ve en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="d5c5a-105">It's typical to see interactions with app configuration as seen in the following code:</span></span>

```csharp
var configurationValue = ConfigurationManager.AppSettings["ConfigurationSettingName"];
var connectionString = ConfigurationManager.ConnectionStrings["MyDatabaseConnectionName"].ConnectionString;
```

<span data-ttu-id="d5c5a-106">Con ASP.NET Core y Blazor del lado servidor, el archivo *web.config* PUEDE estar presente si la aplicación está hospedada en un servidor IIS de Windows.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-106">With ASP.NET Core and server-side Blazor, the *web.config* file MAY be present if your app is hosted on a Windows IIS server.</span></span> <span data-ttu-id="d5c5a-107">Sin embargo, `ConfigurationManager` no hay interacción con esta configuración y puede recibir una configuración de aplicación más estructurada de otros orígenes.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-107">However, there's no `ConfigurationManager` interaction with this configuration, and you can receive more structured app configuration from other sources.</span></span> <span data-ttu-id="d5c5a-108">Echemos un vistazo a cómo se recopila la configuración y cómo puede seguir accediendo a la información de configuración desde un archivo *web.config.*</span><span class="sxs-lookup"><span data-stu-id="d5c5a-108">Let's take a look at how configuration is gathered and how you can still access configuration information from a *web.config* file.</span></span>

## <a name="configuration-sources"></a><span data-ttu-id="d5c5a-109">Orígenes de configuración</span><span class="sxs-lookup"><span data-stu-id="d5c5a-109">Configuration sources</span></span>

<span data-ttu-id="d5c5a-110">ASP.NET Core reconoce que hay muchos orígenes de configuración que puede que desee usar para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-110">ASP.NET Core recognizes there are many configuration sources you may want to use for your app.</span></span> <span data-ttu-id="d5c5a-111">El marco de trabajo intenta ofrecerle la mejor de estas características de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-111">The framework attempts to offer you the best of these features by default.</span></span> <span data-ttu-id="d5c5a-112">La configuración se lee y se agrega de estos diversos orígenes por ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-112">Configuration is read and aggregated from these various sources by ASP.NET Core.</span></span> <span data-ttu-id="d5c5a-113">Los valores cargados posteriormente para la misma clave de configuración tienen prioridad sobre los valores anteriores.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-113">Later loaded values for the same configuration key take precedence over earlier values.</span></span>

<span data-ttu-id="d5c5a-114">ASP.NET Core se diseñó para ser conscientes de la nube y para facilitar la configuración de aplicaciones tanto para los operadores como para los desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-114">ASP.NET Core was designed to be cloud-aware and to make configuration of apps easier for both operators and developers.</span></span> <span data-ttu-id="d5c5a-115">ASP.NET Core es compatible con el entorno y `Production` sabe `Development` si se está ejecutando en su entorno o en su entorno.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-115">ASP.NET Core is environment-aware and knows if it's running in your `Production` or `Development` environment.</span></span> <span data-ttu-id="d5c5a-116">El indicador de entorno `ASPNETCORE_ENVIRONMENT` se establece en la variable de entorno del sistema.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-116">The environment indicator is set in the `ASPNETCORE_ENVIRONMENT` system environment variable.</span></span> <span data-ttu-id="d5c5a-117">Si no se configura ningún valor, el `Production` valor predeterminado de la aplicación se ejecuta en el entorno.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-117">If no value is configured, the app defaults to running in the `Production` environment.</span></span>

<span data-ttu-id="d5c5a-118">La aplicación puede desencadenar y agregar la configuración de varios orígenes en función del nombre del entorno.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-118">Your app can trigger and add configuration from several sources based on the environment's name.</span></span> <span data-ttu-id="d5c5a-119">De forma predeterminada, la configuración se carga desde los siguientes recursos en el orden indicado:</span><span class="sxs-lookup"><span data-stu-id="d5c5a-119">By default, configuration is loaded from the following resources in the order listed:</span></span>

1. <span data-ttu-id="d5c5a-120">*appsettings.json,* si está presente</span><span class="sxs-lookup"><span data-stu-id="d5c5a-120">*appsettings.json* file, if present</span></span>
1. <span data-ttu-id="d5c5a-121">*appsettings. ENVIRONMENT_NAME Si* está presente, si está presente.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-121">*appsettings.{ENVIRONMENT_NAME}.json* file, if present</span></span>
1. <span data-ttu-id="d5c5a-122">Archivo de secretos de usuario en el disco, si está presente</span><span class="sxs-lookup"><span data-stu-id="d5c5a-122">User secrets file on disk, if present</span></span>
1. <span data-ttu-id="d5c5a-123">Variables de entorno</span><span class="sxs-lookup"><span data-stu-id="d5c5a-123">Environment variables</span></span>
1. <span data-ttu-id="d5c5a-124">Argumentos de la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="d5c5a-124">Command-line arguments</span></span>

## <a name="appsettingsjson-format-and-access"></a><span data-ttu-id="d5c5a-125">appsettings.json formato y acceso</span><span class="sxs-lookup"><span data-stu-id="d5c5a-125">appsettings.json format and access</span></span>

<span data-ttu-id="d5c5a-126">El archivo *appsettings.json* puede ser jerárquico con valores estructurados como el siguiente JSON:</span><span class="sxs-lookup"><span data-stu-id="d5c5a-126">The *appsettings.json* file can be hierarchical with values structured like the following JSON:</span></span>

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

<span data-ttu-id="d5c5a-127">Cuando se presenta con el JSON anterior, el sistema de configuración aplana los valores secundarios y hace referencia a sus rutas jerárquicas completas.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-127">When presented with the preceding JSON, the configuration system flattens child values and references their fully qualified hierarchical paths.</span></span> <span data-ttu-id="d5c5a-128">Un carácter de dos puntos (`:`) separa cada propiedad de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-128">A colon (`:`) character separates each property in the hierarchy.</span></span> <span data-ttu-id="d5c5a-129">Por ejemplo, la `section1:key0` clave `section1` de configuración `key0` tiene acceso al valor del literal de objeto.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-129">For example, the configuration key `section1:key0` accesses the `section1` object literal's `key0` value.</span></span>

## <a name="user-secrets"></a><span data-ttu-id="d5c5a-130">Secretos de usuario</span><span class="sxs-lookup"><span data-stu-id="d5c5a-130">User secrets</span></span>

<span data-ttu-id="d5c5a-131">Los secretos de usuario son:</span><span class="sxs-lookup"><span data-stu-id="d5c5a-131">User secrets are:</span></span>

* <span data-ttu-id="d5c5a-132">Valores de configuración que se almacenan en un archivo JSON en la estación de trabajo del desarrollador, fuera de la carpeta de desarrollo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-132">Configuration values that are stored in a JSON file on the developer's workstation, outside of the app development folder.</span></span>
* <span data-ttu-id="d5c5a-133">Solo se carga `Development` cuando se ejecuta en el entorno.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-133">Only loaded when running in the `Development` environment.</span></span>
* <span data-ttu-id="d5c5a-134">Asociado a una aplicación específica.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-134">Associated with a specific app.</span></span>
* <span data-ttu-id="d5c5a-135">Administrado con el comando de `user-secrets` la CLI de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-135">Managed with the .NET Core CLI's `user-secrets` command.</span></span>

<span data-ttu-id="d5c5a-136">Configure la aplicación para el `user-secrets` almacenamiento de secretos ejecutando el comando:</span><span class="sxs-lookup"><span data-stu-id="d5c5a-136">Configure your app for secrets storage by executing the `user-secrets` command:</span></span>

```dotnetcli
dotnet user-secrets init
```

<span data-ttu-id="d5c5a-137">El comando anterior agrega `UserSecretsId` un elemento al archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-137">The preceding command adds a `UserSecretsId` element to the project file.</span></span> <span data-ttu-id="d5c5a-138">El elemento contiene un GUID, que se usa para asociar secretos con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-138">The element contains a GUID, which is used to associate secrets with the app.</span></span> <span data-ttu-id="d5c5a-139">A continuación, puede definir `set` un secreto con el comando.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-139">You can then define a secret with the `set` command.</span></span> <span data-ttu-id="d5c5a-140">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d5c5a-140">For example:</span></span>

```dotnetcli
dotnet user-secrets set "Parent:ApiKey" "12345"
```

<span data-ttu-id="d5c5a-141">El comando anterior `Parent:ApiKey` hace que la clave de configuración `12345`esté disponible en la estación de trabajo de un desarrollador con el valor .</span><span class="sxs-lookup"><span data-stu-id="d5c5a-141">The preceding command makes the `Parent:ApiKey` configuration key available on a developer's workstation with the value `12345`.</span></span>

<span data-ttu-id="d5c5a-142">Para obtener más información acerca de cómo crear, almacenar y administrar secretos de usuario, vea el [almacenamiento seguro de secretos de aplicación en desarrollo en ASP.NET documento principal.](/aspnet/core/security/app-secrets)</span><span class="sxs-lookup"><span data-stu-id="d5c5a-142">For more information about creating, storing, and managing user secrets, see the [Safe storage of app secrets in development in ASP.NET Core](/aspnet/core/security/app-secrets) document.</span></span>

## <a name="environment-variables"></a><span data-ttu-id="d5c5a-143">Variables de entorno</span><span class="sxs-lookup"><span data-stu-id="d5c5a-143">Environment variables</span></span>

<span data-ttu-id="d5c5a-144">El siguiente conjunto de valores cargados en la configuración de la aplicación son las variables de entorno del sistema.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-144">The next set of values loaded into your app configuration is the system's environment variables.</span></span> <span data-ttu-id="d5c5a-145">Todas las opciones de entorno del sistema ahora son accesibles para usted a través de la API de configuración.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-145">All of your system's environment variable settings are now accessible to you through the configuration API.</span></span> <span data-ttu-id="d5c5a-146">Los valores jerárquicos se acoplan y se separan por caracteres de dos puntos cuando se leen dentro de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-146">Hierarchical values are flattened and separated by colon characters when read inside your app.</span></span> <span data-ttu-id="d5c5a-147">Sin embargo, algunos sistemas operativos no permiten los nombres de variables de entorno de caracteres de dos puntos.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-147">However, some operating systems don't allow the colon character environment variable names.</span></span> <span data-ttu-id="d5c5a-148">ASP.NET Core aborda esta limitación convirtiendo valores`__`que tienen guiones dobles ( ) en dos puntos cuando se accede a ellos.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-148">ASP.NET Core addresses this limitation by converting values that have double-underscores (`__`) into a colon when they're accessed.</span></span> <span data-ttu-id="d5c5a-149">El `Parent:ApiKey` valor de la sección de secretos de `Parent__ApiKey`usuario anterior se puede invalidar con la variable de entorno .</span><span class="sxs-lookup"><span data-stu-id="d5c5a-149">The `Parent:ApiKey` value from the user secrets section above can be overridden with the environment variable `Parent__ApiKey`.</span></span>

## <a name="command-line-arguments"></a><span data-ttu-id="d5c5a-150">Argumentos de la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="d5c5a-150">Command-line arguments</span></span>

<span data-ttu-id="d5c5a-151">La configuración también se puede proporcionar como argumentos de línea de comandos cuando se inicia la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-151">Configuration can also be provided as command-line arguments when your app is started.</span></span> <span data-ttu-id="d5c5a-152">Utilice la notación`--`de doble guión ( ) o de barra diagonal (`/`) para indicar el nombre del valor de configuración que se va a establecer y el valor que se va a configurar.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-152">Use the double-dash (`--`) or forward-slash (`/`) notation to indicate the name of the configuration value to set and the value to be configured.</span></span> <span data-ttu-id="d5c5a-153">La sintaxis es similar a los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="d5c5a-153">The syntax resembles the following commands:</span></span>

```dotnetcli
dotnet run CommandLineKey1=value1 --CommandLineKey2=value2 /CommandLineKey3=value3
dotnet run --CommandLineKey1 value1 /CommandLineKey2 value2
dotnet run Parent:ApiKey=67890
```

## <a name="the-return-of-webconfig"></a><span data-ttu-id="d5c5a-154">El retorno de web.config</span><span class="sxs-lookup"><span data-stu-id="d5c5a-154">The return of web.config</span></span>

<span data-ttu-id="d5c5a-155">Si ha implementado la aplicación en Windows en IIS, el archivo *web.config* sigue configurando IIS para administrar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-155">If you've deployed your app to Windows on IIS, the *web.config* file still configures IIS to manage your app.</span></span> <span data-ttu-id="d5c5a-156">De forma predeterminada, IIS agrega una referencia al módulo de núcleo de ASP.NET (ANCM).</span><span class="sxs-lookup"><span data-stu-id="d5c5a-156">By default, IIS adds a reference to the ASP.NET Core Module (ANCM).</span></span> <span data-ttu-id="d5c5a-157">ANCM es un módulo IIS nativo que hospeda la aplicación en lugar del servidor web de Kestrel.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-157">ANCM is a native IIS module that hosts your app in place of the Kestrel web server.</span></span> <span data-ttu-id="d5c5a-158">Esta sección *web.config* es similar al siguiente marcado XML:</span><span class="sxs-lookup"><span data-stu-id="d5c5a-158">This *web.config* section resembles the following XML markup:</span></span>

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

<span data-ttu-id="d5c5a-159">La configuración específica de la aplicación `environmentVariables` se `aspNetCore` puede definir anidando un elemento en el elemento.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-159">App-specific configuration can be defined by nesting an `environmentVariables` element in the `aspNetCore` element.</span></span> <span data-ttu-id="d5c5a-160">Los valores definidos en esta sección se presentan a la aplicación ASP.NET Core como variables de entorno.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-160">The values defined in this section are presented to the ASP.NET Core app as environment variables.</span></span> <span data-ttu-id="d5c5a-161">Las variables de entorno se cargan correctamente durante ese segmento de inicio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-161">The environment variables load appropriately during that segment of app startup.</span></span>

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

## <a name="read-configuration-in-the-app"></a><span data-ttu-id="d5c5a-162">Leer la configuración en la aplicación</span><span class="sxs-lookup"><span data-stu-id="d5c5a-162">Read configuration in the app</span></span>

<span data-ttu-id="d5c5a-163">ASP.NET Core proporciona la <xref:Microsoft.Extensions.Configuration.IConfiguration> configuración de la aplicación a través de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-163">ASP.NET Core provides app configuration through the <xref:Microsoft.Extensions.Configuration.IConfiguration> interface.</span></span> <span data-ttu-id="d5c5a-164">Esta interfaz de configuración debe ser solicitada por los componentes de Blazor, las páginas de Blazor y cualquier otra clase administrada por Core ASP.NET que necesite acceso a la configuración.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-164">This configuration interface should be requested by your Blazor components, Blazor pages, and any other ASP.NET Core-managed class that needs access to configuration.</span></span> <span data-ttu-id="d5c5a-165">El marco de trabajo de ASP.NET Core rellenará automáticamente esta interfaz con la configuración resuelta configurada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-165">The ASP.NET Core framework will automatically populate this interface with the resolved configuration configured earlier.</span></span> <span data-ttu-id="d5c5a-166">En una página Blazor o en el marcado `IConfiguration` Razor de `@inject` un componente, puede insertar el objeto con una directiva en la parte superior del archivo *.razor* como esta:</span><span class="sxs-lookup"><span data-stu-id="d5c5a-166">On a Blazor page or a component's Razor markup, you can inject the `IConfiguration` object with an `@inject` directive at the top of the *.razor* file like this:</span></span>

```razor
@inject IConfiguration Configuration
```

<span data-ttu-id="d5c5a-167">Esta instrucción anterior `IConfiguration` hace que `Configuration` el objeto esté disponible como variable en el resto de la plantilla razor.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-167">This preceding statement makes the `IConfiguration` object available as the `Configuration` variable throughout the rest of the Razor template.</span></span>

<span data-ttu-id="d5c5a-168">Los valores de configuración individuales se pueden leer especificando la jerarquía de valores de configuración buscada como parámetro de indexador:</span><span class="sxs-lookup"><span data-stu-id="d5c5a-168">Individual configuration settings can be read by specifying the configuration setting hierarchy sought as an indexer parameter:</span></span>

```csharp
var mySetting = Configuration["section1:key0"];
```

<span data-ttu-id="d5c5a-169">Puede capturar secciones de <xref:Microsoft.Extensions.Configuration.IConfiguration.GetSection%2A> configuración completas mediante el método para recuperar una `GetSection("section1")` colección de claves en una ubicación específica con una sintaxis similar a la de recuperar la configuración de section1 del ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-169">You can fetch entire configuration sections by using the <xref:Microsoft.Extensions.Configuration.IConfiguration.GetSection%2A> method to retrieve a collection of keys at a specific location with a syntax similar to `GetSection("section1")` to retrieve the configuration for section1 from the earlier example.</span></span>

## <a name="strongly-typed-configuration"></a><span data-ttu-id="d5c5a-170">Configuración fuertemente tipada</span><span class="sxs-lookup"><span data-stu-id="d5c5a-170">Strongly typed configuration</span></span>

<span data-ttu-id="d5c5a-171">Con formularios Web Forms, era posible crear un tipo <xref:System.Configuration.ConfigurationSection> de configuración fuertemente tipado que se heredó del tipo y los tipos asociados.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-171">With Web Forms, it was possible to create a strongly typed configuration type that inherited from the <xref:System.Configuration.ConfigurationSection> type and associated types.</span></span> <span data-ttu-id="d5c5a-172">Un `ConfigurationSection` permite configurar algunas reglas de negocio y procesamiento para esos valores de configuración.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-172">A `ConfigurationSection` allowed you to configure some business rules and processing for those configuration values.</span></span>

<span data-ttu-id="d5c5a-173">En ASP.NET Core, puede especificar una jerarquía de clases que recibirá los valores de configuración.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-173">In ASP.NET Core, you can specify a class hierarchy that will receive the configuration values.</span></span> <span data-ttu-id="d5c5a-174">Estas clases:</span><span class="sxs-lookup"><span data-stu-id="d5c5a-174">These classes:</span></span>

* <span data-ttu-id="d5c5a-175">No es necesario heredar de una clase primaria.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-175">Don't need to inherit from a parent class.</span></span>
* <span data-ttu-id="d5c5a-176">Debe `public` incluir propiedades que coincidan con las propiedades y referencias de tipo para la estructura de configuración que desea capturar.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-176">Should include `public` properties that match the properties and type references for the configuration structure you wish to capture.</span></span>

<span data-ttu-id="d5c5a-177">Para el ejemplo *appsettings.json* anterior, podría definir las siguientes clases para capturar los valores:</span><span class="sxs-lookup"><span data-stu-id="d5c5a-177">For the earlier *appsettings.json* sample, you could define the following classes to capture the values:</span></span>

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

<span data-ttu-id="d5c5a-178">Esta jerarquía de clases se puede rellenar `Startup.ConfigureServices` agregando la siguiente línea al método:</span><span class="sxs-lookup"><span data-stu-id="d5c5a-178">This class hierarchy can be populated by adding the following line to the `Startup.ConfigureServices` method:</span></span>

```csharp
services.Configure<MyConfig>(Configuration);
```

<span data-ttu-id="d5c5a-179">En el resto de la aplicación, puede agregar `@inject` un parámetro de `IOptions<MyConfig>` entrada a las clases o una directiva en plantillas de tipo Razor para recibir los valores de configuración fuertemente tipados.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-179">In the rest of the app, you can add an input parameter to classes or an `@inject` directive in Razor templates of type `IOptions<MyConfig>` to receive the strongly typed configuration settings.</span></span> <span data-ttu-id="d5c5a-180">La `IOptions<MyConfig>.Value` propiedad producirá `MyConfig` el valor rellenado a partir de los valores de configuración.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-180">The `IOptions<MyConfig>.Value` property will yield the `MyConfig` value populated from the configuration settings.</span></span>

```razor
@inject IOptions<MyConfig> options
@code {
    var MyConfiguration = options.Value;
    var theSetting = MyConfiguration.section1.key0;
}
```

<span data-ttu-id="d5c5a-181">Puede encontrar más información sobre la función Opciones en el [patrón Opciones del](/aspnet/core/fundamentals/configuration/options#options-interfaces) documento ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="d5c5a-181">More information about the Options feature can be found in the [Options pattern in ASP.NET Core](/aspnet/core/fundamentals/configuration/options#options-interfaces) document.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="d5c5a-182">[Anterior](middleware.md)
>[Siguiente](security-authentication-authorization.md)</span><span class="sxs-lookup"><span data-stu-id="d5c5a-182">[Previous](middleware.md)
[Next](security-authentication-authorization.md)</span></span>
