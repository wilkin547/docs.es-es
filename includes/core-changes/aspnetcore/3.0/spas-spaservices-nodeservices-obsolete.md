---
ms.openlocfilehash: ac5a3c4f3aefbb59418ad92b2d795f36916f877f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394103"
---
### <a name="spas-spaservices-and-nodeservices-marked-obsolete"></a><span data-ttu-id="7f198-101">SPA: SpaServices y NodeServices se han marcado como obsoletos</span><span class="sxs-lookup"><span data-stu-id="7f198-101">SPAs: SpaServices and NodeServices marked obsolete</span></span>

<span data-ttu-id="7f198-102">El contenido de los siguientes paquetes NuGet no es necesario a partir de ASP.NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="7f198-102">The contents of the following NuGet packages have all been unnecessary since ASP.NET Core 2.1.</span></span> <span data-ttu-id="7f198-103">Por lo tanto, los paquetes siguientes se marcan como obsoletos:</span><span class="sxs-lookup"><span data-stu-id="7f198-103">Consequently, the following packages are being marked as obsolete:</span></span>

- [<span data-ttu-id="7f198-104">Microsoft.AspNetCore.SpaServices</span><span class="sxs-lookup"><span data-stu-id="7f198-104">Microsoft.AspNetCore.SpaServices</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.SpaServices/)
- [<span data-ttu-id="7f198-105">Microsoft.AspNetCore.NodeServices</span><span class="sxs-lookup"><span data-stu-id="7f198-105">Microsoft.AspNetCore.NodeServices</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.NodeServices/)

<span data-ttu-id="7f198-106">Por el mismo motivo, los módulos siguientes npm se han marcado como en desuso:</span><span class="sxs-lookup"><span data-stu-id="7f198-106">For the same reason, the following npm modules are being marked as deprecated:</span></span>

