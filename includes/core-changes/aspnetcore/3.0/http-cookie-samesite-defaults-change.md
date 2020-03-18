---
ms.openlocfilehash: 15ba678431b97e7c961c119d83546569bdf9bad2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "74282526"
---
### <a name="http-some-cookie-samesite-defaults-changed-to-none"></a>HTTP: Cambio a Ninguno de algunos valores predeterminados de cookie de SameSite

`SameSite` es una opción para cookies que puede ayudar a mitigar algunos ataques de falsificación de solicitud entre sitios (CSRF). Cuando esta opción se presentó inicialmente, se usaron valores predeterminados incoherentes en varias API de ASP.NET Core. La incoherencia ha generado unos resultados confusos. A partir de ASP.NET Core 3.0, estos valores predeterminados están organizados de mejor forma. Debe aceptar participar en esta característica individualmente para cada componente.

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="old-behavior"></a>Comportamiento anterior

Las API de ASP.NET Core similares usaban diferentes valores predeterminados de <xref:Microsoft.AspNetCore.Http.SameSiteMode>. Un ejemplo de la incoherencia se percibe en `HttpResponse.Cookies.Append(String, String)` y `HttpResponse.Cookies.Append(String, String, CookieOptions)`, que tenían como valor predeterminado `SameSiteMode.None` y `SameSiteMode.Lax`, respectivamente.

#### <a name="new-behavior"></a>Comportamiento nuevo

Todas las API afectadas tienen como valor predeterminado `SameSiteMode.None`.

#### <a name="reason-for-change"></a>Motivo del cambio

El valor predeterminado se ha cambiado para que `SameSite` fuera una característica de participación opcional.

#### <a name="recommended-action"></a>Acción recomendada

Cada componente que emite cookies debe decidir si `SameSite` es adecuado para sus escenarios. Revise el uso de las API afectadas y vuelva a configurar `SameSite` según sea necesario.

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

- <xref:Microsoft.AspNetCore.Http.IResponseCookies.Append(System.String,System.String,Microsoft.AspNetCore.Http.CookieOptions)?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Builder.CookiePolicyOptions.MinimumSameSitePolicy%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:Microsoft.AspNetCore.Http.IResponseCookies.Append(System.String,System.String,Microsoft.AspNetCore.Http.CookieOptions)`
- `Overload:Microsoft.AspNetCore.Builder.CookiePolicyOptions.MinimumSameSitePolicy`

-->
