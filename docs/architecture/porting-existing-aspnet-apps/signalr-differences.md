---
title: Comparación de ASP.NET Signalr y ASP.NET Core Signalr
description: ¿Cómo difiere ASP.NET Core Signalr de su predecesor, ASP.NET Signalr?
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 4a8680d8a28faaa07687b2c5835ebbf428032fbe
ms.sourcegitcommit: b5d2290673e1c91260c9205202dd8b95fbab1a0b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "106122658"
---
# <a name="compare-aspnet-signalr-and-aspnet-core-signalr"></a>Comparación de ASP.NET Signalr y ASP.NET Core Signalr

ASP.NET Core Signalr no es compatible con clientes o servidores que usan ASP.NET Signalr. Tendrá que actualizar los clientes y el servidor para usar ASP.NET Core Signalr. En esta sección se describen algunas diferencias, mientras que la lista completa está disponible en los [documentos](/aspnet/core/signalr/version-differences). ASP.NET Core Signalr requiere .NET Core 2,1 o superior.

## <a name="feature-differences"></a>Diferencias de características

- ASP.NET Signalr intenta volver a conectar automáticamente las conexiones quitadas. Este comportamiento es opcional para los clientes de Signalr ASP.NET Core
- Ambos marcos admiten JSON; ASP.NET Core Signalr también admite un protocolo binario basado en MessagePack y se pueden crear protocolos personalizados.
- El transporte de tramas Forever, admitido por ASP.NET Signalr, no se admite en ASP.NET Core Signalr.
- ASP.NET Core Signalr se debe configurar agregando `services.AddSignalR()` y `app.UseEndpoints` en `Startup.ConfigureServices` y `Startup.Configure` , respectivamente.
- ASP.NET Core Signalr requiere sesiones permanentes; ASP.NET Signalr no.
- ASP.NET Core simplifica el modelo de conexión; las conexiones solo se realizan en un solo concentrador.
- ASP.NET Core Signalr admite el streaming de datos del concentrador al cliente.
- ASP.NET Core Signalr no admite pasar el estado entre los clientes y el concentrador (pero las llamadas a métodos siguen permitiendo el paso de información entre los concentradores y los clientes).
- La `PersistentConnection` clase no existe en ASP.net Core signalr.
- ASP.NET Signalr admite SQL Server y Redis. ASP.NET Core Signalr es compatible con [Azure signalr](/azure/azure-signalr/) y Redis.

## <a name="references"></a>Referencias

- [Diferencias entre ASP.NET Signalr y ASP.NET Core Signalr](/aspnet/core/signalr/version-differences)
- [Servicio Azure SignalR](/azure/azure-signalr/)

>[!div class="step-by-step"]
>[Anterior](razor-differences.md)
>[Siguiente](testing-differences.md)
