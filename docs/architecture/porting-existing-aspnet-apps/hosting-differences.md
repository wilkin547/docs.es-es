---
title: Diferencias de hospedaje entre ASP.NET MVC y ASP.NET Core
description: Información general sobre las diferencias entre cómo se hospedan las aplicaciones ASP.NET MVC en lugar de ASP.NET Core aplicaciones.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 402dd5782cb215545ff2ef13f97ec269b8a2540b
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401767"
---
# <a name="hosting-differences-between-aspnet-mvc-and-aspnet-core"></a>Diferencias de hospedaje entre ASP.NET MVC y ASP.NET Core

Las aplicaciones de ASP.NET MVC se hospedan en IIS y pueden basarse en la configuración de IIS para su comportamiento. A menudo, esto incluye los [módulos de IIS](/iis/get-started/introduction-to-iis/iis-modules-overview). Como parte de la revisión de una aplicación para preparar su portabilidad de ASP.NET MVC a ASP.NET Core, los equipos deben identificar qué módulos, si los hay, están usando en la lista de módulos de IIS instalados en su servidor.

[ASP.net Core aplicaciones se pueden ejecutar en varios servidores diferentes](/aspnet/core/fundamentals/servers/). El servidor multiplataforma predeterminado, Kestrel, es una buena opción predeterminada. Las aplicaciones que se ejecutan en Kestrel pueden hospedarse en IIS y ejecutarse en un proceso independiente. En Windows, las aplicaciones también se pueden ejecutar en proceso en IIS o mediante HTTP.sys. Suele recomendarse Kestrel para un rendimiento óptimo. HTTP.sys se puede usar en escenarios en los que la aplicación se expone a Internet y las funcionalidades necesarias son compatibles con HTTP.sys pero no con Kestrel.

Kestrel no tiene un equivalente a los módulos de IIS (aunque las aplicaciones hospedadas en IIS pueden seguir aprovechando los módulos de IIS). Para lograr un comportamiento equivalente, normalmente se usa el middleware configurado en la propia aplicación ASP.NET Core.

## <a name="references"></a>Referencias

- [Módulos de IIS](/iis/get-started/introduction-to-iis/iis-modules-overview)
- [Servidores de ASP.NET Core](/aspnet/core/fundamentals/servers/)

>[!div class="step-by-step"]
>[Anterior](app-startup-differences.md)
>[Siguiente](serving-static-files.md)
