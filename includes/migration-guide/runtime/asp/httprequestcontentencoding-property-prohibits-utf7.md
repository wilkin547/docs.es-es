---
ms.openlocfilehash: 7d3568fef933758c40e47cefa86c24d31d4119fc
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620530"
---
### <a name="httprequestcontentencoding-property-prohibits-utf7"></a>La propiedad HttpRequest.ContentEncoding prohíbe la codificación UTF7

#### <a name="details"></a>Detalles

A partir de .NET Framework 4.5, la codificación UTF-7 está prohibida en los cuerpos de elementos <xref:System.Web.HttpRequest?displayProperty=fullName>. Los datos de las aplicaciones que dependen de los datos de entrada UTF-7 no se descodificarán correctamente en algunos casos.

#### <a name="suggestion"></a>Sugerencia

Lo ideal sería actualizar las aplicaciones para que no usen la codificación UTF-7 en los elementos <xref:System.Web.HttpRequest?displayProperty=fullName>. También es posible restaurar el comportamiento heredado usando el atributo <code>aspnet:AllowUtf7RequestContentEncoding</code> del elemento [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md).

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución

#### <a name="affected-apis"></a>API afectadas

-<xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType></li></ul>|
