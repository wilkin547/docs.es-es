---
ms.openlocfilehash: 8b0617d8f021a9534289fd7ae8539cd054684862
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234782"
---
### <a name="wpf-textboxtext-can-be-out-of-sync-with-databinding"></a>TextBox.Text de WPF se puede desincronizar con el enlace de datos

|   |   |
|---|---|
|Detalles|En algunos casos, la propiedad <xref:System.Windows.Controls.TextBox.Text> refleja un valor anterior al valor de propiedad de enlace de datos si la propiedad se modifica durante una operación de escritura de enlace de datos.|
|Sugerencia|Esto no debería tener ningún impacto negativo. Sin embargo, puede restaurar el comportamiento anterior estableciendo la propiedad <xref:System.Windows.FrameworkCompatibilityPreferences.KeepTextBoxDisplaySynchronizedWithTextProperty> en <code>false</code>.|
|Ámbito|Borde|
|Versión|4.5|
|Tipo|Redestinación|
|API afectadas|<ul><li><xref:System.Windows.Controls.TextBox.Text?displayProperty=nameWithType></li></ul>|
