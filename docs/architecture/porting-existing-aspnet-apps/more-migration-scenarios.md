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

## <a name="custom-model-binding"></a>Enlace de modelos personalizado

La mayoría de las aplicaciones de ASP.NET MVC y Web API hacen uso del enlace de modelos. La sintaxis de enlace de modelos predeterminada migra de forma bastante fluida entre estas aplicaciones y ASP.NET Core MVC. Sin embargo, en algunos casos, los clientes han escrito [enlazadores de modelos personalizados](/aspnet/web-api/overview/formats-and-model-binding/parameter-binding-in-aspnet-web-api#model-binders) para admitir determinados tipos de modelos o escenarios de uso. Los enlazadores de modelos personalizados en proyectos de ASP.NET MVC y Web API usan `IModelBinder` interfaces independientes definidas en los `System.Web.Mvc` espacios de `System.Web.Http` nombres y, respectivamente. En ambos casos, el enlazador personalizado expone un `Bind` método que acepta un contexto de controlador o de acción y un contexto de enlace de modelo como argumentos.

Una vez creado el enlazador personalizado, se debe registrar con la aplicación. Este paso requiere la creación de otro tipo, `ModelBinderProvider` que actúa como generador y crea el enlazador de modelos durante una solicitud. Los enlazadores se pueden agregar durante `ApplicationStart` en aplicaciones MVC como se muestra a continuación:

```csharp
ModelBinderProviders.BinderProviders.Insert(0, new MyCustomBinderProvider()); // MVC
```

En aplicaciones de API Web, se puede hacer referencia a los enlazadores personalizados mediante atributos. El `ModelBinder` atributo se puede Agregar a los parámetros de método de acción o a la definición de tipo del parámetro, como se muestra a continuación:

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

Para registrar un enlazador de modelos globalmente en ASP.NET Web API, se debe agregar su proveedor durante el inicio de la aplicación:

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

Al migrar [proveedores de modelos personalizados a ASP.net Core](/aspnet/core/mvc/advanced/custom-model-binding#custom-model-binder-sample), el patrón de API Web está más cerca del enfoque de ASP.NET Core que ASP.NET MVC 5. Las principales diferencias entre la interfaz de ASP.NET Core `IModelBinder` y la API Web es que el método ASP.net Core es Async ( `BindModelAsync` ) y solo requiere un `BindingModelContext` parámetro único en lugar de dos parámetros, como la versión de API Web necesaria. En ASP.NET Core, puede usar un `[ModelBinder]` atributo en parámetros de método de acción individuales o en sus tipos asociados. También puede crear un `ModelBinderProvider` que se usará globalmente dentro de la aplicación cuando sea necesario. Para configurar este tipo de proveedor, debe agregar código a `Startup` en `ConfigureServices` :

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddControllers(options =>
    {
        options.ModelBinderProviders.Insert(0, new CustomModelBinderProvider());
    });
}
```

## <a name="media-formatters"></a>Formateadores multimedia

ASP.NET Web API admite varios formatos multimedia y se puede extender mediante formateadores multimedia personalizados. Los documentos describen un [formateador de medios CSV de ejemplo](/aspnet/web-api/overview/formats-and-model-binding/media-formatters#example-creating-a-csv-media-formatter) que se puede usar para enviar datos en un formato de valores separados por comas. Si la aplicación de API Web usa formateadores de medios personalizados, deberá convertirlos en [ASP.net Core formateadores personalizados](/aspnet/core/web-api/advanced/custom-formatters).

Para crear un formateador personalizado en Web API 2, se ha heredado de una clase base adecuada y, a continuación, se ha agregado el formateador a la canalización de la API Web mediante el `HttpConfiguration` objeto:

```csharp
public static void ConfigureApis(HttpConfiguration config)
{
    config.Formatters.Add(new ProductCsvFormatter()); 
}
```

En ASP.NET Core, el proceso es similar. ASP.NET Core admite formateadores de entrada (utilizados por el enlace de modelos) y formateadores de salida (usados para dar formato a las respuestas). Agregar un formateador personalizado a las respuestas de salida de una manera específica implica heredar de una clase base adecuada y agregar el formateador a MVC en `Startup` :

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

Encontrará una lista completa de las clases base en el espacio de nombres [Microsoft. AspNetCore. Mvc. Formatters](https://docs.microsoft.com/dotnet/api/microsoft.aspnetcore.mvc.formatters) .

Los pasos para migrar desde un formateador de Web API a un formateador de MVC ASP.NET Core son:

1. Identifique una clase base adecuada para el nuevo formateador.
1. Cree una nueva instancia de la clase base e implemente los métodos necesarios.
1. Copie la funcionalidad del formateador de la API Web a la nueva implementación.
1. Configure MVC en el método de la aplicación ASP.NET Core `ConfigureServices` para usar el formateador nuevo.

## <a name="custom-filters"></a>Filtros personalizados

Los filtros se usan en ASP.NET Core aplicaciones para ejecutar código antes o después de ciertas fases de la canalización de procesamiento de solicitudes. ASP.NET MVC y Web API también usan filtros de forma muy similar, pero los detalles varían. Por ejemplo, [ASP.NET MVC admite cuatro tipos de filtros](/aspnet/mvc/overview/older-versions-1/controllers-and-routing/understanding-action-filters-cs#the-different-types-of-filters). ASP.NET Web API 2 admite filtros similares y los atributos MVC y Web API incluidos para [invalidar los filtros](/dotnet/api/system.web.mvc.filters.ioverridefilter).

El filtro más común que se usa en las aplicaciones de ASP.NET MVC y Web API es el filtro de acción, que se define mediante una [interfaz IActionFilter](/dotnet/api/system.web.mvc.iactionfilter). Esta interfaz proporciona métodos para antes ( `OnActionExecuting` ) y después de ( `OnActionExecuted` ), que se pueden utilizar para ejecutar código antes o después de que se ejecute una acción, como se indica en cada método.

ASP.NET Core sigue admitiendo filtros y su unificación de MVC y Web API significa que solo hay un enfoque para su implementación. Los [documentos incluyen una cobertura detallada de los cinco (5) tipos de filtros integrados en ASP.net Core MVC](/aspnet/core/mvc/controllers/filters#filter-types). Todas las variantes de filtro que se admiten en ASP.NET MVC y ASP.NET Web API tienen asociadas versiones en ASP.NET Core, por lo que la migración suele ser solo cuestión de identificar la interfaz o clase base adecuada y migrar el código.

Además de las interfaces sincrónicas, ASP.NET Core también proporciona interfaces asincrónicas como `IAsyncActionFilter` las que proporcionan un único método asincrónico que se puede usar para incorporar código para ejecutarse antes y después de la acción, como se muestra a continuación:

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

Al migrar código asincrónico (o código que debe ser asincrónico), los equipos deben considerar la posibilidad de aprovechar los tipos Async integrados que se proporcionan con este fin.

La mayoría de las aplicaciones de ASP.NET MVC y Web API no usan un gran número de filtros personalizados. Dado que el enfoque de los filtros en ASP.NET Core MVC está estrechamente alineado con los filtros de ASP.NET MVC y Web API, la migración de filtros personalizados es generalmente bastante sencilla. Asegúrese de leer la documentación detallada sobre los filtros en los documentos de ASP.NET Core y, una vez que esté seguro de que tiene una buena comprensión de ellos, porte la lógica del sistema anterior a los filtros del sistema nuevo.

## <a name="route-constraints"></a>Restricciones de ruta

ASP.NET Core usa restricciones de ruta para asegurarse de que las solicitudes se enruten correctamente para enrutar una solicitud. [ASP.NET Core admite un gran número de restricciones de ruta diferentes para este propósito]/ASPNET/Core/Fundamentals/Routing # Route-Constraint-Reference. Las restricciones de ruta se pueden aplicar en la tabla de rutas, pero la mayoría de las aplicaciones compiladas con ASP.NET MVC 5 y/o [ASP.net web API 2](/aspnet/web-api/overview/web-api-routing-and-actions/attribute-routing-in-web-api-2#route-constraints) usan restricciones de ruta insertadas que se aplican a las rutas de atributo. Las restricciones de ruta en línea utilizan un formato como este:

```csharp
[Route("/customer/{id:int}")]
```

`:int`Después de que el `id` parámetro de ruta restringe el valor para que coincida con el `int` tipo. Una ventaja del uso de restricciones de ruta es que permiten dos rutas que, de otro modo, son idénticas, donde los parámetros solo se diferencian por su tipo. Esto permite el equivalente de la [sobrecarga de métodos](/dotnet/standard/design-guidelines/member-overloading) de las rutas basadas únicamente en el tipo de parámetro.

El conjunto de restricciones de ruta, su sintaxis y el uso son muy similares entre los tres métodos. Las restricciones de ruta personalizadas son bastante poco frecuentes en las aplicaciones de cliente. Si la aplicación usa una restricción de ruta personalizada y necesita portar a ASP.NET Core, los documentos incluyen ejemplos que muestran [Cómo crear restricciones de ruta personalizadas en ASP.net Core](/aspnet/core/fundamentals/routing#custom-route-constraints). Esencialmente, lo único que se necesita es implementar `IRouteConstraint` y su `Match` método y, después, agregar la restricción personalizada al configurar el enrutamiento de la aplicación:

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

Esto es muy similar a cómo se usan las restricciones personalizadas en ASP.NET Web API, que usa `IHttpRouteConstraint` y configura mediante un solucionador y una llamada a `HttpConfiguration.MapHttpAttributeRoutes` :

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

ASP.NET MVC 5 sigue un enfoque muy similar, usando `IRouteConstraint` para su nombre de interfaz y configurando la restricción como parte de la configuración de la ruta:

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

La migración del uso de restricciones de ruta y las restricciones de ruta personalizadas a ASP.NET Core suele ser muy sencilla.

## <a name="custom-route-handlers"></a>Controladores de rutas personalizados

Otra característica bastante avanzada de ASP.NET MVC 5 son los controladores de ruta. Los controladores de rutas personalizados implementan `IRouteHandler` , que incluye un único método que devuelve un `IHttpHandler` para una solicitud de entrega. `IHttpHandler`A su vez, expone una `IsReusable` propiedad y un `ProcessRequest` método único. En ASP.NET MVC 5, puede configurar una ruta determinada en la tabla de rutas para usar el controlador personalizado:

```csharp
public static void RegisterRoutes(RouteCollection routes)
{
    routes.IgnoreRoute("{resource}.axd/{*pathInfo}");
 
    routes.Add(new Route("custom", new CustomRouteHandler()));
}
```

Para migrar controladores de rutas personalizados de ASP.NET MVC 5 a ASP.NET Core, puede usar un filtro (por ejemplo, un filtro de acción) o un personalizado [`IRouter`](/dotnet/api/microsoft.aspnetcore.routing.irouter) . El enfoque de filtro es relativamente sencillo y se puede agregar como un filtro global cuando MVC se agrega a `ConfigureServices` en *Startup. CS*.

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddMvc(options =>
    {
        options.Filters.Add(typeof(CustomActionFilter));
    });
}
```

La `IRouter` opción requiere la implementación de los `RouteAsync` métodos y de la interfaz `GetVirtualPath` . El enrutador personalizado se agrega a la canalización de solicitudes en el `Configure` método en *Startup. CS*.

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

En ASP.NET Web API, estos controladores se conocen como controladores de [mensajes personalizados](/aspnet/web-api/overview/advanced/http-message-handlers#custom-message-handlers), en lugar de *controladores de ruta*. Los controladores de mensajes deben derivar de `DelegatingHandler` e invalidar su `SendAsync` método. Los controladores de mensajes se pueden encadenar juntos para formar una canalización de un modo muy similar a ASP.NET Core middleware y su canalización de solicitudes.

ASP.NET Core no tiene un `DelegatingHandler` tipo o una canalización de controlador de mensajes independiente. En su lugar, estos controladores se deben migrar mediante filtros globales, `IRouter` instancias personalizadas (véase más arriba) o middleware personalizado. ASP.NET Core los filtros y `IRouter` tipos MVC tienen la ventaja de tener acceso integrado a las construcciones MVC como los controladores y las acciones, mientras que el middleware es un enfoque de nivel inferior que no tiene ninguna vinculación a MVC. Esto hace que sea más flexible, pero también requiere más esfuerzo si necesita tener acceso a los componentes de MVC.

## <a name="cors-support"></a>Compatibilidad con CORS

CORS, o el uso compartido de recursos entre orígenes, es un estándar del W3C que permite a los servidores aceptar solicitudes que no se originan a partir de las respuestas a las que han servido. ASP.NET MVC 5 y ASP.NET Web API 2 admiten CORS de maneras diferentes. La manera más sencilla de habilitar la compatibilidad con CORS en ASP.NET MVC 5 es con un filtro de acción como este:

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

ASP.NET Web API también puede usar este tipo de filtro, pero también tiene [compatibilidad integrada para habilitar CORS](/aspnet/web-api/overview/security/enabling-cross-origin-requests-in-web-api#enable-cors) también:

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

Una vez que se agrega, puede configurar orígenes, encabezados y métodos permitidos mediante el `EnableCors` atributo, de la siguiente manera:

```csharp
[EnableCors(origins: "https://dot.net", headers: "*", methods: "*")]
public class TestController : ApiController
{
    // Controller methods not shown...
}
```

Antes de migrar la implementación de CORS desde ASP.NET MVC 5 o ASP.NET Web API 2, asegúrese de revisar [Cómo funciona CORS](/aspnet/web-api/overview/security/enabling-cross-origin-requests-in-web-api#how-cors-works) y crear algunas pruebas automatizadas que demuestran que CORS funciona según lo previsto en el sistema actual.

En ASP.NET Core, hay tres formas integradas de habilitar CORS:

- [Configurado a través](/aspnet/core/security/cors?#cors-with-named-policy-and-middleware) de la Directiva en `ConfigureServices`
- Habilitado con [enrutamiento de punto de conexión](/aspnet/core/security/cors?#enable-cors-with-endpoint-routing)
- Habilitado con el [ `EnableCors` atributo](/aspnet/core/security/cors?view=aspnetcore-5.0#enable-cors-with-attributes)

Cada uno de estos enfoques se trata en detalle en los documentos, que están vinculados de las opciones anteriores. El que elija dependerá en gran medida de cómo la aplicación existente sea compatible con CORS. Si la aplicación usa atributos, probablemente pueda migrar para usar el `EnableCors` atributo más fácilmente. Si la aplicación usa filtros, puede seguir usando ese enfoque (aunque no es el enfoque típico que se usa en ASP.NET Core) o migrar para usar atributos o directivas. El enrutamiento de puntos de conexión es una característica relativamente nueva que se presentó con ASP.NET Core 3 y, como tal, no tiene un estrecho análogo en las aplicaciones ASP.NET MVC 5 o ASP.NET Web API 2.

## <a name="custom-areas"></a>Áreas personalizadas

Muchas aplicaciones ASP.NET MVC usan áreas para organizar el proyecto. Normalmente, las áreas residen en la raíz del proyecto en una carpeta de *áreas* y deben registrarse cuando se inicia la aplicación, normalmente en `Application_Start()` :

```csharp
AreaRegistration.RegisterAllAreas();
```

Una alternativa al registro de todas las áreas en el inicio es usar el `RouteArea` atributo en los controladores individuales:

```csharp
[RouteArea("Admin")]
public class SomeController : Controller
```

Cuando se usan áreas, se pasan argumentos adicionales a métodos auxiliares HTML para generar vínculos a acciones en diferentes áreas:

```cshtml
@Html.ActionLink("News", "Index", "News", new { area = "News" }, null)
```

Las aplicaciones ASP.NET Web API no suelen usar áreas explícitamente, ya que sus controladores pueden colocarse en cualquier carpeta del proyecto. Los equipos pueden usar cualquier estructura de carpetas que deseen para organizar sus controladores de API.

Las [áreas](/aspnet/core/mvc/controllers/areas) se admiten en ASP.net Core MVC. El enfoque utilizado es casi idéntico al uso de áreas de ASP.NET MVC 5. Los desarrolladores que migran código mediante áreas deben tener en cuenta las siguientes diferencias:

- `AreaRegistration.RegisterAllAreas` no se usa en ASP.NET Core MVC
- Las áreas se aplican mediante el `[Area("name")]` atributo (no `RouteArea` como en ASP.NET MVC 5)
- Se pueden agregar áreas a las plantillas de tabla de rutas, si se desea (o pueden usar el enrutamiento de atributos).

Para agregar compatibilidad de área a la tabla de rutas en ASP.NET Core MVC, debe agregar lo siguiente en `Configure` en *Startup. CS*:

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

Las áreas también se pueden usar con el enrutamiento de atributos, mediante la `{area}` palabra clave en la definición de ruta (es uno de los distintos [nombres de enrutamiento reservados](/aspnet/core/mvc/controllers/routing#reserved-routing-names) que se pueden usar con las plantillas de ruta).

Las aplicaciones auxiliares de etiquetas admiten áreas con el `asp-area` atributo, que se pueden usar para generar vínculos en las vistas y páginas de Razor:

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

Si va a migrar a Razor Pages tendrá que usar una carpeta de *áreas* en la carpeta de *páginas* . Para obtener más información, vea [áreas con Razor pages](/aspnet/core/mvc/controllers/areas#areas-with-razor-pages).

Además de las instrucciones anteriores, los equipos deben revisar [Cómo funciona el enrutamiento en ASP.net Core con áreas](/aspnet/core/mvc/controllers/routing#areas) como parte de su proceso de planeamiento de la migración.

## <a name="integration-tests-for-aspnet-mvc-and-aspnet-web-api"></a>Pruebas de integración para ASP.NET MVC y ASP.NET Web API

Las pruebas de integración son pruebas automatizadas que comprueban que varias partes de una aplicación funcionan correctamente en conjunto. Escribir pruebas de integración para ASP.NET MVC y ASP.NET Web API normalmente implica implementar la aplicación en un servidor web real, como una instancia local de IIS o IIS Express y, a continuación, realizar solicitudes a esta aplicación hospedada mediante un cliente HTTP. Algunas de estas pruebas pueden interactuar con la interfaz de usuario del lado cliente mediante herramientas de automatización del explorador como [Selenium](https://www.selenium.dev/), aunque a menudo se hace referencia a ellas como *pruebas de IU* en lugar de a pruebas de integración.

Si la aplicación migrada comparte el mismo comportamiento que la versión original, independientemente de la tecnología existente que use el equipo para realizar las pruebas de integración (y las pruebas de interfaz de usuario) debe seguir funcionando igual que antes. Estas pruebas suelen ser indistintas de la tecnología subyacente que se usa para hospedar la aplicación que están probando e interactuar con ella solo a través de solicitudes HTTP. La situación en la que los elementos pueden ser más desafiantes es cómo interactúan las pruebas con la aplicación para ponerla en un estado correcto conocido antes de cada prueba. Esto puede requerir algún esfuerzo de migración, ya que la configuración y el inicio son significativamente diferentes en ASP.NET Core en comparación con ASP.NET MVC o ASP.NET Web API.

Los equipos deben considerar fuertemente la migración de sus pruebas de integración para usar la compatibilidad con las [pruebas de integración integradas de ASP.net Core](/aspnet/core/test/integration-tests) . En ASP.NET Core, las aplicaciones se pueden probar mediante su implementación en un `TestHost` , que se configura mediante `WebApplicationFactory` . Hay un poco de configuración necesaria para hospedar la aplicación para las pruebas, pero una vez que se implementa, la creación de pruebas de integración individuales es muy sencilla.

Una de las mejores características de la compatibilidad con las pruebas de integración de ASP.NET Core es que la aplicación se hospeda en la memoria. No es necesario configurar un servidor de Live real para hospedar la aplicación. No es necesario usar una herramienta de automatización del explorador (si solo está probando ASP.NET Core y no el comportamiento del lado cliente). Muchos de los problemas que se pueden encontrar al intentar usar un servidor web real para las pruebas de integración automatizadas, como problemas de firewall o problemas de inicio y detención de procesos, se eliminan con este enfoque. Puesto que las solicitudes se realizan en memoria sin ningún requisito de red, las pruebas también tienden a ejecutarse mucho más rápido que las pruebas que deben configurar un servidor WebServer independiente y comunicarse con ella a través de la red (incluso si se ejecuta en el mismo equipo).

A continuación puede ver un ejemplo ASP.NET Core prueba de integración (a veces denominada *pruebas funcionales* para distinguirlas de las pruebas de integración de nivel inferior) de la [aplicación de referencia eShopOnWeb](https://github.com/dotnet-architecture/eShopOnWeb):

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

Si la aplicación que se migra no tiene ninguna prueba de integración, el proceso de migración puede ser una gran oportunidad para agregar algunos. Estas pruebas pueden comprobar que la aplicación migrada se comporta como espera el equipo. Cuando estas pruebas se aplican al principio de una migración, pueden garantizar que los esfuerzos de migración posteriores no interrumpan partes migradas previamente de la aplicación. Dada la facilidad con la que se configuran y ejecutan las pruebas de integración en ASP.NET Core, el retorno de la inversión dedicada a la configuración de dichas pruebas suele ser bastante alto.

## <a name="wcf-client-configuration"></a>Configuración del cliente de WCF

Si su aplicación actualmente se basa en los servicios WCF como un cliente, se admite este escenario. Sin embargo, tendrá que [migrar la configuración](/aspnet/core/migration/configuration) de *web.config* para usar el nuevo *appsettings.jsen* el archivo. Otra opción es agregar cualquier configuración necesaria a los clientes mediante programación cuando se crean. Por ejemplo:

```csharp
var wcfClient = new OrderServiceClient(
    new BasicHttpBinding(BasicHttpSecurityMode.None),
    new EndpointAddress("http://localhost:5050/OrderService.svc"));
```

Si su organización tiene extensos servicios compilados con WCF en el que se basa la aplicación, considere la posibilidad de migrarlos para usar gRPC en su lugar. Para obtener más detalles sobre gRPC, por qué es posible que desee migrar y una guía de migración detallada, consulte el libro electrónico [de gRPC para desarrolladores de WCF](/dotnet/architecture/grpc-for-wcf-developers/) .

## <a name="references"></a>Referencias

- [ASP.NET Web API la negociación de contenido](/aspnet/web-api/overview/formats-and-model-binding/content-negotiation)
- [Aplicación de formato a datos de respuesta en ASP.NET Core Web API](/aspnet/core/web-api/advanced/formatting)
- [Enlazadores de modelos personalizados en ASP.NET Web API](/aspnet/web-api/overview/formats-and-model-binding/parameter-binding-in-aspnet-web-api#model-binders)
- [Enlazadores de modelos personalizados en ASP.NET Core](/aspnet/core/mvc/advanced/custom-model-binding#custom-model-binder-sample)
- [Formateadores de medios en ASP.NET Web API 2](/aspnet/web-api/overview/formats-and-model-binding/media-formatters)\
- [Formateadores personalizados en ASP.NET Core Web API](/aspnet/core/web-api/advanced/custom-formatters)
- [Filtros en ASP.NET Core](/aspnet/core/mvc/controllers/filters)
- [Restricciones de ruta en ASP.NET Web API 2](/aspnet/web-api/overview/web-api-routing-and-actions/attribute-routing-in-web-api-2#route-constraints)
- [Restricciones de ruta en ASP.NET MVC 5](https://devblogs.microsoft.com/aspnet/attribute-routing-in-asp-net-mvc-5/#route-constraints)
- [ASP.NET Core referencia de restricción de ruta](/aspnet/core/fundamentals/routing#route-constraint-reference)
- [Controladores de mensajes personalizados en ASP.NET Web API 2](/aspnet/web-api/overview/advanced/http-message-handlers#custom-message-handlers)
- [Control de CORS simple en MVC 5 y Web API 2](https://stackoverflow.com/questions/6290053/setting-access-control-allow-origin-in-asp-net-mvc-simplest-possible-method)
- [Habilitación de solicitudes entre orígenes en Web API](/aspnet/web-api/overview/security/enabling-cross-origin-requests-in-web-api#enable-cors)
- [Habilitación de solicitudes entre orígenes (CORS) en ASP.NET Core](/aspnet/core/security/cors)
- [Áreas de ASP.NET Core](/aspnet/core/mvc/controllers/areas)
- [Pruebas de integración en ASP.NET Core](/aspnet/core/test/integration-tests)

>[!div class="step-by-step"]
>[Anterior](example-migration-eshop.md)
>[Siguiente](deployment-scenarios.md)