- [<span data-ttu-id="7f198-107">aspnet-angular</span><span class="sxs-lookup"><span data-stu-id="7f198-107">aspnet-angular</span></span>](https://www.npmjs.com/package/aspnet-angular)
- [<span data-ttu-id="7f198-108">aspnet-prerendering</span><span class="sxs-lookup"><span data-stu-id="7f198-108">aspnet-prerendering</span></span>](https://www.npmjs.com/package/aspnet-prerendering)
- [<span data-ttu-id="7f198-109">aspnet-webpack</span><span class="sxs-lookup"><span data-stu-id="7f198-109">aspnet-webpack</span></span>](https://www.npmjs.com/package/aspnet-webpack)
- [<span data-ttu-id="7f198-110">aspnet-webpack-react</span><span class="sxs-lookup"><span data-stu-id="7f198-110">aspnet-webpack-react</span></span>](https://www.npmjs.com/package/aspnet-webpack-react)
- [<span data-ttu-id="7f198-111">domain-task</span><span class="sxs-lookup"><span data-stu-id="7f198-111">domain-task</span></span>](https://www.npmjs.com/package/domain-task)

<span data-ttu-id="7f198-112">Los paquetes y módulos npm anteriores se quitarán más adelante en .NET 5.</span><span class="sxs-lookup"><span data-stu-id="7f198-112">The preceding packages and npm modules will later be removed in .NET 5.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="7f198-113">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="7f198-113">Version introduced</span></span>

<span data-ttu-id="7f198-114">3.0</span><span class="sxs-lookup"><span data-stu-id="7f198-114">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="7f198-115">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="7f198-115">Old behavior</span></span>

<span data-ttu-id="7f198-116">Los paquetes y módulos npm en desuso se diseñaron para integrar ASP.NET Core con varios marcos de aplicación de página única (SPA).</span><span class="sxs-lookup"><span data-stu-id="7f198-116">The deprecated packages and npm modules were intended to integrate ASP.NET Core with various Single-Page App (SPA) frameworks.</span></span> <span data-ttu-id="7f198-117">Estos marcos incluyen React, and React con Redux.</span><span class="sxs-lookup"><span data-stu-id="7f198-117">Such frameworks include Angular, React, and React with Redux.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="7f198-118">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="7f198-118">New behavior</span></span>

<span data-ttu-id="7f198-119">Existe un nuevo mecanismo de integración en el paquete de NuGet [Microsoft.AspNetCore.SpaServices.Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.SpaServices.Extensions/).</span><span class="sxs-lookup"><span data-stu-id="7f198-119">A new integration mechanism exists in the [Microsoft.AspNetCore.SpaServices.Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.SpaServices.Extensions/) NuGet package.</span></span> <span data-ttu-id="7f198-120">El paquete sigue siendo la base de las plantillas de proyecto Angular y React a partir de ASP.NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="7f198-120">The package remains the basis of the Angular and React project templates since ASP.NET Core 2.1.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="7f198-121">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="7f198-121">Reason for change</span></span>

<span data-ttu-id="7f198-122">ASP.NET Core admite la integración con varios marcos de aplicación de página única (SPA), como Angular, React y React con Redux.</span><span class="sxs-lookup"><span data-stu-id="7f198-122">ASP.NET Core supports integration with various Single-Page App (SPA) frameworks, including Angular, React, and React with Redux.</span></span> <span data-ttu-id="7f198-123">Inicialmente, la integración con estos marcos se logró con componentes específicos de ASP.NET Core que administraban escenarios como la representación previa y la integración del lado servidor con Webpack.</span><span class="sxs-lookup"><span data-stu-id="7f198-123">Initially, integration with these frameworks was accomplished with ASP.NET Core-specific components that handled scenarios like server-side prerendering and integration with Webpack.</span></span> <span data-ttu-id="7f198-124">Con el paso del tiempo, los estándares del sector cambiaron.</span><span class="sxs-lookup"><span data-stu-id="7f198-124">As time went on, industry standards changed.</span></span> <span data-ttu-id="7f198-125">Cada uno de los marcos de SPA lanzó sus propias interfaces de línea de comandos estándar.</span><span class="sxs-lookup"><span data-stu-id="7f198-125">Each of the SPA frameworks released their own standard command-line interfaces.</span></span> <span data-ttu-id="7f198-126">Por ejemplo, la CLI de Angular y create-react-app.</span><span class="sxs-lookup"><span data-stu-id="7f198-126">For example, Angular CLI and create-react-app.</span></span>

<span data-ttu-id="7f198-127">Cuando se publicó ASP.NET Core 2.1 en mayo de 2018, el equipo respondió al cambio en los estándares.</span><span class="sxs-lookup"><span data-stu-id="7f198-127">When ASP.NET Core 2.1 was released in May 2018, the team responded to the change in standards.</span></span> <span data-ttu-id="7f198-128">Se proporcionó una manera más nueva y sencilla de integrarse con las cadenas de herramientas propias de los marcos de SPA.</span><span class="sxs-lookup"><span data-stu-id="7f198-128">A newer and simpler way to integrate with the SPA frameworks' own toolchains was provided.</span></span> <span data-ttu-id="7f198-129">El nuevo mecanismo de integración existe en el paquete `Microsoft.AspNetCore.SpaServices.Extensions` y sigue siendo la base de las plantillas de proyecto Angular y React a partir de ASP.NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="7f198-129">The new integration mechanism exists in the package `Microsoft.AspNetCore.SpaServices.Extensions` and remains the basis of the Angular and React project templates since ASP.NET Core 2.1.</span></span>

<span data-ttu-id="7f198-130">Para aclarar que los componentes específicos de ASP.NET Core antiguos son irrelevantes y no se recomiendan, se realizan las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="7f198-130">To clarify that the older ASP.NET Core-specific components are irrelevant and not recommended:</span></span>

- <span data-ttu-id="7f198-131">El mecanismo de integración anterior a la versión 2.1 está marcado como obsoleto.</span><span class="sxs-lookup"><span data-stu-id="7f198-131">The pre-2.1 integration mechanism is marked as obsolete.</span></span>
- <span data-ttu-id="7f198-132">Los paquetes npm compatibles se marcan como en desuso.</span><span class="sxs-lookup"><span data-stu-id="7f198-132">The supporting npm packages are marked as deprecated.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="7f198-133">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="7f198-133">Recommended action</span></span>

<span data-ttu-id="7f198-134">Si usa estos paquetes, actualice las aplicaciones para usar la funcionalidad:</span><span class="sxs-lookup"><span data-stu-id="7f198-134">If you're using these packages, update your apps to use the functionality:</span></span>

- <span data-ttu-id="7f198-135">En el paquete `Microsoft.AspNetCore.SpaServices.Extensions`.</span><span class="sxs-lookup"><span data-stu-id="7f198-135">In the `Microsoft.AspNetCore.SpaServices.Extensions` package.</span></span>
- <span data-ttu-id="7f198-136">Que proporcionan los marcos de SPA que está usando.</span><span class="sxs-lookup"><span data-stu-id="7f198-136">Provided by the SPA frameworks you're using</span></span>

<span data-ttu-id="7f198-137">Para habilitar características como la representación previa del lado servidor y la recarga de módulos frecuentes, consulte la documentación del marco de SPA correspondiente.</span><span class="sxs-lookup"><span data-stu-id="7f198-137">To enable features like server-side prerendering and hot module reload, see the documentation for the corresponding SPA framework.</span></span> <span data-ttu-id="7f198-138">La funcionalidad de `Microsoft.AspNetCore.SpaServices.Extensions`*no* está obsoleta y seguirá siendo compatible.</span><span class="sxs-lookup"><span data-stu-id="7f198-138">The functionality in `Microsoft.AspNetCore.SpaServices.Extensions` is *not* obsolete and will continue to be supported.</span></span>

#### <a name="category"></a><span data-ttu-id="7f198-139">Categoría</span><span class="sxs-lookup"><span data-stu-id="7f198-139">Category</span></span>

<span data-ttu-id="7f198-140">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7f198-140">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="7f198-141">API afectadas</span><span class="sxs-lookup"><span data-stu-id="7f198-141">Affected APIs</span></span>

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
