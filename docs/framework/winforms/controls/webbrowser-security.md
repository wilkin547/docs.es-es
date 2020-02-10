---
title: Seguridad de WebBrowser
ms.date: 03/30/2017
helpviewer_keywords:
- WebBrowser control [Windows Forms], security
- security [Windows Forms], WebBrowser control
ms.assetid: 0968846e-48ee-485a-9797-65b5b9a622f8
ms.openlocfilehash: b25cabca050d06dbfe97c563eb56622d1f21be54
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095260"
---
# <a name="webbrowser-security"></a><span data-ttu-id="10db2-102">Seguridad de WebBrowser</span><span class="sxs-lookup"><span data-stu-id="10db2-102">WebBrowser Security</span></span>
<span data-ttu-id="10db2-103">El control de <xref:System.Windows.Forms.WebBrowser> está diseñado para funcionar solo con plena confianza.</span><span class="sxs-lookup"><span data-stu-id="10db2-103">The <xref:System.Windows.Forms.WebBrowser> control is designed to work in full trust only.</span></span> <span data-ttu-id="10db2-104">El contenido HTML que se muestra en el control puede proviene de servidores web externos y puede contener código no administrado en forma de scripts o controles Web.</span><span class="sxs-lookup"><span data-stu-id="10db2-104">The HTML content displayed in the control can come from external Web servers and may contain unmanaged code in the form of scripts or Web controls.</span></span> <span data-ttu-id="10db2-105">Si usa el control <xref:System.Windows.Forms.WebBrowser> en esta situación, el control no es menos seguro que Internet Explorer, pero el control de <xref:System.Windows.Forms.WebBrowser> administrado no impide que se ejecute este código no administrado.</span><span class="sxs-lookup"><span data-stu-id="10db2-105">If you use the <xref:System.Windows.Forms.WebBrowser> control in this situation, the control is no less secure than Internet Explorer would be, but the managed <xref:System.Windows.Forms.WebBrowser> control does not prevent such unmanaged code from running.</span></span>  
  
 <span data-ttu-id="10db2-106">Para obtener más información acerca de los problemas de seguridad relacionados con el control de `WebBrowser` ActiveX subyacente, vea [control WebBrowser](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="10db2-106">For more information about security issues relating to the underlying ActiveX `WebBrowser` control, see [WebBrowser Control](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10db2-107">Consulte también</span><span class="sxs-lookup"><span data-stu-id="10db2-107">See also</span></span>

- <xref:System.Windows.Forms.WebBrowser>
- [<span data-ttu-id="10db2-108">Información general sobre el control WebBrowser</span><span class="sxs-lookup"><span data-stu-id="10db2-108">WebBrowser Control Overview</span></span>](webbrowser-control-overview.md)
- <span data-ttu-id="10db2-109">[WebBrowser (control)](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="10db2-109">[WebBrowser Control](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85))</span></span>
