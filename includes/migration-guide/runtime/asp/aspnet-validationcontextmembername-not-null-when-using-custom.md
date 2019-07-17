---
ms.openlocfilehash: df13f6938ebaf8e96bb2825c1495044621f1c31b
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802618"
---
### <a name="aspnet-validationcontextmembername-is-not-null-when-using-custom-dataannotationsvalidationattribute"></a>ValidationContext.MemberName de APS.NET no es NULL cuando se usa DataAnnotations.ValidationAttribute personalizado

|   |   |
|---|---|
|Detalles|En .NET Framework 4.7.2 y versiones anteriores, cuando se usa <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType> personalizado, la propiedad <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType> devuelve <code>null</code>.  En .NET Framework 4.8, devuelve el nombre del miembro.|
|Sugerencia|El comportamiento predeterminado de la propiedad <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType> sigue siendo el mismo.  Para recuperar un valor válido de la propiedad <code>ValidationContext.MemberName</code>, agregue la siguiente configuración al archivo de configuración de la aplicación:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:GetValidationMemberName&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Ámbito|Desconocido|
|Versión|4.8|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType></li></ul>|

