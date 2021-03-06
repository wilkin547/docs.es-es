---
title: Comparar controladores en ASP.NET MVC y ASP.NET Core
description: ASP.NET Core controladores MVC son similares a los controladores ASP.NET MVC 5 y Web API 2, pero hay diferencias importantes. En esta sección se examinan las diferencias y los pasos necesarios para migrar aplicaciones de ASP.NET MVC y Web API 2 a ASP.NET Core.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 2c2b7b848162a6ab9901ac9f7779787e2cc994ce
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401782"
---
# <a name="compare-controllers-in-aspnet-mvc-and-web-api-with-controllers-in-aspnet-core"></a>Comparar controladores en ASP.NET MVC y Web API con controladores en ASP.NET Core

En ASP.NET MVC 5 y Web API 2, había dos `Controller` tipos base diferentes. Controladores MVC heredados de `Controller` ; Controladores de API Web heredados de `ApiController` . En ASP.NET Core, esta jerarquía de objetos se ha combinado. Se recomienda que los controladores de API de ASP.NET Core hereden de `ControllerBase` y agreguen el `[ApiController]` atributo. Los controladores MVC basados en la vista estándar deben heredar de `Controller` .

En ambos marcos, los controladores se usan para organizar conjuntos de métodos de acción. Los filtros y las rutas se pueden aplicar en un nivel de controlador además de en el nivel de acción. Estas convenciones se pueden ampliar aún más mediante el uso de tipos base personalizados `Controller` con el comportamiento predeterminado y los atributos que se les aplican.

En ASP.NET MVC, no se admite la negociación de contenido. ASP.NET Web API 2 admite la negociación de contenido, como hace ASP.NET Core. Mediante el uso de la [negociación de contenido](/aspnet/core/web-api/advanced/formatting), el formato del contenido devuelto a una solicitud se puede determinar mediante encabezados que el cliente proporciona para indicar su manera preferida de recibir el contenido.

Al migrar controladores de ASP.NET Web API a ASP.NET Core, es necesario cambiar algunos componentes si existen. Entre ellas se incluyen las referencias a la `ApiController` clase base, el `System.Web.Http` espacio de nombres y la `IHttpActionResult` interfaz. Consulte la [documentación para obtener recomendaciones sobre cómo migrar estas diferencias específicas](/aspnet/core/migration/webapi). Tenga en cuenta que el tipo de valor devuelto preferido para las acciones de API en ASP.NET Core es `ActionResult<T>` .

Además, el `[ChildActionOnly]` atributo no se admite en ASP.net Core. En ASP.NET Core, se consigue una funcionalidad similar con [los componentes de vista](/aspnet/core/mvc/views/view-components).

ASP.NET Core incluye dos nuevos atributos: [ConsumesAttribute](/dotnet/api/microsoft.aspnetcore.mvc.consumesattribute) y [ProducesAttribute](/dotnet/api/microsoft.aspnetcore.mvc.producesattribute). Se usan para especificar el tipo que una acción consume o genera, lo que puede ser útil para el enrutamiento y la documentación de la API mediante herramientas como [Swagger/OpenAPI](/aspnet/core/tutorials/web-api-help-pages-using-swagger).

## <a name="references"></a>Referencias

- [Aplicación de formato a datos de respuesta en ASP.NET Core Web API](/aspnet/core/web-api/advanced/formatting)
- [Migrar de ASP.NET Web API a ASP.NET Core](/aspnet/core/migration/webapi)

>[!div class="step-by-step"]
>[Anterior](identity-differences.md)
>[Siguiente](razor-differences.md)
