---
ms.openlocfilehash: d6405573e476ce18513938b500041adefbeeef1b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496841"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a>El fondo de RibbonGroup se establece en transparente en las compilaciones localizadas

#### <a name="details"></a>Detalles

El fondo de <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName> en las compilaciones localizadas siempre se pinta con el pincel transparente, lo que produce una experiencia de interfaz de usuario deficiente. Esto se corrigió en WPF en .NET Framework 4.7 mediante la actualización de los recursos localizados para <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName> lo que, a su vez, garantiza que se seleccione el pincel correcto.

#### <a name="suggestion"></a>Sugerencia

Actualizar a .NET Framework 4.7

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.6.2|
|Tipo|Tiempo de ejecución|

#### <a name="affected-apis"></a>API afectadas

No detectable a través del análisis de la API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
