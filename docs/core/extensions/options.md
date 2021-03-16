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
# <a name="options-pattern-in-net"></a><span data-ttu-id="9ceec-103">Patrón de opciones en .NET</span><span class="sxs-lookup"><span data-stu-id="9ceec-103">Options pattern in .NET</span></span>

<span data-ttu-id="9ceec-104">El patrón de opciones usa clases para proporcionar acceso fuertemente tipado a grupos de configuraciones relacionadas.</span><span class="sxs-lookup"><span data-stu-id="9ceec-104">The options pattern uses classes to provide strongly-typed access to groups of related settings.</span></span> <span data-ttu-id="9ceec-105">Cuando los [valores de configuración](configuration.md) están aislados por escenario en clases independientes, la aplicación se ajusta a dos principios de ingeniería de software importantes:</span><span class="sxs-lookup"><span data-stu-id="9ceec-105">When [configuration settings](configuration.md) are isolated by scenario into separate classes, the app adheres to two important software engineering principles:</span></span>

- <span data-ttu-id="9ceec-106">El [principio de segregación de interfaz (ISP) o encapsulación](../../architecture/modern-web-apps-azure/architectural-principles.md#encapsulation): los escenarios (clases) que dependen de valores de configuración dependen únicamente de los valores de configuración que usen.</span><span class="sxs-lookup"><span data-stu-id="9ceec-106">The [Interface Segregation Principle (ISP) or Encapsulation](../../architecture/modern-web-apps-azure/architectural-principles.md#encapsulation): Scenarios (classes) that depend on configuration settings depend only on the configuration settings that they use.</span></span>
- <span data-ttu-id="9ceec-107">[Separación de intereses](../../architecture/modern-web-apps-azure/architectural-principles.md#separation-of-concerns): los valores de configuración para distintos elementos de la aplicación no son dependientes entre sí ni están emparejados.</span><span class="sxs-lookup"><span data-stu-id="9ceec-107">[Separation of Concerns](../../architecture/modern-web-apps-azure/architectural-principles.md#separation-of-concerns): Settings for different parts of the app aren't dependent or coupled to one another.</span></span>

<span data-ttu-id="9ceec-108">Las opciones también proporcionan un mecanismo para validar los datos de configuración.</span><span class="sxs-lookup"><span data-stu-id="9ceec-108">Options also provide a mechanism to validate configuration data.</span></span> <span data-ttu-id="9ceec-109">Para obtener más información, consulte la sección [Opciones de validación](#options-validation).</span><span class="sxs-lookup"><span data-stu-id="9ceec-109">For more information, see the [Options validation](#options-validation) section.</span></span>

## <a name="bind-hierarchical-configuration"></a><span data-ttu-id="9ceec-110">Enlace de configuración jerárquica</span><span class="sxs-lookup"><span data-stu-id="9ceec-110">Bind hierarchical configuration</span></span>

<span data-ttu-id="9ceec-111">La mejor manera de leer valores de configuración relacionados es usar el patrón de opciones.</span><span class="sxs-lookup"><span data-stu-id="9ceec-111">The preferred way to read related configuration values is using the options pattern.</span></span> <span data-ttu-id="9ceec-112">El patrón de opciones se puede aplicar mediante la interfaz <xref:Microsoft.Extensions.Options.IOptions%601>, donde el parámetro de tipo genérico `TOptions` está restringido a `class`.</span><span class="sxs-lookup"><span data-stu-id="9ceec-112">The options pattern is possible through the <xref:Microsoft.Extensions.Options.IOptions%601> interface, where the generic type parameter `TOptions` is constrained to `class`.</span></span> <span data-ttu-id="9ceec-113">`IOptions<TOptions>` se puede proporcionar posteriormente mediante la inserción de dependencias.</span><span class="sxs-lookup"><span data-stu-id="9ceec-113">The `IOptions<TOptions>` can later be provided through dependency injection.</span></span> <span data-ttu-id="9ceec-114">Para más información, vea [Inserción de dependencias en .NET](dependency-injection.md).</span><span class="sxs-lookup"><span data-stu-id="9ceec-114">For more information, see [Dependency injection in .NET](dependency-injection.md).</span></span>

<span data-ttu-id="9ceec-115">Por ejemplo, para leer los siguientes valores de configuración:</span><span class="sxs-lookup"><span data-stu-id="9ceec-115">For example, to read the following configuration values:</span></span>

:::code language="json" source="snippets/configuration/console-json/appsettings.json" range="3-6":::

<span data-ttu-id="9ceec-116">Cree la siguiente clase `TransientFaultHandlingOptions`:</span><span class="sxs-lookup"><span data-stu-id="9ceec-116">Create the following `TransientFaultHandlingOptions` class:</span></span>

:::code language="csharp" source="snippets/configuration/console-json/TransientFaultHandlingOptions.cs" range="5-9":::

<span data-ttu-id="9ceec-117"><span id="options-class"></span> Al usar el patrón de opciones, una clase de opciones:</span><span class="sxs-lookup"><span data-stu-id="9ceec-117"><span id="options-class"></span> When using the options pattern, an options class:</span></span>

- <span data-ttu-id="9ceec-118">Debe ser no abstracta con un constructor público sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="9ceec-118">Must be non-abstract with a public parameterless constructor</span></span>
- <span data-ttu-id="9ceec-119">Debe contener propiedades de lectura y escritura para enlazar (los campos ***no*** están enlazados).</span><span class="sxs-lookup"><span data-stu-id="9ceec-119">Contain public read-write properties to bind (fields are ***not*** bound)</span></span>

<span data-ttu-id="9ceec-120">El código siguiente:</span><span class="sxs-lookup"><span data-stu-id="9ceec-120">The following code:</span></span>

* <span data-ttu-id="9ceec-121">Llama a [ConfigurationBinder.Bind](xref:Microsoft.Extensions.Configuration.ConfigurationBinder.Bind%2A) para enlazar la clase `TransientFaultHandlingOptions` a la sección `"TransientFaultHandlingOptions"`.</span><span class="sxs-lookup"><span data-stu-id="9ceec-121">Calls [ConfigurationBinder.Bind](xref:Microsoft.Extensions.Configuration.ConfigurationBinder.Bind%2A) to bind the `TransientFaultHandlingOptions` class to the `"TransientFaultHandlingOptions"` section.</span></span>
* <span data-ttu-id="9ceec-122">Muestra los datos de configuración.</span><span class="sxs-lookup"><span data-stu-id="9ceec-122">Displays the configuration data.</span></span>

:::code language="csharp" source="snippets/configuration/console-json/Program.cs" range="31-38":::

<span data-ttu-id="9ceec-123">En el código anterior, los cambios en el archivo de configuración de JSON producidos una vez iniciada la aplicación se leen.</span><span class="sxs-lookup"><span data-stu-id="9ceec-123">In the preceding code, changes to the JSON configuration file after the app has started are read.</span></span>

<span data-ttu-id="9ceec-124">[`ConfigurationBinder.Get<T>`](xref:Microsoft.Extensions.Configuration.ConfigurationBinder.Get%2A) enlaza y devuelve el tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="9ceec-124">[`ConfigurationBinder.Get<T>`](xref:Microsoft.Extensions.Configuration.ConfigurationBinder.Get%2A) binds and returns the specified type.</span></span> <span data-ttu-id="9ceec-125">Puede ser más conveniente usar `ConfigurationBinder.Get<T>` que `ConfigurationBinder.Bind`.</span><span class="sxs-lookup"><span data-stu-id="9ceec-125">`ConfigurationBinder.Get<T>` may be more convenient than using `ConfigurationBinder.Bind`.</span></span> <span data-ttu-id="9ceec-126">En el código siguiente se muestra cómo puede usar `ConfigurationBinder.Get<T>` con la clase `TransientFaultHandlingOptions`:</span><span class="sxs-lookup"><span data-stu-id="9ceec-126">The following code shows how to use `ConfigurationBinder.Get<T>` with the `TransientFaultHandlingOptions` class:</span></span>

```csharp
IConfigurationRoot configurationRoot = configuration.Build();

var options =
    configurationRoot.GetSection(nameof(TransientFaultHandlingOptions))
                     .Get<TransientFaultHandlingOptions>();

Console.WriteLine($"TransientFaultHandlingOptions.Enabled={options.Enabled}");
Console.WriteLine($"TransientFaultHandlingOptions.AutoRetryDelay={options.AutoRetryDelay}");
```

<span data-ttu-id="9ceec-127">En el código anterior, los cambios en el archivo de configuración de JSON producidos una vez iniciada la aplicación se leen.</span><span class="sxs-lookup"><span data-stu-id="9ceec-127">In the preceding code, changes to the JSON configuration file after the app has started are read.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9ceec-128">La clase <xref:Microsoft.Extensions.Configuration.ConfigurationBinder> expone varias API, como `.Bind(object instance)` y `.Get<T>()`, que ***no*** están restringidas a `class`.</span><span class="sxs-lookup"><span data-stu-id="9ceec-128">The <xref:Microsoft.Extensions.Configuration.ConfigurationBinder> class exposes several APIs, such as `.Bind(object instance)` and `.Get<T>()` that are ***not*** constrained to `class`.</span></span> <span data-ttu-id="9ceec-129">Al utilizar cualquiera de las [interfaces de opciones](#options-interfaces), debe cumplir las [restricciones de la clase de opciones](#options-class) mencionadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="9ceec-129">When using any of the [Options interfaces](#options-interfaces), you must adhere to aforementioned [options class constraints](#options-class).</span></span>

<span data-ttu-id="9ceec-130">Un enfoque alternativo a la hora de usar el patrón de opciones consiste en enlazar la sección `"TransientFaultHandlingOptions"` y agregarla al [contenedor del servicio de inserción de dependencias](dependency-injection.md).</span><span class="sxs-lookup"><span data-stu-id="9ceec-130">An alternative approach when using the options pattern is to bind the `"TransientFaultHandlingOptions"` section and add it to the [dependency injection service container](dependency-injection.md).</span></span> <span data-ttu-id="9ceec-131">En el siguiente código se agrega `TransientFaultHandlingOptions` al contenedor de servicios con <xref:Microsoft.Extensions.DependencyInjection.OptionsConfigurationServiceCollectionExtensions.Configure%2A> y se enlaza a la configuración:</span><span class="sxs-lookup"><span data-stu-id="9ceec-131">In the following code, `TransientFaultHandlingOptions` is added to the service container with <xref:Microsoft.Extensions.DependencyInjection.OptionsConfigurationServiceCollectionExtensions.Configure%2A> and bound to configuration:</span></span>

```csharp
services.Configure<TransientFaultHandlingOptions>(
    configurationRoot.GetSection(
        key: nameof(TransientFaultHandlingOptions)));
```

> [!TIP]
> <span data-ttu-id="9ceec-132">El parámetro `key` es el nombre de la sección de configuración que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="9ceec-132">The `key` parameter is the name of the configuration section to search for.</span></span> <span data-ttu-id="9ceec-133">*No* tiene que coincidir con el nombre del tipo que la representa.</span><span class="sxs-lookup"><span data-stu-id="9ceec-133">It does *not* have to match the name of the type that represents it.</span></span> <span data-ttu-id="9ceec-134">Por ejemplo, podría tener una sección denominada `"FaultHandling"` y podría estar representada por la clase `TransientFaultHandlingOptions`.</span><span class="sxs-lookup"><span data-stu-id="9ceec-134">For example, you could have a section named `"FaultHandling"` and it could be represented by the `TransientFaultHandlingOptions` class.</span></span> <span data-ttu-id="9ceec-135">En esta instancia, en su lugar, debe pasar `"FaultHandling"` a la función <xref:Microsoft.Extensions.Configuration.IConfiguration.GetSection%2A>.</span><span class="sxs-lookup"><span data-stu-id="9ceec-135">In this instance, you'd pass `"FaultHandling"` to the <xref:Microsoft.Extensions.Configuration.IConfiguration.GetSection%2A> function instead.</span></span> <span data-ttu-id="9ceec-136">El operador `nameof` se utiliza por comodidad cuando la sección con nombre coincide con el tipo al que corresponde.</span><span class="sxs-lookup"><span data-stu-id="9ceec-136">The `nameof` operator is used as a convenience when the named section matches the type it corresponds to.</span></span>

<span data-ttu-id="9ceec-137">A partir del código anterior, el siguiente código lee las opciones de posición:</span><span class="sxs-lookup"><span data-stu-id="9ceec-137">Using the preceding code, the following code reads the position options:</span></span>

:::code language="csharp" source="snippets/configuration/console-json/ExampleService.cs":::

<span data-ttu-id="9ceec-138">En el código anterior, los cambios en el archivo de configuración de JSON producidos una vez iniciada la aplicación ***no*** se leen.</span><span class="sxs-lookup"><span data-stu-id="9ceec-138">In the preceding code, changes to the JSON configuration file after the app has started are ***not*** read.</span></span> <span data-ttu-id="9ceec-139">Para leer los cambios una vez iniciada la aplicación, use [IOptionsSnapshot](#use-ioptionssnapshot-to-read-updated-data).</span><span class="sxs-lookup"><span data-stu-id="9ceec-139">To read changes after the app has started, use [IOptionsSnapshot](#use-ioptionssnapshot-to-read-updated-data).</span></span>

## <a name="options-interfaces"></a><span data-ttu-id="9ceec-140">Interfaces de opciones</span><span class="sxs-lookup"><span data-stu-id="9ceec-140">Options interfaces</span></span>

<span data-ttu-id="9ceec-141"><xref:Microsoft.Extensions.Options.IOptions%601>:</span><span class="sxs-lookup"><span data-stu-id="9ceec-141"><xref:Microsoft.Extensions.Options.IOptions%601>:</span></span>

- <span data-ttu-id="9ceec-142">***No*** admite:</span><span class="sxs-lookup"><span data-stu-id="9ceec-142">Does ***not*** support:</span></span>
  - <span data-ttu-id="9ceec-143">Lectura de los datos de configuración una vez iniciada la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9ceec-143">Reading of configuration data after the app has started.</span></span>
  - [<span data-ttu-id="9ceec-144">Opciones con nombre</span><span class="sxs-lookup"><span data-stu-id="9ceec-144">Named options</span></span>](#named-options-support-using-iconfigurenamedoptions)
- <span data-ttu-id="9ceec-145">Se registra como [Singleton](dependency-injection.md#singleton) y se puede insertar en cualquier [duración del servicio](dependency-injection.md#service-lifetimes).</span><span class="sxs-lookup"><span data-stu-id="9ceec-145">Is registered as a [Singleton](dependency-injection.md#singleton) and can be injected into any [service lifetime](dependency-injection.md#service-lifetimes).</span></span>

<span data-ttu-id="9ceec-146"><xref:Microsoft.Extensions.Options.IOptionsSnapshot%601>:</span><span class="sxs-lookup"><span data-stu-id="9ceec-146"><xref:Microsoft.Extensions.Options.IOptionsSnapshot%601>:</span></span>

- <span data-ttu-id="9ceec-147">Es útil en escenarios en los que las opciones se deben volver a calcular en cada resolución de inserción, en [duraciones con ámbito o transitorias](dependency-injection.md#service-lifetimes).</span><span class="sxs-lookup"><span data-stu-id="9ceec-147">Is useful in scenarios where options should be recomputed on every injection resolution, in [scoped or transient lifetimes](dependency-injection.md#service-lifetimes).</span></span> <span data-ttu-id="9ceec-148">Para obtener más información, consulte el apartado [Uso de IOptionsSnapshot para leer datos actualizados](#use-ioptionssnapshot-to-read-updated-data).</span><span class="sxs-lookup"><span data-stu-id="9ceec-148">For more information, see [Use IOptionsSnapshot to read updated data](#use-ioptionssnapshot-to-read-updated-data).</span></span>
- <span data-ttu-id="9ceec-149">Se registra como [Con ámbito](dependency-injection.md#scoped) y, por tanto, no se puede insertar en un servicio Singleton.</span><span class="sxs-lookup"><span data-stu-id="9ceec-149">Is registered as [Scoped](dependency-injection.md#scoped) and therefore cannot be injected into a Singleton service.</span></span>
- <span data-ttu-id="9ceec-150">Admite [opciones con nombre](#named-options-support-using-iconfigurenamedoptions)</span><span class="sxs-lookup"><span data-stu-id="9ceec-150">Supports [named options](#named-options-support-using-iconfigurenamedoptions)</span></span>

<span data-ttu-id="9ceec-151"><xref:Microsoft.Extensions.Options.IOptionsMonitor%601>:</span><span class="sxs-lookup"><span data-stu-id="9ceec-151"><xref:Microsoft.Extensions.Options.IOptionsMonitor%601>:</span></span>

- <span data-ttu-id="9ceec-152">se usa para recuperar las opciones y administrar las notificaciones de las opciones para instancias de `TOptions`.</span><span class="sxs-lookup"><span data-stu-id="9ceec-152">Is used to retrieve options and manage options notifications for `TOptions` instances.</span></span>
- <span data-ttu-id="9ceec-153">Se registra como [Singleton](dependency-injection.md#singleton) y se puede insertar en cualquier [duración del servicio](dependency-injection.md#service-lifetimes).</span><span class="sxs-lookup"><span data-stu-id="9ceec-153">Is registered as a [Singleton](dependency-injection.md#singleton) and can be injected into any [service lifetime](dependency-injection.md#service-lifetimes).</span></span>
- <span data-ttu-id="9ceec-154">Es compatible con:</span><span class="sxs-lookup"><span data-stu-id="9ceec-154">Supports:</span></span>
  - <span data-ttu-id="9ceec-155">Notificaciones de cambios</span><span class="sxs-lookup"><span data-stu-id="9ceec-155">Change notifications</span></span>
  - [<span data-ttu-id="9ceec-156">Opciones con nombre</span><span class="sxs-lookup"><span data-stu-id="9ceec-156">Named options</span></span>](#named-options-support-using-iconfigurenamedoptions)
  - [<span data-ttu-id="9ceec-157">Configuración que se puede recargar</span><span class="sxs-lookup"><span data-stu-id="9ceec-157">Reloadable configuration</span></span>](#use-ioptionssnapshot-to-read-updated-data)
  - <span data-ttu-id="9ceec-158">Invalidación de opciones de selección (<xref:Microsoft.Extensions.Options.IOptionsMonitorCache%601>)</span><span class="sxs-lookup"><span data-stu-id="9ceec-158">Selective options invalidation (<xref:Microsoft.Extensions.Options.IOptionsMonitorCache%601>)</span></span>

<span data-ttu-id="9ceec-159"><xref:Microsoft.Extensions.Options.IOptionsFactory%601> es responsable de crear nuevas instancias de opciones.</span><span class="sxs-lookup"><span data-stu-id="9ceec-159"><xref:Microsoft.Extensions.Options.IOptionsFactory%601> is responsible for creating new options instances.</span></span> <span data-ttu-id="9ceec-160">Tiene un solo método <xref:Microsoft.Extensions.Options.IOptionsFactory%601.Create%2A>.</span><span class="sxs-lookup"><span data-stu-id="9ceec-160">It has a single <xref:Microsoft.Extensions.Options.IOptionsFactory%601.Create%2A> method.</span></span> <span data-ttu-id="9ceec-161">La implementación predeterminada toma todas las instancias registradas de <xref:Microsoft.Extensions.Options.IConfigureOptions%601> y <xref:Microsoft.Extensions.Options.IPostConfigureOptions%601>, y establece todas las configuraciones primero, seguidas de las configuraciones posteriores.</span><span class="sxs-lookup"><span data-stu-id="9ceec-161">The default implementation takes all registered <xref:Microsoft.Extensions.Options.IConfigureOptions%601> and <xref:Microsoft.Extensions.Options.IPostConfigureOptions%601> and runs all the configurations first, followed by the post-configuration.</span></span> <span data-ttu-id="9ceec-162">Distingue entre <xref:Microsoft.Extensions.Options.IConfigureNamedOptions%601> y <xref:Microsoft.Extensions.Options.IConfigureOptions%601>, y solo llama a la interfaz adecuada.</span><span class="sxs-lookup"><span data-stu-id="9ceec-162">It distinguishes between <xref:Microsoft.Extensions.Options.IConfigureNamedOptions%601> and <xref:Microsoft.Extensions.Options.IConfigureOptions%601> and only calls the appropriate interface.</span></span>

<span data-ttu-id="9ceec-163"><xref:Microsoft.Extensions.Options.IOptionsMonitorCache%601> se usa por <xref:Microsoft.Extensions.Options.IOptionsMonitor%601> para almacenar en caché las instancias de `TOptions`.</span><span class="sxs-lookup"><span data-stu-id="9ceec-163"><xref:Microsoft.Extensions.Options.IOptionsMonitorCache%601> is used by <xref:Microsoft.Extensions.Options.IOptionsMonitor%601> to cache `TOptions` instances.</span></span> <span data-ttu-id="9ceec-164"><xref:Microsoft.Extensions.Options.IOptionsMonitorCache%601> invalida instancias de opciones en la supervisión para que se pueda volver a calcular el valor (<xref:Microsoft.Extensions.Options.IOptionsMonitorCache%601.TryRemove%2A>).</span><span class="sxs-lookup"><span data-stu-id="9ceec-164">The <xref:Microsoft.Extensions.Options.IOptionsMonitorCache%601> invalidates options instances in the monitor so that the value is recomputed (<xref:Microsoft.Extensions.Options.IOptionsMonitorCache%601.TryRemove%2A>).</span></span> <span data-ttu-id="9ceec-165">Los valores se pueden introducir manualmente y mediante <xref:Microsoft.Extensions.Options.IOptionsMonitorCache%601.TryAdd%2A>.</span><span class="sxs-lookup"><span data-stu-id="9ceec-165">Values can be manually introduced with <xref:Microsoft.Extensions.Options.IOptionsMonitorCache%601.TryAdd%2A>.</span></span> <span data-ttu-id="9ceec-166">Se usa el método <xref:Microsoft.Extensions.Options.IOptionsMonitorCache%601.Clear%2A> cuando todas las instancias con nombre se deben volver a crear a petición.</span><span class="sxs-lookup"><span data-stu-id="9ceec-166">The <xref:Microsoft.Extensions.Options.IOptionsMonitorCache%601.Clear%2A> method is used when all named instances should be recreated on demand.</span></span>

### <a name="options-interfaces-benefits"></a><span data-ttu-id="9ceec-167">Ventajas de las interfaces de opciones</span><span class="sxs-lookup"><span data-stu-id="9ceec-167">Options interfaces benefits</span></span>

<span data-ttu-id="9ceec-168">El uso de un tipo de contenedor genérico proporciona la capacidad de desacoplar la duración de la opción del contenedor de DI.</span><span class="sxs-lookup"><span data-stu-id="9ceec-168">Using a generic wrapper type gives you the ability to decouple the lifetime of the option from the DI container.</span></span> <span data-ttu-id="9ceec-169">La interfaz <xref:Microsoft.Extensions.Options.IOptions%601.Value?displayProperty=nameWithType> proporciona una capa de abstracción, incluidas las restricciones genéricas, en el tipo de opciones.</span><span class="sxs-lookup"><span data-stu-id="9ceec-169">The <xref:Microsoft.Extensions.Options.IOptions%601.Value?displayProperty=nameWithType> interface provides a layer of abstraction, including generic constraints, on your options type.</span></span> <span data-ttu-id="9ceec-170">Esto proporciona las siguientes ventajas:</span><span class="sxs-lookup"><span data-stu-id="9ceec-170">This provides the following benefits:</span></span>

- <span data-ttu-id="9ceec-171">La evaluación de la `T` instancia de configuración se aplaza al acceso de <xref:Microsoft.Extensions.Options.IOptions%601.Value?displayProperty=nameWithType>, en lugar de cuando se inserta.</span><span class="sxs-lookup"><span data-stu-id="9ceec-171">The evaluation of the `T` configuration instance is deferred to the accessing of <xref:Microsoft.Extensions.Options.IOptions%601.Value?displayProperty=nameWithType>, rather than when it is injected.</span></span> <span data-ttu-id="9ceec-172">Esto es importante porque puede utilizar la opción `T` desde varios lugares y elegir la semántica de duración sin cambiar nada en `T`.</span><span class="sxs-lookup"><span data-stu-id="9ceec-172">This is important because you can consume the `T` option from various places and choose the lifetime semantics without changing anything about `T`.</span></span>
- <span data-ttu-id="9ceec-173">Al registrar opciones de tipo `T`, no es necesario registrar explícitamente el tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="9ceec-173">When registering options of type `T`, you do not need to explicitly register the `T` type.</span></span> <span data-ttu-id="9ceec-174">Esto se ofrece por comodidad cuando se [crea una biblioteca](options-library-authors.md) con valores predeterminados sencillos y no se desea obligar al autor de la llamada a registrar opciones en el contenedor de DI con una duración específica.</span><span class="sxs-lookup"><span data-stu-id="9ceec-174">This is a convenience when you're [authoring a library](options-library-authors.md) with simple defaults, and you don't want to force the caller to register options into the DI container with a specific lifetime.</span></span>
- <span data-ttu-id="9ceec-175">Desde la perspectiva de la API, permite restricciones en el tipo `T` (en este caso, `T` está restringido a un tipo de referencia).</span><span class="sxs-lookup"><span data-stu-id="9ceec-175">From the perspective of the API, it allows for constraints on the type `T` (in this case, `T` is constrained to a reference type).</span></span>

## <a name="use-ioptionssnapshot-to-read-updated-data"></a><span data-ttu-id="9ceec-176">Uso de IOptionsSnapshot para leer datos actualizados</span><span class="sxs-lookup"><span data-stu-id="9ceec-176">Use IOptionsSnapshot to read updated data</span></span>

<span data-ttu-id="9ceec-177">Al usar <xref:Microsoft.Extensions.Options.IOptionsSnapshot%601>, las opciones se calculan una vez por solicitud al acceder y se almacenan en caché durante la vigencia de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="9ceec-177">When you use <xref:Microsoft.Extensions.Options.IOptionsSnapshot%601>, options are computed once per request when accessed and are cached for the lifetime of the request.</span></span> <span data-ttu-id="9ceec-178">Los cambios en la configuración se leen tras iniciarse la aplicación al usar proveedores de configuración que admiten la lectura de valores de configuración actualizados.</span><span class="sxs-lookup"><span data-stu-id="9ceec-178">Changes to the configuration are read after the app starts when using configuration providers that support reading updated configuration values.</span></span>

<span data-ttu-id="9ceec-179">La diferencia entre `IOptionsMonitor` y `IOptionsSnapshot` es que:</span><span class="sxs-lookup"><span data-stu-id="9ceec-179">The difference between `IOptionsMonitor` and `IOptionsSnapshot` is that:</span></span>

- <span data-ttu-id="9ceec-180">`IOptionsMonitor` es un [servicio singleton](dependency-injection.md#singleton) que recupera los valores de las opciones actuales en cualquier momento, lo que resulta especialmente útil en las dependencias singleton.</span><span class="sxs-lookup"><span data-stu-id="9ceec-180">`IOptionsMonitor` is a [singleton service](dependency-injection.md#singleton) that retrieves current option values at any time, which is especially useful in singleton dependencies.</span></span>
- <span data-ttu-id="9ceec-181">`IOptionsSnapshot` es un [servicio con ámbito](dependency-injection.md#scoped) y proporciona una instantánea de las opciones en el momento en que se construye el objeto `IOptionsSnapshot<T>`.</span><span class="sxs-lookup"><span data-stu-id="9ceec-181">`IOptionsSnapshot` is a [scoped service](dependency-injection.md#scoped) and provides a snapshot of the options at the time the `IOptionsSnapshot<T>` object is constructed.</span></span> <span data-ttu-id="9ceec-182">Las instantáneas de opciones están diseñadas para usarlas con dependencias transitorias y con ámbito.</span><span class="sxs-lookup"><span data-stu-id="9ceec-182">Options snapshots are designed for use with transient and scoped dependencies.</span></span>

<span data-ttu-id="9ceec-183">El código siguiente usa <xref:Microsoft.Extensions.Options.IOptionsSnapshot%601>.</span><span class="sxs-lookup"><span data-stu-id="9ceec-183">The following code uses <xref:Microsoft.Extensions.Options.IOptionsSnapshot%601>.</span></span>

:::code language="csharp" source="snippets/configuration/console-json/ScopedService.cs":::

<span data-ttu-id="9ceec-184">El código siguiente registra una instancia de configuración en la que se enlaza `TransientFaultHandlingOptions`:</span><span class="sxs-lookup"><span data-stu-id="9ceec-184">The following code registers a configuration instance which `TransientFaultHandlingOptions` binds against:</span></span>

```csharp
services.Configure<TransientFaultHandlingOptions>(
    configurationRoot.GetSection(
        nameof(TransientFaultHandlingOptions)));
```

<span data-ttu-id="9ceec-185">En el código anterior, los cambios en el archivo de configuración de JSON producidos una vez iniciada la aplicación se leen.</span><span class="sxs-lookup"><span data-stu-id="9ceec-185">In the preceding code, changes to the JSON configuration file after the app has started are read.</span></span>

## <a name="ioptionsmonitor"></a><span data-ttu-id="9ceec-186">IOptionsMonitor</span><span class="sxs-lookup"><span data-stu-id="9ceec-186">IOptionsMonitor</span></span>

<span data-ttu-id="9ceec-187">El código siguiente registra una instancia de configuración en la que se enlaza `TransientFaultHandlingOptions`.</span><span class="sxs-lookup"><span data-stu-id="9ceec-187">The following code registers a configuration instance which `TransientFaultHandlingOptions` binds against.</span></span>

```csharp
services.Configure<TransientFaultHandlingOptions>(
    configurationRoot.GetSection(
        nameof(TransientFaultHandlingOptions)));
```

<span data-ttu-id="9ceec-188">En el ejemplo siguiente se usa <xref:Microsoft.Extensions.Options.IOptionsMonitor%601>:</span><span class="sxs-lookup"><span data-stu-id="9ceec-188">The following example uses <xref:Microsoft.Extensions.Options.IOptionsMonitor%601>:</span></span>

:::code language="csharp" source="snippets/configuration/console-json/MonitorService.cs":::

<span data-ttu-id="9ceec-189">En el código anterior, los cambios en el archivo de configuración de JSON producidos una vez iniciada la aplicación se leen.</span><span class="sxs-lookup"><span data-stu-id="9ceec-189">In the preceding code, changes to the JSON configuration file after the app has started are read.</span></span>

## <a name="named-options-support-using-iconfigurenamedoptions"></a><span data-ttu-id="9ceec-190">Compatibilidad de opciones con nombre con IConfigureNamedOptions</span><span class="sxs-lookup"><span data-stu-id="9ceec-190">Named options support using IConfigureNamedOptions</span></span>

<span data-ttu-id="9ceec-191">Opciones con nombre:</span><span class="sxs-lookup"><span data-stu-id="9ceec-191">Named options:</span></span>

- <span data-ttu-id="9ceec-192">son útiles cuando varias secciones de configuración se enlazan a las mismas propiedades.</span><span class="sxs-lookup"><span data-stu-id="9ceec-192">Are useful when multiple configuration sections bind to the same properties.</span></span>
- <span data-ttu-id="9ceec-193">Distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="9ceec-193">Are case-sensitive.</span></span>

<span data-ttu-id="9ceec-194">Fíjese en el siguiente archivo *appsettings.json*:</span><span class="sxs-lookup"><span data-stu-id="9ceec-194">Consider the following *appsettings.json* file:</span></span>

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

<span data-ttu-id="9ceec-195">En lugar de crear dos clases para enlazar `Features:Personalize` y `Features:WeatherStation`, se usará la clase siguiente para cada sección:</span><span class="sxs-lookup"><span data-stu-id="9ceec-195">Rather than creating two classes to bind `Features:Personalize` and `Features:WeatherStation`, the following class is used for each section:</span></span>

```csharp
public class Features
{
    public const string Personalize = nameof(Personalize);
    public const string WeatherStation = nameof(WeatherStation);

    public bool Enabled { get; set; }
    public string ApiKey { get; set; }
}
```

<span data-ttu-id="9ceec-196">El siguiente código configura las opciones con nombre:</span><span class="sxs-lookup"><span data-stu-id="9ceec-196">The following code configures the named options:</span></span>

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

<span data-ttu-id="9ceec-197">En el código siguiente se muestran las opciones con nombre:</span><span class="sxs-lookup"><span data-stu-id="9ceec-197">The following code displays the named options:</span></span>

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

<span data-ttu-id="9ceec-198">Todas las opciones son instancias con nombre.</span><span class="sxs-lookup"><span data-stu-id="9ceec-198">All options are named instances.</span></span> <span data-ttu-id="9ceec-199">Las instancias de <xref:Microsoft.Extensions.Options.IConfigureOptions%601> se usan para seleccionar como destino la instancia de `Options.DefaultName`, que es `string.Empty`.</span><span class="sxs-lookup"><span data-stu-id="9ceec-199"><xref:Microsoft.Extensions.Options.IConfigureOptions%601> instances are treated as targeting the `Options.DefaultName` instance, which is `string.Empty`.</span></span> <span data-ttu-id="9ceec-200"><xref:Microsoft.Extensions.Options.IConfigureNamedOptions%601> también implementa <xref:Microsoft.Extensions.Options.IConfigureOptions%601>.</span><span class="sxs-lookup"><span data-stu-id="9ceec-200"><xref:Microsoft.Extensions.Options.IConfigureNamedOptions%601> also implements <xref:Microsoft.Extensions.Options.IConfigureOptions%601>.</span></span> <span data-ttu-id="9ceec-201">La implementación predeterminada de <xref:Microsoft.Extensions.Options.IOptionsFactory%601> tiene lógica para usar cada una de forma adecuada.</span><span class="sxs-lookup"><span data-stu-id="9ceec-201">The default implementation of the <xref:Microsoft.Extensions.Options.IOptionsFactory%601> has logic to use each appropriately.</span></span> <span data-ttu-id="9ceec-202">La opción con nombre `null` se usa para seleccionar como destino todas las instancias con nombre, en lugar de una instancia con nombre determinada.</span><span class="sxs-lookup"><span data-stu-id="9ceec-202">The `null` named option is used to target all of the named instances instead of a specific named instance.</span></span> <span data-ttu-id="9ceec-203"><xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.ConfigureAll%2A> y <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.PostConfigureAll%2A> usan esta convención.</span><span class="sxs-lookup"><span data-stu-id="9ceec-203"><xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.ConfigureAll%2A> and <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.PostConfigureAll%2A> use this convention.</span></span>

## <a name="optionsbuilder-api"></a><span data-ttu-id="9ceec-204">API OptionsBuilder</span><span class="sxs-lookup"><span data-stu-id="9ceec-204">OptionsBuilder API</span></span>

<span data-ttu-id="9ceec-205"><xref:Microsoft.Extensions.Options.OptionsBuilder%601> se usa para configurar instancias `TOptions`.</span><span class="sxs-lookup"><span data-stu-id="9ceec-205"><xref:Microsoft.Extensions.Options.OptionsBuilder%601> is used to configure `TOptions` instances.</span></span> <span data-ttu-id="9ceec-206">`OptionsBuilder` simplifica la creación de opciones con nombre, ya que es un único parámetro para la llamada `AddOptions<TOptions>(string optionsName)` inicial en lugar de aparecer en todas las llamadas posteriores.</span><span class="sxs-lookup"><span data-stu-id="9ceec-206">`OptionsBuilder` streamlines creating named options as it's only a single parameter to the initial `AddOptions<TOptions>(string optionsName)` call instead of appearing in all of the subsequent calls.</span></span> <span data-ttu-id="9ceec-207">La validación de opciones y las sobrecargas `ConfigureOptions` que aceptan las dependencias de servicio solo están disponibles mediante `OptionsBuilder`.</span><span class="sxs-lookup"><span data-stu-id="9ceec-207">Options validation and the `ConfigureOptions` overloads that accept service dependencies are only available via `OptionsBuilder`.</span></span>

<span data-ttu-id="9ceec-208">`OptionsBuilder` se usa en la sección [Opciones de validación](#options-validation).</span><span class="sxs-lookup"><span data-stu-id="9ceec-208">`OptionsBuilder` is used in the [Options validation](#options-validation) section.</span></span>

## <a name="use-di-services-to-configure-options"></a><span data-ttu-id="9ceec-209">Uso de servicios de DI para configurar opciones</span><span class="sxs-lookup"><span data-stu-id="9ceec-209">Use DI services to configure options</span></span>

<span data-ttu-id="9ceec-210">Hay dos formas de acceder a los servicios desde la inserción de dependencias durante la configuración de opciones:</span><span class="sxs-lookup"><span data-stu-id="9ceec-210">Services can be accessed from dependency injection while configuring options in two ways:</span></span>

- <span data-ttu-id="9ceec-211">Si se pasa un delegado de configuración a [Configure](xref:Microsoft.Extensions.Options.OptionsBuilder%601.Configure%2A) en [OptionsBuilder\<TOptions>](xref:Microsoft.Extensions.Options.OptionsBuilder%601).</span><span class="sxs-lookup"><span data-stu-id="9ceec-211">Pass a configuration delegate to [Configure](xref:Microsoft.Extensions.Options.OptionsBuilder%601.Configure%2A) on [OptionsBuilder\<TOptions>](xref:Microsoft.Extensions.Options.OptionsBuilder%601).</span></span> <span data-ttu-id="9ceec-212">`OptionsBuilder<TOptions>` proporciona sobrecargas de [Configure](xref:Microsoft.Extensions.Options.OptionsBuilder%601.Configure%2A) que permiten usar hasta cinco servicios para configurar las opciones:</span><span class="sxs-lookup"><span data-stu-id="9ceec-212">`OptionsBuilder<TOptions>` provides overloads of [Configure](xref:Microsoft.Extensions.Options.OptionsBuilder%601.Configure%2A) that allow use of up to five services to configure options:</span></span>

  ```csharp
  services.AddOptions<MyOptions>("optionalName")
      .Configure<ExampleService, ScopedService, MonitorService>(
          (options, es, ss, ms) =>
              options.Property = DoSomethingWith(es, ss, ms));
  ```

- <span data-ttu-id="9ceec-213">Si se crea un tipo que implementa <xref:Microsoft.Extensions.Options.IConfigureOptions%601> o <xref:Microsoft.Extensions.Options.IConfigureNamedOptions%601>, y se registra como un servicio.</span><span class="sxs-lookup"><span data-stu-id="9ceec-213">Create a type that implements <xref:Microsoft.Extensions.Options.IConfigureOptions%601> or <xref:Microsoft.Extensions.Options.IConfigureNamedOptions%601> and register the type as a service.</span></span>

<span data-ttu-id="9ceec-214">Se recomienda pasar un delegado de configuración a [Configure](xref:Microsoft.Extensions.Options.OptionsBuilder%601.Configure%2A), ya que la creación de un servicio es más complicada.</span><span class="sxs-lookup"><span data-stu-id="9ceec-214">We recommend passing a configuration delegate to [Configure](xref:Microsoft.Extensions.Options.OptionsBuilder%601.Configure%2A), since creating a service is more complex.</span></span> <span data-ttu-id="9ceec-215">La creación de un tipo es equivalente a lo que el marco hace cuando se llama a [Configure](xref:Microsoft.Extensions.Options.OptionsBuilder%601.Configure%2A).</span><span class="sxs-lookup"><span data-stu-id="9ceec-215">Creating a type is equivalent to what the framework does when calling [Configure](xref:Microsoft.Extensions.Options.OptionsBuilder%601.Configure%2A).</span></span> <span data-ttu-id="9ceec-216">La llamada a [Configure](xref:Microsoft.Extensions.Options.OptionsBuilder%601.Configure%2A) registra una interfaz <xref:Microsoft.Extensions.Options.IConfigureNamedOptions%601> genérica y transitoria, con un constructor que acepta los tipos de servicio genéricos especificados.</span><span class="sxs-lookup"><span data-stu-id="9ceec-216">Calling [Configure](xref:Microsoft.Extensions.Options.OptionsBuilder%601.Configure%2A) registers a transient generic <xref:Microsoft.Extensions.Options.IConfigureNamedOptions%601>, which has a constructor that accepts the generic service types specified.</span></span>

## <a name="options-validation"></a><span data-ttu-id="9ceec-217">Opciones de validación</span><span class="sxs-lookup"><span data-stu-id="9ceec-217">Options validation</span></span>

<span data-ttu-id="9ceec-218">Opciones de validación permite que se validen los valores de opción.</span><span class="sxs-lookup"><span data-stu-id="9ceec-218">Options validation enables option values to be validated.</span></span>

<span data-ttu-id="9ceec-219">Fíjese en el siguiente archivo *appsettings.json*:</span><span class="sxs-lookup"><span data-stu-id="9ceec-219">Consider the following *appsettings.json* file:</span></span>

```json
{
  "Settings": {
    "SiteTitle": "Amazing docs from Awesome people!",
    "Scale": 10,
    "VerbosityLevel": 32
  }
}
```

<span data-ttu-id="9ceec-220">La siguiente clase se enlaza a la sección de configuración `"Settings"` y aplica un par de reglas `DataAnnotations`:</span><span class="sxs-lookup"><span data-stu-id="9ceec-220">The following class binds to the `"Settings"` configuration section and applies a couple of `DataAnnotations` rules:</span></span>

:::code language="csharp" source="snippets/configuration/console-json/SettingsOptions.cs":::

<span data-ttu-id="9ceec-221">El código siguiente:</span><span class="sxs-lookup"><span data-stu-id="9ceec-221">The following code:</span></span>

- <span data-ttu-id="9ceec-222">Llama a <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.AddOptions%2A> para obtener un elemento [OptionsBuilder\<TOptions>](xref:Microsoft.Extensions.Options.OptionsBuilder%601) que enlaza a la clase `SettingsOptions`.</span><span class="sxs-lookup"><span data-stu-id="9ceec-222">Calls <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.AddOptions%2A> to get an [OptionsBuilder\<TOptions>](xref:Microsoft.Extensions.Options.OptionsBuilder%601) that binds to the `SettingsOptions` class.</span></span>
- <span data-ttu-id="9ceec-223">Llama a <xref:Microsoft.Extensions.DependencyInjection.OptionsBuilderDataAnnotationsExtensions.ValidateDataAnnotations%2A> para habilitar la validación con `DataAnnotations`.</span><span class="sxs-lookup"><span data-stu-id="9ceec-223">Calls <xref:Microsoft.Extensions.DependencyInjection.OptionsBuilderDataAnnotationsExtensions.ValidateDataAnnotations%2A> to enable validation using `DataAnnotations`.</span></span>

```csharp
services.AddOptions<SettingsOptions>()
    .Bind(Configuration.GetSection(SettingsOptions.Settings))
    .ValidateDataAnnotations();
```

<span data-ttu-id="9ceec-224">El método de extensión `ValidateDataAnnotations` se define en el paquete NuGet [Microsoft.Extensions.Options.DataAnnotations](https://www.nuget.org/packages/Microsoft.Extensions.Options.DataAnnotations).</span><span class="sxs-lookup"><span data-stu-id="9ceec-224">The `ValidateDataAnnotations` extension method is defined in the [Microsoft.Extensions.Options.DataAnnotations](https://www.nuget.org/packages/Microsoft.Extensions.Options.DataAnnotations) NuGet package.</span></span>

<span data-ttu-id="9ceec-225">En el código siguiente se muestran los valores de configuración o los errores de validación:</span><span class="sxs-lookup"><span data-stu-id="9ceec-225">The following code displays the configuration values or the validation errors:</span></span>

:::code language="csharp" source="snippets/configuration/console-json/ValidationService.cs":::

<span data-ttu-id="9ceec-226">El código siguiente aplica una regla de validación más compleja mediante un delegado:</span><span class="sxs-lookup"><span data-stu-id="9ceec-226">The following code applies a more complex validation rule using a delegate:</span></span>

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

### <a name="ivalidateoptions-for-complex-validation"></a><span data-ttu-id="9ceec-227">IValidateOptions para la validación compleja</span><span class="sxs-lookup"><span data-stu-id="9ceec-227">IValidateOptions for complex validation</span></span>

<span data-ttu-id="9ceec-228">La siguiente clase implementa <xref:Microsoft.Extensions.Options.IValidateOptions%601>:</span><span class="sxs-lookup"><span data-stu-id="9ceec-228">The following class implements <xref:Microsoft.Extensions.Options.IValidateOptions%601>:</span></span>

:::code language="csharp" source="snippets/configuration/console-json/ValidateSettingsOptions.cs":::

<span data-ttu-id="9ceec-229">`IValidateOptions` permite mover el código de validación dentro de una clase.</span><span class="sxs-lookup"><span data-stu-id="9ceec-229">`IValidateOptions` enables moving the validation code into a class.</span></span>

<span data-ttu-id="9ceec-230">Con el código anterior, la validación se habilita en `ConfigureServices` con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="9ceec-230">Using the preceding code, validation is enabled in `ConfigureServices` with the following code:</span></span>

```csharp
services.Configure<SettingsOptions>(
    Configuration.GetSection(
        SettingsOptions.Settings));
services.TryAddEnumerable(
    ServiceDescriptor.Singleton
        <IValidateOptions<SettingsOptions>, ValidateSettingsOptions>());
```

## <a name="options-post-configuration"></a><span data-ttu-id="9ceec-231">Configuración posterior de las opciones</span><span class="sxs-lookup"><span data-stu-id="9ceec-231">Options post-configuration</span></span>

<span data-ttu-id="9ceec-232">Establezca la configuración posterior con <xref:Microsoft.Extensions.Options.IPostConfigureOptions%601>.</span><span class="sxs-lookup"><span data-stu-id="9ceec-232">Set post-configuration with <xref:Microsoft.Extensions.Options.IPostConfigureOptions%601>.</span></span> <span data-ttu-id="9ceec-233">Las tareas posteriores a la configuración se ejecutan una vez realizada toda la configuración de <xref:Microsoft.Extensions.Options.IConfigureOptions%601>, y pueden resultar útiles en los escenarios en los que es necesario invalidar la configuración:</span><span class="sxs-lookup"><span data-stu-id="9ceec-233">Post-configuration runs after all <xref:Microsoft.Extensions.Options.IConfigureOptions%601> configuration occurs, and can be useful in scenarios when you need to override configuration:</span></span>

```csharp
services.PostConfigure<CustomOptions>(customOptions =>
{
    customOptions.Option1 = "post_configured_option1_value";
});
```

<span data-ttu-id="9ceec-234"><xref:Microsoft.Extensions.Options.IPostConfigureOptions%601.PostConfigure%2A> está disponible para configurar posteriormente las opciones con nombre:</span><span class="sxs-lookup"><span data-stu-id="9ceec-234"><xref:Microsoft.Extensions.Options.IPostConfigureOptions%601.PostConfigure%2A> is available to post-configure named options:</span></span>

```csharp
services.PostConfigure<CustomOptions>("named_options_1", customOptions =>
{
    customOptions.Option1 = "post_configured_option1_value";
});
```

<span data-ttu-id="9ceec-235">Use <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.PostConfigureAll%2A> para configurar posteriormente todas las instancias de configuración:</span><span class="sxs-lookup"><span data-stu-id="9ceec-235">Use <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.PostConfigureAll%2A> to post-configure all configuration instances:</span></span>

```csharp
services.PostConfigureAll<CustomOptions>(customOptions =>
{
    customOptions.Option1 = "post_configured_option1_value";
});
```

## <a name="see-also"></a><span data-ttu-id="9ceec-236">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ceec-236">See also</span></span>

- [<span data-ttu-id="9ceec-237">Configuración en .NET</span><span class="sxs-lookup"><span data-stu-id="9ceec-237">Configuration in .NET</span></span>](configuration.md)
- [<span data-ttu-id="9ceec-238">Guía sobre los patrones de opciones para creadores de bibliotecas de .NET</span><span class="sxs-lookup"><span data-stu-id="9ceec-238">Options pattern guidance for .NET library authors</span></span>](options-library-authors.md)
