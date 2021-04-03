---
title: Más escenarios de migración
description: En esta sección se describen escenarios y técnicas de migración adicionales para actualizar .NET Framework aplicaciones a .NET Core/.NET 5.
author: ardalis
ms.date: 02/11/2021
ms.openlocfilehash: 672ad1da4611197e7af63d1408836c4c1a26567a
ms.sourcegitcommit: b5d2290673e1c91260c9205202dd8b95fbab1a0b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "106122786"
---
# <a name="more-migration-scenarios"></a><span data-ttu-id="7f87f-103">Más escenarios de migración</span><span class="sxs-lookup"><span data-stu-id="7f87f-103">More migration scenarios</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="7f87f-104">En esta sección se describen varios escenarios de aplicaciones de ASP.NET diferentes y se ofrecen técnicas específicas para resolver cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="7f87f-104">This section describes several different ASP.NET app scenarios, and offers specific techniques for solving each of them.</span></span> <span data-ttu-id="7f87f-105">Puede usar esta sección para identificar los escenarios aplicables a la aplicación y evaluar qué técnicas funcionarán para su aplicación y su entorno de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="7f87f-105">You can use this section to identify scenarios applicable to your app, and evaluate which techniques will work for your app and its hosting environment.</span></span>

## <a name="migrate-aspnet-mvc-5-and-webapi-2-to-aspnet-core-mvc"></a><span data-ttu-id="7f87f-106">Migración de ASP.NET MVC 5 y WebApi 2 a ASP.NET Core MVC</span><span class="sxs-lookup"><span data-stu-id="7f87f-106">Migrate ASP.NET MVC 5 and WebApi 2 to ASP.NET Core MVC</span></span>

<span data-ttu-id="7f87f-107">Un escenario común en las aplicaciones ASP.NET MVC 5 y Web API 2 era que ambos productos se instalaran en la misma aplicación.</span><span class="sxs-lookup"><span data-stu-id="7f87f-107">A common scenario in ASP.NET MVC 5 and Web API 2 apps was for both products to be installed in the same application.</span></span> <span data-ttu-id="7f87f-108">Se trata de un enfoque compatible y relativamente común que usan muchos equipos, pero debido a que los dos productos utilizan abstracciones diferentes, se requiere un esfuerzo redundante.</span><span class="sxs-lookup"><span data-stu-id="7f87f-108">This is a supported and relatively common approach used by many teams, but because the two products use different abstractions, there is some redundant effort needed.</span></span> <span data-ttu-id="7f87f-109">Por ejemplo, la configuración de rutas para ASP.NET MVC se realiza mediante métodos en `RouteCollection` , como `MapMvcAttributeRoutes()` y `MapRoute()` .</span><span class="sxs-lookup"><span data-stu-id="7f87f-109">For example, setting up routes for ASP.NET MVC is done using methods on `RouteCollection`, such as `MapMvcAttributeRoutes()` and `MapRoute()`.</span></span> <span data-ttu-id="7f87f-110">Pero el enrutamiento de ASP.NET Web API 2 se administra con `HttpConfiguration` métodos y como `MapHttpAttributeRoutes()` y `MapHttpRoute()` .</span><span class="sxs-lookup"><span data-stu-id="7f87f-110">But ASP.NET Web API 2 routing is managed with `HttpConfiguration` and methods like `MapHttpAttributeRoutes()` and `MapHttpRoute()`.</span></span>

<span data-ttu-id="7f87f-111">La `eShopLegacyMVC` aplicación incluye ASP.NET MVC y Web API e incluye métodos en su `App_Start` carpeta para configurar las rutas de ambos.</span><span class="sxs-lookup"><span data-stu-id="7f87f-111">The `eShopLegacyMVC` app includes both ASP.NET MVC and Web API, and includes methods in its `App_Start` folder for setting up routes for both.</span></span> <span data-ttu-id="7f87f-112">También admite la inserción de dependencias mediante Autofac, que también requiere dos conjuntos de trabajo similar para configurar:</span><span class="sxs-lookup"><span data-stu-id="7f87f-112">It also supports dependency injection using Autofac, which also requires two sets of similar work to configure:</span></span>

```csharp
protected IContainer RegisterContainer()
{
    var builder = new ContainerBuilder();

    var thisAssembly = Assembly.GetExecutingAssembly();
    builder.RegisterControllers(thisAssembly);      // MVC controllers
    builder.RegisterApiControllers(thisAssembly);   // Web API controllers

    var mockData = bool.Parse(ConfigurationManager.AppSettings["UseMockData"]);
    builder.RegisterModule(new ApplicationModule(mockData));

    var container = builder.Build();

    // set mvc resolver
    DependencyResolver.SetResolver(new AutofacDependencyResolver(container));

    // set webapi resolver
    var resolver = new AutofacWebApiDependencyResolver(container);
    GlobalConfiguration.Configuration.DependencyResolver = resolver;

    return container;
}
```

<span data-ttu-id="7f87f-113">Al actualizar estas aplicaciones para usar ASP.NET Core, se elimina este trabajo duplicado y la confusión que a veces lo acompaña.</span><span class="sxs-lookup"><span data-stu-id="7f87f-113">When upgrading these apps to use ASP.NET Core, this duplicate effort and the confusion that sometimes accompanies it is eliminated.</span></span> <span data-ttu-id="7f87f-114">ASP.NET Core MVC es un marco unificado con un conjunto de reglas para el enrutamiento, los filtros, etc.</span><span class="sxs-lookup"><span data-stu-id="7f87f-114">ASP.NET Core MVC is a unified framework with one set of rules for routing, filters, and more.</span></span> <span data-ttu-id="7f87f-115">La inserción de dependencias está integrada en .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7f87f-115">Dependency injection is built into .NET Core itself.</span></span> <span data-ttu-id="7f87f-116">Todo esto puede configurarse en `Startup.cs` , tal y como se muestra en la `eShopPorted` aplicación en el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="7f87f-116">All of this can can be configured in `Startup.cs`, as is shown in the `eShopPorted` app in the sample.</span></span>

## <a name="migrate-httpresponsemessage-to-aspnet-core"></a><span data-ttu-id="7f87f-117">Migración de HttpResponseMessage a ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7f87f-117">Migrate HttpResponseMessage to ASP.NET Core</span></span>

<span data-ttu-id="7f87f-118">Algunas aplicaciones ASP.NET Web API pueden tener métodos de acción que devuelven `HttpResponseMessage` .</span><span class="sxs-lookup"><span data-stu-id="7f87f-118">Some ASP.NET Web API apps may have action methods that return `HttpResponseMessage`.</span></span> <span data-ttu-id="7f87f-119">Este tipo no existe en ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="7f87f-119">This type does not exist in ASP.NET Core.</span></span> <span data-ttu-id="7f87f-120">A continuación se muestra un ejemplo de su uso en un `Delete` método de acción, mediante el `ResponseMessage` método auxiliar en la base `ApiController` :</span><span class="sxs-lookup"><span data-stu-id="7f87f-120">Below is an example of its usage in a `Delete` action method, using the `ResponseMessage` helper method on the base `ApiController`:</span></span>

```csharp
// DELETE api/<controller>/5
[HttpDelete]
public IHttpActionResult Delete(int id)
{
    var brandToDelete = _service.GetCatalogBrands().FirstOrDefault(x => x.Id == id);
    if (brandToDelete == null)
    {
        return ResponseMessage(new HttpResponseMessage(HttpStatusCode.NotFound));
    }

    // demo only - don't actually delete
    return ResponseMessage(new HttpResponseMessage(HttpStatusCode.OK));
}
```

<span data-ttu-id="7f87f-121">En ASP.NET Core MVC, hay métodos auxiliares disponibles para todos los códigos de estado de respuesta HTTP comunes, por lo que el método anterior se trasladaría al siguiente código:</span><span class="sxs-lookup"><span data-stu-id="7f87f-121">In ASP.NET Core MVC, there are helper methods available for all of the common HTTP response status codes, so the above method would be ported to the following code:</span></span>

```csharp
[HttpDelete("{id}")]
public IActionResult Delete(int id)
{
    var brandToDelete = _service.GetCatalogBrands().FirstOrDefault(x => x.Id == id);
    if (brandToDelete == null)
    {
        return NotFound();
    }

    // demo only - don't actually delete
    return Ok();
}
```

<span data-ttu-id="7f87f-122">Si encuentra que necesita devolver un código de estado personalizado para el que no existe ninguna aplicación auxiliar, siempre puede usar `return StatusCode(int statusCode)` para devolver el código numérico que desee.</span><span class="sxs-lookup"><span data-stu-id="7f87f-122">If you do find that you need to return a custom status code for which no helper exists, you can always use `return StatusCode(int statusCode)` to return any numeric code you like.</span></span>

## <a name="migrate-content-negotiation-from-aspnet-web-api-to-aspnet-core"></a><span data-ttu-id="7f87f-123">Migrar la negociación de contenido de ASP.NET Web API a ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7f87f-123">Migrate content negotiation from ASP.NET Web API to ASP.NET Core</span></span>

<span data-ttu-id="7f87f-124">ASP.NET Web API 2 admite la [negociación de contenido](/aspnet/web-api/overview/formats-and-model-binding/content-negotiation) de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="7f87f-124">ASP.NET Web API 2 supports [content negotiation](/aspnet/web-api/overview/formats-and-model-binding/content-negotiation) natively.</span></span> <span data-ttu-id="7f87f-125">La aplicación de ejemplo incluye un `BrandsController` que muestra esta compatibilidad al enumerar los resultados en XML o JSON.</span><span class="sxs-lookup"><span data-stu-id="7f87f-125">The sample app includes a `BrandsController` that demonstrates this support by listing its results in either XML or JSON.</span></span> <span data-ttu-id="7f87f-126">Esto se basa en el encabezado de la solicitud `Accept` y cambia cuando incluye `application/xml` o `application/json` .</span><span class="sxs-lookup"><span data-stu-id="7f87f-126">This is based on the request's `Accept` header, and changes when it includes `application/xml` or `application/json`.</span></span>

