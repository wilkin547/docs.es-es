---
title: Comparar middleware con módulos y controladores
description: En esta sección se analizan las diferencias en la estructura de las aplicaciones de ASP.NET que usan controladores y módulos con ASP.NET Core aplicaciones que definen el middleware para sus canalizaciones de control de solicitudes.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 3bc3c30a1ee988550cca907d7289583161337cb9
ms.sourcegitcommit: b5d2290673e1c91260c9205202dd8b95fbab1a0b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "106122877"
---
# <a name="compare-middleware-to-modules-and-handlers"></a><span data-ttu-id="24d1e-103">Comparar middleware con módulos y controladores</span><span class="sxs-lookup"><span data-stu-id="24d1e-103">Compare middleware to modules and handlers</span></span>

<span data-ttu-id="24d1e-104">Si su aplicación existente de ASP.NET MVC o de API Web usa OWIN/Katana, lo más probable es que ya esté familiarizado con el concepto de middleware y su portabilidad a ASP.NET Core debe ser bastante sencillo.</span><span class="sxs-lookup"><span data-stu-id="24d1e-104">If your existing ASP.NET MVC or Web API app uses OWIN/Katana, you're most likely already familiar with the concept of middleware and porting it to ASP.NET Core should be fairly straightforward.</span></span> <span data-ttu-id="24d1e-105">Sin embargo, la mayoría de las aplicaciones ASP.NET dependen de módulos HTTP y controladores HTTP en lugar de middleware.</span><span class="sxs-lookup"><span data-stu-id="24d1e-105">However, most ASP.NET apps rely on HTTP modules and HTTP handlers instead of middleware.</span></span> <span data-ttu-id="24d1e-106">La migración de estos a ASP.NET Core requiere un esfuerzo adicional.</span><span class="sxs-lookup"><span data-stu-id="24d1e-106">Migrating these to ASP.NET Core requires extra effort.</span></span>

## <a name="aspnet-modules-and-handlers"></a><span data-ttu-id="24d1e-107">Módulos y controladores de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="24d1e-107">ASP.NET modules and handlers</span></span>

<span data-ttu-id="24d1e-108">Los [módulos http y los controladores http](/troubleshoot/aspnet/http-modules-handlers) son una parte integral de la arquitectura ASP.net.</span><span class="sxs-lookup"><span data-stu-id="24d1e-108">[HTTP modules and HTTP handlers](/troubleshoot/aspnet/http-modules-handlers) are an integral part of the ASP.NET architecture.</span></span> <span data-ttu-id="24d1e-109">Mientras se procesa una solicitud, cada solicitud se procesa mediante varios módulos HTTP (por ejemplo, el módulo de autenticación y el módulo de sesión) y, a continuación, se procesa mediante un único controlador HTTP.</span><span class="sxs-lookup"><span data-stu-id="24d1e-109">While a request is being processed, each request is processed by multiple HTTP modules (for example, the authentication module and the session module) and is then processed by a single HTTP handler.</span></span> <span data-ttu-id="24d1e-110">Una vez que el controlador ha procesado la solicitud, la solicitud vuelve a través de los módulos HTTP.</span><span class="sxs-lookup"><span data-stu-id="24d1e-110">After the handler has processed the request, the request flows back through the HTTP modules.</span></span>

<span data-ttu-id="24d1e-111">Si la aplicación usa módulos http personalizados o controladores HTTP, necesitará un plan para migrarlos a ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="24d1e-111">If your app is using custom HTTP modules or HTTP handlers, you'll need a plan to migrate them to ASP.NET Core.</span></span> <span data-ttu-id="24d1e-112">El reemplazo más probable en ASP.NET Core es middleware.</span><span class="sxs-lookup"><span data-stu-id="24d1e-112">The most likely replacement in ASP.NET Core is middleware.</span></span>

## <a name="aspnet-core-middleware"></a><span data-ttu-id="24d1e-113">Middleware ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="24d1e-113">ASP.NET Core middleware</span></span>

<span data-ttu-id="24d1e-114">ASP.NET Core define una canalización de solicitudes en cada método de la aplicación `Configure` .</span><span class="sxs-lookup"><span data-stu-id="24d1e-114">ASP.NET Core defines a request pipeline in each app's `Configure` method.</span></span> <span data-ttu-id="24d1e-115">Esta canalización de solicitudes define el modo en que la aplicación controla una solicitud de entrada, con cada método de la canalización que llama al método siguiente hasta el momento en que finaliza un método y la cadena de *middleware* finaliza y devuelve la copia de seguridad de la pila.</span><span class="sxs-lookup"><span data-stu-id="24d1e-115">This request pipeline defines how an incoming request is handled by the app, with each method in the pipeline calling the next method until eventually a method terminates, and the chain of *middleware* terminates and returns back up the stack.</span></span> <span data-ttu-id="24d1e-116">El middleware puede tener como destino todas las solicitudes, o bien se puede configurar para que solo se asigne a determinadas solicitudes en función de la ruta de acceso solicitada u otros factores.</span><span class="sxs-lookup"><span data-stu-id="24d1e-116">Middleware can target all requests, or can be configured to only map to certain requests based on the requested path or other factors.</span></span> <span data-ttu-id="24d1e-117">Se puede configurar por completo en el `Configure` método de una aplicación o implementarse en una clase independiente.</span><span class="sxs-lookup"><span data-stu-id="24d1e-117">It can be configured wholly in the `Configure` method of an app, or implemented in a separate class.</span></span>

