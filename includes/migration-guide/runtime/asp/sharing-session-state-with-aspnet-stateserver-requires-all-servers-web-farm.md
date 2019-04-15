---
ms.openlocfilehash: 958a89015420ce5632d596688963d576c40b4cb6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235853"
---
### <a name="sharing-session-state-with-aspnet-stateserver-requires-all-servers-in-the-web-farm-to-use-the-same-net-framework-version"></a>Compartir el estado de sesión con StateServer de ASP.NET requiere que todos los servidores de la granja de servidores web usen la misma versión de .NET Framework

|   |   |
|---|---|
|Detalles|Al habilitar el estado de sesión <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=name>, todos los servidores de la granja de servidores web indicada deben usar la misma versión de .NET Framework para que el estado se comparta correctamente.|
|Sugerencia|Asegúrese de actualizar las versiones de .NET Framework en los servidores web que compartan el estado al mismo tiempo.|
|Ámbito|Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=nameWithType></li></ul>|
