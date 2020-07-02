---
ms.openlocfilehash: 13d3799aeede86b01aa81ce1cd69b3c4c22311ca
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620713"
---
### <a name="wpf-textbox-defaults-to-undo-limit-of-100"></a>Los cuadros de texto de WPF tienen como valor predeterminado un límite de 100 para la fase de reversión

#### <a name="details"></a>Detalles

En .NET Framework 4.5, el límite para la fase de reversión de un cuadro de texto de WPF es de 100 (a diferencia de .NET Framework 4.0, donde no existía ningún límite).

#### <a name="suggestion"></a>Sugerencia

Si el límite de 100 para la fase de reversión es demasiado bajo, se puede establecer de forma explícita con <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit>.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución

#### <a name="affected-apis"></a>API afectadas

-<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|
