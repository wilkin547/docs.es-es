---
ms.openlocfilehash: b648aee35ff44730f545f0fa06f4e0a86615dece
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606175"
---
### <a name="httputilityjavascriptstringencode-escapes-ampersand"></a>HttpUtility.JavaScriptStringEncode aplica un carácter de escape a la Y comercial

#### <a name="details"></a>Detalles

A partir de .NET Framework 4.5, <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=fullName> incluye un carácter de escape antes del carácter de Y comercial (&amp;).

#### <a name="suggestion"></a>Sugerencia

Si la aplicación depende del comportamiento anterior de este método, puede agregar un ajuste aspnet:JavaScriptDoNotEncodeAmpersand al [elemento appSettings de ASP.NET](/previous-versions/aspnet/hh975440(v=vs.120)) en el archivo de configuración.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Secundaria|
|Versión|4.5|
|Tipo|Tiempo de ejecución|

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=nameWithType>
- <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Web.HttpUtility.JavaScriptStringEncode(System.String)`
- `M:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)`

-->
