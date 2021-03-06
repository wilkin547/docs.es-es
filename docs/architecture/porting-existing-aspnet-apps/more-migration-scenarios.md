---
title: Más escenarios de migración
description: En esta sección se describen escenarios y técnicas de migración adicionales para actualizar .NET Framework aplicaciones a .NET Core/.NET 5.
author: ardalis
ms.date: 02/11/2021
ms.openlocfilehash: fa1b756d8852854e50127ae3e7443e2949cceaa8
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401725"
---
# <a name="more-migration-scenarios"></a><span data-ttu-id="1ae86-103">Más escenarios de migración</span><span class="sxs-lookup"><span data-stu-id="1ae86-103">More migration scenarios</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="1ae86-104">En esta sección se describen varios escenarios de aplicaciones de ASP.NET diferentes y se ofrecen técnicas específicas para resolver cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="1ae86-104">This section describes several different ASP.NET app scenarios, and offers specific techniques for solving each of them.</span></span> <span data-ttu-id="1ae86-105">Puede usar esta sección para identificar los escenarios aplicables a la aplicación y evaluar qué técnicas funcionarán para su aplicación y su entorno de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="1ae86-105">You can use this section to identify scenarios applicable to your app, and evaluate which techniques will work for your app and its hosting environment.</span></span>

## <a name="migrate-aspnet-mvc-5-and-webapi-2-to-aspnet-core-mvc"></a><span data-ttu-id="1ae86-106">Migración de ASP.NET MVC 5 y WebApi 2 a ASP.NET Core MVC</span><span class="sxs-lookup"><span data-stu-id="1ae86-106">Migrate ASP.NET MVC 5 and WebApi 2 to ASP.NET Core MVC</span></span>

<span data-ttu-id="1ae86-107">Un escenario común en las aplicaciones ASP.NET MVC 5 y Web API 2 era que ambos productos se instalaran en la misma aplicación.</span><span class="sxs-lookup"><span data-stu-id="1ae86-107">A common scenario in ASP.NET MVC 5 and Web API 2 apps was for both products to be installed in the same application.</span></span> <span data-ttu-id="1ae86-108">Se trata de un enfoque compatible y relativamente común que usan muchos equipos, pero debido a que los dos productos utilizan abstracciones diferentes, se requiere un esfuerzo redundante.</span><span class="sxs-lookup"><span data-stu-id="1ae86-108">This is a supported and relatively common approach used by many teams, but because the two products use different abstractions, there is some redundant effort needed.</span></span> <span data-ttu-id="1ae86-109">Por ejemplo, la configuración de rutas para ASP.NET MVC se realiza mediante métodos en `RouteCollection` , como `MapMvcAttributeRoutes()` y `MapRoute()` .</span><span class="sxs-lookup"><span data-stu-id="1ae86-109">For example, setting up routes for ASP.NET MVC is done using methods on `RouteCollection`, such as `MapMvcAttributeRoutes()` and `MapRoute()`.</span></span> <span data-ttu-id="1ae86-110">Pero el enrutamiento de ASP.NET Web API 2 se administra con `HttpConfiguration` métodos y como `MapHttpAttributeRoutes()` y `MapHttpRoute()` .</span><span class="sxs-lookup"><span data-stu-id="1ae86-110">But ASP.NET Web API 2 routing is managed with `HttpConfiguration` and methods like `MapHttpAttributeRoutes()` and `MapHttpRoute()`.</span></span>

<span data-ttu-id="1ae86-111">La `eShopLegacyMVC` aplicación incluye ASP.NET MVC y Web API e incluye métodos en su `App_Start` carpeta para configurar las rutas de ambos.</span><span class="sxs-lookup"><span data-stu-id="1ae86-111">The `eShopLegacyMVC` app includes both ASP.NET MVC and Web API, and includes methods in its `App_Start` folder for setting up routes for both.</span></span> <span data-ttu-id="1ae86-112">También admite la inserción de dependencias mediante Autofac, que también requiere dos conjuntos de trabajo similar para configurar:</span><span class="sxs-lookup"><span data-stu-id="1ae86-112">It also supports dependency injection using Autofac, which also requires two sets of similar work to configure:</span></span>

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

