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
# <a name="routing-differences-between-aspnet-mvc-and-aspnet-core"></a><span data-ttu-id="241bd-104">Diferencias de enrutamiento entre ASP.NET MVC y ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="241bd-104">Routing differences between ASP.NET MVC and ASP.NET Core</span></span>

<span data-ttu-id="241bd-105">El enrutamiento es responsable de asignar las solicitudes entrantes del explorador a determinadas acciones de controlador (o controladores de Razor Pages).</span><span class="sxs-lookup"><span data-stu-id="241bd-105">Routing is responsible for mapping incoming browser requests to particular controller actions (or Razor Pages handlers).</span></span> <span data-ttu-id="241bd-106">En esta sección se explica cómo el enrutamiento difiere entre ASP.NET MVC (y Web API) y ASP.NET Core (MVC, Razor Pages, etc.).</span><span class="sxs-lookup"><span data-stu-id="241bd-106">This section covers how routing differs between ASP.NET MVC (and Web API) and ASP.NET Core (MVC, Razor Pages, and otherwise).</span></span>

## <a name="routing-in-aspnet-mvc-and-web-api"></a><span data-ttu-id="241bd-107">Enrutamiento en ASP.NET MVC y Web API</span><span class="sxs-lookup"><span data-stu-id="241bd-107">Routing in ASP.NET MVC and Web API</span></span>

<span data-ttu-id="241bd-108">ASP.NET MVC ofrece dos enfoques para el enrutamiento:</span><span class="sxs-lookup"><span data-stu-id="241bd-108">ASP.NET MVC offers two approaches to routing:</span></span>

1. <span data-ttu-id="241bd-109">La tabla de rutas, que es una colección de rutas que se pueden usar para hacer coincidir las solicitudes entrantes con las acciones de controlador.</span><span class="sxs-lookup"><span data-stu-id="241bd-109">The route table, which is a collection of routes that can be used to match incoming requests to controller actions.</span></span>
1. <span data-ttu-id="241bd-110">El enrutamiento mediante atributos, que realiza la misma función, pero se logra decorando las acciones por sí mismos, en lugar de editar una tabla de rutas global.</span><span class="sxs-lookup"><span data-stu-id="241bd-110">Attribute routing, which performs the same function but is achieved by decorating the actions themselves, rather than editing a global route table.</span></span>

## <a name="route-table"></a><span data-ttu-id="241bd-111">Tabla de rutas</span><span class="sxs-lookup"><span data-stu-id="241bd-111">Route table</span></span>

<span data-ttu-id="241bd-112">La tabla de rutas se configura cuando se inicia la aplicación.</span><span class="sxs-lookup"><span data-stu-id="241bd-112">The route table is configured when the app starts up.</span></span> <span data-ttu-id="241bd-113">Normalmente, una llamada al método estático se usa para configurar la colección de rutas global, como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="241bd-113">Typically, a static method call is used to configure the global route collection, like so:</span></span>

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

<span data-ttu-id="241bd-114">En el código anterior, la tabla de rutas se administra mediante el `RouteCollection` tipo, que se usa para agregar rutas nuevas con `MapRoute` .</span><span class="sxs-lookup"><span data-stu-id="241bd-114">In the preceding code, the route table is managed by the `RouteCollection` type, which is used to add new routes with `MapRoute`.</span></span> <span data-ttu-id="241bd-115">Las rutas se denominan e incluyen una cadena de ruta, que puede incluir parámetros para controladores, acciones, áreas y otros marcadores de posición.</span><span class="sxs-lookup"><span data-stu-id="241bd-115">Routes are named and include a route string, which can include parameters for controllers, actions, areas, and other placeholders.</span></span> <span data-ttu-id="241bd-116">Si una aplicación sigue una convención estándar, la mayoría de sus acciones se pueden controlar mediante esta única ruta predeterminada, con cualquier excepción a esta Convención configurada mediante rutas adicionales.</span><span class="sxs-lookup"><span data-stu-id="241bd-116">If an app follows a standard convention, most of its actions can be handled by this single default route, with any exceptions to this convention configured using additional routes.</span></span>

