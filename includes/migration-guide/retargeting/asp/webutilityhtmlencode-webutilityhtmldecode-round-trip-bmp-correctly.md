---
ms.openlocfilehash: acb5b467fc8f0692d8fa1b3b8263fd27308cc124
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617260"
---
### <a name="webutilityhtmlencode-and-webutilityhtmldecode-round-trip-bmp-correctly"></a>WebUtility.HtmlEncode y WebUtility.HtmlDecode realizan correctamente el recorrido de ida y vuelta de BMP

#### <a name="details"></a>Detalles

En las aplicaciones que tienen como destino .NET Framework 4.5, los caracteres que no pertenecen a Basic Multilingual Plane (BMP) realizan correctamente el recorrido de ida y vuelta cuando se pasan al método <xref:System.Net.WebUtility.HtmlDecode(System.String)>.

#### <a name="suggestion"></a>Sugerencia

Este cambio no debería tener ningún efecto en las aplicaciones actuales, pero, para restaurar el comportamiento original, establezca el atributo `targetFramework` del elemento `<httpRuntime>` en una cadena distinta a "4.5". También puede establecer los atributos `unicodeEncodingConformance` y `unicodeDecodingConformance` del elemento de configuración `<webUtility>` para controlar este comportamiento con independencia de la versión de .NET Framework que se use como destino.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Borde        |
| Versión | 4.5         |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Net.WebUtility.HtmlEncode(System.String)?displayProperty=nameWithType>
- <xref:System.Net.WebUtility.HtmlEncode(System.String,System.IO.TextWriter)?displayProperty=nameWithType>
