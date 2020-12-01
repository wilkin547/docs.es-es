---
ms.openlocfilehash: b0e1d6d720a1c9b827fb4585606e64b545d395d7
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032813"
---
### <a name="kestrel-request-trailer-headers-moved-to-new-collection"></a>Kestrel: se han movido los encabezados de finalizador de solicitud a una nueva recopilación

En versiones anteriores, Kestrel agregaba encabezados de finalizador fragmentados de HTTP/1.1 en la recopilación de encabezados de solicitud cuando el cuerpo de la solicitud se leía al final. Este comportamiento provocó problemas de ambigüedad entre encabezados y finalizadores. Se tomó la decisión de mover los finalizadores a una nueva recopilación.

Los finalizadores de solicitudes HTTP/2 no estaban disponibles en ASP.NET Core 2.2, pero ahora también están disponibles en esta nueva recopilación en ASP.NET Core 3.0.

Se han agregado métodos nuevos de extensión de solicitud para tener acceso a estos finalizadores.

Los finalizadores de HTTP/1.1 están disponibles una vez que se ha leído todo el cuerpo de la solicitud.

Los finalizadores de HTTP/2 están disponibles una vez que se han recibido del cliente. El cliente no enviará los finalizadores hasta que el servidor haya almacenado en búfer como mínimo el cuerpo de la solicitud completo. Es posible que deba leer el cuerpo de la solicitud para liberar espacio en búfer. Los finalizadores siempre están disponibles si lee el cuerpo de la solicitud hasta el final. Los finalizadores marcan el final del cuerpo.

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="old-behavior"></a>Comportamiento anterior

Los encabezados de finalizador de solicitud se agregarán a la recopilación `HttpRequest.Headers`.

#### <a name="new-behavior"></a>Comportamiento nuevo

Los encabezados de finalizador de solicitud **no están presentes** en la recopilación `HttpRequest.Headers`. Use los métodos de extensión siguientes en `HttpRequest` para tener acceso a ellos:

- `GetDeclaredTrailers()`: obtiene el encabezado de "finalizador" de la solicitud que muestra los finalizadores que se esperan después del cuerpo.
- `SupportsTrailers()`: indica si la solicitud admite la recepción de encabezados de finalizador.
- `CheckTrailersAvailable()`: determina si la solicitud admite finalizadores y si están disponible para lectura.
- `GetTrailer(string trailerName)`: obtiene el encabezado de finalización solicitado de la respuesta.

#### <a name="reason-for-change"></a>Motivo del cambio

Los finalizadores son una característica clave en escenarios como gRPC. Combinar los finalizadores en los encabezados de solicitud ha sido confuso para los usuarios.

#### <a name="recommended-action"></a>Acción recomendada

Use los métodos de extensión relacionados con el finalizador en `HttpRequest` para tener acceso a los finalizadores.

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

<xref:Microsoft.AspNetCore.Http.HttpRequest.Headers?displayProperty=nameWithType>

<!--

#### Affected APIs

`P:Microsoft.AspNetCore.Http.HttpRequest.Headers`

-->
