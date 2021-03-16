---
title: Patrón de opciones en .NET
author: IEvangelist
description: Obtenga información sobre cómo usar el patrón de opciones para representar grupos de configuraciones relacionadas en aplicaciones .NET.
ms.author: dapine
ms.date: 02/18/2021
ms.openlocfilehash: df30928cdb1832e94f89abbdf8cc41e1304f8e2e
ms.sourcegitcommit: bdbf6472de867a0a11aaa5b9384a2506c24f27d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2021
ms.locfileid: "102402214"
---
# <a name="options-pattern-in-net"></a>Patrón de opciones en .NET

El patrón de opciones usa clases para proporcionar acceso fuertemente tipado a grupos de configuraciones relacionadas. Cuando los [valores de configuración](configuration.md) están aislados por escenario en clases independientes, la aplicación se ajusta a dos principios de ingeniería de software importantes:

- El [principio de segregación de interfaz (ISP) o encapsulación](../../architecture/modern-web-apps-azure/architectural-principles.md#encapsulation): los escenarios (clases) que dependen de valores de configuración dependen únicamente de los valores de configuración que usen.
- [Separación de intereses](../../architecture/modern-web-apps-azure/architectural-principles.md#separation-of-concerns): los valores de configuración para distintos elementos de la aplicación no son dependientes entre sí ni están emparejados.

Las opciones también proporcionan un mecanismo para validar los datos de configuración. Para obtener más información, consulte la sección [Opciones de validación](#options-validation).

## <a name="bind-hierarchical-configuration"></a>Enlace de configuración jerárquica

La mejor manera de leer valores de configuración relacionados es usar el patrón de opciones. El patrón de opciones se puede aplicar mediante la interfaz <xref:Microsoft.Extensions.Options.IOptions%601>, donde el parámetro de tipo genérico `TOptions` está restringido a `class`. `IOptions<TOptions>` se puede proporcionar posteriormente mediante la inserción de dependencias. Para más información, vea [Inserción de dependencias en .NET](dependency-injection.md).

Por ejemplo, para leer los siguientes valores de configuración:

:::code language="json" source="snippets/configuration/console-json/appsettings.json" range="3-6":::

Cree la siguiente clase `TransientFaultHandlingOptions`:

:::code language="csharp" source="snippets/configuration/console-json/TransientFaultHandlingOptions.cs" range="5-9":::

<span id="options-class"></span> Al usar el patrón de opciones, una clase de opciones:

- Debe ser no abstracta con un constructor público sin parámetros.
- Debe contener propiedades de lectura y escritura para enlazar (los campos ***no*** están enlazados).

El código siguiente:

* Llama a [ConfigurationBinder.Bind](xref:Microsoft.Extensions.Configuration.ConfigurationBinder.Bind%2A) para enlazar la clase `TransientFaultHandlingOptions` a la sección `"TransientFaultHandlingOptions"`.
* Muestra los datos de configuración.

:::code language="csharp" source="snippets/configuration/console-json/Program.cs" range="31-38":::

En el código anterior, los cambios en el archivo de configuración de JSON producidos una vez iniciada la aplicación se leen.

[`ConfigurationBinder.Get<T>`](xref:Microsoft.Extensions.Configuration.ConfigurationBinder.Get%2A) enlaza y devuelve el tipo especificado. Puede ser más conveniente usar `ConfigurationBinder.Get<T>` que `ConfigurationBinder.Bind`. En el código siguiente se muestra cómo puede usar `ConfigurationBinder.Get<T>` con la clase `TransientFaultHandlingOptions`:

```csharp
IConfigurationRoot configurationRoot = configuration.Build();

var options =
    configurationRoot.GetSection(nameof(TransientFaultHandlingOptions))
                     .Get<TransientFaultHandlingOptions>();

Console.WriteLine($"TransientFaultHandlingOptions.Enabled={options.Enabled}");
Console.WriteLine($"TransientFaultHandlingOptions.AutoRetryDelay={options.AutoRetryDelay}");
```

En el código anterior, los cambios en el archivo de configuración de JSON producidos una vez iniciada la aplicación se leen.

> [!IMPORTANT]
> La clase <xref:Microsoft.Extensions.Configuration.ConfigurationBinder> expone varias API, como `.Bind(object instance)` y `.Get<T>()`, que ***no*** están restringidas a `class`. Al utilizar cualquiera de las [interfaces de opciones](#options-interfaces), debe cumplir las [restricciones de la clase de opciones](#options-class) mencionadas anteriormente.

Un enfoque alternativo a la hora de usar el patrón de opciones consiste en enlazar la sección `"TransientFaultHandlingOptions"` y agregarla al [contenedor del servicio de inserción de dependencias](dependency-injection.md). En el siguiente código se agrega `TransientFaultHandlingOptions` al contenedor de servicios con <xref:Microsoft.Extensions.DependencyInjection.OptionsConfigurationServiceCollectionExtensions.Configure%2A> y se enlaza a la configuración:

```csharp
services.Configure<TransientFaultHandlingOptions>(
    configurationRoot.GetSection(
        key: nameof(TransientFaultHandlingOptions)));
```

> [!TIP]
> El parámetro `key` es el nombre de la sección de configuración que se va a buscar. *No* tiene que coincidir con el nombre del tipo que la representa. Por ejemplo, podría tener una sección denominada `"FaultHandling"` y podría estar representada por la clase `TransientFaultHandlingOptions`. En esta instancia, en su lugar, debe pasar `"FaultHandling"` a la función <xref:Microsoft.Extensions.Configuration.IConfiguration.GetSection%2A>. El operador `nameof` se utiliza por comodidad cuando la sección con nombre coincide con el tipo al que corresponde.

A partir del código anterior, el siguiente código lee las opciones de posición:

:::code language="csharp" source="snippets/configuration/console-json/ExampleService.cs":::

En el código anterior, los cambios en el archivo de configuración de JSON producidos una vez iniciada la aplicación ***no*** se leen. Para leer los cambios una vez iniciada la aplicación, use [IOptionsSnapshot](#use-ioptionssnapshot-to-read-updated-data).

## <a name="options-interfaces"></a>Interfaces de opciones

<xref:Microsoft.Extensions.Options.IOptions%601>:

- ***No*** admite:
  - Lectura de los datos de configuración una vez iniciada la aplicación.
  - [Opciones con nombre](#named-options-support-using-iconfigurenamedoptions)
- Se registra como [Singleton](dependency-injection.md#singleton) y se puede insertar en cualquier [duración del servicio](dependency-injection.md#service-lifetimes).

<xref:Microsoft.Extensions.Options.IOptionsSnapshot%601>:

- Es útil en escenarios en los que las opciones se deben volver a calcular en cada resolución de inserción, en [duraciones con ámbito o transitorias](dependency-injection.md#service-lifetimes). Para obtener más información, consulte el apartado [Uso de IOptionsSnapshot para leer datos actualizados](#use-ioptionssnapshot-to-read-updated-data).
- Se registra como [Con ámbito](dependency-injection.md#scoped) y, por tanto, no se puede insertar en un servicio Singleton.
- Admite [opciones con nombre](#named-options-support-using-iconfigurenamedoptions)

<xref:Microsoft.Extensions.Options.IOptionsMonitor%601>:

- se usa para recuperar las opciones y administrar las notificaciones de las opciones para instancias de `TOptions`.
- Se registra como [Singleton](dependency-injection.md#singleton) y se puede insertar en cualquier [duración del servicio](dependency-injection.md#service-lifetimes).
- Es compatible con:
  - Notificaciones de cambios
  - [Opciones con nombre](#named-options-support-using-iconfigurenamedoptions)
  - [Configuración que se puede recargar](#use-ioptionssnapshot-to-read-updated-data)
  - Invalidación de opciones de selección (<xref:Microsoft.Extensions.Options.IOptionsMonitorCache%601>)

<xref:Microsoft.Extensions.Options.IOptionsFactory%601> es responsable de crear nuevas instancias de opciones. Tiene un solo método <xref:Microsoft.Extensions.Options.IOptionsFactory%601.Create%2A>. La implementación predeterminada toma todas las instancias registradas de <xref:Microsoft.Extensions.Options.IConfigureOptions%601> y <xref:Microsoft.Extensions.Options.IPostConfigureOptions%601>, y establece todas las configuraciones primero, seguidas de las configuraciones posteriores. Distingue entre <xref:Microsoft.Extensions.Options.IConfigureNamedOptions%601> y <xref:Microsoft.Extensions.Options.IConfigureOptions%601>, y solo llama a la interfaz adecuada.

<xref:Microsoft.Extensions.Options.IOptionsMonitorCache%601> se usa por <xref:Microsoft.Extensions.Options.IOptionsMonitor%601> para almacenar en caché las instancias de `TOptions`. <xref:Microsoft.Extensions.Options.IOptionsMonitorCache%601> invalida instancias de opciones en la supervisión para que se pueda volver a calcular el valor (<xref:Microsoft.Extensions.Options.IOptionsMonitorCache%601.TryRemove%2A>). Los valores se pueden introducir manualmente y mediante <xref:Microsoft.Extensions.Options.IOptionsMonitorCache%601.TryAdd%2A>. Se usa el método <xref:Microsoft.Extensions.Options.IOptionsMonitorCache%601.Clear%2A> cuando todas las instancias con nombre se deben volver a crear a petición.

### <a name="options-interfaces-benefits"></a>Ventajas de las interfaces de opciones

El uso de un tipo de contenedor genérico proporciona la capacidad de desacoplar la duración de la opción del contenedor de DI. La interfaz <xref:Microsoft.Extensions.Options.IOptions%601.Value?displayProperty=nameWithType> proporciona una capa de abstracción, incluidas las restricciones genéricas, en el tipo de opciones. Esto proporciona las siguientes ventajas:

- La evaluación de la `T` instancia de configuración se aplaza al acceso de <xref:Microsoft.Extensions.Options.IOptions%601.Value?displayProperty=nameWithType>, en lugar de cuando se inserta. Esto es importante porque puede utilizar la opción `T` desde varios lugares y elegir la semántica de duración sin cambiar nada en `T`.
- Al registrar opciones de tipo `T`, no es necesario registrar explícitamente el tipo `T`. Esto se ofrece por comodidad cuando se [crea una biblioteca](options-library-authors.md) con valores predeterminados sencillos y no se desea obligar al autor de la llamada a registrar opciones en el contenedor de DI con una duración específica.
- Desde la perspectiva de la API, permite restricciones en el tipo `T` (en este caso, `T` está restringido a un tipo de referencia).

## <a name="use-ioptionssnapshot-to-read-updated-data"></a>Uso de IOptionsSnapshot para leer datos actualizados

Al usar <xref:Microsoft.Extensions.Options.IOptionsSnapshot%601>, las opciones se calculan una vez por solicitud al acceder y se almacenan en caché durante la vigencia de la solicitud. Los cambios en la configuración se leen tras iniciarse la aplicación al usar proveedores de configuración que admiten la lectura de valores de configuración actualizados.

La diferencia entre `IOptionsMonitor` y `IOptionsSnapshot` es que:

- `IOptionsMonitor` es un [servicio singleton](dependency-injection.md#singleton) que recupera los valores de las opciones actuales en cualquier momento, lo que resulta especialmente útil en las dependencias singleton.
- `IOptionsSnapshot` es un [servicio con ámbito](dependency-injection.md#scoped) y proporciona una instantánea de las opciones en el momento en que se construye el objeto `IOptionsSnapshot<T>`. Las instantáneas de opciones están diseñadas para usarlas con dependencias transitorias y con ámbito.

El código siguiente usa <xref:Microsoft.Extensions.Options.IOptionsSnapshot%601>.

:::code language="csharp" source="snippets/configuration/console-json/ScopedService.cs":::

El código siguiente registra una instancia de configuración en la que se enlaza `TransientFaultHandlingOptions`:

```csharp
services.Configure<TransientFaultHandlingOptions>(
    configurationRoot.GetSection(
        nameof(TransientFaultHandlingOptions)));
```

En el código anterior, los cambios en el archivo de configuración de JSON producidos una vez iniciada la aplicación se leen.

## <a name="ioptionsmonitor"></a>IOptionsMonitor

El código siguiente registra una instancia de configuración en la que se enlaza `TransientFaultHandlingOptions`.

```csharp
services.Configure<TransientFaultHandlingOptions>(
    configurationRoot.GetSection(
        nameof(TransientFaultHandlingOptions)));
```

En el ejemplo siguiente se usa <xref:Microsoft.Extensions.Options.IOptionsMonitor%601>:

:::code language="csharp" source="snippets/configuration/console-json/MonitorService.cs":::

En el código anterior, los cambios en el archivo de configuración de JSON producidos una vez iniciada la aplicación se leen.

## <a name="named-options-support-using-iconfigurenamedoptions"></a>Compatibilidad de opciones con nombre con IConfigureNamedOptions

Opciones con nombre:

- son útiles cuando varias secciones de configuración se enlazan a las mismas propiedades.
- Distinguen mayúsculas de minúsculas.

Fíjese en el siguiente archivo *appsettings.json*:

```json
{
  "Features": {
    "Personalize": {
      "Enabled": true,
      "ApiKey": "aGEgaGEgeW91IHRob3VnaHQgdGhhdCB3YXMgcmVhbGx5IHNvbWV0aGluZw=="
    },
    "WeatherStation": {
      "Enabled": true,
      "ApiKey": "QXJlIHlvdSBhdHRlbXB0aW5nIHRvIGhhY2sgdXM/"
    }
  }
}
```

En lugar de crear dos clases para enlazar `Features:Personalize` y `Features:WeatherStation`, se usará la clase siguiente para cada sección:

```csharp
public class Features
{
    public const string Personalize = nameof(Personalize);
    public const string WeatherStation = nameof(WeatherStation);

    public bool Enabled { get; set; }
    public string ApiKey { get; set; }
}
```

El siguiente código configura las opciones con nombre:

```csharp
ConfigureServices(services =>
{
    services.Configure<Features>(
        Features.Personalize,
        Configuration.GetSection("Features:Personalize"));

    services.Configure<Features>(
        Features.WeatherStation,
        Configuration.GetSection("Features:WeatherStation"));
});
```

En el código siguiente se muestran las opciones con nombre:

```csharp
public class Service
{
    private readonly Features _personalizeFeature;
    private readonly Features _weatherStationFeature;

    public Service(IOptionsSnapshot<Features> namedOptionsAccessor)
    {
        _personalizeFeature = namedOptionsAccessor.Get(Features.Personalize);
        _weatherStationFeature = namedOptionsAccessor.Get(Features.WeatherStation);
    }
}
```

Todas las opciones son instancias con nombre. Las instancias de <xref:Microsoft.Extensions.Options.IConfigureOptions%601> se usan para seleccionar como destino la instancia de `Options.DefaultName`, que es `string.Empty`. <xref:Microsoft.Extensions.Options.IConfigureNamedOptions%601> también implementa <xref:Microsoft.Extensions.Options.IConfigureOptions%601>. La implementación predeterminada de <xref:Microsoft.Extensions.Options.IOptionsFactory%601> tiene lógica para usar cada una de forma adecuada. La opción con nombre `null` se usa para seleccionar como destino todas las instancias con nombre, en lugar de una instancia con nombre determinada. <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.ConfigureAll%2A> y <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.PostConfigureAll%2A> usan esta convención.

## <a name="optionsbuilder-api"></a>API OptionsBuilder

<xref:Microsoft.Extensions.Options.OptionsBuilder%601> se usa para configurar instancias `TOptions`. `OptionsBuilder` simplifica la creación de opciones con nombre, ya que es un único parámetro para la llamada `AddOptions<TOptions>(string optionsName)` inicial en lugar de aparecer en todas las llamadas posteriores. La validación de opciones y las sobrecargas `ConfigureOptions` que aceptan las dependencias de servicio solo están disponibles mediante `OptionsBuilder`.

`OptionsBuilder` se usa en la sección [Opciones de validación](#options-validation).

## <a name="use-di-services-to-configure-options"></a>Uso de servicios de DI para configurar opciones

Hay dos formas de acceder a los servicios desde la inserción de dependencias durante la configuración de opciones:

- Si se pasa un delegado de configuración a [Configure](xref:Microsoft.Extensions.Options.OptionsBuilder%601.Configure%2A) en [OptionsBuilder\<TOptions>](xref:Microsoft.Extensions.Options.OptionsBuilder%601). `OptionsBuilder<TOptions>` proporciona sobrecargas de [Configure](xref:Microsoft.Extensions.Options.OptionsBuilder%601.Configure%2A) que permiten usar hasta cinco servicios para configurar las opciones:

  ```csharp
  services.AddOptions<MyOptions>("optionalName")
      .Configure<ExampleService, ScopedService, MonitorService>(
          (options, es, ss, ms) =>
              options.Property = DoSomethingWith(es, ss, ms));
  ```

- Si se crea un tipo que implementa <xref:Microsoft.Extensions.Options.IConfigureOptions%601> o <xref:Microsoft.Extensions.Options.IConfigureNamedOptions%601>, y se registra como un servicio.

Se recomienda pasar un delegado de configuración a [Configure](xref:Microsoft.Extensions.Options.OptionsBuilder%601.Configure%2A), ya que la creación de un servicio es más complicada. La creación de un tipo es equivalente a lo que el marco hace cuando se llama a [Configure](xref:Microsoft.Extensions.Options.OptionsBuilder%601.Configure%2A). La llamada a [Configure](xref:Microsoft.Extensions.Options.OptionsBuilder%601.Configure%2A) registra una interfaz <xref:Microsoft.Extensions.Options.IConfigureNamedOptions%601> genérica y transitoria, con un constructor que acepta los tipos de servicio genéricos especificados.

## <a name="options-validation"></a>Opciones de validación

Opciones de validación permite que se validen los valores de opción.

Fíjese en el siguiente archivo *appsettings.json*:

```json
{
  "Settings": {
    "SiteTitle": "Amazing docs from Awesome people!",
    "Scale": 10,
    "VerbosityLevel": 32
  }
}
```

La siguiente clase se enlaza a la sección de configuración `"Settings"` y aplica un par de reglas `DataAnnotations`:

:::code language="csharp" source="snippets/configuration/console-json/SettingsOptions.cs":::

El código siguiente:

- Llama a <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.AddOptions%2A> para obtener un elemento [OptionsBuilder\<TOptions>](xref:Microsoft.Extensions.Options.OptionsBuilder%601) que enlaza a la clase `SettingsOptions`.
- Llama a <xref:Microsoft.Extensions.DependencyInjection.OptionsBuilderDataAnnotationsExtensions.ValidateDataAnnotations%2A> para habilitar la validación con `DataAnnotations`.

```csharp
services.AddOptions<SettingsOptions>()
    .Bind(Configuration.GetSection(SettingsOptions.Settings))
    .ValidateDataAnnotations();
```

El método de extensión `ValidateDataAnnotations` se define en el paquete NuGet [Microsoft.Extensions.Options.DataAnnotations](https://www.nuget.org/packages/Microsoft.Extensions.Options.DataAnnotations).

En el código siguiente se muestran los valores de configuración o los errores de validación:

:::code language="csharp" source="snippets/configuration/console-json/ValidationService.cs":::

El código siguiente aplica una regla de validación más compleja mediante un delegado:

```csharp
services.AddOptions<SettingsOptions>()
    .Bind(Configuration.GetSection(SettingsOptions.Settings))
    .ValidateDataAnnotations()
    .Validate(config =>
    {
        if (config.Scale != 0)
        {
            return config.VerbosityLevel > config.Scale;
        }

        return true;
    }, "VerbosityLevel must be > than Scale.");
```

### <a name="ivalidateoptions-for-complex-validation"></a>IValidateOptions para la validación compleja

La siguiente clase implementa <xref:Microsoft.Extensions.Options.IValidateOptions%601>:

:::code language="csharp" source="snippets/configuration/console-json/ValidateSettingsOptions.cs":::

`IValidateOptions` permite mover el código de validación dentro de una clase.

Con el código anterior, la validación se habilita en `ConfigureServices` con el código siguiente:

```csharp
services.Configure<SettingsOptions>(
    Configuration.GetSection(
        SettingsOptions.Settings));
services.TryAddEnumerable(
    ServiceDescriptor.Singleton
        <IValidateOptions<SettingsOptions>, ValidateSettingsOptions>());
```

## <a name="options-post-configuration"></a>Configuración posterior de las opciones

Establezca la configuración posterior con <xref:Microsoft.Extensions.Options.IPostConfigureOptions%601>. Las tareas posteriores a la configuración se ejecutan una vez realizada toda la configuración de <xref:Microsoft.Extensions.Options.IConfigureOptions%601>, y pueden resultar útiles en los escenarios en los que es necesario invalidar la configuración:

```csharp
services.PostConfigure<CustomOptions>(customOptions =>
{
    customOptions.Option1 = "post_configured_option1_value";
});
```

<xref:Microsoft.Extensions.Options.IPostConfigureOptions%601.PostConfigure%2A> está disponible para configurar posteriormente las opciones con nombre:

```csharp
services.PostConfigure<CustomOptions>("named_options_1", customOptions =>
{
    customOptions.Option1 = "post_configured_option1_value";
});
```

Use <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.PostConfigureAll%2A> para configurar posteriormente todas las instancias de configuración:

```csharp
services.PostConfigureAll<CustomOptions>(customOptions =>
{
    customOptions.Option1 = "post_configured_option1_value";
});
```

## <a name="see-also"></a>Vea también

- [Configuración en .NET](configuration.md)
- [Guía sobre los patrones de opciones para creadores de bibliotecas de .NET](options-library-authors.md)
