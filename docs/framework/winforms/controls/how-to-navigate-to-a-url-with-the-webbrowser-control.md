---
title: "Cómo: Desplazarse a una dirección URL con el control WebBrowser"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
f1_keywords:
- WebBrowser.Navigate
helpviewer_keywords:
- WebBrowser control [Windows Forms], examples
- URLs [Windows Forms], navigating to
- WebBrowser control [Windows Forms], navigating to URLs
- examples [Windows Forms], WebBrowser control
ms.assetid: b3ec38cb-f509-4d0b-bd79-9f3611259c62
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a447d69eb6dafbff75ddd9d161abd4f78c607cdd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-navigate-to-a-url-with-the-webbrowser-control"></a>Cómo: Desplazarse a una dirección URL con el control WebBrowser
En el ejemplo de código siguiente se muestra cómo navegar hasta el <xref:System.Windows.Forms.WebBrowser> control a una dirección URL específica.  
  
 Para determinar cuándo se ha cargado completamente el nuevo documento, controle el <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> eventos. Para ver una demostración de este evento, vea [Cómo: imprimir con un WebBrowser Control](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md).  
  
## <a name="example"></a>Ejemplo  
  
```vb  
Me.webBrowser1.Navigate("http://www.microsoft.com")  
```  
  
```csharp  
this.webBrowser1.Navigate("http://www.microsoft.com");  
```  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Control <xref:System.Windows.Forms.WebBrowser> denominado `webBrowser1`.  
  
-   Referencias a los ensamblados `System` y `System.Windows.Forms`.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.WebBrowser>  
 <xref:System.Windows.Forms.WebBrowser.DocumentCompleted?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.WebBrowser.Navigating?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.WebBrowser.Navigated?displayProperty=nameWithType>  
 [WebBrowser (control)](../../../../docs/framework/winforms/controls/webbrowser-control-windows-forms.md)  
 [Imprimir con un control WebBrowser](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md)
