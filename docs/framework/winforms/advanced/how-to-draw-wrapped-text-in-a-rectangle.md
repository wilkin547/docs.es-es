---
title: Procedimiento Dibujar texto ajustado en un rectángulo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drawing text in a rectangle
- text [Windows Forms], drawing in a rectangle
- strings [Windows Forms], drawing in a rectangle
ms.assetid: e1fb432a-dc90-48b5-9b6b-acc14507133d
ms.openlocfilehash: 4afe3eb7c3525dac856751331117e0980063faad
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54602954"
---
# <a name="how-to-draw-wrapped-text-in-a-rectangle"></a><span data-ttu-id="dd735-102">Procedimiento Dibujar texto ajustado en un rectángulo</span><span class="sxs-lookup"><span data-stu-id="dd735-102">How to: Draw Wrapped Text in a Rectangle</span></span>
<span data-ttu-id="dd735-103">Puede dibujar texto ajustado en un rectángulo mediante el uso de la <xref:System.Drawing.Graphics.DrawString%2A> sobrecargar el método de la <xref:System.Drawing.Graphics> clases que toman un <xref:System.Drawing.Rectangle> o <xref:System.Drawing.RectangleF> parámetro.</span><span class="sxs-lookup"><span data-stu-id="dd735-103">You can draw wrapped text in a rectangle by using the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method of the <xref:System.Drawing.Graphics> class that takes a <xref:System.Drawing.Rectangle> or <xref:System.Drawing.RectangleF> parameter.</span></span> <span data-ttu-id="dd735-104">También se puede utilizar un <xref:System.Drawing.Brush> y un <xref:System.Drawing.Font>.</span><span class="sxs-lookup"><span data-stu-id="dd735-104">You will also use a <xref:System.Drawing.Brush> and a <xref:System.Drawing.Font>.</span></span>  
  
 <span data-ttu-id="dd735-105">También puede dibujar texto ajustado en un rectángulo mediante el uso de la <xref:System.Windows.Forms.TextRenderer.DrawText%2A> sobrecargar el método de la <xref:System.Windows.Forms.TextRenderer> que toma un <xref:System.Drawing.Rectangle> y un <xref:System.Windows.Forms.TextFormatFlags> parámetro.</span><span class="sxs-lookup"><span data-stu-id="dd735-105">You can also draw wrapped text in a rectangle by using the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> overloaded method of the <xref:System.Windows.Forms.TextRenderer> that takes a <xref:System.Drawing.Rectangle> and a <xref:System.Windows.Forms.TextFormatFlags> parameter.</span></span> <span data-ttu-id="dd735-106">También se puede utilizar un <xref:System.Drawing.Color> y un <xref:System.Drawing.Font>.</span><span class="sxs-lookup"><span data-stu-id="dd735-106">You will also use a <xref:System.Drawing.Color> and a <xref:System.Drawing.Font>.</span></span>  
  
 <span data-ttu-id="dd735-107">La siguiente ilustración muestra el resultado del texto dibujado en el rectángulo, cuando se usa el <xref:System.Drawing.Graphics.DrawString%2A> método.</span><span class="sxs-lookup"><span data-stu-id="dd735-107">The following illustration shows the output of text drawn in the rectangle when you use the <xref:System.Drawing.Graphics.DrawString%2A> method.</span></span>  
  
 <span data-ttu-id="dd735-108">![Texto de las fuentes](../../../../docs/framework/winforms/advanced/media/csfontstext2.png "csfontstext2")</span><span class="sxs-lookup"><span data-stu-id="dd735-108">![Fonts Text](../../../../docs/framework/winforms/advanced/media/csfontstext2.png "csfontstext2")</span></span>  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a><span data-ttu-id="dd735-109">Para dibujar texto ajustado en un rectángulo con GDI +</span><span class="sxs-lookup"><span data-stu-id="dd735-109">To draw wrapped text in a rectangle with GDI+</span></span>  
  
1.  <span data-ttu-id="dd735-110">Use la <xref:System.Drawing.Graphics.DrawString%2A> método sobrecargado, pasando el texto que desee, <xref:System.Drawing.Rectangle> o <xref:System.Drawing.RectangleF>, <xref:System.Drawing.Font> y <xref:System.Drawing.Brush>.</span><span class="sxs-lookup"><span data-stu-id="dd735-110">Use the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method, passing the text you want, <xref:System.Drawing.Rectangle> or <xref:System.Drawing.RectangleF>, <xref:System.Drawing.Font> and <xref:System.Drawing.Brush>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#50](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#50)]
     [!code-vb[System.Drawing.AlignDrawnText#50](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#50)]  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a><span data-ttu-id="dd735-111">Para dibujar texto ajustado en un rectángulo con GDI</span><span class="sxs-lookup"><span data-stu-id="dd735-111">To draw wrapped text in a rectangle with GDI</span></span>  
  
1.  <span data-ttu-id="dd735-112">Use la <xref:System.Windows.Forms.TextFormatFlags> se debe ajustar el valor de enumeración para especificar el texto con el <xref:System.Windows.Forms.TextRenderer.DrawText%2A> método sobrecargado, pasando el texto que desee, <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Font> y <xref:System.Drawing.Color>.</span><span class="sxs-lookup"><span data-stu-id="dd735-112">Use the <xref:System.Windows.Forms.TextFormatFlags> enumeration value to specify the text should be wrapped with the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> overloaded method, passing the text you want, <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Font> and <xref:System.Drawing.Color>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#60](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#60)]
     [!code-vb[System.Drawing.AlignDrawnText#60](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#60)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="dd735-113">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="dd735-113">Compiling the Code</span></span>  
 <span data-ttu-id="dd735-114">Los ejemplos anteriores requieren:</span><span class="sxs-lookup"><span data-stu-id="dd735-114">The previous examples require:</span></span>  
  
-   <span data-ttu-id="dd735-115"><xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="dd735-115"><xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd735-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd735-116">See also</span></span>
- [<span data-ttu-id="dd735-117">Cómo: Dibujar texto con GDI</span><span class="sxs-lookup"><span data-stu-id="dd735-117">How to: Draw Text with GDI</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)
- [<span data-ttu-id="dd735-118">Utilizar fuentes y texto</span><span class="sxs-lookup"><span data-stu-id="dd735-118">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
- [<span data-ttu-id="dd735-119">Cómo: Construir fuentes y familias de fuentes</span><span class="sxs-lookup"><span data-stu-id="dd735-119">How to: Construct Font Families and Fonts</span></span>](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)
- [<span data-ttu-id="dd735-120">Cómo: Dibujar texto en una ubicación especificada</span><span class="sxs-lookup"><span data-stu-id="dd735-120">How to: Draw Text at a Specified Location</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-at-a-specified-location.md)