<span data-ttu-id="24d1e-118">El comportamiento en una aplicación ASP.NET MVC que usa módulos HTTP probablemente es más adecuado para el [middleware personalizado](/aspnet/core/fundamentals/middleware/?preserve-view=true&view=aspnetcore-3.1).</span><span class="sxs-lookup"><span data-stu-id="24d1e-118">Behavior in an ASP.NET MVC app that uses HTTP modules is probably best suited to [custom middleware](/aspnet/core/fundamentals/middleware/?preserve-view=true&view=aspnetcore-3.1).</span></span> <span data-ttu-id="24d1e-119">Los controladores HTTP personalizados se pueden reemplazar por rutas o puntos de conexión personalizados que responden a la misma ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="24d1e-119">Custom HTTP handlers can be replaced with custom routes or endpoints that respond to the same path.</span></span>

## <a name="accessing-httpcontext"></a><span data-ttu-id="24d1e-120">Acceso a HttpContext</span><span class="sxs-lookup"><span data-stu-id="24d1e-120">Accessing HttpContext</span></span>

<span data-ttu-id="24d1e-121">Muchas aplicaciones .NET hacen referencia al contexto de la solicitud actual a través de `HttpContext.Current` .</span><span class="sxs-lookup"><span data-stu-id="24d1e-121">Many .NET apps reference the current request's context through `HttpContext.Current`.</span></span> <span data-ttu-id="24d1e-122">Este acceso estático puede ser una fuente común de problemas con las pruebas y otro uso de código fuera de las solicitudes individuales.</span><span class="sxs-lookup"><span data-stu-id="24d1e-122">This static access can be a common source of problems with testing and other code usage outside of individual requests.</span></span> <span data-ttu-id="24d1e-123">Al compilar ASP.NET Core aplicaciones, el acceso al HttpContext actual se debe proporcionar como un parámetro de método en middleware, como se muestra en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="24d1e-123">When building ASP.NET Core apps, access to the current HttpContext should be provided as a method parameter on middleware, as this sample demonstrates:</span></span>

```csharp
public class Middleware
{
    private readonly RequestDelegate _next;

    public Middleware(RequestDelegate next)
    {
        _next = next;
    }

    public Task Invoke(HttpContext httpContext)
    {
        return _next(httpContext);
    }
}
```

<span data-ttu-id="24d1e-124">Del mismo modo, ASP.NET Core filtros pasan un argumento de contexto a sus métodos, desde los que se puede tener acceso al HttpContext actual:</span><span class="sxs-lookup"><span data-stu-id="24d1e-124">Similarly, ASP.NET Core filters pass a context argument to their methods, from which the current HttpContext can be accessed:</span></span>

```csharp
public class MyActionFilterAttribute : ActionFilterAttribute
{
    public override void OnResultExecuting(ResultExecutingContext context)
    {
        var headers = context.HttpContext.Request.Headers;
        // do something based on a header

        base.OnResultExecuting(context);
    }
}
```

<span data-ttu-id="24d1e-125">Si tiene componentes o servicios que requieren acceso a HttpContext, en lugar de usar una llamada estática como, `HttpContext.Current` debe usar en su lugar la inserción de dependencias del constructor y la interfaz [IHttpContextAccessor](https://docs.microsoft.com/dotnet/api/microsoft.aspnetcore.http.ihttpcontextaccessor) :</span><span class="sxs-lookup"><span data-stu-id="24d1e-125">If you have components or services that require access to HttpContext, rather than using a static call like `HttpContext.Current` you should instead use constructor dependency injection and the [IHttpContextAccessor](https://docs.microsoft.com/dotnet/api/microsoft.aspnetcore.http.ihttpcontextaccessor) interface:</span></span>

```csharp
public class MyService
{
    private readonly IHttpContextAccessor _httpContextAccessor;

    public MyService(IHttpContextAccessor httpContextAccessor)
    {
        _httpContextAccessor = httpContextAccessor;
    }

    public void DoSomething()
    {
        var currentContext = _httpContextAccessor.HttpContext;
    }
}
```

<span data-ttu-id="24d1e-126">Este enfoque elimina el acoplamiento estático del método al contexto actual y proporciona acceso de forma que se pueda probar.</span><span class="sxs-lookup"><span data-stu-id="24d1e-126">This approach eliminates the static coupling of the method to the current context while providing access in a testable fashion.</span></span>

## <a name="references"></a><span data-ttu-id="24d1e-127">Referencias</span><span class="sxs-lookup"><span data-stu-id="24d1e-127">References</span></span>

- [<span data-ttu-id="24d1e-128">ASP.NET módulos http y controladores HTTP</span><span class="sxs-lookup"><span data-stu-id="24d1e-128">ASP.NET HTTP modules and HTTP handlers</span></span>](/troubleshoot/aspnet/http-modules-handlers)
- [<span data-ttu-id="24d1e-129">Middleware ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="24d1e-129">ASP.NET Core middleware</span></span>](/aspnet/core/fundamentals/middleware/?preserve-view=true&view=aspnetcore-3.1)

>[!div class="step-by-step"]
><span data-ttu-id="24d1e-130">[Anterior](dependency-injection-differences.md)
>[Siguiente](configuration-differences.md)</span><span class="sxs-lookup"><span data-stu-id="24d1e-130">[Previous](dependency-injection-differences.md)
[Next](configuration-differences.md)</span></span>