<span data-ttu-id="1ae86-113">Al actualizar estas aplicaciones para usar ASP.NET Core, se elimina este trabajo duplicado y la confusión que a veces lo acompaña.</span><span class="sxs-lookup"><span data-stu-id="1ae86-113">When upgrading these apps to use ASP.NET Core, this duplicate effort and the confusion that sometimes accompanies it is eliminated.</span></span> <span data-ttu-id="1ae86-114">ASP.NET Core MVC es un marco unificado con un conjunto de reglas para el enrutamiento, los filtros, etc.</span><span class="sxs-lookup"><span data-stu-id="1ae86-114">ASP.NET Core MVC is a unified framework with one set of rules for routing, filters, and more.</span></span> <span data-ttu-id="1ae86-115">La inserción de dependencias está integrada en .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1ae86-115">Dependency injection is built into .NET Core itself.</span></span> <span data-ttu-id="1ae86-116">Todo esto puede configurarse en `Startup.cs` , tal y como se muestra en la `eShopPorted` aplicación en el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="1ae86-116">All of this can can be configured in `Startup.cs`, as is shown in the `eShopPorted` app in the sample.</span></span>

## <a name="migrate-httpresponsemessage-to-aspnet-core"></a><span data-ttu-id="1ae86-117">Migración de HttpResponseMessage a ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1ae86-117">Migrate HttpResponseMessage to ASP.NET Core</span></span>

<span data-ttu-id="1ae86-118">Algunas aplicaciones ASP.NET Web API pueden tener métodos de acción que devuelven `HttpResponseMessage` .</span><span class="sxs-lookup"><span data-stu-id="1ae86-118">Some ASP.NET Web API apps may have action methods that return `HttpResponseMessage`.</span></span> <span data-ttu-id="1ae86-119">Este tipo no existe en ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="1ae86-119">This type does not exist in ASP.NET Core.</span></span> <span data-ttu-id="1ae86-120">A continuación se muestra un ejemplo de su uso en un `Delete` método de acción, mediante el `ResponseMessage` método auxiliar en la base `ApiController` :</span><span class="sxs-lookup"><span data-stu-id="1ae86-120">Below is an example of its usage in a `Delete` action method, using the `ResponseMessage` helper method on the base `ApiController`:</span></span>

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

<span data-ttu-id="1ae86-121">En ASP.NET Core MVC, hay métodos auxiliares disponibles para todos los códigos de estado de respuesta HTTP comunes, por lo que el método anterior se trasladaría al siguiente código:</span><span class="sxs-lookup"><span data-stu-id="1ae86-121">In ASP.NET Core MVC, there are helper methods available for all of the common HTTP response status codes, so the above method would be ported to the following code:</span></span>

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

<span data-ttu-id="1ae86-122">Si encuentra que necesita devolver un código de estado personalizado para el que no existe ninguna aplicación auxiliar, siempre puede usar `return StatusCode(int statusCode)` para devolver el código numérico que desee.</span><span class="sxs-lookup"><span data-stu-id="1ae86-122">If you do find that you need to return a custom status code for which no helper exists, you can always use `return StatusCode(int statusCode)` to return any numeric code you like.</span></span>

## <a name="migrate-content-negotiation-from-aspnet-web-api-to-aspnet-core"></a><span data-ttu-id="1ae86-123">Migrar la negociación de contenido de ASP.NET Web API a ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1ae86-123">Migrate content negotiation from ASP.NET Web API to ASP.NET Core</span></span>

<span data-ttu-id="1ae86-124">ASP.NET Web API 2 admite la [negociación de contenido](/aspnet/web-api/overview/formats-and-model-binding/content-negotiation) de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="1ae86-124">ASP.NET Web API 2 supports [content negotiation](/aspnet/web-api/overview/formats-and-model-binding/content-negotiation) natively.</span></span> <span data-ttu-id="1ae86-125">La aplicación de ejemplo incluye un `BrandsController` que muestra esta compatibilidad al enumerar los resultados en XML o JSON.</span><span class="sxs-lookup"><span data-stu-id="1ae86-125">The sample app includes a `BrandsController` that demonstrates this support by listing its results in either XML or JSON.</span></span> <span data-ttu-id="1ae86-126">Esto se basa en el encabezado de la solicitud `Accept` y cambia cuando incluye `application/xml` o `application/json` .</span><span class="sxs-lookup"><span data-stu-id="1ae86-126">This is based on the request's `Accept` header, and changes when it includes `application/xml` or `application/json`.</span></span>

