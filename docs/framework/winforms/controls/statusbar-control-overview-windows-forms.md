---
title: Información general sobre StatusBar (Control, formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- StatusBar
helpviewer_keywords:
- StatusBar control [Windows Forms], about StatusBar control
- status bars
ms.assetid: b7b9852c-633d-4416-bb2e-94852b989c6c
ms.openlocfilehash: bd58d4c70e3a3c88e57fe242957f669d1944fd71
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964435"
---
# <a name="statusbar-control-overview-windows-forms"></a>Información general sobre StatusBar (Control, formularios Windows Forms)
> [!IMPORTANT]
> Los <xref:System.Windows.Forms.StatusStrip> controles <xref:System.Windows.Forms.ToolStripStatusLabel> y reemplazan y agregan funcionalidad <xref:System.Windows.Forms.StatusBar> a <xref:System.Windows.Forms.StatusBarPanel> los controles y; sin <xref:System.Windows.Forms.StatusBar> embargo <xref:System.Windows.Forms.StatusBarPanel> , los controles y se conservan por compatibilidad con versiones anteriores y uso futuro, si Elija.  
  
 El Windows Forms [control StatusBar](statusbar-control-windows-forms.md) se usa en los formularios como un área, que normalmente se muestra en la parte inferior de una ventana, en la que una aplicación puede mostrar diversos tipos de información de estado. <xref:System.Windows.Forms.StatusBar>los controles pueden tener paneles de barra de estado en los que se muestre texto o iconos para indicar el estado o una serie de iconos de una animación que indiquen que un proceso está funcionando; por ejemplo, Microsoft Word indica que el documento se está guardando.  
  
## <a name="using-the-statusbar-control"></a>Usar el control StatusBar  
 Internet Explorer usa una barra de estado para indicar la dirección URL de una página cuando el mouse se sitúa sobre el hipervínculo; Microsoft Word le proporciona información sobre la ubicación de la página, la ubicación de la sección y los modos de edición como sobreescribir y seguimiento de la revisión. y Visual Studio usa la barra de estado para proporcionar información contextual, como indicar cómo manipular las ventanas acoplables como acopladas o flotantes.  
  
 Puede mostrar un solo mensaje en la barra de estado si establece la <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> propiedad en `false` (valor predeterminado) y establece la <xref:System.Windows.Forms.StatusBar.Text%2A> propiedad de la barra de estado en el texto que desea que aparezca en la barra de estado. Puede dividir la barra de estado en paneles para mostrar más de un tipo de <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> información estableciendo la propiedad en `true` y usando el <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> método de <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [Cómo: Determinar en qué panel del control Windows Forms StatusBar se hizo clic](determine-which-panel-wf-statusbar-control-was-clicked.md)
