---
title: Filtrar para dibujar una línea con extremos de línea
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drawing [Windows Forms], lines
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
- drawing lines [Windows Forms], line caps
ms.assetid: eb68c3e1-c400-4886-8a04-76978a429cb6
ms.openlocfilehash: c4a78569f6c0b14c32154611412d6b3ccd8a84ce
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59146216"
---
# <a name="how-to-draw-a-line-with-line-caps"></a><span data-ttu-id="e4fe2-102">Filtrar para dibujar una línea con extremos de línea</span><span class="sxs-lookup"><span data-stu-id="e4fe2-102">How to: Draw a Line with Line Caps</span></span>
<span data-ttu-id="e4fe2-103">Puede dibujar el inicio o final de una línea en una de varias formas llamadas extremos de línea.</span><span class="sxs-lookup"><span data-stu-id="e4fe2-103">You can draw the start or end of a line in one of several shapes called line caps.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="e4fe2-104">admite varios extremos de línea, como round, cuadrado, rombo y punta de flecha.</span><span class="sxs-lookup"><span data-stu-id="e4fe2-104">supports several line caps, such as round, square, diamond, and arrowhead.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4fe2-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e4fe2-105">Example</span></span>  
 <span data-ttu-id="e4fe2-106">Puede especificar extremos de línea para el inicio de una línea (extremo inicial), el final de una línea (extremo final) o los guiones de una línea discontinua (dash CAP.).</span><span class="sxs-lookup"><span data-stu-id="e4fe2-106">You can specify line caps for the start of a line (start cap), the end of a line (end cap), or the dashes of a dashed line (dash cap).</span></span>  
  
 <span data-ttu-id="e4fe2-107">El ejemplo siguiente dibuja una línea con una punta de flecha en un extremo y un extremo redondeado en el otro extremo.</span><span class="sxs-lookup"><span data-stu-id="e4fe2-107">The following example draws a line with an arrowhead at one end and a round cap at the other end.</span></span> <span data-ttu-id="e4fe2-108">La ilustración muestra la línea resultante:</span><span class="sxs-lookup"><span data-stu-id="e4fe2-108">The illustration shows the resulting line:</span></span>  
  
 ![Ilustración que muestra una línea con un extremo redondeado.](./media/how-to-draw-a-line-with-line-caps/line-cap-arrowhead-example.gif)  
  
 [!code-csharp[System.Drawing.UsingAPen#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.UsingAPen#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e4fe2-110">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="e4fe2-110">Compiling the Code</span></span>  
  
-   <span data-ttu-id="e4fe2-111">Crear un formulario de Windows y controlar el formato <xref:System.Windows.Forms.Control.Paint> eventos.</span><span class="sxs-lookup"><span data-stu-id="e4fe2-111">Create a Windows Form and handle the form's <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="e4fe2-112">Pegue el código de ejemplo en el <xref:System.Windows.Forms.Control.Paint> controlador de eventos pasando `e` como <xref:System.Windows.Forms.PaintEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="e4fe2-112">Paste the example code into the <xref:System.Windows.Forms.Control.Paint> event handler passing `e` as <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4fe2-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4fe2-113">See also</span></span>

- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- <xref:System.Drawing.Drawing2D.LineCap?displayProperty=nameWithType>
- [<span data-ttu-id="e4fe2-114">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e4fe2-114">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="e4fe2-115">Utilizar lápiz para dibujar líneas y formas</span><span class="sxs-lookup"><span data-stu-id="e4fe2-115">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
