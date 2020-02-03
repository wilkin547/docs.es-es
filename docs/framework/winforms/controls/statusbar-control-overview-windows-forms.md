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
# <a name="statusbar-control-overview-windows-forms"></a><span data-ttu-id="57f96-102">Información general sobre StatusBar (Control, formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="57f96-102">StatusBar Control Overview (Windows Forms)</span></span>
> [!IMPORTANT]
> <span data-ttu-id="57f96-103">Los controles <xref:System.Windows.Forms.StatusStrip> y <xref:System.Windows.Forms.ToolStripStatusLabel> reemplazan y agregan funcionalidad a los controles <xref:System.Windows.Forms.StatusBar> y <xref:System.Windows.Forms.StatusBarPanel>; sin embargo, los controles <xref:System.Windows.Forms.StatusBar> y <xref:System.Windows.Forms.StatusBarPanel> se conservan por compatibilidad con versiones anteriores y uso futuro, si así lo decide.</span><span class="sxs-lookup"><span data-stu-id="57f96-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="57f96-104">El Windows Forms [control StatusBar](statusbar-control-windows-forms.md) se usa en los formularios como un área, que normalmente se muestra en la parte inferior de una ventana, en la que una aplicación puede mostrar diversos tipos de información de estado.</span><span class="sxs-lookup"><span data-stu-id="57f96-104">The Windows Forms [StatusBar Control](statusbar-control-windows-forms.md) is used on forms as an area, usually displayed at the bottom of a window, in which an application can display various kinds of status information.</span></span> <span data-ttu-id="57f96-105"><xref:System.Windows.Forms.StatusBar> controles pueden tener paneles de barra de estado en ellos que muestren texto o iconos para indicar el estado o una serie de iconos de una animación que indiquen que un proceso está funcionando; por ejemplo, Microsoft Word indica que el documento se está guardando.</span><span class="sxs-lookup"><span data-stu-id="57f96-105"><xref:System.Windows.Forms.StatusBar> controls can have status bar panels on them that display text or icons to indicate state, or a series of icons in an animation that indicate a process is working; for example, Microsoft Word indicating that the document is being saved.</span></span>  
  
## <a name="using-the-statusbar-control"></a><span data-ttu-id="57f96-106">Usar el control StatusBar</span><span class="sxs-lookup"><span data-stu-id="57f96-106">Using the StatusBar Control</span></span>  
 <span data-ttu-id="57f96-107">Internet Explorer usa una barra de estado para indicar la dirección URL de una página cuando el mouse se sitúa sobre el hipervínculo; Microsoft Word le proporciona información sobre la ubicación de la página, la ubicación de la sección y los modos de edición como sobreescribir y seguimiento de la revisión. y Visual Studio usa la barra de estado para proporcionar información contextual, como indicar cómo manipular las ventanas acoplables como acopladas o flotantes.</span><span class="sxs-lookup"><span data-stu-id="57f96-107">Internet Explorer uses a status bar to indicate the URL of a page when the mouse rolls over the hyperlink; Microsoft Word gives you information on page location, section location, and editing modes such as overtype and revision tracking; and Visual Studio uses the status bar to give context-sensitive information, such as telling you how to manipulate dockable windows as either docked or floating.</span></span>  
  
 <span data-ttu-id="57f96-108">Puede mostrar un solo mensaje en la barra de estado si establece la propiedad <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> en `false` (valor predeterminado) y establece la propiedad <xref:System.Windows.Forms.StatusBar.Text%2A> de la barra de estado en el texto que desea que aparezca en la barra de estado.</span><span class="sxs-lookup"><span data-stu-id="57f96-108">You can display a single message on the status bar by setting the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `false` (the default) and setting the <xref:System.Windows.Forms.StatusBar.Text%2A> property of the status bar to the text you want to appear in the status bar.</span></span> <span data-ttu-id="57f96-109">Puede dividir la barra de estado en paneles para mostrar más de un tipo de información estableciendo la propiedad <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> en `true` y usando el método <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> de <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.</span><span class="sxs-lookup"><span data-stu-id="57f96-109">You can divide the status bar into panels to display more than one type of information by setting the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `true` and using the <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> method of <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57f96-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="57f96-110">See also</span></span>

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [<span data-ttu-id="57f96-111">Determinar en qué panel del control StatusBar de Windows Forms se hizo clic</span><span class="sxs-lookup"><span data-stu-id="57f96-111">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](determine-which-panel-wf-statusbar-control-was-clicked.md)
