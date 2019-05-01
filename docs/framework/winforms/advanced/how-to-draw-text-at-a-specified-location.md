---
title: Procedimiento para dibujar texto en una ubicación especificada
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing at specified locations [Windows Forms]
- drawing text
- drawing text [Windows Forms], specified locations [Windows Forms]
- Windows Forms, drawing text at a specified location
ms.assetid: 60816423-1c38-465e-980d-2c2b64d74086
ms.openlocfilehash: f7834ea45db8dd6e971defd9c3b2b152ffddf512
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62004065"
---
# <a name="how-to-draw-text-at-a-specified-location"></a><span data-ttu-id="8c0c9-102">Procedimiento para dibujar texto en una ubicación especificada</span><span class="sxs-lookup"><span data-stu-id="8c0c9-102">How to: Draw Text at a Specified Location</span></span>
<span data-ttu-id="8c0c9-103">Al realizar dibujos personalizados, puede dibujar texto en una sola línea horizontal a partir de un punto especificado.</span><span class="sxs-lookup"><span data-stu-id="8c0c9-103">When you perform custom drawing, you can draw text in a single horizontal line starting at a specified point.</span></span> <span data-ttu-id="8c0c9-104">Puede dibujar texto mediante el uso de esta manera el <xref:System.Drawing.Graphics.DrawString%2A> sobrecargar el método de la <xref:System.Drawing.Graphics> clases que toman un <xref:System.Drawing.Point> o <xref:System.Drawing.PointF> parámetro.</span><span class="sxs-lookup"><span data-stu-id="8c0c9-104">You can draw text in this manner by using the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method of the <xref:System.Drawing.Graphics> class that takes a <xref:System.Drawing.Point> or <xref:System.Drawing.PointF> parameter.</span></span> <span data-ttu-id="8c0c9-105">El <xref:System.Drawing.Graphics.DrawString%2A> método también requiere una <xref:System.Drawing.Brush> y <xref:System.Drawing.Font></span><span class="sxs-lookup"><span data-stu-id="8c0c9-105">The <xref:System.Drawing.Graphics.DrawString%2A> method also requires a <xref:System.Drawing.Brush> and <xref:System.Drawing.Font></span></span>  
  
 <span data-ttu-id="8c0c9-106">También puede usar el <xref:System.Windows.Forms.TextRenderer.DrawText%2A> sobrecargar el método de la <xref:System.Windows.Forms.TextRenderer> que toma un <xref:System.Drawing.Point>.</span><span class="sxs-lookup"><span data-stu-id="8c0c9-106">You can also use the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> overloaded method of the <xref:System.Windows.Forms.TextRenderer> that takes a <xref:System.Drawing.Point>.</span></span> <span data-ttu-id="8c0c9-107"><xref:System.Windows.Forms.TextRenderer.DrawText%2A> También requiere un <xref:System.Drawing.Color> y un <xref:System.Drawing.Font>.</span><span class="sxs-lookup"><span data-stu-id="8c0c9-107"><xref:System.Windows.Forms.TextRenderer.DrawText%2A> also requires a <xref:System.Drawing.Color> and a <xref:System.Drawing.Font>.</span></span>  
  
 <span data-ttu-id="8c0c9-108">La siguiente ilustración muestra el resultado del texto dibujado en un punto especificado cuando se usa el <xref:System.Drawing.Graphics.DrawString%2A> método sobrecargado.</span><span class="sxs-lookup"><span data-stu-id="8c0c9-108">The following illustration shows the output of text drawn at a specified point when you use the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method.</span></span>  
  
 ![Captura de pantalla que muestra la salida de texto en un punto especificado.](./media/how-to-draw-text-at-a-specified-location/font-text-specified-point.png)  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a><span data-ttu-id="8c0c9-110">Para dibujar una línea de texto con GDI +</span><span class="sxs-lookup"><span data-stu-id="8c0c9-110">To draw a line of text with GDI+</span></span>  
  
1. <span data-ttu-id="8c0c9-111">Use la <xref:System.Drawing.Graphics.DrawString%2A> método, pasando el texto que desee, <xref:System.Drawing.Point> o <xref:System.Drawing.PointF>, <xref:System.Drawing.Font>, y <xref:System.Drawing.Brush>.</span><span class="sxs-lookup"><span data-stu-id="8c0c9-111">Use the <xref:System.Drawing.Graphics.DrawString%2A> method, passing the text you want, <xref:System.Drawing.Point> or <xref:System.Drawing.PointF>, <xref:System.Drawing.Font>, and <xref:System.Drawing.Brush>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#30)]
     [!code-vb[System.Drawing.AlignDrawnText#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#30)]  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a><span data-ttu-id="8c0c9-112">Para dibujar una línea de texto con GDI</span><span class="sxs-lookup"><span data-stu-id="8c0c9-112">To draw a line of text with GDI</span></span>  
  
1. <span data-ttu-id="8c0c9-113">Use la <xref:System.Windows.Forms.TextRenderer.DrawText%2A> método, pasando el texto que desee, <xref:System.Drawing.Point>, <xref:System.Drawing.Font>, y <xref:System.Drawing.Color>.</span><span class="sxs-lookup"><span data-stu-id="8c0c9-113">Use the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method, passing the text you want, <xref:System.Drawing.Point>, <xref:System.Drawing.Font>, and <xref:System.Drawing.Color>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#40)]
     [!code-vb[System.Drawing.AlignDrawnText#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#40)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8c0c9-114">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="8c0c9-114">Compiling the Code</span></span>  
 <span data-ttu-id="8c0c9-115">Los ejemplos anteriores requieren:</span><span class="sxs-lookup"><span data-stu-id="8c0c9-115">The previous examples require:</span></span>  
  
- <span data-ttu-id="8c0c9-116"><xref:System.Windows.Forms.PaintEventArgs>  `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="8c0c9-116"><xref:System.Windows.Forms.PaintEventArgs>  `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c0c9-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="8c0c9-117">See also</span></span>

- [<span data-ttu-id="8c0c9-118">Cómo: Dibujar texto con GDI</span><span class="sxs-lookup"><span data-stu-id="8c0c9-118">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
- [<span data-ttu-id="8c0c9-119">Utilizar fuentes y texto</span><span class="sxs-lookup"><span data-stu-id="8c0c9-119">Using Fonts and Text</span></span>](using-fonts-and-text.md)
- [<span data-ttu-id="8c0c9-120">Cómo: Construir fuentes y familias de fuentes</span><span class="sxs-lookup"><span data-stu-id="8c0c9-120">How to: Construct Font Families and Fonts</span></span>](how-to-construct-font-families-and-fonts.md)
- [<span data-ttu-id="8c0c9-121">Cómo: Dibujar texto ajustado en un rectángulo</span><span class="sxs-lookup"><span data-stu-id="8c0c9-121">How to: Draw Wrapped Text in a Rectangle</span></span>](how-to-draw-wrapped-text-in-a-rectangle.md)
