---
title: Diferencias de enrutamiento entre ASP.NET MVC y ASP.NET Core
description: ¿Cómo se define el enrutamiento y cómo funciona en tiempo de ejecución en ASP.NET MVC? ¿Cómo difiere el enrutamiento en ASP.NET Core aplicaciones?
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: d5c18948248f03a19c97461efe3df38a5be9360b
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401716"
---
# <a name="routing-differences-between-aspnet-mvc-and-aspnet-core"></a>Diferencias de enrutamiento entre ASP.NET MVC y ASP.NET Core

El enrutamiento es responsable de asignar las solicitudes entrantes del explorador a determinadas acciones de controlador (o controladores de Razor Pages). En esta sección se explica cómo el enrutamiento difiere entre ASP.NET MVC (y Web API) y ASP.NET Core (MVC, Razor Pages, etc.).

## <a name="routing-in-aspnet-mvc-and-web-api"></a>Enrutamiento en ASP.NET MVC y Web API

ASP.NET MVC ofrece dos enfoques para el enrutamiento:

1. La tabla de rutas, que es una colección de rutas que se pueden usar para hacer coincidir las solicitudes entrantes con las acciones de controlador.
1. El enrutamiento mediante atributos, que realiza la misma función, pero se logra decorando las acciones por sí mismos, en lugar de editar una tabla de rutas global.

## <a name="route-table"></a>Tabla de rutas

La tabla de rutas se configura cuando se inicia la aplicación. Normalmente, una llamada al método estático se usa para configurar la colección de rutas global, como la siguiente:

```csharp
public class MvcApplication : System.Web.HttpApplication
{
    public static void RegisterRoutes(RouteCollection routes)
    {
        routes.IgnoreRoute("{resource}.axd/{*pathInfo}");
        routes.MapRoute(
            name: "Default",
            url: "{controller}/{action}/{id}",
            defaults: new { controller = "Home", action = "Index", id = "" },
            constraints: new { id = "\\d+" }
        );
    }

    protected void Application_Start()
    {
        RegisterRoutes(RouteTable.Routes);
    }
}
```

En el código anterior, la tabla de rutas se administra mediante el `RouteCollection` tipo, que se usa para agregar rutas nuevas con `MapRoute` . Las rutas se denominan e incluyen una cadena de ruta, que puede incluir parámetros para controladores, acciones, áreas y otros marcadores de posición. Si una aplicación sigue una convención estándar, la mayoría de sus acciones se pueden controlar mediante esta única ruta predeterminada, con cualquier excepción a esta Convención configurada mediante rutas adicionales.

### <a name="attribute-routing-in-aspnet-mvc"></a>Enrutamiento de atributos en MVC de ASP.NET

Es posible que las rutas definidas con sus acciones sean más fáciles de detectar y que no sean las rutas definidas en una ubicación externa. Mediante el enrutamiento de atributos, un método de acción individual puede tener su ruta definida con un `[Route]` atributo:

```csharp
public class ProductsController
{
    [Route("products")]
    public ActionResult Index()
    {
        return View();
    }

    [Route("products/{id}")]
    public ActionResult Details(int id)
    {
        return View();
    }
}
```

