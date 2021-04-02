---
title: Diferencias de hospedaje entre ASP.NET MVC y ASP.NET Core
description: Información general sobre las diferencias entre cómo se hospedan las aplicaciones ASP.NET MVC en lugar de ASP.NET Core aplicaciones.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 9881a40403f8109fa63e25167b753ed4ce8ade17
ms.sourcegitcommit: b5d2290673e1c91260c9205202dd8b95fbab1a0b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "106122903"
---
# <a name="hosting-differences-between-aspnet-mvc-and-aspnet-core"></a><span data-ttu-id="54c26-103">Diferencias de hospedaje entre ASP.NET MVC y ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="54c26-103">Hosting differences between ASP.NET MVC and ASP.NET Core</span></span>

<span data-ttu-id="54c26-104">Las aplicaciones de ASP.NET MVC se hospedan en IIS y pueden basarse en la configuración de IIS para su comportamiento.</span><span class="sxs-lookup"><span data-stu-id="54c26-104">ASP.NET MVC apps are hosted in IIS, and may rely on IIS configuration for their behavior.</span></span> <span data-ttu-id="54c26-105">A menudo, esto incluye los [módulos de IIS](/iis/get-started/introduction-to-iis/iis-modules-overview).</span><span class="sxs-lookup"><span data-stu-id="54c26-105">This often includes [IIS modules](/iis/get-started/introduction-to-iis/iis-modules-overview).</span></span> <span data-ttu-id="54c26-106">Como parte de la revisión de una aplicación para preparar su portabilidad de ASP.NET MVC a ASP.NET Core, los equipos deben identificar qué módulos, si los hay, están usando en la lista de módulos de IIS instalados en su servidor.</span><span class="sxs-lookup"><span data-stu-id="54c26-106">As part of reviewing an app to prepare to port it from ASP.NET MVC to ASP.NET Core, teams should identify which modules, if any, they're using from the list of IIS Modules installed on their server.</span></span>

<span data-ttu-id="54c26-107">[ASP.net Core aplicaciones se pueden ejecutar en varios servidores diferentes](/aspnet/core/fundamentals/servers/).</span><span class="sxs-lookup"><span data-stu-id="54c26-107">[ASP.NET Core apps can run on a number of different servers](/aspnet/core/fundamentals/servers/).</span></span> <span data-ttu-id="54c26-108">El servidor multiplataforma predeterminado, Kestrel, es una buena opción predeterminada.</span><span class="sxs-lookup"><span data-stu-id="54c26-108">The default cross platform server, Kestrel, is a good default choice.</span></span> <span data-ttu-id="54c26-109">Las aplicaciones que se ejecutan en Kestrel pueden hospedarse en IIS y ejecutarse en un proceso independiente.</span><span class="sxs-lookup"><span data-stu-id="54c26-109">Apps running in Kestrel can be hosted by IIS, running in a separate process.</span></span> <span data-ttu-id="54c26-110">En Windows, las aplicaciones también se pueden ejecutar en proceso en IIS o mediante HTTP.sys.</span><span class="sxs-lookup"><span data-stu-id="54c26-110">On Windows, apps can also run in process on IIS or using HTTP.sys.</span></span> <span data-ttu-id="54c26-111">Suele recomendarse Kestrel para un rendimiento óptimo.</span><span class="sxs-lookup"><span data-stu-id="54c26-111">Kestrel is generally recommended for best performance.</span></span> <span data-ttu-id="54c26-112">HTTP.sys se puede usar en escenarios en los que la aplicación se expone a Internet y las funcionalidades necesarias son compatibles con HTTP.sys pero no con Kestrel.</span><span class="sxs-lookup"><span data-stu-id="54c26-112">HTTP.sys can be used in scenarios where the app is exposed to the Internet and required capabilities are supported by HTTP.sys but not Kestrel.</span></span>

<span data-ttu-id="54c26-113">Kestrel no tiene un equivalente a los módulos de IIS (aunque las aplicaciones hospedadas en IIS pueden seguir aprovechando los módulos de IIS).</span><span class="sxs-lookup"><span data-stu-id="54c26-113">Kestrel does not have an equivalent to IIS modules (though apps hosted in IIS can still take advantage of IIS modules).</span></span> <span data-ttu-id="54c26-114">Para lograr un comportamiento equivalente, normalmente se usa el [middleware](/aspnet/core/fundamentals/middleware/) configurado en la propia aplicación ASP.net Core.</span><span class="sxs-lookup"><span data-stu-id="54c26-114">To achieve equivalent behavior, [middleware](/aspnet/core/fundamentals/middleware/) configured in the ASP.NET Core app itself is typically used.</span></span>

## <a name="references"></a><span data-ttu-id="54c26-115">Referencias</span><span class="sxs-lookup"><span data-stu-id="54c26-115">References</span></span>

- [<span data-ttu-id="54c26-116">Módulos de IIS</span><span class="sxs-lookup"><span data-stu-id="54c26-116">IIS Modules</span></span>](/iis/get-started/introduction-to-iis/iis-modules-overview)
- [<span data-ttu-id="54c26-117">Middleware de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="54c26-117">ASP.NET Core Middleware</span></span>](/aspnet/core/fundamentals/middleware/)
- [<span data-ttu-id="54c26-118">Servidores de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="54c26-118">ASP.NET Core Servers</span></span>](/aspnet/core/fundamentals/servers/)

>[!div class="step-by-step"]
><span data-ttu-id="54c26-119">[Anterior](app-startup-differences.md)
>[Siguiente](serving-static-files.md)</span><span class="sxs-lookup"><span data-stu-id="54c26-119">[Previous](app-startup-differences.md)
[Next](serving-static-files.md)</span></span>
