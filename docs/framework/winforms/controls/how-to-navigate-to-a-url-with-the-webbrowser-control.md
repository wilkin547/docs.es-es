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
ms.openlocfilehash: b6c1255fa17d91daaa73001fea04f26e73dba0ae
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015826"
---
# <a name="how-to-navigate-to-a-url-with-the-webbrowser-control"></a>Procedimiento para desplazarse a una dirección URL con el control WebBrowser
En el ejemplo de código siguiente se muestra cómo <xref:System.Windows.Forms.WebBrowser> navegar por el control a una dirección URL específica.

 Para determinar cuándo se carga completamente el nuevo documento, controle <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> el evento. Para ver una demostración de este evento, [consulte Cómo: Imprimir con un control](how-to-print-with-a-webbrowser-control.md)WebBrowser.

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
- [Procedimientos: Imprimir con un control WebBrowser](how-to-print-with-a-webbrowser-control.md)
