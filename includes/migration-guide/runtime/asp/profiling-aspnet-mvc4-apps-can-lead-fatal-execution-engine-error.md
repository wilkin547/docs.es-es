---
ms.openlocfilehash: 8b70df0fb2072fd5243d9e46a4a20c22cc7fd677
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "91607802"
---
### <a name="profiling-aspnet-mvc4-apps-can-lead-to-fatal-execution-engine-error"></a>Posible error irrecuperable en el motor de ejecución por parte de las aplicaciones de MVC4 de generación de perfiles de ASP.NET

#### <a name="details"></a>Detalles

Los generadores de perfiles que usan ensamblados /Profile de NGEN pueden bloquear las aplicaciones de MVC4 con perfiles de ASP.NET durante el inicio con una "Excepción irrecuperable de motor de ejecución".

#### <a name="suggestion"></a>Sugerencia

Este problema se ha corregido en .NET Framework 4.5.2. Como alternativa, el generador de perfiles puede evitar este problema mediante la especificación de <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> en su máscara de eventos.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|

#### <a name="affected-apis"></a>API afectadas

No detectable a través del análisis de la API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
