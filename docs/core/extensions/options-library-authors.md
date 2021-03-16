---
title: Guía sobre los patrones de opciones para creadores de bibliotecas de .NET
author: IEvangelist
description: Obtenga información sobre cómo exponer el patrón de opciones como un autor de bibliotecas en .NET.
ms.author: dapine
ms.date: 01/28/2021
ms.openlocfilehash: d0da94a8f25c9e5aba6093fab07ccca6a0a7c345
ms.sourcegitcommit: 68c9d9d9a97aab3b59d388914004b5474cf1dbd7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "102402206"
---
# <a name="options-pattern-guidance-for-net-library-authors"></a>Guía sobre los patrones de opciones para creadores de bibliotecas de .NET

Con la ayuda de la inserción de dependencias, el registro de los servicios y sus configuraciones correspondientes pueden utilizar el *patrón de opciones*. El patrón de opciones permite a los consumidores de su biblioteca y a sus servicios requerir instancias de [interfaces de opciones](options.md#options-interfaces), donde `TOptions` es la clase de opciones. El consumo de opciones de configuración mediante objetos fuertemente tipados ayuda a garantizar una representación de valores coherente y elimina la carga de analizar manualmente los valores de cadena. Hay muchos [proveedores de configuración](configuration-providers.md) a los que los consumidores pueden recurrir. Con estos proveedores, los consumidores pueden configurar su biblioteca de muchas maneras.

Como autor de bibliotecas de .NET, conocerá instrucciones generales sobre cómo exponer correctamente el patrón de opciones a los consumidores de la biblioteca. Hay varias maneras de lograr lo mismo, y varias consideraciones que se deben contemplar.

## <a name="naming-conventions"></a>Convenciones de nomenclatura

Por convención, los métodos de extensión responsables del registro de servicios se denominan `Add{Service}`, donde `{Service}` es un nombre descriptivo y significativo. Dependiendo del paquete, el registro de servicios puede ir acompañado de los métodos de extensión `Use{Service}`. Los métodos de extensión `Use{Service}` son habituales en [ASP.NET Core](/aspnet).

✔️ CONSIDERE nombres que eliminan la ambigüedad de los servicios respecto a otras ofertas.

❌ NO utilice nombres que ya formen parte del ecosistema de .NET de los paquetes oficiales de Microsoft.

✔️ CONSIDERE la posibilidad de asignar nombres a clases estáticas que expongan métodos de extensión como `{Type}Extensions`, donde `{Type}` es el tipo que se va a extender.

### <a name="namespace-guidance"></a>Guía sobre los espacios de nombres

Los paquetes de Microsoft utilizan el espacio de nombres `Microsoft.Extensions.DependencyInjection` para unificar el registro de varias ofertas de servicio.

✔️ CONSIDERE un espacio de nombres que identifique claramente la oferta del paquete.

❌ NO use el espacio de nombres `Microsoft.Extensions.DependencyInjection` para los paquetes no oficiales de Microsoft.

## <a name="parameterless"></a>Sin parámetros

Si el servicio puede funcionar con una configuración mínima o no explícita, considere la posibilidad de usar un método de extensión sin parámetros.

:::code language="csharp" source="snippets/configuration/options-noparams/ServiceCollectionExtensions.cs" highlight="10-14":::

En el código anterior, `AddMyLibraryService`:

- extiende una instancia de <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>,
- llama a <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.AddOptions%60%601(Microsoft.Extensions.DependencyInjection.IServiceCollection)?displayProperty=nameWithType> con el parámetro de tipo de `LibraryOptions` y
- encadena una llamada a <xref:Microsoft.Extensions.Options.OptionsBuilder%601.Configure%2A>, que especifica los valores de opción predeterminados

## <a name="iconfiguration-parameter"></a>Parámetro `IConfiguration`

Cuando crea una biblioteca que expone muchas opciones a los consumidores, puede que desee considerar la posibilidad de requerir un método de extensión de parámetros `IConfiguration`. La instancia esperada `IConfiguration` debe tener como ámbito una sección con nombre de la configuración mediante la función <xref:Microsoft.Extensions.Configuration.IConfiguration.GetSection%2A?displayProperty=nameWithType>.

:::code language="csharp" source="snippets/configuration/options-configparam/ServiceCollectionExtensions.cs" highlight="10,12-16":::

En el código anterior, `AddMyLibraryService`:

- extiende una instancia de <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>,
- define un parámetro `namedConfigurationSection` de la interfaz <xref:Microsoft.Extensions.Configuration.IConfiguration> y
- llama a <xref:Microsoft.Extensions.Configuration.ConfigurationBinder.Bind(Microsoft.Extensions.Configuration.IConfiguration,System.Object)> para pasar una instancia de opciones a la que se enlaza la configuración.

Los consumidores de este patrón proporcionan la instancia con ámbito `IConfiguration` de la sección titulada:

:::code language="csharp" source="snippets/configuration/options-configparam/Program.cs" highlight="22-23":::

La llamada a `.AddMyLibraryService` se realiza en el método <xref:Microsoft.Extensions.Hosting.IHostBuilder.ConfigureServices%2A>. Lo mismo ocurre cuando se usa una clase `Startup`, y la adición de los servicios que se están registrando se produce en `ConfigureServices`.

Como autor de la biblioteca, la especificación de valores predeterminados depende de usted.

> [!NOTE]
> Es posible enlazar la configuración a una instancia de opciones. Sin embargo, existe el riesgo de que se produzcan conflictos de nombres, lo que provocará errores. Además, cuando se realiza un enlace manual de esta forma, se limita el consumo del patrón de opciones a una sola lectura. Los cambios en la configuración no se volverán a enlazar, ya que estos consumidores no podrán usar la interfaz [IOptionsMonitor](options.md#ioptionsmonitor).
>
> ```csharp
> services.AddOptions<LibraryOptions>()
>     .Configure<IConfiguration>(
>         (options, configuration) =>
>             configuration.GetSection("LibraryOptions").Bind(options));
> ```

## <a name="actiontoptions-parameter"></a>Parámetro `Action<TOptions>`

A los consumidores de la biblioteca les puede interesar proporcionar una expresión lambda que genere una instancia de la clase de opciones. En este escenario, se define un parámetro `Action<LibraryOptions>` en el método de extensión.

:::code language="csharp" source="snippets/configuration/options-action/ServiceCollectionExtensions.cs" highlight="10,12":::

En el código anterior, `AddMyLibraryService`:

- extiende una instancia de <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>,
- define <xref:System.Action%601>, donde `T` es el parámetro `configureOptions` de `LibraryOptions` y
- llama a <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.Configure%2A>, dada la acción `configureOptions`.

Los consumidores de este patrón proporcionan una expresión lambda, o bien un delegado que cumple el parámetro `Action<LibraryOptions>`:

:::code language="csharp" source="snippets/configuration/options-action/Program.cs" highlight="22-26":::

## <a name="options-instance-parameter"></a>Parámetro de la instancia de opciones

Es posible que los consumidores de la biblioteca prefieran proporcionar una instancia de opciones insertadas. En este escenario, se expone un método de extensión que adopta una instancia del objeto de opciones, `LibraryOptions`.

:::code language="csharp" source="snippets/configuration/options-object/ServiceCollectionExtensions.cs" highlight="9,11-17":::

En el código anterior, `AddMyLibraryService`:

- extiende una instancia de <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>,
- llama a <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.AddOptions%60%601(Microsoft.Extensions.DependencyInjection.IServiceCollection)?displayProperty=nameWithType> con el parámetro de tipo de `LibraryOptions` y
- encadena una llamada a <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.Configure%2A>, que especifica los valores de opción predeterminados que se pueden invalidar de la instancia `userOptions` especificada.

Los consumidores de este patrón proporcionan una instancia de la clase `LibraryOptions`, que define los valores de propiedad deseados insertados:

:::code language="csharp" source="snippets/configuration/options-object/Program.cs" highlight="22-26":::

## <a name="post-configuration"></a>Después de la configuración

Una vez que se han enlazado o especificado todos los valores de las opciones de configuración, está disponible la funcionalidad posterior a la configuración. Al exponer el mismo [parámetro `Action<TOptions>`](#actiontoptions-parameter) detallado anteriormente, podría optar por llamar a <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.PostConfigure%2A>. La configuración posterior se ejecuta después de todas las llamadas a `.Configure`.

:::code language="csharp" source="snippets/configuration/options-postconfig/ServiceCollectionExtensions.cs" highlight="10,12":::

En el código anterior, `AddMyLibraryService`:

- extiende una instancia de <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>,
- define <xref:System.Action%601>, donde `T` es el parámetro `configureOptions` de `LibraryOptions` y
- llama a <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.PostConfigure%2A>, dada la acción `configureOptions`.

Los consumidores de este patrón proporcionan una expresión lambda, o bien un delegado que cumple el parámetro `Action<LibraryOptions>`, del mismo modo que lo harían con el [parámetro `Action<TOptions>`] en un escenario que no es posterior a la configuración:

:::code language="csharp" source="snippets/configuration/options-postconfig/Program.cs" highlight="22-26":::

## <a name="see-also"></a>Vea también

- [Patrón de opciones en .NET](options.md)
- [Inserción de dependencias en .NET](dependency-injection.md)
- [Instrucciones para la inserción de dependencias](dependency-injection-guidelines.md)
