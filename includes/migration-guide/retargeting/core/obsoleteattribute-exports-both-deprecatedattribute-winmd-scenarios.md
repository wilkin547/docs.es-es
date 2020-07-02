---
ms.openlocfilehash: 424e8ff704b888aa3d2c1254ac712da4034f59b8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616116"
---
### <a name="obsoleteattribute-exports-as-both-obsoleteattribute-and-deprecatedattribute-in-winmd-scenarios"></a>ObsoleteAttribute se exporta como ObsoleteAttribute y DeprecatedAttribute en escenarios de WinMD

#### <a name="details"></a>Detalles

Cuando se crea una biblioteca de metadatos de Windows (archivo .winmd), el atributo <xref:System.ObsoleteAttribute?displayProperty=fullName> se exporta como <xref:System.ObsoleteAttribute?displayProperty=fullName> y como [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute).

#### <a name="suggestion"></a>Sugerencia

Volver a compilar el código fuente existente que usa el atributo <xref:System.ObsoleteAttribute?displayProperty=fullName> puede generar advertencias cuando ese código se usa desde C++/CX o JavaScript. No se recomienda aplicar <xref:System.ObsoleteAttribute?displayProperty=fullName> y [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute) al código en los ensamblados administrados; se podrían producir advertencias de compilación.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Borde        |
| Versión | 4.5.1       |
| Tipo    | Redestinación |
