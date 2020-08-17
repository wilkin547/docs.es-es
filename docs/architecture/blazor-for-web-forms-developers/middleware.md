---
title: Módulos, controladores y middleware
description: Obtenga información sobre cómo controlar las solicitudes HTTP con módulos, controladores y middleware.
author: danroth27
ms.author: daroth
no-loc:
- Blazor
ms.date: 10/11/2019
ms.openlocfilehash: 639755dd78892df1b70ea5245a9584e575fbf691
ms.sourcegitcommit: 0100be20fcf23f61dab672deced70059ed71bb2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2020
ms.locfileid: "88267885"
---
# <a name="modules-handlers-and-middleware"></a>Módulos, controladores y middleware

Una aplicación ASP.NET Core se basa en una serie de *middleware*. El middleware es controladores que se organizan en una canalización para controlar solicitudes y respuestas. En una aplicación de formularios Web Forms, los controladores y módulos HTTP solucionan problemas similares. En ASP.NET Core, los módulos, los controladores, *global.asax.CS*y el ciclo de vida de la aplicación se reemplazan por middleware. En este capítulo, aprenderá qué middleware en el contexto de una Blazor aplicación.

## <a name="overview"></a>Información general

La canalización de solicitudes de ASP.NET Core consiste en una secuencia de delegados de solicitud a los que se llama de uno en uno. En el siguiente diagrama se muestra este concepto. El subproceso de ejecución sigue las flechas negras.

![pipeline](media/middleware/request-delegate-pipeline.png)

El diagrama anterior carece de un concepto de eventos de ciclo de vida. Este concepto es fundamental para el modo en que se administran las solicitudes de formularios Web Forms de ASP.NET. Este sistema facilita la tarea de pensar en qué proceso está ocurriendo y permite insertar middleware en cualquier momento. El middleware se ejecuta en el orden en que se agrega a la canalización de solicitudes. También se agregan en el código en lugar de en los archivos de configuración, normalmente en *Startup.CS*.

## <a name="katana"></a>Katana

Los lectores familiarizados con Katana se sienten cómodos en ASP.NET Core. De hecho, Katana es un marco del que se deriva ASP.NET Core. Se introdujeron patrones similares de middleware y canalización para ASP.NET 4. x. El middleware diseñado para Katana puede adaptarse para trabajar con la canalización de ASP.NET Core.

## <a name="common-middleware"></a>Middleware común

ASP.NET 4. x incluye muchos módulos. De forma similar, ASP.NET Core tiene también muchos componentes de middleware disponibles. En algunos casos, los módulos IIS se pueden usar con ASP.NET Core. En otros casos, puede que el middleware de ASP.NET Core nativo esté disponible.

En la tabla siguiente se enumeran los componentes y el middleware de reemplazo en ASP.NET Core.

|Module                 |Módulo ASP.NET 4. x           |ASP.NET Core, opción|
|-----------------------|-----------------------------|-------------------|
|Errores HTTP            |`CustomErrorModule`          |[Middleware de páginas de códigos de estado](/aspnet/core/fundamentals/error-handling#usestatuscodepages)|
|Documento predeterminado       |`DefaultDocumentModule`      |[Middleware de archivos predeterminados](/aspnet/core/fundamentals/static-files#serve-a-default-document)|
|Examen de directorios     |`DirectoryListingModule`     |[Middleware de exploración de directorios](/aspnet/core/fundamentals/static-files#enable-directory-browsing)|
|Compresión dinámica    |`DynamicCompressionModule`   |[Middleware de compresión de respuestas](/aspnet/core/performance/response-compression)|
|Seguimiento de solicitudes con error|`FailedRequestsTracingModule`|[Registro de ASP.NET Core](/aspnet/core/fundamentals/logging/index#tracesource-provider)|
|Almacenamiento en caché de archivos           |`FileCacheModule`            |[Middleware de almacenamiento en caché de respuestas](/aspnet/core/performance/caching/middleware)|
|Almacenamiento en caché de HTTP           |`HttpCacheModule`            |[Middleware de almacenamiento en caché de respuestas](/aspnet/core/performance/caching/middleware)|
|Registro HTTP           |`HttpLoggingModule`          |[Registro de ASP.NET Core](/aspnet/core/fundamentals/logging/index)|
|Redirección HTTP       |`HttpRedirectionModule`      |[Middleware de reescritura de dirección URL](/aspnet/core/fundamentals/url-rewriting)|
|Filtros ISAPI          |`IsapiFilterModule`          |[Software intermedio](/aspnet/core/fundamentals/middleware/index)|
|ISAPI                  |`IsapiModule`                |[Software intermedio](/aspnet/core/fundamentals/middleware/index)|
|Filtro de solicitudes      |`RequestFilteringModule`     |[Middleware de reescritura de URL IRule](/aspnet/core/fundamentals/url-rewriting#irule-based-rule)|
|&#8224; de reescritura de direcciones URL   |`RewriteModule`              |[Middleware de reescritura de dirección URL](/aspnet/core/fundamentals/url-rewriting)|
|Compresión estática     |`StaticCompressionModule`    |[Middleware de compresión de respuestas](/aspnet/core/performance/response-compression)|
|Contenido estático         |`StaticFileModule`           |[Middleware de archivos estáticos](/aspnet/core/fundamentals/static-files)|
|Autorización para URL      |`UrlAuthorizationModule`     |[Identidad de ASP.NET Core](/aspnet/core/security/authentication/identity)|

Esta lista no es exhaustiva, pero debe dar una idea de la asignación que existe entre los dos marcos. Para obtener una lista más detallada, vea [módulos de IIS con ASP.net Core](/aspnet/core/host-and-deploy/iis/modules).

## <a name="custom-middleware"></a>Middleware personalizado

Es posible que el middleware integrado no controle todos los escenarios necesarios para una aplicación. En tales casos, tiene sentido crear su propio middleware. Hay varias maneras de definir el middleware, siendo la más simple un delegado simple. Considere el siguiente middleware, que acepta una solicitud de referencia cultural de una cadena de consulta:

```csharp
public class Startup
{
    public void Configure(IApplicationBuilder app)
    {
        app.Use(async (context, next) =>
        {
            var cultureQuery = context.Request.Query["culture"];

            if (!string.IsNullOrWhiteSpace(cultureQuery))
            {
                var culture = new CultureInfo(cultureQuery);

                CultureInfo.CurrentCulture = culture;
                CultureInfo.CurrentUICulture = culture;
            }

            // Call the next delegate/middleware in the pipeline
            await next();
        });

        app.Run(async (context) =>
            await context.Response.WriteAsync(
                $"Hello {CultureInfo.CurrentCulture.DisplayName}"));
    }
}
```

El middleware también se puede definir como clase, ya sea implementando la `IMiddleware` interfaz o mediante la siguiente Convención de middleware. Para obtener más información, consulte [escritura de middleware de ASP.net Core personalizado](/aspnet/core/fundamentals/middleware/write).

>[!div class="step-by-step"]
>[Anterior](data.md)
>[Siguiente](config.md)
