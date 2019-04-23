---
title: Seguridad de WebBrowser
ms.date: 03/30/2017
helpviewer_keywords:
- WebBrowser control [Windows Forms], security
- security [Windows Forms], WebBrowser control
ms.assetid: 0968846e-48ee-485a-9797-65b5b9a622f8
ms.openlocfilehash: 1e658c25ea19f966ac67402c6f3c7693c784d029
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59214019"
---
# <a name="webbrowser-security"></a>Seguridad de WebBrowser
El <xref:System.Windows.Forms.WebBrowser> control está diseñado para funcionar sólo en plena confianza. El contenido HTML mostrado en el control puede provenir de servidores Web externos y puede contener código no administrado en forma de secuencias de comandos o controles Web. Si usas el <xref:System.Windows.Forms.WebBrowser> control en esta situación, el control es no menos segura de Internet Explorer sería, pero los recursos administrados <xref:System.Windows.Forms.WebBrowser> control no impide que se ejecuta este código no administrado.  
  
 Para obtener más información acerca de los problemas de seguridad relativos a ActiveX subyacente `WebBrowser` control, vea [WebBrowser Control](https://go.microsoft.com/fwlink/?LinkId=198812).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.WebBrowser>
- [Información general sobre el control WebBrowser](webbrowser-control-overview.md)
- [WebBrowser (control)](https://go.microsoft.com/fwlink/?LinkId=198812)
