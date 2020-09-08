---
ms.openlocfilehash: 61749f59f9379a6d18bb013b2612a07cb7822b3a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496628"
---
### <a name="new-enum-values-in-wpfs-pagerangeselection"></a>Nuevos valores de enumeración en PageRangeSelection de WPF

#### <a name="details"></a>Detalles

Se han agregado dos miembros nuevos (<xref:System.Windows.Controls.PageRangeSelection.CurrentPage?displayProperty=fullName> y <xref:System.Windows.Controls.PageRangeSelection.SelectedPages?displayProperty=fullName>) a la enumeración <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName>.

#### <a name="suggestion"></a>Sugerencia

En la mayoría de los casos, estos cambios no afectan al código del usuario. Pero se debe modificar el código que depende de un número concreto de elementos existentes en las llamadas a <xref:System.Enum.GetNames(System.Type)> o <xref:System.Enum.GetValues(System.Type)> del tipo <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName>.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Windows.Controls.PageRangeSelection?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Windows.Controls.PageRangeSelection`

-->
