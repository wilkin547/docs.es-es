---
ms.openlocfilehash: 395463225e3c1f1d168dd019ea75966ad54e5a8a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621398"
---
### <a name="changing-the-isenabled-property-of-the-parent-of-a-textblock-control-affects-any-child-controls"></a>El cambio de la propiedad IsEnabled del elemento primario de un control TextBlock afecta a todos los controles secundarios

#### <a name="details"></a>Detalles

A partir de .NET Framework 4.6.2, el cambio de la propiedad <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName> del elemento primario de un control <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> afecta a todos los controles secundarios (como los hipervínculos y los botones) del control <xref:System.Windows.Controls.TextBlock?displayProperty=fullName>. En .NET Framework 4.6.1 y versiones anteriores, los controles dentro de un <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> no siempre reflejaban el estado de la propiedad <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName> del elemento <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> primario.

#### <a name="suggestion"></a>Sugerencia

Ninguno. Este cambio se ajusta al comportamiento esperado de los controles dentro de un control <xref:System.Windows.Controls.TextBlock?displayProperty=fullName>.

| Nombre    | Valor       |
|:--------|:------------|
| Ámbito   |Secundaria|
|Versión|4.6.2|
|Tipo|Tiempo de ejecución

#### <a name="affected-apis"></a>API afectadas

-<xref:System.Windows.UIElement.IsEnabled?displayProperty=nameWithType></li></ul>|
