---
title: "Cómo: Dibujar un rectángulo relleno en Windows Forms"
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
- cpp
f1_keywords:
- Graphics.FillRectangle
helpviewer_keywords:
- drawing [Windows Forms], rectangles
- rectangles [Windows Forms], drawing
- drawing rectangles
ms.assetid: d656a93c-987d-4809-aafd-493fe17450f0
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 17d143c0c265fea876d084ebc21663d93553fe9d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-a-filled-rectangle-on-a-windows-form"></a><span data-ttu-id="d5922-102">Cómo: Dibujar un rectángulo relleno en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d5922-102">How to: Draw a Filled Rectangle on a Windows Form</span></span>
<span data-ttu-id="d5922-103">En este ejemplo se dibuja un rectángulo relleno en un formulario.</span><span class="sxs-lookup"><span data-stu-id="d5922-103">This example draws a filled rectangle on a form.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5922-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d5922-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#2](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#2)]
 [!code-csharp[System.Drawing.ConceptualHowTos#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#2)]
 [!code-vb[System.Drawing.ConceptualHowTos#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#2)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d5922-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="d5922-105">Compiling the Code</span></span>  
 <span data-ttu-id="d5922-106">No se puede llamar a este método el <xref:System.Windows.Forms.Form.Load> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="d5922-106">You cannot call this method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="d5922-107">No se volverá a dibujar el contenido dibujado si el formulario cambia de tamaño o lo ocultan con otra forma.</span><span class="sxs-lookup"><span data-stu-id="d5922-107">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="d5922-108">Para que el contenido automáticamente volver a dibujar, debe invalidar el <xref:System.Windows.Forms.Control.OnPaint%2A> método.</span><span class="sxs-lookup"><span data-stu-id="d5922-108">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="d5922-109">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="d5922-109">Robust Programming</span></span>  
 <span data-ttu-id="d5922-110">Siempre debe llamar a <xref:System.IDisposable.Dispose%2A> en los objetos que consumen recursos del sistema, como <xref:System.Drawing.Brush> y <xref:System.Drawing.Graphics> objetos.</span><span class="sxs-lookup"><span data-stu-id="d5922-110">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Brush> and <xref:System.Drawing.Graphics> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5922-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5922-111">See Also</span></span>  
 <xref:System.Drawing.Graphics.FillRectangle%2A>  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 [<span data-ttu-id="d5922-112">Introducción a la programación de gráficos</span><span class="sxs-lookup"><span data-stu-id="d5922-112">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [<span data-ttu-id="d5922-113">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d5922-113">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="d5922-114">Utilizar lápiz para dibujar líneas y formas</span><span class="sxs-lookup"><span data-stu-id="d5922-114">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [<span data-ttu-id="d5922-115">Pinceles y formas rellenas en GDI+</span><span class="sxs-lookup"><span data-stu-id="d5922-115">Brushes and Filled Shapes in GDI+</span></span>](../../../../docs/framework/winforms/advanced/brushes-and-filled-shapes-in-gdi.md)
