---
ms.openlocfilehash: e450c53008e7562e37518fdfd6872ff9b63b6ac3
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "91609144"
---
### <a name="sharing-session-state-with-aspnet-stateserver-requires-all-servers-in-the-web-farm-to-use-the-same-net-framework-version"></a>Compartir el estado de sesión con StateServer de ASP.NET requiere que todos los servidores de la granja de servidores web usen la misma versión de .NET Framework

#### <a name="details"></a>Detalles

Al habilitar el estado de sesión <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=fullName>, todos los servidores de la granja de servidores web indicada deben usar la misma versión de .NET Framework para que el estado se comparta correctamente.

#### <a name="suggestion"></a>Sugerencia

Asegúrese de actualizar las versiones de .NET Framework en los servidores web que compartan el estado al mismo tiempo.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=nameWithType>

<!--

#### Affected APIs

- `F:System.Web.SessionState.SessionStateMode.StateServer`

-->
