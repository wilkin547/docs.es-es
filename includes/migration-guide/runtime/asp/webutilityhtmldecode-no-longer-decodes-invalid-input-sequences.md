---
ms.openlocfilehash: 0b7d6d9543035ab0a8fdda675ae71572ace12a1f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620541"
---
### <a name="webutilityhtmldecode-no-longer-decodes-invalid-input-sequences"></a>WebUtility.HtmlDecode ya no descodifica secuencias de entrada no válidas

#### <a name="details"></a>Detalles

De forma predeterminada, los métodos de descodificación ya no descodifican secuencias de entrada no válidas en una cadena UTF-16 no válida. En su lugar, devuelven la entrada original.

#### <a name="suggestion"></a>Sugerencia

El cambio en la salida del descodificador solo es importante si se almacenan datos binarios en lugar de datos UTF-16 en cadenas. Para controlar este comportamiento de manera explícita, establezca el atributo <code>aspnet:AllowRelaxedUnicodeDecoding</code> del elemento [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/index.md) en <code>true</code> para habilitar el comportamiento heredado o en <code>false</code> para habilitar el actual.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Secundaria|
|Versión|4.5|
|Tipo|Tiempo de ejecución

#### <a name="affected-apis"></a>API afectadas

-<xref:System.Net.WebUtility.HtmlDecode(System.String)?displayProperty=nameWithType></li><li><xref:System.Net.WebUtility.HtmlDecode(System.String,System.IO.TextWriter)?displayProperty=nameWithType></li><li><xref:System.Net.WebUtility.UrlDecode(System.String)?displayProperty=nameWithType></li></ul>|
