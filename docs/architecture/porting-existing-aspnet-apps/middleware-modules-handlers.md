---
title: Comparar middleware con módulos y controladores
description: En esta sección se analizan las diferencias en la estructura de las aplicaciones de ASP.NET que usan controladores y módulos con ASP.NET Core aplicaciones que definen el middleware para sus canalizaciones de control de solicitudes.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 040ae49d1307ef4dcc9dbf49b20544e9cd2bc913
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401734"
---
# <a name="compare-middleware-to-modules-and-handlers"></a>Comparar middleware con módulos y controladores

Si su aplicación existente de ASP.NET MVC o de API Web usa OWIN/Katana, lo más probable es que ya esté familiarizado con el concepto de middleware y su portabilidad a ASP.NET Core debe ser bastante sencillo. Sin embargo, la mayoría de las aplicaciones ASP.NET dependen de módulos HTTP y controladores HTTP en lugar de middleware. La migración de estos a ASP.NET Core requiere un esfuerzo adicional.

## <a name="aspnet-modules-and-handlers"></a>Módulos y controladores de ASP.NET

Los [módulos http y los controladores http](/troubleshoot/aspnet/http-modules-handlers) son una parte integral de la arquitectura ASP.net. Mientras se procesa una solicitud, cada solicitud se procesa mediante varios módulos HTTP (por ejemplo, el módulo de autenticación y el módulo de sesión) y, a continuación, se procesa mediante un único controlador HTTP. Una vez que el controlador ha procesado la solicitud, la solicitud vuelve a través de los módulos HTTP.

Si la aplicación usa módulos http personalizados o controladores HTTP, necesitará un plan para migrarlos a ASP.NET Core. El reemplazo más probable en ASP.NET Core es middleware.

## <a name="aspnet-core-middleware"></a>Middleware ASP.NET Core

ASP.NET Core define una canalización de solicitudes en cada método de la aplicación `Configure` . Esta canalización de solicitudes define el modo en que la aplicación controla una solicitud de entrada, con cada método de la canalización que llama al método siguiente hasta el momento en que finaliza un método y la cadena de *middleware* finaliza y devuelve la copia de seguridad de la pila. El middleware puede tener como destino todas las solicitudes, o bien se puede configurar para que solo se asigne a determinadas solicitudes en función de la ruta de acceso solicitada u otros factores. Se puede configurar por completo en el `Configure` método de una aplicación o implementarse en una clase independiente.

El comportamiento en una aplicación ASP.NET MVC que usa módulos HTTP probablemente es más adecuado para el [middleware personalizado](/aspnet/core/fundamentals/middleware/?preserve-view=true&view=aspnetcore-3.1). Los controladores HTTP personalizados se pueden reemplazar por rutas o puntos de conexión personalizados que responden a la misma ruta de acceso.

## <a name="references"></a>Referencias

- [ASP.NET módulos http y controladores HTTP](/troubleshoot/aspnet/http-modules-handlers)
- [Middleware ASP.NET Core](/aspnet/core/fundamentals/middleware/?preserve-view=true&view=aspnetcore-3.1)

>[!div class="step-by-step"]
>[Anterior](dependency-injection-differences.md)
>[Siguiente](configuration-differences.md)
