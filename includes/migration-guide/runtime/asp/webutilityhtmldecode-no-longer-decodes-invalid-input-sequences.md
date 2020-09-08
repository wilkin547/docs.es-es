---
ms.openlocfilehash: ef3114a4eb9f62030c3ec36d3b463d07ccd59f6d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496882"
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

- <xref:System.Net.WebUtility.HtmlDecode(System.String)?displayProperty=nameWithType>
- <xref:System.Net.WebUtility.HtmlDecode(System.String,System.IO.TextWriter)?displayProperty=nameWithType>
- <xref:System.Net.WebUtility.UrlDecode(System.String)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Net.WebUtility.HtmlDecode(System.String)`
- `M:System.Net.WebUtility.HtmlDecode(System.String,System.IO.TextWriter)`
- `M:System.Net.WebUtility.UrlDecode(System.String)`

-->
