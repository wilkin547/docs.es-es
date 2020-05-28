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
ms.openlocfilehash: f6cb26ff247bba75cc351d453314bade2d38d9f5
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144843"
---
# <a name="how-to-navigate-to-a-url-with-the-webbrowser-control"></a>Procedimiento para desplazarse a una dirección URL con el control WebBrowser
En el ejemplo de código siguiente se muestra cómo navegar por el <xref:System.Windows.Forms.WebBrowser> control a una dirección URL específica.

 Para determinar cuándo se carga completamente el nuevo documento, controle el <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> evento. Para ver una demostración de este evento, vea [Cómo: imprimir con un control WebBrowser](how-to-print-with-a-webbrowser-control.md).

## <a name="example"></a>Ejemplo

```vb
Me.webBrowser1.Navigate("https://www.microsoft.com")
```

```csharp
this.webBrowser1.Navigate("https://www.microsoft.com");
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
- [WebBrowser (Control)](webbrowser-control-windows-forms.md)
- [Procedimiento para imprimir con un control WebBrowser](how-to-print-with-a-webbrowser-control.md)
