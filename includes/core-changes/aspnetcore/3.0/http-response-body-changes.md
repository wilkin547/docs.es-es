---
ms.openlocfilehash: 22ef5d0f91a4f61ca75203f677bcc14e91d77dc1
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394323"
---
### <a name="http-response-body-infrastructure-changes"></a>HTTP: cambios en la infraestructura del cuerpo de respuesta

La infraestructura que respalda un cuerpo de respuesta HTTP ha cambiado. Si usa `HttpResponse` directamente, no debe realizar ningún cambio en el código. Siga leyendo si ajusta o reemplaza `HttpResponse.Body`, o si accede a `HttpContext.Features`.

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="old-behavior"></a>Comportamiento anterior

Había tres API asociadas al cuerpo de respuesta HTTP:

- `IHttpResponseFeature.Body`
- `IHttpSendFileFeature.SendFileAsync`
- `IHttpBufferingFeature.DisableResponseBuffering`

#### <a name="new-behavior"></a>Comportamiento nuevo

Si reemplaza `HttpResponse.Body`, reemplaza todo el elemento `IHttpResponseBodyFeature` por un contenedor en torno a la secuencia dada mediante `StreamResponseBodyFeature` con el fin de proporcionar implementaciones predeterminadas para todas las API esperadas. Al volver a establecer la secuencia original, este cambio se revierte.

#### <a name="reason-for-change"></a>Motivo del cambio

La motivación es combinar las API del cuerpo de la respuesta en una única interfaz de características nueva.

#### <a name="recommended-action"></a>Acción recomendada

Use `IHttpResponseBodyFeature` donde anteriormente usaba `IHttpResponseFeature.Body`, `IHttpSendFileFeature` o `IHttpBufferingFeature`.

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

- <xref:Microsoft.AspNetCore.Http.Features.IHttpBufferingFeature?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.IHttpResponseFeature.Body?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Http.Features.IHttpSendFileFeature?displayProperty=nameWithType>
 
<!-- 

#### Affected APIs

- `T:Microsoft.AspNetCore.Http.Features.IHttpBufferingFeature`
- `P:Microsoft.AspNetCore.Http.Features.IHttpResponseFeature.Body`
- `T:Microsoft.AspNetCore.Http.Features.IHttpSendFileFeature`

-->
