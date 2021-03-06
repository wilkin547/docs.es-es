---
title: Diferencias de inserción de dependencias entre ASP.NET MVC y ASP.NET Core
description: Vea cómo funciona la inserción de dependencias en ASP.NET MVC y ASP.NET Core, cómo se diferencian y cómo migrar de ASP.NET MVC a ASP.NET Core.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: aa1c7dd2f70e1a545352feb6560177bc6e2baa2d
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401779"
---
# <a name="dependency-injection-differences-between-aspnet-mvc-and-aspnet-core"></a>Diferencias de inserción de dependencias entre ASP.NET MVC y ASP.NET Core

Aunque la inserción de dependencias (DI) no está integrada en ASP.NET MVC o Web API, muchas aplicaciones lo habilitan agregando un paquete de NuGet con un contenedor de inversión de control (IOC). A veces se conocen como contenedores de DI, para la inserción de dependencias (o la inversión). Algunos de los contenedores más populares que se usan en las aplicaciones ASP.NET MVC incluyen:

- [Autofac](https://www.autofac.org/)
- [Unity](https://unitycontainer.github.io/)
- [Ninject](http://www.ninject.org/)
- [StructureMap](http://structuremap.github.io/) *(desusado)*
- [Windsor](http://www.castleproject.org/projects/windsor/)

Si la aplicación de ASP.NET MVC no usa DI, probablemente querrá investigar la compatibilidad integrada para DI en ASP.NET Core. DI promueve el acoplamiento flexible de los módulos de la aplicación y permite una mejor prueba y adherencia a principios como [Solid](https://www.weeklydevtips.com/episodes/047).

Si su aplicación usa DI, probablemente la mejor opción es ver si el contenedor que usa es compatible con ASP.NET Core. En ese caso, es posible que pueda seguir utilizándolo y las reglas de configuración personalizadas que describen las asignaciones de tipos y la duración.

En cualquier caso, debe considerar la posibilidad de usar la compatibilidad integrada con DI que se incluye con ASP.NET Core, ya que puede satisfacer las necesidades de su aplicación.

## <a name="dependency-injection-in-aspnet-core"></a>Inserción de dependencias en ASP.NET Core

ASP.NET Core supone que las aplicaciones usarán DI. No está integrado en el marco de trabajo, pero es necesario para proporcionar compatibilidad con las características de .NET Framework en las aplicaciones ASP.NET Core. En el inicio de la aplicación, se realiza una llamada a, `ConfigureServices` que es responsable de registrar todos los tipos que el contenedor de di (colección de servicios o proveedor de servicios) puede crear e insertar en la aplicación. Las características integradas ASP.NET Core como Entity Framework Core, identidad e incluso MVC se incorporan a la aplicación mediante su configuración como servicios en el `ConfigureServices` método.

Además de usar la implementación predeterminada, las aplicaciones pueden seguir usando contenedores personalizados. [En la documentación se explica cómo reemplazar el contenedor de servicios predeterminado](../../core/extensions/dependency-injection-guidelines.md#default-service-container-replacement).

DI es fundamental para ASP.NET Core. Si el equipo ya no está bien en esta práctica, querrá comprenderlo antes de migrar la aplicación.

## <a name="references"></a>Referencias

- [Inserción de dependencias en .NET](../../core/extensions/dependency-injection.md)
- [Inserción de dependencias en ASP.NET Core](/aspnet/core/fundamentals/dependency-injection)

>[!div class="step-by-step"]
>[Anterior](serving-static-files.md)
>[Siguiente](middleware-modules-handlers.md)
