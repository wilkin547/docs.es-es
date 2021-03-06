---
title: Diferencias de configuración entre ASP.NET MVC y ASP.NET Core
description: La forma en que los valores de configuración se almacenan y cambian drásticamente entre ASP.NET y ASP.NET Core. En esta sección se examinan los detalles y cómo migrar la configuración de ASP.NET a ASP.NET Core.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 1e8e4d4ac408862f0216a5744476047186222304
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401788"
---
# <a name="configuration-differences-between-aspnet-mvc-and-aspnet-core"></a><span data-ttu-id="07628-104">Diferencias de configuración entre ASP.NET MVC y ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="07628-104">Configuration differences between ASP.NET MVC and ASP.NET Core</span></span>

<span data-ttu-id="07628-105">La forma en que los valores de configuración se almacenan y cambian drásticamente entre ASP.NET y ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="07628-105">How configuration values are stored and read changed dramatically between ASP.NET and ASP.NET Core.</span></span>

## <a name="aspnet-mvc-configuration"></a><span data-ttu-id="07628-106">Configuración de ASP.NET MVC</span><span class="sxs-lookup"><span data-stu-id="07628-106">ASP.NET MVC configuration</span></span>

<span data-ttu-id="07628-107">En ASP.NET Apps, la configuración usa los archivos de configuración de .NET integrados, *web.config* en la carpeta de la aplicación y *machine.config* en el servidor.</span><span class="sxs-lookup"><span data-stu-id="07628-107">In ASP.NET apps, configuration uses the built-in .NET configuration files, *web.config* in the app folder and *machine.config* on the server.</span></span> <span data-ttu-id="07628-108">La mayoría de las aplicaciones de ASP.NET MVC y Web API almacenan su configuración en los elementos o del archivo de configuración `appSettings` `connectionStrings` .</span><span class="sxs-lookup"><span data-stu-id="07628-108">Most ASP.NET MVC and Web API apps store their settings in the configuration file's `appSettings` or `connectionStrings` elements.</span></span> <span data-ttu-id="07628-109">Algunos también usan secciones de configuración personalizadas que se pueden asignar a una clase de configuración.</span><span class="sxs-lookup"><span data-stu-id="07628-109">Some also use custom configuration sections that can be mapped to a settings class.</span></span>

<span data-ttu-id="07628-110">Se tiene acceso a la configuración en una aplicación .NET Framework mediante la `System.Configuration.ConfigurationManager` clase.</span><span class="sxs-lookup"><span data-stu-id="07628-110">Configuration in a .NET Framework app is accessed using the `System.Configuration.ConfigurationManager` class.</span></span> <span data-ttu-id="07628-111">Desafortunadamente, esta clase proporciona acceso estático a los elementos de configuración.</span><span class="sxs-lookup"><span data-stu-id="07628-111">Unfortunately, this class provides static access to the configuration elements.</span></span> <span data-ttu-id="07628-112">Como resultado, muy pocas aplicaciones ASP.NET MVC tienden a abstraer el acceso a sus valores de configuración o inyectarlos cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="07628-112">As a result, very few ASP.NET MVC apps tend to abstract access to their configuration settings or inject them where needed.</span></span> <span data-ttu-id="07628-113">En su lugar, la mayoría de las aplicaciones .NET Framework tienden a acceder directamente al sistema de configuración en cualquier lugar en el que la aplicación necesite usar una configuración.</span><span class="sxs-lookup"><span data-stu-id="07628-113">Instead, most .NET Framework apps tend to directly access the configuration system anywhere the app needs to use a setting.</span></span>

<span data-ttu-id="07628-114">Acceso de configuración de MVC de ASP.NET típico:</span><span class="sxs-lookup"><span data-stu-id="07628-114">Typical ASP.NET MVC configuration access:</span></span>

```csharp
string connectionString =
    ConfigurationManager.ConnectionStrings["DefaultConnection"]
        .ConnectionString;
```

## <a name="aspnet-core-configuration"></a><span data-ttu-id="07628-115">Configuración de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="07628-115">ASP.NET Core configuration</span></span>

