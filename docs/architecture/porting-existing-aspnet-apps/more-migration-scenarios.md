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
# <a name="more-migration-scenarios"></a>Más escenarios de migración

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

En esta sección se describen varios escenarios de aplicaciones de ASP.NET diferentes y se ofrecen técnicas específicas para resolver cada uno de ellos. Puede usar esta sección para identificar los escenarios aplicables a la aplicación y evaluar qué técnicas funcionarán para su aplicación y su entorno de hospedaje.

## <a name="migrate-aspnet-mvc-5-and-webapi-2-to-aspnet-core-mvc"></a>Migración de ASP.NET MVC 5 y WebApi 2 a ASP.NET Core MVC

Un escenario común en las aplicaciones ASP.NET MVC 5 y Web API 2 era que ambos productos se instalaran en la misma aplicación. Se trata de un enfoque compatible y relativamente común que usan muchos equipos, pero debido a que los dos productos utilizan abstracciones diferentes, se requiere un esfuerzo redundante. Por ejemplo, la configuración de rutas para ASP.NET MVC se realiza mediante métodos en `RouteCollection` , como `MapMvcAttributeRoutes()` y `MapRoute()` . Pero el enrutamiento de ASP.NET Web API 2 se administra con `HttpConfiguration` métodos y como `MapHttpAttributeRoutes()` y `MapHttpRoute()` .

La `eShopLegacyMVC` aplicación incluye ASP.NET MVC y Web API e incluye métodos en su `App_Start` carpeta para configurar las rutas de ambos. También admite la inserción de dependencias mediante Autofac, que también requiere dos conjuntos de trabajo similar para configurar:

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

Al actualizar estas aplicaciones para usar ASP.NET Core, se elimina este trabajo duplicado y la confusión que a veces lo acompaña. ASP.NET Core MVC es un marco unificado con un conjunto de reglas para el enrutamiento, los filtros, etc. La inserción de dependencias está integrada en .NET Core. Todo esto puede configurarse en `Startup.cs` , tal y como se muestra en la `eShopPorted` aplicación en el ejemplo.

## <a name="migrate-httpresponsemessage-to-aspnet-core"></a>Migración de HttpResponseMessage a ASP.NET Core

Algunas aplicaciones ASP.NET Web API pueden tener métodos de acción que devuelven `HttpResponseMessage` . Este tipo no existe en ASP.NET Core. A continuación se muestra un ejemplo de su uso en un `Delete` método de acción, mediante el `ResponseMessage` método auxiliar en la base `ApiController` :

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

En ASP.NET Core MVC, hay métodos auxiliares disponibles para todos los códigos de estado de respuesta HTTP comunes, por lo que el método anterior se trasladaría al siguiente código:

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

Si encuentra que necesita devolver un código de estado personalizado para el que no existe ninguna aplicación auxiliar, siempre puede usar `return StatusCode(int statusCode)` para devolver el código numérico que desee.

## <a name="migrate-content-negotiation-from-aspnet-web-api-to-aspnet-core"></a>Migrar la negociación de contenido de ASP.NET Web API a ASP.NET Core

ASP.NET Web API 2 admite la [negociación de contenido](/aspnet/web-api/overview/formats-and-model-binding/content-negotiation) de forma nativa. La aplicación de ejemplo incluye un `BrandsController` que muestra esta compatibilidad al enumerar los resultados en XML o JSON. Esto se basa en el encabezado de la solicitud `Accept` y cambia cuando incluye `application/xml` o `application/json` .

Las aplicaciones ASP.NET MVC 5 no admiten la negociación de contenido integrada.

La negociación de contenido es preferible a devolver un tipo de codificación específico, ya que es más flexible y hace que la API esté disponible para un mayor número de clientes. Si actualmente tiene métodos de acción que devuelven un formato específico, considere la posibilidad de modificarlos para que devuelvan un tipo de resultado que admita la negociación de contenido al trasladar el código a ASP.NET Core.

El código siguiente devuelve datos en formato JSON independientemente del contenido del encabezado de cliente `Accept` :

```csharp
[HttpGet]
public ActionResult Index()
{
    return Json(new { Message = "Hello World!" });
}
```

[ASP.net Core MVC admite la negociación de contenido](/aspnet/core/web-api/advanced/formatting)de forma nativa, siempre que se use un [tipo de valor devuelto](/aspnet/core/web-api/action-return-types) adecuado. La negociación de contenido se implementa mediante [ObjectResult] devuelta por los resultados de la acción específica del código de estado devueltos por los métodos auxiliares de controlador. El método de acción anterior, implementado en ASP.NET Core MVC y usando la negociación de contenido, sería:

```csharp
public IActionResult Index()
{
    return Ok(new { Message = "Hello World!"} );
}
```

De forma predeterminada, se devolverán los datos en formato JSON. XML y otros formatos se utilizarán [si la aplicación se ha configurado con el formateador adecuado](/aspnet/core/web-api/advanced/formatting).

## <a name="references"></a>Referencias

- [ASP.NET Web API la negociación de contenido](/aspnet/web-api/overview/formats-and-model-binding/content-negotiation)
- [Aplicación de formato a datos de respuesta en ASP.NET Core Web API](/aspnet/core/web-api/advanced/formatting)

>[!div class="step-by-step"]
>[Anterior](example-migration-eshop.md)
>[Siguiente](deployment-scenarios.md)
