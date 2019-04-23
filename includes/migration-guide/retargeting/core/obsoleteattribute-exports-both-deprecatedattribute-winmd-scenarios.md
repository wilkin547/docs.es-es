---
ms.openlocfilehash: e8c48c4b1031813ce62f576e5bf1f94c082dfe4b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774431"
---
### <a name="obsoleteattribute-exports-as-both-obsoleteattribute-and-deprecatedattribute-in-winmd-scenarios"></a>ObsoleteAttribute se exporta como ObsoleteAttribute y DeprecatedAttribute en escenarios de WinMD

|   |   |
|---|---|
|Detalles|Cuando se crea una biblioteca de metadatos de Windows (archivo .winmd), el atributo <xref:System.ObsoleteAttribute?displayProperty=name> se exporta como <xref:System.ObsoleteAttribute?displayProperty=name> y como [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute).|
|Sugerencia|Volver a compilar el código fuente existente que usa el atributo <xref:System.ObsoleteAttribute?displayProperty=name> puede generar advertencias cuando ese código se usa desde C++/CX o JavaScript. No se recomienda aplicar <xref:System.ObsoleteAttribute?displayProperty=name> y [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute) al código en los ensamblados administrados; se podrían producir advertencias de compilación.|
|Ámbito|Borde|
|Versión|4.5.1|
|Tipo|Redestinación|