<span data-ttu-id="07628-116">En ASP.NET Core aplicaciones, la configuración es, en sí misma, configurable.</span><span class="sxs-lookup"><span data-stu-id="07628-116">In ASP.NET Core apps, configuration is, itself, configurable.</span></span> <span data-ttu-id="07628-117">Sin embargo, la mayoría de las aplicaciones usan un conjunto de valores predeterminados que se proporcionan como parte de las plantillas de proyecto estándar y el método que se `ConfigureWebHostDefaults` usa en ellos.</span><span class="sxs-lookup"><span data-stu-id="07628-117">However, most apps use a set of defaults provided as part of the standard project templates and the `ConfigureWebHostDefaults` method used in them.</span></span> <span data-ttu-id="07628-118">La configuración predeterminada usa archivos con formato JSON, con la capacidad de invalidar la configuración del *appsettings.jsbase en* el archivo con archivos específicos del entorno, como *appsettings.Development.jsen*.</span><span class="sxs-lookup"><span data-stu-id="07628-118">The default settings use JSON formatted files, with the ability to override settings in the base *appsettings.json* file with environment-specific files like *appsettings.Development.json*.</span></span> <span data-ttu-id="07628-119">Además, el sistema de configuración predeterminado invalida aún más todas las configuraciones basadas en archivos con cualquier variable de entorno que exista para la misma configuración con nombre.</span><span class="sxs-lookup"><span data-stu-id="07628-119">Additionally, the default configuration system further overrides all file-based settings with any environment variable that exists for the same named setting.</span></span> <span data-ttu-id="07628-120">Esto es útil en muchos escenarios y es especialmente útil cuando se implementa en un entorno de hospedaje, ya que elimina la necesidad de preocuparse de si la implementación de archivos de configuración sobrescribirá accidentalmente importantes opciones de configuración de producción.</span><span class="sxs-lookup"><span data-stu-id="07628-120">This is useful in many scenarios and is especially useful when deploying to a hosting environment, since it eliminates the need to worry about whether deploying configuration files will accidentally overwrite important production configuration settings.</span></span> <span data-ttu-id="07628-121">Los valores de configuración también se pueden proporcionar como argumentos de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="07628-121">Configuration values can also be provided as command line arguments.</span></span>

<span data-ttu-id="07628-122">El acceso a los valores de configuración se puede realizar de muchas maneras en .NET Core.</span><span class="sxs-lookup"><span data-stu-id="07628-122">Accessing configuration values can be done in many ways in .NET Core.</span></span> <span data-ttu-id="07628-123">Dado que la inserción de dependencias está integrada en .NET Core, generalmente se tiene acceso a los valores de configuración a través de una interfaz que se inserta en las clases que los necesitan.</span><span class="sxs-lookup"><span data-stu-id="07628-123">Because dependency injection is built into .NET Core, configuration values are generally accessed through an interface that is injected into classes that need them.</span></span> <span data-ttu-id="07628-124">Esto puede implicar pasar una interfaz como <xref:Microsoft.Extensions.Configuration.IConfiguration> , pero normalmente es mejor pasar solo la configuración requerida por la clase mediante el [patrón de opciones](/aspnet/core/fundamentals/configuration/options).</span><span class="sxs-lookup"><span data-stu-id="07628-124">This can involve passing a interface like <xref:Microsoft.Extensions.Configuration.IConfiguration>, but usually it's better to pass just the settings required by the class using the [options pattern](/aspnet/core/fundamentals/configuration/options).</span></span>

<span data-ttu-id="07628-125">En la figura 2-2 se muestra cómo pasar a `IConfiguration` una página de Razor y cómo acceder a la configuración desde ella:</span><span class="sxs-lookup"><span data-stu-id="07628-125">Figure 2-2 shows how to pass `IConfiguration` into a Razor Page and access configuration settings from it:</span></span>

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

