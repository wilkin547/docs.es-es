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
# <a name="hosting-differences-between-aspnet-mvc-and-aspnet-core"></a>Diferencias de hospedaje entre ASP.NET MVC y ASP.NET Core

Las aplicaciones de ASP.NET MVC se hospedan en IIS y pueden basarse en la configuración de IIS para su comportamiento. A menudo, esto incluye los [módulos de IIS](/iis/get-started/introduction-to-iis/iis-modules-overview). Como parte de la revisión de una aplicación para preparar su portabilidad de ASP.NET MVC a ASP.NET Core, los equipos deben identificar qué módulos, si los hay, están usando en la lista de módulos de IIS instalados en su servidor.

[ASP.net Core aplicaciones se pueden ejecutar en varios servidores diferentes](/aspnet/core/fundamentals/servers/). El servidor multiplataforma predeterminado, Kestrel, es una buena opción predeterminada. Las aplicaciones que se ejecutan en Kestrel pueden hospedarse en IIS y ejecutarse en un proceso independiente. En Windows, las aplicaciones también se pueden ejecutar en proceso en IIS o mediante HTTP.sys. Suele recomendarse Kestrel para un rendimiento óptimo. HTTP.sys se puede usar en escenarios en los que la aplicación se expone a Internet y las funcionalidades necesarias son compatibles con HTTP.sys pero no con Kestrel.

Kestrel no tiene un equivalente a los módulos de IIS (aunque las aplicaciones hospedadas en IIS pueden seguir aprovechando los módulos de IIS). Para lograr un comportamiento equivalente, normalmente se usa el [middleware](/aspnet/core/fundamentals/middleware/) configurado en la propia aplicación ASP.net Core.

## <a name="references"></a>Referencias

- [Módulos de IIS](/iis/get-started/introduction-to-iis/iis-modules-overview)
- [Middleware de ASP.NET Core](/aspnet/core/fundamentals/middleware/)
- [Servidores de ASP.NET Core](/aspnet/core/fundamentals/servers/)

>[!div class="step-by-step"]
>[Anterior](app-startup-differences.md)
>[Siguiente](serving-static-files.md)
