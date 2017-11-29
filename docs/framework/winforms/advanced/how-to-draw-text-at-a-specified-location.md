---
title: "Cómo: Dibujar texto en una ubicación especificada"
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
helpviewer_keywords:
- text [Windows Forms], drawing at specified locations [Windows Forms]
- drawing text
- drawing text [Windows Forms], specified locations [Windows Forms]
- Windows Forms, drawing text a a specified location
ms.assetid: 60816423-1c38-465e-980d-2c2b64d74086
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: aab9570b98caec5b3975a5b3ff6f1e62d4ad303b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-text-at-a-specified-location"></a><span data-ttu-id="ca14a-102">Cómo: Dibujar texto en una ubicación especificada</span><span class="sxs-lookup"><span data-stu-id="ca14a-102">How to: Draw Text at a Specified Location</span></span>
<span data-ttu-id="ca14a-103">Al realizar un dibujo personalizado, puede dibujar texto en una sola línea horizontal a partir de un punto especificado.</span><span class="sxs-lookup"><span data-stu-id="ca14a-103">When you perform custom drawing, you can draw text in a single horizontal line starting at a specified point.</span></span> <span data-ttu-id="ca14a-104">Se puede dibujar el texto de esta manera, mediante el uso de la <xref:System.Drawing.Graphics.DrawString%2A> sobrecargar el método de la <xref:System.Drawing.Graphics> clase que toma un <xref:System.Drawing.Point> o <xref:System.Drawing.PointF> parámetro.</span><span class="sxs-lookup"><span data-stu-id="ca14a-104">You can draw text in this manner by using the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method of the <xref:System.Drawing.Graphics> class that takes a <xref:System.Drawing.Point> or <xref:System.Drawing.PointF> parameter.</span></span> <span data-ttu-id="ca14a-105">El <xref:System.Drawing.Graphics.DrawString%2A> método también requiere una <xref:System.Drawing.Brush> y<xref:System.Drawing.Font></span><span class="sxs-lookup"><span data-stu-id="ca14a-105">The <xref:System.Drawing.Graphics.DrawString%2A> method also requires a <xref:System.Drawing.Brush> and <xref:System.Drawing.Font></span></span>  
  
 <span data-ttu-id="ca14a-106">También puede usar el <xref:System.Windows.Forms.TextRenderer.DrawText%2A> sobrecargar el método de la <xref:System.Windows.Forms.TextRenderer> que toma un <xref:System.Drawing.Point>.</span><span class="sxs-lookup"><span data-stu-id="ca14a-106">You can also use the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> overloaded method of the <xref:System.Windows.Forms.TextRenderer> that takes a <xref:System.Drawing.Point>.</span></span> <span data-ttu-id="ca14a-107"><xref:System.Windows.Forms.TextRenderer.DrawText%2A>También requiere un <xref:System.Drawing.Color> y <xref:System.Drawing.Font>.</span><span class="sxs-lookup"><span data-stu-id="ca14a-107"><xref:System.Windows.Forms.TextRenderer.DrawText%2A> also requires a <xref:System.Drawing.Color> and a <xref:System.Drawing.Font>.</span></span>  
  
 <span data-ttu-id="ca14a-108">En la siguiente ilustración muestra el resultado del texto dibujado en un punto especificado cuando se usa el <xref:System.Drawing.Graphics.DrawString%2A> el método sobrecargado.</span><span class="sxs-lookup"><span data-stu-id="ca14a-108">The following illustration shows the output of text drawn at a specified point when you use the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method.</span></span>  
  
 <span data-ttu-id="ca14a-109">![Texto de las fuentes](../../../../docs/framework/winforms/advanced/media/csfontstext1.png "csfontstext1")</span><span class="sxs-lookup"><span data-stu-id="ca14a-109">![Fonts Text](../../../../docs/framework/winforms/advanced/media/csfontstext1.png "csfontstext1")</span></span>  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a><span data-ttu-id="ca14a-110">Para dibujar una línea de texto con GDI +</span><span class="sxs-lookup"><span data-stu-id="ca14a-110">To draw a line of text with GDI+</span></span>  
  
1.  <span data-ttu-id="ca14a-111">Use la <xref:System.Drawing.Graphics.DrawString%2A> método, pasando el texto que desee, <xref:System.Drawing.Point> o <xref:System.Drawing.PointF>, <xref:System.Drawing.Font>, y <xref:System.Drawing.Brush>.</span><span class="sxs-lookup"><span data-stu-id="ca14a-111">Use the <xref:System.Drawing.Graphics.DrawString%2A> method, passing the text you want, <xref:System.Drawing.Point> or <xref:System.Drawing.PointF>, <xref:System.Drawing.Font>, and <xref:System.Drawing.Brush>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#30)]
     [!code-vb[System.Drawing.AlignDrawnText#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#30)]  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a><span data-ttu-id="ca14a-112">Para dibujar una línea de texto con GDI</span><span class="sxs-lookup"><span data-stu-id="ca14a-112">To draw a line of text with GDI</span></span>  
  
1.  <span data-ttu-id="ca14a-113">Use la <xref:System.Windows.Forms.TextRenderer.DrawText%2A> método, pasando el texto que desee, <xref:System.Drawing.Point>, <xref:System.Drawing.Font>, y <xref:System.Drawing.Color>.</span><span class="sxs-lookup"><span data-stu-id="ca14a-113">Use the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method, passing the text you want, <xref:System.Drawing.Point>, <xref:System.Drawing.Font>, and <xref:System.Drawing.Color>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#40](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#40)]
     [!code-vb[System.Drawing.AlignDrawnText#40](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#40)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ca14a-114">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="ca14a-114">Compiling the Code</span></span>  
 <span data-ttu-id="ca14a-115">Los ejemplos anteriores requieren:</span><span class="sxs-lookup"><span data-stu-id="ca14a-115">The previous examples require:</span></span>  
  
-   <span data-ttu-id="ca14a-116"><xref:System.Windows.Forms.PaintEventArgs>  `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="ca14a-116"><xref:System.Windows.Forms.PaintEventArgs>  `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca14a-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca14a-117">See Also</span></span>  
 [<span data-ttu-id="ca14a-118">Dibujar texto con GDI</span><span class="sxs-lookup"><span data-stu-id="ca14a-118">How to: Draw Text with GDI</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)  
 [<span data-ttu-id="ca14a-119">Utilizar fuentes y texto</span><span class="sxs-lookup"><span data-stu-id="ca14a-119">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [<span data-ttu-id="ca14a-120">Construir fuentes y familias de fuentes</span><span class="sxs-lookup"><span data-stu-id="ca14a-120">How to: Construct Font Families and Fonts</span></span>](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)  
 [<span data-ttu-id="ca14a-121">Dibujar texto ajustado en un rectángulo</span><span class="sxs-lookup"><span data-stu-id="ca14a-121">How to: Draw Wrapped Text in a Rectangle</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-wrapped-text-in-a-rectangle.md)