<span data-ttu-id="07628-126">**Figura 2-2.**</span><span class="sxs-lookup"><span data-stu-id="07628-126">**Figure 2-2.**</span></span> <span data-ttu-id="07628-127">Obtener acceso a los valores de configuración con `IConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="07628-127">Accessing configuration values with `IConfiguration`.</span></span>

<span data-ttu-id="07628-128">Con el patrón de opciones, el acceso a la configuración es similar, pero está fuertemente tipado y es más específico para las configuraciones que necesita la clase de consumo, como muestra la figura 2-3.</span><span class="sxs-lookup"><span data-stu-id="07628-128">Using the options pattern, settings access is similar but is strongly typed and more specific to the setting(s) needed by the consuming class, as Figure 2-3 demonstrates.</span></span>

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

<span data-ttu-id="07628-129">**Figura 2-3.**</span><span class="sxs-lookup"><span data-stu-id="07628-129">**Figure 2-3.**</span></span> <span data-ttu-id="07628-130">Usar el patrón de opciones en ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="07628-130">Using the options pattern in ASP.NET Core.</span></span>

<span data-ttu-id="07628-131">Para que el patrón de opciones funcione, el tipo de opciones se debe configurar en `ConfigureServices` cuando se inicia la aplicación:</span><span class="sxs-lookup"><span data-stu-id="07628-131">For the options pattern to work, the options type must be configured in `ConfigureServices` when the app starts up:</span></span>

```csharp
// required in ConfigureServices
services.Configure<PositionOptions>(Configuration.GetSection(PositionOptions.Position));
```

## <a name="migrate-configuration"></a><span data-ttu-id="07628-132">Migración de la configuración</span><span class="sxs-lookup"><span data-stu-id="07628-132">Migrate configuration</span></span>

<span data-ttu-id="07628-133">Al considerar cómo trasladar la configuración de una aplicación de .NET Framework a .NET Core, el primer paso es identificar todas las opciones de configuración que se están usando.</span><span class="sxs-lookup"><span data-stu-id="07628-133">When considering how to port an app's configuration settings from .NET Framework to .NET Core, the first step is to identify all of the configuration settings that are being used.</span></span> <span data-ttu-id="07628-134">La mayoría de ellas estarán en el archivo *web.config* en la carpeta raíz de la aplicación, pero algunas aplicaciones esperan que la configuración se encuentre también en el archivo de *machine.config* compartido.</span><span class="sxs-lookup"><span data-stu-id="07628-134">Most of these will be in the *web.config* file in the app's root folder, but some apps expect settings to be found in the shared *machine.config* file as well.</span></span>

<span data-ttu-id="07628-135">Una vez que se han catalogado todos los valores de configuración de los archivos de configuración, el paso siguiente debe ser identificar dónde y cómo se utiliza la configuración en la propia aplicación.</span><span class="sxs-lookup"><span data-stu-id="07628-135">Once all settings in the config files have been cataloged, the next step should be to identify where and how the settings are used in the app itself.</span></span> <span data-ttu-id="07628-136">Si no se usan algunos valores, probablemente se omitan de la migración.</span><span class="sxs-lookup"><span data-stu-id="07628-136">If some settings aren't being used, these can probably be omitted from the migration.</span></span> <span data-ttu-id="07628-137">Para cada configuración, tenga en cuenta todos los lugares en los que se está usando, por lo que puede estar seguro de que no se pierde nada al migrar el código.</span><span class="sxs-lookup"><span data-stu-id="07628-137">For each setting, note all of the places it's being used so you can be sure you don't miss any when you migrate the code.</span></span>

<span data-ttu-id="07628-138">Si todavía está manteniendo la aplicación ASP.NET, puede ser útil evitar referencias estáticas a `ConfigurationManager` y reemplazarlas por el acceso a través de las interfaces.</span><span class="sxs-lookup"><span data-stu-id="07628-138">If you're still maintaining the ASP.NET app, it may be helpful to avoid static references to `ConfigurationManager` and replace them with access through interfaces.</span></span> <span data-ttu-id="07628-139">Esto facilitará la transición al sistema de configuración de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="07628-139">This will ease the transition to ASP.NET Core's configuration system.</span></span> <span data-ttu-id="07628-140">En general, el acceso estático a los recursos externos hace que el código sea más difícil de probar y mantener, por lo que debe estar atento a cualquier lugar en el que la aplicación siga este patrón.</span><span class="sxs-lookup"><span data-stu-id="07628-140">In general, static access to external resources makes code harder to test and maintain, so be on the lookout for anywhere else the app may be following this pattern.</span></span>

## <a name="references"></a><span data-ttu-id="07628-141">Referencias</span><span class="sxs-lookup"><span data-stu-id="07628-141">References</span></span>

- [<span data-ttu-id="07628-142">Configuración en ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="07628-142">Configuration in ASP.NET Core</span></span>](/aspnet/core/fundamentals/configuration/)
- [<span data-ttu-id="07628-143">Patrón de opciones en ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="07628-143">Options pattern in ASP.NET Core</span></span>](/aspnet/core/fundamentals/configuration/options)
- [<span data-ttu-id="07628-144">Migrar la configuración a ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="07628-144">Migrate configuration to ASP.NET Core</span></span>](/aspnet/core/migration/configuration)
- [<span data-ttu-id="07628-145">Refactorizar el acceso a la configuración estática</span><span class="sxs-lookup"><span data-stu-id="07628-145">Refactoring Static Config Access</span></span>](https://ardalis.com/refactoring-static-config-access/)

>[!div class="step-by-step"]
><span data-ttu-id="07628-146">[Anterior](middleware-modules-handlers.md)
>[Siguiente](routing-differences.md)</span><span class="sxs-lookup"><span data-stu-id="07628-146">[Previous](middleware-modules-handlers.md)
[Next](routing-differences.md)</span></span>
