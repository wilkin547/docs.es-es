---
title: Procedimiento para desplazarse a una dirección URL con el control WebBrowser
ms.date: 03/30/2017
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
ms.openlocfilehash: bee16a388d823f74bc9c88bc34b510d2a5907393
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64649221"
---
# <a name="how-to-navigate-to-a-url-with-the-webbrowser-control"></a>Procedimiento para desplazarse a una dirección URL con el control WebBrowser
En el ejemplo de código siguiente se muestra cómo navegar hasta el <xref:System.Windows.Forms.WebBrowser> control a una dirección URL específica.  
  
 Para determinar cuándo se ha cargado completamente el documento nuevo, controle el <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> eventos. Para ver una demostración de este evento, vea [Cómo: Impresión con un Control WebBrowser](how-to-print-with-a-webbrowser-control.md).  
  
## <a name="example"></a>Ejemplo  
  
```vb  
Me.webBrowser1.Navigate("http://www.microsoft.com")  
```  
  
```csharp  
this.webBrowser1.Navigate("http://www.microsoft.com");  
```  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
- Control <xref:System.Windows.Forms.WebBrowser> denominado `webBrowser1`.  
  
- Referencias a los ensamblados `System` y `System.Windows.Forms`.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.DocumentCompleted?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigating?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigated?displayProperty=nameWithType>
- [WebBrowser (control)](webbrowser-control-windows-forms.md)
- [Cómo: Imprimir con un Control WebBrowser](how-to-print-with-a-webbrowser-control.md)
