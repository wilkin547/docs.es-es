---
ms.openlocfilehash: d0de1a262d57c67dd4dfb258d5ac013af5d8783d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617293"
---
### <a name="wpf-textboxtext-can-be-out-of-sync-with-databinding"></a>TextBox.Text de WPF se puede desincronizar con el enlace de datos

#### <a name="details"></a>Detalles

En algunos casos, la propiedad <xref:System.Windows.Controls.TextBox.Text> refleja un valor anterior al valor de propiedad de enlace de datos si la propiedad se modifica durante una operación de escritura de enlace de datos.

#### <a name="suggestion"></a>Sugerencia

Esto no debería tener ningún impacto negativo. Sin embargo, puede restaurar el comportamiento anterior estableciendo la propiedad <xref:System.Windows.FrameworkCompatibilityPreferences.KeepTextBoxDisplaySynchronizedWithTextProperty> en `false`.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Borde        |
| Versión | 4.5         |
|Tipo|Redestinación

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Windows.Controls.TextBox.Text?displayProperty=nameWithType>
