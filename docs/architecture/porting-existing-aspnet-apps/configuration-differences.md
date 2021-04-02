---
title: Diferencias de configuración entre ASP.NET MVC y ASP.NET Core
description: La forma en que los valores de configuración se almacenan y cambian drásticamente entre ASP.NET y ASP.NET Core. En esta sección se examinan los detalles y cómo migrar la configuración de ASP.NET a ASP.NET Core.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 3d721c028b1e760a6227855451e2194d9e471a58
ms.sourcegitcommit: b5d2290673e1c91260c9205202dd8b95fbab1a0b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "106122955"
---
# <a name="configuration-differences-between-aspnet-mvc-and-aspnet-core"></a>Diferencias de configuración entre ASP.NET MVC y ASP.NET Core

La forma en que los valores de configuración se almacenan y cambian drásticamente entre ASP.NET y ASP.NET Core.

## <a name="aspnet-mvc-configuration"></a>Configuración de ASP.NET MVC

En ASP.NET Apps, la configuración usa los archivos de configuración de .NET integrados, *web.config* en la carpeta de la aplicación y *machine.config* en el servidor. La mayoría de las aplicaciones de ASP.NET MVC y Web API almacenan su configuración en los elementos o del archivo de configuración `appSettings` `connectionStrings` . Algunos también usan secciones de configuración personalizadas que se pueden asignar a una clase de configuración.

Se tiene acceso a la configuración en una aplicación .NET Framework mediante la `System.Configuration.ConfigurationManager` clase. Desafortunadamente, esta clase proporciona acceso estático a los elementos de configuración. Como resultado, muy pocas aplicaciones ASP.NET MVC tienden a abstraer el acceso a sus valores de configuración o inyectarlos cuando sea necesario. En su lugar, la mayoría de las aplicaciones .NET Framework tienden a acceder directamente al sistema de configuración en cualquier lugar en el que la aplicación necesite usar una configuración.

Acceso de configuración de MVC de ASP.NET típico:

```csharp
string connectionString =
    ConfigurationManager.ConnectionStrings["DefaultConnection"]
        .ConnectionString;
```

## <a name="aspnet-core-configuration"></a>Configuración de ASP.NET Core

En ASP.NET Core aplicaciones, la configuración es, en sí misma, configurable. Sin embargo, la mayoría de las aplicaciones usan un conjunto de valores predeterminados que se proporcionan como parte de las plantillas de proyecto estándar y el método que se `ConfigureWebHostDefaults` usa en ellos. La configuración predeterminada usa archivos con formato JSON, con la capacidad de invalidar la configuración del *appsettings.jsbase en* el archivo con archivos específicos del entorno, como *appsettings.Development.jsen*. Además, el sistema de configuración predeterminado invalida aún más todas las configuraciones basadas en archivos con cualquier variable de entorno que exista para la misma configuración con nombre. Esto es útil en muchos escenarios y es especialmente útil cuando se implementa en un entorno de hospedaje, ya que elimina la necesidad de preocuparse de si la implementación de archivos de configuración sobrescribirá accidentalmente importantes opciones de configuración de producción. Los valores de configuración también se pueden proporcionar como argumentos de la línea de comandos.

El acceso a los valores de configuración se puede realizar de muchas maneras en .NET Core. Dado que la inserción de dependencias está integrada en .NET Core, generalmente se tiene acceso a los valores de configuración a través de una interfaz que se inserta en las clases que los necesitan. Esto puede implicar pasar una interfaz como <xref:Microsoft.Extensions.Configuration.IConfiguration> , pero normalmente es mejor pasar solo la configuración requerida por la clase mediante el [patrón de opciones](/aspnet/core/fundamentals/configuration/options).

En la figura 2-2 se muestra cómo pasar a `IConfiguration` una página de Razor y cómo acceder a la configuración desde ella:

```csharp
using Microsoft.Extensions.Configuration;

public class TestModel : PageModel
{
    private readonly IConfiguration _configuration;

    public TestModel(IConfiguration configuration)
    {
        _configuration= configuration;
    }

    public ContentResult OnGet()
    {
        var myKeyValue = _configuration["MyKey"];

        // ...
    }
}
```

**Figura 2-2.** Obtener acceso a los valores de configuración con `IConfiguration` .

Con el [patrón de opciones](/dotnet/core/extensions/options), el acceso a la configuración es similar, pero está fuertemente tipado y es más específico para las configuraciones que necesita la clase de consumo, como muestra la figura 2-3.

```csharp
public class PositionOptions
{
    public const string Position = nameof(Position);

    public string Title { get; set; }
    public string Name { get; set; }
}

public class Test2Model : PageModel
{
    private readonly PositionOptions _options;

    public Test2Model(IOptions<PositionOptions> options)
    {
        _options = options.Value;
    }

    public ContentResult OnGet()
    {
        return Content($"Title: {_options.Title}\nName: {_options.Name}");
    }
}
```

**Figura 2-3.** Usar el patrón de opciones en ASP.NET Core.

Para que el patrón de opciones funcione, el tipo de opciones se debe configurar en `ConfigureServices` cuando se inicia la aplicación:

```csharp
// required in ConfigureServices
services.Configure<PositionOptions>(Configuration.GetSection(PositionOptions.Position));
```

## <a name="migrate-configuration"></a>Migración de la configuración

Al considerar cómo trasladar la configuración de una aplicación de .NET Framework a .NET Core, el primer paso es identificar todas las opciones de configuración que se están usando. La mayoría de ellas estarán en el archivo *web.config* en la carpeta raíz de la aplicación, pero algunas aplicaciones esperan que la configuración se encuentre también en el archivo de *machine.config* compartido. Esta configuración incluirá también los elementos del `appSettings` elemento, el `connectionStrings` elemento y los elementos de configuración personalizados. En .NET Core, todas estas opciones de configuración se almacenan normalmente en el *appsettings.jsen* el archivo.

Una vez que se han catalogado todos los valores de configuración de los archivos de configuración, el paso siguiente debe ser identificar dónde y cómo se utiliza la configuración en la propia aplicación. Si no se usan algunos valores, probablemente se omitan de la migración. Para cada configuración, tenga en cuenta todos los lugares en los que se está usando, por lo que puede estar seguro de que no se pierde nada al migrar el código.

Si todavía está manteniendo la aplicación ASP.NET, puede ser útil evitar referencias estáticas a `ConfigurationManager` y reemplazarlas por el acceso a través de las interfaces. Esto facilitará la transición al sistema de configuración de ASP.NET Core. En general, el acceso estático a los recursos externos hace que el código sea más difícil de probar y mantener, por lo que debe estar atento a cualquier lugar en el que la aplicación siga este patrón.

## <a name="references"></a>Referencias

- [Configuración en ASP.NET Core](/aspnet/core/fundamentals/configuration/)
- [Patrón de opciones en ASP.NET Core](/aspnet/core/fundamentals/configuration/options)
- [Migrar la configuración a ASP.NET Core](/aspnet/core/migration/configuration)
- [Refactorizar el acceso a la configuración estática](https://ardalis.com/refactoring-static-config-access/)

>[!div class="step-by-step"]
>[Anterior](middleware-modules-handlers.md)
>[Siguiente](routing-differences.md)
