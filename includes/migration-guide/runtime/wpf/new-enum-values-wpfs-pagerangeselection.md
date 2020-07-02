---
ms.openlocfilehash: bae6d7c0f8843211c721c68ce6f16000b35b4401
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620701"
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
|Tipo|Tiempo de ejecución

#### <a name="affected-apis"></a>API afectadas

-<xref:System.Windows.Controls.PageRangeSelection?displayProperty=nameWithType></li></ul>|