<span data-ttu-id="7f87f-127">Las aplicaciones ASP.NET MVC 5 no admiten la negociación de contenido integrada.</span><span class="sxs-lookup"><span data-stu-id="7f87f-127">ASP.NET MVC 5 apps do not have content negotiation support built in.</span></span>

<span data-ttu-id="7f87f-128">La negociación de contenido es preferible a devolver un tipo de codificación específico, ya que es más flexible y hace que la API esté disponible para un mayor número de clientes.</span><span class="sxs-lookup"><span data-stu-id="7f87f-128">Content negotiation is preferable to returning a specific encoding type, as it is more flexible and makes the API available to a larger number of clients.</span></span> <span data-ttu-id="7f87f-129">Si actualmente tiene métodos de acción que devuelven un formato específico, considere la posibilidad de modificarlos para que devuelvan un tipo de resultado que admita la negociación de contenido al trasladar el código a ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="7f87f-129">If you currently have action methods that return a specific format, you should consider modifying them to return a result type that supports content negotiation when you port the code to ASP.NET Core.</span></span>

<span data-ttu-id="7f87f-130">El código siguiente devuelve datos en formato JSON independientemente del contenido del encabezado de cliente `Accept` :</span><span class="sxs-lookup"><span data-stu-id="7f87f-130">The following code returns data in JSON format regardless of client `Accept` header content:</span></span>

```csharp
[HttpGet]
public ActionResult Index()
{
    return Json(new { Message = "Hello World!" });
}
```

<span data-ttu-id="7f87f-131">[ASP.net Core MVC admite la negociación de contenido](/aspnet/core/web-api/advanced/formatting)de forma nativa, siempre que se use un [tipo de valor devuelto](/aspnet/core/web-api/action-return-types) adecuado.</span><span class="sxs-lookup"><span data-stu-id="7f87f-131">[ASP.NET Core MVC supports content negotiation natively](/aspnet/core/web-api/advanced/formatting), provided an appropriate [return type](/aspnet/core/web-api/action-return-types) is used.</span></span> <span data-ttu-id="7f87f-132">La negociación de contenido se implementa mediante [ObjectResult] devuelta por los resultados de la acción específica del código de estado devueltos por los métodos auxiliares de controlador.</span><span class="sxs-lookup"><span data-stu-id="7f87f-132">Content negotiation is implemented by [ObjectResult] which is returned by the status code-specific action results returned by the controller helper methods.</span></span> <span data-ttu-id="7f87f-133">El método de acción anterior, implementado en ASP.NET Core MVC y usando la negociación de contenido, sería:</span><span class="sxs-lookup"><span data-stu-id="7f87f-133">The previous action method, implemented in ASP.NET Core MVC and using content negotiation, would be:</span></span>

```csharp
public IActionResult Index()
{
    return Ok(new { Message = "Hello World!"} );
}
```

<span data-ttu-id="7f87f-134">De forma predeterminada, se devolverán los datos en formato JSON.</span><span class="sxs-lookup"><span data-stu-id="7f87f-134">This will default to returning the data in JSON format.</span></span> <span data-ttu-id="7f87f-135">XML y otros formatos se utilizarán [si la aplicación se ha configurado con el formateador adecuado](/aspnet/core/web-api/advanced/formatting).</span><span class="sxs-lookup"><span data-stu-id="7f87f-135">XML and other formats will be used [if the app has been configured with the appropriate formatter](/aspnet/core/web-api/advanced/formatting).</span></span>

## <a name="custom-model-binding"></a><span data-ttu-id="7f87f-136">Enlace de modelos personalizado</span><span class="sxs-lookup"><span data-stu-id="7f87f-136">Custom model binding</span></span>

<span data-ttu-id="7f87f-137">La mayoría de las aplicaciones de ASP.NET MVC y Web API hacen uso del enlace de modelos.</span><span class="sxs-lookup"><span data-stu-id="7f87f-137">Most ASP.NET MVC and Web API apps make use of model binding.</span></span> <span data-ttu-id="7f87f-138">La sintaxis de enlace de modelos predeterminada migra de forma bastante fluida entre estas aplicaciones y ASP.NET Core MVC.</span><span class="sxs-lookup"><span data-stu-id="7f87f-138">The default model binding syntax migrates fairly seamlessly between these apps and ASP.NET Core MVC.</span></span> <span data-ttu-id="7f87f-139">Sin embargo, en algunos casos, los clientes han escrito [enlazadores de modelos personalizados](/aspnet/web-api/overview/formats-and-model-binding/parameter-binding-in-aspnet-web-api#model-binders) para admitir determinados tipos de modelos o escenarios de uso.</span><span class="sxs-lookup"><span data-stu-id="7f87f-139">However, in some cases customers have written [custom model binders](/aspnet/web-api/overview/formats-and-model-binding/parameter-binding-in-aspnet-web-api#model-binders) to support specific model types or usage scenarios.</span></span> <span data-ttu-id="7f87f-140">Los enlazadores de modelos personalizados en proyectos de ASP.NET MVC y Web API usan `IModelBinder` interfaces independientes definidas en los `System.Web.Mvc` espacios de `System.Web.Http` nombres y, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="7f87f-140">Custom model binders in ASP.NET MVC and Web API projects use separate `IModelBinder` interfaces defined in `System.Web.Mvc` and `System.Web.Http` namespaces, respectively.</span></span> <span data-ttu-id="7f87f-141">En ambos casos, el enlazador personalizado expone un `Bind` método que acepta un contexto de controlador o de acción y un contexto de enlace de modelo como argumentos.</span><span class="sxs-lookup"><span data-stu-id="7f87f-141">In both cases, the custom binder exposes a `Bind` method that accepts a controller or action context and a model binding context as arguments.</span></span>

<span data-ttu-id="7f87f-142">Una vez creado el enlazador personalizado, se debe registrar con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7f87f-142">Once the custom binder is created, it must be registered with the app.</span></span> <span data-ttu-id="7f87f-143">Este paso requiere la creación de otro tipo, `ModelBinderProvider` que actúa como generador y crea el enlazador de modelos durante una solicitud.</span><span class="sxs-lookup"><span data-stu-id="7f87f-143">This step requires creating another type, a `ModelBinderProvider`, which acts as a factory and creates the model binder during a request.</span></span> <span data-ttu-id="7f87f-144">Los enlazadores se pueden agregar durante `ApplicationStart` en aplicaciones MVC como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="7f87f-144">Binders can be added during `ApplicationStart` in MVC apps as shown:</span></span>

```csharp
ModelBinderProviders.BinderProviders.Insert(0, new MyCustomBinderProvider()); // MVC
```

<span data-ttu-id="7f87f-145">En aplicaciones de API Web, se puede hacer referencia a los enlazadores personalizados mediante atributos.</span><span class="sxs-lookup"><span data-stu-id="7f87f-145">In Web API apps, custom binders can be referenced using attributes.</span></span> <span data-ttu-id="7f87f-146">El `ModelBinder` atributo se puede Agregar a los parámetros de método de acción o a la definición de tipo del parámetro, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="7f87f-146">The `ModelBinder` attribute can be added to action method parameters or to the parameter's type definition, as shown:</span></span>

```csharp
// attribute on action method parameter
public HttpResponseMessage([ModelBinder(typeof(MyCustomBinder))] CustomDTO custom)
{
}

// attribute on type
[ModelBinder(typeof(MyCustomBinder))]
public class CustomDTO
{
}
```

<span data-ttu-id="7f87f-147">Para registrar un enlazador de modelos globalmente en ASP.NET Web API, se debe agregar su proveedor durante el inicio de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="7f87f-147">To register a model binder globally in ASP.NET Web API, its provider must be added during app startup:</span></span>

```csharp
public static class WebApiConfig
{
    public static void Register(HttpConfiguration config)
    {
        var provider = new CustomModelBinderProvider(
            typeof(CustomDTO), new CustomModelBinder());
        config.Services.Insert(typeof(ModelBinderProvider), 0, provider);

        // ...
    }
}
```

<span data-ttu-id="7f87f-148">Al migrar [proveedores de modelos personalizados a ASP.net Core](/aspnet/core/mvc/advanced/custom-model-binding#custom-model-binder-sample), el patrón de API Web está más cerca del enfoque de ASP.NET Core que ASP.NET MVC 5.</span><span class="sxs-lookup"><span data-stu-id="7f87f-148">When migrating [custom model providers to ASP.NET Core](/aspnet/core/mvc/advanced/custom-model-binding#custom-model-binder-sample), the Web API pattern is closer to the ASP.NET Core approach than the ASP.NET MVC 5.</span></span> <span data-ttu-id="7f87f-149">Las principales diferencias entre la interfaz de ASP.NET Core `IModelBinder` y la API Web es que el método ASP.net Core es Async ( `BindModelAsync` ) y solo requiere un `BindingModelContext` parámetro único en lugar de dos parámetros, como la versión de API Web necesaria.</span><span class="sxs-lookup"><span data-stu-id="7f87f-149">The main differences between ASP.NET Core's `IModelBinder` interface and Web API's is that the ASP.NET Core method is async (`BindModelAsync`) and it only requires a single `BindingModelContext` parameter instead of two parameters like Web API's version required.</span></span> <span data-ttu-id="7f87f-150">En ASP.NET Core, puede usar un `[ModelBinder]` atributo en parámetros de método de acción individuales o en sus tipos asociados.</span><span class="sxs-lookup"><span data-stu-id="7f87f-150">In ASP.NET Core, you can use a `[ModelBinder]` attribute on individual action method parameters or their associated types.</span></span> <span data-ttu-id="7f87f-151">También puede crear un `ModelBinderProvider` que se usará globalmente dentro de la aplicación cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="7f87f-151">You can also create a `ModelBinderProvider` that will be used globally within the app where appropriate.</span></span> <span data-ttu-id="7f87f-152">Para configurar este tipo de proveedor, debe agregar código a `Startup` en `ConfigureServices` :</span><span class="sxs-lookup"><span data-stu-id="7f87f-152">To configure such a provider, you would add code to `Startup` in `ConfigureServices`:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddControllers(options =>
    {
        options.ModelBinderProviders.Insert(0, new CustomModelBinderProvider());
    });
}
```

## <a name="media-formatters"></a><span data-ttu-id="7f87f-153">Formateadores multimedia</span><span class="sxs-lookup"><span data-stu-id="7f87f-153">Media formatters</span></span>

<span data-ttu-id="7f87f-154">ASP.NET Web API admite varios formatos multimedia y se puede extender mediante formateadores multimedia personalizados.</span><span class="sxs-lookup"><span data-stu-id="7f87f-154">ASP.NET Web API supports multiple media formats and can be extended by using custom media formatters.</span></span> <span data-ttu-id="7f87f-155">Los documentos describen un [formateador de medios CSV de ejemplo](/aspnet/web-api/overview/formats-and-model-binding/media-formatters#example-creating-a-csv-media-formatter) que se puede usar para enviar datos en un formato de valores separados por comas.</span><span class="sxs-lookup"><span data-stu-id="7f87f-155">The docs describe an [example CSV Media Formatter](/aspnet/web-api/overview/formats-and-model-binding/media-formatters#example-creating-a-csv-media-formatter) that can be used to send data in a comma-separated value format.</span></span> <span data-ttu-id="7f87f-156">Si la aplicación de API Web usa formateadores de medios personalizados, deberá convertirlos en [ASP.net Core formateadores personalizados](/aspnet/core/web-api/advanced/custom-formatters).</span><span class="sxs-lookup"><span data-stu-id="7f87f-156">If your Web API app uses custom media formatters, you'll need to convert them to [ASP.NET Core custom formatters](/aspnet/core/web-api/advanced/custom-formatters).</span></span>

<span data-ttu-id="7f87f-157">Para crear un formateador personalizado en Web API 2, se ha heredado de una clase base adecuada y, a continuación, se ha agregado el formateador a la canalización de la API Web mediante el `HttpConfiguration` objeto:</span><span class="sxs-lookup"><span data-stu-id="7f87f-157">To create a custom formatter in Web API 2, you inherited from an appropriate base class and then added the formatter to the Web API pipeline using the `HttpConfiguration` object:</span></span>

```csharp
public static void ConfigureApis(HttpConfiguration config)
{
    config.Formatters.Add(new ProductCsvFormatter()); 
}
```

<span data-ttu-id="7f87f-158">En ASP.NET Core, el proceso es similar.</span><span class="sxs-lookup"><span data-stu-id="7f87f-158">In ASP.NET Core, the process is similar.</span></span> <span data-ttu-id="7f87f-159">ASP.NET Core admite formateadores de entrada (utilizados por el enlace de modelos) y formateadores de salida (usados para dar formato a las respuestas).</span><span class="sxs-lookup"><span data-stu-id="7f87f-159">ASP.NET Core supports both input formatters (used by model binding) and output formatters (used to format responses).</span></span> <span data-ttu-id="7f87f-160">Agregar un formateador personalizado a las respuestas de salida de una manera específica implica heredar de una clase base adecuada y agregar el formateador a MVC en `Startup` :</span><span class="sxs-lookup"><span data-stu-id="7f87f-160">Adding a custom formatter to output responses in a specific way involves inheriting from an appropriate base class and adding the formatter to MVC in `Startup`:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddControllers(options =>
    {
        options.InputFormatters.Insert(0, new CustomInputFormatter());
        options.OutputFormatters.Insert(0, new CustomOutputFormatter());
    });
}
```

