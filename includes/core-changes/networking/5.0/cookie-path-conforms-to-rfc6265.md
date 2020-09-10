---
ms.openlocfilehash: 7140f6d4cac063088b3663ab98d292104218b542
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2020
ms.locfileid: "89465523"
---
### <a name="cookie-path-handling-now-conforms-to-rfc-6265"></a>La administración de rutas de acceso de cookies ahora se ajusta a RFC 6265.

Los algoritmos de control de rutas de acceso que se definen en [RFC 6265](https://tools.ietf.org/html/rfc6265) se implementaron para las clases <xref:System.Net.Cookie> y <xref:System.Net.CookieContainer>.

#### <a name="version-introduced"></a>Versión introducida

5.0

#### <a name="change-description"></a>Descripción del cambio

- Ya no es necesario que la propiedad <xref:System.Net.Cookie.Path> sea un prefijo de la ruta de acceso de la solicitud.
- El cálculo del valor predeterminado de <xref:System.Net.Cookie.Path> y los algoritmos de coincidencia de ruta de acceso se implementaron tal y como se define en la [sección 5.1.4](https://tools.ietf.org/html/rfc6265#section-5.1.4) de RFC 6265.

#### <a name="recommended-action"></a>Acción recomendada

En la mayoría de los casos, no tiene que realizar ninguna acción. Sin embargo, si el código dependía de la validación de <xref:System.Net.Cookie.Path>, deberá implementar la validación necesaria en el código. Si el código dependía del cálculo de valores predeterminados para <xref:System.Net.Cookie.Path>, considere la posibilidad de proporcionar el valor <xref:System.Net.Cookie.Path> manualmente en lugar de usar el valor predeterminado.

#### <a name="category"></a>Categoría

Redes

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Net.Cookie?displayProperty=fullName>
- <xref:System.Net.CookieContainer?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Net.Cookie`
- `T:System.Net.CookieContainer`

-->
