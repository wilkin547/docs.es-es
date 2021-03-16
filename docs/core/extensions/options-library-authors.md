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
# <a name="options-pattern-guidance-for-net-library-authors"></a><span data-ttu-id="314f1-103">Guía sobre los patrones de opciones para creadores de bibliotecas de .NET</span><span class="sxs-lookup"><span data-stu-id="314f1-103">Options pattern guidance for .NET library authors</span></span>

<span data-ttu-id="314f1-104">Con la ayuda de la inserción de dependencias, el registro de los servicios y sus configuraciones correspondientes pueden utilizar el *patrón de opciones*.</span><span class="sxs-lookup"><span data-stu-id="314f1-104">With the help of dependency injection, registering your services and their corresponding configurations can make use of the *options pattern*.</span></span> <span data-ttu-id="314f1-105">El patrón de opciones permite a los consumidores de su biblioteca y a sus servicios requerir instancias de [interfaces de opciones](options.md#options-interfaces), donde `TOptions` es la clase de opciones.</span><span class="sxs-lookup"><span data-stu-id="314f1-105">The options pattern enables consumers of your library (and your services) to require instances of [options interfaces](options.md#options-interfaces) where `TOptions` is your options class.</span></span> <span data-ttu-id="314f1-106">El consumo de opciones de configuración mediante objetos fuertemente tipados ayuda a garantizar una representación de valores coherente y elimina la carga de analizar manualmente los valores de cadena.</span><span class="sxs-lookup"><span data-stu-id="314f1-106">Consuming configuration options through strongly-typed objects helps to ensure consistent value representation, and removes the burden of manually parsing string values.</span></span> <span data-ttu-id="314f1-107">Hay muchos [proveedores de configuración](configuration-providers.md) a los que los consumidores pueden recurrir.</span><span class="sxs-lookup"><span data-stu-id="314f1-107">There are many [configuration providers](configuration-providers.md) for consumers of your library to use.</span></span> <span data-ttu-id="314f1-108">Con estos proveedores, los consumidores pueden configurar su biblioteca de muchas maneras.</span><span class="sxs-lookup"><span data-stu-id="314f1-108">With these providers, consumers can configure your library in many ways.</span></span>

<span data-ttu-id="314f1-109">Como autor de bibliotecas de .NET, conocerá instrucciones generales sobre cómo exponer correctamente el patrón de opciones a los consumidores de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="314f1-109">As a .NET library author, you'll learn general guidance on how to correctly expose the options pattern to consumers of your library.</span></span> <span data-ttu-id="314f1-110">Hay varias maneras de lograr lo mismo, y varias consideraciones que se deben contemplar.</span><span class="sxs-lookup"><span data-stu-id="314f1-110">There are various ways to achieve the same thing, and several considerations to make.</span></span>

## <a name="naming-conventions"></a><span data-ttu-id="314f1-111">Convenciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="314f1-111">Naming conventions</span></span>

<span data-ttu-id="314f1-112">Por convención, los métodos de extensión responsables del registro de servicios se denominan `Add{Service}`, donde `{Service}` es un nombre descriptivo y significativo.</span><span class="sxs-lookup"><span data-stu-id="314f1-112">By convention, extension methods responsible for registering services are named `Add{Service}`, where `{Service}` is a meaningful and descriptive name.</span></span> <span data-ttu-id="314f1-113">Dependiendo del paquete, el registro de servicios puede ir acompañado de los métodos de extensión `Use{Service}`.</span><span class="sxs-lookup"><span data-stu-id="314f1-113">Depending on the package, the registration of services may be accompanied by `Use{Service}` extension methods.</span></span> <span data-ttu-id="314f1-114">Los métodos de extensión `Use{Service}` son habituales en [ASP.NET Core](/aspnet).</span><span class="sxs-lookup"><span data-stu-id="314f1-114">The `Use{Service}` extension methods are commonplace in [ASP.NET Core](/aspnet).</span></span>

<span data-ttu-id="314f1-115">✔️ CONSIDERE nombres que eliminan la ambigüedad de los servicios respecto a otras ofertas.</span><span class="sxs-lookup"><span data-stu-id="314f1-115">✔️ CONSIDER names that disambiguate your service from other offerings.</span></span>

<span data-ttu-id="314f1-116">❌ NO utilice nombres que ya formen parte del ecosistema de .NET de los paquetes oficiales de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="314f1-116">❌ DO NOT use names that are already part of the .NET ecosystem from official Microsoft packages.</span></span>

<span data-ttu-id="314f1-117">✔️ CONSIDERE la posibilidad de asignar nombres a clases estáticas que expongan métodos de extensión como `{Type}Extensions`, donde `{Type}` es el tipo que se va a extender.</span><span class="sxs-lookup"><span data-stu-id="314f1-117">✔️ CONSIDER naming static classes that expose extension methods as `{Type}Extensions`, where `{Type}` is the type that you're extending.</span></span>

### <a name="namespace-guidance"></a><span data-ttu-id="314f1-118">Guía sobre los espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="314f1-118">Namespace guidance</span></span>

<span data-ttu-id="314f1-119">Los paquetes de Microsoft utilizan el espacio de nombres `Microsoft.Extensions.DependencyInjection` para unificar el registro de varias ofertas de servicio.</span><span class="sxs-lookup"><span data-stu-id="314f1-119">Microsoft packages make use of the `Microsoft.Extensions.DependencyInjection` namespace to unify the registration of various service offerings.</span></span>

<span data-ttu-id="314f1-120">✔️ CONSIDERE un espacio de nombres que identifique claramente la oferta del paquete.</span><span class="sxs-lookup"><span data-stu-id="314f1-120">✔️ CONSIDER a namespace that clearly identifies your package offering.</span></span>

<span data-ttu-id="314f1-121">❌ NO use el espacio de nombres `Microsoft.Extensions.DependencyInjection` para los paquetes no oficiales de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="314f1-121">❌ DO NOT use the `Microsoft.Extensions.DependencyInjection` namespace for non-official Microsoft packages.</span></span>

## <a name="parameterless"></a><span data-ttu-id="314f1-122">Sin parámetros</span><span class="sxs-lookup"><span data-stu-id="314f1-122">Parameterless</span></span>

<span data-ttu-id="314f1-123">Si el servicio puede funcionar con una configuración mínima o no explícita, considere la posibilidad de usar un método de extensión sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="314f1-123">If your service can work with minimal or no explicit configuration, consider a parameterless extension method.</span></span>

:::code language="csharp" source="snippets/configuration/options-noparams/ServiceCollectionExtensions.cs" highlight="10-14":::

<span data-ttu-id="314f1-124">En el código anterior, `AddMyLibraryService`:</span><span class="sxs-lookup"><span data-stu-id="314f1-124">In the preceding code, the `AddMyLibraryService`:</span></span>

- <span data-ttu-id="314f1-125">extiende una instancia de <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>,</span><span class="sxs-lookup"><span data-stu-id="314f1-125">Extends an instance of <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection></span></span>
- <span data-ttu-id="314f1-126">llama a <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.AddOptions%60%601(Microsoft.Extensions.DependencyInjection.IServiceCollection)?displayProperty=nameWithType> con el parámetro de tipo de `LibraryOptions` y</span><span class="sxs-lookup"><span data-stu-id="314f1-126">Calls <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.AddOptions%60%601(Microsoft.Extensions.DependencyInjection.IServiceCollection)?displayProperty=nameWithType> with the type parameter of `LibraryOptions`</span></span>
- <span data-ttu-id="314f1-127">encadena una llamada a <xref:Microsoft.Extensions.Options.OptionsBuilder%601.Configure%2A>, que especifica los valores de opción predeterminados</span><span class="sxs-lookup"><span data-stu-id="314f1-127">Chains a call to <xref:Microsoft.Extensions.Options.OptionsBuilder%601.Configure%2A>, which specifies the default option values</span></span>

## <a name="iconfiguration-parameter"></a><span data-ttu-id="314f1-128">Parámetro `IConfiguration`</span><span class="sxs-lookup"><span data-stu-id="314f1-128">`IConfiguration` parameter</span></span>

<span data-ttu-id="314f1-129">Cuando crea una biblioteca que expone muchas opciones a los consumidores, puede que desee considerar la posibilidad de requerir un método de extensión de parámetros `IConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="314f1-129">When you author a library that exposes many options to consumers, you may want to consider requiring an `IConfiguration` parameter extension method.</span></span> <span data-ttu-id="314f1-130">La instancia esperada `IConfiguration` debe tener como ámbito una sección con nombre de la configuración mediante la función <xref:Microsoft.Extensions.Configuration.IConfiguration.GetSection%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="314f1-130">The expected `IConfiguration` instance should be scoped to a named section of the configuration by using the <xref:Microsoft.Extensions.Configuration.IConfiguration.GetSection%2A?displayProperty=nameWithType> function.</span></span>

:::code language="csharp" source="snippets/configuration/options-configparam/ServiceCollectionExtensions.cs" highlight="10,12-16":::

<span data-ttu-id="314f1-131">En el código anterior, `AddMyLibraryService`:</span><span class="sxs-lookup"><span data-stu-id="314f1-131">In the preceding code, the `AddMyLibraryService`:</span></span>

- <span data-ttu-id="314f1-132">extiende una instancia de <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>,</span><span class="sxs-lookup"><span data-stu-id="314f1-132">Extends an instance of <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection></span></span>
- <span data-ttu-id="314f1-133">define un parámetro `namedConfigurationSection` de la interfaz <xref:Microsoft.Extensions.Configuration.IConfiguration> y</span><span class="sxs-lookup"><span data-stu-id="314f1-133">Defines an <xref:Microsoft.Extensions.Configuration.IConfiguration> parameter `namedConfigurationSection`</span></span>
- <span data-ttu-id="314f1-134">llama a <xref:Microsoft.Extensions.Configuration.ConfigurationBinder.Bind(Microsoft.Extensions.Configuration.IConfiguration,System.Object)> para pasar una instancia de opciones a la que se enlaza la configuración.</span><span class="sxs-lookup"><span data-stu-id="314f1-134">Calls <xref:Microsoft.Extensions.Configuration.ConfigurationBinder.Bind(Microsoft.Extensions.Configuration.IConfiguration,System.Object)> passing an options instance that the configuration binds to</span></span>

<span data-ttu-id="314f1-135">Los consumidores de este patrón proporcionan la instancia con ámbito `IConfiguration` de la sección titulada:</span><span class="sxs-lookup"><span data-stu-id="314f1-135">Consumers in this pattern provide the scoped `IConfiguration` instance of the named section:</span></span>

:::code language="csharp" source="snippets/configuration/options-configparam/Program.cs" highlight="22-23":::

<span data-ttu-id="314f1-136">La llamada a `.AddMyLibraryService` se realiza en el método <xref:Microsoft.Extensions.Hosting.IHostBuilder.ConfigureServices%2A>.</span><span class="sxs-lookup"><span data-stu-id="314f1-136">The call to `.AddMyLibraryService` is made in the <xref:Microsoft.Extensions.Hosting.IHostBuilder.ConfigureServices%2A> method.</span></span> <span data-ttu-id="314f1-137">Lo mismo ocurre cuando se usa una clase `Startup`, y la adición de los servicios que se están registrando se produce en `ConfigureServices`.</span><span class="sxs-lookup"><span data-stu-id="314f1-137">The same is true when using a `Startup` class, the addition of services being registered occurs in `ConfigureServices`.</span></span>

<span data-ttu-id="314f1-138">Como autor de la biblioteca, la especificación de valores predeterminados depende de usted.</span><span class="sxs-lookup"><span data-stu-id="314f1-138">As the library author, specifying default values is up to you.</span></span>

> [!NOTE]
> <span data-ttu-id="314f1-139">Es posible enlazar la configuración a una instancia de opciones.</span><span class="sxs-lookup"><span data-stu-id="314f1-139">It is possible to bind configuration to an options instance.</span></span> <span data-ttu-id="314f1-140">Sin embargo, existe el riesgo de que se produzcan conflictos de nombres, lo que provocará errores.</span><span class="sxs-lookup"><span data-stu-id="314f1-140">However, there is a risk of name collisions - which will cause errors.</span></span> <span data-ttu-id="314f1-141">Además, cuando se realiza un enlace manual de esta forma, se limita el consumo del patrón de opciones a una sola lectura.</span><span class="sxs-lookup"><span data-stu-id="314f1-141">Additionally, when manually binding in this way, you limit the consumption of your options pattern to read-once.</span></span> <span data-ttu-id="314f1-142">Los cambios en la configuración no se volverán a enlazar, ya que estos consumidores no podrán usar la interfaz [IOptionsMonitor](options.md#ioptionsmonitor).</span><span class="sxs-lookup"><span data-stu-id="314f1-142">Changes to settings will not be re-bound, as such consumers will not be able to use the [IOptionsMonitor](options.md#ioptionsmonitor) interface.</span></span>
>
> ```csharp
> services.AddOptions<LibraryOptions>()
>     .Configure<IConfiguration>(
>         (options, configuration) =>
>             configuration.GetSection("LibraryOptions").Bind(options));
> ```

## <a name="actiontoptions-parameter"></a><span data-ttu-id="314f1-143">Parámetro `Action<TOptions>`</span><span class="sxs-lookup"><span data-stu-id="314f1-143">`Action<TOptions>` parameter</span></span>

<span data-ttu-id="314f1-144">A los consumidores de la biblioteca les puede interesar proporcionar una expresión lambda que genere una instancia de la clase de opciones.</span><span class="sxs-lookup"><span data-stu-id="314f1-144">Consumers of your library may be interested in providing a lambda expression that yields an instance of your options class.</span></span> <span data-ttu-id="314f1-145">En este escenario, se define un parámetro `Action<LibraryOptions>` en el método de extensión.</span><span class="sxs-lookup"><span data-stu-id="314f1-145">In this scenario, you define an `Action<LibraryOptions>` parameter in your extension method.</span></span>

:::code language="csharp" source="snippets/configuration/options-action/ServiceCollectionExtensions.cs" highlight="10,12":::

<span data-ttu-id="314f1-146">En el código anterior, `AddMyLibraryService`:</span><span class="sxs-lookup"><span data-stu-id="314f1-146">In the preceding code, the `AddMyLibraryService`:</span></span>

- <span data-ttu-id="314f1-147">extiende una instancia de <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>,</span><span class="sxs-lookup"><span data-stu-id="314f1-147">Extends an instance of <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection></span></span>
- <span data-ttu-id="314f1-148">define <xref:System.Action%601>, donde `T` es el parámetro `configureOptions` de `LibraryOptions` y</span><span class="sxs-lookup"><span data-stu-id="314f1-148">Defines an <xref:System.Action%601> where `T` is `LibraryOptions` parameter `configureOptions`</span></span>
- <span data-ttu-id="314f1-149">llama a <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.Configure%2A>, dada la acción `configureOptions`.</span><span class="sxs-lookup"><span data-stu-id="314f1-149">Calls <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.Configure%2A> given the `configureOptions` action</span></span>

<span data-ttu-id="314f1-150">Los consumidores de este patrón proporcionan una expresión lambda, o bien un delegado que cumple el parámetro `Action<LibraryOptions>`:</span><span class="sxs-lookup"><span data-stu-id="314f1-150">Consumers in this pattern provide a lambda expression (or a delegate that satisfies the `Action<LibraryOptions>` parameter):</span></span>

:::code language="csharp" source="snippets/configuration/options-action/Program.cs" highlight="22-26":::

## <a name="options-instance-parameter"></a><span data-ttu-id="314f1-151">Parámetro de la instancia de opciones</span><span class="sxs-lookup"><span data-stu-id="314f1-151">Options instance parameter</span></span>

<span data-ttu-id="314f1-152">Es posible que los consumidores de la biblioteca prefieran proporcionar una instancia de opciones insertadas.</span><span class="sxs-lookup"><span data-stu-id="314f1-152">Consumers of your library might prefer to provide an inlined options instance.</span></span> <span data-ttu-id="314f1-153">En este escenario, se expone un método de extensión que adopta una instancia del objeto de opciones, `LibraryOptions`.</span><span class="sxs-lookup"><span data-stu-id="314f1-153">In this scenario, you expose an extension method that takes an instance of your options object, `LibraryOptions`.</span></span>

:::code language="csharp" source="snippets/configuration/options-object/ServiceCollectionExtensions.cs" highlight="9,11-17":::

<span data-ttu-id="314f1-154">En el código anterior, `AddMyLibraryService`:</span><span class="sxs-lookup"><span data-stu-id="314f1-154">In the preceding code, the `AddMyLibraryService`:</span></span>

- <span data-ttu-id="314f1-155">extiende una instancia de <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>,</span><span class="sxs-lookup"><span data-stu-id="314f1-155">Extends an instance of <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection></span></span>
- <span data-ttu-id="314f1-156">llama a <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.AddOptions%60%601(Microsoft.Extensions.DependencyInjection.IServiceCollection)?displayProperty=nameWithType> con el parámetro de tipo de `LibraryOptions` y</span><span class="sxs-lookup"><span data-stu-id="314f1-156">Calls <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.AddOptions%60%601(Microsoft.Extensions.DependencyInjection.IServiceCollection)?displayProperty=nameWithType> with the type parameter of `LibraryOptions`</span></span>
- <span data-ttu-id="314f1-157">encadena una llamada a <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.Configure%2A>, que especifica los valores de opción predeterminados que se pueden invalidar de la instancia `userOptions` especificada.</span><span class="sxs-lookup"><span data-stu-id="314f1-157">Chains a call to <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.Configure%2A>, which specifies default option values that can be overridden from the given `userOptions` instance</span></span>

<span data-ttu-id="314f1-158">Los consumidores de este patrón proporcionan una instancia de la clase `LibraryOptions`, que define los valores de propiedad deseados insertados:</span><span class="sxs-lookup"><span data-stu-id="314f1-158">Consumers in this pattern provide an instance of the `LibraryOptions` class, defining desired property values inline:</span></span>

:::code language="csharp" source="snippets/configuration/options-object/Program.cs" highlight="22-26":::

## <a name="post-configuration"></a><span data-ttu-id="314f1-159">Después de la configuración</span><span class="sxs-lookup"><span data-stu-id="314f1-159">Post configuration</span></span>

<span data-ttu-id="314f1-160">Una vez que se han enlazado o especificado todos los valores de las opciones de configuración, está disponible la funcionalidad posterior a la configuración.</span><span class="sxs-lookup"><span data-stu-id="314f1-160">After all configuration option values are bound or specified, post configuration functionality is available.</span></span> <span data-ttu-id="314f1-161">Al exponer el mismo [parámetro `Action<TOptions>`](#actiontoptions-parameter) detallado anteriormente, podría optar por llamar a <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.PostConfigure%2A>.</span><span class="sxs-lookup"><span data-stu-id="314f1-161">Exposing the same [`Action<TOptions>` parameter](#actiontoptions-parameter) detailed earlier, you could choose to call <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.PostConfigure%2A>.</span></span> <span data-ttu-id="314f1-162">La configuración posterior se ejecuta después de todas las llamadas a `.Configure`.</span><span class="sxs-lookup"><span data-stu-id="314f1-162">Post configure runs after all `.Configure` calls.</span></span>

:::code language="csharp" source="snippets/configuration/options-postconfig/ServiceCollectionExtensions.cs" highlight="10,12":::

<span data-ttu-id="314f1-163">En el código anterior, `AddMyLibraryService`:</span><span class="sxs-lookup"><span data-stu-id="314f1-163">In the preceding code, the `AddMyLibraryService`:</span></span>

- <span data-ttu-id="314f1-164">extiende una instancia de <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>,</span><span class="sxs-lookup"><span data-stu-id="314f1-164">Extends an instance of <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection></span></span>
- <span data-ttu-id="314f1-165">define <xref:System.Action%601>, donde `T` es el parámetro `configureOptions` de `LibraryOptions` y</span><span class="sxs-lookup"><span data-stu-id="314f1-165">Defines an <xref:System.Action%601> where `T` is `LibraryOptions` parameter `configureOptions`</span></span>
- <span data-ttu-id="314f1-166">llama a <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.PostConfigure%2A>, dada la acción `configureOptions`.</span><span class="sxs-lookup"><span data-stu-id="314f1-166">Calls <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.PostConfigure%2A> given the `configureOptions` action</span></span>

<span data-ttu-id="314f1-167">Los consumidores de este patrón proporcionan una expresión lambda, o bien un delegado que cumple el parámetro `Action<LibraryOptions>`, del mismo modo que lo harían con el [parámetro `Action<TOptions>`] en un escenario que no es posterior a la configuración:</span><span class="sxs-lookup"><span data-stu-id="314f1-167">Consumers in this pattern provide a lambda expression (or a delegate that satisfies the `Action<LibraryOptions>` parameter), just as they would with the [`Action<TOptions>` parameter] in a non-post configuration scenario:</span></span>

:::code language="csharp" source="snippets/configuration/options-postconfig/Program.cs" highlight="22-26":::

## <a name="see-also"></a><span data-ttu-id="314f1-168">Vea también</span><span class="sxs-lookup"><span data-stu-id="314f1-168">See also</span></span>

- [<span data-ttu-id="314f1-169">Patrón de opciones en .NET</span><span class="sxs-lookup"><span data-stu-id="314f1-169">Options pattern in .NET</span></span>](options.md)
- [<span data-ttu-id="314f1-170">Inserción de dependencias en .NET</span><span class="sxs-lookup"><span data-stu-id="314f1-170">Dependency injection in .NET</span></span>](dependency-injection.md)
- [<span data-ttu-id="314f1-171">Instrucciones para la inserción de dependencias</span><span class="sxs-lookup"><span data-stu-id="314f1-171">Dependency injection guidelines</span></span>](dependency-injection-guidelines.md)
