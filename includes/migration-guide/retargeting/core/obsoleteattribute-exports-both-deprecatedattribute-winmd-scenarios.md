---
ms.openlocfilehash: 7d7424b3ca0d295022999e95ed9862b5226b6220
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606349"
---
### <a name="obsoleteattribute-exports-as-both-obsoleteattribute-and-deprecatedattribute-in-winmd-scenarios"></a>ObsoleteAttribute se exporta como ObsoleteAttribute y DeprecatedAttribute en escenarios de WinMD

#### <a name="details"></a>Detalles

Cuando se crea una biblioteca de metadatos de Windows (archivo .winmd), el atributo <xref:System.ObsoleteAttribute?displayProperty=fullName> se exporta como <xref:System.ObsoleteAttribute?displayProperty=fullName> y como [Windows.Foundation.DeprecatedAttribute](/uwp/api/windows.foundation.metadata.deprecatedattribute).

#### <a name="suggestion"></a>Sugerencia

Volver a compilar el código fuente existente que usa el atributo <xref:System.ObsoleteAttribute?displayProperty=fullName> puede generar advertencias cuando ese código se usa desde C++/CX o JavaScript. No se recomienda aplicar <xref:System.ObsoleteAttribute?displayProperty=fullName> y [Windows.Foundation.DeprecatedAttribute](/uwp/api/windows.foundation.metadata.deprecatedattribute) al código en los ensamblados administrados; se podrían producir advertencias de compilación.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Borde        |
| Versión | 4.5.1       |
| Tipo    | Redestinación |
