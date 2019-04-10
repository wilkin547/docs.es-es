---
title: Seguridad de WebBrowser
ms.date: 03/30/2017
helpviewer_keywords:
- WebBrowser control [Windows Forms], security
- security [Windows Forms], WebBrowser control
ms.assetid: 0968846e-48ee-485a-9797-65b5b9a622f8
ms.openlocfilehash: 1e658c25ea19f966ac67402c6f3c7693c784d029
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59214019"
---
# <a name="webbrowser-security"></a><span data-ttu-id="bc9e5-102">Seguridad de WebBrowser</span><span class="sxs-lookup"><span data-stu-id="bc9e5-102">WebBrowser Security</span></span>
<span data-ttu-id="bc9e5-103">El <xref:System.Windows.Forms.WebBrowser> control está diseñado para funcionar sólo en plena confianza.</span><span class="sxs-lookup"><span data-stu-id="bc9e5-103">The <xref:System.Windows.Forms.WebBrowser> control is designed to work in full trust only.</span></span> <span data-ttu-id="bc9e5-104">El contenido HTML mostrado en el control puede provenir de servidores Web externos y puede contener código no administrado en forma de secuencias de comandos o controles Web.</span><span class="sxs-lookup"><span data-stu-id="bc9e5-104">The HTML content displayed in the control can come from external Web servers and may contain unmanaged code in the form of scripts or Web controls.</span></span> <span data-ttu-id="bc9e5-105">Si usas el <xref:System.Windows.Forms.WebBrowser> control en esta situación, el control es no menos segura de Internet Explorer sería, pero los recursos administrados <xref:System.Windows.Forms.WebBrowser> control no impide que se ejecuta este código no administrado.</span><span class="sxs-lookup"><span data-stu-id="bc9e5-105">If you use the <xref:System.Windows.Forms.WebBrowser> control in this situation, the control is no less secure than Internet Explorer would be, but the managed <xref:System.Windows.Forms.WebBrowser> control does not prevent such unmanaged code from running.</span></span>  
  
 <span data-ttu-id="bc9e5-106">Para obtener más información acerca de los problemas de seguridad relativos a ActiveX subyacente `WebBrowser` control, vea [WebBrowser Control](https://go.microsoft.com/fwlink/?LinkId=198812).</span><span class="sxs-lookup"><span data-stu-id="bc9e5-106">For more information about security issues relating to the underlying ActiveX `WebBrowser` control, see [WebBrowser Control](https://go.microsoft.com/fwlink/?LinkId=198812).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc9e5-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="bc9e5-107">See also</span></span>

- <xref:System.Windows.Forms.WebBrowser>
- [<span data-ttu-id="bc9e5-108">Información general sobre el control WebBrowser</span><span class="sxs-lookup"><span data-stu-id="bc9e5-108">WebBrowser Control Overview</span></span>](webbrowser-control-overview.md)
- [<span data-ttu-id="bc9e5-109">WebBrowser (Control)</span><span class="sxs-lookup"><span data-stu-id="bc9e5-109">WebBrowser Control</span></span>](https://go.microsoft.com/fwlink/?LinkId=198812)
