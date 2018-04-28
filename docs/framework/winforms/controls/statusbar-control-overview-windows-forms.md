---
title: Información general sobre StatusBar (Control, formularios Windows Forms)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- StatusBar
helpviewer_keywords:
- StatusBar control [Windows Forms], about StatusBar control
- status bars
ms.assetid: b7b9852c-633d-4416-bb2e-94852b989c6c
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8e84ae7d62649c0c547417e954560ac0faccafdd
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2018
---
# <a name="statusbar-control-overview-windows-forms"></a><span data-ttu-id="8e36e-102">Información general sobre StatusBar (Control, formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="8e36e-102">StatusBar Control Overview (Windows Forms)</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="8e36e-103">El <xref:System.Windows.Forms.StatusStrip> y <xref:System.Windows.Forms.ToolStripStatusLabel> controles reemplazan y agregan funcionalidad a la <xref:System.Windows.Forms.StatusBar> y <xref:System.Windows.Forms.StatusBarPanel> controla; sin embargo, el <xref:System.Windows.Forms.StatusBar> y <xref:System.Windows.Forms.StatusBarPanel> controles se conservan por compatibilidad con versiones anteriores y uso futuro, si se Elija esta opción.</span><span class="sxs-lookup"><span data-stu-id="8e36e-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="8e36e-104">Los formularios Windows Forms [StatusBar (Control)](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) se utiliza en los formularios como un área, normalmente se muestra en la parte inferior de una ventana, en la que una aplicación puede mostrar varios tipos de información de estado.</span><span class="sxs-lookup"><span data-stu-id="8e36e-104">The Windows Forms [StatusBar Control](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) is used on forms as an area, usually displayed at the bottom of a window, in which an application can display various kinds of status information.</span></span> <span data-ttu-id="8e36e-105"><xref:System.Windows.Forms.StatusBar> los controles pueden tener paneles de barra de estado en ellos que muestran texto o iconos para indicar el estado o una serie de iconos de una animación que indican que un proceso de trabajo; Por ejemplo, [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] que indica que se guarda el documento.</span><span class="sxs-lookup"><span data-stu-id="8e36e-105"><xref:System.Windows.Forms.StatusBar> controls can have status bar panels on them that display text or icons to indicate state, or a series of icons in an animation that indicate a process is working; for example, [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] indicating that the document is being saved.</span></span>  
  
## <a name="using-the-statusbar-control"></a><span data-ttu-id="8e36e-106">Uso del Control StatusBar</span><span class="sxs-lookup"><span data-stu-id="8e36e-106">Using the StatusBar Control</span></span>  
 <span data-ttu-id="8e36e-107">Internet Explorer utiliza una barra de estado para indicar la dirección URL de una página cuando el mouse pasa sobre el hipervínculo; [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] ofrece información sobre la ubicación de la página, la ubicación de sección y modos de edición, como sobrescribir y seguimiento de revisiones; y Visual Studio usa la barra de estado para ofrecer información contextual, por ejemplo, que le indica cómo manipular las ventanas acoplables como acoplada o flotante.</span><span class="sxs-lookup"><span data-stu-id="8e36e-107">Internet Explorer uses a status bar to indicate the URL of a page when the mouse rolls over the hyperlink; [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] gives you information on page location, section location, and editing modes such as overtype and revision tracking; and Visual Studio uses the status bar to give context-sensitive information, such as telling you how to manipulate dockable windows as either docked or floating.</span></span>  
  
 <span data-ttu-id="8e36e-108">También puede mostrar un único mensaje en la barra de estado estableciendo el <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> propiedad a `false` (valor predeterminado) y estableciendo el <xref:System.Windows.Forms.StatusBar.Text%2A> propiedad de la barra de estado para el texto que desea que aparezcan en la barra de estado.</span><span class="sxs-lookup"><span data-stu-id="8e36e-108">You can display a single message on the status bar by setting the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `false` (the default) and setting the <xref:System.Windows.Forms.StatusBar.Text%2A> property of the status bar to the text you want to appear in the status bar.</span></span> <span data-ttu-id="8e36e-109">Puede dividir la barra de estado en paneles para mostrar más de un tipo de información estableciendo la <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> propiedad `true` y el uso de la <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> método de <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.</span><span class="sxs-lookup"><span data-stu-id="8e36e-109">You can divide the status bar into panels to display more than one type of information by setting the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `true` and using the <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> method of <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e36e-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="8e36e-110">See Also</span></span>  
 <xref:System.Windows.Forms.StatusBar>  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 [<span data-ttu-id="8e36e-111">Determinar en qué panel del control StatusBar de Windows Forms se hizo clic</span><span class="sxs-lookup"><span data-stu-id="8e36e-111">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)
