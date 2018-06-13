---
title: Seguridad de WebBrowser
ms.date: 03/30/2017
helpviewer_keywords:
- WebBrowser control [Windows Forms], security
- security [Windows Forms], WebBrowser control
ms.assetid: 0968846e-48ee-485a-9797-65b5b9a622f8
ms.openlocfilehash: 730d8f692a44a06ea142bb870bbd961d5983c785
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33534617"
---
# <a name="webbrowser-security"></a><span data-ttu-id="9e423-102">Seguridad de WebBrowser</span><span class="sxs-lookup"><span data-stu-id="9e423-102">WebBrowser Security</span></span>
<span data-ttu-id="9e423-103">El <xref:System.Windows.Forms.WebBrowser> control está diseñado para funcionar sólo en plena confianza.</span><span class="sxs-lookup"><span data-stu-id="9e423-103">The <xref:System.Windows.Forms.WebBrowser> control is designed to work in full trust only.</span></span> <span data-ttu-id="9e423-104">El contenido HTML mostrado en el control puede proceder de servidores Web externos y puede contener código no administrado en forma de scripts o controles Web.</span><span class="sxs-lookup"><span data-stu-id="9e423-104">The HTML content displayed in the control can come from external Web servers and may contain unmanaged code in the form of scripts or Web controls.</span></span> <span data-ttu-id="9e423-105">Si usas el <xref:System.Windows.Forms.WebBrowser> control en esta situación, el control no es menos seguro que sería Internet Explorer, pero los recursos administrados <xref:System.Windows.Forms.WebBrowser> control impedir que se ejecute este código no administrado.</span><span class="sxs-lookup"><span data-stu-id="9e423-105">If you use the <xref:System.Windows.Forms.WebBrowser> control in this situation, the control is no less secure than Internet Explorer would be, but the managed <xref:System.Windows.Forms.WebBrowser> control does not prevent such unmanaged code from running.</span></span>  
  
 <span data-ttu-id="9e423-106">Para obtener más información acerca de los problemas de seguridad relativos a ActiveX subyacente `WebBrowser` control, vea [WebBrowser (Control)](http://go.microsoft.com/fwlink/?LinkId=198812).</span><span class="sxs-lookup"><span data-stu-id="9e423-106">For more information about security issues relating to the underlying ActiveX `WebBrowser` control, see [WebBrowser Control](http://go.microsoft.com/fwlink/?LinkId=198812).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e423-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e423-107">See Also</span></span>  
 <xref:System.Windows.Forms.WebBrowser>  
 [<span data-ttu-id="9e423-108">Información general sobre el control WebBrowser</span><span class="sxs-lookup"><span data-stu-id="9e423-108">WebBrowser Control Overview</span></span>](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)  
 [<span data-ttu-id="9e423-109">WebBrowser (control)</span><span class="sxs-lookup"><span data-stu-id="9e423-109">WebBrowser Control</span></span>](http://go.microsoft.com/fwlink/?LinkId=198812)
