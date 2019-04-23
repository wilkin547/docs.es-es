---
ms.openlocfilehash: 668d047d3247d64cb1400d4a9ea6887795fa0d44
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59805079"
---
### <a name="httprequestcontentencoding-property-prohibits-utf7"></a>La propiedad HttpRequest.ContentEncoding prohíbe la codificación UTF7

|   |   |
|---|---|
|Detalles|A partir de .NET Framework 4.5, la codificación UTF-7 está prohibida en los cuerpos de elementos <xref:System.Web.HttpRequest?displayProperty=name>. Los datos de las aplicaciones que dependen de los datos de entrada UTF-7 no se descodificarán correctamente en algunos casos.|
|Sugerencia|Lo ideal sería actualizar las aplicaciones para que no usen la codificación UTF-7 en los elementos <xref:System.Web.HttpRequest?displayProperty=name>. También es posible restaurar el comportamiento heredado usando el atributo <code>aspnet:AllowUtf7RequestContentEncoding</code> del elemento [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md).|
|Ámbito|Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType></li></ul>|
