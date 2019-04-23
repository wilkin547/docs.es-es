---
ms.openlocfilehash: ca662b57fae9b1d0d41290f3052f71bca66e9bf3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774467"
---
### <a name="webutilityhtmlencode-and-webutilityhtmldecode-round-trip-bmp-correctly"></a>WebUtility.HtmlEncode y WebUtility.HtmlDecode realizan correctamente el recorrido de ida y vuelta de BMP

|   |   |
|---|---|
|Detalles|En las aplicaciones que tienen como destino .NET Framework 4.5, los caracteres que no pertenecen a Basic Multilingual Plane (BMP) realizan correctamente el recorrido de ida y vuelta cuando se pasan al método <xref:System.Net.WebUtility.HtmlDecode(System.String)>.|
|Sugerencia|Este cambio no debería tener ningún efecto en las aplicaciones actuales, pero para restaurar el comportamiento original, establezca el atributo <code>targetFramework</code> del elemento <code>&lt;httpRuntime&gt;</code> en una cadena distinta a &quot;4.5&quot;. También puede establecer los atributos <code>unicodeEncodingConformance</code> y <code>unicodeDecodingConformance</code> del elemento de configuración <code>&lt;webUtility&gt;</code> para controlar este comportamiento con independencia de la versión de .NET Framework que se use como destino.|
|Ámbito|Borde|
|Versión|4.5|
|Tipo|Redestinación|
|API afectadas|<ul><li><xref:System.Net.WebUtility.HtmlEncode(System.String)?displayProperty=nameWithType></li><li><xref:System.Net.WebUtility.HtmlEncode(System.String,System.IO.TextWriter)?displayProperty=nameWithType></li></ul>|
