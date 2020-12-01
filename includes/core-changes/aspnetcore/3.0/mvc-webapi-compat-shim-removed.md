---
ms.openlocfilehash: 75945e7ff26c1c6db891d12cef4c16ed210da6af
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032842"
---
### <a name="mvc-web-api-compatibility-shim-removed"></a>MVC: se han quitado las correcciones de compatibilidad (shim) con la API web

A partir de ASP.NET Core 3.0, el paquete `Microsoft.AspNetCore.Mvc.WebApiCompatShim` ya no está disponible.

#### <a name="change-description"></a>Descripción del cambio

El paquete `Microsoft.AspNetCore.Mvc.WebApiCompatShim` (WebApiCompatShim) proporciona compatibilidad parcial en ASP.NET Core con ASP.NET 4.x Web API 2 para simplificar la migración de implementaciones existentes de API web a ASP.NET Core. Pero las aplicaciones que usan WebApiCompatShim no se benefician de las características relacionadas con la API que se distribuyen en versiones recientes de ASP.NET Core. Estas características incluyen la generación mejorada de especificaciones de Open API, el control de errores estandarizado y la generación de código de cliente. Para centrar mejor los esfuerzos de API en la versión 3.0, se ha quitado WebApiCompatShim. Las aplicaciones existentes en las que se usa WebApiCompatShim se deben migrar al modelo de `[ApiController]` más reciente.

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="reason-for-change"></a>Motivo del cambio

La corrección de compatibilidad (shim) de la API web era una herramienta de migración. Restringe el acceso de los usuarios a la nueva funcionalidad agregada en ASP.NET Core.

#### <a name="recommended-action"></a>Acción recomendada

Quite el uso de esta corrección de compatibilidad y migre directamente a la funcionalidad similar en ASP.NET Core.

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

<xref:Microsoft.AspNetCore.Mvc.WebApiCompatShim?displayProperty=fullName>

<!--

#### Affected APIs

N:Microsoft.AspNetCore.Mvc.WebApiCompatShim

-->