El [enrutamiento de atributos en ASP.NET MVC 5](https://devblogs.microsoft.com/aspnet/attribute-routing-in-asp-net-mvc-5/) también admite valores predeterminados y prefijos, que se pueden agregar en el nivel de controlador (y que se aplican a todas las acciones de ese controlador). Consulte la documentación para obtener más información.

La configuración del enrutamiento de atributos requiere agregar una línea a la configuración de la tabla de rutas predeterminada:

```csharp
routes.MapMvcAttributeRoutes();
```

El enrutamiento mediante atributos puede aprovechar las restricciones de ruta, tanto integradas como personalizadas, y admite rutas y áreas con nombre mediante el `[RouteArea]` atributo. Si su aplicación usa áreas, deberá configurar la compatibilidad con ellas en el código de registro de la ruta agregando una línea más:

```csharp
routes.MapMvcAttributeRoutes();

AreaRegistration.RegisterAllAreas();
```

### <a name="attribute-routing-in-aspnet-web-api-2"></a>Enrutamiento de atributos en ASP.NET Web API 2

El [enrutamiento de atributos en ASP.net web API 2](/aspnet/web-api/overview/web-api-routing-and-actions/attribute-routing-in-web-api-2) es similar al enrutamiento en ASP.NET MVC 5, con pequeñas diferencias. La configuración de Web API 2 se realiza normalmente en su propia clase, a la que se llama durante el inicio de la aplicación. La configuración de enrutamiento de atributos se controla en esta clase:

```csharp
public static class WebApiConfig
{
    public static void Register(HttpConfiguration config)
    {
        // Attribute routing.
        config.MapHttpAttributeRoutes();

        // Convention-based routing.
        config.Routes.MapHttpRoute(
            name: "DefaultApi",
            routeTemplate: "api/{controller}/{id}",
            defaults: new { id = RouteParameter.Optional }
        );
    }
}
```

Como se muestra en el código anterior, el enrutamiento de atributos se puede combinar con el enrutamiento basado en convenciones en aplicaciones de API Web.

Además del enrutamiento de atributos, [ASP.net web API elige la acción que se va a llamar](/aspnet/web-api/overview/web-api-routing-and-actions/routing-and-action-selection) basándose en el método HTTP (por ejemplo, get o post), el `{action}` marcador de posición en una ruta (si existe) y los parámetros de la acción. En muchos casos, el nombre de la acción ayudará a determinar si coinciden, ya que el uso del nombre de la acción como "Get" o "post" se usa para hacer coincidir con el método HTTP adecuado. Como alternativa, las acciones se pueden decorar con un atributo de método HTTP adecuado, como `[HttpGet]` , lo que permite el uso de nombres de acción que no tienen el prefijo de un método http.

```csharp
public class ProductsController : ApiController
{
    // matched by name and (lack of) parameters
    public IEnumerable<Product> GetAll() { }

    // matched by GET and string parameter
    [HttpGet]
    public IEnumerable<Product> FindProductsByName(string name) { }
}
```

Dado el controlador anterior, una solicitud HTTP GET para `localhost:123/products/` coincide con la `GetAll` acción. Una solicitud HTTP GET para `localhost:123/products?name=ardalis` coincide con la `FindProductsByName` acción.

## <a name="routing-in-aspnet-core-31"></a>Enrutamiento en ASP.NET Core 3,1

En ASP.NET Core, el enrutamiento se controla mediante middleware de enrutamiento, que coincide con las direcciones URL de las solicitudes entrantes a acciones u otros puntos de conexión. Las acciones del controlador se enrutan de forma convencional o se enrutan mediante atributos. El enrutamiento convencional es similar al enfoque de tabla de rutas usado en ASP.NET MVC y Web API. Tanto si usa el atributo convencional como el de ambos, debe configurar la aplicación para que use el middleware de enrutamiento. Para usar el middleware, agregue el código siguiente al `Startup.Configure` método:

```csharp
app.UseRouting();
```

### <a name="conventional-routing"></a>Enrutamiento convencional

Con el enrutamiento convencional, configure una o varias convenciones que se usarán para hacer coincidir las direcciones URL de entrada con los *extremos* de la aplicación. En ASP.NET Core, estos puntos de conexión pueden ser acciones de controlador, como en ASP.NET MVC o Web API. Los puntos de conexión también se pueden Razor Pages, comprobaciones de estado o concentradores de Signalr. Todas estas características enrutables se configuran de manera similar mediante puntos de conexión:

```csharp
// in Startup.Configure()
app.UseEndpoints(endpoints =>
{
    endpoints.MapHealthChecks("/healthz").RequireAuthorization();
    endpoints.MapControllerRoute(
        name: "default",
        pattern: "{controller=Home}/{action=Index}/{id?}");
    endpoints.MapRazorPages();
});
```

El código anterior se usa (además de `UseRouting` ) para configurar varios puntos de conexión, incluidas las comprobaciones de estado, los controladores y el Razor pages. En el caso de los controladores, la configuración anterior especifica una Convención de enrutamiento predeterminada, que es el patrón bastante estándar `{controller}/{action}/{id?}` que se recomienda desde las primeras versiones de ASP.NET MVC.

### <a name="attribute-routing"></a>Enrutamiento mediante atributos

El enrutamiento de atributos en ASP.NET Core es el método preferido para configurar el enrutamiento en los controladores. Si va a compilar las API, el `[ApiController]` atributo se debe aplicar a los controladores. Entre otras cosas, este atributo requiere el uso del enrutamiento de atributo para las acciones en estas clases de controlador.

El enrutamiento de atributos en ASP.NET Core se comporta de forma similar en ASP.NET MVC y Web API. Además de admitir el `[Route]` atributo, sin embargo, la información de ruta también se puede especificar como parte del atributo de método http:

```csharp
[HttpGet("api/products/{id}")]
public async ActionResult<Product> Details(int id)
{
    // ...
}
```

Al igual que con las versiones anteriores, puede especificar una ruta predeterminada con marcadores de posición y Agregar esto en el nivel de clase del controlador o incluso en una clase base. Use el mismo `[Route]` atributo para todos estos casos. Por ejemplo, una clase de controlador de API base podría tener este aspecto:

```csharp
[Route("api/{controller}/{action}/{id?:int}")]
public abstract class BaseApiController : ControllerBase, IApiController
{
    // ...
}
```

Con este atributo, las clases que heredan de este tipo enrutarán las direcciones URL a las acciones según el nombre del controlador, el nombre de acción y un parámetro de entero opcional `id` .

## <a name="references"></a>Referencias

- [Información general sobre el enrutamiento ASP.NET MVC](/aspnet/mvc/overview/older-versions-1/controllers-and-routing/asp-net-mvc-routing-overview-cs)
- [Enrutamiento de atributos en ASP.NET MVC 5](https://devblogs.microsoft.com/aspnet/attribute-routing-in-asp-net-mvc-5/)
- [Enrutamiento de atributos en ASP.NET Web API 2](/aspnet/web-api/overview/web-api-routing-and-actions/attribute-routing-in-web-api-2)
- [Enrutamiento y selección de acciones en ASP.NET Web API](/aspnet/web-api/overview/web-api-routing-and-actions/routing-and-action-selection)
- [Enrutamiento en ASP.NET Core](/aspnet/core/fundamentals/routing)
- [Enrutamiento a las acciones del controlador en ASP.NET Core MVC](/aspnet/core/mvc/controllers/routing)

>[!div class="step-by-step"]
>[Anterior](configuration-differences.md)
>[Siguiente](comparing-razor-pages-aspnet-mvc.md)
