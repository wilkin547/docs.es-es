---
title: Procedimiento Dibujar una elipse con relleno en un formulario de Windows
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Graphics.FillEllipse
helpviewer_keywords:
- ellipses [Windows Forms], drawing
- circles [Windows Forms], drawing
- circular shapes
- drawing [Windows Forms], ellipses
- shapes [Windows Forms], drawing
- forms [Windows Forms], drawing ellipses
ms.assetid: 781db806-950d-4c5b-b022-493f7fd0c4a8
ms.openlocfilehash: 42316cd0d55b5154b21b4462157e044b30674ebd
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57716301"
---
# <a name="how-to-draw-a-filled-ellipse-on-a-windows-form"></a><span data-ttu-id="cbe7a-102">Procedimiento Dibujar una elipse con relleno en un formulario de Windows</span><span class="sxs-lookup"><span data-stu-id="cbe7a-102">How to: Draw a Filled Ellipse on a Windows Form</span></span>
<span data-ttu-id="cbe7a-103">En este ejemplo se dibuja una elipse con relleno en un formulario.</span><span class="sxs-lookup"><span data-stu-id="cbe7a-103">This example draws a filled ellipse on a form.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cbe7a-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cbe7a-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#1)]
 [!code-csharp[System.Drawing.ConceptualHowTos#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#1)]
 [!code-vb[System.Drawing.ConceptualHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cbe7a-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="cbe7a-105">Compiling the Code</span></span>  
 <span data-ttu-id="cbe7a-106">No se puede llamar a este método el <xref:System.Windows.Forms.Form.Load> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="cbe7a-106">You cannot call this method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="cbe7a-107">No se volverá a dibujar el contenido dibujado si el formulario cambia de tamaño u ocultado por otro formulario.</span><span class="sxs-lookup"><span data-stu-id="cbe7a-107">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="cbe7a-108">Para que el contenido automáticamente volver a dibujar, se debe reemplazar el <xref:System.Windows.Forms.Control.OnPaint%2A> método.</span><span class="sxs-lookup"><span data-stu-id="cbe7a-108">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="cbe7a-109">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="cbe7a-109">Robust Programming</span></span>  
 <span data-ttu-id="cbe7a-110">Siempre debe llamar a <xref:System.IDisposable.Dispose%2A> en los objetos que consuman recursos del sistema, como <xref:System.Drawing.Brush> y <xref:System.Drawing.Graphics> objetos.</span><span class="sxs-lookup"><span data-stu-id="cbe7a-110">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Brush> and <xref:System.Drawing.Graphics> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbe7a-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="cbe7a-111">See also</span></span>
- [<span data-ttu-id="cbe7a-112">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cbe7a-112">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="cbe7a-113">Introducción a la programación de gráficos</span><span class="sxs-lookup"><span data-stu-id="cbe7a-113">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="cbe7a-114">Líneas y rellenos con combinación alfa</span><span class="sxs-lookup"><span data-stu-id="cbe7a-114">Alpha Blending Lines and Fills</span></span>](alpha-blending-lines-and-fills.md)
- [<span data-ttu-id="cbe7a-115">Utilizar un pincel para rellenar formas</span><span class="sxs-lookup"><span data-stu-id="cbe7a-115">Using a Brush to Fill Shapes</span></span>](using-a-brush-to-fill-shapes.md)
