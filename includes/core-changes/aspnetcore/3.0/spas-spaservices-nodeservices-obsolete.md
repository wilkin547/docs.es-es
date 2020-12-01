---
ms.openlocfilehash: ac5a3c4f3aefbb59418ad92b2d795f36916f877f
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032900"
---
### <a name="spas-spaservices-and-nodeservices-marked-obsolete"></a>SPA: SpaServices y NodeServices se han marcado como obsoletos

El contenido de los siguientes paquetes NuGet no es necesario a partir de ASP.NET Core 2.1. Por lo tanto, los paquetes siguientes se marcan como obsoletos:

- [Microsoft.AspNetCore.SpaServices](https://www.nuget.org/packages/Microsoft.AspNetCore.SpaServices/)
- [Microsoft.AspNetCore.NodeServices](https://www.nuget.org/packages/Microsoft.AspNetCore.NodeServices/)

Por el mismo motivo, los módulos siguientes npm se han marcado como en desuso:

- [aspnet-angular](https://www.npmjs.com/package/aspnet-angular)
- [aspnet-prerendering](https://www.npmjs.com/package/aspnet-prerendering)
- [aspnet-webpack](https://www.npmjs.com/package/aspnet-webpack)
- [aspnet-webpack-react](https://www.npmjs.com/package/aspnet-webpack-react)
- [domain-task](https://www.npmjs.com/package/domain-task)

Los paquetes y módulos npm anteriores se quitarán más adelante en .NET 5.

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="old-behavior"></a>Comportamiento anterior

Los paquetes y módulos npm en desuso se diseñaron para integrar ASP.NET Core con varios marcos de aplicación de página única (SPA). Estos marcos incluyen React, and React con Redux.

#### <a name="new-behavior"></a>Comportamiento nuevo

Existe un nuevo mecanismo de integración en el paquete de NuGet [Microsoft.AspNetCore.SpaServices.Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.SpaServices.Extensions/). El paquete sigue siendo la base de las plantillas de proyecto Angular y React a partir de ASP.NET Core 2.1.

#### <a name="reason-for-change"></a>Motivo del cambio

ASP.NET Core admite la integración con varios marcos de aplicación de página única (SPA), como Angular, React y React con Redux. Inicialmente, la integración con estos marcos se logró con componentes específicos de ASP.NET Core que administraban escenarios como la representación previa y la integración del lado servidor con Webpack. Con el paso del tiempo, los estándares del sector cambiaron. Cada uno de los marcos de SPA lanzó sus propias interfaces de línea de comandos estándar. Por ejemplo, la CLI de Angular y create-react-app.

Cuando se publicó ASP.NET Core 2.1 en mayo de 2018, el equipo respondió al cambio en los estándares. Se proporcionó una manera más nueva y sencilla de integrarse con las cadenas de herramientas propias de los marcos de SPA. El nuevo mecanismo de integración existe en el paquete `Microsoft.AspNetCore.SpaServices.Extensions` y sigue siendo la base de las plantillas de proyecto Angular y React a partir de ASP.NET Core 2.1.

Para aclarar que los componentes específicos de ASP.NET Core antiguos son irrelevantes y no se recomiendan, se realizan las acciones siguientes:

- El mecanismo de integración anterior a la versión 2.1 está marcado como obsoleto.
- Los paquetes npm compatibles se marcan como en desuso.

#### <a name="recommended-action"></a>Acción recomendada

Si usa estos paquetes, actualice las aplicaciones para usar la funcionalidad:

- En el paquete `Microsoft.AspNetCore.SpaServices.Extensions`.
- Que proporcionan los marcos de SPA que está usando.

Para habilitar características como la representación previa del lado servidor y la recarga de módulos frecuentes, consulte la documentación del marco de SPA correspondiente. La funcionalidad de `Microsoft.AspNetCore.SpaServices.Extensions`*no* está obsoleta y seguirá siendo compatible.

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

- <xref:Microsoft.AspNetCore.Builder.SpaRouteExtensions?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Builder.WebpackDevMiddleware?displayProperty=nameWithType>

- <xref:Microsoft.AspNetCore.NodeServices.EmbeddedResourceReader?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.INodeServices?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.NodeServicesFactory?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.NodeServicesOptions?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.StringAsTempFile?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.HostingModels.INodeInstance?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.HostingModels.NodeInvocationException?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.HostingModels.NodeInvocationInfo?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.HostingModels.NodeServicesOptionsExtensions?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.HostingModels.OutOfProcessNodeInstance?displayProperty=nameWithType>

- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.ISpaPrerenderer?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.ISpaPrerendererBuilder?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.JavaScriptModuleExport?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.Prerenderer?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.PrerenderTagHelper?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.RenderToStringResult?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Webpack.WebpackDevMiddlewareOptions?displayProperty=nameWithType>

- <xref:Microsoft.Extensions.DependencyInjection.NodeServicesServiceCollectionExtensions?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.DependencyInjection.PrerenderingServiceCollectionExtensions?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:Microsoft.AspNetCore.Builder.SpaRouteExtensions`
- `T:Microsoft.AspNetCore.Builder.WebpackDevMiddleware`

- `T:Microsoft.AspNetCore.NodeServices.EmbeddedResourceReader`
- `T:Microsoft.AspNetCore.NodeServices.INodeServices`
- `T:Microsoft.AspNetCore.NodeServices.NodeServicesFactory`
- `T:Microsoft.AspNetCore.NodeServices.NodeServicesOptions`
- `T:Microsoft.AspNetCore.NodeServices.StringAsTempFile`
- `T:Microsoft.AspNetCore.NodeServices.HostingModels.INodeInstance`
- `T:Microsoft.AspNetCore.NodeServices.HostingModels.NodeInvocationException`
- `T:Microsoft.AspNetCore.NodeServices.HostingModels.NodeInvocationInfo`
- `T:Microsoft.AspNetCore.NodeServices.HostingModels.NodeServicesOptionsExtensions`
- `T:Microsoft.AspNetCore.NodeServices.HostingModels.OutOfProcessNodeInstance`

- `T:Microsoft.AspNetCore.SpaServices.Prerendering.ISpaPrerenderer`
- `T:Microsoft.AspNetCore.SpaServices.Prerendering.ISpaPrerendererBuilder`
- `T:Microsoft.AspNetCore.SpaServices.Prerendering.JavaScriptModuleExport`
- `T:Microsoft.AspNetCore.SpaServices.Prerendering.Prerenderer`
- `T:Microsoft.AspNetCore.SpaServices.Prerendering.PrerenderTagHelper`
- `T:Microsoft.AspNetCore.SpaServices.Prerendering.RenderToStringResult`
- `T:Microsoft.AspNetCore.SpaServices.Webpack.WebpackDevMiddlewareOptions`

- `T:Microsoft.Extensions.DependencyInjection.NodeServicesServiceCollectionExtensions`
- `T:Microsoft.Extensions.DependencyInjection.PrerenderingServiceCollectionExtensions`

-->