<span data-ttu-id="7f87f-161">Encontrará una lista completa de las clases base en el espacio de nombres [Microsoft. AspNetCore. Mvc. Formatters](https://docs.microsoft.com/dotnet/api/microsoft.aspnetcore.mvc.formatters) .</span><span class="sxs-lookup"><span data-stu-id="7f87f-161">You'll find a complete list of base classes in the [Microsoft.AspNetCore.Mvc.Formatters](https://docs.microsoft.com/dotnet/api/microsoft.aspnetcore.mvc.formatters) namespace.</span></span>

<span data-ttu-id="7f87f-162">Los pasos para migrar desde un formateador de Web API a un formateador de MVC ASP.NET Core son:</span><span class="sxs-lookup"><span data-stu-id="7f87f-162">The steps to migrate from a Web API formatter to an ASP.NET Core MVC formatter are:</span></span>

1. <span data-ttu-id="7f87f-163">Identifique una clase base adecuada para el nuevo formateador.</span><span class="sxs-lookup"><span data-stu-id="7f87f-163">Identify an appropriate base class for the new formatter.</span></span>
1. <span data-ttu-id="7f87f-164">Cree una nueva instancia de la clase base e implemente los métodos necesarios.</span><span class="sxs-lookup"><span data-stu-id="7f87f-164">Create a new instance of the base class and implement its required methods.</span></span>
1. <span data-ttu-id="7f87f-165">Copie la funcionalidad del formateador de la API Web a la nueva implementación.</span><span class="sxs-lookup"><span data-stu-id="7f87f-165">Copy over the functionality from the Web API formatter to the new implementation.</span></span>
1. <span data-ttu-id="7f87f-166">Configure MVC en el método de la aplicación ASP.NET Core `ConfigureServices` para usar el formateador nuevo.</span><span class="sxs-lookup"><span data-stu-id="7f87f-166">Configure MVC in the ASP.NET Core App's `ConfigureServices` method to use the new formatter.</span></span>

## <a name="custom-filters"></a><span data-ttu-id="7f87f-167">Filtros personalizados</span><span class="sxs-lookup"><span data-stu-id="7f87f-167">Custom filters</span></span>

<span data-ttu-id="7f87f-168">Los filtros se usan en ASP.NET Core aplicaciones para ejecutar código antes o después de ciertas fases de la canalización de procesamiento de solicitudes.</span><span class="sxs-lookup"><span data-stu-id="7f87f-168">Filters are used in ASP.NET Core apps to execute code before and/or after certain stages in the request processing pipeline.</span></span> <span data-ttu-id="7f87f-169">ASP.NET MVC y Web API también usan filtros de forma muy similar, pero los detalles varían.</span><span class="sxs-lookup"><span data-stu-id="7f87f-169">ASP.NET MVC and Web API also use filters in much the same way, but the details vary.</span></span> <span data-ttu-id="7f87f-170">Por ejemplo, [ASP.NET MVC admite cuatro tipos de filtros](/aspnet/mvc/overview/older-versions-1/controllers-and-routing/understanding-action-filters-cs#the-different-types-of-filters).</span><span class="sxs-lookup"><span data-stu-id="7f87f-170">For instance, [ASP.NET MVC supports four kinds of filters](/aspnet/mvc/overview/older-versions-1/controllers-and-routing/understanding-action-filters-cs#the-different-types-of-filters).</span></span> <span data-ttu-id="7f87f-171">ASP.NET Web API 2 admite filtros similares y los atributos MVC y Web API incluidos para [invalidar los filtros](/dotnet/api/system.web.mvc.filters.ioverridefilter).</span><span class="sxs-lookup"><span data-stu-id="7f87f-171">ASP.NET Web API 2 supports similar filters, and both MVC and Web API included attributes to [override filters](/dotnet/api/system.web.mvc.filters.ioverridefilter).</span></span>

<span data-ttu-id="7f87f-172">El filtro más común que se usa en las aplicaciones de ASP.NET MVC y Web API es el filtro de acción, que se define mediante una [interfaz IActionFilter](/dotnet/api/system.web.mvc.iactionfilter).</span><span class="sxs-lookup"><span data-stu-id="7f87f-172">The most common filter used in ASP.NET MVC and Web API apps is the action filter, which is defined by an [IActionFilter interface](/dotnet/api/system.web.mvc.iactionfilter).</span></span> <span data-ttu-id="7f87f-173">Esta interfaz proporciona métodos para antes ( `OnActionExecuting` ) y después de ( `OnActionExecuted` ), que se pueden utilizar para ejecutar código antes o después de que se ejecute una acción, como se indica en cada método.</span><span class="sxs-lookup"><span data-stu-id="7f87f-173">This interface provides methods for before (`OnActionExecuting`) and after (`OnActionExecuted`) which can be used to execute code before and/or after an action executes, as noted for each method.</span></span>

<span data-ttu-id="7f87f-174">ASP.NET Core sigue admitiendo filtros y su unificación de MVC y Web API significa que solo hay un enfoque para su implementación.</span><span class="sxs-lookup"><span data-stu-id="7f87f-174">ASP.NET Core continues to support filters, and its unification of MVC and Web API means there is only one approach to their implementation.</span></span> <span data-ttu-id="7f87f-175">Los [documentos incluyen una cobertura detallada de los cinco (5) tipos de filtros integrados en ASP.net Core MVC](/aspnet/core/mvc/controllers/filters#filter-types).</span><span class="sxs-lookup"><span data-stu-id="7f87f-175">The [docs include detailed coverage of the five (5) kinds of filters built into ASP.NET Core MVC](/aspnet/core/mvc/controllers/filters#filter-types).</span></span> <span data-ttu-id="7f87f-176">Todas las variantes de filtro que se admiten en ASP.NET MVC y ASP.NET Web API tienen asociadas versiones en ASP.NET Core, por lo que la migración suele ser solo cuestión de identificar la interfaz o clase base adecuada y migrar el código.</span><span class="sxs-lookup"><span data-stu-id="7f87f-176">All of the filter variants supported in ASP.NET MVC and ASP.NET Web API have associated versions in ASP.NET Core, so migration is generally just a matter of identifying the appropriate interface and/or base class and migrating the code over.</span></span>

<span data-ttu-id="7f87f-177">Además de las interfaces sincrónicas, ASP.NET Core también proporciona interfaces asincrónicas como `IAsyncActionFilter` las que proporcionan un único método asincrónico que se puede usar para incorporar código para ejecutarse antes y después de la acción, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="7f87f-177">In addition to the synchronous interfaces, ASP.NET Core also provides async interfaces like `IAsyncActionFilter` which provide a single async method that can be used to incorporate code to run both before and after the action, as shown:</span></span>

```csharp
public class SampleAsyncActionFilter : IAsyncActionFilter
{
    public async Task OnActionExecutionAsync(
        ActionExecutingContext context,
        ActionExecutionDelegate next)
    {
        // Do something before the action executes.

        // next() calls the action method.
        var resultContext = await next();
        // resultContext.Result is set.
        // Do something after the action executes.
    }
}
```

<span data-ttu-id="7f87f-178">Al migrar código asincrónico (o código que debe ser asincrónico), los equipos deben considerar la posibilidad de aprovechar los tipos Async integrados que se proporcionan con este fin.</span><span class="sxs-lookup"><span data-stu-id="7f87f-178">When migrating async code (or code that should be async), teams should consider leveraging the built in async types that are provided for this purpose.</span></span>

<span data-ttu-id="7f87f-179">La mayoría de las aplicaciones de ASP.NET MVC y Web API no usan un gran número de filtros personalizados.</span><span class="sxs-lookup"><span data-stu-id="7f87f-179">Most ASP.NET MVC and Web API apps do not use a large number of custom filters.</span></span> <span data-ttu-id="7f87f-180">Dado que el enfoque de los filtros en ASP.NET Core MVC está estrechamente alineado con los filtros de ASP.NET MVC y Web API, la migración de filtros personalizados es generalmente bastante sencilla.</span><span class="sxs-lookup"><span data-stu-id="7f87f-180">Since the approach to filters in ASP.NET Core MVC is closely aligned with filters in ASP.NET MVC and Web API, the migration of custom filters is generally fairly straightforward.</span></span> <span data-ttu-id="7f87f-181">Asegúrese de leer la documentación detallada sobre los filtros en los documentos de ASP.NET Core y, una vez que esté seguro de que tiene una buena comprensión de ellos, porte la lógica del sistema anterior a los filtros del sistema nuevo.</span><span class="sxs-lookup"><span data-stu-id="7f87f-181">Be sure to read the detailed documentation on filters in ASP.NET Core's docs, and once you're sure you have a good understanding of them, port the logic from the old system to the new system's filters.</span></span>

## <a name="route-constraints"></a><span data-ttu-id="7f87f-182">Restricciones de ruta</span><span class="sxs-lookup"><span data-stu-id="7f87f-182">Route constraints</span></span>

<span data-ttu-id="7f87f-183">ASP.NET Core usa restricciones de ruta para asegurarse de que las solicitudes se enruten correctamente para enrutar una solicitud.</span><span class="sxs-lookup"><span data-stu-id="7f87f-183">ASP.NET Core uses route constraints to help ensure requests are routed properly to route a request.</span></span> <span data-ttu-id="7f87f-184">[ASP.NET Core admite un gran número de restricciones de ruta diferentes para este propósito]/ASPNET/Core/Fundamentals/Routing # Route-Constraint-Reference.</span><span class="sxs-lookup"><span data-stu-id="7f87f-184">[ASP.NET Core supports a large number of different route constraints for this purpose]/aspnet/core/fundamentals/routing#route-constraint-reference).</span></span> <span data-ttu-id="7f87f-185">Las restricciones de ruta se pueden aplicar en la tabla de rutas, pero la mayoría de las aplicaciones compiladas con ASP.NET MVC 5 y/o [ASP.net web API 2](/aspnet/web-api/overview/web-api-routing-and-actions/attribute-routing-in-web-api-2#route-constraints) usan restricciones de ruta insertadas que se aplican a las rutas de atributo.</span><span class="sxs-lookup"><span data-stu-id="7f87f-185">Route constraints can be applied in the route table, but most apps built with ASP.NET MVC 5 and/or [ASP.NET Web API 2](/aspnet/web-api/overview/web-api-routing-and-actions/attribute-routing-in-web-api-2#route-constraints) use inline route constraints applied to attribute routes.</span></span> <span data-ttu-id="7f87f-186">Las restricciones de ruta en línea utilizan un formato como este:</span><span class="sxs-lookup"><span data-stu-id="7f87f-186">Inline route constraints use a format like this one:</span></span>

```csharp
[Route("/customer/{id:int}")]
```

<span data-ttu-id="7f87f-187">`:int`Después de que el `id` parámetro de ruta restringe el valor para que coincida con el `int` tipo.</span><span class="sxs-lookup"><span data-stu-id="7f87f-187">The `:int` after the `id` route parameter constrains the value to match the the `int` type.</span></span> <span data-ttu-id="7f87f-188">Una ventaja del uso de restricciones de ruta es que permiten dos rutas que, de otro modo, son idénticas, donde los parámetros solo se diferencian por su tipo.</span><span class="sxs-lookup"><span data-stu-id="7f87f-188">One benefit of using route constraints is that they allow for two otherwise-identical routes to exist where the parameters differ only by their type.</span></span> <span data-ttu-id="7f87f-189">Esto permite el equivalente de la [sobrecarga de métodos](/dotnet/standard/design-guidelines/member-overloading) de las rutas basadas únicamente en el tipo de parámetro.</span><span class="sxs-lookup"><span data-stu-id="7f87f-189">This allows for the equivalent of [method overloading](/dotnet/standard/design-guidelines/member-overloading) of routes based solely on parameter type.</span></span>

<span data-ttu-id="7f87f-190">El conjunto de restricciones de ruta, su sintaxis y el uso son muy similares entre los tres métodos.</span><span class="sxs-lookup"><span data-stu-id="7f87f-190">The set of route constraints, their syntax, and usage is very similar between all three approaches.</span></span> <span data-ttu-id="7f87f-191">Las restricciones de ruta personalizadas son bastante poco frecuentes en las aplicaciones de cliente.</span><span class="sxs-lookup"><span data-stu-id="7f87f-191">Custom route constraints are fairly rare in customer applications.</span></span> <span data-ttu-id="7f87f-192">Si la aplicación usa una restricción de ruta personalizada y necesita portar a ASP.NET Core, los documentos incluyen ejemplos que muestran [Cómo crear restricciones de ruta personalizadas en ASP.net Core](/aspnet/core/fundamentals/routing#custom-route-constraints).</span><span class="sxs-lookup"><span data-stu-id="7f87f-192">If your app uses a custom route constraint and needs to port to ASP.NET Core, the docs include examples showing [how to create custom route constraints in ASP.NET Core](/aspnet/core/fundamentals/routing#custom-route-constraints).</span></span> <span data-ttu-id="7f87f-193">Esencialmente, lo único que se necesita es implementar `IRouteConstraint` y su `Match` método y, después, agregar la restricción personalizada al configurar el enrutamiento de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="7f87f-193">Essentially all that's required is to implement `IRouteConstraint` and its `Match` method, and then add the custom constraint when configuring routing for the app:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddControllers();

    services.AddRouting(options =>
    {
        options.ConstraintMap.Add("customName", typeof(MyCustomConstraint));
    });
}
```

<span data-ttu-id="7f87f-194">Esto es muy similar a cómo se usan las restricciones personalizadas en ASP.NET Web API, que usa `IHttpRouteConstraint` y configura mediante un solucionador y una llamada a `HttpConfiguration.MapHttpAttributeRoutes` :</span><span class="sxs-lookup"><span data-stu-id="7f87f-194">This is very similar to how custom constraints are used in ASP.NET Web API, which uses `IHttpRouteConstraint` and configures it using a resolver and a call to `HttpConfiguration.MapHttpAttributeRoutes`:</span></span>

```csharp
public static class WebApiConfig
{
    public static void Register(HttpConfiguration config)
    {
        var constraintResolver = new DefaultInlineConstraintResolver();
        constraintResolver.ConstraintMap.Add("nonzero", typeof(CustomConstraint));

        config.MapHttpAttributeRoutes(constraintResolver);
    }
}
```

<span data-ttu-id="7f87f-195">ASP.NET MVC 5 sigue un enfoque muy similar, usando `IRouteConstraint` para su nombre de interfaz y configurando la restricción como parte de la configuración de la ruta:</span><span class="sxs-lookup"><span data-stu-id="7f87f-195">ASP.NET MVC 5 follows a very similar approach, using `IRouteConstraint` for its interface name and configuring the constraint as part of route configuration:</span></span>

```csharp
public class RouteConfig
{
    public static void RegisterRoutes(RouteCollection routes)
    {
        routes.IgnoreRoute("{resource}.axd/{*pathInfo}");
 
        var constraintsResolver = new DefaultInlineConstraintResolver();
        constraintsResolver.ConstraintMap.Add("values", typeof(ValuesConstraint));
        routes.MapMvcAttributeRoutes(constraintsResolver);
    }
}
```

<span data-ttu-id="7f87f-196">La migración del uso de restricciones de ruta y las restricciones de ruta personalizadas a ASP.NET Core suele ser muy sencilla.</span><span class="sxs-lookup"><span data-stu-id="7f87f-196">Migrating route constraint usage as well as custom route constraints to ASP.NET Core is typically very straightforward.</span></span>

## <a name="custom-route-handlers"></a><span data-ttu-id="7f87f-197">Controladores de rutas personalizados</span><span class="sxs-lookup"><span data-stu-id="7f87f-197">Custom route handlers</span></span>

<span data-ttu-id="7f87f-198">Otra característica bastante avanzada de ASP.NET MVC 5 son los controladores de ruta.</span><span class="sxs-lookup"><span data-stu-id="7f87f-198">Another fairly advanced feature of ASP.NET MVC 5 is route handlers.</span></span> <span data-ttu-id="7f87f-199">Los controladores de rutas personalizados implementan `IRouteHandler` , que incluye un único método que devuelve un `IHttpHandler` para una solicitud de entrega.</span><span class="sxs-lookup"><span data-stu-id="7f87f-199">Custom route handlers implement `IRouteHandler`, which includes a single method that returns an `IHttpHandler` for a give request.</span></span> <span data-ttu-id="7f87f-200">`IHttpHandler`A su vez, expone una `IsReusable` propiedad y un `ProcessRequest` método único.</span><span class="sxs-lookup"><span data-stu-id="7f87f-200">The `IHttpHandler`, in turn, exposes an `IsReusable` property and a single `ProcessRequest` method.</span></span> <span data-ttu-id="7f87f-201">En ASP.NET MVC 5, puede configurar una ruta determinada en la tabla de rutas para usar el controlador personalizado:</span><span class="sxs-lookup"><span data-stu-id="7f87f-201">In ASP.NET MVC 5, you can configure a particular route in the route table to use your custom handler:</span></span>

```csharp
public static void RegisterRoutes(RouteCollection routes)
{
    routes.IgnoreRoute("{resource}.axd/{*pathInfo}");
 
    routes.Add(new Route("custom", new CustomRouteHandler()));
}
```

<span data-ttu-id="7f87f-202">Para migrar controladores de rutas personalizados de ASP.NET MVC 5 a ASP.NET Core, puede usar un filtro (por ejemplo, un filtro de acción) o un personalizado [`IRouter`](/dotnet/api/microsoft.aspnetcore.routing.irouter) .</span><span class="sxs-lookup"><span data-stu-id="7f87f-202">To migrate custom route handlers from ASP.NET MVC 5 to ASP.NET Core, you can either use a filter (such as an action filter) or a custom [`IRouter`](/dotnet/api/microsoft.aspnetcore.routing.irouter).</span></span> <span data-ttu-id="7f87f-203">El enfoque de filtro es relativamente sencillo y se puede agregar como un filtro global cuando MVC se agrega a `ConfigureServices` en *Startup. CS*.</span><span class="sxs-lookup"><span data-stu-id="7f87f-203">The filter approach is relatively straightforward, and can be added as a global filter when MVC is added to `ConfigureServices` in *Startup.cs*.</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddMvc(options =>
    {
        options.Filters.Add(typeof(CustomActionFilter));
    });
}
```

<span data-ttu-id="7f87f-204">La `IRouter` opción requiere la implementación de los `RouteAsync` métodos y de la interfaz `GetVirtualPath` .</span><span class="sxs-lookup"><span data-stu-id="7f87f-204">The `IRouter` option requires implementing the interface's `RouteAsync` and `GetVirtualPath` methods.</span></span> <span data-ttu-id="7f87f-205">El enrutador personalizado se agrega a la canalización de solicitudes en el `Configure` método en *Startup. CS*.</span><span class="sxs-lookup"><span data-stu-id="7f87f-205">The custom router is added to the request pipeline in the `Configure` method in *Startup.cs*.</span></span>

```csharp
public void Configure(IApplicationBuilder app)
{
    // ...
    app.UseMvc(routes =>
    {
        routes.Routes.Add(new CustomRouter(routes.DefaultHandler));
    });
}
```

<span data-ttu-id="7f87f-206">En ASP.NET Web API, estos controladores se conocen como controladores de [mensajes personalizados](/aspnet/web-api/overview/advanced/http-message-handlers#custom-message-handlers), en lugar de *controladores de ruta*.</span><span class="sxs-lookup"><span data-stu-id="7f87f-206">In ASP.NET Web API, these handlers are referred to as [custom message handlers](/aspnet/web-api/overview/advanced/http-message-handlers#custom-message-handlers), rather than *route handlers*.</span></span> <span data-ttu-id="7f87f-207">Los controladores de mensajes deben derivar de `DelegatingHandler` e invalidar su `SendAsync` método.</span><span class="sxs-lookup"><span data-stu-id="7f87f-207">Message handlers must derive from `DelegatingHandler` and override its `SendAsync` method.</span></span> <span data-ttu-id="7f87f-208">Los controladores de mensajes se pueden encadenar juntos para formar una canalización de un modo muy similar a ASP.NET Core middleware y su canalización de solicitudes.</span><span class="sxs-lookup"><span data-stu-id="7f87f-208">Message handlers can be chained together to form a pipeline in a fashion that is very similar to ASP.NET Core middleware and its request pipeline.</span></span>

<span data-ttu-id="7f87f-209">ASP.NET Core no tiene un `DelegatingHandler` tipo o una canalización de controlador de mensajes independiente.</span><span class="sxs-lookup"><span data-stu-id="7f87f-209">ASP.NET Core has no `DelegatingHandler` type or separate message handler pipeline.</span></span> <span data-ttu-id="7f87f-210">En su lugar, estos controladores se deben migrar mediante filtros globales, `IRouter` instancias personalizadas (véase más arriba) o middleware personalizado.</span><span class="sxs-lookup"><span data-stu-id="7f87f-210">Instead, such handlers should be migrated using global filters, custom `IRouter` instances (see above), or custom middleware.</span></span> <span data-ttu-id="7f87f-211">ASP.NET Core los filtros y `IRouter` tipos MVC tienen la ventaja de tener acceso integrado a las construcciones MVC como los controladores y las acciones, mientras que el middleware es un enfoque de nivel inferior que no tiene ninguna vinculación a MVC.</span><span class="sxs-lookup"><span data-stu-id="7f87f-211">ASP.NET Core MVC filters and `IRouter` types have the advantage of having built-in access to MVC constructs like controllers and actions, while middleware is a lower level approach that has no ties to MVC.</span></span> <span data-ttu-id="7f87f-212">Esto hace que sea más flexible, pero también requiere más esfuerzo si necesita tener acceso a los componentes de MVC.</span><span class="sxs-lookup"><span data-stu-id="7f87f-212">This makes it more flexible but also requires more effort if you need to access MVC components.</span></span>

## <a name="cors-support"></a><span data-ttu-id="7f87f-213">Compatibilidad con CORS</span><span class="sxs-lookup"><span data-stu-id="7f87f-213">CORS support</span></span>

<span data-ttu-id="7f87f-214">CORS, o el uso compartido de recursos entre orígenes, es un estándar del W3C que permite a los servidores aceptar solicitudes que no se originan a partir de las respuestas a las que han servido.</span><span class="sxs-lookup"><span data-stu-id="7f87f-214">CORS, or Cross-Origin Resource Sharing, is a W3C standard that allows servers to accept requests that don't originate from responses they've served.</span></span> <span data-ttu-id="7f87f-215">ASP.NET MVC 5 y ASP.NET Web API 2 admiten CORS de maneras diferentes.</span><span class="sxs-lookup"><span data-stu-id="7f87f-215">ASP.NET MVC 5 and ASP.NET Web API 2 support CORS in different ways.</span></span> <span data-ttu-id="7f87f-216">La manera más sencilla de habilitar la compatibilidad con CORS en ASP.NET MVC 5 es con un filtro de acción como este:</span><span class="sxs-lookup"><span data-stu-id="7f87f-216">The simplest way to enable CORS support in ASP.NET MVC 5 is with an action filter like this one:</span></span>

```csharp
public class AllowCrossSiteAttribute : ActionFilterAttribute
{
    public override void OnActionExecuting(ActionExecutingContext filterContext)
    {
        filterContext.RequestContext.HttpContext.Response.AddHeader(
            "Access-Control-Allow-Origin", "example.com");
        base.OnActionExecuting(filterContext);
    }
}
```

<span data-ttu-id="7f87f-217">ASP.NET Web API también puede usar este tipo de filtro, pero también tiene [compatibilidad integrada para habilitar CORS](/aspnet/web-api/overview/security/enabling-cross-origin-requests-in-web-api#enable-cors) también:</span><span class="sxs-lookup"><span data-stu-id="7f87f-217">ASP.NET Web API can also use such a filter, but it has [built-in support for enabling CORS](/aspnet/web-api/overview/security/enabling-cross-origin-requests-in-web-api#enable-cors) as well:</span></span>

```csharp
public static class WebApiConfig
{
    public static void Register(HttpConfiguration config)
    {
        config.EnableCors();
        // ...
    }
}
```

<span data-ttu-id="7f87f-218">Una vez que se agrega, puede configurar orígenes, encabezados y métodos permitidos mediante el `EnableCors` atributo, de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="7f87f-218">Once this is added, you can configure allowed origins, headers, and methods using the `EnableCors` attribute, like so:</span></span>

```csharp
[EnableCors(origins: "https://dot.net", headers: "*", methods: "*")]
public class TestController : ApiController
{
    // Controller methods not shown...
}
```

<span data-ttu-id="7f87f-219">Antes de migrar la implementación de CORS desde ASP.NET MVC 5 o ASP.NET Web API 2, asegúrese de revisar [Cómo funciona CORS](/aspnet/web-api/overview/security/enabling-cross-origin-requests-in-web-api#how-cors-works) y crear algunas pruebas automatizadas que demuestran que CORS funciona según lo previsto en el sistema actual.</span><span class="sxs-lookup"><span data-stu-id="7f87f-219">Before migrating your CORS implementation from ASP.NET MVC 5 or ASP.NET Web API 2, be sure to review [how CORS works](/aspnet/web-api/overview/security/enabling-cross-origin-requests-in-web-api#how-cors-works) and create some automated tests that demonstrate CORS is working as expected in your current system.</span></span>

<span data-ttu-id="7f87f-220">En ASP.NET Core, hay tres formas integradas de habilitar CORS:</span><span class="sxs-lookup"><span data-stu-id="7f87f-220">In ASP.NET Core, there are three built-in ways to enable CORS:</span></span>

- <span data-ttu-id="7f87f-221">[Configurado a través](/aspnet/core/security/cors?#cors-with-named-policy-and-middleware) de la Directiva en `ConfigureServices`</span><span class="sxs-lookup"><span data-stu-id="7f87f-221">[Configured via policy](/aspnet/core/security/cors?#cors-with-named-policy-and-middleware) in `ConfigureServices`</span></span>
- <span data-ttu-id="7f87f-222">Habilitado con [enrutamiento de punto de conexión](/aspnet/core/security/cors?#enable-cors-with-endpoint-routing)</span><span class="sxs-lookup"><span data-stu-id="7f87f-222">Enabled with [endpoint routing](/aspnet/core/security/cors?#enable-cors-with-endpoint-routing)</span></span>
- <span data-ttu-id="7f87f-223">Habilitado con el [ `EnableCors` atributo](/aspnet/core/security/cors?view=aspnetcore-5.0#enable-cors-with-attributes)</span><span class="sxs-lookup"><span data-stu-id="7f87f-223">Enabled with the [`EnableCors` attribute](/aspnet/core/security/cors?view=aspnetcore-5.0#enable-cors-with-attributes)</span></span>

<span data-ttu-id="7f87f-224">Cada uno de estos enfoques se trata en detalle en los documentos, que están vinculados de las opciones anteriores.</span><span class="sxs-lookup"><span data-stu-id="7f87f-224">Each of these approaches is covered in detail in the docs, which are linked from the above options.</span></span> <span data-ttu-id="7f87f-225">El que elija dependerá en gran medida de cómo la aplicación existente sea compatible con CORS.</span><span class="sxs-lookup"><span data-stu-id="7f87f-225">Which one you choose will largely depend on how your existing app supports CORS.</span></span> <span data-ttu-id="7f87f-226">Si la aplicación usa atributos, probablemente pueda migrar para usar el `EnableCors` atributo más fácilmente.</span><span class="sxs-lookup"><span data-stu-id="7f87f-226">If the app uses attributes, you can probably migrate to use the `EnableCors` attribute most easily.</span></span> <span data-ttu-id="7f87f-227">Si la aplicación usa filtros, puede seguir usando ese enfoque (aunque no es el enfoque típico que se usa en ASP.NET Core) o migrar para usar atributos o directivas.</span><span class="sxs-lookup"><span data-stu-id="7f87f-227">If your app uses filters, you could continue using that approach (though it's not the typical approach used in ASP.NET Core), or migrate to use attributes or policies.</span></span> <span data-ttu-id="7f87f-228">El enrutamiento de puntos de conexión es una característica relativamente nueva que se presentó con ASP.NET Core 3 y, como tal, no tiene un estrecho análogo en las aplicaciones ASP.NET MVC 5 o ASP.NET Web API 2.</span><span class="sxs-lookup"><span data-stu-id="7f87f-228">Endpoint routing is a relatively new feature introduced with ASP.NET Core 3 and as such it doesn't have a close analog in ASP.NET MVC 5 or ASP.NET Web API 2 apps.</span></span>

## <a name="custom-areas"></a><span data-ttu-id="7f87f-229">Áreas personalizadas</span><span class="sxs-lookup"><span data-stu-id="7f87f-229">Custom areas</span></span>

<span data-ttu-id="7f87f-230">Muchas aplicaciones ASP.NET MVC usan áreas para organizar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="7f87f-230">Many ASP.NET MVC apps use Areas to organize the project.</span></span> <span data-ttu-id="7f87f-231">Normalmente, las áreas residen en la raíz del proyecto en una carpeta de *áreas* y deben registrarse cuando se inicia la aplicación, normalmente en `Application_Start()` :</span><span class="sxs-lookup"><span data-stu-id="7f87f-231">Areas typically reside in the root of the project in an *Areas* folder, and must be registered when the application starts, typically in `Application_Start()`:</span></span>

```csharp
AreaRegistration.RegisterAllAreas();
```

<span data-ttu-id="7f87f-232">Una alternativa al registro de todas las áreas en el inicio es usar el `RouteArea` atributo en los controladores individuales:</span><span class="sxs-lookup"><span data-stu-id="7f87f-232">An alternative to registering all areas in startup is to use the `RouteArea` attribute on individual controllers:</span></span>

```csharp
[RouteArea("Admin")]
public class SomeController : Controller
```

<span data-ttu-id="7f87f-233">Cuando se usan áreas, se pasan argumentos adicionales a métodos auxiliares HTML para generar vínculos a acciones en diferentes áreas:</span><span class="sxs-lookup"><span data-stu-id="7f87f-233">When using Areas, additional arguments are passed into HTML helper methods to generate links to actions in different areas:</span></span>

```cshtml
@Html.ActionLink("News", "Index", "News", new { area = "News" }, null)
```

<span data-ttu-id="7f87f-234">Las aplicaciones ASP.NET Web API no suelen usar áreas explícitamente, ya que sus controladores pueden colocarse en cualquier carpeta del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7f87f-234">ASP.NET Web API apps don't typically use areas explicitly, since their controllers can be placed in any folder in the project.</span></span> <span data-ttu-id="7f87f-235">Los equipos pueden usar cualquier estructura de carpetas que deseen para organizar sus controladores de API.</span><span class="sxs-lookup"><span data-stu-id="7f87f-235">Teams can use any folder structure they like to organize their API controllers.</span></span>

<span data-ttu-id="7f87f-236">Las [áreas](/aspnet/core/mvc/controllers/areas) se admiten en ASP.net Core MVC.</span><span class="sxs-lookup"><span data-stu-id="7f87f-236">[Areas](/aspnet/core/mvc/controllers/areas) are supported in ASP.NET Core MVC.</span></span> <span data-ttu-id="7f87f-237">El enfoque utilizado es casi idéntico al uso de áreas de ASP.NET MVC 5.</span><span class="sxs-lookup"><span data-stu-id="7f87f-237">The approach used is nearly identical to the use of areas in ASP.NET MVC 5.</span></span> <span data-ttu-id="7f87f-238">Los desarrolladores que migran código mediante áreas deben tener en cuenta las siguientes diferencias:</span><span class="sxs-lookup"><span data-stu-id="7f87f-238">Developers migrating code using areas should keep in mind the following differences:</span></span>

- <span data-ttu-id="7f87f-239">`AreaRegistration.RegisterAllAreas` no se usa en ASP.NET Core MVC</span><span class="sxs-lookup"><span data-stu-id="7f87f-239">`AreaRegistration.RegisterAllAreas` is not used in ASP.NET Core MVC</span></span>
- <span data-ttu-id="7f87f-240">Las áreas se aplican mediante el `[Area("name")]` atributo (no `RouteArea` como en ASP.NET MVC 5)</span><span class="sxs-lookup"><span data-stu-id="7f87f-240">Areas are applied using the `[Area("name")]` attribute (not `RouteArea` as in ASP.NET MVC 5)</span></span>
- <span data-ttu-id="7f87f-241">Se pueden agregar áreas a las plantillas de tabla de rutas, si se desea (o pueden usar el enrutamiento de atributos).</span><span class="sxs-lookup"><span data-stu-id="7f87f-241">Areas can be added to the route table templates, if desired (or they can use attribute routing)</span></span>

<span data-ttu-id="7f87f-242">Para agregar compatibilidad de área a la tabla de rutas en ASP.NET Core MVC, debe agregar lo siguiente en `Configure` en *Startup. CS*:</span><span class="sxs-lookup"><span data-stu-id="7f87f-242">To add area support to the route table in ASP.NET Core MVC, you would add the following in `Configure` in *Startup.cs*:</span></span>

```csharp
app.UseEndpoints(endpoints =>
{
    endpoints.MapControllerRoute(
        name: "MyArea",
        pattern: "{area:exists}/{controller=Home}/{action=Index}/{id?}");

    endpoints.MapControllerRoute(
        name: "default",
        pattern: "{controller=Home}/{action=Index}/{id?}");
});
```

<span data-ttu-id="7f87f-243">Las áreas también se pueden usar con el enrutamiento de atributos, mediante la `{area}` palabra clave en la definición de ruta (es uno de los distintos [nombres de enrutamiento reservados](/aspnet/core/mvc/controllers/routing#reserved-routing-names) que se pueden usar con las plantillas de ruta).</span><span class="sxs-lookup"><span data-stu-id="7f87f-243">Areas can also be used with attribute routing, using the `{area}` keyword in the route definition (it's one of several [reserved routing names](/aspnet/core/mvc/controllers/routing#reserved-routing-names) that can be used with route templates).</span></span>

<span data-ttu-id="7f87f-244">Las aplicaciones auxiliares de etiquetas admiten áreas con el `asp-area` atributo, que se pueden usar para generar vínculos en las vistas y páginas de Razor:</span><span class="sxs-lookup"><span data-stu-id="7f87f-244">Tag helpers support areas with the `asp-area` attribute, which can be used to generate links in Razor views and pages:</span></span>

```razor
<ul>
    <li>
        <a asp-area="Products" asp-controller="Home" asp-action="About">
            Products/Home/About
        </a>
    </li>
    <li>
        <a asp-area="Services" asp-controller="Home" asp-action="About">
            Services About
        </a>
    </li>
    <li>
        <a asp-area="" asp-controller="Home" asp-action="About">
            /Home/About
        </a>
    </li>
</ul>
```

<span data-ttu-id="7f87f-245">Si va a migrar a Razor Pages tendrá que usar una carpeta de *áreas* en la carpeta de *páginas* .</span><span class="sxs-lookup"><span data-stu-id="7f87f-245">If you're migrating to Razor Pages you will need to use an *Areas* folder in your *Pages* folder.</span></span> <span data-ttu-id="7f87f-246">Para obtener más información, vea [áreas con Razor pages](/aspnet/core/mvc/controllers/areas#areas-with-razor-pages).</span><span class="sxs-lookup"><span data-stu-id="7f87f-246">For more information, see [Areas with Razor Pages](/aspnet/core/mvc/controllers/areas#areas-with-razor-pages).</span></span>

<span data-ttu-id="7f87f-247">Además de las instrucciones anteriores, los equipos deben revisar [Cómo funciona el enrutamiento en ASP.net Core con áreas](/aspnet/core/mvc/controllers/routing#areas) como parte de su proceso de planeamiento de la migración.</span><span class="sxs-lookup"><span data-stu-id="7f87f-247">In addition to the above guidance, teams should review [how routing in ASP.NET Core works with areas](/aspnet/core/mvc/controllers/routing#areas) as part of their migration planning process.</span></span>

## <a name="integration-tests-for-aspnet-mvc-and-aspnet-web-api"></a><span data-ttu-id="7f87f-248">Pruebas de integración para ASP.NET MVC y ASP.NET Web API</span><span class="sxs-lookup"><span data-stu-id="7f87f-248">Integration tests for ASP.NET MVC and ASP.NET Web API</span></span>

<span data-ttu-id="7f87f-249">Las pruebas de integración son pruebas automatizadas que comprueban que varias partes de una aplicación funcionan correctamente en conjunto.</span><span class="sxs-lookup"><span data-stu-id="7f87f-249">Integration tests are automated tests that verify several different parts of an app work together correctly.</span></span> <span data-ttu-id="7f87f-250">Escribir pruebas de integración para ASP.NET MVC y ASP.NET Web API normalmente implica implementar la aplicación en un servidor web real, como una instancia local de IIS o IIS Express y, a continuación, realizar solicitudes a esta aplicación hospedada mediante un cliente HTTP.</span><span class="sxs-lookup"><span data-stu-id="7f87f-250">Writing integration tests for ASP.NET MVC and ASP.NET Web API usually involved deploying the app to a real web server, such as a local instance of IIS or IIS Express, and then making requests to this hosted application using an HTTP client.</span></span> <span data-ttu-id="7f87f-251">Algunas de estas pruebas pueden interactuar con la interfaz de usuario del lado cliente mediante herramientas de automatización del explorador como [Selenium](https://www.selenium.dev/), aunque a menudo se hace referencia a ellas como *pruebas de IU* en lugar de a pruebas de integración.</span><span class="sxs-lookup"><span data-stu-id="7f87f-251">Some of these tests may interact with the client-side user interface using browser automation tools like [Selenium](https://www.selenium.dev/), though often these are referred to as *UI tests* rather than integration tests.</span></span>

<span data-ttu-id="7f87f-252">Si la aplicación migrada comparte el mismo comportamiento que la versión original, independientemente de la tecnología existente que use el equipo para realizar las pruebas de integración (y las pruebas de interfaz de usuario) debe seguir funcionando igual que antes.</span><span class="sxs-lookup"><span data-stu-id="7f87f-252">If your migrated app shares the same behavior as its original version, whatever existing technology the team is using to perform integration tests (and UI tests) should continue to work just as it did before.</span></span> <span data-ttu-id="7f87f-253">Estas pruebas suelen ser indistintas de la tecnología subyacente que se usa para hospedar la aplicación que están probando e interactuar con ella solo a través de solicitudes HTTP.</span><span class="sxs-lookup"><span data-stu-id="7f87f-253">These tests are usually indifferent to the underlying technology used to host the app they're testing, and interact with it only through HTTP requests.</span></span> <span data-ttu-id="7f87f-254">La situación en la que los elementos pueden ser más desafiantes es cómo interactúan las pruebas con la aplicación para ponerla en un estado correcto conocido antes de cada prueba.</span><span class="sxs-lookup"><span data-stu-id="7f87f-254">Where things may get more challenging is with how the tests interact with the app to get it into a known good state prior to each test.</span></span> <span data-ttu-id="7f87f-255">Esto puede requerir algún esfuerzo de migración, ya que la configuración y el inicio son significativamente diferentes en ASP.NET Core en comparación con ASP.NET MVC o ASP.NET Web API.</span><span class="sxs-lookup"><span data-stu-id="7f87f-255">This may require some migration effort, since configuration and startup are significantly different in ASP.NET Core compared to ASP.NET MVC or ASP.NET Web API.</span></span>

<span data-ttu-id="7f87f-256">Los equipos deben considerar fuertemente la migración de sus pruebas de integración para usar la compatibilidad con las [pruebas de integración integradas de ASP.net Core](/aspnet/core/test/integration-tests) .</span><span class="sxs-lookup"><span data-stu-id="7f87f-256">Teams should strongly consider migrating their integration tests to use [ASP.NET Core's built-in integration testing](/aspnet/core/test/integration-tests) support.</span></span> <span data-ttu-id="7f87f-257">En ASP.NET Core, las aplicaciones se pueden probar mediante su implementación en un `TestHost` , que se configura mediante `WebApplicationFactory` .</span><span class="sxs-lookup"><span data-stu-id="7f87f-257">In ASP.NET Core, apps can be tested by deploying them to a `TestHost`, which is configured using a `WebApplicationFactory`.</span></span> <span data-ttu-id="7f87f-258">Hay un poco de configuración necesaria para hospedar la aplicación para las pruebas, pero una vez que se implementa, la creación de pruebas de integración individuales es muy sencilla.</span><span class="sxs-lookup"><span data-stu-id="7f87f-258">There's a little bit of setup required to host the app for testing, but once this is in place, creating individual integration tests is very straightforward.</span></span>

<span data-ttu-id="7f87f-259">Una de las mejores características de la compatibilidad con las pruebas de integración de ASP.NET Core es que la aplicación se hospeda en la memoria.</span><span class="sxs-lookup"><span data-stu-id="7f87f-259">One of the best features of ASP.NET Core's integration testing support is that the app is hosted in memory.</span></span> <span data-ttu-id="7f87f-260">No es necesario configurar un servidor de Live real para hospedar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7f87f-260">There's no need to configure a real webserver to host the app.</span></span> <span data-ttu-id="7f87f-261">No es necesario usar una herramienta de automatización del explorador (si solo está probando ASP.NET Core y no el comportamiento del lado cliente).</span><span class="sxs-lookup"><span data-stu-id="7f87f-261">There's no need to use a browser automation tool (if you're only testing ASP.NET Core and not client-side behavior).</span></span> <span data-ttu-id="7f87f-262">Muchos de los problemas que se pueden encontrar al intentar usar un servidor web real para las pruebas de integración automatizadas, como problemas de firewall o problemas de inicio y detención de procesos, se eliminan con este enfoque.</span><span class="sxs-lookup"><span data-stu-id="7f87f-262">Many of the problems that can be encountered when trying to use a real web server for automated integration tests, such as firewall issues or process start/stop issues, are eliminated with this approach.</span></span> <span data-ttu-id="7f87f-263">Puesto que las solicitudes se realizan en memoria sin ningún requisito de red, las pruebas también tienden a ejecutarse mucho más rápido que las pruebas que deben configurar un servidor WebServer independiente y comunicarse con ella a través de la red (incluso si se ejecuta en el mismo equipo).</span><span class="sxs-lookup"><span data-stu-id="7f87f-263">Since the requests are all made in memory with no network requirement, the tests also tend to run much faster than tests that must set up a separate webserver and communicate with it over the network (even if it's running on the same machine).</span></span>

<span data-ttu-id="7f87f-264">A continuación puede ver un ejemplo ASP.NET Core prueba de integración (a veces denominada *pruebas funcionales* para distinguirlas de las pruebas de integración de nivel inferior) de la [aplicación de referencia eShopOnWeb](https://github.com/dotnet-architecture/eShopOnWeb):</span><span class="sxs-lookup"><span data-stu-id="7f87f-264">Below you can see an example ASP.NET Core integration test (sometimes referred to as *functional tests* to distinguish them from lower-level integration tests) from the [eShopOnWeb reference application](https://github.com/dotnet-architecture/eShopOnWeb):</span></span>

```csharp
public class GetByIdEndpoint : IClassFixture<ApiTestFixture>
{
    JsonSerializerOptions _jsonOptions = new JsonSerializerOptions { PropertyNameCaseInsensitive = true };

    public GetByIdEndpoint(ApiTestFixture factory)
    {
        Client = factory.CreateClient();
    }

    public HttpClient Client { get; }

    [Fact]
    public async Task ReturnsItemGivenValidId()
    {
        var response = await Client.GetAsync("api/catalog-items/5");
        response.EnsureSuccessStatusCode();
        var stringResponse = await response.Content.ReadAsStringAsync();
        var model = stringResponse.FromJson<GetByIdCatalogItemResponse>();

        Assert.Equal(5, model.CatalogItem.Id);
        Assert.Equal("Roslyn Red Sheet", model.CatalogItem.Name);
    }
}
```

<span data-ttu-id="7f87f-265">Si la aplicación que se migra no tiene ninguna prueba de integración, el proceso de migración puede ser una gran oportunidad para agregar algunos.</span><span class="sxs-lookup"><span data-stu-id="7f87f-265">If the app being migrated has no integration tests, the migration process can be a great opportunity to add some.</span></span> <span data-ttu-id="7f87f-266">Estas pruebas pueden comprobar que la aplicación migrada se comporta como espera el equipo.</span><span class="sxs-lookup"><span data-stu-id="7f87f-266">These tests can verify that the migrated app behaves as the team expects.</span></span> <span data-ttu-id="7f87f-267">Cuando estas pruebas se aplican al principio de una migración, pueden garantizar que los esfuerzos de migración posteriores no interrumpan partes migradas previamente de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7f87f-267">When such tests are in place early in a migration, they can ensure that later migration efforts do not break previously migrated portions of the app.</span></span> <span data-ttu-id="7f87f-268">Dada la facilidad con la que se configuran y ejecutan las pruebas de integración en ASP.NET Core, el retorno de la inversión dedicada a la configuración de dichas pruebas suele ser bastante alto.</span><span class="sxs-lookup"><span data-stu-id="7f87f-268">Given how easy it is to set up and run integration tests in ASP.NET Core, the return on the investment spent setting up such tests is usually pretty high.</span></span>

## <a name="wcf-client-configuration"></a><span data-ttu-id="7f87f-269">Configuración del cliente de WCF</span><span class="sxs-lookup"><span data-stu-id="7f87f-269">WCF client configuration</span></span>

<span data-ttu-id="7f87f-270">Si su aplicación actualmente se basa en los servicios WCF como un cliente, se admite este escenario.</span><span class="sxs-lookup"><span data-stu-id="7f87f-270">If your app currently relies on WCF services as a client, this scenario is supported.</span></span> <span data-ttu-id="7f87f-271">Sin embargo, tendrá que [migrar la configuración](/aspnet/core/migration/configuration) de *web.config* para usar el nuevo *appsettings.jsen* el archivo.</span><span class="sxs-lookup"><span data-stu-id="7f87f-271">However, you will need to [migrate your configuration](/aspnet/core/migration/configuration) from *web.config* to use the new *appsettings.json* file.</span></span> <span data-ttu-id="7f87f-272">Otra opción es agregar cualquier configuración necesaria a los clientes mediante programación cuando se crean.</span><span class="sxs-lookup"><span data-stu-id="7f87f-272">Another option is to add any necessary configuration to your clients programmatically when you create them.</span></span> <span data-ttu-id="7f87f-273">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7f87f-273">For example:</span></span>

```csharp
var wcfClient = new OrderServiceClient(
    new BasicHttpBinding(BasicHttpSecurityMode.None),
    new EndpointAddress("http://localhost:5050/OrderService.svc"));
```

<span data-ttu-id="7f87f-274">Si su organización tiene extensos servicios compilados con WCF en el que se basa la aplicación, considere la posibilidad de migrarlos para usar gRPC en su lugar.</span><span class="sxs-lookup"><span data-stu-id="7f87f-274">If your organization has extensive services built using WCF that your app relies on, consider migrating them to use gRPC instead.</span></span> <span data-ttu-id="7f87f-275">Para obtener más detalles sobre gRPC, por qué es posible que desee migrar y una guía de migración detallada, consulte el libro electrónico [de gRPC para desarrolladores de WCF](/dotnet/architecture/grpc-for-wcf-developers/) .</span><span class="sxs-lookup"><span data-stu-id="7f87f-275">For more details on gRPC, why you may wish to migrate, and a detailed migration guide, consult the [gRPC for WCF Developers](/dotnet/architecture/grpc-for-wcf-developers/) eBook.</span></span>

## <a name="references"></a><span data-ttu-id="7f87f-276">Referencias</span><span class="sxs-lookup"><span data-stu-id="7f87f-276">References</span></span>

- [<span data-ttu-id="7f87f-277">ASP.NET Web API la negociación de contenido</span><span class="sxs-lookup"><span data-stu-id="7f87f-277">ASP.NET Web API Content Negotiation</span></span>](/aspnet/web-api/overview/formats-and-model-binding/content-negotiation)
- [<span data-ttu-id="7f87f-278">Aplicación de formato a datos de respuesta en ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="7f87f-278">Format response data in ASP.NET Core Web API</span></span>](/aspnet/core/web-api/advanced/formatting)
- [<span data-ttu-id="7f87f-279">Enlazadores de modelos personalizados en ASP.NET Web API</span><span class="sxs-lookup"><span data-stu-id="7f87f-279">Custom Model Binders in ASP.NET Web API</span></span>](/aspnet/web-api/overview/formats-and-model-binding/parameter-binding-in-aspnet-web-api#model-binders)
- [<span data-ttu-id="7f87f-280">Enlazadores de modelos personalizados en ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7f87f-280">Custom Model Binders in ASP.NET Core</span></span>](/aspnet/core/mvc/advanced/custom-model-binding#custom-model-binder-sample)
- <span data-ttu-id="7f87f-281">[Formateadores de medios en ASP.NET Web API 2](/aspnet/web-api/overview/formats-and-model-binding/media-formatters)</span><span class="sxs-lookup"><span data-stu-id="7f87f-281">[Media Formatters in ASP.NET Web API 2](/aspnet/web-api/overview/formats-and-model-binding/media-formatters)</span></span>\
- [<span data-ttu-id="7f87f-282">Formateadores personalizados en ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="7f87f-282">Custom formatters in ASP.NET Core Web API</span></span>](/aspnet/core/web-api/advanced/custom-formatters)
- [<span data-ttu-id="7f87f-283">Filtros en ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7f87f-283">Filters in ASP.NET Core</span></span>](/aspnet/core/mvc/controllers/filters)
- [<span data-ttu-id="7f87f-284">Restricciones de ruta en ASP.NET Web API 2</span><span class="sxs-lookup"><span data-stu-id="7f87f-284">Route constraints in ASP.NET Web API 2</span></span>](/aspnet/web-api/overview/web-api-routing-and-actions/attribute-routing-in-web-api-2#route-constraints)
- [<span data-ttu-id="7f87f-285">Restricciones de ruta en ASP.NET MVC 5</span><span class="sxs-lookup"><span data-stu-id="7f87f-285">Route constraints in ASP.NET MVC 5</span></span>](https://devblogs.microsoft.com/aspnet/attribute-routing-in-asp-net-mvc-5/#route-constraints)
- [<span data-ttu-id="7f87f-286">ASP.NET Core referencia de restricción de ruta</span><span class="sxs-lookup"><span data-stu-id="7f87f-286">ASP.NET Core Route Constraint Reference</span></span>](/aspnet/core/fundamentals/routing#route-constraint-reference)
- [<span data-ttu-id="7f87f-287">Controladores de mensajes personalizados en ASP.NET Web API 2</span><span class="sxs-lookup"><span data-stu-id="7f87f-287">Custom message handlers in ASP.NET Web API 2</span></span>](/aspnet/web-api/overview/advanced/http-message-handlers#custom-message-handlers)
- [<span data-ttu-id="7f87f-288">Control de CORS simple en MVC 5 y Web API 2</span><span class="sxs-lookup"><span data-stu-id="7f87f-288">Simple CORS control in MVC 5 and Web API 2</span></span>](https://stackoverflow.com/questions/6290053/setting-access-control-allow-origin-in-asp-net-mvc-simplest-possible-method)
- [<span data-ttu-id="7f87f-289">Habilitación de solicitudes entre orígenes en Web API</span><span class="sxs-lookup"><span data-stu-id="7f87f-289">Enabling Cross-Origin Requests in Web API</span></span>](/aspnet/web-api/overview/security/enabling-cross-origin-requests-in-web-api#enable-cors)
- [<span data-ttu-id="7f87f-290">Habilitación de solicitudes entre orígenes (CORS) en ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7f87f-290">Enable Cross-Origin Requests (CORS) in ASP.NET Core</span></span>](/aspnet/core/security/cors)
- [<span data-ttu-id="7f87f-291">Áreas de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7f87f-291">Areas in ASP.NET Core</span></span>](/aspnet/core/mvc/controllers/areas)
- [<span data-ttu-id="7f87f-292">Pruebas de integración en ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7f87f-292">Integration tests in ASP.NET Core</span></span>](/aspnet/core/test/integration-tests)

>[!div class="step-by-step"]
><span data-ttu-id="7f87f-293">[Anterior](example-migration-eshop.md)
>[Siguiente](deployment-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="7f87f-293">[Previous](example-migration-eshop.md)
[Next](deployment-scenarios.md)</span></span>
