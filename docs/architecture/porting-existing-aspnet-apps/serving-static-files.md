---
title: Servir archivos estáticos en ASP.NET MVC y ASP.NET Core
description: ¿Qué implica configurar la compatibilidad para servir archivos estáticos en ASP.NET Core, en comparación con ASP.NET MVC en IIS?
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 02f84a6985835502c24db8cc68db24c8de086b18
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401701"
---
# <a name="serve-static-files-in-aspnet-mvc-and-aspnet-core"></a>Servir archivos estáticos en ASP.NET MVC y ASP.NET Core

La mayoría de las aplicaciones Web implican una combinación de lógica del lado servidor y archivos estáticos que se deben enviar al cliente tal cual. ¿Cómo debe la migración de ASP.NET MVC a ASP.NET Core controlar el servicio de archivos estáticos?

## <a name="host-static-files-in-aspnet-mvc"></a>Hospede archivos estáticos en ASP.NET MVC

Las aplicaciones MVC de ASP.NET, hospedadas por IIS, suelen hospedar archivos estáticos directamente desde la aplicación. ASP.NET MVC admite la colocación de archivos estáticos en paralelo con archivos que deben mantenerse privados en el servidor. IIS y ASP.NET requieren que se restrinja explícitamente ciertos archivos o extensiones de archivo para que se puedan atender desde la carpeta en la que se hospeda una aplicación de ASP.NET.

En el caso de muchos archivos estáticos, se recomienda usar una red de entrega de contenido (CDN). El [hospedaje de contenido estático](/azure/architecture/patterns/static-content-hosting) permite mejorar el rendimiento y reducir la carga y el ancho de banda de los servidores de aplicaciones.

## <a name="host-static-files-in-aspnet-core"></a>Hospedar archivos estáticos en ASP.NET Core

Puede ser sorprendente, pero ASP.NET Core no tiene compatibilidad integrada para archivos estáticos. Esta característica que siempre existía como parte de ASP.NET, habilitada por IIS, no es intrínseca a ASP.NET Core o su servidor Web Kestrel. Para servir archivos estáticos desde una aplicación ASP.NET Core, debe configurar el [middleware de archivos estáticos](/aspnet/core/fundamentals/static-files).

Con el middleware de archivos estáticos configurado, una aplicación ASP.NET Core atenderá a todos los archivos ubicados en una determinada carpeta (normalmente */wwwroot*). Ningún otro archivo de la carpeta de aplicación o de proyecto corre el riesgo de que el servidor lo exponga accidentalmente. No es necesario configurar ninguna restricción especial basada en nombres de archivo o extensiones, como sucede con IIS. En su lugar, los programadores eligen explícitamente exponer los archivos públicamente cuando los colocan en la carpeta *wwwroot* . De forma predeterminada, los archivos que están fuera de esta carpeta no se comparten.

Dado que la compatibilidad con los archivos estáticos usa middleware, cualquier otro middleware puede aplicarse como parte de la misma canalización de solicitudes. Algunos ejemplos de middleware son la autenticación, el almacenamiento en caché y la compresión.

Por supuesto, las redes CDN siguen siendo una buena elección para las aplicaciones ASP.NET Core por todas las mismas razones que se usan en las aplicaciones MVC de ASP.NET. Como parte de la preparación para migrar a .NET Core, si hay ventajas que la aplicación podría obtener al usar una red CDN, sería conveniente trasladar los archivos estáticos a una red CDN antes de migrar a .NET Core. Al hacerlo, se reduce el ámbito general del trabajo de migración para los recursos estáticos.

## <a name="references"></a>Referencias

- [Hospedaje de contenido estático](/azure/architecture/patterns/static-content-hosting)
- [Archivos estáticos en ASP.NET Core](/aspnet/core/fundamentals/static-files)

>[!div class="step-by-step"]
>[Anterior](hosting-differences.md)
>[Siguiente](dependency-injection-differences.md)
