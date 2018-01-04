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
ms.workload: dotnet
ms.openlocfilehash: 3985fc9916b3e95e650502ef1f8dc301363b1f90
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="webbrowser-security"></a>Seguridad de WebBrowser
El <xref:System.Windows.Forms.WebBrowser> control está diseñado para funcionar sólo en plena confianza. El contenido HTML mostrado en el control puede proceder de servidores Web externos y puede contener código no administrado en forma de scripts o controles Web. Si usas el <xref:System.Windows.Forms.WebBrowser> control en esta situación, el control no es menos seguro que sería Internet Explorer, pero los recursos administrados <xref:System.Windows.Forms.WebBrowser> control impedir que se ejecute este código no administrado.  
  
 Para obtener más información acerca de los problemas de seguridad relativos a ActiveX subyacente `WebBrowser` control, vea [WebBrowser (Control)](http://go.microsoft.com/fwlink/?LinkId=198812).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.WebBrowser>  
 [Información general sobre el control WebBrowser](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)  
 [WebBrowser (control)](http://go.microsoft.com/fwlink/?LinkId=198812)
