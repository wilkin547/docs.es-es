---
ms.openlocfilehash: de79182e326082786c1e0691f8888e30cd410f5d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59235794"
---
### <a name="wpf-textbox-defaults-to-undo-limit-of-100"></a>Los cuadros de texto de WPF tienen como valor predeterminado un límite de 100 para la fase de reversión

|   |   |
|---|---|
|Detalles|En .NET Framework 4.5, el límite para la fase de reversión de un cuadro de texto de WPF es de 100 (a diferencia de .NET Framework 4.0, donde no existía ningún límite).|
|Sugerencia|Si el límite de 100 para la fase de reversión es demasiado bajo, se puede establecer de forma explícita con <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit>.|
|Ámbito|Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|
