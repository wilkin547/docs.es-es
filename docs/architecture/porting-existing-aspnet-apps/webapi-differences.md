---
title: Comparar ASP.NET Web API 2 y ASP.NET Core
description: ¿Cómo difieren las API Web entre ASP.NET Web API 2 aplicaciones y aplicaciones de ASP.NET Core?
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 93aa917174bce24fdf924f6372312c3972473289
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401683"
---
# <a name="compare-aspnet-web-api-2-and-aspnet-core"></a>Comparar ASP.NET Web API 2 y ASP.NET Core

ASP.NET Core ofrece mejoras iterativas en ASP.NET Web API 2, pero debe sentirse familiar a los desarrolladores que han usado Web API 2. ASP.NET Web API 2 se desarrolló y se distribuyó junto con ASP.NET MVC. Esto significaba que los dos enfoques tenían enfoques similares, pero diferentes, a aspectos como el enrutamiento de atributos y la inserción de dependencias. En ASP.NET Core, ya no hay ninguna distinción entre MVC y las API Web. Solo hay ASP.NET MVC, que incluye compatibilidad con escenarios basados en la vista, puntos de conexión de API y Razor Pages (y otras variaciones como las comprobaciones de estado y el señalizador).

Además de ser coherente y unificada dentro de ASP.NET Core, las API integradas en .NET Core son mucho más fáciles de probar que las basadas en ASP.NET Web API 2. Trataremos las [diferencias](testing-differences.md) de las pruebas con más detalle en un momento. La compatibilidad integrada con el hospedaje de aplicaciones de ASP.NET Core, en un host de prueba que puede crear un `HttpClient` que realiza solicitudes en memoria en la aplicación, es una gran ventaja en lo que respecta a las pruebas automatizadas.

Al migrar de ASP.NET Web API 2 a ASP.NET Core, la transición es sencilla. Si tiene controladores de gran tamaño, un enfoque que puede considerar dividirlos es el uso de los paquetes de NuGet [Ardalis. ApiEndpoints](https://www.nuget.org/packages/Ardalis.ApiEndpoints/) . Este paquete divide cada punto de conexión en su propia clase específica, con los tipos de solicitud y respuesta asociados, según corresponda. Este enfoque ofrece muchas de [las ventajas que Razor pages oferta en la organización de código basado en vistas](comparing-razor-pages-aspnet-mvc.md).

## <a name="references"></a>Referencias

- [Migrar de ASP.NET Web API a ASP.NET Core](/aspnet/core/migration/webapi)
- [Paquete NuGet Ardalis. ApiEndpoints](https://www.nuget.org/packages/Ardalis.ApiEndpoints/)

>[!div class="step-by-step"]
>[Anterior](comparing-razor-pages-aspnet-mvc.md)
>[Siguiente](authentication-differences.md)
