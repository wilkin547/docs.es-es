---
title: Filtrar Dibujar un rectángulo relleno en un formulario de Windows
ms.date: 03/30/2017
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
ms.openlocfilehash: 53fab93f47c16257b5ab2e336b43c6133a31d509
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57716899"
---
# <a name="how-to-draw-a-filled-rectangle-on-a-windows-form"></a><span data-ttu-id="73f9c-102">Procedimiento Dibujar un rectángulo relleno en un formulario de Windows</span><span class="sxs-lookup"><span data-stu-id="73f9c-102">How to: Draw a Filled Rectangle on a Windows Form</span></span>
<span data-ttu-id="73f9c-103">En este ejemplo se dibuja un rectángulo relleno en un formulario.</span><span class="sxs-lookup"><span data-stu-id="73f9c-103">This example draws a filled rectangle on a form.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73f9c-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="73f9c-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#2](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#2)]
 [!code-csharp[System.Drawing.ConceptualHowTos#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#2)]
 [!code-vb[System.Drawing.ConceptualHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#2)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="73f9c-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="73f9c-105">Compiling the Code</span></span>  
 <span data-ttu-id="73f9c-106">No se puede llamar a este método el <xref:System.Windows.Forms.Form.Load> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="73f9c-106">You cannot call this method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="73f9c-107">No se volverá a dibujar el contenido dibujado si el formulario cambia de tamaño u ocultado por otro formulario.</span><span class="sxs-lookup"><span data-stu-id="73f9c-107">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="73f9c-108">Para que el contenido automáticamente volver a dibujar, se debe reemplazar el <xref:System.Windows.Forms.Control.OnPaint%2A> método.</span><span class="sxs-lookup"><span data-stu-id="73f9c-108">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="73f9c-109">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="73f9c-109">Robust Programming</span></span>  
 <span data-ttu-id="73f9c-110">Siempre debe llamar a <xref:System.IDisposable.Dispose%2A> en los objetos que consuman recursos del sistema, como <xref:System.Drawing.Brush> y <xref:System.Drawing.Graphics> objetos.</span><span class="sxs-lookup"><span data-stu-id="73f9c-110">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Brush> and <xref:System.Drawing.Graphics> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73f9c-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="73f9c-111">See also</span></span>
- <xref:System.Drawing.Graphics.FillRectangle%2A>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [<span data-ttu-id="73f9c-112">Introducción a la programación de gráficos</span><span class="sxs-lookup"><span data-stu-id="73f9c-112">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="73f9c-113">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="73f9c-113">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="73f9c-114">Utilizar lápiz para dibujar líneas y formas</span><span class="sxs-lookup"><span data-stu-id="73f9c-114">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="73f9c-115">Pinceles y formas rellenas en GDI+</span><span class="sxs-lookup"><span data-stu-id="73f9c-115">Brushes and Filled Shapes in GDI+</span></span>](brushes-and-filled-shapes-in-gdi.md)
