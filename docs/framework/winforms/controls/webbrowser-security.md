---
title: Seguridad de WebBrowser
ms.date: 03/30/2017
helpviewer_keywords:
- WebBrowser control [Windows Forms], security
- security [Windows Forms], WebBrowser control
ms.assetid: 0968846e-48ee-485a-9797-65b5b9a622f8
ms.openlocfilehash: 957c11a085c971a81e5baa81a5b797dd53f2451a
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703438"
---
# <a name="webbrowser-security"></a>Seguridad de WebBrowser
El <xref:System.Windows.Forms.WebBrowser> control está diseñado para funcionar sólo en plena confianza. El contenido HTML mostrado en el control puede provenir de servidores Web externos y puede contener código no administrado en forma de secuencias de comandos o controles Web. Si usas el <xref:System.Windows.Forms.WebBrowser> control en esta situación, el control es no menos segura de Internet Explorer sería, pero los recursos administrados <xref:System.Windows.Forms.WebBrowser> control no impide que se ejecuta este código no administrado.  
  
 Para obtener más información acerca de los problemas de seguridad relativos a ActiveX subyacente `WebBrowser` control, vea [WebBrowser Control](https://go.microsoft.com/fwlink/?LinkId=198812).  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.WebBrowser>
- [Información general sobre el control WebBrowser](webbrowser-control-overview.md)
- [WebBrowser (control)](https://go.microsoft.com/fwlink/?LinkId=198812)
