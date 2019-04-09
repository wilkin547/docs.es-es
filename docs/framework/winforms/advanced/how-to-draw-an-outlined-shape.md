---
title: Filtrar para dibujar una forma con contorno
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Graphics.DrawEllipse
helpviewer_keywords:
- ellipses [Windows Forms], drawing
- circles [Windows Forms], drawing
- drawing [Windows Forms], shapes
- circular shapes
- forms [Windows Forms], drawing circular shapes
- circles
- outlined shapes [Windows Forms], examples
- outlined shapes [Windows Forms], drawing
- drawing [Windows Forms], circular shapes
- shapes [Windows Forms], drawing
ms.assetid: f4f9214c-607e-407d-8cdd-6549f0278451
ms.openlocfilehash: 019bbc19cc4b26c42f8539eccd93ec4ff87fab12
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59192214"
---
# <a name="how-to-draw-an-outlined-shape"></a><span data-ttu-id="b4692-102">Filtrar para dibujar una forma con contorno</span><span class="sxs-lookup"><span data-stu-id="b4692-102">How to: Draw an Outlined Shape</span></span>
<span data-ttu-id="b4692-103">En este ejemplo se dibuja elipses con contorno y rectángulos en un formulario.</span><span class="sxs-lookup"><span data-stu-id="b4692-103">This example draws outlined ellipses and rectangles on a form.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4692-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b4692-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#6](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#6)]
 [!code-csharp[System.Drawing.ConceptualHowTos#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#6)]
 [!code-vb[System.Drawing.ConceptualHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#6)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b4692-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="b4692-105">Compiling the Code</span></span>  
 <span data-ttu-id="b4692-106">No se puede llamar a este método el <xref:System.Windows.Forms.Form.Load> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="b4692-106">You cannot call this method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="b4692-107">No se volverá a dibujar el contenido dibujado si el formulario cambia de tamaño u ocultado por otro formulario.</span><span class="sxs-lookup"><span data-stu-id="b4692-107">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="b4692-108">Para que el contenido automáticamente volver a dibujar, se debe reemplazar el <xref:System.Windows.Forms.Control.OnPaint%2A> método.</span><span class="sxs-lookup"><span data-stu-id="b4692-108">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="b4692-109">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="b4692-109">Robust Programming</span></span>  
 <span data-ttu-id="b4692-110">Siempre debe llamar a <xref:System.IDisposable.Dispose%2A> en los objetos que consuman recursos del sistema, como <xref:System.Drawing.Pen> y <xref:System.Drawing.Graphics> objetos.</span><span class="sxs-lookup"><span data-stu-id="b4692-110">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Pen> and <xref:System.Drawing.Graphics> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4692-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4692-111">See also</span></span>

- <xref:System.Drawing.Graphics.DrawEllipse%2A>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- <xref:System.Drawing.Graphics.DrawRectangle%2A>
- [<span data-ttu-id="b4692-112">Introducción a la programación de gráficos</span><span class="sxs-lookup"><span data-stu-id="b4692-112">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="b4692-113">Utilizar lápiz para dibujar líneas y formas</span><span class="sxs-lookup"><span data-stu-id="b4692-113">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="b4692-114">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b4692-114">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