<span data-ttu-id="1ae86-127">Las aplicaciones ASP.NET MVC 5 no admiten la negociación de contenido integrada.</span><span class="sxs-lookup"><span data-stu-id="1ae86-127">ASP.NET MVC 5 apps do not have content negotiation support built in.</span></span>

<span data-ttu-id="1ae86-128">La negociación de contenido es preferible a devolver un tipo de codificación específico, ya que es más flexible y hace que la API esté disponible para un mayor número de clientes.</span><span class="sxs-lookup"><span data-stu-id="1ae86-128">Content negotiation is preferable to returning a specific encoding type, as it is more flexible and makes the API available to a larger number of clients.</span></span> <span data-ttu-id="1ae86-129">Si actualmente tiene métodos de acción que devuelven un formato específico, considere la posibilidad de modificarlos para que devuelvan un tipo de resultado que admita la negociación de contenido al trasladar el código a ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="1ae86-129">If you currently have action methods that return a specific format, you should consider modifying them to return a result type that supports content negotiation when you port the code to ASP.NET Core.</span></span>

<span data-ttu-id="1ae86-130">El código siguiente devuelve datos en formato JSON independientemente del contenido del encabezado de cliente `Accept` :</span><span class="sxs-lookup"><span data-stu-id="1ae86-130">The following code returns data in JSON format regardless of client `Accept` header content:</span></span>

```csharp
[HttpGet]
public ActionResult Index()
{
    return Json(new { Message = "Hello World!" });
}
```

<span data-ttu-id="1ae86-131">[ASP.net Core MVC admite la negociación de contenido](/aspnet/core/web-api/advanced/formatting)de forma nativa, siempre que se use un [tipo de valor devuelto](/aspnet/core/web-api/action-return-types) adecuado.</span><span class="sxs-lookup"><span data-stu-id="1ae86-131">[ASP.NET Core MVC supports content negotiation natively](/aspnet/core/web-api/advanced/formatting), provided an appropriate [return type](/aspnet/core/web-api/action-return-types) is used.</span></span> <span data-ttu-id="1ae86-132">La negociación de contenido se implementa mediante [ObjectResult] devuelta por los resultados de la acción específica del código de estado devueltos por los métodos auxiliares de controlador.</span><span class="sxs-lookup"><span data-stu-id="1ae86-132">Content negotiation is implemented by [ObjectResult] which is returned by the status code-specific action results returned by the controller helper methods.</span></span> <span data-ttu-id="1ae86-133">El método de acción anterior, implementado en ASP.NET Core MVC y usando la negociación de contenido, sería:</span><span class="sxs-lookup"><span data-stu-id="1ae86-133">The previous action method, implemented in ASP.NET Core MVC and using content negotiation, would be:</span></span>

```csharp
public IActionResult Index()
{
    return Ok(new { Message = "Hello World!"} );
}
```

<span data-ttu-id="1ae86-134">De forma predeterminada, se devolverán los datos en formato JSON.</span><span class="sxs-lookup"><span data-stu-id="1ae86-134">This will default to returning the data in JSON format.</span></span> <span data-ttu-id="1ae86-135">XML y otros formatos se utilizarán [si la aplicación se ha configurado con el formateador adecuado](/aspnet/core/web-api/advanced/formatting).</span><span class="sxs-lookup"><span data-stu-id="1ae86-135">XML and other formats will be used [if the app has been configured with the appropriate formatter](/aspnet/core/web-api/advanced/formatting).</span></span>

## <a name="references"></a><span data-ttu-id="1ae86-136">Referencias</span><span class="sxs-lookup"><span data-stu-id="1ae86-136">References</span></span>

- [<span data-ttu-id="1ae86-137">ASP.NET Web API la negociación de contenido</span><span class="sxs-lookup"><span data-stu-id="1ae86-137">ASP.NET Web API Content Negotiation</span></span>](/aspnet/web-api/overview/formats-and-model-binding/content-negotiation)
- [<span data-ttu-id="1ae86-138">Aplicación de formato a datos de respuesta en ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="1ae86-138">Format response data in ASP.NET Core Web API</span></span>](/aspnet/core/web-api/advanced/formatting)

>[!div class="step-by-step"]
><span data-ttu-id="1ae86-139">[Anterior](example-migration-eshop.md)
>[Siguiente](deployment-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="1ae86-139">[Previous](example-migration-eshop.md)
[Next](deployment-scenarios.md)</span></span>
