---
title: "Información general sobre StatusBar (Control, formularios Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: StatusBar
helpviewer_keywords:
- StatusBar control [Windows Forms], about StatusBar control
- status bars
ms.assetid: b7b9852c-633d-4416-bb2e-94852b989c6c
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9c26463fae5beca23026a71dd83b19bf3eb52875
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="statusbar-control-overview-windows-forms"></a>Información general sobre StatusBar (Control, formularios Windows Forms)
> [!IMPORTANT]
>  El <xref:System.Windows.Forms.StatusStrip> y <xref:System.Windows.Forms.ToolStripStatusLabel> controles reemplazan y agregan funcionalidad a la <xref:System.Windows.Forms.StatusBar> y <xref:System.Windows.Forms.StatusBarPanel> controla; sin embargo, el <xref:System.Windows.Forms.StatusBar> y <xref:System.Windows.Forms.StatusBarPanel> controles se conservan por compatibilidad con versiones anteriores y uso futuro, si se Elija esta opción.  
  
 Los formularios Windows Forms [StatusBar (Control)](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) se utiliza en los formularios como un área, normalmente se muestra en la parte inferior de una ventana, en la que una aplicación puede mostrar varios tipos de información de estado. <xref:System.Windows.Forms.StatusBar>los controles pueden tener paneles de barra de estado en ellos que muestran texto o iconos para indicar el estado o una serie de iconos de una animación que indican que un proceso de trabajo; Por ejemplo, [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] que indica que se guarda el documento.  
  
## <a name="using-the-statusbar-control"></a>Uso del Control StatusBar  
 Internet Explorer utiliza una barra de estado para indicar la dirección URL de una página cuando el mouse pasa sobre el hipervínculo; [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] ofrece información sobre la ubicación de la página, la ubicación de la sección y la edición modos como sobrescribir y revisar cambios; y [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] usa la barra de estado para ofrecer información contextual, por ejemplo, que le indica cómo manipular acoplable Windows como acoplada o flotante.  
  
 También puede mostrar un único mensaje en la barra de estado estableciendo el <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> propiedad a `false` (valor predeterminado) y estableciendo el <xref:System.Windows.Forms.StatusBar.Text%2A> propiedad de la barra de estado para el texto que desea que aparezcan en la barra de estado. Puede dividir la barra de estado en paneles para mostrar más de un tipo de información estableciendo la <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> propiedad `true` y el uso de la <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> método de <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.StatusBar>  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 [Determinar en qué panel del control StatusBar de Windows Forms se hizo clic](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)
