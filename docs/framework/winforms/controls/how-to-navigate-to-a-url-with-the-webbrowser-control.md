---
title: Procedimiento para desplazarse a una dirección URL con el control WebBrowser
description: Aprenda a usar el control Windows Forms WebBrowser. Navigate para navegar a una dirección URL específica. También aprenderá a determinar cuándo se carga el nuevo documento.
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
ms.openlocfilehash: e6ad360cc73a84ca040869832bb59d354cb78bd5
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325569"
---
# <a name="how-to-navigate-to-a-url-with-the-webbrowser-control"></a><span data-ttu-id="03e0c-104">Procedimiento para desplazarse a una dirección URL con el control WebBrowser</span><span class="sxs-lookup"><span data-stu-id="03e0c-104">How to: Navigate to a URL with the WebBrowser Control</span></span>
<span data-ttu-id="03e0c-105">En el ejemplo de código siguiente se muestra cómo navegar por el <xref:System.Windows.Forms.WebBrowser> control a una dirección URL específica.</span><span class="sxs-lookup"><span data-stu-id="03e0c-105">The following code example demonstrates how to navigate the <xref:System.Windows.Forms.WebBrowser> control to a specific URL.</span></span>

 <span data-ttu-id="03e0c-106">Para determinar cuándo se carga completamente el nuevo documento, controle el <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> evento.</span><span class="sxs-lookup"><span data-stu-id="03e0c-106">To determine when the new document is fully loaded, handle the <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event.</span></span> <span data-ttu-id="03e0c-107">Para ver una demostración de este evento, vea [Cómo: imprimir con un control WebBrowser](how-to-print-with-a-webbrowser-control.md).</span><span class="sxs-lookup"><span data-stu-id="03e0c-107">For a demonstration of this event, see [How to: Print with a WebBrowser Control](how-to-print-with-a-webbrowser-control.md).</span></span>

## <a name="example"></a><span data-ttu-id="03e0c-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="03e0c-108">Example</span></span>

```vb
Me.webBrowser1.Navigate("https://www.microsoft.com")
```

```csharp
this.webBrowser1.Navigate("https://www.microsoft.com");
```

## <a name="compiling-the-code"></a><span data-ttu-id="03e0c-109">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="03e0c-109">Compiling the Code</span></span>
 <span data-ttu-id="03e0c-110">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="03e0c-110">This example requires:</span></span>

- <span data-ttu-id="03e0c-111">Control <xref:System.Windows.Forms.WebBrowser> denominado `webBrowser1`.</span><span class="sxs-lookup"><span data-stu-id="03e0c-111">A <xref:System.Windows.Forms.WebBrowser> control named `webBrowser1`.</span></span>

- <span data-ttu-id="03e0c-112">Referencias a los ensamblados `System` y `System.Windows.Forms`.</span><span class="sxs-lookup"><span data-stu-id="03e0c-112">References to the `System` and `System.Windows.Forms` assemblies.</span></span>

## <a name="see-also"></a><span data-ttu-id="03e0c-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="03e0c-113">See also</span></span>

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.DocumentCompleted?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigating?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigated?displayProperty=nameWithType>
- [<span data-ttu-id="03e0c-114">WebBrowser (Control)</span><span class="sxs-lookup"><span data-stu-id="03e0c-114">WebBrowser Control</span></span>](webbrowser-control-windows-forms.md)
- [<span data-ttu-id="03e0c-115">Procedimiento para imprimir con un control WebBrowser</span><span class="sxs-lookup"><span data-stu-id="03e0c-115">How to: Print with a WebBrowser Control</span></span>](how-to-print-with-a-webbrowser-control.md)
