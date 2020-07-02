---
ms.openlocfilehash: d587e542a72d584502ac3ac892619cc38b88ef77
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620534"
---
### <a name="httputilityjavascriptstringencode-escapes-ampersand"></a>HttpUtility.JavaScriptStringEncode aplica un carácter de escape a la Y comercial

#### <a name="details"></a>Detalles

A partir de .NET Framework 4.5, <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=fullName> incluye un carácter de escape antes del carácter de Y comercial (&amp;).

#### <a name="suggestion"></a>Sugerencia

Si la aplicación depende del comportamiento anterior de este método, puede agregar un ajuste aspnet:JavaScriptDoNotEncodeAmpersand al [elemento appSettings de ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/hh975440(v=vs.120)) en el archivo de configuración.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Secundaria|
|Versión|4.5|
|Tipo|Tiempo de ejecución

#### <a name="affected-apis"></a>API afectadas

-<xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=nameWithType></li><li><xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)?displayProperty=nameWithType></li></ul>|
