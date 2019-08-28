---
ms.openlocfilehash: 3b94c88809513e31a5f226bcfce39abbfa4de378
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/24/2019
ms.locfileid: "70017377"
---
### <a name="aspnet-validationcontextmembername-is-not-null-when-using-custom-dataannotationsvalidationattribute"></a>ValidationContext.MemberName de APS.NET no es NULL cuando se usa DataAnnotations.ValidationAttribute personalizado

|   |   |
|---|---|
|Detalles|En .NET Framework 4.7.2 y versiones anteriores, cuando se usa <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType> personalizado, la propiedad <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType> devuelve <code>null</code>.  En .NET Framework 4.8, devuelve el nombre del miembro.|
|Sugerencia|Para restaurar el comportamiento anterior, agregue la siguiente configuración al archivo de configuración de la aplicación:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:GetValidationMemberName&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>Este comportamiento cambiará en una próxima versión del servicio, cuando tendrá que seleccionar explícitamente el nuevo comportamiento. La propiedad devolverá un valor distinto de null para un atributo `ValidationAttribute` personalizado si el modificador `aspnet:GetValidationMemberName` se establece en `true`.|
|Ámbito|Desconocido|
|Versión|4.8|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType></li></ul>|
