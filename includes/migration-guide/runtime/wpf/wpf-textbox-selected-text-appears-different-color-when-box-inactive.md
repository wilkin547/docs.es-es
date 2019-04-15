---
ms.openlocfilehash: 74ce1bbc9a887aee3a33eaf05084e8c2000967c2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235956"
---
### <a name="wpf-textbox-selected-text-appears-a-different-color-when-the-text-box-is-inactive"></a>El texto seleccionado de un cuadro de texto de WPF aparece en otro color cuando el cuadro de texto está inactivo

|   |   |
|---|---|
|Detalles|En .NET Framework 4.5, cuando un control de cuadro de texto de WPF está inactivo (sin el foco), el texto seleccionado dentro del cuadro aparecerá en un color diferente al que lo haría con el control activo.|
|Sugerencia|El comportamiento anterior (.NET Framework 4.0) se puede restaurar si se establece la propiedad <xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported> en <code>false</code>.|
|Ámbito|Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|
