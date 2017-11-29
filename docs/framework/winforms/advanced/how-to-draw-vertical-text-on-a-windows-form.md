---
title: "Cómo: Dibujar texto vertical en Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- StringFormat.FormatFlags
- Graphics.DrawString
helpviewer_keywords:
- text [Windows Forms], drawing vertical
- strings [Windows Forms], drawing vertical
- text [Windows Forms], drawing
- text [Windows Forms], vertical text
ms.assetid: 717a6131-00f6-4373-b574-9894e8317799
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 76da7be50f9e12454e16e08ec4db494585fae613
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-vertical-text-on-a-windows-form"></a><span data-ttu-id="6a559-102">Cómo: Dibujar texto vertical en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6a559-102">How to: Draw Vertical Text on a Windows Form</span></span>
<span data-ttu-id="6a559-103">En el ejemplo de código siguiente se muestra cómo dibujar texto vertical en un formulario mediante el uso de la <xref:System.Drawing.Graphics.DrawString%2A> método <xref:System.Drawing.Graphics>.</span><span class="sxs-lookup"><span data-stu-id="6a559-103">The following code example shows how to draw vertical text on a form by using the <xref:System.Drawing.Graphics.DrawString%2A> method of <xref:System.Drawing.Graphics>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a559-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6a559-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#8](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#8)]
 [!code-csharp[System.Drawing.ConceptualHowTos#8](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#8)]
 [!code-vb[System.Drawing.ConceptualHowTos#8](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#8)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6a559-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="6a559-105">Compiling the Code</span></span>  
 <span data-ttu-id="6a559-106">No se puede llamar a este método el <xref:System.Windows.Forms.Form.Load> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="6a559-106">You cannot call this method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="6a559-107">No se volverá a dibujar el contenido dibujado si el formulario cambia de tamaño o lo ocultan con otra forma.</span><span class="sxs-lookup"><span data-stu-id="6a559-107">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="6a559-108">Para que el contenido automáticamente volver a dibujar, debe invalidar el <xref:System.Windows.Forms.Control.OnPaint%2A> método.</span><span class="sxs-lookup"><span data-stu-id="6a559-108">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="6a559-109">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="6a559-109">Robust Programming</span></span>  
 <span data-ttu-id="6a559-110">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="6a559-110">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="6a559-111">La fuente Arial no está instalada.</span><span class="sxs-lookup"><span data-stu-id="6a559-111">The Arial font is not installed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a559-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="6a559-112">See Also</span></span>  
 <xref:System.Drawing.Graphics.DrawString%2A>  
 <xref:System.Drawing.StringFormat.FormatFlags%2A>  
 <xref:System.Drawing.StringFormatFlags>  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 [<span data-ttu-id="6a559-113">Introducción a la programación de gráficos</span><span class="sxs-lookup"><span data-stu-id="6a559-113">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [<span data-ttu-id="6a559-114">Utilizar fuentes y texto</span><span class="sxs-lookup"><span data-stu-id="6a559-114">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
