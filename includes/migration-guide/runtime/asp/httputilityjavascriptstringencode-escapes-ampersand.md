---
ms.openlocfilehash: 0056baa1e5f0cdc5bfcf8b0e83c9490ec5722926
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235926"
---
### <a name="httputilityjavascriptstringencode-escapes-ampersand"></a>HttpUtility.JavaScriptStringEncode aplica un carácter de escape a la Y comercial

|   |   |
|---|---|
|Detalles|A partir de .NET Framework 4.5, <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=name> incluye un carácter de escape antes del carácter de Y comercial (&amp;).|
|Sugerencia|Si la aplicación depende del comportamiento anterior de este método, puede agregar un ajuste aspnet:JavaScriptDoNotEncodeAmpersand al [elemento appSettings de ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/hh975440(v=vs.120)) en el archivo de configuración.|
|Ámbito|Secundaria|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=nameWithType></li><li><xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)?displayProperty=nameWithType></li></ul>|