### <a name="attribute-routing-in-aspnet-mvc"></a><span data-ttu-id="241bd-117">Enrutamiento de atributos en MVC de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="241bd-117">Attribute routing in ASP.NET MVC</span></span>

<span data-ttu-id="241bd-118">Es posible que las rutas definidas con sus acciones sean más fáciles de detectar y que no sean las rutas definidas en una ubicación externa.</span><span class="sxs-lookup"><span data-stu-id="241bd-118">Routes that are defined with their actions may be easier to discover and reason about than routes defined in an external location.</span></span> <span data-ttu-id="241bd-119">Mediante el enrutamiento de atributos, un método de acción individual puede tener su ruta definida con un `[Route]` atributo:</span><span class="sxs-lookup"><span data-stu-id="241bd-119">Using attribute routing, an individual action method can have its route defined with a `[Route]` attribute:</span></span>

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

<span data-ttu-id="241bd-120">El [enrutamiento de atributos en ASP.NET MVC 5](https://devblogs.microsoft.com/aspnet/attribute-routing-in-asp-net-mvc-5/) también admite valores predeterminados y prefijos, que se pueden agregar en el nivel de controlador (y que se aplican a todas las acciones de ese controlador).</span><span class="sxs-lookup"><span data-stu-id="241bd-120">[Attribute routing in ASP.NET MVC 5](https://devblogs.microsoft.com/aspnet/attribute-routing-in-asp-net-mvc-5/) also supports defaults and prefixes, which can be added at the controller level (and which are applied to all actions within that controller).</span></span> <span data-ttu-id="241bd-121">Consulte la documentación para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="241bd-121">Refer to the documentation for details.</span></span>

<span data-ttu-id="241bd-122">La configuración del enrutamiento de atributos requiere agregar una línea a la configuración de la tabla de rutas predeterminada:</span><span class="sxs-lookup"><span data-stu-id="241bd-122">Setting up attribute routing requires adding one line to the default route table configuration:</span></span>

```csharp
routes.MapMvcAttributeRoutes();
```

<span data-ttu-id="241bd-123">El enrutamiento mediante atributos puede aprovechar las restricciones de ruta, tanto integradas como personalizadas, y admite rutas y áreas con nombre mediante el `[RouteArea]` atributo.</span><span class="sxs-lookup"><span data-stu-id="241bd-123">Attribute routing can take advantage of route constraints, both built-in and custom, and supports named routes and areas using the `[RouteArea]` attribute.</span></span> <span data-ttu-id="241bd-124">Si su aplicación usa áreas, deberá configurar la compatibilidad con ellas en el código de registro de la ruta agregando una línea más:</span><span class="sxs-lookup"><span data-stu-id="241bd-124">If your app uses areas, you'll need to configure support for them in your route registration code by adding one more line:</span></span>

```csharp
routes.MapMvcAttributeRoutes();

AreaRegistration.RegisterAllAreas();
```

### <a name="attribute-routing-in-aspnet-web-api-2"></a><span data-ttu-id="241bd-125">Enrutamiento de atributos en ASP.NET Web API 2</span><span class="sxs-lookup"><span data-stu-id="241bd-125">Attribute routing in ASP.NET Web API 2</span></span>

<span data-ttu-id="241bd-126">El [enrutamiento de atributos en ASP.net web API 2](/aspnet/web-api/overview/web-api-routing-and-actions/attribute-routing-in-web-api-2) es similar al enrutamiento en ASP.NET MVC 5, con pequeñas diferencias.</span><span class="sxs-lookup"><span data-stu-id="241bd-126">[Attribute routing in ASP.NET Web API 2](/aspnet/web-api/overview/web-api-routing-and-actions/attribute-routing-in-web-api-2) is similar to routing in ASP.NET MVC 5, with minor differences.</span></span> <span data-ttu-id="241bd-127">La configuración de Web API 2 se realiza normalmente en su propia clase, a la que se llama durante el inicio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="241bd-127">Configuring Web API 2 is typically done in its own class, which is called during app startup.</span></span> <span data-ttu-id="241bd-128">La configuración de enrutamiento de atributos se controla en esta clase:</span><span class="sxs-lookup"><span data-stu-id="241bd-128">Attribute routing configuration is handled in this class:</span></span>

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

<span data-ttu-id="241bd-129">Como se muestra en el código anterior, el enrutamiento de atributos se puede combinar con el enrutamiento basado en convenciones en aplicaciones de API Web.</span><span class="sxs-lookup"><span data-stu-id="241bd-129">As shown in the preceding code, attribute routing may be combined with convention-based routing in Web API apps.</span></span>

<span data-ttu-id="241bd-130">Además del enrutamiento de atributos, [ASP.net web API elige la acción que se va a llamar](/aspnet/web-api/overview/web-api-routing-and-actions/routing-and-action-selection) basándose en el método HTTP (por ejemplo, get o post), el `{action}` marcador de posición en una ruta (si existe) y los parámetros de la acción.</span><span class="sxs-lookup"><span data-stu-id="241bd-130">In addition to attribute routing, [ASP.NET Web API chooses which action to call](/aspnet/web-api/overview/web-api-routing-and-actions/routing-and-action-selection) based on the HTTP method (for example, GET or POST), the `{action}` placeholder in a route (if any), and parameters of the action.</span></span> <span data-ttu-id="241bd-131">En muchos casos, el nombre de la acción ayudará a determinar si coinciden, ya que el uso del nombre de la acción como "Get" o "post" se usa para hacer coincidir con el método HTTP adecuado.</span><span class="sxs-lookup"><span data-stu-id="241bd-131">In many cases, the name of the action will help determine whether it's matched, since prefixing the action name with "Get" or "Post" is used to match the appropriate HTTP method to it.</span></span> <span data-ttu-id="241bd-132">Como alternativa, las acciones se pueden decorar con un atributo de método HTTP adecuado, como `[HttpGet]` , lo que permite el uso de nombres de acción que no tienen el prefijo de un método http.</span><span class="sxs-lookup"><span data-stu-id="241bd-132">Alternatively, actions can be decorated with an appropriate HTTP method attribute, like `[HttpGet]`, allowing the use of action names that aren't prefixed with an HTTP method.</span></span>

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

<span data-ttu-id="241bd-133">Dado el controlador anterior, una solicitud HTTP GET para `localhost:123/products/` coincide con la `GetAll` acción.</span><span class="sxs-lookup"><span data-stu-id="241bd-133">Given the above controller, an HTTP GET request to `localhost:123/products/` matches the `GetAll` action.</span></span> <span data-ttu-id="241bd-134">Una solicitud HTTP GET para `localhost:123/products?name=ardalis` coincide con la `FindProductsByName` acción.</span><span class="sxs-lookup"><span data-stu-id="241bd-134">An HTTP GET request to `localhost:123/products?name=ardalis` matches the `FindProductsByName` action.</span></span>

## <a name="routing-in-aspnet-core-31"></a><span data-ttu-id="241bd-135">Enrutamiento en ASP.NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="241bd-135">Routing in ASP.NET Core 3.1</span></span>

<span data-ttu-id="241bd-136">En ASP.NET Core, el enrutamiento se controla mediante middleware de enrutamiento, que coincide con las direcciones URL de las solicitudes entrantes a acciones u otros puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="241bd-136">In ASP.NET Core, routing is handled by routing middleware, which matches the URLs of incoming requests to actions or other endpoints.</span></span> <span data-ttu-id="241bd-137">Las acciones del controlador se enrutan de forma convencional o se enrutan mediante atributos.</span><span class="sxs-lookup"><span data-stu-id="241bd-137">Controller actions are either conventionally routed or attribute-routed.</span></span> <span data-ttu-id="241bd-138">El enrutamiento convencional es similar al enfoque de tabla de rutas usado en ASP.NET MVC y Web API.</span><span class="sxs-lookup"><span data-stu-id="241bd-138">Conventional routing is similar to the route table approach used in ASP.NET MVC and Web API.</span></span> <span data-ttu-id="241bd-139">Tanto si usa el atributo convencional como el de ambos, debe configurar la aplicación para que use el middleware de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="241bd-139">Whether you're using conventional, attribute, or both, you need to configure your app to use the routing middleware.</span></span> <span data-ttu-id="241bd-140">Para usar el middleware, agregue el código siguiente al `Startup.Configure` método:</span><span class="sxs-lookup"><span data-stu-id="241bd-140">To use the middleware, add the following code to your `Startup.Configure` method:</span></span>

```csharp
app.UseRouting();
```

### <a name="conventional-routing"></a><span data-ttu-id="241bd-141">Enrutamiento convencional</span><span class="sxs-lookup"><span data-stu-id="241bd-141">Conventional routing</span></span>

<span data-ttu-id="241bd-142">Con el enrutamiento convencional, configure una o varias convenciones que se usarán para hacer coincidir las direcciones URL de entrada con los *extremos* de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="241bd-142">With conventional routing, you set up one or more conventions that will be used to match incoming URLs to *endpoints* in the app.</span></span> <span data-ttu-id="241bd-143">En ASP.NET Core, estos puntos de conexión pueden ser acciones de controlador, como en ASP.NET MVC o Web API.</span><span class="sxs-lookup"><span data-stu-id="241bd-143">In ASP.NET Core, these endpoints may be controller actions, like in ASP.NET MVC or Web API.</span></span> <span data-ttu-id="241bd-144">Los puntos de conexión también se pueden Razor Pages, comprobaciones de estado o concentradores de Signalr.</span><span class="sxs-lookup"><span data-stu-id="241bd-144">The endpoints could also be Razor Pages, Health Checks, or SignalR hubs.</span></span> <span data-ttu-id="241bd-145">Todas estas características enrutables se configuran de manera similar mediante puntos de conexión:</span><span class="sxs-lookup"><span data-stu-id="241bd-145">All of these routable features are configured in a similar fashion using endpoints:</span></span>

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

<span data-ttu-id="241bd-146">El código anterior se usa (además de `UseRouting` ) para configurar varios puntos de conexión, incluidas las comprobaciones de estado, los controladores y el Razor pages.</span><span class="sxs-lookup"><span data-stu-id="241bd-146">The preceding code is used (in addition to `UseRouting`) to configure various endpoints, including Health Checks, controllers, and Razor Pages.</span></span> <span data-ttu-id="241bd-147">En el caso de los controladores, la configuración anterior especifica una Convención de enrutamiento predeterminada, que es el patrón bastante estándar `{controller}/{action}/{id?}` que se recomienda desde las primeras versiones de ASP.NET MVC.</span><span class="sxs-lookup"><span data-stu-id="241bd-147">For controllers, the above configuration specifies a default routing convention, which is the fairly standard `{controller}/{action}/{id?}` pattern that's been recommended since the first versions of ASP.NET MVC.</span></span>

### <a name="attribute-routing"></a><span data-ttu-id="241bd-148">Enrutamiento mediante atributos</span><span class="sxs-lookup"><span data-stu-id="241bd-148">Attribute routing</span></span>

<span data-ttu-id="241bd-149">El enrutamiento de atributos en ASP.NET Core es el método preferido para configurar el enrutamiento en los controladores.</span><span class="sxs-lookup"><span data-stu-id="241bd-149">Attribute routing in ASP.NET Core is the preferred approach for configuring routing in controllers.</span></span> <span data-ttu-id="241bd-150">Si va a compilar las API, el `[ApiController]` atributo se debe aplicar a los controladores.</span><span class="sxs-lookup"><span data-stu-id="241bd-150">If you're building APIs, the `[ApiController]` attribute should be applied to your controllers.</span></span> <span data-ttu-id="241bd-151">Entre otras cosas, este atributo requiere el uso del enrutamiento de atributo para las acciones en estas clases de controlador.</span><span class="sxs-lookup"><span data-stu-id="241bd-151">Among other things, this attribute requires the use of attribute routing for actions in such controller classes.</span></span>

<span data-ttu-id="241bd-152">El enrutamiento de atributos en ASP.NET Core se comporta de forma similar en ASP.NET MVC y Web API.</span><span class="sxs-lookup"><span data-stu-id="241bd-152">Attribute routing in ASP.NET Core behaves similarly in ASP.NET MVC and Web API.</span></span> <span data-ttu-id="241bd-153">Además de admitir el `[Route]` atributo, sin embargo, la información de ruta también se puede especificar como parte del atributo de método http:</span><span class="sxs-lookup"><span data-stu-id="241bd-153">In addition to supporting the `[Route]` attribute, however, route information can also be specified as part of the HTTP method attribute:</span></span>

```csharp
[HttpGet("api/products/{id}")]
public async ActionResult<Product> Details(int id)
{
    // ...
}
```

<span data-ttu-id="241bd-154">Al igual que con las versiones anteriores, puede especificar una ruta predeterminada con marcadores de posición y Agregar esto en el nivel de clase del controlador o incluso en una clase base.</span><span class="sxs-lookup"><span data-stu-id="241bd-154">As with previous versions, you can specify a default route with placeholders, and add this at the controller class level or even on a base class.</span></span> <span data-ttu-id="241bd-155">Use el mismo `[Route]` atributo para todos estos casos.</span><span class="sxs-lookup"><span data-stu-id="241bd-155">You use the same `[Route]` attribute for all of these cases.</span></span> <span data-ttu-id="241bd-156">Por ejemplo, una clase de controlador de API base podría tener este aspecto:</span><span class="sxs-lookup"><span data-stu-id="241bd-156">For example, a base API controller class might look like this:</span></span>

```csharp
[Route("api/{controller}/{action}/{id?:int}")]
public abstract class BaseApiController : ControllerBase, IApiController
{
    // ...
}
```

<span data-ttu-id="241bd-157">Con este atributo, las clases que heredan de este tipo enrutarán las direcciones URL a las acciones según el nombre del controlador, el nombre de acción y un parámetro de entero opcional `id` .</span><span class="sxs-lookup"><span data-stu-id="241bd-157">Using this attribute, classes inheriting from this type would route URLs to actions based on the controller name, action name, and an optional integer `id` parameter.</span></span>

## <a name="references"></a><span data-ttu-id="241bd-158">Referencias</span><span class="sxs-lookup"><span data-stu-id="241bd-158">References</span></span>

- [<span data-ttu-id="241bd-159">Información general sobre el enrutamiento ASP.NET MVC</span><span class="sxs-lookup"><span data-stu-id="241bd-159">ASP.NET MVC Routing Overview</span></span>](/aspnet/mvc/overview/older-versions-1/controllers-and-routing/asp-net-mvc-routing-overview-cs)
- [<span data-ttu-id="241bd-160">Enrutamiento de atributos en ASP.NET MVC 5</span><span class="sxs-lookup"><span data-stu-id="241bd-160">Attribute Routing in ASP.NET MVC 5</span></span>](https://devblogs.microsoft.com/aspnet/attribute-routing-in-asp-net-mvc-5/)
- [<span data-ttu-id="241bd-161">Enrutamiento de atributos en ASP.NET Web API 2</span><span class="sxs-lookup"><span data-stu-id="241bd-161">Attribute routing in ASP.NET Web API 2</span></span>](/aspnet/web-api/overview/web-api-routing-and-actions/attribute-routing-in-web-api-2)
- [<span data-ttu-id="241bd-162">Enrutamiento y selección de acciones en ASP.NET Web API</span><span class="sxs-lookup"><span data-stu-id="241bd-162">Routing and Action Selection in ASP.NET Web API</span></span>](/aspnet/web-api/overview/web-api-routing-and-actions/routing-and-action-selection)
- [<span data-ttu-id="241bd-163">Enrutamiento en ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="241bd-163">Routing in ASP.NET Core</span></span>](/aspnet/core/fundamentals/routing)
- [<span data-ttu-id="241bd-164">Enrutamiento a las acciones del controlador en ASP.NET Core MVC</span><span class="sxs-lookup"><span data-stu-id="241bd-164">Routing to controller actions in ASP.NET Core MVC</span></span>](/aspnet/core/mvc/controllers/routing)

>[!div class="step-by-step"]
><span data-ttu-id="241bd-165">[Anterior](configuration-differences.md)
>[Siguiente](comparing-razor-pages-aspnet-mvc.md)</span><span class="sxs-lookup"><span data-stu-id="241bd-165">[Previous](configuration-differences.md)
[Next](comparing-razor-pages-aspnet-mvc.md)</span></span>
