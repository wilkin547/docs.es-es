---
ms.openlocfilehash: 2aa6603e2ed77ffa94fbc6325cd5db50985bda6a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620680"
---
### <a name="previewlostkeyboardfocus-is-called-repeatedly-if-its-handler-shows-a-windows-forms-message-box"></a>Se llama repetidas veces a PreviewLostKeyboardFocus si su controlador muestra un cuadro de mensaje de Windows Forms

#### <a name="details"></a>Detalles

A partir de .NET Framework 4.5, si se llama a <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType> desde un controlador de <xref:System.Windows.UIElement.PreviewLostKeyboardFocus>, se volverá a activar el controlador al cerrar el cuadro de mensaje, lo que podría generar un bucle infinito de cuadros de mensaje.

#### <a name="suggestion"></a>Sugerencia

Hay dos opciones para solucionar este problema:<ol><li>Se puede evitar llamando a <xref:System.Windows.MessageBox.Show%2A?displayProperty=nameWithType> en lugar de a <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType>.</li><li>Se puede evitar mostrando el cuadro de mensaje desde un controlador de eventos <xref:System.Windows.UIElement.LostKeyboardFocus> (en contraposición a un controlador de eventos <xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=fullName>).</li></ol>

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución

#### <a name="affected-apis"></a>API afectadas

-<xref:System.Windows.ContentElement.PreviewLostKeyboardFocus?displayProperty=nameWithType></li><li><xref:System.Windows.IInputElement.PreviewLostKeyboardFocus?displayProperty=nameWithType></li><li><xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=nameWithType></li><li><xref:System.Windows.UIElement3D.PreviewLostKeyboardFocus?displayProperty=nameWithType></li></ul>|
