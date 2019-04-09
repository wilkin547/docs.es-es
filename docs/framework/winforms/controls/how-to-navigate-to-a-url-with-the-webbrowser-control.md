---
title: Filtrar para desplazarse a una dirección URL con el control WebBrowser
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
ms.openlocfilehash: a174b6ae60f87e91e6f97e8fa7f8ad3892ef017a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59132943"
---
# <a name="how-to-navigate-to-a-url-with-the-webbrowser-control"></a><span data-ttu-id="822c9-102">Filtrar para desplazarse a una dirección URL con el control WebBrowser</span><span class="sxs-lookup"><span data-stu-id="822c9-102">How to: Navigate to a URL with the WebBrowser Control</span></span>
<span data-ttu-id="822c9-103">En el ejemplo de código siguiente se muestra cómo navegar hasta el <xref:System.Windows.Forms.WebBrowser> control a una dirección URL específica.</span><span class="sxs-lookup"><span data-stu-id="822c9-103">The following code example demonstrates how to navigate the <xref:System.Windows.Forms.WebBrowser> control to a specific URL.</span></span>  
  
 <span data-ttu-id="822c9-104">Para determinar cuándo se ha cargado completamente el documento nuevo, controle el <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> eventos.</span><span class="sxs-lookup"><span data-stu-id="822c9-104">To determine when the new document is fully loaded, handle the <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event.</span></span> <span data-ttu-id="822c9-105">Para ver una demostración de este evento, vea [Cómo: Impresión con un Control WebBrowser](how-to-print-with-a-webbrowser-control.md).</span><span class="sxs-lookup"><span data-stu-id="822c9-105">For a demonstration of this event, see [How to: Print with a WebBrowser Control](how-to-print-with-a-webbrowser-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="822c9-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="822c9-106">Example</span></span>  
  
```vb  
Me.webBrowser1.Navigate("http://www.microsoft.com")  
```  
  
```csharp  
this.webBrowser1.Navigate("http://www.microsoft.com");  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="822c9-107">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="822c9-107">Compiling the Code</span></span>  
 <span data-ttu-id="822c9-108">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="822c9-108">This example requires:</span></span>  
  
-   <span data-ttu-id="822c9-109">Control <xref:System.Windows.Forms.WebBrowser> denominado `webBrowser1`.</span><span class="sxs-lookup"><span data-stu-id="822c9-109">A <xref:System.Windows.Forms.WebBrowser> control named `webBrowser1`.</span></span>  
  
-   <span data-ttu-id="822c9-110">Referencias a los ensamblados `System` y `System.Windows.Forms`.</span><span class="sxs-lookup"><span data-stu-id="822c9-110">References to the `System` and `System.Windows.Forms` assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="822c9-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="822c9-111">See also</span></span>

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.DocumentCompleted?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigating?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigated?displayProperty=nameWithType>
- [<span data-ttu-id="822c9-112">WebBrowser (Control)</span><span class="sxs-lookup"><span data-stu-id="822c9-112">WebBrowser Control</span></span>](webbrowser-control-windows-forms.md)
- [<span data-ttu-id="822c9-113">Filtrar para imprimir con un control WebBrowser</span><span class="sxs-lookup"><span data-stu-id="822c9-113">How to: Print with a WebBrowser Control</span></span>](how-to-print-with-a-webbrowser-control.md)
