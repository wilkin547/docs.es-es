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
# <a name="webbrowser-security"></a>Seguridad de WebBrowser
El control de <xref:System.Windows.Forms.WebBrowser> está diseñado para funcionar solo con plena confianza. El contenido HTML que se muestra en el control puede proviene de servidores web externos y puede contener código no administrado en forma de scripts o controles Web. Si usa el control <xref:System.Windows.Forms.WebBrowser> en esta situación, el control no es menos seguro que Internet Explorer, pero el control de <xref:System.Windows.Forms.WebBrowser> administrado no impide que se ejecute este código no administrado.  
  
 Para obtener más información acerca de los problemas de seguridad relacionados con el control de `WebBrowser` ActiveX subyacente, vea [control WebBrowser](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85)).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.WebBrowser>
- [Información general sobre el control WebBrowser](webbrowser-control-overview.md)
- [WebBrowser (control)](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85))
