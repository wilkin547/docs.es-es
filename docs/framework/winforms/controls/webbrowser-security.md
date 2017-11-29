---
title: Seguridad de WebBrowser
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WebBrowser control [Windows Forms], security
- security [Windows Forms], WebBrowser control
ms.assetid: 0968846e-48ee-485a-9797-65b5b9a622f8
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a0d84f0c70619324bbbd38a2961914f88ac42671
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="webbrowser-security"></a><span data-ttu-id="82ac5-102">Seguridad de WebBrowser</span><span class="sxs-lookup"><span data-stu-id="82ac5-102">WebBrowser Security</span></span>
<span data-ttu-id="82ac5-103">El <xref:System.Windows.Forms.WebBrowser> control está diseñado para funcionar sólo en plena confianza.</span><span class="sxs-lookup"><span data-stu-id="82ac5-103">The <xref:System.Windows.Forms.WebBrowser> control is designed to work in full trust only.</span></span> <span data-ttu-id="82ac5-104">El contenido HTML mostrado en el control puede proceder de servidores Web externos y puede contener código no administrado en forma de scripts o controles Web.</span><span class="sxs-lookup"><span data-stu-id="82ac5-104">The HTML content displayed in the control can come from external Web servers and may contain unmanaged code in the form of scripts or Web controls.</span></span> <span data-ttu-id="82ac5-105">Si usas el <xref:System.Windows.Forms.WebBrowser> control en esta situación, el control no es menos seguro que sería Internet Explorer, pero los recursos administrados <xref:System.Windows.Forms.WebBrowser> control impedir que se ejecute este código no administrado.</span><span class="sxs-lookup"><span data-stu-id="82ac5-105">If you use the <xref:System.Windows.Forms.WebBrowser> control in this situation, the control is no less secure than Internet Explorer would be, but the managed <xref:System.Windows.Forms.WebBrowser> control does not prevent such unmanaged code from running.</span></span>  
  
 <span data-ttu-id="82ac5-106">Para obtener más información acerca de los problemas de seguridad relativos a ActiveX subyacente `WebBrowser` control, vea [WebBrowser (Control)](http://go.microsoft.com/fwlink/?LinkId=198812).</span><span class="sxs-lookup"><span data-stu-id="82ac5-106">For more information about security issues relating to the underlying ActiveX `WebBrowser` control, see [WebBrowser Control](http://go.microsoft.com/fwlink/?LinkId=198812).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82ac5-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="82ac5-107">See Also</span></span>  
 <xref:System.Windows.Forms.WebBrowser>  
 [<span data-ttu-id="82ac5-108">Información general sobre el control WebBrowser</span><span class="sxs-lookup"><span data-stu-id="82ac5-108">WebBrowser Control Overview</span></span>](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)  
 [<span data-ttu-id="82ac5-109">WebBrowser (control)</span><span class="sxs-lookup"><span data-stu-id="82ac5-109">WebBrowser Control</span></span>](http://go.microsoft.com/fwlink/?LinkId=198812)
