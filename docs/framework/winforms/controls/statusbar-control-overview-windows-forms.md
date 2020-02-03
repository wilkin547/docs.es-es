---
title: Información general sobre StatusBar (Control)
ms.date: 03/30/2017
f1_keywords:
- StatusBar
helpviewer_keywords:
- StatusBar control [Windows Forms], about StatusBar control
- status bars
ms.assetid: b7b9852c-633d-4416-bb2e-94852b989c6c
ms.openlocfilehash: b0b97bc3cb0291871e1fd113d82d0b480b53cdba
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742868"
---
# <a name="statusbar-control-overview-windows-forms"></a>Información general sobre StatusBar (Control, formularios Windows Forms)
> [!IMPORTANT]
> Los controles <xref:System.Windows.Forms.StatusStrip> y <xref:System.Windows.Forms.ToolStripStatusLabel> reemplazan y agregan funcionalidad a los controles <xref:System.Windows.Forms.StatusBar> y <xref:System.Windows.Forms.StatusBarPanel>; sin embargo, los controles <xref:System.Windows.Forms.StatusBar> y <xref:System.Windows.Forms.StatusBarPanel> se conservan por compatibilidad con versiones anteriores y uso futuro, si así lo decide.  
  
 El Windows Forms [control StatusBar](statusbar-control-windows-forms.md) se usa en los formularios como un área, que normalmente se muestra en la parte inferior de una ventana, en la que una aplicación puede mostrar diversos tipos de información de estado. <xref:System.Windows.Forms.StatusBar> controles pueden tener paneles de barra de estado en ellos que muestren texto o iconos para indicar el estado o una serie de iconos de una animación que indiquen que un proceso está funcionando; por ejemplo, Microsoft Word indica que el documento se está guardando.  
  
## <a name="using-the-statusbar-control"></a>Usar el control StatusBar  
 Internet Explorer usa una barra de estado para indicar la dirección URL de una página cuando el mouse se sitúa sobre el hipervínculo; Microsoft Word le proporciona información sobre la ubicación de la página, la ubicación de la sección y los modos de edición como sobreescribir y seguimiento de la revisión. y Visual Studio usa la barra de estado para proporcionar información contextual, como indicar cómo manipular las ventanas acoplables como acopladas o flotantes.  
  
 Puede mostrar un solo mensaje en la barra de estado si establece la propiedad <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> en `false` (valor predeterminado) y establece la propiedad <xref:System.Windows.Forms.StatusBar.Text%2A> de la barra de estado en el texto que desea que aparezca en la barra de estado. Puede dividir la barra de estado en paneles para mostrar más de un tipo de información estableciendo la propiedad <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> en `true` y usando el método <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> de <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [Determinar en qué panel del control StatusBar de Windows Forms se hizo clic](determine-which-panel-wf-statusbar-control-was-clicked.md)
